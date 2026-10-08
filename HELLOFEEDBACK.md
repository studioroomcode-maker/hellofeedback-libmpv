# hellofeedback-libmpv

[HelloFeedback](https://studioroomkr.com) Windows 버전에 들어가는 **LGPL libmpv** 빌드 레시피입니다.
[shinchiro/mpv-winbuild-cmake](https://github.com/shinchiro/mpv-winbuild-cmake)를 포크해서 아래만 바꿨습니다.

- `packages/ffmpeg.cmake`: `--enable-gpl` 과 GPL 전용 라이브러리(x264, x265, davs2, rubberband, dvdnav/dvdread, avisynth, zvbi) 제거. 디코더는 전부 켬 → ProRes, DNxHD, QuickTime Animation, CineForm, HAP 재생 가능. `--enable-version3` 이므로 FFmpeg 은 LGPLv3.
- `packages/mpv.cmake`: `-Dgpl=false` (LGPL), dvdnav·rubberband 끔.
- `.github/workflows/hellofeedback.yml`: x86_64 하나만 빌드하고 결과(`mpv-dev-x86_64-*.7z`)를 릴리스로 올림. 라이선스 플래그를 확인하는 단계 포함.

빌드: Actions → **HelloFeedback libmpv (LGPL)** → Run workflow.

## License

mpv(LGPLv2.1+), FFmpeg(LGPLv3+) 및 각 라이브러리의 라이선스를 따릅니다. 이 저장소의 원본 빌드 스크립트 라이선스는 상위 저장소를 따릅니다.
