# Persona Chatbot (Historical Figure)

Original PS16 mini project by Saanvi Rajendra Dhote, Roll No. 16, LY CORE 3 (https://github.com/Saanvi1710/llm-ps16-16).

Interface redesign (front end only: `app/static/index.html`, `app/static/styles.css`) and new screenshots by Sujal Ganesh Deshmukh, LY Core 5, Roll No. 16. The backend, API, database and persona prompts are unchanged from the original.

This educational FastAPI application lets students ask questions to a clearly labeled AI role-play of a historical figure. Supported figures are Mahatma Gandhi, Rani Lakshmibai, Dr. B. R. Ambedkar, and Nelson Mandela.

## Run locally

1. Create and activate a virtual environment.
2. Install dependencies with `pip install -r requirements.txt`.
3. Copy `.env.example` to `.env` and set `OPENAI_API_KEY`.
4. Run `uvicorn app.main:app --reload`.
5. Open `http://127.0.0.1:8000`.

The application stores messages in SQLite and uses SQLAlchemy for persistence. Its persona prompts require factual answers, clear uncertainty, and no claims about events after a figure's death. Every assistant message is labeled AI role-play.

## Screenshots

The interface uses a split layout: a side rail with the title and the AI role-play notice, and a chat pane beside it. Only the front end (`app/static/index.html` and `app/static/styles.css`) was redesigned; the API, database, persona prompts and behavior are unchanged.

Home screen and AI role-play label:

![Home screen and AI role-play label](screenshots/new-ui-01-home.png)

Answer from Mahatma Gandhi:

![Answer from Mahatma Gandhi](screenshots/new-ui-02-gandhi-answer.png)

Factuality guardrail (no knowledge of events after the figure's death):

![Factuality guardrail](screenshots/new-ui-03-factuality-guardrail.png)

Switching to another figure (Nelson Mandela):

![Nelson Mandela conversation](screenshots/new-ui-04-mandela.png)

Mobile layout:

![Mobile layout](screenshots/new-ui-05-mobile.png)

Error shown when `OPENAI_API_KEY` is not set:

![Missing API key error](screenshots/new-ui-06-real-backend-no-api-key.png)

Note: in the new screenshots 02-05, the replies come from a stand-in for the OpenAI call because no API key was available when they were captured. With a key in `.env`, the app returns real model replies in the same layout. The original screenshots from the first version remain in `screenshots/test-*.png`.
