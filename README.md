<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Zenhaiku Testing Interface</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        body { font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif; }
        .fade-in { animation: fadeIn 0.5s ease-in; }
        @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }
        .card-hover { transition: all 0.3s ease; }
        .card-hover:hover { transform: translateY(-4px); box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1); }
        .gradient-text { background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); -webkit-background-clip: text; -webkit-text-fill-color: transparent; }
        .pulse-dot { animation: pulse 2s cubic-bezier(0.4, 0, 0.6, 1) infinite; }
        @keyframes pulse { 0%, 100% { opacity: 1; } 50% { opacity: 0.5; } }
    </style>
</head>
<body class="bg-gradient-to-br from-slate-900 via-slate-800 to-slate-900 min-h-screen">
    <div class="min-h-screen flex items-center justify-center p-4">
        <div class="w-full max-w-4xl fade-in">
            <div class="text-center mb-12">
                <h1 class="text-5xl font-bold gradient-text mb-3">Zenhaiku Testing Hub</h1>
                <p class="text-gray-300 text-lg">Quick access to application interfaces for testing</p>
                <div class="flex items-center justify-center gap-2 mt-4">
                    <div class="w-2 h-2 bg-green-500 rounded-full pulse-dot"></div>
                    <span class="text-green-400 text-sm">All systems operational</span>
                </div>
            </div>

            <div class="grid md:grid-cols-2 gap-6 mb-8">
                <div class="card-hover bg-white rounded-2xl shadow-2xl overflow-hidden">
                    <div class="bg-gradient-to-r from-blue-500 to-blue-600 p-6 text-white">
                        <div class="flex items-center gap-3 mb-2">
                            <span class="text-3xl">🚀</span>
                            <h2 class="text-2xl font-bold">User Interface</h2>
                        </div>
                        <p class="text-blue-100">Main application with AI proxy</p>
                    </div>
                    <div class="p-6">
                        <div class="space-y-4 mb-6">
                            <div class="flex items-start gap-3">
                                <span class="text-green-500 font-bold">✓</span>
                                <span class="text-gray-700">Multi-provider AI access</span>
                            </div>
                            <div class="flex items-start gap-3">
                                <span class="text-green-500 font-bold">✓</span>
                                <span class="text-gray-700">Real-time provider switching</span>
                            </div>
                            <div class="flex items-start gap-3">
                                <span class="text-green-500 font-bold">✓</span>
                                <span class="text-gray-700">Encrypted session storage</span>
                            </div>
                            <div class="flex items-start gap-3">
                                <span class="text-green-500 font-bold">✓</span>
                                <span class="text-gray-700">Settings & preferences</span>
                            </div>
                        </div>
                        <button onclick="launchUserInterface()" class="w-full bg-gradient-to-r from-blue-500 to-blue-600 text-white font-semibold py-3 rounded-lg hover:shadow-lg transition">
                            Launch User Interface
                        </button>
                    </div>
                </div>

                <div class="card-hover bg-white rounded-2xl shadow-2xl overflow-hidden">
                    <div class="bg-gradient-to-r from-purple-500 to-purple-600 p-6 text-white">
                        <div class="flex items-center gap-3 mb-2">
                            <span class="text-3xl">⚙️</span>
                            <h2 class="text-2xl font-bold">Admin Console</h2>
                        </div>
                        <p class="text-purple-100">Management and configuration</p>
                    </div>
                    <div class="p-6">
                        <div class="space-y-4 mb-6">
                            <div class="flex items-start gap-3">
                                <span class="text-green-500 font-bold">✓</span>
                                <span class="text-gray-700">Token generation</span>
                            </div>
                            <div class="flex items-start gap-3">
                                <span class="text-green-500 font-bold">✓</span>
                                <span class="text-gray-700">Session configuration</span>
                            </div>
                            <div class="flex items-start gap-3">
                                <span class="text-green-500 font-bold">✓</span>
                                <span class="text-gray-700">Token history tracking</span>
                            </div>
                            <div class="flex items-start gap-3">
                                <span class="text-green-500 font-bold">✓</span>
                                <span class="text-gray-700">Admin settings</span>
                            </div>
                        </div>
                        <button onclick="launchAdminConsole()" class="w-full bg-gradient-to-r from-purple-500 to-purple-600 text-white font-semibold py-3 rounded-lg hover:shadow-lg transition">
                            Launch Admin Console
                        </button>
                    </div>
                </div>
            </div>

            <div class="bg-white rounded-2xl shadow-2xl p-8 mb-8">
                <h3 class="text-2xl font-bold text-gray-800 mb-6 flex items-center gap-2">
                    <span>🧪</span> Testing Tools
                </h3>
                <div class="grid md:grid-cols-3 gap-4">
                    <button onclick="testSession()" class="bg-blue-50 hover:bg-blue-100 border-2 border-blue-200 rounded-lg p-4 text-left transition">
                        <div class="font-semibold text-blue-700 mb-1">Test Session</div>
                        <div class="text-sm text-blue-600">Create and validate test session</div>
                    </button>
                    <button onclick="clearStorage()" class="bg-orange-50 hover:bg-orange-100 border-2 border-orange-200 rounded-lg p-4 text-left transition">
                        <div class="font-semibold text-orange-700 mb-1">Clear Storage</div>
                        <div class="text-sm text-orange-600">Reset all local data</div>
                    </button>
                    <button onclick="viewConsole()" class="bg-gray-50 hover:bg-gray-100 border-2 border-gray-200 rounded-lg p-4 text-left transition">
                        <div class="font-semibold text-gray-700 mb-1">Browser Console</div>
                        <div class="text-sm text-gray-600">Open developer tools (F12)</div>
                    </button>
                </div>
            </div>

            <div class="bg-slate-800 rounded-2xl p-8 border border-slate-700">
                <h3 class="text-xl font-bold text-white mb-4 flex items-center gap-2">
                    <span>📚</span> Quick Reference
                </h3>
                <div class="grid md:grid-cols-2 gap-6 text-sm text-gray-300">
                    <div>
                        <div class="font-semibold text-white mb-2">User Interface</div>
                        <ul class="space-y-1 text-xs">
                            <li>• Email-based session generation</li>
                            <li>• Multi-provider AI access</li>
                            <li>• Real-time provider status</li>
                            <li>• Encrypted data storage</li>
                        </ul>
                    </div>
                    <div>
                        <div class="font-semibold text-white mb-2">Admin Console</div>
                        <ul class="space-y-1 text-xs">
                            <li>• Generate API tokens</li>
                            <li>• Configure session duration</li>
                            <li>• View token history</li>
                            <li>• Manage settings</li>
                        </ul>
                    </div>
                </div>
            </div>

            <div class="text-center mt-12 text-gray-400 text-sm">
                <p>Testing Interface v1.0 • Zenhaiku Application</p>
                <p class="mt-2 text-xs text-gray-500">For development and testing purposes only</p>
            </div>
        </div>
    </div>

    <script>
        function launchUserInterface() {
            const testEmail = 'test@zenhaiku.local';
            const sessionData = {
                email: testEmail,
                timestamp: Date.now(),
                expires: Date.now() + (365 * 24 * 60 * 60 * 1000),
                apiCode: generateApiCode(),
                providers: {}
            };
            localStorage.setItem('zenhaiku_session', JSON.stringify(sessionData));
            localStorage.setItem('zenhaiku_test_mode', 'true');
            window.location.href = 'index.html?test=true';
        }

        function launchAdminConsole() {
            localStorage.setItem('zenhaiku_admin_mode', 'true');
            localStorage.setItem('zenhaiku_test_mode', 'true');
            window.location.href = 'admin.html?test=true';
        }

        function generateApiCode() {
            const chars = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789';
            let code = '';
            for (let i = 0; i < 16; i++) {
                code += chars.charAt(Math.floor(Math.random() * chars.length));
            }
            return code;
        }

        function testSession() {
            const testEmail = 'test@zenhaiku.local';
            const sessionData = {
                email: testEmail,
                timestamp: Date.now(),
                expires: Date.now() + (365 * 24 * 60 * 60 * 1000),
                apiCode: generateApiCode()
            };
            localStorage.setItem('zenhaiku_session', JSON.stringify(sessionData));
            alert(`✓ Test session created!\n\nEmail: ${testEmail}\nAPI Code: ${sessionData.apiCode}\nExpires: ${new Date(sessionData.expires).toLocaleDateString()}`);
        }

        function clearStorage() {
            if (confirm('Clear all local storage data? This cannot be undone.')) {
                localStorage.clear();
                sessionStorage.clear();
                alert('✓ All storage cleared!');
                location.reload();
            }
        }

        function viewConsole() {
            alert('Opening browser console...\n\nPress F12 or right-click → Inspect → Console');
        }
    </script>
</body>
</html>
- **admin.html** - Admin console (300 lines)
  - Token generation interface
  - Admin settings management
  - Token history tracking
  - Email/SMS delivery simulation

- **admin.js** - Admin console logic (300 lines)
  - Token generation and validation
  - Settings persistence
  - Token history management

## Getting Started

### Option 1: Direct Browser Access

1. Open `index.html` in a modern web browser
2. Enter your email address to receive a session link
3. Check your email for the session link (or paste it directly in the app)
4. Add your AI provider API keys in the settings
5. Start using the AI proxy

### Option 2: Local Server

```bash
# Using Python
python -m http.server 8000

# Using Node.js (npx)
npx http-server -p 8000

# Using npm
npm start
```

Then open `http://localhost:8000` in your browser.

### Option 3: Deploy to Vercel

```bash
# Install Vercel CLI
npm i -g vercel

# Deploy
cd zenhaiku_app
vercel
```

### Option 4: Deploy to GitHub Pages

1. Push the `zenhaiku_app` folder to your GitHub repository
2. Go to Settings → Pages
3. Set source to "GitHub Actions"
4. Use the "Static HTML" workflow

## Configuration

### API Keys

Set your API keys in the application settings (they're stored encrypted locally):

- **Groq API**: Get from https://console.groq.com
- **OpenAI API**: Get from https://platform.openai.com
- **Together AI API**: Get from https://www.together.ai
- **Hugging Face Token**: Get from https://huggingface.co/settings/tokens
- **Ollama**: No key needed (local deployment)

### Provider Priorities

In the main interface, adjust provider priorities using the number inputs. Lower numbers = higher priority.

### Session Duration

Default: 365 days
Modify in: `Admin Console` → `Settings` → `Default Session Duration`

### Temperature & Max Tokens

- **Temperature**: Affects response creativity (0=deterministic, 2=maximum randomness)
- **Max Tokens**: Limits response length (100-4000 characters)

## How It Works

### Session Flow

1. **Email Entry**: User enters email on auth screen
2. **Session Generation**: App generates unique 32-character session token
3. **Link Delivery**: Session link sent via FormSubmit.co (no registration needed)
4. **Link Validation**: User opens link or pastes it into the app
5. **Session Activation**: App verifies token and loads user settings
6. **Encrypted Storage**: All data stored encrypted in browser localStorage

### AI Query Flow

1. **User Prompt**: User enters a question/prompt
2. **Provider Selection**: App tries providers in priority order
3. **Request Sent**: First available provider receives the query
4. **Response Handling**: Response displayed with provider attribution
5. **Fallback**: If provider fails, automatically tries the next one
6. **Action Logged**: All interactions logged with timestamps

## Security Considerations

### Current Implementation (Demo Level)

- XOR-based encryption for data storage
- Client-side only (no server exposure)
- localStorage isolation per browser

### Production Recommendations

1. **Upgrade Encryption**: Implement AES-256 using TweetNaCl.js or libsodium.js
2. **HTTPS Only**: Always deploy over HTTPS
3. **API Key Management**: 
   - Consider using a secure key management service
   - Never expose keys in client-side code
   - Use encrypted environment variables
4. **Rate Limiting**: Add rate limiting per API key
5. **Token Rotation**: Implement periodic session token rotation
6. **Audit Logging**: Log all admin activities

## API Integration Guide

### Adding a Custom AI Provider

Edit `app.js` and add to `initProviders()`:

```javascript
customProvider: {
    name: 'Custom AI',
    enabled: true,
    priority: 3,
    icon: '✨',
    endpoint: 'https://api.example.com/v1/chat',
    model: 'model-name',
    apiKey: '',
    status: 'unknown',
    color: '#00FF00'
}
```

Then add a query method:

```javascript
async queryCustomProvider(prompt, temperature, maxTokens) {
    const apiKey = this.currentSession.settings.customApiKey || '';
    if (!apiKey) throw new Error('Custom requires API key');
    
    const response = await fetch('https://api.example.com/v1/chat', {
        method: 'POST',
        headers: {
            'Authorization': `Bearer ${apiKey}`,
            'Content-Type': 'application/json'
        },
        body: JSON.stringify({
            model: 'model-name',
            messages: [{ role: 'user', content: prompt }],
            temperature,
            max_tokens: maxTokens
        })
    });
    
    if (!response.ok) throw new Error('API error');
    const data = await response.json();
    return data.choices[0]?.message?.content || 'No response';
}
```

Update `queryProvider()` switch statement:

```javascript
case 'customprovider':
    return await this.queryCustomProvider(prompt, temperature, maxTokens);
```

## Troubleshooting

### Email Not Received

1. Check spam/junk folder
2. Verify email address is correct
3. In browser console, check network requests to FormSubmit.co
4. Session link is still available in app under "Or paste your session link"

### Provider Returns Error

1. Verify API key is correct
2. Check provider status with "Test All Providers" button
3. Try a different provider (fallback should engage automatically)
4. Check browser console for detailed error messages

### Session Expired

1. Generate a new session link with your email
2. Previous conversations cannot be recovered
3. Settings may be preserved in localStorage if not cleared

### No Providers Working

1. Check internet connection
2. Verify at least one API key is configured
3. Open browser DevTools → Network tab to see request errors
4. Try local Ollama if installed

## Deployment Options

### Vercel (Recommended)

```bash
vercel
```

### Netlify

Drag and drop the `zenhaiku_app` folder to https://app.netlify.com/drop

### GitHub Pages

Push to `gh-pages` branch, enable in repository settings.

### Docker

```dockerfile
FROM nginx:alpine
COPY zenhaiku_app /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
```

```bash
docker build -t peaceful-llm .
docker run -p 8080:80 peaceful-llm
```

### AWS S3 + CloudFront

1. Create S3 bucket
2. Enable static website hosting
3. Upload `zenhaiku_app` contents
4. Create CloudFront distribution
5. Point domain to CloudFront

## Performance Tips

- Use Groq API for fastest responses
- Reduce max tokens for quicker responses
- Disable unused providers
- Lower temperature for more deterministic responses
- Use local Ollama for offline access

## Support & Issues

For issues, feature requests, or security concerns:
1. Check the troubleshooting section above
2. Review browser console for error messages
3. Test individual providers to isolate problems
4. Clear browser cache and localStorage if experiencing issues

## License

MIT - Open source and free to use

## Contributing

Contributions welcome! Areas for enhancement:
- Additional AI providers
- Enhanced encryption methods
- Real-time collaboration features
- Analytics dashboard
- Mobile app version
- Conversation history sync

---

**Built with ❤️ for the AI community**

Zero backend. Zero registration. Pure client-side AI proxy.