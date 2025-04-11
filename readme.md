# 학급 관계도 애플리케이션

학생들의 관계를 시각화하고 주간식 정보를 관리하는 웹 애플리케이션입니다.

## 기능

- 학급 관리 (추가, 수정, 삭제)
- 학생 관리 (추가, 수정, 삭제)
- 학생 간 관계 설정 및 시각화
- 주간식 설문 관리

## 기술 스택

- Backend: Flask, SQLAlchemy
- Frontend: HTML, CSS, JavaScript, D3.js
- Database: SQLite (개발), PostgreSQL (배포)

## 로컬 개발 환경 설정

1. 저장소 클론
   ```
   git clone <repository-url>
   cd student_relationship_html
   ```

2. 가상 환경 설정 (선택 사항)
   ```
   python -m venv venv
   source venv/bin/activate  # Windows의 경우: venv\Scripts\activate
   ```

3. 의존성 설치
   ```
   pip install -r requirements.txt
   ```

4. 애플리케이션 실행
   ```
   python app.py
   ```

5. 브라우저에서 `http://localhost:5000` 접속

## Render.com 배포 방법

1. [Render](https://render.com) 계정 가입 및 로그인

2. PostgreSQL 데이터베이스 생성
   - Dashboard에서 "New +" > "PostgreSQL"
   - 이름 설정 및 필요한 설정 구성
   - 생성 후 "Internal Database URL" 복사 (Web Service 환경 변수 설정에 사용)

3. Web Service 생성
   - Dashboard에서 "New +" > "Web Service"
   - GitHub 저장소 연결
   - 이름 설정
   - 환경: "Python 3"
   - 빌드 명령: `pip install -r requirements.txt`
   - 시작 명령: `gunicorn app:app`
   - 환경 변수 설정:
     - `DATABASE_URL`: PostgreSQL 데이터베이스 URL
     - `FLASK_ENV`: production

4. 배포 시작
   - "Create Web Service" 클릭
   - 배포 과정 모니터링

## 라이센스

이 프로젝트는 MIT 라이센스로 제공됩니다.
