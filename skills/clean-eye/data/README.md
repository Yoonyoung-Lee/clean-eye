# data/sample_personas.json — 여기에 넣을 것

이 스킬은 **기본적으로 이 폴더의 `sample_personas.json`을 읽어서 동작한다.** huggingface.co 접속이 막힌 환경(Enterprise 코드 실행 샌드박스 등)에서도 네트워크 호출 없이 바로 쓸 수 있게 하기 위함이다.

## 생성 방법 (huggingface.co 접속 가능한 로컬/Colab에서, 최초 1회)

```bash
pip install huggingface_hub pyarrow
python scripts/download.py --shards 2
python scripts/search.py \
  --age-min 20 --age-max 60 \
  --large-corp-proxy \
  --diversity sex,age_band,occupation_root \
  --persona-types summary,professional \
  --n 15 \
  --out data/sample_personas.json
```

생성된 `data/sample_personas.json`을 이 스킬 폴더(`clean-eye/data/`) 안에 그대로 두고, 전체 폴더를 다시 zip으로 압축해서 claude.ai에 업로드하면 된다.

## 왜 15명인가

`--n 15` 정도로 넉넉하게 뽑아두면, 실제 평가 시 화면 성격에 맞게 이 15명 중 5명 안팎을 골라 쓸 수 있다 (예: 연령대 다양하게, 또는 특정 직군 위주로). 스킬 사용 시 이 파일 안에서 서브셋을 고르는 것이지, 매번 새로 뽑는 게 아니다.

## 갱신하고 싶을 때

이 15명 풀이 너무 좁게 느껴지면, huggingface.co 접속 가능한 환경에서 위 명령을 다시 실행해서 (다른 `--seed` 값으로) `data/sample_personas.json`을 교체하면 된다. 조직 네트워크 허용 도메인에 huggingface.co가 추가되면, `SKILL.md`의 "실시간 재검색" 절차(Step 1~2, 선택사항)를 따로 써도 된다.

## 파일이 없을 때

`data/sample_personas.json`이 없으면 스킬은 사용자에게 이 파일이 없다는 것과, 위 생성 절차를 안내한다. 임의로 페르소나를 지어내지 않는다 (지어낸 경우 반드시 "실제 데이터셋 기반 아님"이라고 명시 — `SKILL.md` 참고).
