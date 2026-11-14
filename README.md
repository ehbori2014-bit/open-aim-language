<h1 align="center">open-aim · 다국어판</h1>

<p align="center">
  실제 VALORANT 맵에서 하는 오프라인 에임 트레이너.<br>
  <b>한국어 · 日本語 · 中文 · English</b>로 쓸 수 있어요.
</p>

<p align="center">
  <a href="../../releases/latest"><b>Windows용 다운로드</b></a>
  &nbsp;·&nbsp;
  <a href="#언어-설정">언어 설정</a>
  &nbsp;·&nbsp;
  <a href="#소스로-실행하기">소스로 실행하기</a>
  &nbsp;·&nbsp;
  <a href="#출처">출처</a>
  &nbsp;·&nbsp;
  <a href="#english">English</a>
</p>

<p align="center">
  <img src="docs/images/v1.3/hero-sunset.png" alt="Sunset 맵에서 RGX 밴달로 봇과 훈련하는 화면" width="100%">
</p>

> [!NOTE]
> 이 저장소는 **[unkwsr/open-aim](https://github.com/unkwsr/open-aim)** 을 바탕으로 만든 포크예요.
> 원본의 훈련 기능은 그대로 두고, **설정에 Language 탭과 한국어·일본어·중국어 번역**을 더했어요.
> 원본 제작자는 [@unkwsr](https://github.com/unkwsr) 님이고, 이 포크는 원작자와 관계없이 따로 관리돼요.

<br>

## 이 포크에서 달라진 점

- **설정 → Language 탭:** Audio, Visuals 다음에 새 탭이 생겼어요. 국기와 그 나라 말로 쓴 언어 이름이 나오고, 하나를 누르면 화면이 다시 불러와지면서 바로 바뀌어요.

  | 국기 | 언어 | 상태 |
  |:---:|---|---|
  | 🇺🇸 | English | 원본과 같음 |
  | 🇰🇷 | 한국어 | 전체 번역 완료 |
  | 🇯🇵 | 日本語 | 번역 중 (메뉴와 설정은 완료, 나머지는 영어로 표시) |
  | 🇨🇳 | 中文 | 게임 원문(중국어) + open-aim 추가 화면 번역 |

- **기계 번역 말투를 줄인 번역:** 메뉴, 설정, 드릴 이름과 설명을 일상적인 말투로 옮겼어요. 한국어는 해요체, 일본어는 です・ます체를 쓰고, 맵·요원·무기 이름은 게임의 공식 현지화 이름을 따랐어요.
- **번역이 없는 줄은 영어로:** 한 줄 안에서 한국어와 영어가 뒤섞이지 않도록, 번역이 없는 줄은 원래 영어 문장을 통째로 보여 줘요.
- 스튜디오 편집기는 영어로 남아 있어요.

<br>

## 원본 기능

원본 open-aim의 기능은 모두 그대로예요.

- **실제 맵 훈련:** 어센트, 스플릿, 헤이븐, 로터스, 바인드, 코로드, 어비스, 서밋, 선셋에서 실제 동선을 따라 각을 정리해요. 봇이 피킹하고, 섬광을 쓰고, 반격해요.
- **훈련 종류:** 프리에임, 각 잡기, 섬광 대응, 기본기(미세 플릭, 드리프트 클릭, 무빙 봇, 트래킹).
- **스튜디오:** 실제 맵이나 빈 아레나에 봇을 놓고 동선과 엄폐물을 만들어 나만의 드릴을 만들 수 있어요. 내 움직임을 녹화해 따라 하는 **카피캣 봇**도 있어요.
- **스킨과 조준:** 소총 ADS, 저격 스코프, 스킨 15종.
- **기록:** 점수, 시간, 명중률, 사격 오차 그래프, 훈련 기록.
- **내 게임처럼 설정:** VALORANT 설정 파일 가져오기(감도, 조준선, 키 설정), 다른 게임 감도 변환, 프레임 제한, FPS 표시.
- **오프라인:** 계정도 인터넷도 필요 없어요. 데이터는 `%APPDATA%\AimTrainer`에 저장되고, 시작할 때마다 자동으로 백업돼요.

자세한 내용은 [원본 README](https://github.com/unkwsr/open-aim#readme)와 [CHANGELOG.md](CHANGELOG.md)를 봐 주세요.

<br>

## 설치

1. [Releases](../../releases/latest)에서 **AimTrainer-Setup.exe**를 받아 실행해요.
   설치 없이 쓰려면 **AimTrainer.exe**(포터블)를 받으면 돼요.
2. 이미 원본 AimTrainer가 깔려 있다면 먼저 종료해 주세요. 설정과 훈련 기록은 그대로 남아요.
3. Windows 10 또는 11, WebGL 2를 지원하는 그래픽카드가 필요해요.

<br>

## 언어 설정

**설정 → Language**에서 언어를 고르세요. 고른 언어는 이 PC에 저장되고 다음 실행 때도 유지돼요.

<br>

## 소스로 실행하기

[Node.js](https://nodejs.org) 20 이상과 `site/` 폴더의 게임 파일이 필요해요
([docs/game-files.md](docs/game-files.md) 참고).

```bash
git clone https://github.com/<내-아이디>/open-aim.git
cd open-aim/app
npm install
npm start
```

`npm run build`를 실행하면 `app/dist/`에 설치 파일과 포터블 실행 파일이 만들어져요.
전체 구조는 [docs/architecture.md](docs/architecture.md)에 있어요.

<br>

## 번역 구조

| 파일 | 내용 |
|---|---|
| `app/language.js` | 설정의 Language 탭, 국기, 언어 목록 |
| `app/main.js` | 고른 언어의 번역 묶음을 `/_aim_lang/<code>.json`으로 내려주고 화면 글자를 바꾸는 부분 |
| `app/i18n/ko.js`, `ja.js`, `zh.js` | 사람이 직접 다듬은 번역 (메뉴, 설정, 맵 이름 등). 가장 우선해서 쓰여요 |
| `app/i18n/ollama/*.json` | 게임 사전 전체를 로컬 LLM으로 옮긴 번역 |
| `scripts/translate-ollama.mjs` | 위 JSON을 만드는 스크립트 |
| `scripts/english-source.mjs` | 드릴 이름·설명처럼 영어로만 있는 줄을 모으는 스크립트 |

게임 사전(약 2만 3천 줄)은 로컬 [Ollama](https://ollama.com)의 `gpt-oss:20b`로 먼저 옮기고,
고유 이름은 용어집으로 고정했어요. 자주 보이는 화면과 틀린 번역은 사람이 직접 고쳤어요.

번역을 이어서 하거나 다시 돌리려면:

```bash
# 게임 사전 번역 (중간에 멈춰도 이어서 해요)
node scripts/translate-ollama.mjs ja

# 맵·요원 이름이 틀린 항목만 다시 번역
node scripts/translate-ollama.mjs ko --recheck

# 드릴 이름과 설명
node scripts/translate-ollama.mjs ja --english app/i18n/english-source.json
```

### 번역 고치기

어색한 번역을 찾으면 이슈나 PR로 알려 주세요. `app/i18n/<언어>.js`에 원문과 번역을 한 줄 넣으면
LLM 번역보다 먼저 쓰여요.

```js
// app/i18n/ko.js
zh: { "预瞄": "프리에임" },          // 게임 원문(중국어) → 번역
en: { "Drift Click": "드리프트 클릭" }, // open-aim 영어 문장 → 번역
```

<br>

## 출처

- **원본 프로젝트:** [unkwsr/open-aim](https://github.com/unkwsr/open-aim) by [@unkwsr](https://github.com/unkwsr) (MIT License).
  훈련 기능, 스튜디오, 스킨, 설정 가져오기 등 언어 기능을 뺀 모든 기능은 원본 프로젝트의 작업이에요.
- **3D 맵:** [ishoutu aim trainer](https://ishoutu.cn/aim)에서 가져왔어요. 원본 제작자의 작업이 아니며 MIT 라이선스에 포함되지 않아요.
- **번역:** 로컬 Ollama `gpt-oss:20b`로 초벌 번역하고 사람이 검수했어요.

<br>

---

<a id="english"></a>

## English

**open-aim (multilingual fork)** is a fork of **[unkwsr/open-aim](https://github.com/unkwsr/open-aim)**, an offline aim trainer on real VALORANT maps.
All training features are the original project's work. This fork adds:

- A **Language** tab in Settings (after Audio and Visuals) with flags and native language names.
- **Korean** (complete), **Japanese** (in progress) and **Chinese** interface translations, written in natural everyday language rather than literal machine output.

Run from source with `cd app && npm install && npm start`; build the installer with `npm run build`.
See [Translation layout](#번역-구조) for where the language files live.

<br>

<sub>
MIT licensed (see <a href="LICENSE">LICENSE</a>). Original work © 2026 <a href="https://github.com/unkwsr">unkwsr</a>.
Built with <a href="https://www.electronjs.org">Electron</a> and <a href="https://threejs.org">three.js</a>.
Not affiliated with or endorsed by Riot Games. VALORANT and its maps belong to Riot Games.
</sub>
