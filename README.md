# pvre-threads-media

PVRE 대만 Threads 계정(`@pvrepharmacy_taiwan`) 발행용 **이미지 호스팅**.

Threads(Meta) API는 이미지를 파일 업로드로 받지 않는다. 컨테이너를 만들 때 `image_url` 에 **공개 URL** 을 주면
Meta 서버가 그 주소로 이미지를 가져간다. 그래서 공개 저장소가 필요하다.

## 규칙

- 경로는 **내용 해시**로 정한다: `img/<sha256 앞 2자>/<sha256>.<jpg|png>`
  같은 이미지는 같은 주소가 되고, 주소가 한 번 정해지면 내용이 바뀌지 않는다(CDN 캐시 문제 없음).
- 공개 URL: `https://raw.githubusercontent.com/thyoon-pvre/pvre-threads-media/main/<경로>`
- 규격: JPEG/PNG · 8MB 이하 · 폭 320~1440px (발행 도구가 첨부 시점에 검사한다)

## 여기에 올리면 안 되는 것

이 저장소는 **공개**이고, 지운 파일도 git 이력에 남는다.

- 손님 얼굴·SNS 인증사진 등 개인을 알아볼 수 있는 자료 (리뷰 인증 판독 자료는 절대 금지)
- 매장 매출·원가 등 내부 수치가 보이는 이미지
- 계약서·신분증·처방전

발행용으로 제작한 마케팅 이미지만 올린다.
