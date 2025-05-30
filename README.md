<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>LiveScanAI - Real-time YouTube Stream Monitoring & AI Bot Detection</title>
</head>
<body>
    <h1>LiveScanAI</h1>
    <p><strong>Highlights:</strong> Real-time monitoring + AI detection</p>
    <h2>Overview</h2>
    <p>
        LiveScanAI is a Node.js application that monitors YouTube live streams in real-time,
        analyzing chat activity to estimate the number of real viewers versus bot viewers.
        It uses YouTube's Data API v3 to fetch live stream stats and live chat messages, then
        applies heuristics and AI-like phrase detection to identify suspicious chat behavior.
    </p>
    <p><em>Note: The AI detection part is still in beta.</em></p>
    <h2>Important</h2>
    <p><strong>You need a valid YouTube Data API v3 key to use this tool.</strong> Obtain one from the <a href="https://console.developers.google.com/apis/library/youtube.googleapis.com" target="_blank" rel="noopener noreferrer">Google Cloud Console - YouTube Data API v3</a> and set it in the <code>API_KEY</code> constant in the script.</p>
    <h2>Features</h2>
    <ul>
        <li>Fetch live stream details and concurrent viewers count</li>
        <li>Real-time chat message collection and analysis over configurable intervals</li>
        <li>Detection of suspicious chatters and AI-like bot behavior using phrase heuristics</li>
        <li>Estimation of real viewers vs. bot viewers using chat activity and heuristics</li>
        <li>Logging of all analysis data to a JSON file for offline review</li>
    </ul>
    <h2>Setup & Installation</h2>
    <ol>
        <li>Clone or download the repository:
            <pre><code>git clone https://github.com/Riotcoke123/LiveScanAIyt.git</code></pre>
        </li>
        <li>Ensure you have <code>Node.js</code> installed (v14+ recommended).</li>
        <li>Install dependencies:
            <pre><code>npm install</code></pre>
        </li>
        <li>Set your YouTube Data API v3 key and target channel ID in the script (<code>API_KEY</code> and <code>CHANNEL_ID</code> constants).</li>
        <li>Run the script:
            <pre><code>node index.js</code></pre>
        </li>
    </ol>
    <h2>Configuration</h2>
    <ul>
        <li><code>API_KEY</code>: Your YouTube Data API key</li>
        <li><code>CHANNEL_ID</code>: The YouTube channel ID to monitor</li>
        <li><code>CHAT_COLLECTION_DURATION_SEC</code>: Duration to collect chat messages for each analysis cycle (default 30 seconds)</li>
        <li><code>BOT_ESTIMATION_INTERVAL_MS</code>: Interval between bot estimation cycles (default 60,000 ms = 1 minute)</li>
    </ul>
    <h2>Output</h2>
    <p>Analysis results are logged in <code>stream_analysis_log.json</code> file in the root directory, with entries like:</p>
    <pre><code>{
  "timestamp": "2025-05-30T12:00:00Z",
  "channelId": "UCoxFxZirbfLvy9tres71eSA",
  "videoId": "abc123xyz",
  "concurrentViewers": 1200,
  "uniqueChatterCount": 100,
  "totalMessagesCollected": 250,
  "averageMessagesPerChatter": 2.5,
  "potentiallySuspiciousChatters": 3,
  "detectedAiLikeBots": 5,
  "estimatedRealViewers": 450,
  "estimatedBotViewers": 750,
  "estimationMethod": "Lurker Factor (0.25)",
  "rawChatToViewerRatio": 0.0833,
  "adjustedChatToViewerRatio": 0.0625
}</code></pre>
    <h2>Repository</h2>
    <p>Check out the source code and contribute on GitHub: <a href="https://github.com/Riotcoke123/LiveScanAIyt" target="_blank" rel="noopener noreferrer">https://github.com/Riotcoke123/LiveScanAIyt</a></p>
    <h2>License</h2>
    <p>This project is licensed under the <a href="https://www.gnu.org/licenses/gpl-3.0.html" target="_blank" rel="noopener noreferrer">GNU General Public License v3.0</a>.</p>
    <h2>Disclaimer</h2>
    <p>
        The AI detection part of this tool is experimental and currently in beta. 
        Use results as guidance rather than definitive proof of bot presence.
    </p>
</body>
</html>
