# Website-Breakthrough
Website Breakthrough

<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
        <title>ElementVerse - Crazy UI Elements, Backgrounds, Graphs & Layouts</title>
        <style>
            :root {
                --a: #8b5cf6;
                --c: #22d3ee;
                padding-top: env(safe-area-inset-top,0px);
                padding-bottom: env(safe-area-inset-bottom,0px)
            }

            html {
                scroll-padding-top: env(safe-area-inset-top,0px);
                scroll-behavior: smooth
            }

            * {
                box-sizing: border-box;
                margin: 0
            }

            body {
                background: #05040a;
                color: #ece8ff;
                font-family: system-ui,Segoe UI,sans-serif;
                min-height: 100vh;
                overflow-x: hidden
            }

            button {
                cursor: pointer;
                font: inherit
            }

            .bg i {
                position: fixed;
                width: 45vmax;
                height: 45vmax;
                border-radius: 50%;
                filter: blur(110px);
                opacity: .28;
                z-index: -2;
                animation: dr 14s ease-in-out infinite alternate
            }

            .bg i:nth-child(1) {
                background: #8b5cf6;
                top: -15%;
                left: -10%
            }

            .bg i:nth-child(2) {
                background: #22d3ee;
                bottom: -20%;
                right: -10%;
                animation-delay: -6s
            }

            .bg i:nth-child(3) {
                background: #f472b6;
                top: 30%;
                left: 45%;
                opacity: .15;
                animation-delay: -10s
            }

            @keyframes dr {
                to {
                    transform: translate(10vmax,6vmax) scale(1.25)
                }
            }

            .floor {
                position: fixed;
                left: -50%;
                width: 200%;
                bottom: 0;
                height: 45vh;
                z-index: -1;
                opacity: .45;
                background-image: linear-gradient(#8b5cf655 1px,transparent 1px),linear-gradient(90deg,#8b5cf655 1px,transparent 1px);
                background-size: 60px 60px;
                transform: perspective(300px) rotateX(60deg);
                transform-origin: bottom;
                animation: fl 2s linear infinite;
                -webkit-mask-image: linear-gradient(transparent,#000);
                mask-image: linear-gradient(transparent,#000)
            }

            @keyframes fl {
                to {
                    background-position: 0 60px
                }
            }

            header {
                min-height: 100vh;
                display: flex;
                flex-direction: column;
                justify-content: center;
                align-items: center;
                text-align: center;
                padding: 40px 20px;
                overflow: hidden
            }

            .scene {
                height: 300px;
                width: 100%;
                perspective: 900px;
                display: grid;
                place-items: center
            }

            #rig {
                position: relative;
                width: 120px;
                height: 120px;
                transform-style: preserve-3d;
                transition: transform .25s
            }

            .hc {
                position: absolute;
                inset: 0;
                transform-style: preserve-3d;
                animation: rt 10s linear infinite
            }

            .hc i {
                position: absolute;
                inset: 0;
                border: 2px solid var(--a);
                background: #8b5cf622;
                box-shadow: 0 0 25px var(--a) inset,0 0 20px #8b5cf688
            }

            .ring {
                position: absolute;
                inset: 0;
                transform-style: preserve-3d;
                animation: ry 14s linear infinite
            }

            .ring span {
                position: absolute;
                left: 50%;
                top: 50%;
                width: 36px;
                height: 36px;
                margin: -18px;
                border: 2px solid var(--c);
                background: #22d3ee22;
                box-shadow: 0 0 18px var(--c)
            }

            @keyframes rt {
                to {
                    transform: rotateX(360deg) rotateY(360deg)
                }
            }

            @keyframes ry {
                to {
                    transform: rotateY(360deg)
                }
            }

            h1 {
                font-size: clamp(40px,10vw,110px);
                font-weight: 900;
                letter-spacing: -3px;
                line-height: 1;
                animation: gl 3s infinite
            }

            h1 b {
                background: linear-gradient(90deg,#8b5cf6,#22d3ee,#f472b6,#8b5cf6);
                background-size: 300%;
                -webkit-background-clip: text;
                background-clip: text;
                color: transparent;
                animation: sh 6s linear infinite
            }

            @keyframes sh {
                to {
                    background-position: 300% 0
                }
            }

            @keyframes gl {
                0%,90%,100% {
                    transform: none;
                    text-shadow: none
                }

                93% {
                    transform: translateX(-5px) skewX(8deg);
                    text-shadow: 5px 0 #f0f,-5px 0 #0ff
                }

                96% {
                    transform: translateX(5px);
                    text-shadow: -5px 0 #f0f,5px 0 #0ff
                }
            }

            header p {
                opacity: .65;
                margin: 16px auto 26px;
                max-width: 560px
            }

            #go {
                padding: 18px 46px;
                font-size: 18px;
                font-weight: 800;
                border: 0;
                border-radius: 50px;
                background: linear-gradient(90deg,var(--a),var(--c));
                color: #05040a;
                box-shadow: 0 0 40px #8b5cf699;
                animation: pl 2s ease-in-out infinite
            }

            @keyframes pl {
                50% {
                    box-shadow: 0 0 80px #22d3ee;
                    transform: scale(1.05)
                }
            }

            .stats {
                display: flex;
                gap: 34px;
                margin-top: 34px;
                flex-wrap: wrap;
                justify-content: center
            }

            .stats span {
                opacity: .7;
                font-size: 13px;
                text-transform: uppercase;
                letter-spacing: 2px
            }

            .stats b {
                display: block;
                font-size: 28px;
                letter-spacing: 0;
                background: linear-gradient(90deg,var(--a),var(--c));
                -webkit-background-clip: text;
                background-clip: text;
                color: transparent
            }

            #lib {
                display: none;
                padding-top: 40px
            }

            #lib.on {
                display: block;
                animation: in .8s both
            }

            @keyframes in {
                from {
                    opacity: 0;
                    transform: translateY(30px)
                }
            }

            .ht {
                text-align: center;
                font-size: clamp(22px,4vw,38px);
                background: linear-gradient(90deg,#8b5cf6,#22d3ee);
                -webkit-background-clip: text;
                background-clip: text;
                color: transparent
            }

            #tabs {
                display: flex;
                flex-wrap: wrap;
                gap: 8px;
                justify-content: center;
                margin: 20px auto;
                max-width: 900px;
                padding: 0 12px
            }

            .tb {
                padding: 8px 18px;
                border-radius: 30px;
                border: 1px solid #ffffff22;
                background: #ffffff0a;
                color: #ddd;
                font-size: 14px;
                transition: .25s
            }

            .tb:hover,.tb.on {
                background: linear-gradient(90deg,var(--a),var(--c));
                color: #05040a;
                border-color: transparent;
                font-weight: 700
            }

            #grid {
                display: grid;
                grid-template-columns: repeat(auto-fill,minmax(310px,1fr));
                gap: 24px;
                padding: 10px min(5vw,60px) 90px
            }

            .card {
                border-radius: 18px;
                background: #ffffff08;
                border: 1px solid #ffffff1a;
                overflow: hidden;
                transition: transform .15s,border-color .3s,box-shadow .3s;
                animation: in .6s both
            }

            .card:hover {
                border-color: var(--a);
                box-shadow: 0 20px 60px #8b5cf633
            }

            .pv {
                aspect-ratio: 8/5;
                overflow: hidden;
                background: #0a0812;
                cursor: pointer
            }

            .pv iframe {
                border: 0;
                transform-origin: 0 0;
                pointer-events: none
            }

            .inf {
                display: flex;
                justify-content: space-between;
                align-items: center;
                gap: 8px;
                padding: 12px 14px
            }

            .inf b {
                display: block;
                font-size: 14px
            }

            .inf small {
                opacity: .5;
                font-size: 12px
            }

            .inf button {
                padding: 8px 13px;
                margin-left: 4px;
                border-radius: 9px;
                border: 1px solid #ffffff2a;
                background: #ffffff0f;
                color: #fff;
                font-size: 12px;
                transition: .2s
            }

            .inf button:hover {
                background: var(--a);
                border-color: var(--a)
            }

            .inf button[data-a=c] {
                background: linear-gradient(90deg,var(--a),var(--c));
                color: #05040a;
                font-weight: 700;
                border: 0
            }

            #md {
                position: fixed;
                inset: 0;
                background: #000000cc;
                backdrop-filter: blur(8px);
                display: none;
                place-items: center;
                z-index: 9
            }

            #md.on {
                display: grid
            }

            .box {
                width: min(1240px,96vw);
                height: 90vh;
                display: grid;
                grid-template-rows: auto 1fr;
                background: #0b0914;
                border: 1px solid #ffffff2a;
                border-radius: 16px;
                overflow: hidden
            }

            .bar {
                display: flex;
                flex-wrap: wrap;
                justify-content: space-between;
                align-items: center;
                gap: 8px;
                padding: 10px 14px;
                border-bottom: 1px solid #ffffff1a
            }

            .bar button {
                padding: 8px 14px;
                margin-left: 5px;
                border-radius: 9px;
                border: 1px solid #ffffff2a;
                background: #ffffff0f;
                color: #fff;
                font-size: 13px
            }

            .bar button:hover,.bar button.on {
                background: linear-gradient(90deg,var(--a),var(--c));
                color: #05040a;
                font-weight: 700
            }

            #mf {
                width: 100%;
                height: 100%;
                border: 0;
                background: #0a0812
            }

            #mc {
                display: none;
                overflow: auto;
                padding: 16px;
                font: 12px/1.55 ui-monospace,Consolas,monospace;
                color: #c4b5fd;
                tab-size: 2;
                white-space: pre-wrap;
                word-break: break-all
            }

            #tt {
                position: fixed;
                bottom: calc(30px + env(safe-area-inset-bottom,0px));
                left: 50%;
                transform: translateX(-50%) translateY(90px);
                background: linear-gradient(90deg,var(--a),var(--c));
                color: #05040a;
                font-weight: 700;
                padding: 12px 24px;
                border-radius: 30px;
                transition: .4s;
                z-index: 20
            }

            #tt.on {
                transform: translateX(-50%)
            }

            .ft {
                text-align: center;
                padding: 34px 20px calc(40px + env(safe-area-inset-bottom,0px));
                font-size: 14px;
                letter-spacing: 6px;
                text-transform: uppercase;
                opacity: .75;
                border-top: 1px solid #ffffff14
            }

            .ft b {
                background: linear-gradient(90deg,var(--a),var(--c));
                -webkit-background-clip: text;
                background-clip: text;
                color: transparent;
                font-weight: 900
            }
        </style>
    </head>
    <body>
        <div class="bg">
            <i></i>
            <i></i>
            <i></i>
        </div>
        <div class="floor"></div>
        <header>
            <div class="scene">
                <div id="rig">
                    <div class="ring" id="r1"></div>
                    <div class="hc" id="hc"></div>
                </div>
            </div>
            <h1>
                ELEMENT<b>VERSE</b>
            </h1>
            <p>Flip effects, animations, backgrounds, graphs, stats and full page layouts. Every one is different code. Click, preview, copy.</p>
            <button id="go">Show All Elements ↓</button>
            <div class="stats" id="st"></div>
        </header>
        <section id="lib">
            <h2 class="ht">Pick a category, press Copy Code</h2>
            <div id="tabs"></div>
            <div id="grid"></div>
        </section>
        <footer class="ft">
            An <b>Aksh</b>
            Venture
        </footer>
        <div id="md">
            <div class="box">
                <div class="bar">
                    <b id="mt"></b>
                    <span>
                        <button id="bp" class="on">Preview</button>
                        <button id="bc">Code</button>
                        <button id="cp">Copy Code</button>
                        <button id="x">Close</button>
                    </span>
                </div>
                <iframe id="mf" sandbox="allow-scripts"></iframe>
                <pre id="mc"></pre>
            </div>
        </div>
        <div id="tt">Code copied!</div>
        <script>
            const E = [];
            const add = (c, n, code) => E.push({
                c: c,
                n: n,
                code: code
            });

            /* ===== FLIP ===== */
            add('Flip', '3D Flip Card', `<style>.fc{width:200px;height:260px;perspective:800px}.fc div{position:relative;width:100%;height:100%;transition:.8s;transform-style:preserve-3d}.fc:hover div{transform:rotateY(180deg)}.fc b,.fc i{position:absolute;inset:0;display:grid;place-items:center;border-radius:18px;backface-visibility:hidden;-webkit-backface-visibility:hidden;font:700 22px system-ui}.fc b{background:linear-gradient(135deg,#7c3aed,#22d3ee);color:#fff}.fc i{background:#fff;color:#111;transform:rotateY(180deg);font-style:normal}</style><div class="fc"><div><b>Hover me</b><i>Surprise!</i></div></div>`);
            add('Flip', 'Rolling Cube Button', `<style>.cb{width:230px;height:70px;perspective:600px}.cb div{position:relative;height:100%;transform-style:preserve-3d;transition:.6s}.cb:hover div{transform:rotateX(-90deg)}.cb span{position:absolute;inset:0;display:grid;place-items:center;font:700 20px system-ui;border-radius:12px}.cb span:first-child{background:#f43f5e;color:#fff;transform:translateZ(35px)}.cb span:last-child{background:#fbbf24;color:#111;transform:rotateX(90deg) translateZ(35px)}</style><div class="cb"><div><span>Order Now</span><span>Free Delivery!</span></div></div>`);
            add('Flip', 'Click-to-Flip Coin', `<style>.co{position:relative;width:130px;height:130px;perspective:700px;cursor:pointer}.co div{position:relative;width:100%;height:100%;border-radius:50%;transform-style:preserve-3d;transition:1.4s cubic-bezier(.3,1.3,.5,1)}.co b,.co i{position:absolute;inset:0;border-radius:50%;display:grid;place-items:center;font:800 42px system-ui;backface-visibility:hidden;-webkit-backface-visibility:hidden;border:7px solid #b45309}.co b{background:radial-gradient(#fde68a,#f59e0b);color:#78350f}.co i{background:radial-gradient(#e5e7eb,#9ca3af);color:#374151;transform:rotateY(180deg);font-style:normal}</style><div class="co" onclick="this.r=(this.r||0)+180*(6+(Math.random()*2|0));this.children[0].style.transform='rotateY('+this.r+'deg)'"><div><b>H</b><i>T</i></div></div>`);
            add('Flip', 'Card Fan Spread', `<style>.fn{position:relative;width:170px;height:230px}.fn div{position:absolute;inset:0;border-radius:16px;transition:.5s;transform-origin:50% 100%;display:grid;place-items:center;font:700 44px system-ui;color:#fff}.fn div:nth-child(1){background:#ec4899}.fn div:nth-child(2){background:#8b5cf6}.fn div:nth-child(3){background:#06b6d4}.fn:hover div:nth-child(1){transform:rotate(-24deg) translateX(-55px)}.fn:hover div:nth-child(3){transform:rotate(24deg) translateX(55px)}</style><div class="fn"><div>A</div><div>K</div><div>Q</div></div>`);

            /* ===== ANIMATION ===== */
            add('Animation', 'Bouncing Dots', `<style>.bd{display:flex;gap:10px}.bd i{width:18px;height:18px;border-radius:50%;background:#22d3ee;animation:b .6s ease-in-out infinite alternate}.bd i:nth-child(2){animation-delay:.2s;background:#a78bfa}.bd i:nth-child(3){animation-delay:.4s;background:#f472b6}@keyframes b{to{transform:translateY(-44px)}}</style><div class="bd"><i></i><i></i><i></i></div>`);
            add('Animation', 'Orbit System', `<style>.ob{position:relative;width:200px;height:200px}.ob:before{content:'';position:absolute;inset:80px;border-radius:50%;background:#fbbf24;box-shadow:0 0 30px #fbbf24}.ob i{position:absolute;inset:0;border:1px dashed #ffffff33;border-radius:50%;animation:o 3s linear infinite}.ob i:after{content:'';position:absolute;top:-8px;left:calc(50% - 8px);width:16px;height:16px;border-radius:50%;background:#38bdf8}.ob i+i{inset:30px;animation-duration:1.8s;animation-direction:reverse}.ob i+i:after{background:#f472b6}@keyframes o{to{transform:rotate(360deg)}}</style><div class="ob"><i></i><i></i></div>`);
            add('Animation', 'Morphing Blob', `<style>.mb{width:180px;height:180px;background:linear-gradient(135deg,#f97316,#ec4899);animation:m 6s ease-in-out infinite;filter:drop-shadow(0 0 30px #ec4899)}@keyframes m{0%,100%{border-radius:60% 40% 30% 70%/60% 30% 70% 40%}50%{border-radius:30% 60% 70% 40%/50% 60% 30% 60%;transform:rotate(90deg) scale(1.1)}}</style><div class="mb"></div>`);
            add('Animation', 'Typewriter Terminal', `<style>.tw{font:700 26px ui-monospace,monospace;color:#4ade80;white-space:nowrap;overflow:hidden;border-right:3px solid #4ade80;width:0;animation:t 4s steps(22) infinite alternate,c .7s step-end infinite}@keyframes t{to{width:22ch}}@keyframes c{50%{border-color:transparent}}</style><div class="tw">console.log('Hello!');</div>`);
            add('Animation', 'Glitch Text', `<style>.gt{font:900 64px system-ui;position:relative;color:#fff}.gt:before,.gt:after{content:attr(data-t);position:absolute;left:0;top:0;width:100%;overflow:hidden}.gt:before{color:#0ff;left:3px;animation:g 2s infinite linear alternate-reverse;clip-path:inset(0 0 60% 0)}.gt:after{color:#f0f;left:-3px;animation:g 1.5s infinite linear alternate-reverse;clip-path:inset(60% 0 0 0)}@keyframes g{0%{transform:translate(0)}20%{transform:translate(-4px,2px)}40%{transform:translate(4px,-2px)}60%{transform:translate(-2px,3px)}100%{transform:translate(2px,-3px)}}</style><div class="gt" data-t="GLITCH">GLITCH</div>`);
            add('Animation', 'Liquid Fill Circle', `<style>.lw{width:180px;height:180px;border-radius:50%;border:4px solid #38bdf8;overflow:hidden;position:relative;display:grid;place-items:center}.lw:before,.lw:after{content:'';position:absolute;left:-50%;width:200%;height:200%;top:45%;border-radius:40%;background:#38bdf888;animation:w 5s linear infinite}.lw:after{background:#0ea5e988;border-radius:38%;animation-duration:8s;top:50%}.lw b{position:relative;z-index:1;font:800 36px system-ui;color:#fff}@keyframes w{to{transform:rotate(360deg)}}</style><div class="lw"><b>64%</b></div>`);
            add('Animation', 'Magnetic Button', `<style>.mg{padding:18px 44px;border:0;border-radius:50px;background:#a3e635;color:#111;font:800 18px system-ui;cursor:pointer;transition:transform .2s}</style><button class="mg">Magnetic</button><script>var b=document.querySelector('.mg');document.onmousemove=function(e){var r=b.getBoundingClientRect(),x=e.clientX-r.left-r.width/2,y=e.clientY-r.top-r.height/2;b.style.transform=Math.hypot(x,y)<160?'translate('+x*.4+'px,'+y*.4+'px)':''}<\/script>`);
            add('Animation', 'Ripple Click Button', `<style>.rp{position:relative;overflow:hidden;padding:16px 40px;border:0;border-radius:12px;background:#6366f1;color:#fff;font:700 18px system-ui;cursor:pointer}.rp span{position:absolute;border-radius:50%;background:#fff6;transform:scale(0);animation:r .6s linear}@keyframes r{to{transform:scale(4);opacity:0}}</style><button class="rp">Click me</button><script>document.querySelector('.rp').onclick=function(e){var r=this.getBoundingClientRect(),s=document.createElement('span'),d=Math.max(r.width,r.height);s.style.cssText='width:'+d+'px;height:'+d+'px;left:'+(e.clientX-r.left-d/2)+'px;top:'+(e.clientY-r.top-d/2)+'px';this.appendChild(s);setTimeout(function(){s.remove()},600)}<\/script>`);
            add('Animation', 'Flickering Neon Sign', `<style>.nn{font:900 70px system-ui;color:#fff;text-shadow:0 0 7px #fff,0 0 20px #f0f,0 0 42px #f0f,0 0 82px #f0f;animation:f 3s infinite}@keyframes f{0%,18%,22%,25%,53%,57%,100%{opacity:1}20%,24%,55%{opacity:.3}}</style><div class="nn">NEON</div>`);
            add('Animation', 'Radar Scanner', `<style>.rd{position:relative;width:200px;height:200px;border-radius:50%;border:2px solid #22c55e;background:repeating-radial-gradient(#0000 0 24px,#22c55e33 25px 26px);overflow:hidden}.rd:before{content:'';position:absolute;inset:0;background:conic-gradient(#22c55e99,#0000 25%);animation:s 3s linear infinite}.rd i{position:absolute;width:8px;height:8px;border-radius:50%;background:#4ade80;animation:p 3s infinite}@keyframes s{to{transform:rotate(360deg)}}@keyframes p{50%{opacity:.1}}</style><div class="rd"><i style="left:60%;top:30%"></i><i style="left:30%;top:65%;animation-delay:-1s"></i></div>`);
            add('Animation', 'Shimmer Text', `<style>.sh{font:900 60px system-ui;background:linear-gradient(90deg,#666 30%,#fff 50%,#666 70%);background-size:200%;-webkit-background-clip:text;background-clip:text;color:transparent;animation:s 2.5s linear infinite}@keyframes s{to{background-position:-200% 0}}</style><div class="sh">Shimmer</div>`);

            /* ===== BACKGROUND ===== */
            add('Background', 'Mesh Gradient Blobs', `<style>.mesh{position:fixed;inset:0;background:#0b1020;overflow:hidden}.mesh i{position:absolute;width:60vmax;height:60vmax;border-radius:50%;filter:blur(90px);opacity:.7;animation:d 12s ease-in-out infinite alternate}.mesh i:nth-child(1){background:#ff3d81;left:-10%;top:-20%}.mesh i:nth-child(2){background:#3d7bff;right:-10%;bottom:-20%;animation-delay:-4s}.mesh i:nth-child(3){background:#26e0b0;left:30%;top:20%;animation-delay:-8s}@keyframes d{to{transform:translate(20vmax,10vmax) scale(1.3)}}</style><div class="mesh"><i></i><i></i><i></i></div>`);
            add('Background', 'Warp Starfield', `<canvas id="c" style="position:fixed;inset:0"></canvas><script>var c=document.getElementById('c'),x=c.getContext('2d'),S=[],W=c.width=innerWidth,H=c.height=innerHeight;for(var i=0;i<300;i++)S.push({x:Math.random()*2-1,y:Math.random()*2-1,z:Math.random()});(function L(){x.fillStyle='rgba(0,0,0,.35)';x.fillRect(0,0,W,H);S.forEach(function(s){s.z-=.006;if(s.z<=0)s.z=1;var k=.5/s.z,r=(1-s.z)*3;x.fillStyle='#fff';x.fillRect(W/2+s.x*W*k,H/2+s.y*H*k,r,r)});requestAnimationFrame(L)})()<\/script>`);
            add('Background', 'Matrix Rain', `<canvas id="c" style="position:fixed;inset:0"></canvas><script>var c=document.getElementById('c'),x=c.getContext('2d'),W=c.width=innerWidth,H=c.height=innerHeight,D=[];for(var i=0;i<W/16;i++)D[i]=Math.random()*H/16;setInterval(function(){x.fillStyle='rgba(0,0,0,.08)';x.fillRect(0,0,W,H);x.fillStyle='#22ff66';x.font='16px monospace';D.forEach(function(y,i){x.fillText(String.fromCharCode(12448+Math.random()*96),i*16,y*16);D[i]=y*16>H&&Math.random()>.97?0:y+1})},50)<\/script>`);
            add('Background', 'Retro Synthwave Grid', `<style>.rg{position:fixed;inset:0;background:linear-gradient(#1a0033,#ff2d95 62%,#ffb86b);overflow:hidden}.rg:before{content:'';position:absolute;left:50%;bottom:42%;width:220px;height:220px;margin-left:-110px;border-radius:50%;background:linear-gradient(#fff200,#ff2d95)}.rg:after{content:'';position:absolute;left:-50%;width:200%;bottom:0;height:45%;background-color:#12002b;background-image:linear-gradient(#0ff 1px,transparent 1px),linear-gradient(90deg,#0ff 1px,transparent 1px);background-size:60px 60px;transform:perspective(300px) rotateX(60deg);transform-origin:bottom;animation:g 1s linear infinite}@keyframes g{to{background-position:0 60px}}</style><div class="rg"></div>`);
            add('Background', 'Floating Bubbles', `<style>.bb{position:fixed;inset:0;background:linear-gradient(#0f2027,#2c5364);overflow:hidden}.bb i{position:absolute;bottom:-80px;border-radius:50%;background:radial-gradient(#ffffff55,#ffffff11);border:1px solid #fff4;animation:u linear infinite}@keyframes u{to{transform:translateY(-110vh) translateX(40px)}}</style><div class="bb"></div><script>var h='';for(var i=0;i<25;i++){var s=10+Math.random()*50;h+='<i style="left:'+Math.random()*100+'%;width:'+s+'px;height:'+s+'px;animation-duration:'+(6+Math.random()*10)+'s;animation-delay:-'+Math.random()*10+'s"></i>'}document.querySelector('.bb').innerHTML=h<\/script>`);
            add('Background', 'Northern Lights', `<style>.au{position:fixed;inset:0;background:#02060f;overflow:hidden}.au i{position:absolute;left:-20%;width:140%;height:40%;filter:blur(50px);opacity:.6;animation:a 8s ease-in-out infinite alternate}.au i:nth-child(1){top:5%;background:linear-gradient(90deg,#00ff9d,#00b8ff);transform:skewY(-8deg)}.au i:nth-child(2){top:25%;background:linear-gradient(90deg,#a855f7,#22d3ee);animation-delay:-3s;transform:skewY(6deg)}@keyframes a{to{transform:translateY(80px) skewY(10deg);opacity:.3}}</style><div class="au"><i></i><i></i></div>`);

            /* ===== GRAPHS ===== */
            add('Graph', 'Animated Bar Chart', `<style>.bc{display:flex;align-items:end;gap:12px;height:200px;padding:20px;border:1px solid #fff2;border-radius:16px;background:#ffffff08}.bc b{width:34px;height:var(--h);background:linear-gradient(#f59e0b,#ef4444);border-radius:8px 8px 0 0;transform-origin:bottom;animation:g 1s cubic-bezier(.2,1.4,.4,1) both;animation-delay:calc(var(--i)*.1s)}.bc b:hover{filter:brightness(1.4)}@keyframes g{from{transform:scaleY(0)}}</style><div class="bc"><b style="--i:0;--h:40%"></b><b style="--i:1;--h:65%"></b><b style="--i:2;--h:50%"></b><b style="--i:3;--h:90%"></b><b style="--i:4;--h:70%"></b><b style="--i:5;--h:100%"></b><b style="--i:6;--h:60%"></b></div>`);
            add('Graph', 'Line Area Chart', `<style>.ln{stroke-dasharray:1;stroke-dashoffset:1;animation:d 3s ease infinite alternate}@keyframes d{to{stroke-dashoffset:0}}</style><svg viewBox="0 0 300 160" width="380"><defs><linearGradient id="a" x1="0" y1="0" x2="0" y2="1"><stop offset="0" stop-color="#22d3ee" stop-opacity=".5"/><stop offset="1" stop-color="#22d3ee" stop-opacity="0"/></linearGradient></defs><path d="M0 120L50 90L100 105L150 50L200 70L250 20L300 35V160H0Z" fill="url(#a)"/><path class="ln" pathLength="1" d="M0 120L50 90L100 105L150 50L200 70L250 20L300 35" fill="none" stroke="#22d3ee" stroke-width="3"/></svg>`);
            add('Graph', 'Donut Chart', `<style>svg{transform:rotate(-90deg)}circle{animation:d 1.6s ease both}@keyframes d{from{stroke-dasharray:0 100}}</style><svg viewBox="0 0 120 120" width="210"><circle cx="60" cy="60" r="45" fill="none" stroke="#ffffff15" stroke-width="16"/><circle cx="60" cy="60" r="45" fill="none" stroke="#f472b6" stroke-width="16" pathLength="100" stroke-dasharray="45 100"/><circle cx="60" cy="60" r="45" fill="none" stroke="#22d3ee" stroke-width="16" pathLength="100" stroke-dasharray="30 100" stroke-dashoffset="-45"/><circle cx="60" cy="60" r="45" fill="none" stroke="#fbbf24" stroke-width="16" pathLength="100" stroke-dasharray="25 100" stroke-dashoffset="-75"/></svg>`);
            add('Graph', 'Radar Spider Chart', `<style>.dp{transform-origin:100px 100px;animation:z 2s ease infinite alternate}@keyframes z{from{transform:scale(.2)}}</style><svg viewBox="0 0 200 200" width="240"><g fill="none" stroke="#ffffff30"><polygon points="100,20 176,75 147,165 53,165 24,75"/><polygon points="100,20 176,75 147,165 53,165 24,75" transform="translate(33 33) scale(.67)"/><polygon points="100,20 176,75 147,165 53,165 24,75" transform="translate(66 66) scale(.34)"/></g><polygon class="dp" points="100,28 153,83 140,155 76,132 43,82" fill="#a78bfa66" stroke="#a78bfa" stroke-width="2"/></svg>`);
            add('Graph', 'Speedometer Gauge', `<style>.v{stroke-dasharray:72 100;animation:g 2s ease both}.nd{transform-origin:100px 100px;animation:n 2s ease both}@keyframes g{from{stroke-dasharray:0 100}}@keyframes n{from{transform:rotate(-90deg)}to{transform:rotate(39deg)}}</style><svg viewBox="0 0 200 120" width="280"><path d="M20 100A80 80 0 0 1 180 100" fill="none" stroke="#ffffff15" stroke-width="16" stroke-linecap="round" pathLength="100"/><path class="v" d="M20 100A80 80 0 0 1 180 100" fill="none" stroke="#4ade80" stroke-width="16" stroke-linecap="round" pathLength="100"/><line class="nd" x1="100" y1="100" x2="100" y2="35" stroke="#fff" stroke-width="3" stroke-linecap="round"/><circle cx="100" cy="100" r="7" fill="#fff"/><text x="100" y="118" text-anchor="middle" fill="#fff" font-family="system-ui" font-weight="800" font-size="14">72%</text></svg>`);
            add('Graph', 'Skill Progress Bars', `<style>.sk{width:300px;font:600 14px system-ui;color:#fff}.sk div{margin:14px 0}.sk i{display:block;height:10px;border-radius:9px;background:#ffffff15;margin-top:6px;overflow:hidden}.sk i:after{content:'';display:block;height:100%;width:var(--w);border-radius:9px;background:linear-gradient(90deg,#34d399,#22d3ee);animation:f 1.6s ease both}@keyframes f{from{width:0}}</style><div class="sk"><div>HTML<i style="--w:95%"></i></div><div>CSS<i style="--w:88%"></i></div><div>JavaScript<i style="--w:76%"></i></div><div>React<i style="--w:64%"></i></div></div>`);
            add('Graph', 'Activity Heatmap', `<style>.hm{display:grid;grid-template-columns:repeat(20,15px);gap:3px}.hm i{height:15px;border-radius:3px;animation:p .5s both}@keyframes p{from{transform:scale(0)}}</style><div class="hm"></div><script>var h='';for(var i=0;i<180;i++)h+='<i style="background:rgba(74,222,128,'+(.1+Math.random()*.9)+');animation-delay:'+Math.random()*1.5+'s"></i>';document.querySelector('.hm').innerHTML=h<\/script>`);

            /* ===== STATS ===== */
            add('Stats', 'Count-Up Numbers', `<style>.st{display:flex;gap:40px;text-align:center;font-family:system-ui;color:#fff}.st b{display:block;font:900 54px system-ui;background:linear-gradient(#fff,#a78bfa);-webkit-background-clip:text;background-clip:text;color:transparent}.st span{opacity:.6;font-size:13px;letter-spacing:2px;text-transform:uppercase}</style><div class="st"><div><b data-n="1280">0</b><span>Users</span></div><div><b data-n="86">0</b><span>Countries</span></div><div><b data-n="99">0</b><span>Uptime %</span></div></div><script>document.querySelectorAll('[data-n]').forEach(function(e){var n=+e.dataset.n,i=0,t=setInterval(function(){i+=n/50;e.textContent=Math.round(Math.min(i,n));if(i>=n)clearInterval(t)},30)})<\/script>`);
            add('Stats', 'KPI Trend Card', `<style>.kp{width:250px;padding:22px;border-radius:20px;background:linear-gradient(145deg,#1e1b4b,#0f172a);border:1px solid #6366f155;font-family:system-ui;color:#fff}.kp small{opacity:.6}.kp h2{font:800 40px system-ui;margin:6px 0}.kp span{color:#4ade80;font-weight:700}.kp div{display:flex;gap:4px;align-items:end;height:44px;margin-top:14px}.kp i{flex:1;background:#6366f1;border-radius:3px;animation:u 1s both}@keyframes u{from{height:0!important}}</style><div class="kp"><small>Monthly revenue</small><h2>$48,290</h2><span>▲ 12.4%</span><div><i style="height:30%"></i><i style="height:50%"></i><i style="height:40%"></i><i style="height:70%"></i><i style="height:55%"></i><i style="height:90%"></i><i style="height:100%"></i></div></div>`);
            add('Stats', 'Activity Rings', `<style>.f{stroke-linecap:round;stroke-dasharray:0 100;animation:a 2s ease forwards}@keyframes a{to{stroke-dasharray:var(--v) 100}}</style><svg viewBox="0 0 120 120" width="210" style="transform:rotate(-90deg)" fill="none" stroke-width="9"><g stroke="#ffffff14"><circle cx="60" cy="60" r="52"/><circle cx="60" cy="60" r="40"/><circle cx="60" cy="60" r="28"/></g><circle class="f" style="--v:85" pathLength="100" cx="60" cy="60" r="52" stroke="#fb7185"/><circle class="f" style="--v:65;animation-delay:.3s" pathLength="100" cx="60" cy="60" r="40" stroke="#a3e635"/><circle class="f" style="--v:45;animation-delay:.6s" pathLength="100" cx="60" cy="60" r="28" stroke="#22d3ee"/></svg>`);
            add('Stats', 'Live Pulse Metric', `<style>.lv{font-family:system-ui;color:#fff;text-align:center}.lv i{display:inline-block;width:12px;height:12px;border-radius:50%;background:#22c55e;margin-right:8px;animation:p 1.2s infinite}.lv b{display:block;font:900 72px ui-monospace,monospace;color:#4ade80;text-shadow:0 0 30px #22c55e}@keyframes p{0%{box-shadow:0 0 0 0 #22c55e}100%{box-shadow:0 0 0 16px #0000}}</style><div class="lv"><span><i></i>Visitors online</span><b id="n">1,204</b></div><script>setInterval(function(){document.getElementById('n').textContent=(1000+Math.floor(Math.random()*500)).toLocaleString()},900)<\/script>`);

            /* ===== PAGE LAYOUTS ===== */
            add('Page', 'SaaS Landing Page', `<style>body{margin:0;background:#0b0b14;color:#fff;font-family:system-ui}nav{display:flex;justify-content:space-between;padding:22px 6vw;align-items:center}nav b{font-size:22px;background:linear-gradient(90deg,#a78bfa,#22d3ee);-webkit-background-clip:text;background-clip:text;color:transparent}nav a{margin-left:24px;opacity:.7;font-size:14px}.hero{text-align:center;padding:9vh 6vw 6vh}.hero h1{font-size:clamp(34px,6vw,72px);margin:0;line-height:1.05}.hero p{opacity:.65;margin:18px auto 28px;max-width:520px}.hero button{padding:14px 34px;border:0;border-radius:40px;background:linear-gradient(90deg,#7c3aed,#22d3ee);color:#fff;font-weight:700}.fs{display:grid;grid-template-columns:repeat(3,1fr);gap:18px;padding:0 6vw}.fs div{padding:26px;border-radius:20px;background:#ffffff0a;border:1px solid #fff2;transition:.3s}.fs div:hover{transform:translateY(-8px);border-color:#a78bfa}</style><nav><b>Novaly</b><span><a>Product</a><a>Pricing</a><a>Login</a></span></nav><section class="hero"><h1>Ship ideas at the speed of light</h1><p>One platform for teams who build fast.</p><button>Start free</button></section><section class="fs"><div><h3>Fast</h3><p>Deploy in seconds.</p></div><div><h3>Secure</h3><p>Bank-grade safety.</p></div><div><h3>Scalable</h3><p>Grows with you.</p></div></section>`);
            add('Page', 'Admin Dashboard', `<style>body{margin:0;background:#0d1117;color:#e6edf3;font-family:system-ui;display:grid;grid-template-columns:200px 1fr;min-height:100vh}aside{background:#161b22;padding:24px;border-right:1px solid #30363d}aside p{padding:10px 12px;border-radius:8px;opacity:.7;margin:4px 0}aside p:first-of-type{background:#238636;opacity:1}main{padding:24px;display:grid;gap:16px;align-content:start}.k{display:grid;grid-template-columns:repeat(4,1fr);gap:14px}.k div{padding:16px;border-radius:12px;background:#161b22;border:1px solid #30363d}.k h3{margin:4px 0 0;font-size:26px}.ch{height:220px;padding:16px;border-radius:12px;background:#161b22;border:1px solid #30363d;display:flex;align-items:end;gap:8px}.ch i{flex:1;background:linear-gradient(#58a6ff,#1f6feb);border-radius:4px 4px 0 0;animation:g 1s both}@keyframes g{from{height:0!important}}</style><aside><b>Admin</b><p>Overview</p><p>Users</p><p>Reports</p><p>Settings</p></aside><main><div class="k"><div>Users<h3>8.2k</h3></div><div>Sales<h3>$24k</h3></div><div>Orders<h3>1,204</h3></div><div>Churn<h3>2.1%</h3></div></div><div class="ch"><i style="height:40%"></i><i style="height:60%"></i><i style="height:45%"></i><i style="height:80%"></i><i style="height:65%"></i><i style="height:95%"></i><i style="height:70%"></i><i style="height:85%"></i><i style="height:55%"></i></div></main>`);
            add('Page', 'Editorial Magazine', `<style>body{margin:0;background:#f5efe6;color:#1a1a1a;font-family:Georgia,serif;display:grid;grid-template-columns:1fr 1fr;min-height:100vh}.l{padding:8vw 6vw;display:flex;flex-direction:column;justify-content:center}.l small{letter-spacing:4px;text-transform:uppercase;color:#b45309}.l h1{font-size:clamp(40px,6vw,84px);line-height:.95;margin:14px 0}.l p{columns:2;gap:24px;line-height:1.6}.l p:first-letter{font-size:56px;float:left;line-height:.8;padding-right:8px;color:#b45309}.r{background:linear-gradient(160deg,#b45309,#7c2d12 60%,#1c1917);position:relative;overflow:hidden}.r:before{content:'';position:absolute;width:60%;aspect-ratio:1;border-radius:50%;left:20%;top:20%;background:radial-gradient(#fde68a,#f59e0b);animation:s 6s ease-in-out infinite alternate}@keyframes s{to{transform:translateY(40px) scale(1.15)}}</style><div class="l"><small>Issue 07</small><h1>The Art of Slow Design</h1><p>Good design takes time. We explore the quiet craft behind objects made to last, and why patience is the rarest material in a fast world of endless scrolling.</p></div><div class="r"></div>`);
            add('Page', '3D Tilt Login', `<style>body{margin:0;min-height:100vh;display:grid;place-items:center;background:radial-gradient(circle at 30% 20%,#312e81,#020617);font-family:system-ui;color:#fff;perspective:900px}.lg{width:300px;padding:34px;border-radius:24px;background:#ffffff14;backdrop-filter:blur(20px);border:1px solid #fff3;transition:transform .1s;transform-style:preserve-3d}.lg h2{margin:0 0 18px;transform:translateZ(40px)}.lg input{width:100%;padding:12px;margin:8px 0;border-radius:10px;border:1px solid #fff3;background:#0004;color:#fff;transform:translateZ(20px)}.lg button{width:100%;padding:12px;margin-top:10px;border:0;border-radius:10px;background:linear-gradient(90deg,#6366f1,#ec4899);color:#fff;font-weight:700;transform:translateZ(50px)}</style><form class="lg" onsubmit="return false"><h2>Welcome back</h2><input placeholder="Email"><input type="password" placeholder="Password"><button>Sign in</button></form><script>var f=document.querySelector('.lg');document.onmousemove=function(e){f.style.transform='rotateY('+(e.clientX/innerWidth-.5)*30+'deg) rotateX('+(.5-e.clientY/innerHeight)*30+'deg)'}<\/script>`);
            add('Page', 'Coming Soon Countdown', `<style>body{margin:0;min-height:100vh;display:grid;place-items:center;text-align:center;background:#000;color:#fff;font-family:system-ui;overflow:hidden}body:before{content:'';position:fixed;inset:-50%;background:conic-gradient(#f43f5e,#8b5cf6,#06b6d4,#f43f5e);filter:blur(120px);opacity:.35;animation:r 14s linear infinite}@keyframes r{to{transform:rotate(360deg)}}main{position:relative}h1{font-size:clamp(36px,7vw,90px);margin:0;letter-spacing:-2px}.t{display:flex;gap:16px;justify-content:center;margin-top:30px}.t div{width:90px;padding:18px 0;border-radius:16px;background:#ffffff14;border:1px solid #fff3}.t b{display:block;font-size:34px}.t small{opacity:.6}</style><main><h1>Launching Soon</h1><div class="t"><div><b id="d">0</b><small>days</small></div><div><b id="h">0</b><small>hrs</small></div><div><b id="m">0</b><small>min</small></div><div><b id="s">0</b><small>sec</small></div></div></main><script>var T=Date.now()+864e5*9;setInterval(function(){var t=Math.max(0,T-Date.now());d.textContent=Math.floor(t/864e5);h.textContent=Math.floor(t/36e5)%24;m.textContent=Math.floor(t/6e4)%60;s.textContent=Math.floor(t/1e3)%60},250)<\/script>`);
            add('Page', 'Masonry Portfolio', `<style>body{margin:0;background:#0a0a0a;padding:5vw;font-family:system-ui;color:#fff}h1{margin:0 0 20px}.ms{columns:4 180px;gap:14px}.ms div{margin-bottom:14px;border-radius:16px;display:flex;align-items:end;padding:14px;font-weight:700;transition:.4s}.ms div:hover{transform:scale(1.04) rotate(-1deg);filter:saturate(1.6)}</style><h1>Selected Work</h1><div class="ms"></div><script>var h='';for(var i=0;i<12;i++)h+='<div style="height:'+(120+(i*47%140))+'px;background:linear-gradient(135deg,hsl('+i*30+',80%,55%),hsl('+(i*30+50)+',80%,40%))">Project '+(i+1)+'</div>';document.querySelector('.ms').innerHTML=h<\/script>`);

            /* ===== BATCH 2: REAL 3D + UI ===== */
            add('3D', 'Glossy Rotating Cube', `<style>.sc{perspective:900px}.cu{position:relative;width:140px;height:140px;transform-style:preserve-3d;animation:r 12s linear infinite}.cu i{position:absolute;inset:0;border-radius:14px;border:1px solid #fff5;box-shadow:inset 0 0 30px #fff3}.cu i:nth-child(1){transform:translateZ(70px);background:linear-gradient(135deg,#a78bfa,#6d28d9)}.cu i:nth-child(2){transform:rotateY(90deg) translateZ(70px);background:linear-gradient(135deg,#7c3aed,#4c1d95)}.cu i:nth-child(3){transform:rotateY(180deg) translateZ(70px);background:linear-gradient(135deg,#6d28d9,#2e1065)}.cu i:nth-child(4){transform:rotateY(-90deg) translateZ(70px);background:linear-gradient(135deg,#8b5cf6,#5b21b6)}.cu i:nth-child(5){transform:rotateX(90deg) translateZ(70px);background:linear-gradient(135deg,#ddd6fe,#a78bfa)}.cu i:nth-child(6){transform:rotateX(-90deg) translateZ(70px);background:#1e1b4b}@keyframes r{from{transform:rotateX(-22deg) rotateY(0)}to{transform:rotateX(-22deg) rotateY(360deg)}}</style><div class="sc"><div class="cu"><i></i><i></i><i></i><i></i><i></i><i></i></div></div>`);
            add('3D', 'Wireframe Globe', `<canvas id="c" width="320" height="320" style="filter:drop-shadow(0 0 12px #38bdf8)"></canvas><script>var c=document.getElementById('c'),x=c.getContext('2d'),P=[],a=0;for(var i=0;i<420;i++){var t=Math.acos(1-2*(i+.5)/420),p=Math.PI*(1+Math.sqrt(5))*i;P.push([Math.sin(t)*Math.cos(p),Math.cos(t),Math.sin(t)*Math.sin(p)])}(function L(){x.clearRect(0,0,320,320);a+=.008;var s=Math.sin(a),co=Math.cos(a);P.forEach(function(q){var X=q[0]*co-q[2]*s,Z=q[0]*s+q[2]*co;x.fillStyle='rgba(56,189,248,'+(.15+.85*(Z+1)/2)+')';x.beginPath();x.arc(160+X*130,160+q[1]*130,1+1.6*(Z+1),0,7);x.fill()});requestAnimationFrame(L)})()<\/script>`);
            add('3D', 'Holographic Credit Card', `<style>.cd{width:340px;height:210px;border-radius:20px;padding:24px;color:#fff;font-family:ui-monospace,monospace;position:relative;overflow:hidden;background:linear-gradient(135deg,#1e3a8a,#7c3aed 60%,#db2777);box-shadow:0 30px 60px #000a;transition:transform .1s}.cd:before{content:'';position:absolute;inset:0;background:radial-gradient(circle at var(--x,50%) var(--y,0%),#ffffff66,#0000 55%),linear-gradient(115deg,#0000 30%,#ffffff22 45%,#0000 60%);mix-blend-mode:overlay}.cd b{display:block;width:46px;height:34px;border-radius:6px;background:linear-gradient(135deg,#fde68a,#b45309);margin-bottom:34px}.cd p{font-size:22px;letter-spacing:3px}.cd small{position:absolute;bottom:22px;left:24px;opacity:.85}</style><div class="cd"><b></b><p>4539 8821 0043 7712</p><small>ALEX MORGAN &nbsp; 09/29</small></div><script>var d=document.querySelector('.cd');document.onmousemove=function(e){var r=d.getBoundingClientRect(),x=(e.clientX-r.left)/r.width,y=(e.clientY-r.top)/r.height;d.style.transform='perspective(800px) rotateY('+(x-.5)*30+'deg) rotateX('+(.5-y)*30+'deg)';d.style.setProperty('--x',x*100+'%');d.style.setProperty('--y',y*100+'%')}<\/script>`);
            add('3D', 'Vinyl Music Player', `<style>.vp{width:300px;padding:22px;border-radius:24px;background:linear-gradient(145deg,#2a2a35,#14141b);box-shadow:0 30px 50px #000a,inset 0 1px #fff2;color:#fff;font-family:system-ui;text-align:center}.vn{position:relative;width:200px;height:200px;margin:0 auto 16px;border-radius:50%;background:repeating-radial-gradient(#111 0 2px,#1d1d24 3px 4px);box-shadow:0 10px 30px #000;animation:s 4s linear infinite}.vn:before{content:'';position:absolute;inset:0;border-radius:50%;background:conic-gradient(#fff0,#ffffff25 10%,#fff0 25%,#fff0 50%,#ffffff25 60%,#fff0 75%)}.vn:after{content:'';position:absolute;inset:70px;border-radius:50%;background:linear-gradient(135deg,#f472b6,#8b5cf6);border:6px solid #0006;box-shadow:0 0 0 2px #000}@keyframes s{to{transform:rotate(360deg)}}.vp small{opacity:.5}.vb{height:4px;border-radius:4px;background:#fff2;margin:14px 0}.vb i{display:block;width:40%;height:100%;border-radius:4px;background:#f472b6;animation:p 8s linear infinite}@keyframes p{to{width:100%}}</style><div class="vp"><div class="vn"></div><b>Midnight Drive</b><br><small>Neon Waves</small><div class="vb"><i></i></div>⏮ &nbsp; ⏸ &nbsp; ⏭</div>`);
            add('3D', 'Open-on-Hover Book', `<style>.bo{width:180px;height:250px;perspective:1200px}.bi{position:relative;width:100%;height:100%;transform-style:preserve-3d;transform:rotateY(-20deg);transition:1s}.bo:hover .bi{transform:rotateY(-8deg) translateX(70px)}.pg{position:absolute;inset:0;border-radius:2px 8px 8px 2px;background:repeating-linear-gradient(#f5f0e6 0 22px,#d6cdb8 23px);box-shadow:0 20px 40px #000a}.cv{position:absolute;inset:0;transform-origin:left;transform-style:preserve-3d;transition:1s}.bo:hover .cv{transform:rotateY(-160deg)}.cv b,.cv i{position:absolute;inset:0;border-radius:2px 8px 8px 2px;backface-visibility:hidden;-webkit-backface-visibility:hidden}.cv b{background:linear-gradient(135deg,#1e3a8a,#3b82f6);display:grid;place-items:center;color:#fff;font:800 24px Georgia,serif;text-align:center;box-shadow:inset 8px 0 12px #0006}.cv i{background:#e9e2d0;transform:rotateY(180deg)}</style><div class="bo"><div class="bi"><div class="pg"></div><div class="cv"><b>The Art<br>of Motion</b><i></i></div></div></div>`);
            add('Graph', '3D Extruded Bar Chart', `<style>.sc{perspective:900px}.b3{display:flex;align-items:flex-end;gap:36px;height:200px;transform-style:preserve-3d;transform:rotateX(-22deg) rotateY(-32deg)}.b3 div{position:relative;width:34px;height:var(--h);transform-style:preserve-3d;transform-origin:bottom;animation:g 1.4s cubic-bezier(.2,1.3,.4,1) both;animation-delay:calc(var(--i)*.15s)}.b3 i{position:absolute;background:var(--c)}.b3 i:nth-child(1){inset:0;transform:translateZ(17px)}.b3 i:nth-child(2){left:0;top:0;width:34px;height:100%;transform:rotateY(90deg) translateZ(17px);filter:brightness(.6)}.b3 i:nth-child(3){left:0;top:0;width:34px;height:34px;transform:rotateX(90deg) translateZ(17px);filter:brightness(1.4)}@keyframes g{from{transform:scaleY(0)}}</style><div class="sc"><div class="b3"><div style="--i:0;--h:80px;--c:#f43f5e"><i></i><i></i><i></i></div><div style="--i:1;--h:130px;--c:#f59e0b"><i></i><i></i><i></i></div><div style="--i:2;--h:100px;--c:#22c55e"><i></i><i></i><i></i></div><div style="--i:3;--h:170px;--c:#06b6d4"><i></i><i></i><i></i></div><div style="--i:4;--h:120px;--c:#8b5cf6"><i></i><i></i><i></i></div></div></div>`);
            add('Background', 'Neon Warp Tunnel', `<style>.tn{position:fixed;inset:0;perspective:400px;overflow:hidden;background:#000}.tn i{position:absolute;left:50%;top:50%;width:70vmin;height:70vmin;margin:-35vmin;border:3px solid;border-radius:6%;animation:z 5s linear infinite;animation-delay:calc(var(--i)*-.4s);box-shadow:0 0 20px currentColor,inset 0 0 20px currentColor}@keyframes z{from{transform:translateZ(-1600px) rotate(0);opacity:0}20%{opacity:1}to{transform:translateZ(300px) rotate(90deg);opacity:0}}</style><div class="tn"></div><script>var h='';for(var i=0;i<13;i++)h+='<i style="--i:'+i+';color:hsl('+i*28+',100%,60%)"></i>';document.querySelector('.tn').innerHTML=h<\/script>`);
            add('UI', 'Skeuomorphic Push Button', `<style>.pb{width:150px;height:150px;border-radius:50%;border:0;cursor:pointer;background:radial-gradient(circle at 35% 25%,#ff8a8a,#e11d48 45%,#7f1d1d);box-shadow:0 12px 0 #5b0f1f,0 22px 30px #000a,inset 0 4px 10px #fff6,inset 0 -8px 16px #0006;color:#fff;font:800 22px system-ui;text-shadow:0 2px 4px #0008;transition:.12s}.pb:active{transform:translateY(10px);box-shadow:0 2px 0 #5b0f1f,0 6px 10px #000a,inset 0 4px 10px #fff6,inset 0 -8px 16px #0006}</style><button class="pb">PUSH</button>`);
            add('UI', 'Neumorphic Toggles', `<style>.nm{background:#1c1f26;padding:40px;border-radius:24px;display:flex;gap:28px}.sw{width:90px;height:46px;border-radius:30px;background:#1c1f26;box-shadow:inset 6px 6px 12px #12141a,inset -6px -6px 12px #262a33;position:relative;cursor:pointer}.sw:after{content:'';position:absolute;top:5px;left:6px;width:36px;height:36px;border-radius:50%;background:linear-gradient(145deg,#2a2e38,#181b21);box-shadow:4px 4px 8px #101216,-2px -2px 6px #2c313c;transition:.35s}.sw.on:after{left:48px;background:linear-gradient(145deg,#34d399,#059669);box-shadow:0 0 18px #34d399}</style><div class="nm"><div class="sw on" onclick="this.classList.toggle('on')"></div><div class="sw" onclick="this.classList.toggle('on')"></div></div>`);
            add('UI', 'Spinning Gradient Border Card', `<style>.cb2{position:relative;width:260px;height:180px;border-radius:20px;overflow:hidden;padding:2px}.cb2:before{content:'';position:absolute;inset:-50%;background:conic-gradient(#0000 60%,#22d3ee,#a855f7,#0000);animation:s 3s linear infinite}.cb2 div{position:relative;height:100%;border-radius:18px;background:#0b0b14;color:#fff;font-family:system-ui;padding:24px}.cb2 p{opacity:.6;margin-top:8px}@keyframes s{to{transform:rotate(360deg)}}</style><div class="cb2"><div><h3>Pro Plan</h3><p>Unlimited projects and priority support.</p></div></div>`);
            add('UI', 'Magnifying Dock', `<style>.dk{display:flex;align-items:end;gap:10px;padding:12px 16px;border-radius:24px;background:#ffffff1f;backdrop-filter:blur(20px);border:1px solid #fff3;box-shadow:0 20px 40px #0008}.dk i{width:56px;height:56px;border-radius:14px;transition:transform .15s;transform-origin:bottom;box-shadow:inset 0 2px 4px #fff6,0 6px 10px #0006}</style><div class="dk"></div><script>var d=document.querySelector('.dk'),g=['#f43f5e','#f59e0b','#22c55e','#06b6d4','#6366f1','#d946ef'],h='';g.forEach(function(c){h+='<i style="background:linear-gradient(160deg,'+c+',#0008 140%)"></i>'});d.innerHTML=h;var I=d.children;d.onmousemove=function(e){[].forEach.call(I,function(i){var r=i.getBoundingClientRect(),k=Math.max(0,1-Math.abs(e.clientX-r.left-r.width/2)/110);i.style.transform='scale('+(1+k*.8)+') translateY('+-k*10+'px)'})};d.onmouseleave=function(){[].forEach.call(I,function(i){i.style.transform=''})}<\/script>`);
            add('UI', 'Rotary Volume Knob', `<style>.kn{position:relative;width:170px;height:170px;border-radius:50%;background:conic-gradient(#2b2b33,#4a4a55,#2b2b33,#4a4a55,#2b2b33);box-shadow:0 20px 30px #000a,inset 0 2px 4px #fff5,0 0 0 10px #16161c;cursor:grab;transform:rotate(-40deg)}.kn:after{content:'';position:absolute;left:50%;top:12px;width:6px;height:28px;margin-left:-3px;border-radius:4px;background:#22d3ee;box-shadow:0 0 12px #22d3ee}.kt{text-align:center;font:800 28px system-ui;color:#22d3ee;margin-top:26px}</style><div class="kn" id="k"></div><div class="kt" id="v">30</div><script>var k=document.getElementById('k'),dn=0;k.onpointerdown=function(){dn=1};onpointerup=function(){dn=0};onpointermove=function(e){if(!dn)return;var r=k.getBoundingClientRect(),a=Math.atan2(e.clientY-r.top-r.height/2,e.clientX-r.left-r.width/2)*180/Math.PI+90;if(a>180)a-=360;a=Math.max(-140,Math.min(140,a));k.style.transform='rotate('+a+'deg)';document.getElementById('v').textContent=Math.round((a+140)/2.8)}<\/script>`);
            add('Stats', 'Split-Flap Digital Clock', `<style>.fk{display:flex;gap:10px}.dg{position:relative;width:70px;height:100px;border-radius:10px;background:linear-gradient(#2a2a30 50%,#1c1c21 50%);color:#f5f5f5;font:800 64px/100px system-ui;text-align:center;box-shadow:0 10px 20px #000a}.dg:after{content:'';position:absolute;left:0;right:0;top:50%;height:2px;background:#000}.dg span{display:block;animation:fl .5s}.fk em{font:800 50px/100px system-ui;color:#888;font-style:normal}@keyframes fl{from{transform:perspective(300px) rotateX(-90deg);opacity:.2}}</style><div class="fk"><div class="dg"></div><div class="dg"></div><em>:</em><div class="dg"></div><div class="dg"></div><em>:</em><div class="dg"></div><div class="dg"></div></div><script>var D=document.querySelectorAll('.dg');function t(){var n=new Date(),s=('0'+n.getHours()).slice(-2)+('0'+n.getMinutes()).slice(-2)+('0'+n.getSeconds()).slice(-2);for(var i=0;i<6;i++)if(s[i]!=D[i].dataset.v){D[i].dataset.v=s[i];D[i].innerHTML='<span>'+s[i]+'</span>'}}t();setInterval(t,250)<\/script>`);
            add('Page', 'Parallax Depth Hero', `<style>body{margin:0;height:100vh;overflow:hidden;background:linear-gradient(#0f0c29,#302b63 60%,#f97316);font-family:system-ui;color:#fff;display:grid;place-items:center}.ly{position:absolute;inset:-5%;transition:transform .15s}.ly svg{position:absolute;bottom:0;width:100%}.tx{position:relative;z-index:5;text-align:center;transition:transform .15s}.tx h1{font-size:clamp(40px,8vw,110px);margin:0;letter-spacing:-3px;text-shadow:0 10px 40px #0008}.tx p{opacity:.8}</style><div class="ly" data-d="10"><svg viewBox="0 0 100 40" preserveAspectRatio="none" height="60%"><path d="M0 40V22L15 12L30 24L48 8L65 26L82 14L100 26V40Z" fill="#3b2f7a"/></svg></div><div class="ly" data-d="25"><svg viewBox="0 0 100 40" preserveAspectRatio="none" height="45%"><path d="M0 40V26L20 16L38 28L58 14L78 30L100 20V40Z" fill="#231a52"/></svg></div><div class="ly" data-d="45"><svg viewBox="0 0 100 40" preserveAspectRatio="none" height="30%"><path d="M0 40V30L25 20L50 32L75 18L100 30V40Z" fill="#0c0824"/></svg></div><div class="tx" data-d="-20"><h1>BEYOND</h1><p>Move your mouse to feel the depth</p></div><script>var L=document.querySelectorAll('[data-d]');document.onmousemove=function(e){var x=e.clientX/innerWidth-.5,y=e.clientY/innerHeight-.5;L.forEach(function(l){var d=+l.dataset.d;l.style.transform='translate('+-x*d+'px,'+-y*d/2+'px)'})}<\/script>`);

            /* ===== BATCH 3: BACKGROUNDS ===== */
            const CV = '<canvas id="c" style="position:fixed;inset:0"></canvas><script>var c=document.getElementById("c"),x=c.getContext("2d"),W=c.width=innerWidth,H=c.height=innerHeight;';
            add('Background', 'Plasma Energy', `<canvas id="c" style="position:fixed;inset:0;filter:blur(5px) saturate(1.4)"></canvas><script>var c=document.getElementById('c'),x=c.getContext('2d'),W=c.width=innerWidth,H=c.height=innerHeight,t=0;(function L(){t+=.03;for(var i=0;i<W;i+=12)for(var j=0;j<H;j+=12){var v=Math.sin(i/90+t)+Math.sin(j/70+t*1.3)+Math.sin((i+j)/120+t*.7);x.fillStyle='hsl('+(v*60+260)+',90%,'+(45+v*10)+'%)';x.fillRect(i,j,12,12)}requestAnimationFrame(L)})()<\/script>`);
            add('Background', 'Rising Embers Fire', `<canvas id="c" style="position:fixed;inset:0"></canvas><script>var c=document.getElementById('c'),x=c.getContext('2d'),W=c.width=innerWidth,H=c.height=innerHeight,P=[];(function L(){x.globalCompositeOperation='source-over';x.fillStyle='rgba(12,2,0,.22)';x.fillRect(0,0,W,H);x.globalCompositeOperation='lighter';for(var i=0;i<7;i++)P.push({x:W/2+(Math.random()-.5)*W*.7,y:H,vx:Math.random()-.5,vy:-1-Math.random()*3,l:1});P=P.filter(function(p){p.x+=p.vx+Math.sin(p.y/30);p.y+=p.vy;p.l-=.008;x.fillStyle='hsla('+p.l*55+',100%,'+(25+p.l*35)+'%,'+p.l+')';x.beginPath();x.arc(p.x,p.y,p.l*11,0,7);x.fill();return p.l>0});requestAnimationFrame(L)})()<\/script>`);
            add('Background', 'Thunder Storm', `<canvas id="c" style="position:fixed;inset:0"></canvas><script>var c=document.getElementById('c'),x=c.getContext('2d'),W=c.width=innerWidth,H=c.height=innerHeight;function B(a,b){x.beginPath();x.moveTo(a,b);while(b<H){a+=(Math.random()-.5)*70;b+=15+Math.random()*30;x.lineTo(a,b)}x.stroke()}setInterval(function(){x.fillStyle='rgba(4,6,24,.3)';x.fillRect(0,0,W,H);if(Math.random()<.07){x.fillStyle='rgba(180,210,255,.12)';x.fillRect(0,0,W,H);x.strokeStyle='#dff';x.lineWidth=2;x.shadowColor='#7cf';x.shadowBlur=30;B(Math.random()*W,0);x.shadowBlur=0}},40)<\/script>`);
            add('Background', 'Spiral Galaxy', `<canvas id="c" style="position:fixed;inset:0"></canvas><script>var c=document.getElementById('c'),x=c.getContext('2d'),W=c.width=innerWidth,H=c.height=innerHeight,S=[],t=0;for(var i=0;i<1800;i++){var r=Math.random()*Math.random()*Math.min(W,H)*.5;S.push([r,i%3*2.094+r*.012+Math.random()*.5,Math.random()*2+.5,Math.random()*80+190])}(function L(){x.fillStyle='rgba(0,0,12,.28)';x.fillRect(0,0,W,H);t+=.004;S.forEach(function(s){var a=s[1]+t*(1.3-s[0]/400);x.fillStyle='hsl('+s[3]+',90%,72%)';x.fillRect(W/2+Math.cos(a)*s[0],H/2+Math.sin(a)*s[0]*.45,s[2],s[2])});requestAnimationFrame(L)})()<\/script>`);
            add('Background', 'Flow Field Ink', `<canvas id="c" style="position:fixed;inset:0"></canvas><script>var c=document.getElementById('c'),x=c.getContext('2d'),W=c.width=innerWidth,H=c.height=innerHeight,P=[],t=0;for(var i=0;i<900;i++)P.push([Math.random()*W,Math.random()*H]);x.fillStyle='#050510';x.fillRect(0,0,W,H);(function L(){t+=.002;x.fillStyle='rgba(5,5,16,.04)';x.fillRect(0,0,W,H);P.forEach(function(p){var a=Math.sin(p[0]/150+t*5)*Math.cos(p[1]/130-t*3)*6.28;p[0]+=Math.cos(a)*1.4;p[1]+=Math.sin(a)*1.4;if(p[0]<0||p[0]>W||p[1]<0||p[1]>H){p[0]=Math.random()*W;p[1]=Math.random()*H}x.fillStyle='hsl('+(a*30+200)+',90%,65%)';x.fillRect(p[0],p[1],1.6,1.6)});requestAnimationFrame(L)})()<\/script>`);
            add('Background', 'Water Ripples', `<canvas id="c" style="position:fixed;inset:0"></canvas><script>var c=document.getElementById('c'),x=c.getContext('2d'),W=c.width=innerWidth,H=c.height=innerHeight,R=[];setInterval(function(){R.push([Math.random()*W,Math.random()*H,0])},450);(function L(){x.fillStyle='#03121f';x.fillRect(0,0,W,H);R=R.filter(function(r){r[2]+=1.6;for(var k=0;k<3;k++){x.strokeStyle='rgba(56,189,248,'+Math.max(0,1-r[2]/260)*(1-k*.3)+')';x.beginPath();x.arc(r[0],r[1],Math.max(0,r[2]-k*14),0,7);x.stroke()}return r[2]<260});requestAnimationFrame(L)})()<\/script>`);
            add('Background', 'Mouse Repel Dot Grid', `<canvas id="c" style="position:fixed;inset:0"></canvas><script>var c=document.getElementById('c'),x=c.getContext('2d'),W=c.width=innerWidth,H=c.height=innerHeight,D=[],m={x:-999,y:-999};for(var i=15;i<W;i+=30)for(var j=15;j<H;j+=30)D.push([i,j,i,j]);onmousemove=function(e){m.x=e.clientX;m.y=e.clientY};(function L(){x.clearRect(0,0,W,H);D.forEach(function(d){var dx=d[2]-m.x,dy=d[3]-m.y,r=Math.hypot(dx,dy)||1,f=Math.max(0,1-r/130);d[0]+=(d[2]+dx/r*f*55-d[0])*.12;d[1]+=(d[3]+dy/r*f*55-d[1])*.12;x.fillStyle='hsl('+(200+f*150)+',90%,'+(40+f*40)+'%)';x.beginPath();x.arc(d[0],d[1],2+f*3,0,7);x.fill()});requestAnimationFrame(L)})()<\/script>`);
            add('Background', 'Layered Sine Waves', `<canvas id="c" style="position:fixed;inset:0"></canvas><script>var c=document.getElementById('c'),x=c.getContext('2d'),W=c.width=innerWidth,H=c.height=innerHeight,t=0;(function L(){t+=.012;x.globalCompositeOperation='source-over';x.fillStyle='#020617';x.fillRect(0,0,W,H);x.globalCompositeOperation='lighter';for(var k=0;k<4;k++){x.beginPath();x.moveTo(0,H);for(var i=0;i<=W;i+=10)x.lineTo(i,H*.5+Math.sin(i/200+t+k)*80+Math.sin(i/90-t*1.5+k*2)*40);x.lineTo(W,H);var g=x.createLinearGradient(0,H*.3,0,H);g.addColorStop(0,'hsla('+(150+k*50)+',90%,55%,.6)');g.addColorStop(1,'rgba(0,0,0,0)');x.fillStyle=g;x.fill()}requestAnimationFrame(L)})()<\/script>`);
            add('Background', 'Wireframe Terrain Flight', `<canvas id="c" style="position:fixed;inset:0"></canvas><script>var c=document.getElementById('c'),x=c.getContext('2d'),W=c.width=innerWidth,H=c.height=innerHeight,t=0;(function L(){t+=.04;x.fillStyle='#0a001f';x.fillRect(0,0,W,H);x.strokeStyle='#ff2bd6';x.shadowColor='#ff2bd6';x.shadowBlur=8;var f=Math.floor(t),s=t-f;for(var z=30;z>=0;z--){var zz=z-s,k=1/(1+zz*.22),wz=z+f;x.beginPath();for(var i=-24;i<=24;i++){var h=(Math.sin(i*.5+wz*.7)+Math.sin(i*.23-wz*.4))*45*Math.min(1,Math.abs(i)/6),X=W/2+i*60*k,Y=H*.32+H*.65*k-h*k;i==-24?x.moveTo(X,Y):x.lineTo(X,Y)}x.globalAlpha=Math.min(1,k*1.6);x.stroke()}x.globalAlpha=1;requestAnimationFrame(L)})()<\/script>`);
            add('Background', 'Pulsing Dot Wave', `<canvas id="c" style="position:fixed;inset:0"></canvas><script>var c=document.getElementById('c'),x=c.getContext('2d'),W=c.width=innerWidth,H=c.height=innerHeight,t=0;(function L(){t+=.04;x.fillStyle='#04070f';x.fillRect(0,0,W,H);for(var i=12;i<W;i+=24)for(var j=12;j<H;j+=24){var v=Math.sin(i/70+t)+Math.cos(j/60-t*1.2);x.fillStyle='hsl('+(200+v*40)+',90%,'+(45+v*15)+'%)';x.beginPath();x.arc(i,j,3.4+v*1.4,0,7);x.fill()}requestAnimationFrame(L)})()<\/script>`);
            add('Background', 'Snowfall Night', `<canvas id="c" style="position:fixed;inset:0"></canvas><script>var c=document.getElementById('c'),x=c.getContext('2d'),W=c.width=innerWidth,H=c.height=innerHeight,S=[];for(var i=0;i<220;i++)S.push([Math.random()*W,Math.random()*H,Math.random()*3+1,Math.random()*6]);(function L(){var g=x.createLinearGradient(0,0,0,H);g.addColorStop(0,'#0b1d3a');g.addColorStop(1,'#3b5b8c');x.fillStyle=g;x.fillRect(0,0,W,H);x.fillStyle='#fff';S.forEach(function(s){s[1]+=s[2]*.6;s[3]+=.02;s[0]+=Math.sin(s[3])*.6;if(s[1]>H){s[1]=-5;s[0]=Math.random()*W}x.globalAlpha=s[2]/4;x.beginPath();x.arc(s[0],s[1],s[2],0,7);x.fill()});x.globalAlpha=1;requestAnimationFrame(L)})()<\/script>`);
            add('Background', 'Gooey Lava Lamp', `<style>.lv{position:fixed;inset:0;background:linear-gradient(#1a0a2e,#3a0d4e)}.lv div{position:absolute;inset:0;filter:url(#g)}.lv i{position:absolute;bottom:-120px;border-radius:50%;background:linear-gradient(#ff2d95,#ff9a3c);animation:u ease-in-out infinite alternate}@keyframes u{to{transform:translateY(-70vh) scale(1.4)}}</style><svg width="0" height="0"><filter id="g"><feGaussianBlur stdDeviation="16"/><feColorMatrix values="1 0 0 0 0 0 1 0 0 0 0 0 1 0 0 0 0 0 28 -12"/></filter></svg><div class="lv"><div></div></div><script>var h='';for(var i=0;i<9;i++){var s=90+Math.random()*120;h+='<i style="left:'+(5+i*11)+'%;width:'+s+'px;height:'+s+'px;animation-duration:'+(6+Math.random()*8)+'s;animation-delay:-'+Math.random()*8+'s"></i>'}document.querySelector('.lv div').innerHTML=h<\/script>`);
            add('Background', 'Neon Vortex Rings', `<style>.vx{position:fixed;inset:0;background:#000;display:grid;place-items:center;overflow:hidden}.vx i{position:absolute;border-radius:50%;border:3px solid transparent;animation:s linear infinite}@keyframes s{to{transform:rotate(360deg)}}</style><div class="vx"></div><script>var h='';for(var i=0;i<16;i++){var z=60+i*46,c='hsl('+i*22+',100%,60%)';h+='<i style="width:'+z+'px;height:'+z+'px;border-top-color:'+c+';border-bottom-color:'+c+';filter:drop-shadow(0 0 6px '+c+');animation-duration:'+(2+i*.5)+'s;animation-direction:'+(i%2?'reverse':'normal')+'"></i>'}document.querySelector('.vx').innerHTML=h<\/script>`);
            add('Background', 'Bokeh City Lights', `<style>.bk{position:fixed;inset:0;background:linear-gradient(#1a1035,#0d1b3a);overflow:hidden}.bk i{position:absolute;bottom:-120px;border-radius:50%;filter:blur(3px);mix-blend-mode:screen;animation:f linear infinite}@keyframes f{to{transform:translateY(-120vh)}}</style><div class="bk"></div><script>var h='';for(var i=0;i<40;i++){var s=20+Math.random()*90;h+='<i style="left:'+Math.random()*100+'%;width:'+s+'px;height:'+s+'px;background:hsla('+(Math.random()*80+280)+',90%,60%,.45);animation-duration:'+(10+Math.random()*14)+'s;animation-delay:-'+Math.random()*20+'s"></i>'}document.querySelector('.bk').innerHTML=h<\/script>`);
            add('Background', 'CRT Terminal Scanlines', `<style>.cr{position:fixed;inset:0;background:radial-gradient(#0a3d1c,#020c06);display:grid;place-items:center;font:700 34px ui-monospace,monospace;color:#4dff88;text-shadow:0 0 12px #4dff88;overflow:hidden;animation:fk .15s infinite}.cr:before{content:'';position:absolute;inset:0;background:repeating-linear-gradient(#0000 0 2px,#0007 3px)}.cr:after{content:'';position:absolute;left:0;right:0;height:140px;background:linear-gradient(#0000,#4dff8830,#0000);animation:r 5s linear infinite}@keyframes r{from{top:-140px}to{top:100%}}@keyframes fk{50%{opacity:.96}}</style><div class="cr">&gt; SYSTEM ONLINE_</div>`);
            add('Background', 'Sunburst Rays', `<style>.sb{position:fixed;inset:0;background:radial-gradient(#fff4,#0000 60%),#c2410c;overflow:hidden}.sb:before{content:'';position:absolute;left:-50%;top:-50%;width:200%;height:200%;background:repeating-conic-gradient(#fff2 0 6deg,#0000 6deg 18deg);animation:s 40s linear infinite}.sb:after{content:'';position:absolute;left:50%;top:50%;width:260px;height:260px;margin:-130px;border-radius:50%;background:radial-gradient(#fff,#fde047 40%,#f97316);box-shadow:0 0 120px #fde047}@keyframes s{to{transform:rotate(360deg)}}</style><div class="sb"></div>`);
            add('Background', '3D Floating Shapes', `<style>.sf{position:fixed;inset:0;perspective:600px;background:#070712;overflow:hidden}.sf i{position:absolute;border:2px solid;animation:r linear infinite;box-shadow:0 0 18px currentColor,inset 0 0 18px currentColor}@keyframes r{to{transform:translate3d(0,-80px,220px) rotateX(360deg) rotateY(360deg)}}</style><div class="sf"></div><script>var h='';for(var i=0;i<30;i++){var s=30+Math.random()*80;h+='<i style="left:'+Math.random()*95+'%;top:'+Math.random()*90+'%;width:'+s+'px;height:'+s+'px;color:hsl('+Math.random()*360+',100%,65%);border-radius:'+(i%3?'8px':'50%')+';animation-duration:'+(6+Math.random()*10)+'s;animation-delay:-'+Math.random()*10+'s"></i>'}document.querySelector('.sf').innerHTML=h<\/script>`);

            /* ===== BATCH 3: HARD 3D + ANIMATION + LOADERS ===== */
            add('3D', 'Realistic Rolling Dice', `<style>.dc{width:100px;height:100px;perspective:600px;cursor:pointer}.di{position:relative;width:100%;height:100%;transform-style:preserve-3d;transition:transform 1.4s cubic-bezier(.2,1.2,.4,1);transform:rotateX(-25deg) rotateY(25deg)}.di b{position:absolute;inset:0;display:grid;grid:repeat(3,1fr)/repeat(3,1fr);padding:14px;border-radius:16px;background:linear-gradient(145deg,#fff,#c9ced8);box-shadow:inset 0 0 14px #0004}.di i{width:18px;height:18px;margin:auto;border-radius:50%;background:radial-gradient(#444,#000)}</style><div class="dc"><div class="di" id="d"></div></div><script>var P=[[4],[0,8],[0,4,8],[0,2,6,8],[0,2,4,6,8],[0,2,3,5,6,8]],T=['rotateY(0)','rotateX(-90deg)','rotateY(90deg)','rotateY(-90deg)','rotateX(90deg)','rotateY(180deg)'],h='',n=0,d=document.getElementById('d');for(var f=0;f<6;f++){h+='<b style="transform:'+T[f]+' translateZ(50px)">';for(var k=0;k<9;k++)h+='<i'+(P[f].indexOf(k)<0?' style="visibility:hidden"':'')+'></i>';h+='</b>'}d.innerHTML=h;d.parentNode.onclick=function(){n++;d.style.transform='rotateX(-25deg) rotateY(25deg) rotateX('+(90*(Math.random()*4|0)+720*n)+'deg) rotateY('+(90*(Math.random()*4|0)+720*n)+'deg)'}<\/script>`);
            add('3D', 'Tag Cloud Sphere', `<style>.tc{position:relative;width:300px;height:300px}.tc span{position:absolute;left:50%;top:50%;font:700 16px system-ui;white-space:nowrap}</style><div class="tc"></div><script>var W=['HTML','CSS','JS','React','Node','3D','SVG','Vue','API','UX','Git','SQL','Web','Sass','Bun','Deno','AI','Cloud','Rust','Go','Docker','Vite'],e=[],a=0,T=document.querySelector('.tc');W.forEach(function(w,i){var s=document.createElement('span');s.textContent=w;T.appendChild(s);var p=Math.acos(1-2*(i+.5)/W.length),q=Math.PI*(1+Math.sqrt(5))*i;e.push([s,Math.sin(p)*Math.cos(q),Math.cos(p),Math.sin(p)*Math.sin(q)])});(function L(){a+=.01;var c=Math.cos(a),s=Math.sin(a);e.forEach(function(o){var X=o[1]*c-o[3]*s,Z=o[1]*s+o[3]*c,k=(Z+2)/3;o[0].style.transform='translate(-50%,-50%) translate('+X*120+'px,'+o[2]*120+'px) scale('+k+')';o[0].style.opacity=k;o[0].style.color='hsl('+(200+Z*60)+',90%,70%)'});requestAnimationFrame(L)})()<\/script>`);
            add('3D', 'Extruded Gold 3D Text', `<style>.ex{font:900 110px system-ui;color:#fde68a;text-shadow:0 1px #f59e0b,0 2px #f59e0b,0 3px #f59e0b,0 4px #d97706,0 5px #d97706,0 6px #d97706,0 7px #b45309,0 8px #b45309,0 9px #b45309,0 10px #92400e,0 12px 12px #0008,0 22px 30px #0006;animation:s 4s ease-in-out infinite alternate}@keyframes s{from{transform:perspective(500px) rotateY(-25deg) rotateX(8deg)}to{transform:perspective(500px) rotateY(25deg) rotateX(8deg)}}</style><div class="ex">GOLD</div>`);
            add('3D', 'DNA Double Helix', `<canvas id="c" width="320" height="340"></canvas><script>var x=document.getElementById('c').getContext('2d'),t=0;(function L(){t+=.03;x.clearRect(0,0,320,340);for(var i=0;i<21;i++){var y=15+i*15,a=t+i*.5,X1=160+Math.sin(a)*75,X2=320-X1,z=Math.cos(a);x.strokeStyle='rgba(255,255,255,.25)';x.beginPath();x.moveTo(X1,y);x.lineTo(X2,y);x.stroke();[[X1,z,'#22d3ee'],[X2,-z,'#f472b6']].forEach(function(p){x.fillStyle=p[2];x.globalAlpha=.55+p[1]*.45;x.beginPath();x.arc(p[0],y,6+p[1]*3,0,7);x.fill()});x.globalAlpha=1}requestAnimationFrame(L)})()<\/script>`);
            add('3D', 'Atom Model', `<style>.sc{perspective:800px}.at{position:relative;width:240px;height:240px;transform-style:preserve-3d;animation:sp 12s linear infinite}.at:before{content:'';position:absolute;left:50%;top:50%;width:34px;height:34px;margin:-17px;border-radius:50%;background:radial-gradient(circle at 35% 30%,#fff,#f472b6 40%,#831843);box-shadow:0 0 30px #f472b6}.at i{position:absolute;inset:0;border:1px solid #38bdf877;border-radius:50%}.at i:nth-child(1){transform:rotateY(70deg)}.at i:nth-child(2){transform:rotateY(70deg) rotateZ(60deg)}.at i:nth-child(3){transform:rotateY(70deg) rotateZ(120deg)}.at b{position:absolute;inset:0;animation:o 2s linear infinite}.at i:nth-child(2) b{animation-duration:2.6s}.at i:nth-child(3) b{animation-duration:3.2s}.at b:after{content:'';position:absolute;top:-7px;left:calc(50% - 7px);width:14px;height:14px;border-radius:50%;background:radial-gradient(#fff,#38bdf8);box-shadow:0 0 14px #38bdf8}@keyframes o{to{transform:rotateZ(360deg)}}@keyframes sp{from{transform:rotateX(20deg) rotateY(0)}to{transform:rotateX(20deg) rotateY(360deg)}}</style><div class="sc"><div class="at"><i><b></b></i><i><b></b></i><i><b></b></i></div></div>`);
            add('3D', 'Newton\'s Cradle', `<style>.nc{position:relative;display:flex;padding:0 20px;height:190px}.nc:before{content:'';position:absolute;left:0;right:0;top:0;height:10px;border-radius:5px;background:linear-gradient(#9ca3af,#4b5563)}.nc i{position:relative;width:40px;height:170px;margin-top:10px;transform-origin:50% 0}.nc i:before{content:'';position:absolute;left:50%;top:0;width:1px;height:130px;background:#aaa}.nc i:after{content:'';position:absolute;bottom:0;left:0;width:40px;height:40px;border-radius:50%;background:radial-gradient(circle at 35% 30%,#fff,#9ca3af 40%,#374151);box-shadow:0 8px 10px #0006}.nc i:first-of-type{animation:l 1.6s infinite}.nc i:last-child{animation:r 1.6s infinite}@keyframes l{0%{transform:rotate(38deg);animation-timing-function:ease-in}25%{transform:rotate(0)}75%{transform:rotate(0);animation-timing-function:ease-out}100%{transform:rotate(38deg)}}@keyframes r{0%,25%{transform:rotate(0);animation-timing-function:ease-out}50%{transform:rotate(-38deg);animation-timing-function:ease-in}75%,100%{transform:rotate(0)}}</style><div class="nc"><i></i><i></i><i></i><i></i><i></i></div>`);
            add('3D', 'Rotating Text Ring', `<style>.rn{perspective:800px}.rr{position:relative;width:0;height:0;transform-style:preserve-3d;animation:s 12s linear infinite}.rr span{position:absolute;font:900 34px system-ui;color:#fff;text-shadow:0 0 12px #a78bfa}@keyframes s{from{transform:rotateX(-12deg) rotateY(0)}to{transform:rotateX(-12deg) rotateY(360deg)}}</style><div class="rn"><div class="rr"></div></div><script>var t='ELEMENTVERSE • CREATE • ',h='';for(var i=0;i<t.length;i++)h+='<span style="transform:rotateY('+i*360/t.length+'deg) translateZ(180px)">'+t[i]+'</span>';document.querySelector('.rr').innerHTML=h<\/script>`);
            add('Animation', 'Text Scramble Decoder', `<style>.sc2{font:800 44px ui-monospace,monospace;color:#4ade80;cursor:pointer;text-shadow:0 0 14px #22c55e}</style><div class="sc2" id="s">HOVER ME</div><script>var s=document.getElementById('s'),W=s.textContent,C='!<>-_/[]{}=+*^?#';s.onmouseenter=function(){var f=0;clearInterval(s.t);s.t=setInterval(function(){s.textContent=W.split('').map(function(ch,i){return i<f/3?ch:C[Math.random()*C.length|0]}).join('');if(++f>W.length*3)clearInterval(s.t)},35)};s.onmouseenter()<\/script>`);
            add('Animation', 'Confetti Burst Button', `<canvas id="c" style="position:fixed;inset:0"></canvas><button id="b" style="position:relative;padding:16px 36px;border:0;border-radius:40px;background:#f59e0b;font:800 18px system-ui;cursor:pointer">Celebrate!</button><script>var c=document.getElementById('c'),x=c.getContext('2d'),W=c.width=innerWidth,H=c.height=innerHeight,P=[];document.getElementById('b').onclick=function(e){for(var i=0;i<140;i++)P.push({x:e.clientX,y:e.clientY,vx:(Math.random()-.5)*16,vy:-Math.random()*16-4,r:Math.random()*6.28,c:'hsl('+Math.random()*360+',90%,60%)'})};(function L(){x.clearRect(0,0,W,H);P=P.filter(function(p){p.vy+=.35;p.x+=p.vx;p.y+=p.vy;p.r+=.2;x.save();x.translate(p.x,p.y);x.rotate(p.r);x.fillStyle=p.c;x.fillRect(-4,-2,8,4);x.restore();return p.y<H+20});requestAnimationFrame(L)})()<\/script>`);
            add('Animation', 'Music Equalizer', `<style>.eq{display:flex;gap:6px;align-items:end;height:120px}.eq i{width:12px;height:100%;background:linear-gradient(#f0abfc,#7c3aed);border-radius:4px;transform-origin:bottom;animation:e 1s ease-in-out infinite alternate;box-shadow:0 0 12px #a855f7}@keyframes e{from{transform:scaleY(.1)}}</style><div class="eq"></div><script>var h='';for(var i=0;i<18;i++)h+='<i style="animation-duration:'+(.4+Math.random()*.8)+'s;animation-delay:-'+Math.random()+'s"></i>';document.querySelector('.eq').innerHTML=h<\/script>`);
            add('Loader', 'Folding Cube Loader', `<style>.fo{width:60px;height:60px;position:relative;transform:rotateZ(45deg)}.fo i{float:left;width:50%;height:50%;position:relative;transform:scale(1.1)}.fo i:before{content:'';position:absolute;inset:0;background:#22d3ee;animation:f 2.4s infinite linear both;transform-origin:100% 100%}.fo i:nth-child(2){transform:scale(1.1) rotateZ(90deg)}.fo i:nth-child(4){transform:scale(1.1) rotateZ(180deg)}.fo i:nth-child(3){transform:scale(1.1) rotateZ(270deg)}.fo i:nth-child(2):before{animation-delay:.3s}.fo i:nth-child(4):before{animation-delay:.6s}.fo i:nth-child(3):before{animation-delay:.9s}@keyframes f{0%,10%{transform:perspective(140px) rotateX(-180deg);opacity:0}25%,75%{transform:perspective(140px) rotateX(0);opacity:1}90%,100%{transform:perspective(140px) rotateY(180deg);opacity:0}}</style><div class="fo"><i></i><i></i><i></i><i></i></div>`);
            add('Loader', 'Infinity Trail Loader', `<style>.if path.m{stroke-dasharray:30 70;animation:d 2s linear infinite;filter:drop-shadow(0 0 8px #22d3ee)}@keyframes d{to{stroke-dashoffset:-100}}</style><svg class="if" viewBox="0 0 120 60" width="240" fill="none" stroke-width="6" stroke-linecap="round"><path pathLength="100" stroke="#ffffff12" d="M60 30C75 5 105 5 105 30S75 55 60 30C45 5 15 5 15 30S45 55 60 30Z"/><path class="m" pathLength="100" stroke="#22d3ee" d="M60 30C75 5 105 5 105 30S75 55 60 30C45 5 15 5 15 30S45 55 60 30Z"/></svg>`);
            add('Loader', 'Sonar Pulse Loader', `<style>.pr{position:relative;width:120px;height:120px}.pr i{position:absolute;inset:0;border:3px solid #f472b6;border-radius:50%;animation:p 2.4s ease-out infinite}.pr i:nth-child(2){animation-delay:.8s}.pr i:nth-child(3){animation-delay:1.6s}@keyframes p{from{transform:scale(.1);opacity:1}to{transform:scale(1);opacity:0}}</style><div class="pr"><i></i><i></i><i></i></div>`);
            add('Loader', 'Glossy Progress Bar', `<style>.pg{width:300px;height:18px;border-radius:12px;background:#ffffff14;overflow:hidden;box-shadow:inset 0 2px 4px #0008}.pg i{display:block;height:100%;border-radius:12px;background:linear-gradient(90deg,#22c55e,#a3e635);position:relative;animation:f 4s ease-in-out infinite alternate}.pg i:after{content:'';position:absolute;inset:0;background:linear-gradient(110deg,#0000 30%,#fff8 50%,#0000 70%);background-size:200%;animation:s 1.2s linear infinite}@keyframes f{from{width:8%}to{width:96%}}@keyframes s{from{background-position:200% 0}to{background-position:-200% 0}}</style><div class="pg"><i></i></div>`);

            /* ===== BATCH 4 ===== */
            add('Background', 'Grainy Aurora Gradient', `<style>.gn{position:fixed;inset:0;background:linear-gradient(120deg,#ff5f6d,#7b2ff7,#00c6ff,#ff5f6d);background-size:300% 300%;animation:m 10s ease infinite}.gn:after{content:'';position:absolute;inset:0;opacity:.3;background:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='200' height='200'%3E%3Cfilter id='n'%3E%3CfeTurbulence baseFrequency='.8' numOctaves='2'/%3E%3C/filter%3E%3Crect width='200' height='200' filter='url(%23n)'/%3E%3C/svg%3E")}@keyframes m{50%{background-position:100% 50%}}</style><div class="gn"></div>`);
            add('Background', 'Cursor Glow Grid', `<style>.cg{position:fixed;inset:0;background:#05060d}.cg:before{content:'';position:absolute;inset:0;background-image:linear-gradient(#22d3eecc 1px,transparent 1px),linear-gradient(90deg,#22d3eecc 1px,transparent 1px);background-size:50px 50px;-webkit-mask-image:radial-gradient(260px circle at var(--x,50%) var(--y,50%),#000,transparent);mask-image:radial-gradient(260px circle at var(--x,50%) var(--y,50%),#000,transparent)}</style><div class="cg" id="g"></div><script>onmousemove=function(e){g.style.setProperty('--x',e.clientX+'px');g.style.setProperty('--y',e.clientY+'px')}<\/script>`);
            add('Background', 'Meteor Shower', `<style>.mt{position:fixed;inset:0;background:radial-gradient(#1b2450,#050816);overflow:hidden}.mt i{position:absolute;top:-150px;width:2px;height:130px;background:linear-gradient(#fff,#0000);transform:rotate(35deg);animation:m linear infinite}@keyframes m{to{transform:translate(-560px,900px) rotate(35deg)}}</style><div class="mt"></div><script>var h='';for(var i=0;i<18;i++)h+='<i style="left:'+(Math.random()*130)+'%;animation-duration:'+(1.2+Math.random()*2)+'s;animation-delay:-'+Math.random()*4+'s"></i>';document.querySelector('.mt').innerHTML=h<\/script>`);
            add('UI', 'Sliding Tab Bar', `<style>.tb2{position:relative;display:flex;padding:6px;border-radius:14px;background:#ffffff10;font:600 15px system-ui;color:#fff}.tb2 span{position:relative;z-index:1;padding:10px 22px;cursor:pointer}.tb2 i{position:absolute;top:6px;bottom:6px;left:6px;width:80px;border-radius:10px;background:linear-gradient(90deg,#7c3aed,#22d3ee);transition:.35s cubic-bezier(.5,1.4,.5,1)}</style><div class="tb2"><i></i><span>Home</span><span>Explore</span><span>Profile</span></div><script>var T=document.querySelector('.tb2'),I=T.querySelector('i');T.querySelectorAll('span').forEach(function(s){s.onclick=function(){I.style.left=s.offsetLeft+'px';I.style.width=s.offsetWidth+'px'}});T.querySelector('span').click()<\/script>`);
            add('UI', 'Skeleton Loading Card', `<style>.sk2{width:260px;padding:16px;border-radius:16px;background:#ffffff0a}.sk2 i{display:block;border-radius:8px;background:linear-gradient(90deg,#ffffff10 30%,#ffffff25 50%,#ffffff10 70%);background-size:300%;animation:s 1.4s linear infinite;margin-bottom:12px}@keyframes s{to{background-position:-300% 0}}</style><div class="sk2"><i style="height:120px"></i><i style="height:14px;width:70%"></i><i style="height:14px"></i><i style="height:14px;width:50%"></i></div>`);
            add('UI', 'Toast Notifications', `<style>.ts{position:fixed;right:20px;bottom:20px;display:flex;flex-direction:column;gap:10px}.ts div{padding:14px 20px;border-radius:12px;background:#111827;border-left:4px solid #22c55e;color:#fff;font:600 14px system-ui;box-shadow:0 10px 30px #0008;animation:i .4s cubic-bezier(.2,1.4,.4,1),o .4s 2.6s forwards}@keyframes i{from{transform:translateX(120%)}}@keyframes o{to{opacity:0;transform:translateX(120%)}}.tb{padding:14px 30px;border:0;border-radius:12px;background:#22c55e;font:700 16px system-ui;cursor:pointer}</style><button class="tb" onclick="var d=document.createElement('div');d.textContent='Saved successfully!';document.querySelector('.ts').appendChild(d);setTimeout(function(){d.remove()},3100)">Show toast</button><div class="ts"></div>`);
            add('UI', 'Glow Star Rating', `<style>.st5{display:flex;flex-direction:row-reverse;gap:6px}.st5 input{display:none}.st5 label{font-size:44px;color:#374151;cursor:pointer;transition:.2s}.st5 label:hover,.st5 label:hover~label,.st5 input:checked~label{color:#fbbf24;text-shadow:0 0 16px #fbbf24;transform:scale(1.15)}</style><div class="st5"><input type="radio" name="r" id="r5"><label for="r5">★</label><input type="radio" name="r" id="r4"><label for="r4">★</label><input type="radio" name="r" id="r3"><label for="r3">★</label><input type="radio" name="r" id="r2"><label for="r2">★</label><input type="radio" name="r" id="r1"><label for="r1">★</label></div>`);
            add('UI', 'Hamburger to X Menu', `<style>.hm2{width:60px;height:60px;border-radius:16px;background:#ffffff12;display:grid;place-content:center;gap:7px;cursor:pointer}.hm2 i{width:30px;height:3px;border-radius:3px;background:#fff;transition:.4s}.hm2.o i:nth-child(1){transform:translateY(10px) rotate(45deg)}.hm2.o i:nth-child(2){opacity:0;transform:scaleX(0)}.hm2.o i:nth-child(3){transform:translateY(-10px) rotate(-45deg)}</style><div class="hm2" onclick="this.classList.toggle('o')"><i></i><i></i><i></i></div>`);
            add('UI', 'Sun and Moon Toggle', `<style>.tm{width:120px;height:56px;border-radius:40px;background:linear-gradient(#60a5fa,#93c5fd);position:relative;cursor:pointer;transition:.5s;overflow:hidden}.tm i{position:absolute;top:6px;left:6px;width:44px;height:44px;border-radius:50%;background:radial-gradient(#fde047,#f59e0b);box-shadow:0 0 20px #fde047;transition:.5s}.tm.n{background:linear-gradient(#0f172a,#312e81)}.tm.n i{left:70px;background:radial-gradient(circle at 30% 30%,#fff,#cbd5e1);box-shadow:inset -8px -4px 0 #94a3b8,0 0 16px #fff6}</style><div class="tm" onclick="this.classList.toggle('n')"><i></i></div>`);
            add('UI', 'Heart Like Burst', `<style>.hb{position:relative;font-size:70px;cursor:pointer;filter:grayscale(1);transition:.3s;user-select:none}.hb.on{filter:none;animation:p .5s}.hb s{position:absolute;left:50%;top:50%;width:8px;height:8px;border-radius:50%;background:#f43f5e;animation:b .7s forwards}@keyframes p{40%{transform:scale(1.5)}}@keyframes b{to{transform:translate(var(--x),var(--y)) scale(0);opacity:0}}</style><div class="hb" onclick="var e=this;e.classList.toggle('on');if(e.classList.contains('on'))for(var i=0;i<10;i++){var s=document.createElement('s'),a=i*36*Math.PI/180;s.style.setProperty('--x',Math.cos(a)*60+'px');s.style.setProperty('--y',Math.sin(a)*60+'px');e.appendChild(s);setTimeout(function(q){q.remove()},700,s)}">❤️</div>`);
            add('UI', 'Expanding Search Bar', `<style>.sr{display:flex;align-items:center;width:52px;height:52px;border-radius:30px;background:#ffffff14;border:1px solid #fff3;transition:.5s cubic-bezier(.5,1.3,.5,1);overflow:hidden}.sr:focus-within,.sr:hover{width:300px}.sr span{min-width:52px;text-align:center;font-size:20px}.sr input{flex:1;background:none;border:0;outline:0;color:#fff;font:16px system-ui;padding-right:18px}</style><div class="sr"><span>🔍</span><input placeholder="Search anything..."></div>`);
            add('UI', 'Spotlight Pricing Card', `<style>.sp{position:relative;width:260px;padding:30px;border-radius:20px;background:#0f0f1a;color:#fff;font-family:system-ui;overflow:hidden;border:1px solid #ffffff1a}.sp:before{content:'';position:absolute;inset:0;background:radial-gradient(220px circle at var(--x,50%) var(--y,50%),#a855f766,transparent);opacity:0;transition:.3s}.sp:hover:before{opacity:1}.sp>*{position:relative}.sp h2{font:800 46px system-ui;margin:8px 0}.sp li{list-style:none;padding:5px 0;opacity:.75}</style><div class="sp"><small>PRO</small><h2>$29</h2><ul><li>✓ Unlimited projects</li><li>✓ Priority support</li><li>✓ Analytics</li></ul></div><script>var s=document.querySelector('.sp');s.onmousemove=function(e){var r=s.getBoundingClientRect();s.style.setProperty('--x',e.clientX-r.left+'px');s.style.setProperty('--y',e.clientY-r.top+'px')}<\/script>`);
            add('UI', 'Neon Glow Input', `<style>.gi{position:relative;width:300px}.gi:before{content:'';position:absolute;inset:-2px;border-radius:14px;background:linear-gradient(90deg,#f0f,#0ff,#ff0,#f0f);background-size:300%;filter:blur(8px);opacity:.6;animation:g 4s linear infinite}.gi input{position:relative;width:100%;padding:16px 18px;border-radius:12px;border:0;outline:0;background:#0b0b14;color:#fff;font:16px system-ui}@keyframes g{to{background-position:300% 0}}</style><div class="gi"><input placeholder="Type something..."></div>`);
            add('Animation', 'Wavy Letters', `<style>.wv2{display:flex;font:900 64px system-ui;color:#fff}.wv2 span{animation:w 1.2s ease-in-out infinite;text-shadow:0 0 16px #a78bfa}@keyframes w{50%{transform:translateY(-22px);color:#22d3ee}}</style><div class="wv2"></div><script>document.querySelector('.wv2').innerHTML='WAVE MOTION'.split('').map(function(c,i){return '<span style="animation-delay:'+i*.08+'s">'+(c==' '?'&nbsp;':c)+'</span>'}).join('')<\/script>`);
            add('Animation', 'Cursor Follower Blob', `<style>.fb{position:fixed;left:0;top:0;width:60px;height:60px;margin:-30px;border-radius:50%;background:radial-gradient(#22d3ee,#8b5cf6 70%,#0000);filter:blur(6px);pointer-events:none;mix-blend-mode:screen}.hi{font:800 40px system-ui;color:#fff;opacity:.6}</style><div class="hi">Move your mouse</div><div class="fb"></div><script>var b=document.querySelector('.fb'),X=innerWidth/2,Y=innerHeight/2,mx=X,my=Y;onmousemove=function(e){mx=e.clientX;my=e.clientY};(function L(){X+=(mx-X)*.12;Y+=(my-Y)*.12;b.style.transform='translate('+X+'px,'+Y+'px)';requestAnimationFrame(L)})()<\/script>`);
            add('Animation', 'Sweep Fill Button', `<style>.sw2{position:relative;padding:16px 44px;border:2px solid #22d3ee;border-radius:12px;background:none;color:#22d3ee;font:800 18px system-ui;overflow:hidden;cursor:pointer;transition:color .4s}.sw2:before{content:'';position:absolute;inset:0;background:#22d3ee;transform:translateX(-101%) skewX(-20deg);transition:.45s}.sw2:hover{color:#031318}.sw2:hover:before{transform:translateX(0) skewX(-20deg) scale(1.3)}.sw2 span{position:relative}</style><button class="sw2"><span>Hover Sweep</span></button>`);
            add('Animation', 'Typing Indicator', `<style>.ty{display:inline-flex;gap:6px;padding:18px 22px;border-radius:24px 24px 24px 6px;background:#334155}.ty i{width:10px;height:10px;border-radius:50%;background:#cbd5e1;animation:t 1.2s infinite}.ty i:nth-child(2){animation-delay:.2s}.ty i:nth-child(3){animation-delay:.4s}@keyframes t{30%{transform:translateY(-8px);background:#fff}}</style><div class="ty"><i></i><i></i><i></i></div>`);
            add('Animation', 'Rotating Text Badge', `<style>.cbg{width:200px;height:200px;animation:r 12s linear infinite}@keyframes r{to{transform:rotate(360deg)}}</style><svg class="cbg" viewBox="0 0 200 200"><defs><path id="p" d="M100 100m-75 0a75 75 0 1 1 150 0a75 75 0 1 1 -150 0"/></defs><circle cx="100" cy="100" r="42" fill="#a855f7"/><text font-family="system-ui" font-weight="800" font-size="19" fill="#fff" letter-spacing="3"><textPath href="#p">CREATE • DESIGN • SHIP • CREATE • DESIGN • SHIP •</textPath></text></svg>`);
            add('Graph', 'Live Stock Sparkline', `<style>svg{overflow:visible}</style><svg viewBox="0 0 300 100" width="360"><polyline id="pl" fill="none" stroke="#4ade80" stroke-width="3" stroke-linejoin="round" style="filter:drop-shadow(0 0 6px #4ade80)"/></svg><script>var v=[];for(var i=0;i<30;i++)v.push(50);setInterval(function(){v.push(Math.max(5,Math.min(95,v[v.length-1]+(Math.random()-.5)*30)));v.shift();document.getElementById('pl').setAttribute('points',v.map(function(y,i){return i*10.3+','+(100-y)}).join(' '))},200)<\/script>`);
            add('Stats', 'Ring Countdown Timer', `<style>svg{transform:rotate(-90deg)}.rt{stroke-dasharray:100;animation:r 10s linear infinite}@keyframes r{from{stroke-dashoffset:0}to{stroke-dashoffset:100}}</style><svg viewBox="0 0 120 120" width="200" fill="none" stroke-width="8" stroke-linecap="round"><circle cx="60" cy="60" r="50" stroke="#ffffff14"/><circle class="rt" pathLength="100" cx="60" cy="60" r="50" stroke="#f472b6" style="filter:drop-shadow(0 0 6px #f472b6)"/></svg>`);
            add('3D', 'Layered Pop-Out Card', `<style>.pl{width:220px;height:280px;perspective:800px}.pl div{position:relative;width:100%;height:100%;transform-style:preserve-3d;transition:.5s;border-radius:20px;background:linear-gradient(160deg,#4c1d95,#0f172a);border:1px solid #fff3}.pl:hover div{transform:rotateX(14deg) rotateY(-16deg)}.pl b{position:absolute;left:22px;top:22px;font:800 30px system-ui;color:#fff;transform:translateZ(60px)}.pl i{position:absolute;right:-24px;bottom:34px;width:110px;height:110px;border-radius:50%;background:radial-gradient(circle at 30% 30%,#f0abfc,#a855f7);transform:translateZ(90px);box-shadow:0 20px 30px #0008}</style><div class="pl"><div><b>Hover<br>Me</b><i></i></div></div>`);

            /* ===== SITE ===== */
            const $ = s => document.querySelector(s);
            const FULL = c => c == 'Background' || c == 'Page';
            const wrap = e => '<!DOCTYPE html><html><head><meta charset="utf-8"><meta name="viewport" content="width=device-width,initial-scale=1"><style>*{box-sizing:border-box}body{margin:0;background:#0a0812;color:#eee;font-family:system-ui,sans-serif;' + (FULL(e.c) ? '' : 'min-height:100vh;display:grid;place-items:center;overflow:hidden') + '}</style></head><body>' + e.code + '</body></html>';
            const N = (k, f) => Array.from({
                length: k
            }, (_, i) => f(i)).join('');
            const F = ['', 'rotateY(90deg)', 'rotateY(180deg)', 'rotateY(-90deg)', 'rotateX(90deg)', 'rotateX(-90deg)'];
            $('#hc').innerHTML = F.map(t => '<i style="transform:' + t + ' translateZ(60px)"></i>').join('');
            $('#r1').innerHTML = N(6, i => '<span style="transform:rotateY(' + i * 60 + 'deg) translateZ(190px)"></span>');
            document.addEventListener('mousemove', e => {
                const x = e.clientX / innerWidth - .5
                  , y = e.clientY / innerHeight - .5;
                $('#rig').style.transform = 'rotateY(' + x * 50 + 'deg) rotateX(' + -y * 35 + 'deg)'
            }
            );
            const cats = ['All', ...new Set(E.map(e => e.c))];
            $('#st').innerHTML = '<span><b>100+</b>Elements</span><span><b>' + (cats.length - 1) + '</b>Categories</span><span><b>1 Click</b>Copy Code</span>';
            $('#tabs').innerHTML = cats.map(c => '<button class="tb' + (c == 'All' ? ' on' : '') + '">' + c + '</button>').join('');
            let cur = 'All';
            const fit = () => document.querySelectorAll('.pv').forEach(p => {
                p.firstChild.style.transform = 'scale(' + p.clientWidth / p.dataset.w + ')'
            }
            );
            const io = new IntersectionObserver(es => es.forEach(e => {
                const f = e.target.querySelector('iframe');
                if (e.isIntersecting) {
                    if (!f.srcdoc)
                        f.srcdoc = wrap(E[e.target.dataset.i]);
                    fit()
                } else
                    f.srcdoc = ''
            }
            ),{
                rootMargin: '300px'
            });
            function toast(m) {
                const t = $('#tt');
                t.textContent = m;
                t.classList.add('on');
                setTimeout( () => t.classList.remove('on'), 1800)
            }
            async function copy(s) {
                try {
                    await navigator.clipboard.writeText(s)
                } catch (e) {
                    const a = document.createElement('textarea');
                    a.value = s;
                    document.body.appendChild(a);
                    a.select();
                    document.execCommand('copy');
                    a.remove()
                }
                toast('Code copied!')
            }
            function render() {
                const g = $('#grid');
                g.innerHTML = '';
                E.forEach( (e, i) => {
                    if (cur != 'All' && e.c != cur)
                        return;
                    const w = FULL(e.c) ? 1200 : 600
                      , a = document.createElement('article');
                    a.className = 'card';
                    a.dataset.i = i;
                    a.style.animationDelay = (g.children.length % 12) * .04 + 's';
                    a.innerHTML = '<div class="pv" data-w="' + w + '"><iframe sandbox="allow-scripts" tabindex="-1" style="width:' + w + 'px;height:' + w * .625 + 'px"></iframe></div><div class="inf"><div><b>' + e.n + '</b><small>' + e.c + '</small></div><div><button data-a="c">Copy Code</button><button data-a="o">Preview</button></div></div>';
                    a.onmousemove = v => {
                        const r = a.getBoundingClientRect()
                          , x = (v.clientX - r.left) / r.width - .5
                          , y = (v.clientY - r.top) / r.height - .5;
                        a.style.transform = 'perspective(800px) rotateY(' + x * 8 + 'deg) rotateX(' + -y * 8 + 'deg) translateY(-4px)'
                    }
                    ;
                    a.onmouseleave = () => a.style.transform = '';
                    a.querySelector('.pv').onclick = () => openM(i);
                    a.querySelector('[data-a=c]').onclick = () => copy(e.code);
                    a.querySelector('[data-a=o]').onclick = () => openM(i);
                    g.appendChild(a);
                    io.observe(a);
                }
                );
            }
            $('#tabs').onclick = e => {
                if (!e.target.classList.contains('tb'))
                    return;
                cur = e.target.textContent;
                document.querySelectorAll('.tb').forEach(c => c.classList.toggle('on', c == e.target));
                render();
                fit()
            }
            ;
            $('#go').onclick = () => {
                const s = $('#lib');
                s.classList.add('on');
                fit();
                s.scrollIntoView({
                    behavior: 'smooth'
                })
            }
            ;
            addEventListener('resize', fit);
            let ci = 0;
            function tab(code) {
                $('#mf').style.display = code ? 'none' : 'block';
                $('#mc').style.display = code ? 'block' : 'none';
                $('#bp').classList.toggle('on', !code);
                $('#bc').classList.toggle('on', code)
            }
            function openM(i) {
                ci = i;
                $('#mt').textContent = E[i].n;
                $('#mf').srcdoc = wrap(E[i]);
                $('#mc').textContent = E[i].code;
                tab(false);
                $('#md').classList.add('on')
            }
            const closeM = () => {
                $('#md').classList.remove('on');
                $('#mf').srcdoc = ''
            }
            ;
            $('#x').onclick = closeM;
            $('#md').onclick = e => {
                if (e.target.id == 'md')
                    closeM()
            }
            ;
            document.onkeydown = e => {
                if (e.key == 'Escape')
                    closeM()
            }
            ;
            $('#bp').onclick = () => tab(false);
            $('#bc').onclick = () => tab(true);
            $('#cp').onclick = () => copy(E[ci].code);
            render();
        </script>
    </body>
</html>
