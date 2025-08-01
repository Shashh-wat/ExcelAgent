🎙️ Excel Interview System - Complete Production Version


A sophisticated AI-powered Excel skills assessment platform with voice integration, real-time evaluation, and comprehensive session management.


🚀 Features


🎯 Core Interview System


AI-Powered Evaluation - Claude 3.5 Sonnet analyzes responses with detailed feedback
Voice Integration - Text-to-speech questions and voice recognition for responses
Session Management - Complete interview orchestration with progress tracking
File Analysis - Upload and analyze Excel files with comprehensive parsing
Real-time Scoring - Instant evaluation with detailed strengths and improvement areas


🎙️ Voice Capabilities


Universal Browser Support - Works in Chrome, Safari, Firefox, Edge
Text-to-Speech - Questions spoken using Murf AI voice synthesis
Speech Recognition - Voice responses automatically transcribed
Audio Feedback - Scores and feedback delivered via voice
Fallback Modes - Graceful degradation when voice features unavailable


📊 Advanced Assessment Features


10+ Excel Questions - Covering formulas, pivot tables, error handling, formatting
Skill Categories - Organized by Excel competency areas
Difficulty Levels - Beginner, intermediate, and advanced questions
Performance Analytics - Detailed reporting and progress tracking
Caching System - Optimized evaluation with Redis and memory caching


🏗️ System Architecture


Backend Components


interview_orchestrator.py - Main orchestration engine with session management
evaluation_engine.py - Claude-powered evaluation with Excel file analysis
fixed_murf_client.py - Production-grade Murf API integration for voice synthesis
main_production.py - FastAPI production server with all endpoints


Frontend


universal_voice_interview.html - Universal web interface with voice capabilities


Configuration


requirements.txt - Python dependencies
Procfile - Deployment configuration


🚀 Quick Deploy


1. Environment Variables


Set these in your deployment platform:


ANTHROPIC_API_KEY=your_anthropic_key_here
MURF_API_KEY=your_murf_key_here
ENVIRONMENT=production



2. Deploy on Render


Connect this repository to Render
Build Command: pip install -r requirements.txt
Start Command: uvicorn main_production:app --host=0.0.0.0 --port=$PORT
Health Check Path: /health


3. Deploy on Railway


railway login
railway init
railway up
railway variables set ANTHROPIC_API_KEY=your_key
railway variables set MURF_API_KEY=your_key



🔧 Local Development


Prerequisites


Python 3.11+
Anthropic API key
Murf API key (optional for voice features)


Setup


git clone https://github.com/Shashh-wat/excel-interview-complete.git
cd excel-interview-complete
pip install -r requirements.txt

# Set environment variables
export ANTHROPIC_API_KEY=your_key
export MURF_API_KEY=your_key

# Run development server
python main_production.py



Open universal_voice_interview.html in your browser and update the API_BASE URL to http://localhost:8000.


📡 API Endpoints


Interview Management


POST /api/interview/start - Start new interview session
POST /api/interview/{session_id}/respond - Submit response
GET /api/interview/{session_id}/status - Get session status
GET /api/interview/{session_id}/report - Generate detailed report


Voice Features


POST /api/voice/synthesize - Convert text to speech
POST /api/voice/test - Test voice system


System Monitoring


GET /health - Health check endpoint
GET /api/system/stats - System performance statistics
GET /api/sessions - List all active sessions


🎯 Interview Flow


Candidate starts interview with name and preferences
AI presents Excel questions via text and/or voice
Candidate responds via typing or voice recognition
Claude evaluates response with detailed scoring and feedback
System provides feedback and moves to next question
Final report generated with comprehensive analysis


🧠 Evaluation Engine


The system uses Claude 3.5 Sonnet to evaluate responses across multiple dimensions:


Scoring Criteria (0-5 scale)


Technical Accuracy - Correctness of Excel knowledge
Depth of Understanding - Quality of explanations
Practical Application - Use of examples and real-world scenarios


Feedback Components


Strengths Identified - What the candidate did well
Areas for Improvement - Specific suggestions for growth
Keywords Found - Technical terms used correctly
Mistakes Detected - Common errors flagged


🎙️ Voice System


Text-to-Speech


Murf AI Integration - Professional voice synthesis
Multiple Voices - Various accents and speaking styles
Audio Caching - Optimized performance with file caching
Fallback Support - Browser TTS when Murf unavailable


Speech Recognition


Web Speech API - Browser-native voice recognition
Chrome/Edge Optimized - Best performance on Chromium browsers
Automatic Transcription - Voice converted to text seamlessly
Error Handling - Graceful fallbacks for unsupported browsers


📊 System Statistics


The system tracks comprehensive metrics:


Interview completion rates
Average scores by skill category
Response time analytics
Voice interaction statistics
API performance monitoring


🔧 Configuration Options


Feature Flags


ENABLE_VOICE - Enable/disable voice features
ENABLE_FILE_UPLOAD - Enable/disable Excel file uploads
ENABLE_AI_EVALUATION - Use Claude vs fallback evaluation


Performance Tuning


CACHE_TTL_HOURS - How long to cache evaluations
MAX_FILE_SIZE - Maximum Excel file upload size
EVALUATION_TIMEOUT - Claude API timeout settings


🛠️ Troubleshooting


Common Issues


Voice Not Working:


Check browser compatibility (Chrome/Edge recommended)
Verify microphone permissions granted
Ensure MURF_API_KEY is set correctly


Evaluation Errors:


Verify ANTHROPIC_API_KEY is valid
Check API rate limits
Review logs for specific error messages


Deployment Issues:


Ensure all environment variables are set
Check build logs for dependency conflicts
Verify health check endpoint returns 200


Debug Endpoints


GET /debug - Comprehensive system information
GET /api/system/stats - Performance metrics
GET /health - Component health status


📈 Performance


Optimizations


Evaluation Caching - Responses cached for 24 hours
Audio File Caching - TTS results stored locally
Async Processing - Non-blocking interview operations
Memory Management - Automatic cleanup of old sessions


Scalability


Stateless Design - Can run multiple instances
Redis Support - Distributed caching capability
Health Monitoring - Built-in performance tracking
Graceful Degradation - System continues operating when components fail


📄 License


This project is proprietary software for Excel skills assessment.


🤝 Support


For technical support or deployment assistance, check the health endpoints and system logs for diagnostic information.



🎉 Ready to assess Excel skills with AI-powered precision!
