# 화면 번역기 (Screen Translator)

선택한 화면의 영어·일본어를 PC에서 한국어로 번역하고 읽어 주는 Windows 앱입니다.
현재 Windows 앱 구현은 Rust이며, 설치와 업데이트는 Microsoft Store에서 제공합니다.

**[Microsoft Store에서 설치](https://apps.microsoft.com/detail/9P98RX98ZXSH)**

- Windows 10 2004 이상·Windows 11, x64
- 화면·원문·번역문·합성 음성을 외부 AI 서비스로 보내지 않습니다.
- OCR·QuickMT 기본 번역·음성 합성은 CPU에서 실행합니다. GPU 실행기는 선택 사항입니다.
- 모델은 앱에서 선택해 별도로 받으며, 다운로드 후에는 오프라인으로 사용할 수 있습니다.
- 기존 설정과 모델을 유지해 업데이트합니다. 앱을 제거할 필요가 없습니다.

## v0.7.45

[변경 내역과 패키지](https://github.com/reezex0-ux/screen-translator-releases/releases/tag/native-v0.7.45)

번역 패널의 원문 보기, 배율, 음성, 읽어주기를 같은 높이로 정렬했습니다.
배율과 음성 선택 상자의 모양을 맞추고, 배율 상자에는 100%처럼 선택한 값만 표시합니다.

Microsoft Store 제출 8은 인증을 통과한 뒤 자동으로 게시됩니다. GitHub에 첨부된 MSIX는 Store 제출용 서명 전 패키지입니다.

## 사용 방법

1. 앱의 모델 받기로 OCR·선택한 번역 모델을 준비합니다.
2. 읽기 영역을 글자 위에 두고 시작 또는 Ctrl+Alt+T를 누릅니다.
3. 번역을 옆 패널에서 읽거나 원문 위에 표시합니다. 번역 패널은 분리하거나 접을 수 있습니다.
4. 음성 모델을 받은 뒤 여성 5종·남성 5종 중 목소리를 골라 읽어주기를 누릅니다.

번역 모델은 QuickMT, MT2, Qwen3 4B, Kanana 2.1B, NLLB 600M·1.3B를 선택할 수 있습니다.
NLLB 모델 가중치는 CC BY-NC 4.0에 따라 비상업적 용도로만 사용할 수 있습니다.
앱에 포함된 모델·실행기·오픈소스 고지는 제목 영역의 오른쪽 메뉴에서 확인할 수 있습니다.

## 지원과 이전 버전

- [지원 게시판](https://github.com/reezex0-ux/screen-translator-releases/issues)
- [개인정보처리방침](PRIVACY-native.md)
- [전체 릴리스](https://github.com/reezex0-ux/screen-translator-releases/releases)

과거 Python 설치판과 포터블판은 이력으로 남겨 두며, 이번 버전의 배포 경로는 Microsoft Store입니다.
