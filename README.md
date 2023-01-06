# Tailwind css (based off netninja tailwindcss tutorial)

## 1. Source / Preview Links

- Preview - https://tutorial-netninja-tailwindcss.vercel.app/
- Youtube tutorial - https://www.youtube.com/playlist?app=desktop&list=PL4cUxeGkcC9gpXORlEHjc5bgnIi5HEGhw
- github - https://github.com/iamshaunjp/tailwind-tutorial

## 2. setup - installation - https://tailwindcss.com/docs/installation

    ```terminal
    npm install -D tailwindcss postcss autoprefixer

    npx tailwindcss init
    ```

- visual studio code plugin - tailwind css intellisense

### 1. Add Tailwind to your PostCSS configuration

    ```
    <!-- postcss.config.js -->
    module.exports = {
    plugins: {
        tailwindcss: {},
        autoprefixer: {},
    }
    }
    ```

### 2. Configure your template paths

    ```
    <!-- tailwind.config.js -->
    /** @type {import('tailwindcss').Config} */
    module.exports = {
    content: ["./src/**/*.{html,js}"],
    theme: {
        extend: {},
    },
    plugins: [],
    }
    ```

### 3. Add the Tailwind directives to your CSS

    ```
    <!-- input.css -->
    @tailwind base;
    @tailwind components;
    @tailwind utilities;
    ```

## 3. fonts and colors

### fonts

text-xs
text-sm
text-base
text-lg
text-xl
...
.text-6xl

### colors

text-red-400
text-gray-300
uppercase
font-bold
font-semibold

## 4. padding/margin/borders

### padding

p-1,2,3,4,5,6,8,10,12,16,20,24,32,40,48,56,64
px-
py-
pt-
pr-
pb-
pl-

### margin

m-1,2,3,4,5,6,8,10,12,16,20,24,32,40,48,56,64
mx-
my-
mt-
mr-
mb-
ml-

### borders

border
border-0,2,4,8
border-t,r,b,l
border-t-0
border-r-0
border-b-0
border-l-0

## 5. tailwind config

### tailwind default : npx tailwindcss init

- edit default using prop: 'extend'

```js
//tailwind.config.js
module.exports = {
	purge:[],
	theme:{
		extend:{
			// adding custom style example
			colors:{
				primary: '#FF4324';
				secondary: {
					100: '#ee3435',
					200: '#dd3332'
				}
			}
		}
	},
	variants:{},
	plugins:[]
}
```

### creating tailwind.config.js config file with default values populated

```
npx tailwindcss init --full
```

## 6. custom fonts

font-sans
font-serif
font-mono

### google font

- import the code given by google fonts into input.css

```js
@import url('...some url');

@tailwind base;
@tailwind components;
@tailwind utilities;
```

- add the name in the tailwind.config.js

```js
//tailwind.config.js
module.exports = {
  purge: [],
  theme: {
    extend: {
      //add custom font
      fontFamily: {
        body: ['Nunito'],
      },
    },
  },
  variants: {},
  plugins: [],
};
```

## 7. Flexbox / CSS Grid

### Flexbox

- make parent flex container (default is 'row')
- justify-start, justify-end, justify-center, justify-between, justify-around, justify-evently

## width/height

w-6
h-6

## alignment

- aligns children:
  items-center
  items-start
  items-end
  justify-center
  justify-start
  justify-end

## 8. responsive classes

- mobile goes from breakpoint small to larger, specifying responsive class changes from responsive class size and larger breakpoints
- classes trailing the responsive classes fall under that responsive size
- for every class that should fall under the responsive class, the responsive class should be declared

sm:
lg:
xl:

## 9. card

bg-white
rounded
overflow-hidden
shadow
shadow-xs,sm,md,lg,xl,2xl,inner,outline,none

### styling image width

- full width of image
- object-cover fixes distortion on image

w-full object-cover
max-w-full
min-w-full

## 10. badges

```html
<div
  class="bg-secondary-100 text-secondary-200 text-xs uppercase font-bold rounded-full p-2 absolute top-0 ml-2 mt-2"
></div>
```

## 11. reusable class style sets with @apply Directive

- create a class
- use @apply in css

```html
<div class="card"></div>
```

```css
.card {
  @apply bg-white rounded overflow-hidden shadow-md relative;
}
```

## 12. css Grids

grid grid-cols-1,2,3,4,5,6,7,8,9,10,11,12 gap-10

grid md:grid-cols-3
md:col-span-1
md:col-span-2

## 13. buttons

```css
.btn {
  @apply rounded-full py-2 px-3 uppercase text-xs font-bold cursor-pointer tracking-wider;
}
```

```html
<div class="btn border-primary md:border-2"></div>
```

## 14. icons

heroicons.dev

- add class to svg

```html
<svg
  class="w-6 h-6"
  fill="none"
  stroke="currentColor"
  viewBox="0 0 24 24"
  xmlns="http://www.w3.org/2000/svg"
>
  <path
    stroke-linecap="round"
    stroke-linejoin="round"
    stroke-width="2"
    d="M14.121 14.121L19 19m-7-7l7-7m-7 7l-2.879 2.879M12 12L9.121 9.121m0 5.758a3 3 0 10-4.243 4.243 3 3 0 004.243-4.243zm0-5.758a3 3 0 10-4.243-4.243 3 3 0 004.243 4.243z"
  ></path>
</svg>
```

## 15. hover effects

class="hover:text-gray-700 hover:text-white"
class="hover:shadow-lg"
class="hover:shadow-inner"

## 16./17. responsive nav

md:block
md:hidden

## 18. transitions

1. add class 'transition'
2. easing function: 'ease-linear', 'ease-in', 'ease-out', 'ease-in-out'
3. duration (ms): 'duration-500'

```html
class="transition ease-out duration-500"
```
