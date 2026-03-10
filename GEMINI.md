# Project Overview: Tanay's Blog

This is a personal blog project built using **MkDocs** with the **Material for MkDocs** theme. It is a static site that leverages Markdown for content and custom CSS for a modern, card-based layout. The blog features a single-column vertical feed, responsive design, and a dedicated "About Me" profile component.

## Tech Stack
- **Language:** Python (>= 3.12)
- **Static Site Generator:** [MkDocs](https://www.mkdocs.org/)
- **Theme:** [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)
- **Package Manager:** [uv](https://github.com/astral-sh/uv)
- **Deployment:** GitHub Actions to GitHub Pages

## Project Structure
- `docs/`: Root directory for all Markdown content.
    - `posts/`: Individual blog post files.
    - `assets/`: Media files (images, etc.).
    - `stylesheets/`: Custom CSS files (e.g., `extra.css`).
- `mkdocs.yml`: Global configuration for the MkDocs site, plugins, and navigation.
- `pyproject.toml`: Python project configuration and dependencies.
- `.github/workflows/ci.yml`: Automated deployment pipeline.

## Building and Running
The project uses `uv` for dependency management.

- **Install dependencies:**
  ```bash
  uv sync
  ```
- **Run the development server (local preview):**
  ```bash
  uv run mkdocs serve
  ```
- **Build the static site:**
  ```bash
  uv run mkdocs build
  ```
- **Deploy manually (usually handled by CI):**
  ```bash
  uv run mkdocs gh-deploy
  ```

## Development Conventions
- **Content:** All blog posts should be placed in `docs/posts/`.
- **Styling:** Custom styles should be added to `docs/stylesheets/extra.css` rather than modifying the theme directly.
- **Workflow:** Significant changes should follow the **OpenSpec** artifact-driven approach (Proposal -> Specs -> Design -> Tasks).
- **Assets:** Reference images in Markdown using the `attr_list` syntax (e.g., `{: .profile-image }`) to ensure correct CSS class application and path resolution.

## Configuration Details
- **Plugins:** 
    - `search`: Built-in search functionality.
    - `blog`: Powers the blog index and post metadata.
- **Extensions:** 
    - `attr_list`: Allows adding CSS classes and attributes to Markdown elements.
    - `md_in_html`: Enables Markdown rendering inside HTML blocks.
