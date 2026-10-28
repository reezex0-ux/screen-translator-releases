# 화면 번역기 (Screen Translator)

Windows 화면의 글자를 OCR로 읽어 한국어로 번역해 옆 패널이나 원문 위에
보여 주는 앱입니다. OCR과 번역은 모두 PC 안에서 처리하며, 화면이나 글을
외부로 보내지 않습니다.

이 저장소에는 설치 파일만 올립니다.

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

## 모델

모델은 설치 파일에 들어 있지 않고, 앱에서 고른 모델만 받습니다.

| 모델 | 크기 | 라이선스 |
|---|---|---|
| QuickMT (기본, 영·일 → 한) | 약 400MB | CC BY 4.0 |
| MT2 1.8B (Tencent Hy-MT2) | 약 1.1GB | Apache 2.0 |
| Qwen3 4B Instruct | 약 2.5GB | Apache 2.0 |
| Kanana 1.5 2.1B (카카오) | 약 1.5GB | Apache 2.0 |
| NLLB 600M / 1.3B (Meta) | 약 650MB / 1.4GB | CC BY-NC 4.0 (비상업) |

MT2·Qwen3·Kanana는 llama.cpp의 llama-server(약 32MB)를 함께 받습니다.
받은 모델은 `%LOCALAPPDATA%\ScreenTranslator`에 저장되고, 앱을 제거할 때
지울지 물어봅니다.

## 오픈소스 라이선스

설치 폴더의 `THIRD_PARTY_NOTICES.txt`(시작 메뉴 **오픈소스 라이선스**)에
앱에 들어 있는 Python, Qt(PySide6, LGPL-3.0), ONNX Runtime, RapidOCR,
CTranslate2 등의 라이선스가 있습니다.
