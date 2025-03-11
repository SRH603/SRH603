<svg xmlns="http://www.w3.org/2000/svg" width="100%" height="100%">
  <foreignObject width="100%" height="100%">
    <div xmlns="http://www.w3.org/1999/xhtml">
      <style>
        /* CSS 代码 */
        @import url('https://unpkg.com/normalize.css') layer(normalize);

        @layer normalize, base, demo;

        @layer demo {
          body {
            background: light-dark(#fff, #000);
            display: flex;
            align-items: center;
            justify-content: center;
            flex-direction: column;
            gap: 1rem;
            padding-block: 2rem;
          }

          h1, p {
            margin: 0;
          }

          h1.fluid {
            --font-size-min: 22;
            --font-level: 4.25;
          }

          h3 {
            white-space: nowrap;
            margin: 0;
          }

          body > p {
            width: 74ch;
            max-width: calc(100% - 4rem);
            text-wrap: balance;
            font-family: monospace;
            margin-bottom: 4rem;
            line-height: 1.5;
            opacity: 0.8;
            font-weight: 400;
          }

          @media (max-width: 768px) {
            body > p {
              text-align: center;
            }
          }

          li :is(svg, h3) {
            opacity: 0.6;
            transition: opacity calc(var(--speed) * 1.2) var(--easing);
          }

          li :is(a, p) {
            opacity: 0;
            transition: opacity calc(var(--speed) * 1.2) var(--easing);
            width: fit-content;
          }

          li img {
            filter: grayscale(1) brightness(1.5);
            scale: 1.1;
            transition-property: filter, scale;
            transition-duration: calc(var(--speed) * 1.2);
            transition-timing-function: var(--easing);
          }

          [data-active='true'] :is(a, p, h3, svg) {
            opacity: var(--opacity, 1);
          }

          [data-active='true'] :is(a, p) {
            transition-delay: calc(var(--speed) * 0.25);
          }

          [data-active='true'] img {
            filter: grayscale(0) brightness(1);
            scale: 1;
            transition-delay: calc(var(--speed) * 0.25);
          }

          article {
            width: calc(var(--article-width) * 1px);
            height: 100%;
            position: absolute;
            font-family: monospace;
            top: 0;
            left: 0;
            display: flex;
            flex-direction: column;
            justify-content: flex-end;
            gap: 1rem;
            padding-inline: calc(var(--base) * 0.5 - 9px);
            padding-bottom: 1rem;
            overflow: hidden;
          }

          article h3 {
            position: absolute;
            top: 1rem;
            left: calc(var(--base) * 0.5);
            transform-origin: 0 50%;
            rotate: 90deg;
            font-size: 1rem;
            font-weight: 300;
            text-transform: uppercase;
            font-family: monospace;
          }

          article svg {
            width: 18px;
            fill: none;
          }

          article p {
            font-size: 13px;
            text-wrap: balance;
            line-height: 1.25;
            --opacity: 0.8;
          }

          article a {
            position: absolute;
            bottom: 1rem;
            height: 18px;
            line-height: 1;
            color: inherit;
          }

          article a:is(:focus-visible, :hover) {
            outline: none;
          }

          article a:is(:focus-visible, :hover) span {
            text-decoration: underline;
            text-underline-offset: 4px;
          }

          article a span {
            display: inline-block;
            line-height: 18px;
            translate: calc(var(--base) * 0.5);
            font-weight: 500;
          }

          article img {
            position: absolute;
            pointer-events: none;
            inset: 0;
            width: 100%;
            height: 100%;
            object-fit: cover;
            mask: radial-gradient(100% 100% at 100% 0, #fff, #0000);
          }

          :root {
            --gap: 8px;
            --base: clamp(2rem, 8cqi, 80px);
            --easing: linear(
              0 0%,
              0.1538 4.09%,
              0.2926 8.29%,
              0.4173 12.63%,
              0.5282 17.12%,
              0.6255 21.77%,
              0.7099 26.61%,
              0.782 31.67%,
              0.8425 37%,
              0.8887 42.23%,
              0.9257 47.79%,
              0.9543 53.78%,
              0.9752 60.32%,
              0.9883 67.11%,
              0.9961 75%,
              1 100%
            );
            --speed: 0.6s;
          }

          ul {
            display: grid;
            container-type: inline-size;
            grid-template-columns: 10fr 1fr 1fr 1fr 1fr 1fr 1fr;
            gap: var(--gap);
            list-style-type: none;
            justify-content: center;
            padding: 0;
            height: clamp(300px, 40dvh, 474px);
            margin: 0;
            width: 820px;
            max-width: calc(100% - 4rem);
            transition: grid-template-columns var(--speed) var(--easing);
          }

          li {
            background: light-dark(#fff, #000);
            position: relative;
            overflow: hidden;
            min-width: var(--base);
            border-radius: 8px;
            border: 1px solid color-mix(in hsl, canvas, canvasText 50%);
          }

          #bottomButton {
            width: 100%;
            height: 50px;
            font-size: 30px;
            font-weight: bold;
            color: rgba(255, 255, 255, 0.3);
            background: transparent;
            border: 32px solid rgba(200, 200, 200, 0.0);
            cursor: pointer;
            text-align: center;
            line-height: 0px;
            transition: background-color 0.3s ease, color 0.3s ease;
          }

          #bottomButton:hover {
            background: rgba(200, 200, 200, 0.1);
            color: rgba(0, 0, 0, 0.3);
          }

          .footer {
            bottom: 0;
            left: 0;
            width: 100%;
            background-color: rgba(200, 200, 200, 0.1);
            color: white;
            text-align: center;
            padding: 10px;
            transition: height 0.3s ease-in-out;
            overflow: hidden;
            height: 100px;
          }

          .footer.expanded {
            height: 200px;
          }

          .footer-content {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            color: rgba(255, 255, 255, 0.3);
            height: 100%;
          }

          .pdf-link {
            margin-top: 10px;
            margin-bottom: 10px;
            color: rgba(255, 255, 255, 0.5);
          }
        }

        @layer base {
          :root {
            --font-size-min: 16;
            --font-size-max: 20;
            --font-ratio-min: 1.2;
            --font-ratio-max: 1.33;
            --font-width-min: 375;
            --font-width-max: 1500;
          }

          html {
            color-scheme: dark only;
          }

          [data-theme='light'] {
            color-scheme: light only;
          }

          [data-theme='dark'] {
            color-scheme: dark only;
          }

          :where(.fluid) {
            --fluid-min: calc(
              var(--font-size-min) * pow(var(--font-ratio-min), var(--font-level, 0))
            );
            --fluid-max: calc(
              var(--font-size-max) * pow(var(--font-ratio-max), var(--font-level, 0))
            );
            --fluid-preferred: calc(
              (var(--fluid-max) - var(--fluid-min)) /
              (var(--font-width-max) - var(--font-width-min))
            );
            --fluid-type: clamp(
              (var(--fluid-min) / 16) * 1rem,
              ((var(--fluid-min) / 16) * 1rem) -
              (((var(--fluid-preferred) * var(--font-width-min)) / 16) * 1rem) +
              (var(--fluid-preferred) * var(--variable-unit, 100vi)),
              (var(--fluid-max) / 16) * 1rem
            );
            font-size: var(--fluid-type);
          }

          *, *:after, *:before {
            box-sizing: border-box;
          }

          body {
            display: grid;
            place-items: center;
            min-height: 100vh;
            font-family: 'SF Pro Text', 'SF Pro Icons', 'AOS Icons', 'Helvetica Neue',
            Helvetica, Arial, sans-serif, system-ui;
          }

          body::before {
            --size: 45px;
            --line: color-mix(in hsl, canvasText, transparent 70%);
            content: '';
            height: 100vh;
            width: 100vw;
            position: fixed;
            background: linear-gradient(
              90deg,
              var(--line) 1px,
              transparent 1px var(--size)
            ) 50% 50% / var(--size) var(--size),
            linear-gradient(var(--line) 1px, transparent 1px var(--size)) 50% 50% /
            var(--size) var(--size);
            mask: linear-gradient(-20deg, transparent 50%, white);
            top: 0;
            transform-style: flat;
            pointer-events: none;
            z-index: -1;
          }

          .bear-link {
            color: canvasText;
            position: fixed;
            top: 1rem;
            left: 1rem;
            width: 48px;
            aspect-ratio: 1;
            display: grid;
            place-items: center;
            opacity: 0.8;
            filter: invert(1) grayscale(1);
          }

          :where(.x-link, .bear-link):is(:hover, :focus-visible) {
            opacity: 1;
          }
        }
      </style>

      <!-- HTML 代码 -->
      <h1 class="fluid">Π Tournament</h1>
      <p style="text-align: center;">
        「Explore the mystery of mathematics together」<br>
        International Pi Thunder Tournament<br><br>
        Organizer: <strong>Pi Tournament Committee</strong><br>
        Presented by: <strong>WLSA Shanghai Academy</strong><br><br>
        <button disabled id="bottomButton">Register is now closed</button>
      </p>
      <ul>
        <li data-active="true">
          <article>
            <h3>Archive</h3>
            <p>
              See the Π Tournament 2025 Result!<br>
              -- "The Collatz Conjecture (3n+1 Problem)"
            </p>
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <path d="M6 3h12l4 6-10 13L2 9Z" />
              <path d="M11 3 8 9l4 13 4-13-3-6" />
              <path d="M2 9h20" />
            </svg>
            <a href="archive.html"><span>Learn more</span></a>
            <img src="https://thumbs.dreamstime.com/b/math-background-mathematic-pattern-blackboard-341102941.jpg" alt="" />
          </article>
        </li>
        <li>
          <article>
            <h3>Registration</h3>
            <p>
              Registration is currently unavailable<br>
              -- "Existence and smoothness of solutions to the Navier-Stokes equations"
            </p>
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <rect width="18" height="18" x="3" y="3" rx="2" />
              <path d="M7 3v18" />
              <path d="M3 7.5h4" />
              <path d="M3 12h18" />
              <path d="M3 16.5h4" />
              <path d="M17 3v18" />
              <path d="M17 7.5h4" />
              <path d="M17 16.5h4" />
            </svg>
            <a href="#"><span>Learn more</span></a>
            <img src="https://cdn.pixabay.com/photo/2016/06/13/07/59/pi-1453836_640.jpg" alt="" />
          </article>
        </li>
        <li>
          <article>
            <h3>Committee Info</h3>
            <p>
              More information<br>
              -- "The Hodge conjecture (topological yoke of algebraic clusters)"
            </p>
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <polygon points="22 3 2 3 10 12.46 10 19 14 21 14 12.46 22 3" />
            </svg>
            <a href="info.html"><span>Learn more</span></a>
            <img src="https://as1.ftcdn.net/jpg/01/09/28/58/1000_F_109285832_mn0G2dCysMSpkbxNVPMdT6k8vyYVdA7F.jpg" alt="" />
          </article>
        </li>
        <li>
          <article>
            <h3>Rules</h3>
            <p>
              Learn more about the rules of the contests<br>
              -- "The twin prime conjecture (infinitely close lone primes)"
            </p>
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <path d="M19 17V5a2 2 0 0 0-2-2H4" />
              <path d="M8 21h12a2 2 0 0 0 2-2v-1a1 1 0 0 0-1-1H11a1 1 0 0 0-1 1v1a2 2 0 1 1-4 0V5a2 2 0 1 0-4 0v2a1 1 0 0 0 1 1h3" />
            </svg>
            <a href="rules.html"><span>Learn more</span></a>
            <img src="https://images.pond5.com/math-looping-animated-background-000984568_prevstill.jpeg" alt="" />
          </article>
        </li>
        <li>
          <article>
            <h3>Sponsors</h3>
            <p>
              Learn more about our sponsors<br>
              -- “The Riemann hypothesis (The Plotter from Hell for the Distribution of Prime Numbers)”
            </p>
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <circle cx="13.5" cy="6.5" r=".5" fill="currentColor" />
              <circle cx="17.5" cy="10.5" r=".5" fill="currentColor" />
              <circle cx="8.5" cy="7.5" r=".5" fill="currentColor" />
              <circle cx="6.5" cy="12.5" r=".5" fill="currentColor" />
              <path d="M12 2C6.5 2 2 6.5 2 12s4.5 10 10 10c.926 0 1.648-.746 1.648-1.688 0-.437-.18-.835-.437-1.125-.29-.289-.438-.652-.438-1.125a1.64 1.64 0 0 1 1.668-1.668h1.996c3.051 0 5.555-2.503 5.555-5.554C21.965 6.012 17.461 2 12 2z" />
            </svg>
            <a href="sponsors.html"><span>Learn more</span></a>
            <img src="https://cdn.vectorstock.com/i/1000v/46/15/maths-background-vector-8244615.jpg" alt="" />
          </article>
        </li>
        <li>
          <article>
            <h3>Contact</h3>
            <p>
              Get in touch with us<br>
              -- “The P vs. NP problem (the ultimate seal of the algorithmic abyss)”
            </p>
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <path d="m21.64 3.64-1.28-1.28a1.21 1.21 0 0 0-1.72 0L2.36 18.64a1.21 1.21 0 0 0 0 1.72l1.28 1.28a1.2 1.2 0 0 0 1.72 0L21.64 5.36a1.2 1.2 0 0 0 0-1.72" />
              <path d="m14 7 3 3" />
              <path d="M5 6v4" />
              <path d="M19 14v4" />
              <path d="M10 2v2" />
              <path d="M7 8H3" />
              <path d="M21 16h-4" />
              <path d="M11 3H9" />
            </svg>
            <a href="contact.html"><span>Learn more</span></a>
            <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQaXYNoOzPj_aO9i5wtRvPT1FLhP0eUuzO0YQ&s" alt="" />
          </article>
        </li>
        <li>
          <article>
            <h3>FAQ</h3>
            <p>
              See the frequently asked questions<br>
              -- “The Birch and Swinnerton-Dyer Conjecture (The Code of Silence for Elliptic Curves)”
            </p>
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <path d="M5 22h14" />
              <path d="M5 2h14" />
              <path d="M17 22v-4.172a2 2 0 0 0-.586-1.414L12 12l-4.414 4.414A2 2 0 0 0 7 17.828V22" />
              <path d="M7 2v4.172a2 2 0 0 0 .586 1.414L12 12l4.414-4.414A2 2 0 0 0 17 6.172V2" />
            </svg>
            <a href="faq.html"><span>Learn more</span></a>
            <img src="https://t3.ftcdn.net/jpg/04/61/03/02/360_F_461030258_TwMAu6MNzYmbI33f4Jr7thEZeNM1lXkR.jpg" alt="" />
          </article>
        </li>
      </ul>
      <a class="bear-link" href="detail.html" rel="noreferrer noopener">
        <img src="Logo.jpg" alt="GitHub" width="72">
      </a>
      <p style="text-align: center;">
        <br><br>
        Explore, explore, and explore<br>
      </p>
      <div class="footer" id="footer">
        <div class="footer-content">
          <p style="text-align: center;">Wechat: t-tsinsita</p>
          <a class="pdf-link" href="plan.pdf" target="_blank">Click to view the detailed arrangement</a>
          © 2025 Pi Tournament Committee. All rights reserved.
        </div>
      </div>
    </div>
  </foreignObject>
</svg>
