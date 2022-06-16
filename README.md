# Demo components for the Svelte workshop

Demo at https://magenta-components-demo.vercel.app/

Installation: `npm install or yarn add magenta-components-demo`

Usage:
```html
<script>
  import { Navbar } from 'magenta-components-demo'
</script>

<Navbar />

// Optionally you can add links
<Navbar
  links={[
    { name: 'About', path: '/about' },
    { name: 'Contact', path: '/contact' }
  ]}
/>
```
