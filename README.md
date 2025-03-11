# radar-self-enrolment-definitions
Definition files to define the contents and behaviour of various parts of self enrolment portal such as study information, eligibility, consent and more.

The definitions are used by the self enrolment portal to render the [UI](https://github.com/RADAR-base/radar-self-enrolment-ui) and validate the user input. The definitions are written in JSON format and are loaded by the portal at runtime.


## protocol.json


## landingpage.json

This JSON file is a list of 'blocks'. Each block renders a specific type of content on the page, for example a 'hero block', a 'video block', or a 'markdown block'.
Each block is a key-value map with general block keys and content-specific keys.

All blocks have the following parameters:

| Param     | required | value | description |
|-----------|----------|---------|-----------|
| blockType | required | ("markdown", "text", "hero", or "video") | The type of block |
| noCard    | optional | boolean | Whether to render the content in a card |
| blockPadding | optional | number | The padding around the contents of the block |
| blockBackground | optional | string | The background colour behind the block (Not the card) |
| title | optional | string | The title heading to display |
| subtitle | optional | string | The subtitle of the block |

### Text block
A simple block to display plain text

| Param     | required | value   | description |
|-----------|----------|---------|-------------|
| content   | required | string  | The string to display in the block

### Markdown block
A block which will display markdown and HTML content while keeping the study CSS/material theme

| Param     | required | value   | description |
|-----------|----------|---------|-------------|
| content   | required | string  | A string containing markdown/html content |

### Hero block
A 'hero' banner with up to two call to action buttons

| Param     | required | value   | description |
|-----------|----------|---------|-------------|
| heroImage | true | {src: string, altText: string} | An object containing the image src path and an alt string to display |
| cta | optional | {text: string, href: string} | The call-to-action button text and link |
| cta2 | optional | {text: string, href: string} | A second call-to-action button |

### Video block
A block to display a video in the `<video>` tag


| Param     | required | value   | description |
|-----------|----------|---------|-------------|
| video     | required | {src: string, type: string, params: {}} | The source, video type (e.g. "video/mp4"), and parameters to include (e.g. autoPlay, muted) |

## Scripts

The `scripts` directory contains scripts to pull definitions from external systems such as REDCap or local CSV files.

