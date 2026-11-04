# convert_mp4

영상 파일의 컨테이너를 재인코딩 없이 MP4로 바꾸는 macOS용 Bash 스크립트

Final Cut Pro에서 소스 작업을 할 때 컨테이너만 MP4로 바꾸는 작업이 필요해서 만든 스크립트다.

## 사용법

```
convert_mp4 <파일경로> [파일경로 ...]
```

- `-h`, `-help`, `--help`: 사용법 출력

```
convert_mp4 ~/Movies/녹화.mkv
convert_mp4 ~/Movies/*.mkv
```

- 예: ~/Movies/녹화.mkv는 ~/Movies/녹화.mp4로 저장된다.
    - MP4에 넣을 수 없는 자막: 녹화.kor.srt처럼 별도 파일

## 필요 환경

- ffmpeg, ffprobe

```
brew install ffmpeg
```

## 참고

- 모든 트랙을 그대로 복사하고, 원본과 데이터가 다르면 결과물을 지운다.
- 같은 이름의 파일이 있으면 덮어쓰지 않고 녹화_1.mp4처럼 저장한다.
- 촬영 일시, 챕터 같은 메타데이터와 파일 생성일, 수정일을 옮긴다.
- Final Cut Pro가 지원하지 않는 코덱(VP9, AV1, Opus 등)은 재인코딩이 필요하다.
