# power-cost-tracker
A resilient, offline-first hybrid utility tracking PWA built with React, TypeScript, and Supabase. Enforces strict relational data integrity for SME cost management during network volatility.

##  Architecture Overview

This project is built using a **Hybrid Architecture** designed for absolute data survival and zero mathematical drift over unstable network connections:

* **Client-Side (Layered / Offline-First):** Built with **React** and **TypeScript** wrapped in **Capacitor**. It uses a local-first storage paradigm via **IndexedDB (Dexie.js & PouchDB)**. The UI interacts exclusively with a local repository layer, guaranteeing sub-millisecond responsiveness and complete operational durability during connectivity blackouts.
* **Backend (Serverless / Feature-Based):** Hosted on **Supabase**. Database operations are controlled using declarative PostgreSQL migrations, leveraging **Row Level Security (RLS)** to enforce strict multi-tenant isolation directly at the database layer. 
* **Asynchronous Communications Tier:** Extends operational reach via stateless **Supabase Edge Functions** serving as secure webhooks for the **WhatsApp Business API**, enabling merchants to seamlessly log operational metrics via conversational text.

##   Core Tech Stack

* **Frontend:** React, TypeScript, Capacitor, Dexie.js, PouchDB
* **Backend & Database:** Supabase, PostgreSQL, Deno (Edge Functions)
* **Security:** Cryptographically signed JWTs + Postgres RLS Policies
