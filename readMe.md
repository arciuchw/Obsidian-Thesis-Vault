This vault template was made with Master's/PhD thesis' in mind, but can also be used as structured learning environment. 

The main goals:
- Knowledge **retention** -- both when it comes to remembering the core ideas of papers/books/etc and repetition
- **Cross referencing** sources -- the templates and directory structure enable fast filtering of sources
- **Little organization** overhead -- no overthinking over how to organize notes and what templates to use

If you want to know how to use the templates and workflows please see the **Methodology*** section.

For full guide of installation and configuration of the vault please visit **Setup*** section.

# Methodology
Short fyi -- **it is strongly suggested that you modify or limit use of some of the workflows if you deem them useless!**

## Organization
This section answers:
- What is the directory structure?
- How do templates look like?
- How should I use the templates?

### Directories
My proposed structure that works pretty well looks as follows:

```shell
├── 00_Organization
├── 10_Concepts
├── 20_Merges
├── 30_Drafts
├── 40_Technical
├── 90_Dirt
├── 99_Templates
└──readMe.md
```

Now the quick rundown:
- **Organization** -- Here you can make dashboards, calendars, queries, task boards, weekly plans etc. It's just a space to organize your work and remember what to do.
- **Concepts** -- Here you input your 'pre-processed' notes, so what you note while reading or learning. Should be kept pretty atomic - so one per paper or book. **Do not over-complicate it**, if you keep yourself asking if the volume of the note is too big, you're doing it wrong -- the tags in the templates are built for this exact reason. **Focus on writing**
- **Merges** -- Here you 'process' the notes, for example after reading few papers you might notice there is a common core of them. Here's a place to combine all that knowledge. In other words those are summaries and extrapolations from the concept notes
- **Drafts** -- A place to keep the thesis/paper drafts that should be built mostly on merges
- **Technical** -- This is a place to keep notes of bugs, technical issues, tool tutorials etc. Separated from the concepts as usually those won't be as relevant to the thesis/papers -- you can use it as reference to things you check upon often.
- **Dirt** -- Place for loose notes such as links, unchecked references, loose thoughts etc. Basically space for files such as `asdajkd.md` -- after all we are all human.

My overall suggestion is to organize the files by their contexts and meaning rather than their form or format -- keep in mind **how you search for things** while making your directory structure. In case of organizing merges and concepts don't stress too much over it, you can always add queries to your workflow -- that will take care of any intersections between the subjects.

### Notes -- Papers
The template for the papers is based on the **three-pass method**, you can read more [here](https://web.stanford.edu/class/ee384m/Handouts/HowtoReadPaper.pdf), and Cornell Method. It is also integrated with **Zotero** to make the first pass as fast as possible.

The idea is that:
a) after reading many papers we forget their core (especially after long time)
b) it's easy to spend too much time on irrelevant papers

To avoid the first problem the Cornell Method is introduced -- it is flexible enough to provide the brief about any paper, no matter its relevance

To avoid the second problem the three-pass method is introduced:
- **First pass (<= 15 min)** -- read the abstract, introduction and conclusion, skim through the section names. Answers the main questions: what is it about, how relevant is it, do I want to read it.
- **Second pass (<= 1 hour)** -- understand the concepts, terminology, graphs/illustrations. Look for new references.
- **Third pass (sky is the limit)** -- DIY the paper from ground up, try to recreate and validate, check the assumptions
I encourage you to **start notes even for the papers eliminated in the first pass** -- then you can query the database and see if you already checked it out at some point.

### Notes -- Books
Books can serve as learning source and as citation material. Because those two differ significantly there are two templates provided. 

#### Learning Approach
For the learning note, the concept is to first skim the chapters and 'prepare' for what's coming. Then it's in a way similar to the three pass method. 

On the first pass fill-out the Cornell Method note, focus on important ideas and terminology, highlight what is unclear. 

On the second pass look at previously highlighted sections and fill-in the gaps.

Third pass is exercise based, that's when you do the problems that are often listed at the end of the chapters.

#### Research Approach
In this approach you can simply use the three pass method used in the papers -- treat each chapter like paper. Before starting asses which chapters might be interesting and relevant to your research.

### Notes -- Merges
The idea of merges is to compile loose 'bites' of knowledge into more organized manner. It can include comparative analysis, meta analysis or detailed explanation of phenomena. 

Example:
*Let's assume you read some books and articles trying to understand how transistors work. You gained some knowledge about semiconductor physics, structure of diodes and basic circuit theory. Now you might want to merge all of those topics into note: Transistors in Circuit Analysis*. 

Those should be effects of your critical thinking and connecting the dots! Later on, those will be really easy to turn into your thesis/paper drafts.

## Workflows
The `00_Organization` directory contains automated views of your vault: 
- **`01-reading-pipeline.md`** — Query-based reading management. Filters sources by status (unread → pass 1/2/3 → complete), thesis relevance, and topic. Use when deciding what to read next. 
- **`02-thesis-workflow.md`** — Writing pipeline. Maps concepts → merges → drafts for each thesis section. Tracks citations and synthesis progress.
- **`03-weekly-planning.md`** — Reusable weekly template. Set goals, plan daily tasks, and reflect on progress. Duplicate for each week. All workflows use **Dataview queries** to auto-populate from your frontmatter data. Keep them simple — if a workflow doesn't help, delete it.

### Template Usage Workflow

#### From Source to Complete
**1. Find a source** (paper, book, etc.)
- Add to vault using the appropriate template (`concept-template.md`, `book-learning-template.md`, or `book-research-template.md`) using `Ctrl+P -> Zotero Integration: ` 
- Set `reading-status: ❔ unread` and `thesis-relevance: ❔undefined`
- Assign a `topic: [[Topic Name]]`
    
**2. First pass** (15 min for papers, skim chapters for books)
- Fill out quick review section with key concepts and main ideas
- Decide: continue to second pass or skip?
- Update `reading-status: 1️⃣ pass_1`

**3. Second pass** (≤1 hour)
- Deep dive into concepts, terminology, examples
- For books: fill Cornell Method tables per chapter
- Update `thesis-relevance` (🔥, ⭐️⭐️⭐️, ⭐️⭐️, ⭐️, or ❔)
- Update `reading-status: 2️⃣ pass_2`
    

**4. Third pass** (as needed)
- Validate assumptions, recreate logic, test concepts
- Extract key quotes and findings    
- Update `reading-status: 3️⃣ pass_3` or `✅ complete`

**5. Process into merges**
- When multiple sources on same topic are complete, create a **merge note** (`merge-template.md`)
- Synthesis: compare findings, resolve contradictions, extract unique insights
- Link back to source concepts
    

**6. Draft thesis sections**
- Use merges to build thesis drafts (`30_Drafts`)
- Track which merges feed each thesis section
- Update `cited: true` in concept notes as you use them
    

# Setup
## Obsidian Plug-Ins
Keep in mind that good tool is a tool you actually use, if some of those options seem useless or ineffective feel free to modify both the templates and the plug-ins!

Strongly suggested:
- **Dataview** -- for queries and building dashboards
- **Zotero Integration** -- self-explanatory
- **css snippets** -- for better look of Cornell notes

Optional:
- **Templater** -- for inline functions, in templates used to fill-out dates automatically

Quality of life:
- **Style Settings** -- for personalization of Obsidian, worth a shot if you don't already use it!
- **Git** -- to keep your notes safe
- **Excalidraw** -- if you wish to have hand-written notes as well 

**Make sure to enable the plugins**

### Zotero Integration -- Config
To configure the plugin for comfortable use:
1. Change the note import directory to `10_Concepts/<whatever you like>`
2. Add templates for concept, book-research and book-learning. To do that look for `Import Formats -> Add Import Format`. 
	1. I suggest that you setup the output name as `{{title}}.md` or similar -- that way the new notes will have the same name as the title of paper/book
	2. Choose the correct template file
Now when you `Ctrl+P` you can see the Zotero templates that you added!

### css snippets -- config
Even though the plugin doesn't need any configuration make sure that the snippets you want to use:
1. Are in `<vault>/.obsidian/snippets` directory, make one if it doesn't exist
2. Are enabled in the vault settings `Settings -> Appearence`

If you want the **Cornell** table look please input the `.css` file from this repository into your snippets folder.

### Templater -- config
1. Add the `99_Templates` as the templates directory
2. Turn on `Trigger Templater on file creation`
3. Add shortcuts to the `weekly-planning_template` and `merge_template` if you wish

## Zotero Setup
The Zotero plugin for Obsidian requires that you install **Better BibTex**, installation guide [here](https://retorque.re/zotero-better-bibtex/installation/)

