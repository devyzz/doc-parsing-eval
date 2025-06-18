# doc-parsing-eval
문서 파싱/추출 라이브러리의 성능을 비교 평가하는 프로젝트입니다. 

**👾 [unstructured.io open source](https://docs.unstructured.io/open-source/introduction/overview#common-use-cases)**

## 🔧 프로젝트 구조

```csharp
doc-parsing-eval/
├── README.md                     # 프로젝트 개요 및 실행 방법 설명
├── pyproject.toml                # poetry 설정 파일 (dependencies, scripts 등 정의)
├── poetry.lock                   # poetry가 관리하는 의존성 버전 고정 파일
├── data/                         # 테스트용 원본 문서 디렉토리
│   └── sample_docs/              # 샘플 문서 보관 (pdf, docx, html 등)
├── results/                      # 문서 추출 결과 저장 디렉토리
│   ├── unstructured/             # unstructured로 추출한 결과 저장
│   └── docling/                  # docling 결과 저장 예정 (후속 실험용)
├── notebooks/                    # 실험용 Jupyter 노트북 디렉토리
│   ├── 01_run_unstructured.ipynb # unstructured 테스트용 노트북
│   └── 02_run_docling.ipynb      # (예정) docling 테스트용 노트북
├── .gitignore                    # 캐시, 가상환경 등 Git에 포함하지 않을 항목 지정
└── .venv/                        # poetry의 로컬 가상환경 (옵션: `poetry config virtualenvs.in-project true` 시 생성)
              
```
---

## 🧪 테스트 대상 문서 예시
- PDF 리포트
- docx 논문 파일
- HTML 뉴스 아티클

다양한 포맷과 길이의 문서를 포함하여 테스트합니다.

---

## 실행 방법

### 1. 환경 설정
```bash
# 프로젝트 디렉토리로 이동
cd doc-parsing-eval
# poetry 초기화
poetry init --name doc-parsing-eval --python ">=3.9,<3.12"
# 필요한 패키지 설치
poetry add jupyter unstructured pdfminer.six python-docx
# Jupyter 커널 등록
poetry run python -m ipykernel install --user --name=doc-parsing-eval
```
---

## 📌 테스트 기준
- 문서 파싱 속도
- 텍스트 추출 정확도
- 메타데이터 추출 가능 여부
- 다양한 문서 포맷에 대한 지원 여부
---

## 📅 향후 계획
- [ ] `docling` 비교 테스트 추가
