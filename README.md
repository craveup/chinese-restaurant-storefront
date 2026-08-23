# Crave.js - Xichuan Noodles Storefront Template

> [!WARNING]
> **Legacy visual reference only.** This repository pins the retired Storefront
> SDK 1.x browser-key contract. Do not use it as a production starter, expose a
> Crave API key in browser code, or use its one-click deployment flow. Build new
> integrations from the current [Storefront SDK guide](https://docs.craveup.com/getting-started/storefront-sdk)
> and treat this repository only as design and interaction reference material.

This Next.js 15 example demonstrates branded menu browsing, cart presentation,
and theme customization for a noodle-house concept.

## Tech Stack

- [Next.js 15 (App Router)](https://nextjs.org/)
- [React 19](https://react.dev/)
- [TypeScript](https://www.typescriptlang.org/)
- [Tailwind CSS](https://tailwindcss.com/) with design tokens
- [shadcn/ui](https://ui.shadcn.com/) + Radix UI primitives
- [CraveUp Storefront SDK](https://docs.craveup.com/)

## Key Features

- Dynamic menu, product, and location data fetched with `@tanstack/react-query`
- Cart provider that gracefully falls back to local state when APIs are unavailable
- Theme engine powered by JSON files for rapid brand swaps
- Location-focused hero and CTA flow tailored to restaurants and dark kitchens
- Mobile-first drawer, category navigation, and product dialogs
- shadcn/ui + Radix primitives for accessible dialogs, drawers, and forms
- Local visual study with `.env.example` containing public-only placeholders

## Demo

- Live storefront: [https://xichuan-noodles.order.page/](https://xichuan-noodles.order.page/)

Capture the following states and drop the assets into `public/screenshots/`:

| Hero (Light)                                     | Hero (Dark)                                    |
| ------------------------------------------------ | ---------------------------------------------- |
| ![Hero Light](public/screenshots/hero-light.png) | ![Hero Dark](public/screenshots/hero-dark.png) |

| Menu Grid                                      | Product Drawer                                           |
| ---------------------------------------------- | -------------------------------------------------------- |
| ![Menu Grid](public/screenshots/menu-grid.png) | ![Product Drawer](public/screenshots/product-drawer.png) |

| Cart & Recommendations                               | Menu Scroll GIF                                        |
| ---------------------------------------------------- | ------------------------------------------------------ |
| ![Cart Sidebar](public/screenshots/cart-sidebar.png) | ![Menu Scroll GIF](public/screenshots/menu-scroll.gif) |

## Getting Started

1. **Clone the template**
   ```bash
   git clone https://github.com/your-org/xichuan-noodles-template
   cd xichuan-noodles-template
   ```
2. **Install dependencies**
   ```bash
   npm install
   ```
3. **Create your env file** (details below)
4. **Run the dev server**
   ```bash
   npm run dev
   ```
   Visit `http://localhost:3000` to explore the storefront.

## Environment Variables

Environment variables live in `.env.local`. Start by copying the template file:

```bash
cp .env.example .env.local
```

Use only non-sensitive public values while studying the local UI:

- Do not add `NEXT_PUBLIC_CRAVEUP_API_KEY`; the legacy SDK 1.x integration is not supported for a new live build
- `NEXT_PUBLIC_LOCATION_ID` - optional location label for local UI study
- `NEXT_PUBLIC_ORG_SLUG` - optional, unlocks richer branding metadata
- `NEXT_PUBLIC_GOOGLE_MAPS_API_KEY` - optional, powers the embedded map module

## Scripts

| Command         | Description                          |
| --------------- | ------------------------------------ |
| `pnpm dev`   | Start the local development server   |
| `pnpm build` | Create an optimized production build |
| `pnpm start` | Serve the production build locally   |
| `pnpm lint`  | Run ESLint using the Next.js config  |

## Project Structure

```
.
|- public/
|  |- images/xichuan-noodles/      # Hero + menu imagery
|  |- themes/                      # JSON theme presets
|- src/
|  |- app/                         # App Router entry + sections
|  |- app/components/              # Hero, menu, cart, footer, etc.
|  |- app/providers/               # Cart + React Query providers
|  |- components/ui/               # Tailored shadcn/ui primitives
|  |- hooks/                       # Cart + theme hooks
|  |- lib/                         # Storefront client and helpers
|- README.md
```

## Customization Guide

1. **Branding and imagery** - Replace assets in `public/images/xichuan-noodles` with your photography.
2. **Theme presets** - Update or add JSON files inside `public/themes` to match your color system.
3. **Copy and layout** - Tweak hero, menu, and footer content under `src/app/components`.
4. **Menu data** - Study the legacy data flow locally; use the current Storefront SDK guide for a new live integration.
5. **UI primitives** - Extend buttons, drawers, and dialogs in `src/components/ui` if you need additional states.

## Deployment status

Do not deploy this legacy integration as a live ordering storefront. Reuse its
visual ideas in a new application built against the current Storefront API and
SDK contract instead.

## Support & Reference

- [CraveUp Docs](https://docs.craveup.com/)
- [Next.js Documentation](https://nextjs.org/docs)
- [Tailwind CSS Docs](https://tailwindcss.com/docs)
- [shadcn/ui Documentation](https://ui.shadcn.com/)
- [Radix UI Documentation](https://www.radix-ui.com/primitives/docs)

## Next Steps

1. Run the example locally without a Crave API key and inspect the design patterns.
2. Configure menu imagery, hero copy, and CTAs for your restaurant.
3. Add additional sections or pages in `src/app` if you need loyalty, catering, or reservations flows.

## License

Distributed under the MIT License. See `LICENSE` for details.
