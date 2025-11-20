# LEfSe

LEfSe (Linear discriminant analysis Effect Size) 생물정보학 분석 도구입니다.

## 개요

LEfSe는 클래스 간 차이를 설명하는 특징(생물체, 클레이드, OTU, 유전자, 기능)을 결정하는 생물정보학 분석 도구입니다. 통계적 유의성 검정과 생물학적 일관성 및 효과 관련성 검정을 결합합니다.

## 주요 기능

- 선형 판별 분석 (LDA) 기반 효과 크기 계산
- 클래스 간 차별적 특징 식별
- 클래도그램(cladogram) 시각화
- 특징 플롯 생성
- 결과 플롯 생성

## 사용 방법

### 기본 실행

```bash
python lefse/lefse_run.py <input_file> <output_file>
```

### 입력 파일 포맷 변환

```bash
python lefse/lefse_format_input.py <input_file> <output_file>
```

### 시각화

```bash
# 클래도그램
python lefse/lefse_plot_cladogram.py <input_file> <output_file>

# 특징 플롯
python lefse/lefse_plot_features.py <input_file> <output_file>

# 결과 플롯
python lefse/lefse_plot_res.py <input_file> <output_file>
```

## 요구사항

- Python 3.12
- R (v. 3.6 이상)
- R 라이브러리: survival, mvtnorm, modeltools, coin, MASS
- Python 라이브러리: rpy2, numpy, matplotlib, scipy, cython, biom-format

## 설치

### uv 설치

#### Windows
```powershell
# PowerShell에서 실행
irm https://astral.sh/uv/install.ps1 | iex
```

#### macOS / Linux
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

설치 후 터미널을 재시작하거나 다음 명령어로 PATH에 추가:
```bash
export PATH="$HOME/.cargo/bin:$PATH"
```

### 가상환경 설정

```bash
# Python 3.12 가상환경 생성
uv venv --python 3.12

# 가상환경 활성화
# Windows (PowerShell)
.venv\Scripts\Activate.ps1

# macOS / Linux
source .venv/bin/activate
```

### Python 패키지 설치

```bash
# uv를 사용한 패키지 설치
uv pip install -r requirements.txt
```

### R 및 R 라이브러리

```r
install.packages(c("survival", "mvtnorm", "modeltools", "coin", "MASS"))
```

### Conda를 통한 설치 (권장)

```bash
conda install -c bioconda lefse
```

### Docker를 통한 설치

```bash
docker run -it biobakery/lefse bash
```

## 파일 구조

- `lefse/`: LEfSe 메인 모듈
  - `lefse.py`: 메인 LEfSe 분석
  - `lefse_run.py`: 실행 스크립트
  - `lefse_format_input.py`: 입력 파일 포맷 변환
  - `lefse_plot_cladogram.py`: 클래도그램 시각화
  - `lefse_plot_features.py`: 특징 플롯 시각화
  - `lefse_plot_res.py`: 결과 플롯 시각화
  - `qiime2lefse.py`: QIIME2 형식 변환
- `lefsebiom/`: BIOM 형식 지원 모듈
- `setup.py`: 설치 스크립트

## 입력 데이터 형식

LEfSe는 특정 형식의 입력 파일이 필요합니다. `lefse_format_input.py`를 사용하여 데이터를 변환할 수 있습니다.

## 참고

- LEfSe는 Galaxy 모듈, Conda, Docker, bioBakery (VM 및 클라우드)에서도 사용 가능합니다.
- 자세한 정보는 [LEfSe 논문](http://www.ncbi.nlm.nih.gov/pubmed/21702898)을 참조하세요.
- 지원 포럼: [bioBakery Support Forum](https://forum.biobakery.org/c/Downstream-analysis-and-statistics/LEfSe)

---

해당 프로젝트는 Examples-Python의 Private Repository에서 공개 가능한 수준의 소스를 Public Repository로 변환한 것입니다.
