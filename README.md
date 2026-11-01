# Mini Browser Web API Tools

> Single File Web App: No install, no build, no server required to run.

서버 전송 및 백엔드 런타임 없이 브라우저 내장 Web API(HTML5 Canvas, FileReader, Blob 등)를 활용하여 동작하는 경량 웹 도구 모음이다.

## Core Principles
- 100% 로컬 연산: 사용자가 선택한 파일이 외부 서버로 전송되지 않고 브라우저 메모리 내부에서만 즉시 처리되어 개인정보 및 데이터 보안을 유지.
- 무설치 구동: Browser만 있으면 운영체제 구분 없이 HTML 파일을 더블 클릭하여 즉시 실행 가능.
- Browser Native Web API 활용: Canvas API(CanvasRenderingContext2D), File API, File System Access API, Drag and Drop API 등을 처리 엔진으로 사용.

## Tools

### 이미지 형식 변환기 (image-converter.html)
- 지원 포맷: PNG, JPEG, WebP 등 브라우저 지원 형식 상호 변환.
- 기능: 여러 이미지를 큐(Queue)에 등록하여 원하는 포맷 및 해상도로 일괄 변환/리사이징.
- UX: 비율 유지 리사이즈(가로/세로 지정), 품질(Quality) 압축 슬라이더, 개별 다운로드.
- 사용 기술: HTMLCanvasElement.toBlob(), createImageBitmap(), FileReader.

### 이미지 자르기 도구 (image-cropper.html)
- 기능: 단일 이미지에 대해 인터랙티브 크롭 박스를 조작하여 원하는 영역만 정밀하게 잘라내기.
- UX: 마우스 드래그를 통한 자유 비율 또는 고정 종횡비(1:1, 4:3, 16:9) 영역 지정, 실시간 미리보기.
- 핵심 기술: 순수 2D Canvas 렌더링, 오프스크린 캔버스를 통한 무손실 픽셀 슬라이싱(drawImage).

### PDF 파일 병합기 (pdf-merger.html)
- 기능: 여러 개의 PDF 문서를 로컬에서 하나의 단일 PDF 파일로 결합.
- UX: 파일 드래그 앤 드롭 업로드, 순서 변경(재정렬), 병합 실행 및 저장.
- 사용 기술: 클라이언트 사이드 스트림 바이트 병합, 브라우저 Blob URL 생성(URL.createObjectURL).

### ASCII 트리 다이어그램 생성기 (text-diagram-tree.html)
- 기능: 들여쓰기된 텍스트 목록을 터미널 및 마크다운에 적합한 계층적 ASCII/UTF-8 트리 다이어그램으로 실시간 변환.
- UX: 실시간 2단 에디터, 주석(#) 열 자동 정렬(Aligned Comment) 토글, 테마 전환(Dark/Light), 원클릭 클립보드 복사.
- 사용 기술: 정규식 기반 들여쓰기 깊이 측정, 스택 기반 트리 순회 알고리즘, 전각 문자 폭 계산(Visual Width)을 통한 주석 위치 보정.

### 텍스트 에디터 (text-editor.html)
- 기능: 다중 탭 기반 경량 텍스트 편집기, 파일 직접 열기 및 로컬 원본 파일 직접 덮어쓰기 저장/다른 이름으로 저장.
- UX: 탭 세션 관리, 줄 번호 거터 동기 스크롤, 정규식 지원 찾기/바꾸기(Ctrl+F), 자동 줄바꿈, 괄호 자동 닫기, 모노크롬 다크/라이트 테마, 드래그 앤 드롭 파일 로드.
- 사용 기술: File System Access API(showOpenFilePicker, showSaveFilePicker, FileSystemFileHandle), TextDecoder(UTF-8 / EUC-KR 감지 및 재인코딩), LocalStorage(작업 상태 자동 보존).

### 텍스트 변환기 (text-converter.html)
- 기능: 대소문자 변환, 프로그래밍 케이스(camel, Pascal, snake, kebab 등), 줄 정리/정렬, 인코딩/디코딩(URL, Base64, HTML, Hex, JWT 등), 유니코드 스타일 올인원 변환.
- UX: 원본-결과 2단 뷰, 실시간 자동 변환(Live Mode) 및 줄 단위 개별 처리 옵션, 결과 재입력(연속 체이닝 변환), 텍스트 통계(글자/단어/줄/바이트), 규칙 가이드 모달.
- 사용 기술: 정규식 기반 토큰 분해 및 문자열 알고리즘, TextEncoder/TextDecoder, Web Clipboard API, Blob URL 다운로드.

### 미니 계산기 (mini-calculator.html)
- 기능: Desmos 스타일 수식 직접 입력(암시적 곱셈 및 미완성 괄호 자동 보정), 삼각함수/로그/팩토리얼 등 공학 연산, 각도 모드(RAD/DEG), 직전 계산값(Ans) 및 히스토리 테이프 재사용.
- UX: 키패드 클릭과 키보드 타이핑 동시 지원, 실시간 연산 결과 프리뷰, 자릿수 얇은 공백(Thin Space) 가독성 서식화, 원본 숫자 원클릭 복사, 수식 문법 도움말 모달.
- 사용 기술: 토크나이저 및 클라이언트 사이드 수식 파서(Implicit Math Parser), Web Storage API(LocalStorage 히스토리 보존), Web Clipboard API.

## 실행 방법 (Usage)
1. 파일 관리자에서 원하는 기능의 HTML 파일(image-converter.html, image-cropper.html, pdf-merger.html, text-diagram-tree.html, text-editor.html, text-converter.html, mini-calculator.html)을 더블 클릭한다.
2. 시스템 기본 브라우저(Chrome, Firefox, Whale, Edge 등)에서 즉시 도구가 열린다.
3. 작업 완료 후 결과물을 로컬 드라이브에 직접 다운로드한다.
