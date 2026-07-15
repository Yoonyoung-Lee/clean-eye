# Nemotron-Personas-Korea 필드 스키마 (요약)

> 출처: https://huggingface.co/datasets/nvidia/Nemotron-Personas-Korea (CC BY 4.0, NVIDIA)
> 총 26개 필드, 100만 행, 텍스트는 모두 한국어.

## 식별자

- `uuid`: 32자 hex 고유 식별자

## 인구통계 (필터 키)

| 필드 | 카디널리티 | 예시 |
|---|---|---|
| `sex` | 2 | 남자/여자 |
| `age` | 19~99 정수 | |
| `marital_status` | 4 | 미혼/배우자있음/사별/이혼 |
| `military_status` | 2 | 병역필/해당없음 |
| `family_type` | 39 | 가구 구성 |
| `housing_type` | 6 | 아파트/단독주택 등 |
| `education_level` | 7 | 초등학교 졸업 ~ 대학원 졸업 |
| `bachelors_field` | 11 | 공학/인문/사회 등 |
| `occupation` | 자유 텍스트 | "응용 소프트웨어 개발자" 등 |
| `district` | 252 | `{province}-시군구` 포맷 |
| `province` | 17 | 광역 단위 |
| `country` | 1 | "대한민국" 고정 |

**주의: 회사 규모(대기업/중소기업) 필드는 존재하지 않는다.** 이것이 `corp-proxy-keywords.md`에서 근사 필터가 필요한 이유다.

## 페르소나 텍스트 (7종)

`persona`(종합) · `professional_persona`(직업) · `sports_persona` · `arts_persona` · `travel_persona` · `culinary_persona` · `family_persona`

## 보조 컨텍스트 필드

`cultural_background`, `skills_and_expertise` / `_list`, `hobbies_and_interests` / `_list`, `career_goals_and_ambitions`

## 라이선스

CC BY 4.0 — 상업/비상업 자유, 저작자 표기 필수. 이 스킬이 생성하는 산출물에는 다음 문구를 포함할 것:

> 본 페르소나는 NVIDIA Nemotron-Personas-Korea (CC BY 4.0)의 합성 데이터를 기반으로 한다.
