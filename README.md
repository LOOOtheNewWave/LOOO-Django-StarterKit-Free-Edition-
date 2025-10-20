## 🚀 **LOOO Django StarterKit (Free Edition)**

> 💡 Launch Once, Operate Often
> 
> 
> 빠르게 시작하고, 오래 유지할 수 있는 Django 스타터킷
> 

---

## 🧩 **프로젝트 개요**

> LOOO Django StarterKit은 학생·초급 개발자를 위한
> 
> 
> “즉시 실행 가능한 Django 백엔드 환경”을 제공합니다.
> 
> Docker 기반으로 손쉽게 개발·테스트·배포가 가능하며,
> 
> SQLite와 MySQL 두 가지 데이터베이스 옵션을 모두 지원합니다.
> 

---

## 🧱 **기본 구성**

| 구성 요소 | 설명 |
| --- | --- |
| ⚙️ Django 5 + DRF 3.x | RESTful API 기본 구조 |
| 🗄️ MySQL (Docker) | 실서버용 DB 환경 |
| 💾 SQLite | 빠른 로컬 테스트용 DB |
| 🧰 CRUD API (Post 예시) | `/api/posts/` 기본 엔드포인트 제공 |
| 🐳 Docker Compose | `up --build` 한 줄 실행 구조 |

---

## 📂 **폴더 구조**

```bash
LOOO-DJANGO/
│
├── backend/                  # Django 프로젝트 루트
│   ├── config/               # 프로젝트 전역 설정
│   │   ├── settings.py       # 환경변수 기반 DB 자동 분기
│   │   ├── urls.py
│   │   ├── wsgi.py
│   │   ├── asgi.py
│   │   └── __init__.py
│   │
│   ├── core/                 # 기본 CRUD 기능 (예시 앱)
│   │   ├── models.py
│   │   ├── serializers.py
│   │   ├── views.py
│   │   ├── urls.py
│   │   ├── __init__.py
│   │   └── migrations/
│   │        └─ __init__.py
│   │
│   ├── manage.py             # Django 명령 실행 엔트리포인트 
│   ├──.env                   # 실제 실행 환경 변수 파일
│   ├──.env.example           # 환경 변수 예시 파일
│   ├──db.sqlite3             # SQLite 모드 실행 시 자동 생성              
│   ├──Dockerfile             # Django 백엔드 컨테이너 빌드 설정
│   └──requirements.txt       # Python 패키지 의존성
│
├── docker-compose.yml        # Django + DB 통합 실행 (MySQL 또는 SQLite)  
└── README.md
```

---

## ⚙️ **환경변수 설정 (.env)**

📄 `.env.example` → `.env` 로 복사 후 수정하세요.

```bash
cp .env.example .env
```

### 예시:

```bash
# 🌐 기본 설정
SECRET_KEY=dev-secret
DEBUG=True
ALLOWED_HOSTS=*

# 🧱 데이터베이스
DB_ENGINE=mysql       # 또는 sqlite
DB_NAME=looo_db
DB_USER=root
DB_PASSWORD=password
DB_HOST=db
DB_PORT=3306

# 🐍 Django 서버
BACKEND_PORT=8000
API_URL=http://localhost:8000
```

---

## 🐳 **실행 방법**

1️⃣ **프로젝트 클론**

```bash
git clone https://github.com/yourname/looo-django.git
cd looo-django
```

2️⃣ **환경변수 세팅**

```bash
cp .env.example .env
```

3️⃣ **Docker 실행**

```bash
docker compose up --build
```

4️⃣ **DB 마이그레이션**

```bash
docker compose exec backend python manage.py makemigrations
docker compose exec backend python manage.py migrate
```

5️⃣ **API 테스트**

```bash
http://localhost:8000/api/posts/
```

---

## 🔄 **DB 선택 가이드**

| 목적 | 추천 DB | 설명 |
| --- | --- | --- |
| ⚡ 빠른 테스트 | SQLite | 파일 기반, 설정 불필요 |
| 🚀 실제 배포 | MySQL | Docker로 자동 실행 |

👉 `.env`의 `DB_ENGINE` 값만 바꾸면 자동 전환됩니다.

---

## 🧠 **테스트 실행**

```bash
docker compose exec backend python manage.py test
```

🆚 Free 🩵 vs Pro 🧡 Edition
기능 구분	LOOO Django StarterKit 🩵 (Free)	LOOO DevKit 🧡 (Pro)
⚙️ Django 버전	Django 5 + DRF 3.x	Django 5 + DRF 3.x + JWT 인증
🧩 앱 구조	단일 앱(core) 예시	다중 앱 구조 + User/Auth 모듈
💾 데이터베이스	SQLite + MySQL 지원	PostgreSQL + MySQL + 환경 자동분기
🐳 Docker 구성	Backend + DB 단일 Compose	Nginx + Backend + DB + Static 멀티 컨테이너
🧰 API 예시	/api/posts/ CRUD	게시물 + 사용자 + 알림 API
🔒 인증/보안	기본 Django Auth (선택적)	JWT 토큰 기반 Auth / CORS 세팅
📘 문서화	README + 실행 가이드	Swagger UI + Postman Collection 자동 생성
🧠 테스트 코드	미포함 (필요시 작성)	pytest + coverage 기본 지원
🧱 배포 구성	개발용 Docker 환경	CI/CD (GitHub Actions + Render or AWS)
🎨 UI/UX	API 전용 백엔드	React + Tailwind 샘플 대시보드
💡 대상 사용자	학생 / 초급 개발자 / 학습용	스타트업 / 프로덕트 팀 / 실서비스용
💰 라이선스	MIT License (무료)	LOOO Pro License (상용 가능)
🧩 Pro Edition 추가 기능 예정

🔑 JWT + Custom User Model 기본 세팅

📄 Swagger / Postman 자동 문서화

☁️ S3 또는 Cloudinary 정적 파일 저장

🧱 Docker 멀티스테이지 빌드

⚙️ GitHub Actions CI/CD 파이프라인

💡 Free로 시작하고 Pro로 확장하세요.
한 번 배운 구조로, 실서비스까지 연결되는 LOOO 스타터킷.

## 🪶 **License**

MIT License © 2025 **LOOO**

> 자유롭게 사용, 수정, 배포 가능하나 출처 표시는 유지해주세요.
> 

---

📘 **LOOO — 한 번 배우면, 계속 써먹을 수 있는 풀스택 스타터킷.**

> 빠르게, 간결하게, 그리고 무한히. ♾️
>
