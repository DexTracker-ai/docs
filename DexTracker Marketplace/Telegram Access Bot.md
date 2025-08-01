# Telegram Access Bot - DexTracker

Multi-language Telegram bot for managing access to private channels based on subscription to the main channel. Supports Russian and English languages, automatically detects user's language, and provides appropriate channels.

**Current Price**: $300
**Contacts**: [https://t.me/daniil_jave](https://t.me/daniil_jave)

What you get:

- Free setup into your hosting
- Free help to integrate app to your server
- Full access to the codebase and code updates
- Free updates for app, you can request for free updates via access to issues
- Full access to Project Time tracking by developers

## Features

- 🌍 Multi-language support (RU/EN)
- 🔄 Automatic user language detection
- 🔐 Channel subscription verification
- 🎯 Single-use invite link generation
- 📊 User statistics
- 📨 Message broadcasting system
- ⏰ Daily reminders for unsubscribed users

## Requirements

- Node.js 16+
- pnpm
- Telegram Bot Token (get from [@BotFather](https://t.me/BotFather))
- Two channels for each language (public source + private target)

## Installation

1. Clone the repository:
```bash
git clone [repository-url]
cd telegram-access-bot
```

2. Install dependencies:
```bash
pnpm install
```

3. Create configuration file:
```bash
cp config.example.yaml config.yaml
```

4. Configure config.yaml:
```yaml
bot:
  token: "YOUR_BOT_TOKEN"  # Token from @BotFather
  adminIds: [123456789]    # Admin user IDs

channels:
  ru:
    sourceChannelId: "@channel_name_ru"  # Public channel (with @)
    targetChannelId: "-100123456789"     # Private channel (with -100)
    targetChannelLink: "https://t.me/+abcdefghijk"
  en:
    sourceChannelId: "@channel_name_en"
    targetChannelId: "-100987654321"
    targetChannelLink: "https://t.me/+zyxwvutsrqp"
```

## Running

Development:
```bash
pnpm run dev
```

Production:
```bash
pnpm run build
pnpm run start
```

## Bot Commands

### User Commands

- `/start` - Start interaction with the bot
- `/check` - Check subscription status
- `/ref` - Get your personal referral link and statistics
- `/ref [code]` - Check statistics for a specific referral code

### Admin Commands

- `/stats` - Show detailed user statistics
- `/broadcast_all [text]` - Send message to all users
- `/broadcast_subscribed [text]` - Send message to subscribed users
- `/broadcast_unsubscribed [text]` - Send message to unsubscribed users
- `/create_ref [code]` - Create custom referral code (generates random code if not specified)
- `/ref [code]` - Check detailed statistics for any referral code

## Referral System

The bot includes a comprehensive referral system that allows users to invite others and track their referral statistics.

### Referral Features

- Generate personal referral links
- Track number of invited users
- View detailed referral statistics
- Monitor active invitations

### Referral Code Management

Administrators can create custom referral codes using:
- `/create_ref` - Generates a random 6-character code
- `/create_ref customcode` - Creates a referral code with specified name

Examples:
```bash
/create_ref           # Creates random code like "ab12cd"
/create_ref SUMMER23  # Creates code "SUMMER23"
```

Each referral code can be tracked using `/ref [code]` command which shows:
- Total number of invited users
- Currently active users
- Detailed list of invited users with their status

### How Referral System Works

1. **Getting Referral Link**
   - Use `/ref` command to get your personal referral link
   - Share the link with potential users

2. **Inviting Users**
   - When users join via referral link, they're automatically tracked
   - The system records the referral relationship

3. **Viewing Statistics**
   - Use `/ref` to see your referral statistics
   - Use `/ref [code]` to check specific referral code statistics
   - Statistics include total invites and active users

### Referral Data Storage

Bot saves referral data in `data/referrals.json`:
- Referral codes
- Invited users list
- Total invitation count
- Active referrals tracking

## Data Structure

### User Data (`data/users.json`)
```json
{
  "userId": {
    "id": number,
    "username": string,
    "firstName": string,
    "lastName": string,
    "startDate": string,
    "hasAccess": boolean,
    "lastMessageIndex": number,
    "language": "ru" | "en",
    "referredBy": string
  }
}
```

### Referral Data (`data/referrals.json`)
```json
{
  "referralCode": {
    "code": string,
    "invitedUsers": number[],
    "totalInvited": number
  }
}
```

## Channel Setup

1. Create two channels for each language:
   - Public channel (source) - must have a username
   - Private channel (target) - can be private

2. Add the bot as an administrator to both channels

3. Get channel IDs:
   - For public channel, use username with @ (e.g., "@mychannel")
   - For private channel, get ID via [@getidsbot](https://t.me/getidsbot)
   - Private channel ID must start with -100

## Statistics and Data

Bot saves user data in `data/users.json`:
- User ID
- Username
- First and last name
- First interaction date
- Access status
- Selected language

Statistics include:
- Total number of users
- Number of subscribed/unsubscribed users
- Language distribution

## Message Broadcasting

Administrators can send messages to different user groups:
```
/broadcast_all Important announcement for everyone!
/broadcast_subscribed New content in private channel
/broadcast_unsubscribed Don't forget to subscribe to the channel!
```

Broadcasting system includes:
- Anti-spam protection (delay between messages)
- Delivery report (number of successful/failed sends)
- Markdown markup support

## Daily Reminders

Bot automatically sends reminders to unsubscribed users:
- Sent at 12:00 every day
- Different messages for each language
- Message rotation for variety

## Security

- Single-use invite links for private channel
- Admin rights verification for special commands
- Anti-spam protection for broadcasts

## Troubleshooting

If you encounter problems:
1. Check bot permissions in channels
2. Verify channel IDs are correct
3. Ensure public channels have usernames
4. Check error logs in console

## License

MIT
