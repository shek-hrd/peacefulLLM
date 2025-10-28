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
3. Check your email inbox (or spam folder)
4. Click the session link or paste it in the app
5. Enjoy! ✓

**Note**: If email service is down, you can paste the link directly into "Or paste your session link" section.

## Step 3: Configure AI Providers (2 minutes)

### Quick Setup (Fastest)

**Use Groq (Recommended - Free & Fast)**

1. Get free API key: https://console.groq.com
2. In the app, go to Settings
3. Paste Groq API key
4. Click "Test All Providers"
5. See Groq as "ACTIVE" ✓

### Add More Providers (Optional)

Other free options:
- **OpenAI**: https://platform.openai.com (free trial credits)
- **Together AI**: https://www.together.ai (free tier)
- **Hugging Face**: https://huggingface.co (free tokens)
- **Local Ollama**: https://ollama.ai (completely free, offline)

## Step 4: Start Using (1 minute)

1. Type a question in the prompt box
2. Press Shift+Enter or click Send
3. See the AI respond
4. Adjust temperature and max tokens if needed
5. Enjoy unlimited AI access! ✓

## Troubleshooting

### "Session link not received"
- Check spam folder
- Try entering it manually in the text box
- Refresh the page

### "Groq Error: No API key"
- Generate free API key at https://console.groq.com
- Add it in Settings → API Keys
- Test again

### "All providers failed"
- Ensure at least one API key is configured
- Click "Test All Providers"
- Check browser console (F12) for errors
- Try local Ollama (offline option)

### "Response is slow"
- Switch to Groq (fastest)
- Reduce max tokens
- Lower temperature
- Close other browser tabs

## Tips & Tricks

### 1. Use Keyboard Shortcuts
- **Shift+Enter**: Send message quickly
- **Tab+Enter**: In settings

### 2. Copy API Code
- Click "Copy Code" to get your API code
- Use it in your own applications

### 3. Monitor Provider Performance
- Watch response times in the Stats panel
- See which provider is active
- Switch priorities if needed

### 4. Adjust Settings
- **Temperature**: 0 (consistent) → 2 (creative)
- **Max Tokens**: Lower = faster, Higher = longer responses
- **Priority**: 1 (highest), 5 (lowest)

### 5. Check Action Log
- See all your interactions timestamped
- Useful for debugging
- Actions saved per session

## API Key Resources

| Provider | Get Key | Speed | Cost | Docs |
|----------|---------|-------|------|------|
| Groq | https://console.groq.com | ⚡⚡⚡ | Free | https://console.groq.com/docs |
| OpenAI | https://platform.openai.com | ⚡⚡ | $0.01 | https://platform.openai.com/docs |
| Together AI | https://www.together.ai | ⚡⚡⚡ | Free | https://www.together.ai/api |
| Hugging Face | https://huggingface.co | ⚡ | Free | https://huggingface.co/docs/api |
| Ollama | https://ollama.ai | ⚡⚡ | Free | https://github.com/jmorganca/ollama |

## Free Trial Options

### Groq (Best for Starting)
- **Free**: Unlimited API calls
- **Speed**: Fastest free tier
- **Model**: Mixtral-8x7b (excellent)
- **Get Started**: 5 seconds

### OpenAI Free Trial
- **Free**: $5 trial credit (3 months)
- **Model**: GPT-3.5-turbo (reliable)
- **Cost**: ~$0.01 per 1K tokens

### Together AI Free Tier
- **Free**: Generous free tier
- **Models**: Multiple LLaMA models
- **Get Started**: Instant

### Hugging Face Free
- **Free**: API calls with rate limits
- **Models**: Mistral, LLaMA, etc.
- **Speed**: Slower but solid

### Local Ollama (Best Privacy)
- **Free**: Completely free, offline
- **Setup**: 5 minutes
- **Speed**: Depends on your computer
- **Privacy**: 100% local, no data sent

## Next Steps

Once you're comfortable:

1. **Add More Providers**: Mix and match for best results
2. **Set Priorities**: Order providers by your preference
3. **Fine-tune Settings**: Adjust temperature/tokens
4. **Save Settings**: They persist automatically
5. **Explore**: Try different prompts and learn what works

## Common Questions

**Q: Is my data safe?**
A: Yes! All data is encrypted locally. No backend server exists.

**Q: Can I use multiple providers?**
A: Yes! The app automatically tries them in priority order.

**Q: What happens if a provider goes down?**
A: The app automatically switches to the next one.

**Q: Can I use this offline?**
A: Yes! Install Ollama and use the local provider.

**Q: How long do sessions last?**
A: 365 days by default. Configurable in Admin Console.

**Q: Can I access from multiple devices?**
A: Yes! Just use the same session link on any device.

## Security Best Practices

1. **Use HTTPS**: Always use secure connections
2. **API Keys**: Keep them private, use admin console
3. **Sessions**: Don't share session links
4. **Passwords**: Not used (token-based auth)
5. **Local Data**: Encrypted in browser storage

## Getting Help

- Check the README.md for full documentation
- Review browser console (F12) for error messages
- Test each provider individually
- Try a different provider if one fails
- Reset browser cache if stuck

## Ready to Go! 🚀

You now have everything you need:
- ✅ Application running
- ✅ Session created
- ✅ At least one AI provider configured
- ✅ Understanding of key features

**Start asking questions!**

```
"What is machine learning?"
"Write a haiku about coding"
"Explain quantum computing simply"
```

Enjoy your AI journey! 🤖✨

---

**Questions?** Check README.md for detailed docs.
**Want to deploy?** See DEPLOYMENT.md.
**Need admin features?** Visit the Admin Console.