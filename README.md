# Custom Audio Manager

Custom Audio Manager(CAM)의 Windows 배포판을 받는 저장소입니다. CAM은 Windows 다채널 오디오 라우팅, VST2/VST3 플러그인 호스팅, LPCM/공간음향 출력, 애트모스 바이패스와 리시버 볼륨 제어를 제공하는 앱입니다.

이 저장소에는 개발 이력이나 소스 트리를 두지 않습니다. 배포판은 버전마다 [Releases](https://github.com/weirdsoup/CAM-releases/releases)에 올라갑니다. 각 버전의 소스는 같은 Release의 소스 ZIP에 들어 있습니다.

## 받을 파일

| 파일 | 내용 |
| --- | --- |
| `CustomAudioManager-<버전>.zip` | 실행 파일, 설치·업데이트·롤백 스크립트, 사용 안내(`README.ko.md`), 릴리스 노트, 라이선스 고지 |
| `CustomAudioManager-<버전>-source.zip` | 그 버전의 소스. JUCE는 들어 있지 않으며 빌드 방법은 ZIP 안의 `README.md`에 있습니다. |
| `release-verification.txt` | 배포 전 자동 검사 기록(패키지 구성, 설치·롤백, 개인정보 검사) |

Release 본문에 세 파일의 SHA-256이 있습니다. 받은 파일이 손상되지 않았는지 PowerShell에서 확인할 수 있습니다.

```powershell
Get-FileHash .\CustomAudioManager-0.11.3.zip -Algorithm SHA256
```

파일 이름의 버전은 받은 Release에 맞게 바꿉니다.

## 설치와 업데이트

- **처음 사용** ZIP을 쓰기 가능한 폴더에 모두 풀고 `CustomAudioManager.exe`를 실행합니다.
- **업데이트** ZIP을 기존 CAM 폴더 밖의 다른 폴더에 풀고 `Install.cmd`를 실행합니다. 기존 설정·프로필과 가져온 TAG DLL은 그대로 남습니다.
- **되돌리기** 업데이트한 뒤 기존 설치 폴더에서 `Rollback.cmd`를 실행하면 직전 백업을 복원합니다.

설치 위치 조건, 화면별 기능, 진단 방법은 ZIP 안의 `README.ko.md`에 있습니다. 버전별 변경 사항은 Release 본문과 ZIP 안의 `RELEASE-NOTES.ko.md`에 있습니다.

## 따로 설치하는 구성요소

아래 구성요소는 CAM 배포판에 들어 있지 않습니다. 필요한 경우 각 배포처에서 받아 설치하고 각자의 라이선스를 따릅니다.

- VB-CABLE 등 가상 오디오 장치
- 오디오 인터페이스 드라이버
- TAG v2 드라이버와 공식 x64 `tagapi.dll`(앱 안의 `TAG DLL 설정`에서 가져옵니다)
- 사용할 VST2/VST3 플러그인
- AVR/DSP 펌웨어

## 라이선스

CAM의 자체 작성 코드는 [MIT License](LICENSE)를 따릅니다. 배포판에 포함되거나 빌드에 쓰인 외부 구성요소는 각자의 라이선스를 따르며, 요약은 [NOTICE.md](NOTICE.md)에 있습니다. 고지 원문은 각 ZIP의 `THIRD_PARTY.md`, `THIRD_PARTY_LICENSES.txt`, `licenses/`에 있습니다.
