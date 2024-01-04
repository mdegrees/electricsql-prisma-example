## Electric with Prisma example

1. Run the Electric backend
   `cd backend && docker compose up`
2. Migrate DB and enable Electric

   1. `npx prisma migrate dev --create-only`
   2. open prisma/migrations/[folder-name-of-your-first-migration]/migration.sql
   3. append `ALTER TABLE "Todo" ENABLE ELECTRIC; ALTER TABLE "User" ENABLE ELECTRIC;`
   4. `npx prisma migrate dev`

3. Generate Electric client
   `npx electric-sql generate --service http://localhost:5133 --proxy postgresql://prisma:proxy_password@localhost:65432/electric`
