# convert_mp4

영상 파일(주로 MKV)을 재인코딩 없이 MP4로 바꾸는 macOS용 bash 스크립트입니다.

## 특징
- 모든 비디오, 오디오 트랙을 그대로 복사하고, 변환 후 원본과 데이터가 같은지 검증합니다. 다르면 결과물을 지우며, 원본은 건드리지 않습니다.
- 촬영 일시, 챕터, 커버 이미지 같은 메타데이터와 파일 생성일, 수정일, Finder 태그를 옮깁니다.
- MP4에 넣을 수 없는 자막은 별도 파일로 꺼내 둡니다.
- HEVC는 hvc1 태그로 저장해 Final Cut Pro와 QuickTime에서 열리게 합니다.

## 설치

```
brew install ffmpeg
git clone https://github.com/Limeheron/convert-mp4.git
mkdir -p ~/.local/bin
cp convert-mp4/convert_mp4 ~/.local/bin/
```

- `~/.local/bin`이 PATH에 있어야 합니다.

## 사용법

```
convert_mp4 녹화.mkv
convert_mp4 ~/Movies/*.mkv
```

- 결과물은 원본과 같은 폴더에 같은 이름의 .mp4로 만듭니다.
- 자세한 설명은 `convert_mp4 -h`로 봅니다.

## 제한
- 컨테이너만 바꾸므로, MP4나 Final Cut Pro가 지원하지 않는 코덱은 재인코딩이 필요합니다.
