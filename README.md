# Mini Browser Web API Tools

서버 전송 및 백엔드 런타임 없이 브라우저 내장 Web API(HTML5 Canvas, FileReader, Blob 등)를 활용하여 100% 클라이언트 사이드 컴퓨팅(Client-side Computing)으로 동작하는 경량 웹 도구 모음이다.

## 1. 핵심 아키텍처 원칙 (Core Principles)
- 100% 로컬 연산: 사용자가 선택한 파일이 외부 서버로 전송되지 않고 브라우저 메모리 내부에서만 즉시 처리되어 개인정보 및 데이터 보안을 유지.
- 무설치 구동: 브라우저만 있으면 운영체제 구분 없이 HTML 파일을 더블 클릭하여 즉시 실행 가능.
- 내장 Web API 활용: Canvas API(CanvasRenderingContext2D), File API, Drag and Drop API 등을 핵심 처리 엔진으로 사용.

## 2. 제공 도구 목록 (Tools)

### 2.1 이미지 일괄 변환기 (image-converter.html)
- 기능: 여러 이미지를 큐(Queue)에 등록하여 원하는 포맷 및 해상도로 일괄 변환/리사이징.
- 지원 포맷: PNG, JPEG, WebP 등 브라우저 지원 형식 상호 변환.
- 조절 옵션: 비율 유지 리사이즈(가로/세로 지정), 품질(Quality) 압축 슬라이더, 개별 다운로드.
- 핵심 기술: HTMLCanvasElement.toBlob(), createImageBitmap(), FileReader.

### 2.2 이미지 크롭 도구 (image-cropper.html)
- 기능: 단일 이미지에 대해 인터랙티브 크롭 박스를 조작하여 원하는 영역만 정밀하게 잘라내기.
- 조작 인터랙션: 마우스 드래그를 통한 자유 비율 또는 고정 종횡비(1:1, 4:3, 16:9) 영역 지정, 실시간 미리보기.
- 핵심 기술: 순수 2D Canvas 렌더링, 오프스크린 캔버스를 통한 무손실 픽셀 슬라이싱(drawImage).

### 2.3 PDF 병합기 (pdf-merger.html)
- 기능: 여러 개의 PDF 문서를 로컬에서 하나의 단일 PDF 파일로 결합.
- 조작 인터랙션: 파일 드래그 앤 드롭 업로드, 순서 변경(재정렬), 병합 실행 및 저장.
- 핵심 기술: 클라이언트 사이드 스트림 바이트 병합, 브라우저 Blob URL 생성(URL.createObjectURL).

## 3. 실행 방법 (Usage)
1. 파일 관리자에서 원하는 기능의 HTML 파일(image-converter.html, image-cropper.html, pdf-merger.html)을 더블 클릭한다.
2. 시스템 기본 브라우저(Chrome, Firefox, Whale, Edge 등)에서 즉시 도구가 열린다.
3. 작업 완료 후 결과물을 로컬 드라이브에 직접 다운로드한다.
