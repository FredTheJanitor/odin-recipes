Master:
Refs: OdinRecipes
--

Refs: OdinRecipes02
Project 2: Recipes - from The Odin Project - CSS foundations: Block & Inline

Core Skills Used & Demonstrated:

CSS,
Git,
CLI and Bash,

--

After Project Review:

Styled recipe website with 1 external style sheet, reviewed code and realized that there are some quite
sloppy elements.  Ran code through chatgpt to get oppinions on what sucks and it produced the following

Simon-cowell-esque roast of my shoddy CSS:

--

ChatGPT Response:


        Alright, I read your CSS and HTML with a black coffee and a red pen. Here's the roast you asked for — lovingly brutal and hopefully educational. 🍖🔥

        ---

        ## 🧪 Overall Impression

        Your creativity and narrative tone are fantastic — the recipe content is absolutely metal. As for the **CSS**, you’re making solid beginner moves, but some things are hacky, overly verbose, or a little misapplied. Let’s dive in.

        ---

        ## 🔥 CSS Roast & Feedback

        ### 1. **Redundant Selectors & Over-specificity**

        ```css
        .recipeCard.container.bonesOfFoes {
        ```

        You're chaining `.recipeCard.container.bonesOfFoes`. That’s **super specific**, and in CSS, that can become your enemy later. You might find yourself needing `!important` to override it. Why not just:

        ```css
        .bonesOfFoes { }
        ```

        Unless you're intentionally making a bulletproof override, dial it down for flexibility.

        ### 2. **Flex Properties Without Flex Context**

        ```css
        .subcontainer {
            display: flex;
            align-items: center;
            justify-content: center;
            flex-direction: column;
        }
        ```

        Solid intent, but this will **center everything** inside `.subcontainer` even when it doesn’t always need it. Overusing flex for vertical stacking is like eating soup with a fork — you *can*, but why not let the browser’s default block flow handle vertical layout unless you need something more?

        Also, consider:

        ```css
        .subcontainer img {
            margin: 0 auto;
        }
        ```

        To center an image *only*, instead of shoving the entire `.subcontainer` into flex mode.

        ### 3. **You're Styling Elements, But Relying on Class Names**

        You have a class for everything (`.container`, `.subcontainer`, `.steps`, `.ingredients`, etc.), but you’re not using much semantic structure.

        For example, you could simplify:

        ```css
        .steps ol {
            padding-left: 1.5rem;
        }
        ```

        Instead of:

        ```css
        .container.subcontainer.steps ol {
        ```

        Keep it lean. Deep nesting adds no value here unless you're preparing for conflicting sibling styles.

        ### 4. **Typography Choices**

        ```css
        h1 {
            font-size: 3em;
            text-align: center;
            color: #740505;
        }
        ```

        Big dramatic headers work here thematically — but be aware that **3em** on mobile could cause wrapping or overflow. Try using `clamp()` for a more responsive size:

        ```css
        font-size: clamp(2rem, 4vw, 3rem);
        ```

        ### 5. **Color Choices Are Brutal (on Eyes)**

        ```css
        background-color: #111;
        color: #eee;
        ```

        Yes, I know — goth aesthetic. But try to make link states more distinct. Currently, your anchor `<a>` tags get swallowed up. Consider adding a hover state:

        ```css
        a {
        color: #aaa;
        text-decoration: none;
        border-bottom: 1px solid #555;
        }
        a:hover {
        color: red;
        }
        ```

        Lean into that *blood of enemies* theme.

        ### 6. **Home Link Needs Some Love**

        ```html
        <a href="../index.html">Home</a>
        ```

        Right now it’s an afterthought. Make it a button-like element:

        ```css
        a {
        display: inline-block;
        padding: 0.5em 1em;
        background-color: #333;
        color: white;
        border-radius: 5px;
        text-align: center;
        margin-top: 2rem;
        }
        a:hover {
        background-color: crimson;
        }
        ```

        It deserves as much drama as the blood beverage.

        ### 7. **No Mobile Consideration Yet**

        You're using `height="400px"` on images. That’s a hardcoded value — it won’t look good on small screens. Instead:

        ```css
        img {
        max-width: 100%;
        height: auto;
        }
        ```

        Or let the layout define it fluidly with flex/grid and aspect ratios.

        ---

        ## 🏁 File Naming + Structure Notes

        * `styles/style.css` should be `css/style.css` or `assets/css/...` if you start organizing more.
        * The link to the CSS in the HTML is slightly inconsistent in directory level (`../styles/style.css`) vs actual file name you uploaded (`style.css` was in root). Just double-check pathing.

        ---

        ## ✅ What You're Doing Right

        * Excellent use of semantic HTML overall.
        * Consistent formatting and spacing — not sloppy.
        * Fun, creative, and confidently written content. This will serve you *very well* in frontend.
        * You’re experimenting with layout tools like `margin: auto`, `flex`, and stacking — exactly what you should be doing at this stage.

        ---

        ## 🧠 Practice Challenges for You

        To level up:

        1. **Refactor all `.container.subcontainer.XYZ` combos** into more modular, reusable class names.
        2. Add a **media query** that shrinks padding/margins on small screens (mobile).
        3. Add a **hover state to links/buttons** for interactivity.
        4. Try recreating the layout using **Grid** instead of Flexbox.
        5. Make your images **responsive** instead of using fixed `height`.

        ---

        Let me know when you want me to **re-roast a refactor**, or if you want to challenge yourself with a new layout concept (like a grid version of these recipe cards). Keep it metal 🤘



--

Project: Recipes - from The Odin Project

Core Skills Used & Demonstrated:

HTML,
Git/ Github (Conventional Commits),
File Creation & Project Organization,
CLI and Bash,
Culinary Prowess

--

After Project Review:

I have some basic experience with HTML and have been concerned about being stuck in "tutorial hell."
While this is a very "tutorial-hell-ish" project, the focus on git commits, made it feel more advanced.
I believe the focus of prior TOP lessons on git, set me up to take the "git element" of this project 
more seriously than I might have if just presented the generic task of "create a recipe website."

This project pushed me to use CLI for the practical purpose of copying my initial recipe file as a sudo-
template for the subsequent recipes.  I also used git in an Ubuntu Bash terminal with my WSL2 set up
paired with VS Code for my first attempt towards Conventional commits. I created the entire file-
structure and tried to make any and all file structure changes within the terminal, including a mix up
where I had put a file in the wrong folder initially and had to move it after committing. This 
interaction of git and the command line gave me an appreciation for the add and rm features of git.

I feel that I have probably failed quite miserably to properly match the cadence of Conventional commits
here in this first attempt.  However, the process has further encouraged me to imagine the automation 
possibilities that could come with some sort of documentation software that reads properly formatted git
logs.

Upon review of this project I realized that 1: I need to be way better about clicking ctrl+S before
barrelling into my commits LMAO, also being careful and not rushing pays off, for example I noticed
small mistakes in many other students' projects and therefore intuit that I have many of my own. 1
Flaw I discovered was the alt attribute for my flesh of adversaries recipe was not updated properly
which caused me to discover my much larger problem of not hitting ctrl S before Gittin my Git on lol.

A good lesson from this would be to make step 1 of Git: CTRL S YO SHIT.
