# Infinite Loop Website

A modern, responsive website for Infinite Loop, showcasing our innovative software solutions.

## Project Structure

```
infinite_loop/
├── public/           # Static files and assets
│   ├── index.html    # Main HTML file
│   ├── css/          # Stylesheets
│   ├── locales/      # Localization JSON files
│   └── config.js     # EmailJS config (generated at deploy)
├── src/              # Source files (for future use)
├── package.json      # Project dependencies
└── README.md         # Project documentation
```

## Setup

1. Install dependencies:
   ```bash
   npm install
   ```

2. Start the development server:
   ```bash
   npm start
   ```

3. Open your browser and navigate to:
   ```
   http://localhost:8080
   ```

## Features

- Responsive design
- Modern UI with Inter font
- Social media integration
- Live reload development server
- **Localized UI** (English by default, easily extendable)
- **Contact form** with single Name, Email, and Message fields
- **EmailJS integration** for direct email sending
- **GitHub Actions** workflow generates `public/config.js` from repository secrets for secure deployment

## EmailJS & Deployment

- The contact form uses [EmailJS](https://www.emailjs.com/) to send messages directly from the frontend.
- EmailJS configuration (public key, service ID, template ID) is injected at deploy time via GitHub Actions using repository secrets.
- The `public/config.js` file is generated automatically and should **not** be tracked by git.
- To configure, add the following secrets to your GitHub repository:
  - `EMAILJS_PUBLIC_KEY`
  - `EMAILJS_SERVICE_ID`
  - `EMAILJS_TEMPLATE_ID`

## Localization

- All UI texts are stored in `public/locales/en.json`.
- To add more languages, create additional JSON files in the `locales` directory and update the fetch path in `index.html`.

## Deployment

- The site is deployed to GitHub Pages using the workflow in `.github/workflows/static.yml`.
- Only the `public` directory is deployed as the site root.
- The workflow generates `public/config.js` from secrets before deployment.

---

For any questions or contributions, please open an issue or pull request.

## Technologies Used

- HTML5
- CSS3
- Font Awesome
- Live Server 