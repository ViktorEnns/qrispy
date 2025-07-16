# Qrispy - QR Code Generator

[**Qrispy**](https://studio--swiftqr-577rq.us-central1.hosted.app/) is a sleek, modern, and mobile-first web app for instantly generating QR codes for website links, SEPA banking details, and physical addresses. It features a minimalist interface, a sophisticated dark mode, and a smooth, intuitive user experience. The application leverages generative AI to suggest valid web addresses if a user's input appears to be an invalid URL.

## Screenshots

<div align="center">
  <img src="https://github.com/user-attachments/assets/4ae3880e-3c0a-463e-b22a-471b25eed73a" alt="Qrispy Screenshot URL" width="32%" style="vertical-align: top;">
  <img src="https://github.com/user-attachments/assets/9f3f6690-3af6-407e-9f5e-6334d0213c62" alt="Qrispy Banking Details Mode" width="32%" style="vertical-align: top;">
  <img src="https://github.com/user-attachments/assets/dad16ef7-99fa-46ad-abd9-e84afd689518" alt="Qrispy Screenshot Address Mode" width="32%" style="vertical-align: top;">
  <img src="https://github.com/user-attachments/assets/dad16ef7-99fa-46ad-abd9-e84afd689518" alt="Qrispy Screenshot Address Mode" width="32%" style="vertical-align: top;">
</div>

## ✨ Features

-   **Multiple QR Modes:** Generate QR codes for URLs, SEPA banking transfers, or Google Maps addresses.
-   **AI-Powered Suggestions:** If you enter an invalid URL, the app uses AI to suggest potential correct web addresses.
-   **AI Address Parsing:** Automatically parse a full address string into structured fields (street, city, zip, etc.) to generate a map link.
-   **Instant Previews:** See your QR code generated in real-time.
-   **High-Quality Downloads:** Download a crisp, scalable SVG of your QR code.
-   **Copy to Clipboard:** Easily copy the QR code image to your clipboard for quick use.
-   **Responsive Design:** A beautiful and functional interface on both desktop and mobile devices.
-   **Light & Dark Modes:** A stunning theme that adapts to your system preference.

## 🚀 Live Demo

[*Qrispy - QR Code Generator*](https://studio--swiftqr-577rq.us-central1.hosted.app/)

## 🛠️ Tech Stack

-   **Framework:** [Next.js](https://nextjs.org/) (with React)
-   **Language:** [TypeScript](https://www.typescriptlang.org/)
-   **Styling:** [Tailwind CSS](https://tailwindcss.com/)
-   **UI Components:** [Shadcn/UI](https://ui.shadcn.com/)
-   **AI/Backend:** [Genkit (Firebase AI)](https://firebase.google.com/docs/genkit)
-   **Deployment:** [Firebase App Hosting](https://firebase.google.com/docs/hosting)
-   **Forms:** [React Hook Form](https://react-hook-form.com/) & [Zod](https://zod.dev/) for validation
-   **Icons:** [Lucide React](https://lucide.dev/)
-   **Version Control** Github

## 📂 Project Structure

Here is a high-level overview of the most important files and folders in the Qrispy project:

```
/
├── src/
│   ├── app/
│   │   ├── page.tsx          # The main (and only) page component, contains all UI and state logic.
│   │   ├── layout.tsx        # The root layout for the app (sets up fonts, theme provider).
│   │   └── globals.css       # Global styles and Tailwind/Shadcn theme variables.
│   │
│   ├── ai/
│   │   ├── flows/
│   │   │   ├── web-address-suggestion.ts  # Genkit flow for URL suggestions.
│   │   │   └── parse-address-flow.ts      # Genkit flow for parsing addresses.
│   │   └── genkit.ts         # Genkit initialization and configuration.
│   │
│   ├── components/
│   │   ├── ui/               # Reusable UI components from Shadcn (Button, Card, etc.).
│   │   ├── theme-provider.tsx # Manages the light/dark theme state.
│   │   └── theme-toggle.tsx  # The UI button for switching themes.
│   │
│   └── lib/
│       └── utils.ts          # Utility functions, including cn() for merging CSS classes.
│
├── public/                   # Static assets (images, fonts, etc.).
│
├── tailwind.config.ts        # Configuration file for Tailwind CSS.
├── next.config.ts            # Configuration file for Next.js.
└── package.json              # Project dependencies and scripts.
```

## Local Development

### Prerequisites

-   [Node.js](https://nodejs.org/) (v20.x or later)
-   [npm](https://www.npmjs.com/) or another package manager

### Installation & Setup

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/viktorenns/qrispy.git
    cd qrispy
    ```

2.  **Install dependencies:**
    ```bash
    npm install
    ```

3.  **Set up environment variables:**
    Create a `.env` file in the root of the project and add your Google AI API key. You can get one from [Google AI Studio](https://aistudio.google.com/app/apikey).
    ```
    GOOGLE_API_KEY=your_api_key_here
    ```

4.  **Run the development server:**
    The application runs in two parts: the Next.js frontend and the Genkit AI backend. You'll need to run both in separate terminal windows.

    *   **Terminal 1 (Next.js App):**
        ```bash
        npm run dev
        ```
        This will start the web app on [http://localhost:9002](http://localhost:9002).

    *   **Terminal 2 (Genkit AI Flows):**
        ```bash
        npm run genkit:watch
        ```
        This starts the local Genkit development server, which your Next.js app will call for AI features.

## ⚖️ License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
