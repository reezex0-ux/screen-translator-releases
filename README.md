# 화면 번역기 (Screen Translator)

선택한 화면의 영어·일본어를 PC에서 한국어로 번역하고 읽어 주는 Windows 앱입니다.
현재 Windows 앱 구현은 Rust이며, 설치와 업데이트는 Microsoft Store에서 제공합니다.

**[Microsoft Store에서 설치](https://apps.microsoft.com/detail/9P98RX98ZXSH)**

- Windows 10 2004 이상·Windows 11, x64
- 화면·원문·번역문·합성 음성을 외부 AI 서비스로 보내지 않습니다.
- OCR·QuickMT 기본 번역·음성 합성은 CPU에서 실행합니다. GPU 실행기는 선택 사항입니다.
- 모델은 앱에서 선택해 별도로 받으며, 다운로드 후에는 오프라인으로 사용할 수 있습니다.
- 기존 설정과 모델을 유지해 업데이트합니다. 앱을 제거할 필요가 없습니다.

## v0.7.44

[변경 내역과 패키지](https://github.com/reezex0-ux/screen-translator-releases/releases/tag/native-v0.7.44)

글자가 없던 영역의 OCR 캐시가 3초 뒤 만료되어 새 자막을 다시 읽습니다.
CUDA 초기화에 실패하면 CPU 실행으로 대체하고 실행기 표시를 실제 상태에 맞춥니다.
실행기 복구 시 정상 DLL을 유지하고 파일 교체가 실패하면 원래 파일을 복원합니다.
기존 설정과 모델을 유지하는 0.7.43→0.7.44 업데이트 설치를 확인했습니다.

GitHub 릴리스 게시와 Store 인증·공개는 별개입니다. Store에서는 Microsoft가 승인한 버전을 받습니다.
첨부 MSIX는 Store 제출용 서명 전 패키지이며 일반 설치용이 아닙니다.
추가 화면·GPU 재현은 하지 않았으므로 실사용 화면 멈춤 해소는 미확인입니다.

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
