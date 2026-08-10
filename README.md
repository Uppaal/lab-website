# Hu Lab Website (GitHub Pages)

This repository contains the source code for the lab website, hosted via GitHub Pages and built using Jekyll. 

The site is data-driven where possible (people, carousel, research blogs) and uses BibTeX for publications, so most updates do not require editing HTML.

The website can currently be accessed at:
```
https://madison-nlp.github.io/hu-lab/
```

## Deployment (One-Time)

The site is deployed via GitHub Pages using GitHub Actions.
- Repository: `hu-lab`
- Deployment: `Settings` -> `Pages` -> `Build and deployment` -> Source: `GitHub Actions`
- Live URL: `https://madison-nlp.github.io/hu-lab/`
  - Or custom domain if configured

**Important:** This site depends on Jekyll. Do not add a `.nojekyll` file.

The publications page uses Jekyll plugins from `Gemfile` (`jekyll-scholar` and `al_folio_core`). Build/deploy with Bundler so those plugins are available.

## Repository Structure

### Root Files
- `_config.yml`: Global site configuration. Update this if: Changing domain, updating site title.
- `Gemfile`: Jekyll build dependencies, including BibTeX publication rendering plugins.
- `assets/css/style.css`: Contains all custom styling. Only edit if changing visual design.
- `index.md`: Homepage. Contains: Research themes and the carousel layout. Carousel images are loaded from `_data/carousel.yml`.
- `group.md`: Group page. Contains: Faculty (hero block), PhD Students, Masters and Undergrad Students, Alumni.
   - Uses data from `_data/people.yml`. Do not hardcode people here.
- `publications.md`: Publications page.
   - Rendered from `_data/papers.bib`. Only edit this file if changing layout, not when adding papers.
- `research-blogs.md`: Research Blogs page.
   - Rendered from `_data/blogs.yml`. Only edit this file if changing layout, not when adding blog posts.
- `join.md`: Recruiting / open positions page.

### Data Files (Update These Regularly)

Dynamic YAML content lives in `_data/`.

- `_data/people.yml`
  - Controls: Faculty, PhD Students, Masters and Undergrad Students, Alumni
  - Update this when: Adding a student, Moving a student to alumni, Updating role/title/website links/photos
  - Example structure:
    ```
    pi:
      name: "Prof. X"
      title: "Assistant Professor, Dept of X"
      affiliation: "University of Y"
      photo: "assets/photos/prof-x.png"
      website: "website"

    phd_students:
      - name: "Student A"
        role: "PhD in CS, Fall 2025-"
        photo: "assets/photos/student-a.jpg"
        website: "..."

    masters_undergrad_students:
      - name: "Student B"
        role: "BS in CS"
        photo: "assets/photos/student-b.jpg"
        website: "..."
  
    alumni:
      - name: "Alum A"
        degree: "PhD"
        role: "PhD (2024), now Company"
        photo: "assets/photos/alum-a.jpg"
        website: "..."
    ```
  - Alumni entries require `degree: "PhD"`, `degree: "MS"`, or `degree: "BS"` to choose the subsection on the Group page.

- `_data/carousel.yml`
  - Controls the homepage carousel images in display order.
  - Add, remove, or reorder carousel slides here. Do not hardcode slides in `index.md`.
  - Each entry should include:
    ```
    - image: "assets/photos/lab-2026-spring.jpg"
      caption: "Hu Lab Outing - Summer 2026"
      alt: "Hu Lab outing in Summer 2026"
    ```
  - `image` should point to an existing file under `assets/photos/`.
  - `caption` is shown over the carousel on medium and larger screens.
  - `alt` should briefly describe the image for accessibility.

- `_data/blogs.yml`
  - Controls the Research Blogs page.
  - Add, remove, or reorder blog posts here. Do not hardcode posts in `research-blogs.md`.
  - Each entry should include:
    ```
    - title: "Understanding Language Model Behavior"
      url: "https://example.com/blog-post"
      authors: "Jane Doe, John Smith"
      byline: "A short one-sentence description of the post."
      image: "assets/blog_diagrams/example.jpg"
    ```
  - Required fields: `title`.
  - Recommended fields: `url`, `authors`, `byline`.
  - Optional field: `image`. If used, point it to an existing file under `assets/photos/` or to a full external URL.
  - If `url` is omitted, the title is rendered as plain text.
  - If `image` is omitted, the tile renders without an image.

### Publications

- `_data/papers.bib`
  - Controls all publications on the Publications page.
  - Add new papers as BibTeX entries. Entries are grouped by `year` automatically.
  - Supported link fields rendered as buttons:
    - `abbr`
    - `paper`
    - `code`
    - `checkpoints`
    - `website`
  - Example entry:
    ```
    @inproceedings{example2026paper,
      title = {Example Paper Title},
      author = {Student A and Junjie Hu},
      venue = {In Example Conference 2026},
      year = {2026},
      abbr = {EMNLP},
      paper = {https://arxiv.org/abs/...},
      code = {https://github.com/...},
      website = {https://example.com/project}
    }
    ```

### Research Blogs

- `_data/blogs.yml`
  - Controls all entries on the Research Blogs page.
  - To add a post, append a new YAML item with `title`, `url`, `authors`, `byline`, and optionally `image`.
  - Keep image paths relative to the repository root, for example `assets/photos/blog-image.jpg`.
  - Blog posts appear in the same order as the YAML entries.

### Image Assets

- `assets/photos/`
  - Contains: Faculty, Student, Alumni photos, Carousel images
  - All image paths in YAML are relative to repository root.
  - Use lowercase filenames and avoid spaces.
  - Example: `assets/photos/lab-2024-spring.jpg`
   
  
