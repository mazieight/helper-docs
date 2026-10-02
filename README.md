# Discord Channel Backup Bot

## Description
Had l-bot kay3tik l-imkaniya bach t-backup smiyat dyal les channels f Discord server w t-reapply f server akhor.

## Installation
1. Install Python 3.8+ 
2. Install les dependencies:
```bash
pip install -r requirements.txt
```
3. Dir file `.env` w zid fih token dyal bot:
```
DISCORD_TOKEN=your_token_here
```

## Commands (Les Commandes)

### !backup <server_id>
- Kay-backup smiyat dyal ga3 les channels f server
- Khassk tkun admin f server
- Kay-backup: text channels, voice channels, w categories

### !load <channel_id>
- Kay-reapply smiya dyal channel specific
- Khassk tkun admin f server
- Kaykhdem m3a text channels w voice channels

### !loadcat <category_id>
- Kay-reapply smiya dyal category specific
- Khassk tkun admin f server

### !loadall <server_id>
- Kay-reapply smiyat dyal ga3 les channels f server
- Khassk tkun admin f server
- Kaykhdem m3a ga3 types dyal channels

### !view
- Kay3tik overview dyal backups li kaynin
- Kay3tik details 3la kol server w chhal men channel fih

## Important Notes
- Bot kaykhdem ghir m3a smiyat dyal channels
- Ma kay-tbedelch permissions wla settings
- Kaykhdem m3a emojis w special characters
- Khassk tkun admin bach tkhdem les commands 