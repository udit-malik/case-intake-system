# Tavrn AI Case Intake
An AI-powered case intake system that automates the processing of personal injury cases from audio recordings to final decisions. 

## Summary
This system takes audio recordings of client interviews and automatically:
1. Transcribes the audio using Deepgram
2. Extracts structured case data using OpenAI GPT-4
3. Scores the case and makes a decision
Perfect for law firms, insurance companies, or any organization that needs to process large volumes of case intake interviews efficiently.

## Key Features
### Smart Case Processing
- Drag-and-drop audio file uploads with validation
- High-accuracy speech-to-text using Deepgram
- Automatically extracts client details, incident information, and case facts
- Sophisticated scoring algorithm that evaluates case strength
- AI-powered Accept/Review/Decline recommendations

### Case Management
- Dashboard: Overview of all cases with status tracking
- Case Pipeline: Visual progress through Upload → Transcribe → Extract → Score → Submit
- Intake Forms: Clean, user-friendly forms for manual data entry and corrections
- Search & Filter: Find cases by status, client name, or decision type

### AI
- Deterministic processing: Consistent results using fixed seeds and temperature settings
- Smart caching: Process-wide memoization to avoid redundant AI calls
- Feature extraction: Combines LLM and heuristic approaches for robust data extraction
- Scoring algorithm: Multi-factor scoring system with case-type specific profiles

## Setup and Usage
1. **Clone and Install**
   ```bash
   git clone <repository-url>
   cd case-intake
   npm install
   ```

2. **Environment Setup**
   ```bash
   cp .env.example .env.local
   ```
   
   Fill in your environment variables:
   ```env
   # Database
   DATABASE_URL="postgresql://username:password@localhost:5432/case_intake"
   
   # Authentication
   AUTH_SECRET="your-auth-secret-here"
   
   # AI Services
   OPENAI_API_KEY="your-openai-key"
   DEEPGRAM_API_KEY="your-deepgram-key"
   
   # File Uploads
   UPLOADTHING_SECRET="your-uploadthing-secret"
   UPLOADTHING_APP_ID="your-uploadthing-app-id"
   ```

3. **Database Setup**
   ```bash
   npx prisma migrate dev
   npx prisma generate
   ```

4. **Start Development Server**
   ```bash
   npm run dev
   ```

5. **Open in Browser**
   Navigate to `http://localhost:3000`

### Available Scripts
- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run start` - Start production server
- `npm run lint` - Run ESLint
- `npm run format` - Format code with Prettier
- `npm run test` - Run test suite
