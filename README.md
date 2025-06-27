# Vibes

A repository with GitHub Codespaces configuration that includes Claude Code and Gemini CLI for AI development.

## Setup

1. Fork this repository
2. Create a Codespace from your fork
3. Set your `ANTHROPIC_API_KEY` environment variable in GitHub Codespaces secrets:
   - Go to [GitHub Codespaces Settings](https://github.com/settings/codespaces)
   - Click "New secret"
   - Name: `ANTHROPIC_API_KEY`
   - Value: Your API key from [Anthropic Console](https://console.anthropic.com/keys)
   - Select your forked repository

4. Launch your Codespace - you'll see a prompt if the API key isn't set

## Using Claude Code

Once your Codespace is set up with your API key, simply use Claude Code with:

```bash
claude
```

Or with a specific question:

```bash
claude "What does this repository do?"
```

## Using Gemini CLI

This environment also includes Google's Gemini CLI for AI development. Once your Codespace is set up, you can use:

```bash
gemini --help
```

To get started with Gemini CLI, you'll need to authenticate with your Google account:

```bash
gemini auth login
```

## GitHub Integration Setup

To enable Claude Code GitHub integration for automated issue and PR responses:

1. **Add API Key to Repository Secrets**:
   - Go to your repository's Settings → Secrets and variables → Actions
   - Click "New repository secret"
   - Name: `ANTHROPIC_API_KEY`
   - Value: Your API key from [Anthropic Console](https://console.anthropic.com/keys)

2. **Add GitHub Workflow**:
   - Copy the `claude.yml` workflow file to `.github/workflows/claude.yml` in your repository
   - This enables Claude to respond to `@claude` mentions in issues and pull requests

## Troubleshooting

If you see a warning about missing API key when the Codespace starts:

1. Follow the on-screen instructions to set up your API key
2. After adding the secret, you may need to rebuild your Codespace for it to take effect
3. Alternatively, you can set the key for your current session with:
   ```bash
   export ANTHROPIC_API_KEY=your-api-key-here
   ```