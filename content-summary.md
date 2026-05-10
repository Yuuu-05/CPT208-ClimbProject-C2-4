# HoldLight 作品集文案内容分块总结

> 这个文档只用于内容梳理和自查。当前网站没有引用这个文件，修改它不会影响页面展示。

## 0. 全站导航与首页

### 首页 `index.html`

#### 背景宣言文案
- 通过重复短句营造攀岩运动感：`GO HIGHER`、`TRUST YOUR FEET`、`FIND THE NEXT HOLD`、`KEEP MOVING UP`、`CLIMB BY FEEL`、`OWN THE WALL`、`REACH HIGHER`、`STAY LOCKED IN`。

#### 品牌标题
- 主标题是 `HoldLight`。
- 首页没有大段项目介绍，而是用品牌名和模块入口建立作品集结构。

#### 模块入口
- `Choose Your Module`
- `01. Why & Gap`
- `02. User Requirements`
- `03. Iteration & Alternatives`
- `04. Implementation`
- `05. Evaluation & Reflection`

### 全站顶部导航
- 主页面顶部导航包含：`Home`、`Why`、`Requirements`、`Iteration`、`Implementation`、`Evaluation`。
- `portfolio.js` 会根据当前页面自动标记 active 状态。

### 页面内二级导航
- `why-gap.html`：`Motivation`、`Problem Space`、`Gap Analysis`、`Stakeholders`
- `user-requirements.html`：`User & Persona`、`User Journey Map`、`Evidence`、`Requirements & Traceability`
- `iteration-alternatives.html`：`Early Ideation`、`Prototype & Alternatives`、`Design Direction`
- `implementation.html`：`Contributions`、`High-fi & Core Features`、`Architecture & Technical Notes`
- `evaluation-reflection.html`：`Testing Overview`、`Participants & Phases`、`Testing Tasks`、`Results`、`Design & Reflection`、`Vibe Process`、`References`

## 1. Why & Gap 页面

### 页面定位
- 页面编号：`01 Why & Gap`
- 页面标题：`Why & Gap`
- 页面描述：介绍 HoldLight 的动机、问题框定、学术研究缺口、商业产品缺口和利益相关者背景。
- 视觉标签：`Motivation`、`Research`、`Motivation · Problem Space · Research Gap · Product Gap · Stakeholders`

### 1.1 Why We Chose This Track

#### Active Lifestyles + Climbing
- 说明团队选择 Active track 的原因：体育活动中的 accessibility 不只是“能不能进入活动”，更重要的是能否独立参与活动本身。
- 室内攀岩被用来说明这个 gap，因为攀岩高度依赖路线预览、动作规划和实时判断。
- 对 blind and low-vision climbers 来说，视觉信息不可见会影响路线理解、攀爬中的指导和自我决策。
- 项目目标不是被动 accommodation，而是支持 agency、flow、confidence 和 enjoyment。
- 选择 mobile web app，是因为手机和浏览器可以利用 camera input、speech output、accessibility settings，也符合攀岩馆现场使用场景。

#### Design Priorities
- 攀爬开始前要帮助用户清楚理解路线。
- 攀爬中要提供短、轻量、低认知负担的支持。
- 当系统不确定时，要保留明确 fallback，让用户仍然保持独立性。

### 1.2 Problem Space

#### 总体问题定义
- HoldLight 是一个面向 indoor climbing 的 accessibility-oriented mobile web app。
- 系统结合 route / hold recognition、simplified route preview、short audio guidance 和 assistant-supported fallback，减少攀爬前和攀爬中的不确定性。

#### Problem 01: Route visibility problem
- 室内路线依赖 hold color、position 和 route shape 等视觉编码。
- BLV climbers 常常需要他人翻译路线结构，才能开始规划动作。
- Design implication：提供 confidence-building route preview。

#### Problem 02: Cognitive load problem
- 长解释在身体已经参与攀爬后很难记住。
- 指导需要 brief、timed carefully、easy to repeat。
- Design implication：in-climb support 要 short、audio-first、low-overload。

#### Problem 03: Safety and trust problem
- 攀岩支持系统不能假装自己永远确定。
- 用户需要知道系统何时不确定，以及如何 pause、repeat 或 ask for human help。
- Design implication：明确 fallback 和 recovery states。

### 1.3 Academic Research Gap

#### Braun et al. (2025)
- Strengths：明确 BLV climbers 在 climbing / bouldering 中的 accessibility barriers；提供用户需求基础；强调 accessibility 应作为核心设计要求。
- Limitations：主要停留在 needs assessment；缺少实际攀爬中不打断 flow 的支持证据；没有完整结合 pre-climb route understanding、real-time lightweight guidance 和 gym-ready implementation。

#### Ramsay & Chang (2020)
- Strengths：证明 auditory feedback 可作为 blind climbers 的 non-visual channel；关注攀爬中支持；用身体位置转化为可听反馈。
- Limitations：声音反馈可能增加认知负担；重点是 body pose 而不是完整 route sequence / hold layout；更像 research prototype，离普通攀岩馆采用还有距离。

#### Richardson et al. (2022)
- Strengths：用 computer vision 直接回应攀岩的视觉依赖；为 hold detection 和 sensory substitution 提供参考；不只做 logging 或 route browsing。
- Limitations：真实攀岩馆光线、遮挡、墙面角度、拥挤环境会影响 vision reliability；额外传感或反馈设备可能影响舒适度和 flow；缺少 scalable gym deployment workflow 证据。

#### Simone & Galatolo (2020)
- Strengths：展示 visually impaired climbers 在真实 human instruction 中如何被引导；强调 timing、trust、communication、safety；提供自然指导方式的设计启发。
- Limitations：高度依赖另一个人，限制独立 route preview 和 decision-making；partner-based instruction 难以规模化；频繁 verbal guidance 可能打断 rhythm 和 problem-solving。

### 1.4 Commercial Product Gap

#### KAYA
- Strengths：提供 route discovery、beta content、climbing media、logging、progress tracking、community。
- Limitations：强视觉优先；beta videos 缺少结构化 audio description / non-visual route summaries；没有围绕 BLV climbers 的独立路线理解或攀爬中辅助设计。

#### Vertical-Life
- Strengths：清晰组织 route、topo、grade、climbing-area 信息；支持 pre-climb planning；说明 digital route information platforms 有商业可行性。
- Limitations：visual topos 是核心交互，造成 accessibility barrier；route information 没有转化为 audio、tactile 或 semantic explanation；侧重 route browsing，不支持 real-time low-interruption climbing support。

#### TopLogger
- Strengths：适合 indoor climbing gym 的 route updates、grading、logging；支持 dashboard、ranking、progress、achievement；与 gym route resets 和 records 连接。
- Limitations：完成后 logging 不能帮助 BLV climbers 攀爬前理解路线；ranking / leaderboard 不解决 accessibility、independence、safety；价值取决于特定 gym 是否采用和维护。

#### RouteIt Indoor Bouldering
- Strengths：聚焦 indoor bouldering；通过 route images、beta videos、route status 支持准备；整合 gym connection、beta sharing、statistics、route progress。
- Limitations：仍然 image / video-heavy；依赖 gym coverage 和 route database；不提供保持 flow、减少 cognitive load 的 robust in-climb guidance。

### 1.5 Stakeholder Overview

#### Primary User: Blind / low-vision beginner climber
- 需要 route understanding、short cues、accessible controls、confidence，以及 guidance unclear 时的 safe recovery。

#### Secondary User: Sighted assistant / coach / peer supporter
- 负责 setup、safety monitoring、camera positioning、human fallback，但不应该成为整个 guidance system。

#### Context: Indoor climbing gym, mobile onsite use
- 环境 noisy、visually dense、time-sensitive、safety-critical。
- 支持必须 fast、readable、audible，并诚实表达 uncertainty。

## 2. User Requirements 页面

### 页面定位
- 页面编号：`02 User Requirements`
- 页面标题：`User Requirements`
- 页面描述：包括 target users、personas、current journey map、evidence of life、requirements list 和 traceability。

### 2.1 Target Users

#### Blind or low-vision beginner climber
- 需要 clear route preview、accessible guidance、confidence-building feedback，以及 missed cues 后的 recovery 方法。

#### Sighted assistant / coach / peer supporter
- 支持 setup、safety awareness、route confirmation 和 human fallback，但不接管全部体验。

#### Indoor climbing gym
- 使用场景是 noisy、visually dense、safety-critical 的移动现场环境。
- 支持必须 fast and low-overload。

### 2.2 Service Personas

#### Persona Group: Blind or Low-Vision Climber
- 组标题：`Blind or Low-Vision Climber`
- Kicker：`Primary User File`

##### Li Wen
- 角色：`Low-Vision Beginner Climber`
- Quote：`I want enough information to solve the route myself, not constant instructions.`
- Tags：`Accessible Mode`、`Audio Cues`
- Background：Li Wen 有一定攀岩经验，通常依赖 coach / sighted guide 做路线解释和攀爬中提示，但不希望全程被 move-by-move 指挥。她想在理解路线后自己做决定并保持节奏。
- Goals：攀爬前理解路线；保持攀爬节奏并独立决策；不确定时快速恢复；感到 confident、in control、actively engaged。
- Frustrations：路线解释碎片化且难记；长指令在身体负荷下造成 overload；提示时机差会打断动作；反复求助有社交负担。
- Needs：layered on-demand route preview；short actionable next-hold cues；repeat、simplify、pause、request human help 等 fallback。
- Design implications：route preview 必须先于 live guidance；audio cues 必须足够短；fallback controls 要保护 autonomy。

#### Persona Group: Assistant Support
- 组标题：`Assistant Support`
- Kicker：`Setup + Safety Backup File`

##### Lance
- 角色：`Sighted Assistant / Coach / Peer Supporter`
- Quote：`I want to support when needed, not become the entire guidance system.`
- Tags：`Setup Support`、`Safety Backup`
- Background：Lance 是有经验的 supporter，需要把路线结构和空间信息转化为短 verbal cues，同时监控 pace、uncertainty 和 safety。他希望支持 climber，但不成为全部 guidance system。
- Goals：保持 safety oversight 而不主导体验；减少 continuous prompting；知道何时 step in、clarify 或让 climber 自主继续。
- Frustrations：复杂路线信息难以转化为 brief real-time cues；持续提示消耗精力并影响安全观察；不确定何时 repeat、simplify、pause 或 take over。
- Needs：bounded workflow；清晰的 system / human handoff points；uncertain moments 中快速可理解反馈。
- Design implications：setup 中要有 assistant confirmation；系统需要 explicit uncertainty 和 request-help states；support tools 要减少重复工作。

### 2.3 Current User Journey Map

#### Stage 01: Arriving / Choosing a route
- Step：用户到达 gym，在支持下选择 beginner route。
- Pain point：route choice 依赖可能不可访问的视觉信息。
- Emotion：curious but unsure，担心路线是否可理解。
- Opportunity：让 route access 从第一屏就明显。
- HoldLight support：scan-first entry 和 beginner route context。

#### Stage 02: Understanding the route
- Step：尝试理解 hold order、direction、key transitions。
- Pain point：verbal route explanation 攀爬开始后很难记住。
- Emotion：focused，希望获得足够信息但仍然自己解决。
- Opportunity：提供 overview 到 key holds 的 layered preview。
- HoldLight support：camera scan、route confirmation、simplified preview。

#### Stage 03: Preparing to climb
- Step：设置 preferences、确认 phone position、准备开始。
- Pain point：setup decisions 可能让用户在开始前焦虑。
- Emotion：slightly anxious，希望 setup 快速可信。
- Opportunity：保存 accessibility preferences 并支持 assistant confirmation。
- HoldLight support：accessibility settings、assistant check、start confirmation。

#### Stage 04: Receiving guidance
- Step：攀爬时听 brief cues，需要时 repeat。
- Pain point：long / unclear guidance 会打断 rhythm 并增加 cognitive load。
- Emotion：tense but active，需要短到可以立即执行的 cue。
- Opportunity：使用 short audio cues 和 repeat controls。
- HoldLight support：audio-first guidance，包含 repeat、pause、low-overload phrasing。

#### Stage 05: Recovering and reflecting
- Step：pause、ask for clarification、review climb、plan next attempt。
- Pain point：guidance fails 时需要 clear next action，而不是 silent uncertainty。
- Emotion：relieved or frustrated，需要安全恢复并理解发生了什么。
- Opportunity：显示 fallback options 和 post-climb reflection。
- HoldLight support：explicit fallback、recovery support、reflection summary。

### 2.4 Evidence of Life

- Early pilot testing：初步测试验证概念是否符合真实攀岩需求。
- Feedback collection：早期反馈暴露 route explanation、phone handling、audio-first guidance 需要更清晰结构。
- Concept validation：pilot sessions 让项目基于真实 accessibility concerns，而不是简单假设视觉路线可以被翻译。
- Internal flow check：团队测试验证 scan-first flow、screen sequence、interaction logic。
- Prototype rehearsal：内部排练帮助细化用户在 route preparation 和 guidance 中需要 hear、tap、confirm 的内容。
- Participant contact：招募和准备消息说明测试如何围绕 participant availability、context、accessibility needs 组织。
- Needs discussion：访谈沟通转化为 clearer route preview、controls、fallback support 的 requirements。
- Prototype validation：内部原型检查 route scanning、cue controls、accessibility settings 是否按顺序可见且可理解。
- Climbing trial：攀爬试验说明 guidance 必须 short、timely、recoverable。
- Full test setup：最终 onsite setup 包括 phone framing、guide support、climber movement、belayer safety、real wall constraints。

### 2.5 Must-Have Requirements

#### Must-have 1: Layered Route Preview
- 用户必须能通过 overview、segment 和 optional detail 在攀爬前理解路线。

#### Must-have 2: Brief Direction-First Audio Guidance
- 用户攀爬中必须获得 short、actionable cues，且不打断节奏或造成注意力 overload。

#### Must-have 3: Recoverable Fallback and Human Help
- 当 cues missed 或 uncertain 时，用户必须能 repeat、pause、request more detail 或 ask for human support。

#### Functional Requirements: Core product behaviour
- 从 clear primary action 开始 camera scan。
- Guidance 前确认 detected route。
- 提供 repeat、pause、fallback controls。
- 记录 basic session summary 供 reflection。

#### Accessibility Requirements: Readable and audio-first support
- 高对比和大尺寸可读控件。
- Screen-reader-friendly headings and labels。
- Short speech cues with repeat support。
- Visible focus states 和 non-colour-only status cues。

### 2.6 Requirement Traceability

- Cannot distinguish route clearly -> Route preview -> Camera scan + route confirmation。
- Cannot read screen while climbing -> Audio-first guidance -> Short speech cues。
- Gets confused when system fails -> Recovery support -> Repeat / pause / fallback。
- Assistant support can become constant and tiring -> Bounded human handoff -> Assistant confirmation and request-help states。

## 3. Iteration & Alternatives 页面

### 页面定位
- 页面编号：`03 Iteration & Alternatives`
- 页面标题：`Iteration & Alternatives`
- 页面描述：展示 HoldLight 如何从 broad idea generation 发展到 scan-first、accessibility-focused Hi-Fi prototype。

### 3.1 Early Ideation
- 团队用 rapid sketching 探索 route scanning、beginner learning、assistant support、voice interaction、mobile-first climbing guidance。
- 视觉材料包括 Crazy 8 sketches。
- Low-Fi Prototype Links 包含 `Monkey`、`Figma` 和 `Google AI`。

### 3.2 Prototype & Alternatives

#### 总体演变
- UI 经历三个阶段：simple early interface -> richer sports-app direction -> simplified accessibility-focused Hi-Fi prototype。

#### Design Direction Options
- Option A: Pre-climb route preview only。Strength 是建立路线理解；Weakness 是攀爬中支持不足；Decision 是 not enough alone。
- Option B: Detailed continuous in-climb guidance。Strength 是 real-time support 强；Weakness 是 cognitive load 高并打断 rhythm；Decision 是 rejected。
- Option C: Brief in-climb cueing only。Strength 是轻量、少打断；Weakness 是 initial route understanding 弱；Decision 是 not enough alone。
- Final: Layered preview + brief cueing + fallback。Strength 是平衡 preparation、rhythm、autonomy；Weakness 是仍需要 human safety support；Decision 是 chosen。

#### Stage 1: Low-Fi Prototype
- Explored：simple mobile interface structure、basic settings / early navigation、让 climbing assistant approachable 的初步尝试。
- Worked：视觉简单，主要动作容易识别。
- Lacked：还不足以支撑完整 climbing support workflow；accessibility needs 不够突出；scan guidance 尚未成为中心。
- Evidence captions：Low-Fi prototype screens 和 Low-Fi demo 记录最早的移动结构与 walkthrough。

#### Stage 2: Mid-Fi Prototype
- Changed：视觉方向转为 green climbing / sports-app style；增加更多功能；探索 dashboard、route support、guidance 和 richer app-like features。
- Why expanded：测试 fuller sports-app structure 是否更真实；探索 HoldLight 是否能支持多种 climbing tasks。
- Learned：产品更完整但变得 feature-heavy；丰富结构可能增加 BLV users 的 cognitive load；因此转向更清晰 accessibility support。
- Evidence captions：Mid-Fi visual direction 和 Middle-fi demo 展示扩展后的绿色 sports-app 方向。

#### Stage 3: Accessibility-Focused Hi-Fi Prototype
- Changed：保留 mature green visual identity；移除不必要复杂度；转向 scan-first 和 task-focused；聚焦 route scanning、route confirmation、short guidance、accessibility support。
- Why simplified：BLV users 需要 clarity 而不是 feature density；攀爬时不能处理过多选项；更简单的 scan-first flow 支持 safety、confidence、low cognitive load。
- Why final：最符合 user requirements；让 main task 更容易开始；更清晰支持 audio guidance 和 fallback；更符合 human-centered accessibility design。
- Evidence captions：Final Hi-Fi UI flow 和 Final Hi-Fi demo 展示最终 scan-first direction。

### 3.3 Why the Design Changed

#### From simple to complete
- 第一版帮助测试 basic structure，但还不能支撑 full route guidance workflow，因此转向更完整 app-like direction。

#### From complete to complex
- 中期版本增加功能并更像 sports app，但也带来更高 visual and interaction complexity。

#### From complex to focused
- 最终版本减少不必要功能，聚焦 accessibility task：帮助用户 scan、understand、follow climbing route，并降低 cognitive load。

#### 总结句
- 设计从 “more features” 演变为 “clearer support”。
- 最终原型优先 accessibility、scan-first interaction、low-overload guidance，而不是 feature density。

### 3.4 Final Design Direction

#### Brand Direction: HoldLight
- HoldLight identity 表达“calm guiding light”：帮助不能只依赖视觉路线信息的 climbers。
- 经过多轮迭代，设计变得 simpler、clearer、more focused on accessible climbing support。
- Keywords：Mobile-first、Scan-first、Lower cognitive load、Short audio guidance、Accessible interaction、Simplified user flow。

## 4. Implementation 页面

### 页面定位
- 页面编号：`04 Implementation`
- 页面标题：`Implementation`
- 页面描述：包括 team contributions、high-fi prototype evidence、core feature set、system architecture 和 technical notes。

### 4.1 Squad / Individual Contributions

#### Chenyu Du
- Role：Research & Structure
- Student ID：2360743
- Responsibilities：负责 research framing、academic / product gap synthesis 和 portfolio structure；把 problem space evidence 连接成清晰叙事。

#### Junyan He
- Role：Persona & UI/UX
- Student ID：2363304
- Responsibilities：开发 personas、user journey framing、UI/UX flows 和 visual refinement；让 user needs 和 interaction logic 更容易扫描。

#### Jiafei Sun
- Role：Front-end & Code
- Student ID：2361510
- Responsibilities：支持 prototype implementation、frontend integration、responsive behaviour 和 verification；将 design decisions 转化为 working interactive page behaviour。

#### Youming Yang
- Role：Inclusive Design
- Student ID：2361217
- Responsibilities：审查 accessibility、inclusive design choices、low-overload guidance 和 ethical reflection；确保 guidance model 对 BLV climbers 可理解。

### 4.2 High-Fi Prototype

#### Prototype Evidence
- Final Hi-Fi Overview：展示最终高保真界面总览。
- Final System Demo：展示最终系统 demo。

#### Start from scanning
- 主要旅程从 route scanning 开始，而不是 dense dashboard，让核心任务更容易找到。

#### Preview + short guidance
- Flow 支持 route preview、route correction、short guidance 和 recovery controls。

#### Lower cognitive load
- 最终原型减少 feature density，聚焦 BLV beginner climbers 真正关键的时刻。

### 4.3 Core Feature Set

#### Scan & Route Preview
- User problem：route shape 很难通过视觉获得。
- Implemented feature：camera scan、route confirmation、simplified preview。
- Requirement supported：confidence-building route preview。
- Current limitation：real gym conditions 下 recognition 仍需要 confirmation。

#### Short Audio Guidance
- User problem：攀爬时 screen prompts 不实用。
- Implemented feature：Web Speech API concise cue output，支持 repeat 和 pause。
- Requirement supported：low-overload audio guidance。
- Current limitation：noisy gym environments 可能影响理解。

#### Accessibility & Fallback Controls
- User problem：uncertainty 可能变得 unsafe 或 confusing。
- Implemented feature：text size、contrast、repeat、pause、request-help controls。
- Requirement supported：safe fallback and recovery。
- Current limitation：safety-critical decisions 仍需要 human support。

### 4.4 System Architecture and Data Flow
- HoldLight 被描述为 mobile-first web application。
- Frontend：React + Vite，管理 authentication、onboarding、dashboard、accessibility、speech、camera access 和 Climb Assist flow。
- Browser capabilities：getUserMedia、MediaPipe Pose、speech synthesis、audio、haptics。
- Backend：static hosting + API proxy 到 Node + Express，处理 users、notifications、climb scans、climb sessions、guidance logs、vision requests。
- Python vision runtime：wall detection、hold grouping、color analysis、planar calibration。
- Database：MongoDB 存储 user、scan、session、guidance data。
- 两条主要 pipeline：wall scanning 和 live guidance。

### 4.5 Technical Notes / AI Logs

#### Mobile web prototype
- Browser frontend for mobile interaction and accessibility controls。
- Node / Express API for backend coordination。
- MongoDB for persistent app data。
- Python vision engine for camera-based recognition experiments。
- Web Speech API / speech synthesis for audio cues。

#### Setup and evidence trail
- README / setup instructions 应说明如何本地运行 app。
- repository includes `/ai-logs` with placeholder prompt documentation to be completed before final submission。
- Verification methods 包括 manual user-flow checks、responsive layout checks、accessibility review。
- AI-assisted code suggestions 应在采用前 review。

## 5. Evaluation & Reflection 页面

### 页面定位
- 页面编号：`05 Evaluation & Reflection`
- 页面标题：`Evaluation & Reflection`
- 页面描述：包含 staged testing overview、participants、tasks、results、iterative refinements、final reflection、AI disclosure 和 references。

### 5.1 Testing Overview

#### Staged Evaluation
- 项目通过 staged human-centered testing 评估。
- Phase A：理解 BLV climbers 和 support stakeholders 的需求。
- Phase B：pilot testing，优化 preview density、cue wording / timing、fallback behavior。
- Phase C：controlled indoor climbing tasks 中对比 HoldLight 和 standardized current-practice human-support baseline。
- 测试目标不是只验证 hold recognition，而是评估 workflow 是否帮助用户理解路线、接受低负担 guidance、从 uncertainty 中恢复，并在人类安全支持可用的前提下保持 control。

#### Phase cards
- Formative Inquiry：针对 BLV climbers 和 support stakeholders 的 needs research。
- Pilot Refinement：小规模测试，调试 preview density、cue timing、fallback behavior。
- Controlled Initial Evaluation：within-subjects 对比 HoldLight 和 standardized human-support baseline。

### 5.2 Participants & Study Phases

#### Phase A: Formative Inquiry
- Purpose：理解 barriers、preferences、success criteria。
- Participants：11 BLV questionnaire respondents；4 BLV interviewees；5 secondary stakeholders，包括 3 sighted guides 和 2 coaches。
- Informed：user needs、design goals、current support practices、communication breakdowns、automated support 与 human help 的边界。

#### Phase B: Pilot Refinement
- Purpose：stress-test preview、cue wording、timing、fallback。
- Participants：4 BLV climbers，包括 2 blind 和 2 low-vision。
- Informed：layered preview、shorter cue format、active movement 中的 silence、explicit fallback。

#### Phase C: Controlled Initial Evaluation
- Purpose：比较 HoldLight 和 standardized current-practice human support。
- Participants：12 BLV climbers，包括 6 blind 和 6 low-vision。
- Informed：within-subjects comparison；每位 participant 都测试 Baseline 和 HoldLight；测量 route understanding、uncertainty recovery、human-help burden、perceived autonomy、cue usefulness、trust、safety、acceptability。

### 5.3 Process Evidence

- Early communication with visually impaired climbing contacts：了解 initial concerns、practical needs，以及 guided climbing support 是否有真实意义；设计洞察是需要 clear、familiar、consistent guidance language。
- Interview scheduling and follow-up discussion：安排并进行 follow-up conversation，了解 expectations、practical constraints、testing communication；设计洞察是更 respectful and practical 地组织测试。
- Internal prototype testing：外部测试前检查 interface、guidance panel、route-related interaction 是否能在 mobile 上理解和操作；设计洞察是提前发现 interaction issues。
- Participant climbing trial：观察真实攀爬中的 body movement、hold reachability、guidance 与 movement 的关系；设计洞察是 short、well-timed guidance 和 realistic physical constraints。
- Final full-context onsite test：包含 participant、guide、tripod-mounted phone、belayer support、top-rope environment；为真实攀爬场景中的 route guidance 评估提供最完整证据。

### 5.4 Testing Tasks

#### Understand the Route Before Climbing
- 任务：participants 接收 route information 后，在攀爬前解释路线。
- Observed：start area、finish area、overall route direction、key segment or difficult move。

#### Use In-Climb Next-Hold Guidance
- 任务：participants 攀爬时接收 short audio cues，例如 `Right hand, two o'clock, far.`
- Observed：cues 是否清晰、是否足够短、timing 是否打断 rhythm、users 是否能根据 prompt 行动。

#### Recover from Uncertainty
- 任务：participants 在 uncertain、missed cue 或需要 clarification 时使用 fallback controls。
- Observed：Repeat、More Detail、Pause、Human Help，以及 users 是否能不失去 control 地恢复。

#### Compare HoldLight with Current Human Support
- 任务：controlled evaluation 中 participants 分别体验 standardized human-support baseline 和 HoldLight condition。
- Observed：route understanding、uncertainty recovery、clarification interruptions、explicit human-help requests、perceived autonomy。

### 5.5 Testing Results

#### What We Measured
- Route Understanding：是否能识别 start、finish、overall route direction、key segment。
- Uncertainty Recovery：uncertainty breakdown episodes、clarification-dependent interruptions、repeat / more detail / pause / help actions。
- Human Help Burden：explicit human-help requests、extra information-support interventions、system-to-human fallback events；测量 routine route-information support，而不是 safety support。
- Perceived Autonomy and Acceptability：perceived autonomy、cue usefulness、uncertainty recovery、trust、safety、acceptability、willingness to use again。

#### Key Findings
- Route understanding score：Baseline 2.0 / 4，HoldLight 3.5 / 4；用户在攀爬前建立了更清楚的 route model。
- Uncertainty breakdown episodes：Baseline 4.0，HoldLight 2.0；用户更少卡住。
- Clarification-dependent interruptions：Baseline 3.0，HoldLight 1.0；需要重复解释或澄清的停顿减少。
- Explicit human-help requests：Baseline 3.5，HoldLight 1.0；对 human route prompts 的日常依赖降低。
- Perceived autonomy：Baseline 3.0 / 5，HoldLight 5.0 / 5；用户感到更 in control。

#### Result Pattern
- HoldLight 没有主要让用户爬得更快，而是帮助用户建立更清晰的 route model、更顺畅地从 uncertainty 中恢复、减少 repeated human route prompts，同时保留 human safety support。

#### Boundary & Safety Notes
- Total task time 没有明显改善。
- Safety-only interventions 没有显著差异，说明 HoldLight 减少的是 routine information support，而不是替代 human safety support。
- 36 次 HoldLight trials 中，human guides 为 route-information support 重新介入 14 次。
- 36 次 initial mobile scans 中，manual route revision 需要 7 次。
- Fallback 共触发 42 次：27 次 user-triggered，15 次 system-triggered。
- 主要 boundary cases：dense same-color hold clusters 和 visually similar adjacent routes。
- 结论：HoldLight 仍有局限，应减少 routine route-information support，而不是替代 human safety support。

### 5.6 Iterative Refinement: Before & After

#### 总说明
- Refinements 来自 alpha testing、BLV user feedback 和 real use observations。
- Evaluation 不只是最后检查，而是用于 simplify interface、reduce cognitive load、support clearer route understanding、improve route correction。

#### Testing Sources Behind the Refinements
- Team-based alpha testing：发现 unclear system entry points 和 overloaded scan flow。
- BLV user testing：优化 route preview 和 in-climb audio guidance，让信息在 physical load 下更容易理解。
- Real user testing of route correction：发现逐个编辑 holds 太慢，因此加入 batch editing controls。

#### Refinement 01: Interface Simplification and Clearer Scan Entry
- Feedback source：Team-based alpha testing。
- Observation：classmates 能理解概念，但需要更清楚的 first action；早期界面入口太多，scan function 不够 dominant。
- Design issue：系统像 feature collection，而不是 guided accessibility workflow；用户在 wall scan 前需要额外判断从哪里开始。
- Change made：简化整体结构，让 wall scanning 成为更明显 primary action，减少 clutter。
- Impact：降低进入系统的摩擦，更符合 climbing gym 中 mobile-first、quick、clear interaction。

#### Refinement 02: From Long Route Explanation to Layered Route Preview
- Feedback source：Blind and low-vision user testing。
- Observation：攀爬前 route information 不应该是一整段长解释，用户需要 step-by-step 建立理解。
- Design issue：早期 route preview 一次性给太多信息，开始攀爬后难以记住。
- Change made：改为 Overview -> Segment -> Drill-down 的 layered structure。
- Impact：支持独立 route understanding，避免 information overload，并保留 climbing 的 puzzle-solving 感。

#### Refinement 03: From Verbose Instructions to Brief Direction-First Audio Cueing
- Feedback source：Blind and low-vision user testing。
- Observation：攀爬中详细指令难以处理，特别是 climber 正在移动或承重时；需要 short、consistent、immediately actionable cues。
- Design issue：长描述虽然信息更多，但会拖慢 decision-making、打断 rhythm、增加 cognitive load。
- Change made：改为 direction-first audio guidance，例如 body part + direction + distance：`Right hand, two o'clock, far.`；需要时可请求更多细节。
- Impact：更容易在攀爬中执行，减少 cognitive load，同时避免让 climber 变成 passive follower。

#### Refinement 04: From One-by-One Hold Editing to Batch Hold Editing
- Feedback source：Real user testing of route correction workflow。
- Observation：当 scan result 中有多个错误或 missing holds 时，逐个添加 / 删除太慢。
- Design issue：individual hold editing 让 route preview 前的 correction 成本过高，不适合真实 gym 中复杂墙面。
- Change made：加入 batch editing controls，可多选删除或更高效添加调整，同时保留 individual editing。
- Impact：wall scan correction 更快、更贴近真实使用，也提高后续 route preview 和 audio guidance 的可靠性。

#### Design Reflection
- 设计改进不只是视觉 polish，而是来自 human-centered evaluation。
- 最终设计在 autonomy 和 safety 之间平衡：不替代 coaches、guides、belayers，而是减少 routine information-support burden，并保留 uncertain / safety-critical moments 中的人类支持。
- AI tools 用于 visual refinement、wording、coding assistance，但核心 design logic、testing findings、human-centered decisions 来自团队 research 和 evaluation。

### 5.7 Final Reflection

#### Human-Centric Impact
- HoldLight 从一个观察出发：indoor climbing 仍围绕 visual certainty 组织。
- 对 BLV climbers 来说，route preview、hold identification、movement planning 的视觉假设会造成 informational barrier，限制 confidence、independence、belonging。

#### Social / Ethical Implications
- 核心伦理问题不是提供最多 guidance，而是支持 climber 同时不剥夺 agency，不夸大系统的可靠性。
- 过密、过连续、过确定的 guidance 可能打断 rhythm、增加 cognitive load，并暗示 technology 能承担它无法保证的安全责任。

#### Project Limitations
- 当前 prototype 仍是 early implementation。
- Route recognition 需要进一步 real-gym validation。
- Camera framing 仍部分依赖 assistant support。
- Noisy climbing environments 可能影响 audio cue comprehension。
- 项目不应被视为 complete safety system。

#### Future Work
- 在 ethically and practically possible 的情况下继续和 BLV climbers 测试。
- 加强 uncertainty handling。
- 做更 robust vision evaluation。
- 探索 haptic feedback。
- 更深入整合 climbing gym workflows。

### 5.8 Vibe Coding Process Overview

#### AI & Design Resources Used
- 总说明：项目使用 AI tools 和 design resource platforms 支持 research、visual exploration、prototyping、front-end implementation；最终决策仍基于 accessibility、consistency 和 project requirements 手动 review。

#### Selected tool descriptions
- ChatGPT：用于 early idea structuring、UI logic summary、front-end framework organization、prompt / implementation instruction refinement。
- Gemini：用于分析 interaction style、visual direction、layout mood、motion feeling、aesthetic references 和 possible code approaches。
- Pinterest：用于收集 UI styles、sports app layouts、color moods、interaction inspiration；选定图像再交给 Gemini 分析 visual direction 和 design patterns。
- Uiverse：用于探索 implemented UI components，如 buttons、cards、hover effects、icon interactions；部分想法被重写进自己的代码或作为 Figma 视觉参考。
- Figma：用于 prototyping stage，组织 interface ideas、探索 low-fidelity layouts、把 references 和 generated suggestions 转为清晰 visual structures。
- Google AI Studio：用于根据 design direction 和 documents 生成 early front-end UI prototypes，快速测试 layout、visual style、page structure。
- Codex：用于在 VS Code 中 build and refine code framework，改善 page navigation、component structure、UI consistency，以及 prototype 与 front-end implementation 的连接。

#### AI Workflow Review: What Works
- Fast visual exploration：AI 帮助快速探索 UI styles、color palettes、layout directions。
- Clearer design communication：text-based AI 把 rough ideas 转成 structured prompts 和 front-end instructions。
- Faster front-end prototyping：Google AI Studio 和 Codex 帮助快速生成 / 优化 early UI prototypes。
- Better iteration speed：可以测试多个 design directions 并逐步改善 interface。

#### AI Workflow Review: What Needed Review
- AI output was not always accessible：有些生成界面好看但没有充分考虑 low-vision readability、contrast、spacing、simple interaction。
- Navigation logic needed manual correction：页面跳转和 transition logic 需要人工检查。
- Visual style could become inconsistent：不同 AI output 的 spacing、colors、component styles 可能不统一，需要手动统一 UI system。
- AI could not replace user-centered judgement：最终决定仍要基于 project requirements、accessibility needs、group discussion。

#### Vibe Coding Process Timeline
- App Research：研究 Keep 等 existing apps / sports products，理解 common functions、layout patterns、user flow structures。
- Team Discussion：收集 references 后与组员讨论 features，决定产品应包含哪些功能。
- Hand Sketch：用手绘 sketch 规划 key UI screens 和 transition logic。
- UI Reference Collection：搜索 sports app interfaces 和 design references，并和 sketches 对比。
- AI Style Summary：使用 image-based AI 总结 visual style、color palette、interaction mood。
- AI Layout Planning：使用 text-based AI 整理 page structure、layout logic、navigation flow。
- Prototype in Google AI Studio：基于 chosen style direction 生成 early front-end prototype 并导出 zip。
- Refine in Codex：用 Codex 改善 component consistency、page transitions、interaction logic，使原型成为更完整 front-end result。

#### Ethical Reflection
- 总说明：AI 提高 prototyping speed，但 final design 仍由 accessibility、safety、real user needs 指导。
- Accessibility First：因为项目支持 BLV climbers，UI 不能只追求视觉效果，需要手动检查 readability、contrast、spacing、speech feedback、simplified interaction。
- Human Safety Matters：AI 和 computer vision 不能替代 climbing 中的人类安全支持，系统应提供 guidance 和 fallback messages，真实安全依然依赖 human supervision 和 careful judgement。
- Responsible AI Use：AI 用于 visual exploration、layout planning、front-end iteration，但输出不直接作为最终结果；不够 accessible 的生成设计会根据 project goals 和 user-centered principles 调整。
- Conclusion：vibe coding 提升设计速度，但最终决策来自 human judgement、group discussion、accessibility review 和 testing。

### 5.9 References & Sources Reviewed

#### Section purpose
- 列出 research stage 中审查的 academic papers 和 commercial products。
- 这些 sources 支持 problem framing、accessibility gap analysis、design requirements 和 final evaluation focus。

#### Academic Papers
- Braun et al. (2025)：帮助理解 BLV climbers' accessibility needs，以及 climbing practice 与 assistive system design 之间的 gap。
- Ramsay & Chang (2020)：用于比较 audio-based climbing assistance，并理解缺少 full workflow 的 technical guidance 局限。
- Richardson et al. (2022)：作为 computer-vision-assisted climbing support 的参考，同时强调 deployable and user-controlled interaction 的必要性。
- Simone & Galatolo (2020)：帮助理解 human guidance、verbal instruction、timing 和 BLV climbing support 的 social nature。

#### Commercial Products
- KAYA：帮助理解 commercial climbing platforms，但对 BLV climbers 的 accessibility support 公开记录很少。
- Vertical-Life：展示 mainstream climbing apps 如何支持 route information 和 gym feedback，但不是面向 BLV route understanding。
- TopLogger：强于 indoor logging 和 progress tracking，但不解决 accessible route preview 或 in-climb next-hold guidance。
- RouteIt Indoor Bouldering：支持 route images 和 beta sharing，但仍假设 visual route access，不支持 BLV climbing workflow needs。

#### Formal IEEE References
- 网站列出 8 条正式引用：4 篇 academic papers 和 4 个 commercial product / app 来源。
- 访问日期多为 Apr. 29, 2026。

#### AI Tools Used
- ChatGPT：early idea structuring、UI logic organization、prompt writing、wording refinement。
- Gemini：design alternatives comparison、research / UI direction summary。
- Pinterest：visual reference collection、mood-board exploration。
- Uiverse：UI interaction and component style inspiration。
- Figma：visual design exploration、interface planning、prototype review。
- Google AI Studio：early front-end prototype generation、layout exploration。
- Codex：front-end implementation、debugging、component consistency、responsive layout refinement。

#### Image sources note
- 当前 portfolio images 使用 local project assets 和 placeholders。
- 如果之后使用 image generation tools，应在 references 或 AI logs 中记录 generated assets 和 prompts。

## 6. 旧页面 / 合并说明页

这些文件是旧内容入口或跳转说明页，当前主要内容已合并到主页面中。

### `brief.html`
- 标题：`Project overview merged into HoldLight Home`
- 说明：原 project overview content 已合并进 Home overview 和 `01 Why & Gap` problem space。
- 链接：`Go to Home`

### `beta-map.html`
- 标题：`Journey map merged into 02 User Requirements`
- 说明：current user journey map 现在位于 personas 之后、evidence of life 之前。
- 链接：`Go to Journey Map`

### `personas.html`
- 标题：`Personas merged into 02 User Requirements`
- 说明：Li Wen 和 Lance 已放入 User Requirements 页面，并与 evidence、journey map、traceability 结合。
- 链接：`Go to Personas`

### `requirement.html`
- 标题：`Requirements merged into 02 User Requirements`
- 说明：requirements list 和 traceability table 现在位于 User Requirements 页面。
- 链接：`Go to Requirements`

### `progression.html`
- 标题：`Progression renamed to 03 Iteration & Alternatives`
- 说明：progression content 已围绕 Crazy Eights、design alternatives、low-fi prototype 和 final direction 重构。
- 链接：`Go to Iteration & Alternatives`

### `squad.html`
- 标题：`Squad merged into 04 Implementation`
- 说明：animated squad section 现在和 individual contribution table 一起位于 Implementation 页面。
- 链接：`Go to Squad Contributions`

### `testing-iteration.html`
- 标题：`Testing merged into 05 Evaluation & Reflection`
- 说明：usability testing、key findings、before / after refinements、reflection 和 AI disclosure 现在整合在一起。
- 链接：`Go to Evaluation & Reflection`

### `final-reflection.html`
- 标题：`Final reflection merged into 05 Evaluation & Reflection`
- 说明：final reflection 现在和 testing evidence、iteration、AI reflection、references 一起展示。
- 链接：`Go to Final Reflection`

## 7. 额外动态 / 装饰性文案

### `portfolio.js`
- Copy feedback：复制按钮成功时显示 `Copied`，失败时显示 `Copy failed`。
- Home module transition overlay 主要是视觉 SVG 路线，没有额外正文。
- AI 工具说明卡片的动态文案已归入 `5.8 Vibe Coding Process Overview`。

### `portfolio.css`
- 伪元素中少量装饰文字包括 `ID CARD`、`OPPORTUNITY` 和若干外链箭头符号。
- 这些内容主要服务于视觉标签，不承担主体叙事。
