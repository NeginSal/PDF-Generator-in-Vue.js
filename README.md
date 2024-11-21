# PDF Generator in Vue3

This project generates a PDF document using the `@html2pdf.js` package. It organizes images into rows and pages, includes a header (just in first page) & footer with company details, and adds a signature page at the end.

## Features
- Report Layout:

    The report consists of three main sections:

     - Text Content Page
     - Image Pages: Displays images in a structured grid format, with one or two images per row.
     - Signature Page: Displays a signature, logo, and related information at the bottom of the last page.

- Dynamic Image Layout:

    Each row in the report can contain one or two images, resized to fit uniformly.
    Handles a large number of images (e.g., more than 10).
    Distributes images across multiple pages, with a maximum of 4 rows per page.
  
- PDF Generation:

    A "Generate PDF" button exports the report as a PDF document.
    Ensures the PDF matches the preview, with images and signature text properly placed.
    Optimizes the PDF size by adjusting image quality.

## Technologies Used

   - `Vue.js`: Frontend framework for managing the UI and reactivity.
   - `HTML2PDF.js`: Library for converting HTML content to PDF.
   - `Bootstrap 5`: For styling and responsive layouts.

## How to Start

1. Clone the repository & then go to projcet directory

2. Install dependencies:  `npm install`

3. Start the development server:  `npm run dev`

The app will be available at http://localhost:5173.

## What This Project Does

Takes an array of images as input.
Generates a PDF document with:
  - A header just in first page.
  - Images arranged in rows of two per page.
  - A footer displaying page numbers, company name, and logo.
  - A signature page at the end.
        
## Dependencies

   `@html2pdf.js`: For rendering PDF documents.
