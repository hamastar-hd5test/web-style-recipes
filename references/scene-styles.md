# 場景畫風庫：同一個場景的 33 種畫風

> 2026-11-22 建。來源：Dex 提供的〈10 Claude Animation Styles〉教學文件（同一張「紅色敞篷車開過城市街道」的圖改成十種畫風，再做成動畫）。本檔是改寫整理，描述、prompt 與網頁做法用我們自己的話。原文沒有給每種畫風的歷史出處；下面「可借的出處」只寫本 skill 已查證過的條目（`aesthetics.md` 的 A 編號），寫「待查」的照核心原則 6，開工前先查一件代表作。
> S11 來源：Instagram @automance_ 的 Reel（2026-11-22）。
> S12–S26 來源：Instagram @vec3.motion（同一場追逐戲換十種畫風）與 @anylancer（一顆彈珠連鎖反應穿過十個世界）的 Reel（2026-11-22 讀取）。兩支各十種，與既有條目重疊的不另開編號，見下方「別名對照」；示範場景用自己的，不沿用原片的遊戲角色或第三方產品。
> S27 來源：Instagram @githubsignals 介紹的開源專案 JDhruv14/line-art-animation（MIT，2026-11-22 讀取）。
> S33 來源：Instagram @matt_penny_applied_ai 的 Reel（同一座火山爆發換十種畫風，2026-11-22 讀取）；其餘九種（Ink-Wash、Pixel-Art、Isometric、Three.js-3D、Blueprint、Paper-Cutout、Claymation、Neon-Synth、Watercolor）都已在庫內，見別名對照。
> 2026-11-25 再讀四支 Reel：@tonistelk（雨中撐傘十種）、@vec3.motion（十種 Genjutsu）、@matt_penny_applied_ai（八種）、@science_in_8bit（像素畫加運鏡）。畫風都對得到既有條目，只補別名；@science_in_8bit 講的是鏡頭語言不是畫風，收進 `sprite-stack` 的 `references/optimization-directions.md` 方向四。
> S28–S32 來源：Higgsfield 的 Notion 教學〈10 Animation Styles in Claude — Genjutsu and 3D Jutsu〉（2026-11-22 讀取）裡的畫風名單；描述與 prompt 是我們自己寫的。
> 編號寫成 `S01`–`S33`，避免和配方 01–11、美學 A01–A20 撞號。

## 這份跟另外兩份的差別

| | 配方 `styles/01-11` | 美學 `aesthetics.md` A01–A20 | 本檔 S01–S33 |
|---|---|---|---|
| 是什麼 | 能玩的互動首頁做法 | 有出處的視覺語言 | 換到同一個場景上的「畫風」，每種都附動法 |
| 主要產出 | 單一 HTML | 配方的皮、brief 的參考 | 靜態畫面的 prompt＋動畫方向，組成一套風格包 |
| 誰在用 | 本 skill | 本 skill、探索模式 | 本 skill（當皮用）、`style-pack` skill（做風格包） |

和美學庫重疊的五種（S02、S04、S07、S08、S10）不重寫歷史，只補「放到場景上怎麼畫、怎麼動」。

## 共通：換畫風只換處理方式

- 構圖、主角數量、主角輪廓、畫面比例一律不動，只換線條、色彩、材質、光線。
- 一個畫風一句「看得見」的描述就夠；描述越長越容易和其他畫風混在一起。
- 動作要跟著這個畫風的「材料」動：粉筆是被畫出來的、像素是一格一格跳的、積木是卡進去的。

## 別名對照（名字對不到編號時先查這裡）

| 常見叫法 | 用哪一條 | 補充 |
|---|---|---|
| Claymation、Claymotion、Soft clay 3D、黏土動畫 | A05 黏土 3D | 停格感：12 fps、指紋與壓痕 |
| Paper Cut-out、Paper Cutout、Paper-Cut、Paper collage、Paper Diorama、3D Papercraft、剪紙、紙雕 | A10 紙張拼貼 | 分層剪紙要加每層的投影，整頁像立體書一層層翻起 |
| Bauhaus Shapes | A14 包浩斯 | 人物也拆成圓、方、三角 |
| 太空科普扁平（常被叫成 Kurzgesagt 風） | S07 扁平向量 | 深藍星空、行星帶光環與柔光；prompt 不寫工作室名 |
| 3D Movie Style、皮克斯感 | S09 CGI 電影感＋S10 解說 3D | 白天、圓潤、材質精緻；prompt 不寫工作室名 |
| Wireframe | S14 線框 3D | 2D 發光輪廓是 S01 |
| Voxel、方塊世界 | S25 體素 | 有凸點的是 S03；要用 2D 畫布做出可旋轉的體素物件，交 `sprite-stack` skill |
| Sprite stacking、切片堆疊、像素 3D | S04 像素＋S25 體素的外觀，做法交 `sprite-stack` skill | 俯視、暖色少色、單一深棕輪廓 |
| LEGO 風 | S03 積木玩具 | 商標注意見 S03 |
| 像素特效、遊戲特效、受擊與技能特效 | S04 像素＋`pixel-fx` skill | 特效與動作時序交 `pixel-fx` |
| Hologram | S28 全息投影 | |
| Blueprint | S29 藍圖 | |
| Anime Cel、Hand-Painted Cel、Graphic Cel、Outline-free Cel、Cel-Shaded CG Anime | S30 賽璐珞動畫 | 無描線的版本就把描線拿掉 |
| Knitted Yarn World | S31 毛線編織 | |
| Felt Puppet Stop Motion | S32 不織布偶停格 | |
| Cyberpunk Neon | A08 合成波 | 加雨夜、招牌與反光地面 |
| Thermal Cam | 配方 02 熱感應的視覺 | |
| Isometric | A18 等距 | |
| ASCII Terminal | S23 ASCII 字元 | |
| Watercolor | S22 動畫水彩 | |
| Rounded Toy CGI | S12 搪膠公仔 3D、S10 解說 3D | |
| Chunky Textured Low-Poly、Retro Game 3D | A19 低多邊形、S06 早期 3D 主機風 | |
| Comic 3D | S02 漫畫 | 3D 模型加粗外框與網點 |
| Nighttime Anime Pixel Art | S04 像素 | 夜景、霓虹與月光的像素版 |
| Gouache、Painterly 3D 這類畫筆質感的 3D（Warm Painterly 3D Animation、Painterly Cinematic 3D、Painterly Sculpted Animation、Expressive Gouache Fashion、Textured Gouache Character Illustration） | 暫無對應，待查 | 要用時先查一件代表作再寫成新條目；看過一格 Painterly Cinematic 3D（@vec3.motion 11/13 Reel 第 6 段）：暖色夕陽森林、筆觸貼在 3D 體積上，只看過縮圖，還不夠寫成條目 |
| Grotesque Street CGI、Sculptural 3D Fashion、Mannequin、Fluffy Toy、Fairy Tale & Myth、Mixed Media | 暫無對應，待查 | 同上；Fluffy Toy 最接近 S32 不織布偶 |
| Expressive 2D Animation、Hand Drawn、2D Illustrator、Pastel Flat 2D、Poster Vector、Flat cartoon、Isometric Flat Vector | S07 扁平向量（等距的加 A18） | 手繪感重的改用 S27 墨線生活插畫 |
| Neon Graphic Cinematic 3D | A08 合成波＋S09 CGI 電影感 | |
| Stickman Cartoon、Whiteboard Doodle | S21 火柴人塗鴉 | 白板版：白底、麥克筆線、一筆一筆畫出 |
| Editorial Motion Graphics | A01 瑞士＋`sui-motion-graphic-reel` | 是做法多於畫風 |
| Colorful 3D、Studio 3D、3D Mix | S10 解說 3D | |
| Watercolor Chronicle | S22 動畫水彩 | |
| Vintage comic print、Halftone screen-print | S02 漫畫、A09 Riso | 網點與套色偏移 |
| White line art on black | S01 發光線稿、S08 極簡線條 | |
| Ink silhouette with a red sun | S24 水墨、S19 皮影 | 黑剪影＋一顆紅日 |
| 16-bit pixel art、8-bit sprite、Pixel Art | S04 像素 | 8 位元：色數更少、動作只有幾個姿勢循環 |
| Low-poly game、Low Poly | A19 低多邊形 | |
| Mosaic、Glass Mosaic、磁磚拼貼 | S33 馬賽克磁磚 | |
| Neon-Synth | A08 合成波 | |
| Three.js-3D | S09 CGI 電影感、S10 解說 3D | 「用 three.js 做」是做法不是畫風，照要的質感挑 |
| 8-Bit Quest | S04 像素 | 做成遊戲畫面：上緣分數與關卡字、下緣一排道具欄，主角像可操作的角色 |
| Pixel Explainer | S04 像素＋S11 浮卡逐字解說 | 像素場景角落放一張小標題卡，旁白講到哪、場景演到哪 |
| Pixel Lightning、像素閃電 | S04 像素＋`pixel-fx` skill | 閃電一兩格全亮再熄、落點炸出火花粒子；時序交 `pixel-fx` |
| Chalk Doodle | S05 黑板粉筆 | |
| Golden Neon | A08 合成波 | 雨夜，霓虹換成金黃與琥珀色，不用粉紫 |
| Retro Console | S06 早期 3D 主機風 | |
| Pop Comic | S02 漫畫 | 分格加對話框 |
| Flat Poster | S07 扁平向量 | |
| Line Diagram | S08 極簡線條、S29 藍圖 | 黑底細白線，旁邊加尺寸刻度與標註 |
| Cinematic 3D | S09 CGI 電影感 | |
| Toy Bricks | S03 積木玩具 | 商標注意見 S03 |
| Soft 3D | S10 解說 3D、S12 搪膠公仔 3D | |
| Stat Reveal | A01 瑞士＋`sui-motion-graphic-reel` | 深底、大數字逐位跳出，旁邊放一個會發光的主體（例如行星）；是做法多於畫風 |
| Marble Run | S10 解說 3D 的外觀＋物理模擬 | 奶油色底、柔軟投影，彈珠沿漏斗與軌道滾下 |
| Neon City | A08 合成波＋S09 CGI 電影感 | 雨夜街道，鏡頭沿路往前推，招牌倒映在濕地面 |

---

## 線條與發光

### S01 發光線稿 Glow Sketch
- **看得見**：純黑底；所有物件只剩細亮線，主角一條紅色發光輪廓；路燈與窗戶是暖金色光暈；城市輪廓線微微發亮。
- **動法**：光的強弱在呼吸；路燈偶爾閃一下；遠方窗戶一盞一盞小亮點輪流亮起。整體慢。
- **適合**：未來感解說、高對比動態圖、夜景。
- **可借的出處**：待查（相近：A08 合成波的霓虹與黑底）。
- **網頁做法**：SVG 線條＋`filter: drop-shadow` 疊兩層（一層細、一層寬而淡）做光暈；動畫只改 `opacity` 與光暈強度。
- **prompt**：`dark glow-sketch rendering: thin luminous outlines on pure black, the hero object outlined in glowing red, warm golden halos on lamps and windows, softly glowing skyline contours, elegant night-time mood`

### S08 極簡線條 Minimal Line
- **看得見**：大量留白；極細等寬線，只畫必要的幾何；全畫面一兩個強調光點，主角用一條紅線。
- **動法**：線條被描出來、淡入淡出；動作少、停頓多，留呼吸。
- **適合**：高級介面動效、品牌系統、抽象解說。
- **可借的出處**：A20 線條畫（Picasso、Matisse 的線描）。
- **網頁做法**：SVG `stroke-dasharray`＋`stroke-dashoffset` 描線；同一時間只畫一條。
- **prompt**：`minimal line-art: very thin uniform strokes, sparse geometry, generous negative space, only one or two accent lights, the hero object drawn as a single red line, premium design-system feel`

### S05 黑板粉筆 Chalkboard
- **看得見**：墨綠黑板底、有擦過的灰霧；白色粉筆線帶顆粒與斷續；只有一兩處上色（例如車燈、領帶）；可加手寫標註。
- **動法**：線一筆一筆畫出來；字照書寫順序出現；偶爾有粉塵。
- **適合**：教學、教程、課堂、簡化解說。
- **可借的出處**：待查。
- **網頁做法**：SVG 描線＋`feTurbulence`／`feDisplacementMap` 讓線緣粗糙；底色加一層低透明度雜訊。擋住後景的底色塊要跟著該物件的線一起出現（線畫到一半才淡入），不然線還沒畫，深色塊先浮出來（2026-11-22 實測）。
- **prompt**：`chalkboard drawing: dark green board with faint eraser smudges, white chalk outlines with grainy broken edges, color only on one or two accents, hand-lettered labels, educational and hand-drawn`


### S13 鉛筆翻頁本 Pencil Flipbook
- **看得見**：米白紙、看得到紙纖維；石墨鉛筆線，同一條輪廓描了兩三次沒擦乾淨；只有灰階，最多一處淡淡上色；角落寫著頁碼（p.21）。
- **動法**：12 fps 左右，一拍兩格；每一格線條都重描，所以靜止的東西也在微微抖（線條「沸騰」）；換頁時頁碼跟著跳，偶爾看得到下一頁透上來的淡影。
- **適合**：故事開場、手作感教學、「從草稿到成品」的過程片。
- **可借的出處**：待查（翻頁書與動畫鉛筆稿）。
- **網頁做法**：同一份路徑每格加不同種子的小位移（`feTurbulence` 換 `seed`）再畫，製造沸騰；背景一層紙紋；用 `steps(12)` 或 `render(t)` 取整到 1/12 秒。
- **prompt**：`pencil flipbook animation frame: graphite lines on off-white paper with visible fibre, outlines traced two or three times, greyscale only, a handwritten page number in the corner, rough animator's pencil test feel`

### S14 線框 3D Wireframe 3D
- **看得見**：黑或深綠底；所有物件只剩三角面的邊，綠色或青色單色線；遠的線比較暗；看得到格線地面；像早期電腦圖學或雷達螢幕。
- **動法**：攝影機慢慢繞；物件的頂點先一個個亮起、邊再連上；掃描線或雷達掃過時線條變亮。
- **適合**：科技、資料、資安、「系統在算」的畫面。
- **可借的出處**：待查（相近：S01 發光線稿；本條是 3D 的網格，不是 2D 的輪廓）。
- **網頁做法**：three.js `WireframeGeometry`／`EdgesGeometry`＋`LineBasicMaterial`，加霧讓遠的線變暗；後製加一點 bloom。
- **prompt**：`wireframe 3D rendering: every object reduced to the edges of its polygon mesh, single-colour green lines on near-black, a receding grid floor, distant lines dimmer, early computer-graphics feel`

### S21 火柴人塗鴉 Stickman
- **看得見**：白紙；一條黑筆畫出圓頭、單線四肢的小人；背景是幾筆就交代的物件（太陽、雲、箱子、坡道）；線有手抖；只有一個顏色點綴（例如紅球）。
- **動法**：動作誇張、彈性大；線條像剛畫上去的；碰撞有「碰」的小星號；整體好笑。
- **適合**：輕鬆解說、梗圖式內容、連鎖反應。
- **可借的出處**：待查（相近：S08 極簡線條，本條要的是手抖與幽默，不是高級感）。
- **網頁做法**：SVG 細線＋`feDisplacementMap` 微抖；人物用骨架（幾個關節點）驅動，四肢就是兩點連線。
- **prompt**：`hand-drawn stickman doodle: round-headed stick figures in black pen on white paper, a few quick props like a sun, clouds and boxes, slightly wobbly lines, one red accent object, playful and funny`

### S27 墨線生活插畫 Ink Line Life
- **看得見**：暖白紙上一支細墨筆畫到底；人物沒有臉、比例修長，靠帽子和髮型辨認；四肢是兩條沒接起來的開口線；建築畫成正立面、細節多（瓦片、格柵、招牌）；只用一兩個平塗小色塊（紅燈籠、靛藍和服）。夜晚整張反轉成靛藍紙、淡色墨線，窗戶發暖光。
- **動法**：走路是算出來的：踩地的腳不滑、身體在每一步上升又下沉、衣襬跟著膝蓋開合；袖子、圍巾、燈籠掛在彈簧或擺錘上晃；滑鼠移動就是風；點人物會回應（脫帽、鞠躬），不是跳出按鈕。日夜循環時人照正常速度走，只壓縮來人的頻率與天色。
- **適合**：品牌插畫元件、首頁的「活著的街景」、旅遊或在地內容、溫和的說故事。
- **可借的出處**：JDhruv14/line-art-animation（MIT，2026-11-22 讀取；Instagram @githubsignals 介紹）；相近 A20 線條畫。
- **網頁做法**：直接用它的 `lib/`（四個無依賴 TypeScript 模組：`ink.ts` 畫線、`gait.ts` 算步態、`motion.ts` 彈簧擺錘、`daynight.ts` 日夜配色），MIT 可以搬，保留授權聲明。墨色用 `currentColor`、紙用一個 class，日夜一次換色；元件是一張卡，頁面背景不跟著變。先做一個人給人看過，再做整條街。
- **prompt**：`animated ink line illustration: one thin slightly wobbly pen line on warm paper, faceless figures recognised by hats and hair, limbs drawn as two open strokes, street buildings drawn flat as elevations with rich tile and lattice detail, one or two small flat colour accents`


### S28 全息投影 Hologram
- **看得見**：深色底；物件是半透明的青藍光體，邊緣最亮、內部淡；水平掃描線穿過；偶爾整體錯位一兩像素；底部有投影台的光圈。
- **動法**：掃描線由下往上走；整體微微閃爍，偶爾斷訊一格再恢復；物件慢慢自轉。
- **適合**：科技發表、未來介面、資料視覺化的主視覺。
- **可借的出處**：待查（相近：S14 線框 3D 是網格線，本條是半透明的發光體）。
- **網頁做法**：three.js 用 Fresnel 邊緣光（`ShaderMaterial` 依視角算亮度）＋`AdditiveBlending`；掃描線是一張捲動的條紋貼圖；斷訊用偶發的 `translateX` 抖動。
- **prompt**：`hologram rendering: translucent cyan light-forms brightest at the edges, faint interiors, horizontal scanlines drifting upward, occasional one-frame glitch offset, a glowing projector ring below, dark surroundings`

### S29 藍圖 Blueprint
- **看得見**：普魯士藍底；白色或淡藍細線畫成工程圖：正視、側視、剖面；有尺寸標註線、箭頭、格線、手寫風的編號註記。
- **動法**：線照工程繪圖順序畫出來（外框→細節→標註）；標註數字跳出；可從平面圖「立起來」變成 3D 線框。
- **適合**：產品原理、架構說明、「怎麼做出來的」。
- **可借的出處**：工程藍曬圖（cyanotype 藍圖，19 世紀末起用於建築與機械圖）。
- **網頁做法**：SVG 細線＋`stroke-dashoffset` 依序描；格線是重複背景；標註用等寬字型。
- **prompt**：`engineering blueprint: Prussian-blue paper, thin white technical linework in front, side and section views, dimension lines with arrows, a faint grid, small handwritten callout numbers`

## 平面與印刷

### S02 漫畫 Comic Art
- **看得見**：粗黑外框；平塗高彩度色；網點陰影；畫面一角有說明框；可有速度線。
- **動法**：像翻格子一樣切換；字卡與狀聲詞「啪」地跳出；前後景小幅視差。節奏有力。
- **適合**：故事型社群內容、輕鬆的解說、普普視覺。
- **可借的出處**：A03 普普藝術（Lichtenstein 的網點與說明框）。
- **網頁做法**：`radial-gradient` 重複背景做網點；粗 `stroke`；切換用 `steps()` 或硬切。
- **prompt**：`comic-book art: bold black ink outlines, flat vibrant colors, halftone dot shading, a caption box in one corner, playful editorial comic feel, every object instantly readable`

### S07 扁平向量 Flat Vector
- **看得見**：圓潤簡化的形；平塗、色彩平衡；陰影是一塊深一階的色；乾淨外框或無外框；現代雜誌插畫感。
- **動法**：乾淨的滑入；前中後景分層視差；緩動整齊，像簡報。
- **適合**：簡報、新創、解說影片、乾淨的社群圖。
- **可借的出處**：A04 扁平 2D（Charley Harper、Kurzgesagt；每個物件三階色）。
- **網頁做法**：純 SVG 色塊；每層一個 `translateX` 視差速度。
- **prompt**：`flat vector illustration: smooth simplified shapes, balanced flat colors, simple one-step shadows, clean outlines, modern editorial style, minimal and presentation-ready`


### S15 木刻版畫 Woodblock Print
- **看得見**：刻刀留下的粗細不均黑線；四到六個平塗色版，色塊邊緣有點沒對準；紙紋與木紋透出來；天空用漸層刷色（一條色帶）；外圍有一圈邊框。
- **動法**：像一版一版印上去：先黑線版、再一色一色疊；動作少、停格感；水與雲用重複的刻線圖案慢慢移。
- **適合**：在地、節慶、文化題材、海報式動態。
- **可借的出處**：浮世繪（葛飾北齋〈神奈川沖浪裏〉，1831 年前後）。
- **網頁做法**：SVG 每個色版一層、各自小偏移；黑線用不規則寬度的路徑；整張疊一層紙紋 `mix-blend-mode: multiply`。
- **prompt**：`woodblock print: carved black keylines of uneven width, four to six flat colour blocks slightly off-register, visible paper and wood grain, a graded colour band in the sky, a printed border around the frame`

### S17 噴漆模板 Graffiti Stencil
- **看得見**：磚牆或水泥牆底；人物是剪紙模板噴出來的單色剪影，邊緣有噴霧的顆粒與流下的漆痕；兩三色；牆上有手寫標記。
- **動法**：一層模板一層模板「噴」上去（顆粒從邊緣往內填滿）；畫面硬切；偶爾整張晃一下像手持攝影。
- **適合**：街頭、潮流、叛逆感的宣傳、音樂活動。
- **可借的出處**：1980 年代巴黎的模板塗鴉（Blek le Rat）。
- **網頁做法**：剪影用 SVG `mask`，邊緣用 `feTurbulence` 做噴霧顆粒；漆痕是幾條往下長的細路徑。
- **prompt**：`graffiti stencil art on a brick wall: figures as single-colour spray-painted stencil silhouettes, grainy overspray at the edges, a few paint drips, two or three colours, a hand-written tag nearby`

### S20 兒童蠟筆 Kids Crayon
- **看得見**：白紙；蠟筆的粗蠟質筆觸，塗色超出邊線、留白沒塗滿；斜線塗法看得到方向；顏色鮮豔但不精準；比例天真（太陽有臉、房子歪）。
- **動法**：一筆一筆塗出來；物件跳動、搖晃，像小孩拿著紙在演；可以有 8～12 fps 的抖動。
- **適合**：親子、教育、溫馨品牌、童趣活動。
- **可借的出處**：待查。
- **網頁做法**：canvas 用很多條半透明短筆畫沿同一方向塗滿形狀，筆畫刻意超出邊界；紙紋疊在上面讓蠟筆「卡」在紙紋凹處。
- **prompt**：`children's crayon drawing: waxy crayon strokes on white paper, colouring that goes outside the lines with gaps left white, visible diagonal hatching, bright naive colours, naive proportions`

### S22 動畫水彩 Anime Watercolor
- **看得見**：手繪動畫的水彩背景：天空大塊藍、積雨雲很立體；草地與樹用層層透明水彩疊出；光很柔、帶夏天的暖；物件有乾淨的描線；可飄花瓣或光點。
- **動法**：慢；雲緩緩移、草被風吹出一波波浪；花瓣與光點飄；鏡頭小幅橫移。
- **適合**：情緒、回憶、季節感、溫柔的品牌故事。
- **可借的出處**：日本手繪動畫的背景美術（待查一件具體作品；prompt 不寫工作室或作者名）。
- **網頁做法**：背景用預先畫好的分層圖做視差；草的波浪用 shader 或多條 `skewX` 動畫；花瓣是粒子。
- **prompt**：`hand-painted anime background in watercolour: big blue summer sky with towering cumulus, layered translucent greens for grass and trees, soft warm light, clean line work, drifting petals and light motes`

### S24 水墨 Ink Wash
- **看得見**：宣紙米白；濃淡墨一筆畫出山與路，大片留白；遠山很淡；只有一個朱紅印章或一個紅色物件；筆觸有飛白。
- **動法**：一筆從起點畫到終點、墨會暈開；動作少而慢；畫面安靜。
- **適合**：東方、靜心、高級、節氣、茶與酒。
- **可借的出處**：南宋馬遠（「馬一角」，主景放一角、其餘留白）。
- **網頁做法**：SVG 粗細變化的筆觸路徑描出來；暈墨用 `feGaussianBlur` 的淡邊；紙紋一層；紅色只給一處。
- **prompt**：`Chinese ink wash painting: varied black ink strokes on off-white rice paper, wide empty space, faint distant mountains, dry-brush streaks, a single vermilion seal or red object`


### S30 賽璐珞動畫 Cel Anime
- **看得見**：乾淨的黑色描線；角色上色只分亮面與暗面兩階（硬邊陰影）；高光是一小塊白；背景可以是較細緻的手繪；3D 版是卡通著色（cel-shaded）的模型，看起來像 2D。
- **動法**：一拍二或一拍三（12 或 8 fps）的有限動畫；動作有關鍵姿勢的停頓；速度線、表情符號誇張化。
- **適合**：故事、角色介紹、年輕向社群內容。
- **可借的出處**：日本電視動畫的賽璐珞上色（待查一件具體作品；prompt 不寫工作室或作者名）。
- **網頁做法**：2D 用 SVG 平塗兩階；3D 用 three.js `MeshToonMaterial`＋兩階漸層貼圖＋外框（背面放大一點塗黑）；動畫時間取整到 1/12 秒。
- **prompt**：`cel-shaded anime look: clean black line art, flat two-tone shading with hard shadow edges, small white highlights, detailed painted background, limited animation on twos`

## 遊戲與玩具

### S04 像素 Pixel Art
- **看得見**：像素格對齊；少色數；8／16 位元遊戲感，可加血條、分數等介面；主角小而好認。
- **動法**：一格一格跳，不補間；雲朵循環；介面元素閃爍。避免太滑順。
- **適合**：遊戲內容、復古活動、App 開場、懷舊動態。
- **可借的出處**：A17 像素風（KOF、Dave the Diver）；可疊配方 09。
- **網頁做法**：低解析 canvas 放大＋`image-rendering: pixelated`；動畫用 `steps()`。
- **prompt**：`clean pixel art: aligned to a strict pixel grid, limited palette, retro 8/16-bit game UI overlay, pixel clouds and skyline, a compact readable hero sprite, crisp composition`

### S06 早期 3D 主機風（PS2 時代）
- **看得見**：低多邊形、塊狀幾何；低解析度模糊貼圖；簡單打光；有點霧；整體是 2000 年前後主機遊戲的感覺。
- **動法**：遊戲攝影機式的移動；低多邊形物件旋轉；遊戲介面式的轉場。
- **適合**：懷舊遊戲剪輯、復古循環動畫、風格化廣告。
- **可借的出處**：A19 低多邊形（Timothy J. Reynolds、Kentucky Route Zero）是它的插畫版；本條要的是「當年硬體的粗糙」，不是精修的平塗切面。
- **網頁做法**：three.js 低面數模型＋小尺寸貼圖用 `NearestFilter`＋`flatShading`＋霧。
- **prompt**：`early-2000s console game look: low-poly chunky geometry, soft low-resolution textures, simple vertex lighting, light distance fog, nostalgic early-3D aesthetic, clean and iconic`

### S03 積木玩具（別名：樂高風）
- **看得見**：所有物件由凸點積木拼成；角色是方頭積木小人；高光亮、塑膠反光；顏色鮮明、像精修過的玩具攝影。
- **動法**：動作俐落、帶玩具感；輪子小幅轉；攝影機的動作像在拍桌上模型；新物件「卡」進去。
- **適合**：親子內容、產品示範、輕鬆的品牌視覺。
- **可借的出處**：待查。
- **⚠ 商標**：LEGO 是註冊商標。對外產出不用 LEGO 字樣、logo、凸點上的字、官方人偶的正式造型；prompt 寫「brick-built toy」，不寫品牌名。
- **網頁做法**：three.js 方塊＋圓柱凸點，物件以 `InstancedMesh` 排列；進場用彈跳的 `scale`。
- **prompt**：`brick-built toy diorama: every object assembled from studded plastic bricks, characters as blocky toy figures, glossy plastic highlights, bright saturated colors, polished toy-photography look (generic bricks, no brand marks)`


### S12 搪膠公仔 3D Vinyl Toy
- **看得見**：設計師玩具：大頭、短身、圓潤，像搪膠一體成型；表面半光澤、軟塑膠的柔亮高光；色彩飽和；場景也做成玩具尺寸（棕櫚樹、車都是圓角小物）。
- **動法**：彈性、有重量的小跳；落地輕壓扁；攝影機像在桌上拍模型。
- **適合**：品牌吉祥物、潮玩、親切的產品介紹。
- **可借的出處**：待查（相近：A05 黏土 3D 的圓潤與擠壓、S10 解說 3D 的舞台）。
- **網頁做法**：three.js 圓角幾何＋`MeshPhysicalMaterial`（`clearcoat` 低、`roughness` 0.4 左右）；柔和陰影；進場用彈跳縮放。
- **prompt**：`vinyl designer-toy 3D: chunky big-headed figures with rounded one-piece forms, semi-gloss soft plastic highlights, saturated colours, the whole set built toy-sized, tabletop photography lighting`

### S16 十字繡 Cross Stitch
- **看得見**：米白十字繡布（看得到格子孔）；每一格是一個 X 形針腳，像素一樣排；色數少；線有絲光與立體；邊緣看得到繡框或沒剪的線頭。
- **動法**：一格一格繡出來（X 的兩撇依序出現）；動畫是格子層級的替換，像 S04 像素但慢、軟。
- **適合**：手作、溫暖、懷舊、居家品牌。
- **可借的出處**：待查（相近：S04 像素的格子規則）。
- **網頁做法**：先把場景算成低解析色格（同 S04），再把每格畫成兩條交叉的短線，加一點陰影做線的立體；底層畫布紋格子。
- **prompt**：`cross-stitch embroidery: an off-white aida cloth grid, every pixel a small X stitch in glossy thread, limited palette, slight thread texture and shadow, visible hoop edge or loose thread ends`

### S19 皮影 Shadow Puppet
- **看得見**：暖橘到琥珀色的光幕；人物與景物是黑色剪影，關節處看得到鉚釘與支桿；可透出鏤空花紋；光源在中間，四周較暗。
- **動法**：只能在幕面上平移、轉關節；四肢擺動像被桿子推；靠近光幕時邊緣清楚、離遠變大變模糊。
- **適合**：說故事、傳說、文化題材、戲劇化開場。
- **可借的出處**：台灣皮影戲；Lotte Reiniger〈阿基米德王子歷險記〉（1926，剪影動畫）。
- **網頁做法**：SVG 黑色剪影分成幾段，用 `transform-origin` 設在關節轉動；背景 `radial-gradient` 暖光；模糊程度跟「離幕距離」連動。
- **prompt**：`shadow puppet theatre: black cut-out silhouettes with visible joint rivets and control rods against a glowing warm amber screen, ornamental cut-out patterns, a bright centre falling off to dark edges`

### S25 體素 Voxel Art
- **看得見**：世界由同尺寸的小立方體堆成；每個面一個平塗色，三個面明暗不同；邊緣是直角階梯；像方塊沙盒遊戲的低解析 3D。
- **動法**：物件一塊一塊長出來或掉下來堆好；攝影機繞；水是一層緩慢上下的藍色方塊。
- **適合**：遊戲、建造、科普、「一步步搭起來」的流程。
- **可借的出處**：待查（相近：S04 像素是 2D 格子、S03 積木玩具有凸點與塑膠光，本條是無凸點的啞光方塊）。
- **網頁做法**：three.js `InstancedMesh` 一個方塊幾何畫全部；`flatShading`、`NearestFilter`；進場依高度錯開時間。
- **prompt**：`voxel art: the whole world built from equal-sized small cubes, each face a flat colour with three-tone face shading, stair-stepped edges, low-resolution sandbox-game 3D, clean daylight`


### S31 毛線編織 Knitted Yarn
- **看得見**：所有東西都是毛線織的：看得到一排排 V 字針目、毛線的絨毛與粗細；顏色是毛線的飽和但柔和；邊緣是收針的弧線；光很柔，像拍桌上的手作。
- **動法**：停格感（8～12 fps）；物件移動時針目紋理跟著物件走、不會滑；偶爾一根線頭晃動。
- **適合**：冬季、溫暖、手作品牌、療癒內容。
- **可借的出處**：待查（相近：S16 十字繡是平面繡布，本條是立體的編織物）。
- **網頁做法**：three.js 模型貼一張 V 字針目的法線貼圖＋絨毛用 `sheen`；2D 版用重複的 V 形圖案沿物件方向排。
- **prompt**：`knitted yarn world: every object made of knitted wool with visible rows of V-shaped stitches, fuzzy fibres, soft saturated yarn colours, cast-off edges, soft tabletop lighting, stop-motion feel`

### S32 不織布偶停格 Felt Puppet
- **看得見**：角色和場景用不織布、毛氈剪縫：表面有毛絨顆粒、邊緣有縫線；眼睛是鈕扣或小圓布；比例圓胖；看得到一點點手工的不對稱。
- **動法**：停格動畫（12 fps），每格位置有極小的抖動；表情靠換一塊布（嘴形、眉毛）而不是變形。
- **適合**：兒童、溫馨品牌、教學角色、節日。
- **可借的出處**：毛氈與布偶停格動畫（待查一件具體作品）；相近 A05 黏土 3D（本條是布，不會被擠壓變形）。
- **網頁做法**：three.js 圓胖幾何＋毛氈材質（高 `roughness`、`sheen`、雜訊法線）；縫線是沿邊緣的短虛線；時間取整到 1/12 秒並加每格微抖。
- **prompt**：`felt puppet stop-motion: characters and sets cut and stitched from felt with fuzzy surface texture, visible edge stitching, button eyes, chubby proportions, slight handmade asymmetry, frame-by-frame jitter`

### S33 馬賽克磁磚 Mosaic
- **看得見**：整個畫面由一顆顆小磁磚拼成（方形、圓形或六角形），磁磚之間有淺色水泥灰縫（和 S18 LED 點陣的黑縫分開，否則兩者看起來一樣，2026-11-22 實測）；每顆一個平塗色，顏色偏飽和；同一區塊裡相鄰磁磚有一點色差，看得出手工貼；可以加一點釉面反光。
- **動法**：以磁磚為單位換色，沒有補間；動態（岩漿、火花、水波）是一顆顆磁磚依序亮起或換色；爆發時磁磚一圈圈往外點亮。
- **適合**：節慶、在地文化、公共藝術感、需要「拼起來」意象的主題。
- **可借的出處**：待查（相近：S04 像素是無縫的方格，S16 十字繡是 X 針腳；本條的格子之間一定有灰縫）。
- **網頁做法**：場景先算成低解析色格（同 S04），每格畫成縮小一點的磁磚（留出灰縫），顏色加 ±5% 隨機色差（用固定種子）；六角形就把奇數列錯開半格。範例：`tests/s-batch2/index.html`。
- **prompt**：`mosaic tile artwork: the whole scene assembled from small square or hexagonal tiles with light cement grout lines between them, each tile a flat saturated colour with slight hand-laid variation, faint glazed highlights`

## 3D 與電影

### S09 CGI 電影感 CGI Motion
- **看得見**：精修的 3D 算圖；柔和電影光；表面有細微反射；淺景深；高級夜景氣氛。主角很亮麗但造型簡單。
- **動法**：攝影機緩慢漂移；高光在車身上滑過；光線從一側掃過。
- **適合**：高價產品廣告、精品短片、電影感動態。
- **可借的出處**：待查（相近：A07 Y2K 鉻金屬的反射規則）。
- **網頁做法**：three.js `MeshPhysicalMaterial`＋環境貼圖＋後製景深；動畫只動攝影機與燈。
- **prompt**：`polished CGI render: soft cinematic lighting, subtle reflections on smooth surfaces, shallow depth of field, premium night-city atmosphere, hero object glossy yet simple`

### S10 解說 3D Explainer 3D
- **看得見**：圓角造型；白天明亮光線；啞光、像玩具的材質；形狀簡單；親切、好懂。
- **動法**：柔和、圓潤的移動；物件動作清楚、一次一個；舞台式擺位。
- **適合**：SaaS 解說、教育動畫、親切的品牌內容。
- **可借的出處**：A05 黏土 3D（擠壓、圓潤）、A18 等距視角（舞台擺位）。
- **網頁做法**：three.js 圓角幾何（`RoundedBoxGeometry`）＋柔和陰影；緩動用 ease-in-out。
- **prompt**：`soft explainer-style 3D: rounded forms, bright daylight, matte toy-like materials, simple shapes, friendly approachable look, clean modern staging, easy to animate`


### S26 1930 年代橡皮管卡通 Rubber Hose Cartoon
- **看得見**：黑白或褪色的棕灰；角色四肢像橡皮管、沒有關節，戴白手套；連房子、雲都有眼睛；粗黑線、白底；有底片顆粒、刮痕和閃爍。
- **動法**：所有東西照拍子一起上下彈（連建築也跳）；擠壓與伸展很誇張；畫面輕微閃爍和晃動，像老放映機。
- **適合**：復古、搞笑、音樂、節奏感強的內容。
- **可借的出處**：1920–30 年代的美國卡通，例如迪士尼〈汽船威利號〉（1928）、弗萊舍兄弟的作品。只借畫法，不重畫任何既有角色。
- **網頁做法**：SVG 粗線；所有物件共用一條節拍（`sin` 取絕對值）做上下彈；整張加顆粒、垂直刮痕與亮度閃爍的濾鏡層。
- **prompt**：`1930s rubber-hose cartoon: black and white with thick ink lines, bendy limbs without joints, white gloves, buildings and clouds with cartoon eyes, film grain, scratches and gentle flicker, everything bouncing to the beat`

## 介面、字元與看板

### S11 浮卡逐字解說 Floating Card Explainer
- **看得見**：淺灰底，正中一圈很大的柔白光暈；白色圓角卡片帶大而淡的投影，浮在畫面中上；卡片上的分類標籤是白底小膠囊，說明句是黑底白字膠囊；畫面下方四分之一處只有一行字幕，關鍵字加粗；全片只有一個強調色（例如珊瑚橘），只留給行動呼籲那個字。直式 9:16。
- **動法**：旁白決定所有節拍。字幕一個詞一個詞進：從模糊、淺灰、略低的位置，約 0.15 秒變成清楚、深色、到位；一句 3～5 個詞，下一句開始時整句換掉。卡片彈出（縮放 0.92→1、淡入、一點點回彈），多張卡錯開 60～80ms；數字卡計數上升；清單卡逐項打勾；輸入框卡逐字打出提示句；開場與結尾用扇形疊起的卡片收束。
- **適合**：工具教學、功能介紹、Reels／Shorts 解說、課程宣傳。
- **可借的出處**：Instagram @automance_ 的 Reel（2026-11-22 讀取，推薦 lemo-opuscar 的那支）。版式本身的經典待查。
- **網頁做法**：整支片寫成 `render(t)` 純函數；逐字時間來自 whisper 的 word timestamps，每個詞的模糊（`filter: blur()`）、透明度、位移都由 t 算出；卡片只動 `transform` 與 `opacity`；背景是一層 `radial-gradient`。整句的每個詞一開始就排進版面（還沒念到的透明佔位），否則置中的字幕每多一個詞整行就跳一次（2026-11-22 實測）。範例：`tests/s11/index.html`，逐幀呼叫 `render(t)` 截圖再用 ffmpeg 合成。
- **prompt**：`clean vertical explainer frame: light grey background with a large soft white radial glow, floating white rounded cards with big soft shadows, small pill labels, one line of word-by-word captions in the lower quarter with key words in bold, a single coral accent`

### S18 LED 點陣看板 LED Matrix
- **看得見**：黑底上一格一格的圓點燈，亮的點有光暈、沒亮的是暗灰點；色數少（紅、黃、綠或全彩低解析）；可有跑馬燈字。
- **動法**：以「點」為單位換格，沒有補間；跑馬燈一格一格往左；整張偶爾掃一次亮度。
- **適合**：活動倒數、交通與看板感、夜市、運動賽事。
- **可借的出處**：待查（相近：S04 像素；本條的像素是會發光的圓點，中間有黑縫）。
- **網頁做法**：場景先畫到低解析 canvas，再把每格畫成圓點，亮度＝原色亮度；光暈用 `shadowBlur` 或疊一層模糊。
- **prompt**：`LED dot-matrix display: the scene rendered as a grid of round LED dots on black, lit dots glowing with bloom, unlit dots dark grey, limited bright palette, a scrolling marquee line`

### S23 ASCII 字元 ASCII Art
- **看得見**：黑底綠字（或白底黑字）的等寬字元畫；亮處用 `@#%`、暗處用 `.:-`；有提示符或標題 `> ASCII_ART`；可加 CRT 掃描線。
- **動法**：字元逐格換（像終端機刷新）；物件移動是字元在格子裡跳；新東西由打字游標「打」出來。
- **適合**：工程、開發者、駭客感、終端機主題。
- **可借的出處**：待查（相近：配方 05 賽博監控的終端感、配方 08 動態文字）。
- **網頁做法**：場景畫到隱藏的低解析 canvas，每格查一個字元，輸出到 `<pre>`；等寬字型。字元要照「物件」給、物件邊界一律描成實心字元（`#`），不要只照原色亮度換：天空、房子、草地的亮度多半都在中間調，換出來整張是同一種符號、主角看不見（2026-11-22 實測）。行數乘行高要放得進框，不然下半部被裁掉。範例：`tests/s-batch2/index.html`（S16、S18、S19、S23 共用一份場景格子）。
- **prompt**：`ASCII art rendering: the scene drawn entirely in monospaced characters, dense symbols like @#% for bright areas and .:- for dark, green on black terminal, a prompt-style title line, faint CRT scanlines`


---

## 一頁對照（挑畫風用）

| 編號 | 名稱 | 節奏 | 最該檢查 |
|---|---|---|---|
| S01 | 發光線稿 | 慢、呼吸 | 黑底上主角輪廓仍認得出 |
| S02 | 漫畫 | 有力、硬切 | 網點沒有蓋掉主角 |
| S03 | 積木玩具 | 俐落、彈 | 沒有品牌標記 |
| S04 | 像素 | 一格一格 | 沒有補間的滑順動作 |
| S05 | 黑板粉筆 | 書寫順序 | 上色處只有一兩個 |
| S06 | 早期 3D 主機 | 遊戲鏡頭 | 粗糙是刻意的，不是畫壞 |
| S07 | 扁平向量 | 整齊滑入 | 陰影只深一階 |
| S08 | 極簡線條 | 少、留白 | 同時只畫一條線 |
| S09 | CGI 電影感 | 漂移、光掃 | 造型沒有因為材質變複雜 |
| S10 | 解說 3D | 柔和、一次一個 | 光線是白天、材質是啞光 |
| S11 | 浮卡逐字解說 | 跟旁白逐詞走 | 字幕不蓋卡片；強調色只出現一次 |
| S12 | 搪膠公仔 3D | 彈、有重量 | 圓角一體成型，不是黏土的手捏痕 |
| S13 | 鉛筆翻頁本 | 12 fps 沸騰 | 靜止的線也要每格重描 |
| S14 | 線框 3D | 慢繞、掃描 | 遠的線比較暗，主角仍認得出 |
| S15 | 木刻版畫 | 一版一版印 | 色版有一點沒對準 |
| S16 | 十字繡 | 一格一格繡 | 每格是 X，不是方塊 |
| S17 | 噴漆模板 | 噴上去、硬切 | 邊緣有噴霧顆粒與流漆 |
| S18 | LED 點陣看板 | 點對點換格 | 點與點之間有黑縫 |
| S19 | 皮影 | 平移、轉關節 | 只能在幕面上動，看得到支桿 |
| S20 | 兒童蠟筆 | 塗出來、搖晃 | 塗色超出邊線、留白 |
| S21 | 火柴人塗鴉 | 誇張、好笑 | 只有一個顏色 |
| S22 | 動畫水彩 | 慢、風吹 | 透明水彩一層層疊，不是平塗 |
| S23 | ASCII 字元 | 終端刷新 | 等寬字型，主角輪廓讀得出 |
| S24 | 水墨 | 一筆、暈開 | 大片留白，紅色只一處 |
| S25 | 體素 | 一塊塊堆 | 三個面明暗不同 |
| S26 | 1930 橡皮管卡通 | 全體跟拍子彈 | 不出現任何既有卡通角色 |
| S27 | 墨線生活插畫 | 算出來的步態 | 腳不滑、四肢是開口雙線 |
| S28 | 全息投影 | 掃描、閃斷 | 邊緣最亮、內部透明 |
| S29 | 藍圖 | 照繪圖順序描 | 有尺寸標註，線是白或淡藍 |
| S30 | 賽璐珞動畫 | 一拍二 | 陰影只有一階、邊是硬的 |
| S31 | 毛線編織 | 停格、針目跟著走 | 看得到 V 字針目 |
| S32 | 不織布偶停格 | 12 fps 微抖 | 表情換布片，不變形 |
| S33 | 馬賽克磁磚 | 一顆顆換色 | 灰縫是淺色水泥，不是黑縫 |
