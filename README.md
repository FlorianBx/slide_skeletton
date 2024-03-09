# Guide to Creating Slides with Reveal.js

This framework allows you to easily create interactive presentations using Reveal.js. With a simplified project structure, you can add new slides by creating individual files in the `slides` folder.

## 🛠️ Setup

Before starting, ensure you have cloned the repository and installed all necessary dependencies (if applicable). Launch your local server to see the presentation in action.

## 📄 Creating Slides

To add a new slide to your presentation, follow these simple steps:

1. **Create an HTML file** in the `slides` folder. Name your file meaningfully, for example, `slide_about.html` for a slide talking about yourself or your project.

2. **Structure your slide** using `<section>` tags for each slide or subsection you want to display. For example:

```html
<section>
  <h2>My Slide Title</h2>
  <p>Here are some interesting facts to share.</p>
</section>
```

3. **Repeat** the process for as many slides as you want to add to your presentation.

## 💅 Adding CSS to Your Slides

To style individual slides, follow these guidelines:

1. **Include a `<style>` tag** within your HTML slide file. This tag should come after your slide's content (sections) to ensure styles are scoped properly to the slide. For example:

```html
<section class="custom-slide">
  <h2>Custom Styled Slide</h2>
  <p>This slide has custom styles!</p>
</section>
<style>
  .custom-slide h2 {
    color: red;
  }
  .custom-slide p {
    font-size: 20px;
  }
</style>
```

2. **Scope your styles** by using a unique class or ID for each slide's root `<section>` and prefixing all CSS rules with it. This ensures that styles are applied only to the intended slide and do not affect others.

## 📝 Updating Your Presentation

After creating your slide files in the `slides` folder, you need to add them to the list in the slide-loading script. Open the main presentation file (often `index.html`) and update the `slides` variable in the `loadAllSlides` function with the names of your new slide files.

```javascript
async function loadAllSlides() {
  const slides = ["slide_1", "slide_2", "slide_about"]; // Add your slide file names here
  for (let slideName of slides) {
    await loadSlide(slideName + ".html");
  }

  Reveal.initialize({
    // Reveal.js configuration options
  });
}
```

Replace `"slide_1"`, `"slide_2"`, `"slide_about"` with the names of your slide files without the `.html` extension.

## ▶️ Launching Your Presentation

With your slides added and the list updated, launch your local server (if not already done) and access your presentation through the browser. You should see your new slides integrated into the presentation.

## 📚 Additional Resources

For more information on customizing your slides and using advanced features of Reveal.js (such as transitions, animations, or integrating multimedia content), consult the [official Reveal.js documentation](https://revealjs.com/).
