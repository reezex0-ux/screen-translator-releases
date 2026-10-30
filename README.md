# 화면 번역기 (Screen Translator)

Windows 화면의 글자를 OCR로 읽어 한국어로 번역해 옆 패널이나 원문 위에
보여 주는 앱입니다. OCR·번역·읽어주기는 모두 PC 안에서 처리하며, 화면이나 글을
외부로 보내지 않습니다.

이 저장소에는 설치 파일만 올립니다.

현재 배포 버전은 **v0.15.14**입니다.

- 원문 위 번역은 배경 색상의 보색(파랑→주황, 빨강→청록 등)으로 칠하고, 확대 외곽선으로
  표시합니다. 흰색·검정·회색 배경에서는 원문 글자색의 보색이나 하늘색·파랑을 씁니다.
- 읽기 영역 안 왼쪽 아래의 점 손잡이를 끌어 크기를 조절합니다.
- 배경은 투명하며 원문과 그림을 사각형으로 덮지 않습니다.
- 긴 영어 줄을 뒤집힌 글자로 잘못 읽어 깨뜨리던 OCR 문제를 고쳤습니다(v0.15.14).
- CJK 세로글은 위에서 아래로, 열은 오른쪽에서 왼쪽으로 표시합니다.

## 내려받기

**[최신 설치 파일 받기](https://github.com/reezex0-ux/screen-translator-releases/releases/latest/download/ScreenTranslator-Setup.exe)**
· [모든 버전](https://github.com/reezex0-ux/screen-translator-releases/releases)

- Windows 10/11 64비트
- 관리자 권한 없이 사용자 계정에 설치됩니다.
- 코드 서명이 없어 처음 실행할 때 Windows SmartScreen 경고가 뜰 수 있습니다.
  **추가 정보 → 실행**을 누르면 됩니다. 각 릴리스에 SHA-256을 적어 둡니다.

## 쓰는 법

1. 설치 후 실행하면 돋보기 모양의 읽기 영역과 번역 패널이 뜹니다.
2. 패널의 **모델 내려받기**로 번역 모델을 받습니다. 기본 모델 QuickMT는
   약 400MB이고 GPU 없이 CPU로 번역합니다.
3. 읽기 영역을 번역할 글자 위에 두고 **시작**(또는 `Ctrl+Alt+T`)을 누릅니다.
4. 돋보기와 번역 패널 사이 연결부를 클릭하면 패널을 접거나 펼칩니다.
5. 번역이 끝나면 **여성1~5·남성1~5** 중 음성을 고르고 그 오른쪽의 **읽어주기**를
   누릅니다. 패널을 접었을 때는 읽기 영역 아래 탭에서 읽습니다.
   기본은 여성4입니다. 처음 사용할 때 음성 모델 약 401MB를 받으며 CPU에서
   합성합니다. 첫 문장이 준비되면 바로 읽기 시작하고, 재생하는 동안 다음 문장을 준비합니다.
   **중지**로 재생을 멈춥니다. CUDA 설치는 필요하지 않습니다.
6. 머리글의 **업데이트 확인** 버튼을 누르면 새 버전이 있는지 확인합니다. 새 버전이 있으면
   **업데이트 설치**를 눌러 설치 파일을 받고(SHA-256 확인), 앱이 닫혔다가 새
   버전으로 다시 열립니다. 누르기 전에는 인터넷에 접속하지 않습니다.
   v0.14.0부터 있는 기능이라, v0.13.0 이하에서는 위 링크로 한 번 직접 설치합니다.

## 모델

모델은 설치 파일에 들어 있지 않고, 앱에서 고른 모델만 받습니다.

| 모델 | 크기 | 라이선스 |
|---|---|---|
| QuickMT (기본, 영·일 → 한) | 약 400MB | CC BY 4.0 |
| MT2 1.8B (Tencent Hy-MT2) | 약 1.1GB | Apache 2.0 |
| Qwen3 4B Instruct | 약 2.5GB | Apache 2.0 |
| Kanana 1.5 2.1B (카카오) | 약 1.5GB | Apache 2.0 |
| NLLB 600M / 1.3B (Meta) | 약 650MB / 1.4GB | CC BY-NC 4.0 (비상업) |
| Supertonic 3 (한국어 읽어주기, 음성 10종) | 약 401MB | [Open RAIL-M](https://huggingface.co/supertone-oss-archive/supertonic-3/blob/aafc6e32416a594460b32413efc49d7fe4ce6d46/LICENSE) |

MT2·Qwen3·Kanana는 llama.cpp의 llama-server(약 32MB)를 함께 받습니다.
받은 모델은 `%LOCALAPPDATA%\ScreenTranslator`에 저장되고, 앱을 제거할 때
지울지 물어봅니다.

## 오픈소스 라이선스

설치 폴더의 `THIRD_PARTY_NOTICES.txt`(시작 메뉴 **오픈소스 라이선스**)에
앱에 들어 있는 Python, Qt(PySide6, LGPL-3.0), ONNX Runtime, RapidOCR,
CTranslate2 등의 라이선스가 있습니다.
