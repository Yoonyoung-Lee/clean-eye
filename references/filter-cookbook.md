# 필터 쿡북

## 옵션 요약

| 옵션 | 의미 |
|---|---|
| `--age-min N` / `--age-max N` | 연령 범위 |
| `--large-corp-proxy` | occupation 화이트리스트 + 대졸이상 (근사 필터) |
| `--sex` / `--province` / `--district` | 인구통계 |
| `--education-level` | 학력 정확 일치 (단일값) |
| `--keywords A,B` | 페르소나 텍스트 부분일치 (OR) |
| `--diversity LIST` | 다양성 샘플링 축 |
| `--n` | 결과 개수 |
| `--persona-types` | 출력할 페르소나 텍스트 종류 |
| `--out PATH` | 저장 경로 |

## 패턴 1: 기본 — 20~60세 대기업 직장인 8명 (성별·연령대·직군 다양)

```bash
python scripts/search.py \
  --age-min 20 --age-max 60 \
  --large-corp-proxy \
  --diversity sex,age_band,occupation_root \
  --persona-types summary,professional \
  --n 8 \
  --out _workspace/personas.json
```

## 패턴 2: 특정 화면 도메인에 맞춰 좁히기 (예: 사내 ERP/그룹웨어 화면)

```bash
python scripts/search.py \
  --age-min 25 --age-max 55 \
  --large-corp-proxy \
  --keywords "회계,인사,결재,보고서" \
  --diversity sex,age_band \
  --n 6
```

## 패턴 3: 연령대별 비교가 필요할 때 (세대 간 화면 이해도 격차 확인)

```bash
python scripts/search.py --age-min 20 --age-max 29 --large-corp-proxy --n 4 --out _workspace/p20s.json
python scripts/search.py --age-min 50 --age-max 60 --large-corp-proxy --n 4 --out _workspace/p50s.json
```

## 결과 비어있을 때

- `--large-corp-proxy` 조건이 너무 좁으면 `OCCUPATION_WHITELIST`(search.py 상단)에 직군 키워드 추가
- `--age-min/max` 범위를 넓히기
- `education_level` 하한을 낮추려면 `search.py`의 `EDU_LEVEL_MIN_DEFAULT`를 직접 수정 (단, 이 경우 "대기업" 근사 신뢰도가 낮아짐을 인지)
