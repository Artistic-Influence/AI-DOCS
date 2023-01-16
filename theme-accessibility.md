## Accessibility Tests
- [ ] [Use Theme Check to identify performance issues](https://shopify.dev/themes/best-practices/performance#use-theme-check-to-identify-performance-issues)
- [ ] [Check Speed Score and Report](https://help.shopify.com/en/manual/online-store/store-speed/speed-report?shpxid=b9695b10-4923-45C7-CD42-AD47164CB5D5)
- [ ] [Run Lighthouse audit using Shopify data](https://shopify.dev/themes/best-practices/performance#run-a-lighthouse-audit-using-shopify-data)
- [ ] [View managed store performance](https://help.shopify.com/en/partners/dashboard/managing-stores/store-performance?shpxid=b9695b10-4923-45C7-CD42-AD47164CB5D5)

# Main Checklist

## Keyboard Support 
- [ ] The focus indicator is visible and consistent on active elements. When navigating with either the mouse or the keyboard, the focus indicator is apparent on active elements.
- [ ] The keyboard focus order must match the DOM order. Focus should move from top to bottom and left to right.
- [ ] The focus style is visible on the desktop when using a keyboard.
- [ ] Your theme doesn't rely on a mouse hover action to be visible or accessible.
- [ ] The Tab key and Shift + Tab keys can be used to navigate your theme.
- [ ] No sudden changes of context when a part of your theme receives focus. For example, when navigating with a keyboard, focus must not switch to something else when a control receives focus.

## Gesture Support
- [ ] Zooming gestures, for example pinch to zoom, are always available.
- [ ] Any functionality that requires several fingers or complex gestures, for example navigating 3D models, should be available with a single tap or click.

## Page Structure
- [ ] Your theme must be built using valid HTML. You can validate the generated HTML using the [W3 HTML checker](https://validator.w3.org/nu/#textarea).

### Global
- [ ] The page lang attribute is set on the html element to help screen readers pronounce content in the correct accent and dialect.
- [ ] The viewport zoom is enabled. Your theme shouldn't use the maximum-scale and user-scalable=”no” attributes.
- [ ] Skip link is available and visible when focused to provide quick access to page content by skipping past common content such as headers. Your themes should include tabindex="-1" on the container for the main content to receive focus.
- [ ] The content flow is linear. Your themes uses no tabindex attributes values other than 0 or -1 and no autofocus attribute. Positive tabindex values in use and autofocus take the power away from the user by forcing a specific focus order. Let the user discover page content organically.

### Headings
- [ ] The HTML heading elements use heading markup. Your theme uses heading tags (h1 to h6) to communicate the organization of the content on the page.
- [ ] The heading tags are used in sequence. Your theme shouldn't use headings for design but rather to set the logical order of content on the page.
- [ ] The h1 element is used to identify the main topic of a page.

### Navigation
- [ ] The navigation areas are wrapped with the nav HTML element.
- [ ] aria-current is used to communicate the current page when traversing links.
- [ ] role=”menu” or role=”menuitem” aren't used for navigation.

### Drop-down menu navigation
- [ ] `aria-expanded` is used to communicate the state of collapsible navigation.
- [ ] `aria-controls` is used to convey to assistive technology that there's a visually-hidden container that the drop-down menu controls.
- [ ] aria-current is used to communicate the current location or page when traversing navigation items.
- [ ] Enter and Space keys are supported to open the drop-down menu. Your theme must keep focus on the launcher control. The Tab key moves focus to the first item in the drop-down menu.
- [ ] The Esc key is supported to collapse the drop-down menu and return focus to the launcher control.

### Product information
- [ ] Product images include descriptive alt text.
- [ ] Sale and regular prices are marked differently, both visually and by using markup for screen readers. Your theme must use visually-hidden text to help discern the regular price from the sales price.
- [ ] If your theme dynamically changes a product price and availability when different variants are selected, then the changes must also be communicated to screen readers.
- [ ] aria-live is used to communicate dynamic changes in the UI.

### Controls
- [ ] The a element is used for links. Your theme should use links for navigation, loading a new page, or shifting keyboard focus from one element to another.
- [ ] The button element is used for on-screen actions such as launching a modal window and sorting a data table.
- [ ] The destination of your link must be clear from the text alone.
- [ ] Links that open a new window include a warning. Your theme should include a visual icon with alternative text to help screen reader and sighted, keyboard-only users understand that clicking the link opens a new window.

### Tables
- [ ] The table element is used for tables data.
- [ ] The caption element is used to help assistive technology identify that a table is being read.
- [ ] The th element is used for headers with scope attributes.
- [ ] The scope="col" element is used for column headers, and scope="row" for row headers.

### Forms
- [ ] All form fields include a label. Fields can use aria-label, the .visuallyhidden element, floating labels, or a visible label to label forms. Form inputs and controls have names that clearly state their purpose.
- [ ] Form inputs have labels with for attributes, including form labels in the theme settings.
- [ ] Required inputs have the required attribute.
- [ ] Fields use the autocomplete attribute. Auto-complete helps people fill in form fields by using the data stored in their browser.

### Form errors
- [ ] Focus is placed on the feedback message. Any errors returned as a result of completing or submitting a form are communicated to screen readers where possible and as soon as possible.
- [ ] Error messages are clear and descriptive.
- [ ] The `aria-describedby` attribute is applied to `input` elements which reference the error text container.
- [ ] Notifications, error messages, success messages are announced aloud. Critical information is announced by screen readers using `aria-live`.

### Media
Media can be distracting, disruptive, or unexpected. All the media in your theme should adhere to the following best practices:

- [ ] Media doesn't autoplay.
- [ ] Media controls are marked up using native HTML elements. Make sure your theme has a toggle state for buttons and range input for sliders.
- [ ] Media can be paused using the Space key.

### Images and icons
- [ ] All img elements must have an alt attribute. Without an alt attribute, screen readers announce the name and path of the image file.
- [ ] Product or content images feature alt text which describes the image for screen reader users.
- [ ] Decorative images use empty values for alt attributes. Use <img src="…" alt=""> to hide images and icons from screen readers.

### Video
- [ ] Closed captions are available.
- [ ] Descriptive audio is available.
- [ ] If an auto-playing video is required, including videos in slideshows, the sound is muted.
- [ ] Videos with audio aren't visually obstructed.
- [ ] The Space key can be used to pause and play the video.

### Audio
- [ ] Transcripts are available.
- [ ] Auto-playing audio can be paused.

## Color and contrast
When you add colors to your theme, make sure that all of your text is accessible to merchants and customers who are colorblind or have other visual impairments. These merchants and customers rely on adequate color contrast to visually differentiate one thing from another.

You can use an online contrast ratio tool to check the contrast of the different parts of your store. The content in your theme should adhere to the following best practices:

- [ ] Text that is less than 24 pixels (regular) or 18.5 pixels (bold) has a contrast ratio of 4.5:1 against its background.
- [ ] Text that is 24 pixels (regular), or 18.5 pixels (bold) and larger, has a contrast ratio of 3.0:1 against its background.
- [ ] Icons have a contrast ratio of 3.0:1 against their background.
- [ ] Input element borders have a contrast ratio of 3.0:1 against their background.
- [ ] Color isn't the only indicator used to convey information.

## Dynamic components
Dynamic components such as slideshows, predictive search, modal windows, and tabs can be complex and difficult to navigate. Use elements that can be interpreted by screen readers, provide context, and include keyboard functionality.

### Drawers and modals
- [ ] When a drawer or modal is opened, focus is moved to the element that labels the drawer or modal.
- [ ] Navigating with the keyboard stays within the open drawer or modal.
- [ ] The Esc key is supported to close drawers and modals, and returns keyboard focus to the launcher element.
- [ ] The role used to identify modals is `dialog`.

### Slideshows
- [ ] Content that plays automatically in a slideshow can be paused or stopped.
- [ ] Content in a slideshow can be accessed through next and previous buttons.

## Touch screen and mobile devices
The main consideration for touch screens and mobile devices is to make sure that the merchant or customer can easily change the orientation and tap the target to navigate the content.

Touch targets on primary controls and links need to be at least 44 by 44 pixels. Primary touch targets include controls and links such as:

- [ ] Main menu links (regardless if first or third level)
- [ ] Submit buttons for any forms, such as contact forms, comment forms, search, and add to cart,
- [ ] Menu buttons for carts and for hamburger menus
- [ ] Close buttons for modals
- [ ] Product page variants and options, such as color, size, and quantity.
