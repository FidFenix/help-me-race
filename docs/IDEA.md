
# SIM-RACING APP

Create a web application that simulates a 3D real-tme training platform for sim racing and records metrics for the physics of every capex and sector of the track in the backend.
The web application allows to configure weather conditions described in weather conditions data and the web app accepts voice recognition by the user to move the car, speed up the car, press the pedal and increase gasoline.
1. Circuits:  
    Use Monza circuit and Monaco grand prix. and other circuit parameters defined by you.
2. Cars metrics using cars: Maclaren and Porsche.
    
    interface TelemetryFrame {
        timestamp: number;
        throttle: number;    // 0.0 - 1.0
        brake: number;       // 0.0 - 1.0
        steering: number;    // -1.0 to 1.0
        speed: number;       // km/h
        gear: number;
        rpm: number;
        lapTime: number;     // milliseconds
        lapNumber: number;
        normalizedPosition: number; // 0.0 - 1.0 (track position)
    }

3. Weather conditions: dry, sunny, cloudy, cold, snow and rainy, presure level.


## Features:
1.Real-time telemetry: live streaming of throttle, brake, and steering inputs, rpm.
2. Lap analysis: automatic lap detection and archival.
3. Ai coaching: GPT-4 powered suggestions for improving lap times.
4. Interactive Chat: ask questions about driving technique using voice.
5. Session management: organize qnd review multiple practice sessions.
6. Demo mode: try the app with pre-coded telemtry data.

## AI analysis
The AI analysis uses Gemini 3.0 with specialized racing coach prompt and gives the user the expert feedback and reasoning behind the wrong decisions made by the user. It analyzes:
- Baking poinst: Early/late braking detection.
- Throttle applicaton: Smoothness and timing.
- Steering input: Smoothness and corner entry/exit technique.
- Corner-specific advice: Turn-by-turn suggestions.
- Deep lap analysis and corner-specific suggestions.

## Architecture:
- Frontend: streamlite on the frontend that shows the car and circuit in 3D and processess speech recognition.
- Charts: recharts.
- Backend: Next.js API Routes, node.js
- Database: sqlite with prisma ORM to record data (telemetry)
- Real-time: web sockets with ws library.
- AI: Gemini 3.0
- Icons: lucide react.

## Tools
- Python 3.10
