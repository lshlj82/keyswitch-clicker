# A key switch that lights up · 불이 켜지는 키 스위치

**경상국립대학교 수학물리학부 1학년 물리학2 교과목 보조자료 (데모 4 전기회로의 보충 자료)**

An interactive web demo built around a key-switch clicker keychain, a souvenir from the Korean Physical Society's Physics Outreach Committee special session [“무리(無理)하는 물리(物理)학자들 (Unphysical Physicists)”](https://www.kps.or.kr/conference/event/content/program/search_result_session.php?id=2748). Each transparent cell of the toy holds a clicky mechanical keyboard switch sitting on a 3 V coin cell. Pressing the key both makes the click and closes a contact that lights an LED, with no resistor in the circuit. The demo is a supplement to demo 4, Electric circuits, of the [Physics 2 interactive demos](https://lshlj82.github.io/physics2-GNU/) ([source](https://github.com/lshlj82/physics2-GNU)), listed there as 4a.

**Live pages:** [English](https://lshlj82.github.io/keyswitch-clicker/clicker-en.html) · [한국어](https://lshlj82.github.io/keyswitch-clicker/clicker-ko.html)

Created by Claude Opus 5.5, based on photos of the toy taken by Prof. Sang Hoon Lee, who also opened and repaired it. The photos appear on the page as references next to the drawings.
한국물리학회 물리대중화위원회 특별세션 “무리(無理)하는 물리(物理)학자들”의 기념품을 이상훈 교수가 찍은 사진을 바탕으로 Claude Opus 5.5가 만들었습니다. 사진은 그림과 나란히 참고 자료로 실려 있습니다.

## What's on the page · 페이지 구성

1. **Inside the switch.** An animated cutaway of the switch on its coin cell, labeled part by part and drawn from photos of the repaired toy, with the photos alongside for comparison. Press the key with the button, the keycap, or the space bar, or drag the travel slider for slow motion. The click jacket snaps at 1.8 mm, the leaf contact closes at 2.2 mm, and the LED lights. An optional click sound plays at the snap.
2. **The circuit.** A coin cell with internal resistance $`r`$, the switch, and an LED in series. The loop rule $`\mathcal{E} - ir - V_{\rm LED}(i) = 0`$ is solved graphically, as the intersection of the battery's load line with the LED's $`I`$–$`V`$ curve. Readouts show the current, the voltages and powers, and the continuous lighting time.
3. **Why it stopped working.** Choose where the LED's anode leg and switch pin B touch the coin cell (− face, + face or rim, or nothing). The page tells you whether the LED lights, and if not, whether the cause is an open circuit, reversed polarity, or both leads on the same terminal. The contact Prof. Sang Hoon Lee repaired is marked, and photos of the opened toy are included.
4. **Why the color keeps changing.** The toy's LED is a self-cycling RGB LED: three chips (red, green, blue) and a control chip inside one 3 mm dome, fed by the same two legs. The animation follows the program measured from a video of the toy (60 fps, key held for 28 s). The program repeats every 13.4 s: about 6.8 s of smooth fades between red and blue, starting at sky blue, then 24 flashes of 0.13 s every 0.27 s, green–blue–red four times and yellow–cyan–magenta four times. The page shows each chip's duty cycle over the program, optional slowed-down PWM pulses, and the operating point hopping between the three chips' I–V curves on the battery's load line. The measured timeline and six video frames appear below the animation. Releasing the key resets the program, as the real control chip does.
5. **Why a dying battery dims a blue LED first.** LED current versus battery emf for six colors. It shows why a draining cell dims the blue and green (InGaN) chips, which need about 3 V, long before the red one, which needs about 2 V.

## Models and assumptions · 모형과 가정

- **Coin cell:** CR1220, 3.0 V, 37 mAh, with an internal resistance of order tens of ohms (adjustable).
- **LED:** the Shockley equation plus a 12 Ω series resistance. Forward voltages at 10 mA are typical datasheet values: red 1.95 V, yellow 2.05 V, green 2.85 V, blue 2.95 V, cyan 3.00 V, white 3.00 V.
- **Switch:** the forces and travel are typical illustrative values for clicky "blue" switches, not measurements. Total travel is 4.0 mm, the click at 1.8 mm, and actuation at 2.2 mm.
- **Wiring (as in the repaired toy):** the coin cell sits − face up, facing the switch. A 3 mm LED sits in the switch's LED slot. Its cathode leg is hooked around one switch pin (A), the other switch pin (B) rests on the − face, and its anode leg wraps around the edge of the cell to the + face on the back. The contact Prof. Sang Hoon Lee repaired, pin B on the − face, is marked with a green circle on the page. The wiring is read from photos of the toy, not from a manufacturer's schematic.

## Files · 파일

- `clicker-en.html`: English page.
- `clicker-ko.html`: Korean page.
- `photos/`: eight reference photos and three figures from a video of the real toy by Sang Hoon Lee, cropped and compressed for the web (about 40–110 KB each). The souvenir in its bag and a side view appear in the header; the LED in its slot, the LED legs, the leg hooked on a switch pin, and the back of the cells appear in section 1; the opened toy and a switch tested on a coin cell appear in section 3. `video-timeline.png` (English) and `video-timeline-ko.png` (Korean) show the LED light measured frame by frame from a video of the toy, and `video-frames.jpg` shows six frames from that video; both appear in section 4.

Both pages are self-contained HTML, CSS, and JavaScript with no build step and no libraries. Drawings and plots are SVG. The IBM Plex Sans KR font loads from Google Fonts, with system fallbacks. The light/dark button (top right) shares its setting (`netsci-theme`) with the other course demos.

## Deploying · 배포

1. Put both HTML files, the `photos/` folder, and this `README.md` at the root of the repository.
2. In **Settings → Pages**, set the source to the `main` branch, root folder.
3. The pages will be served at `https://lshlj82.github.io/keyswitch-clicker/clicker-en.html` and `.../clicker-ko.html`.
