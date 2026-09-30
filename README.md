# Cont.

> A web platform showcasing the cultural richness of countries around the world through interactive, visually engaging content.

**Cont.** (Everyday Culture) is an ASP.NET Core Razor Pages application that educates and engages visitors with detailed insights into global traditions, festivals, food, architecture, and customs. It combines static editorial content with multimedia and a contact pipeline to create an immersive cultural discovery experience.

---

## Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [Configuration](#configuration)
- [Development](#development)
- [Roadmap](#roadmap)
- [Contributing](#contributing)
- [License](#license)
- [Author](#author)

---

## Features

- Interactive homepage with cultural highlights and calls to action
- Dedicated country pages (Egypt, China, France, Canada, USA, Saudi Arabia)
- A cultures index that links to every country
- Responsive design for desktop, tablet, and mobile
- User authentication UI (Login and Registration)
- Contact form with email delivery
- Multimedia-rich content (images, icons, custom CSS per page)
- Reusable layout with shared navigation and footer

---

## Tech Stack

| Layer | Technology |
|-------|------------|
| Framework | ASP.NET Core 8 (`net8.0`) |
| UI | Razor Pages, HTML5, CSS3, JavaScript |
| Data | Entity Framework Core 9 (`Microsoft.EntityFrameworkCore.SqlServer`) |
| Serialization | `System.Text.Json` |
| Scaffolding | `Microsoft.VisualStudio.Web.CodeGeneration.Design` |
| Styling | Bootstrap (from `lib/`) + custom per-page CSS |
| Icons | Font Awesome 5.15.3 |
| Contact | Web3Forms API |
| Tooling | Visual Studio 2022 (v17), .NET SDK 8.0 |

---

## Project Structure

```
Cont.-main/
├── Cont.sln                     # Visual Studio solution
├── README.md
└── Cont/
    ├── Cont.csproj              # Project file (net8.0)
    ├── Program.cs               # App entry point and middleware pipeline
    ├── appsettings.json         # App configuration
    ├── appsettings.Development.json
    ├── Pages/
    │   ├── Index.cshtml         # Home page
    │   ├── About.cshtml         # About page
    │   ├── Cultures.cshtml      # Culture index
    │   ├── Contact.cshtml       # Contact form
    │   ├── Login.cshtml         # Login page
    │   ├── Register.cshtml      # Registration page
    │   ├── Egypt.cshtml         # Country page
    │   ├── China.cshtml         # Country page
    │   ├── France.cshtml        # Country page
    │   ├── Canada.cshtml        # Country page
    │   ├── Usa.cshtml           # Country page
    │   ├── Saudi Arabia.cshtml  # Country page
    │   └── Shared/
    │       ├── _Layout.cshtml   # Shared navigation and footer
    │       ├── _Layout.cshtml.css
    │       └── _ValidationScriptsPartial.cshtml
    └── wwwroot/                 # Static assets (CSS, JS, images, icons)
```

---

## Prerequisites

- [.NET SDK 8.0](https://dotnet.microsoft.com/download/dotnet/8.0) or newer
- SQL Server (required if you wire up the Entity Framework Core data layer)
- A code editor such as Visual Studio 2022 or VS Code

---

## Getting Started

1. **Clone the repository**

   ```bash
   git clone <repository-url>
   cd "Cont.-main"
   ```

2. **Restore dependencies**

   ```bash
   dotnet restore
   ```

3. **Run the application**

   ```bash
   dotnet run --project Cont
   ```

   The app starts on the HTTPS launch profile. Open the URL printed in the console (typically `https://localhost:7xxx`).

---

## Usage

- Navigate to `/` for the homepage.
- Use the top navigation to reach **About**, **Cultures**, and **Contact**.
- From **Cultures**, open individual country pages.
- Use **Login/Register** for the authentication flows.
- Submit the **Contact** form to send a message via Web3Forms.

---

## Configuration

Settings live in `Cont/appsettings.json`:

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft.AspNetCore": "Warning"
    }
  },
  "AllowedHosts": "*",
  "ConnectionStrings": {
  }
}
```

- Add your SQL Server connection string under `ConnectionStrings` when enabling EF Core.
- The contact form posts to Web3Forms; replace the `access_key` in `Cont/Pages/Contact.cshtml` with your own key for production use.

---

## Development

Build and run locally:

```bash
# Build
dotnet build Cont/Cont.csproj

# Run with hot reload
dotnet watch --project Cont run
```

The middleware pipeline is defined in `Cont/Program.cs`: Razor Pages, HTTPS redirection, static files, routing, and authorization.

---

## Roadmap

- Wire up real authentication backed by ASP.NET Core Identity
- Persist users and content with EF Core + SQL Server
- Add more country pages
- Add search and filtering on the cultures index
- Introduce automated tests (unit and integration)

---

## Contributing

1. Fork the repository and create a feature branch.
2. Keep changes focused and match the existing Razor Pages conventions.
3. Test locally with `dotnet run` before opening a pull request.
4. Submit a pull request with a clear description of your changes.

---

## License

No license has been specified for this project. Contact the author before reusing the code.

---

## Author

**Dahy**

- Designed and developed Cont. / Everyday Culture
- Footer: `Copyright © 2024. Designed By Dahy`
