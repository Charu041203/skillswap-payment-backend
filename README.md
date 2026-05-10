# SkillSwap Backend

A backend system for a skill-sharing platform where users can exchange 
services using cash and credits.

## Tech Stack
- **Runtime**: Node.js
- **Framework**: Express.js
- **Database**: PostgreSQL
- **ORM**: Prisma v7
- **Payment Gateway**: Razorpay
- **Background Jobs**: node-cron

## Features
- 💳 Wallet System (Cash + Credits)
- 💰 Hybrid Payment Logic (Credits first, then Cash)
- 🔐 Razorpay Payment Integration
- 📊 Commission Logic (5-8% on cash payments)
- 🔄 Refund System
- ⏰ Background Jobs (Trust Score + Fraud Detection)
- 🔒 Webhook Verification

## API Endpoints

### Wallet
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | /api/wallet/balance/:userId | Get wallet balance |
| POST | /api/wallet/add-cash | Add cash to wallet |
| POST | /api/wallet/add-credits | Add credits to wallet |
| POST | /api/wallet/pay | Hybrid payment |

### Payments
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | /api/payments/create-order | Create Razorpay order |
| POST | /api/payments/verify | Verify payment |
| POST | /api/payments/refund | Refund payment |
| POST | /api/payments/webhook | Razorpay webhook |

## Setup

1. Clone the repository
2. Install dependencies
```bash
   npm install
```
3. Create `.env` file
```env
   PORT=5000
   DATABASE_URL="postgresql://postgres:YOUR_PASSWORD@localhost:5432/skillswap"
   RAZORPAY_KEY=your_razorpay_key
   RAZORPAY_SECRET=your_razorpay_secret
```
4. Run migrations
```bash
   npx prisma migrate dev
```
5. Start the server
```bash
   npm run dev
```
