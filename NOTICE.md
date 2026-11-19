# 외부 구성요소 고지

이 문서는 [Releases](https://github.com/weirdsoup/CAM-releases/releases)의 CAM 배포판에 들어 있는 외부 구성요소를 요약합니다. 정본은 각 버전 ZIP의 `THIRD_PARTY.md`, `THIRD_PARTY_LICENSES.txt`, `licenses/`입니다. 이 요약과 다르면 해당 버전 ZIP의 고지를 따릅니다.

## CAM 자체 작성 코드

- 라이선스: [MIT License](LICENSE)
- 범위: CAM이 직접 작성한 소스·테스트·스크립트·설치 스크립트·자산과 VST2 어댑터 헤더.
- 소스 ZIP의 JUCE 패치(`patches/*.patch`)는 CAM이 추가·변경한 줄(`+`)만 MIT입니다. 패치의 문맥 줄과 삭제 줄은 JUCE 원본에서 발췌한 것이므로 JUCE 라이선스를 따릅니다.

## 실행 파일에 포함된 구성요소

`CustomAudioManager.exe`는 아래 코드를 포함해 빌드됩니다.

| 구성요소 | 라이선스 | 고지 파일(`licenses/`) |
| --- | --- | --- |
| JUCE 8.0.15 | JUCE 8 Starter License | `JUCE-LICENSE.md` |
| Steinberg VST3 SDK(JUCE 내장) | MIT | `VST3-MIT.txt` |
| JUCE 내장 라이브러리: FLAC, Ogg Vorbis, HarfBuzz, JPEG, PNG, SheenBidi, zlib | 각 라이브러리의 BSD·MIT·IJG·libpng·Apache 2.0·zlib 계열 라이선스 | `FLAC-BSD.txt`, `Ogg-Vorbis-BSD.txt`, `HarfBuzz.txt`, `JPEG.txt`, `PNG.txt`, `SheenBidi-Apache-2.0.txt`, `zlib.txt` |
| VST2 호환 헤더(Xaymar, DPF) | BSD·ISC | `Xaymar-BSD.txt`, `DPF-ISC.txt` |

ASIO는 모든 빌드에서 끄므로(`JUCE_ASIO=0`) Steinberg ASIO SDK는 포함하지 않습니다. 독점 Steinberg VST2 SDK도 포함하거나 참조하지 않습니다.

## 함께 배포하는 별도 프로그램

- NirSoft SoundVolumeCommandLine(`svcl.exe`, `svcl.chm`, `readme.txt`): NirSoft의 프리웨어입니다. 배포 조건에 따라 원본 세 파일을 수정하지 않고 함께 넣습니다. CAM의 MIT License는 이 파일들에 적용되지 않습니다. 배포 조건은 `licenses/NirSoft-readme.txt`에 있습니다.

## 포함하지 않는 구성요소

- TAG SDK와 `tagapi.dll`은 배포판에 넣지 않으며 정적 링크하지 않습니다. 사용자가 공식 배포처에서 받은 x64 `tagapi.dll`을 앱 안에서 가져오면 실행 중에 불러옵니다.
- 사용자가 따로 설치하는 가상 오디오 장치, 드라이버, 플러그인, 펌웨어는 각자의 라이선스를 따릅니다.
