# 🌸 JWLI Website Rebuild

A responsive rebuild of the homepage for the Japanese Women's Leadership Initiative (JWLI), a Boston-based program founded in 2006 that brings emerging women leaders from Japan to Boston for hands-on nonprofit management training. The page covers the program's mission, its history and founders, its partner organizations, and email sign-up forms, and adjusts its layout for laptop, tablet, and phone screens.

_This is a practice project and is not affiliated with JWLI. Logos and photos belong to their owners._

[![Screenshot-2026-10-10-at-3-37-17-AM.png](https://i.postimg.cc/9FwKDRyh/Screenshot-2026-10-10-at-3-37-17-AM.png)](https://postimg.cc/3d7n6wLS)

## How It's Made:

**Tech used:**

<p align="left">
  <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5" />
  <img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white" alt="CSS3" />
</p>

The page is organized into clear sections with semantic HTML: a `<header>` with the main `<nav>`, a hero section with the JWLI logo, mission statement, and an email sign-up `<form>`, followed by the mission highlights, "Our History," "Who We Are," the partner foundations, a newsletter sign-up, and a `<footer>` with site links.

**Layout:** Flexbox handles every part of the layout, from the wrapping nav bar to the side-by-side history text and photos, the founder bio card, and the partner organizations. Each section uses the same centering technique:

```css
padding-left: max(20px, calc((100% - 1500px) / 2));
```

This keeps the content in a centered 1500px column on large screens while letting the section backgrounds stretch full width, and always leaves at least 20px of space on small screens.

**Flexible sizing:** I used `flex: 1` with `min-width` on cards like the founder bio and partner sections, plus `flex-wrap: wrap`, so they share space evenly and wrap onto new lines when the screen gets narrow. Images use `max-width: 100%` so they never overflow their containers.

**Responsiveness:** media queries at 1024px, 768px, and 480px tighten the spacing, hide the decorative hero image on smaller screens, and switch rows to `flex-direction: column` on phones so the history, bio, partners, forms, and footer links stack vertically.

## Optimizations

- Make the nav links work by adding matching `id`s to each section, and turn the footer link lists into real `<a>` links.
- Give each email input a unique `id`. Both forms use `id="email"`, so the second form's label points to the wrong input.
- Keep the newsletter and footer visible on phones. They're currently hidden at 480px, which removes the contact and site links for mobile visitors.
- Rename the image files to short names without spaces (e.g. `jwli-logo.png`, `founder-atsuko-fish.png`).
- Use the organization's name consistently. The page uses "Institute," "Initiative," and "Woman's" in different places.
- Add an **Apply** button style. `.apply-btn` is defined in the CSS but not used in the HTML.
- Remove the unused `normalize.css` and `reset.css` files, since only `style.css` is linked.

## Lessons Learned:

Rebuilding a real organization's site taught me how to break a busy page into sections and plan a layout for each one before writing code. I got much more comfortable with Flexbox, especially combining `flex: 1`, `min-width`, and `flex-wrap` so content adjusts on its own before a media query is even needed. I also learned the `max()` and `calc()` padding trick to center content without extra wrapper `div`s, and how to use media queries to stack and simplify the layout for smaller screens.
