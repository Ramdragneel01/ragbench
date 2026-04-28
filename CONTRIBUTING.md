# Contributing

## Development Setup

1. Install Python 3.12+ and Node.js 20+.
2. Copy `.env.example` to `.env`.
3. Install backend and frontend dependencies.
4. Run tests and builds before opening a pull request.

## Local Validation

```bash
cd backend
pip install -r requirements.txt
pytest -q

cd ../frontend
npm install
npm run build
```

## Pull Request Requirements

1. Keep changes scoped to one concern.
2. Include updated docs for behavior changes.
3. Add future clarification notes for non-obvious design choices.
