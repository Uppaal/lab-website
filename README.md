# Hu Lab Website (GitHub Pages)

This repository contains the source code for the lab website, hosted via GitHub Pages and built using Jekyll. 

The site is data-driven where possible (people, publications, carousel), so most updates do not require editing HTML.

The website can currently be accessed at:
```
https://uppaal.github.io/lab-website/
```

## Deployment (One-Time)

The site is deployed via GitHub Pages.
- Repository: `lab-website`
- Deployment: `Settings` → `Pages` → `Deploy` from main branch (root)
- Live URL: `https://YOUR_GITHUB_USERNAME.github.io/lab-website/`
  - Or custom domain if configured

**Important:** This site depends on Jekyll. Do not add a `.nojekyll` file.

## Repository Structure

```
_config.yml
index.md
group.md
publications.md
join.md
/_layouts
/_includes
/_data
/assets
```

### Root Files
- `_config.yml`: Global site configuration. Update this if: Changing domain, updating site title.
- `assets/css/style.css`: Contains all custom styling. Only edit if changing visual design.
- `index.md`: Homepage. Contains: Research themes and the carousel layout. Carousel images are loaded from `_data/carousel.yml`.
- `group.md`: Group page. Contains: Faculty (hero block), PhD Students, Masters and Undergrad Students, Alumni.
   - Uses data from `_data/people.yml`. Do not hardcode people here.
- `publications.md`: Publications page.
   - Rendered from `_data/publications.yml`. Only edit this file if changing layout — not when adding papers.
- `join.md`: Recruiting / open positions page.

### Data Files (Update These Regularly)

All dynamic content lives in `_data/`.

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

- `_data/publications.yml`
  - Controls all publications.
  - Add new papers by year:
    ```
    - year: 2025
      items:
        - title: "Title"
          authors: "Authors"
          venue: "In The ..."
          links:
            - label: "Paper"
              url: "https://arxiv.org/abs/..."
            - label: "Code"
              url: "https://github.com/..."
            - label: "Checkpoints"
              url: "https://huggingface.co/collections/..."
            - label: "Project Website"
              url: "..."
    ```

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

### Image Assets

- `assets/photos/`
  - Contains: Faculty, Student, Alumni photos, Carousel images
  - All image paths in YAML are relative to repository root.
  - Use lowercase filenames and avoid spaces.
  - Example: `assets/photos/lab-2024-spring.jpg`
   
  
