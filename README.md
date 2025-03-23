# 🔐 HeidiSQL Password Decoder

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Version](https://img.shields.io/badge/version-1.0.0-green.svg)

A sleek, secure client-side tool to decode passwords from your HeidiSQL connection settings file.

![screenshot](https://github.com/user-attachments/assets/60fe0ca5-0207-4311-8df3-bfe2cb76e479)


## ✨ Features

- **🔒 100% Client-side Processing**: All decoding happens in your browser - no data is ever sent to a server
- **🖥️ Clean Modern Interface**: Intuitive design with visual feedback
- **📋 Easy Copy Functionality**: One-click copy for decoded passwords
- **🔍 Smart Detection**: Automatically finds password entries in your settings file
- **🌐 Works Offline**: No internet connection required after initial page load

## 📋 How to Use

1. Export your HeidiSQL connection settings or copy from your sessions file
2. Paste the contents into the text area
3. Click "Decode Passwords"
4. View all your server connections and their decoded passwords
5. Copy any password with a single click

## 🔍 How It Works

HeidiSQL stores passwords in a simple encoded format. This tool uses the same algorithm that HeidiSQL uses to decode passwords but does it entirely in your browser. The encoded password format ends with a digit that indicates the shift value used in the encoding.

```javascript
function heidiDecode(hex) {
    var str = '';
    var shift = parseInt(hex.substr(-1));
    hex = hex.substr(0, hex.length - 1);
    for (var i = 0; i < hex.length; i += 2) 
        str += String.fromCharCode(parseInt(hex.substr(i, 2), 16) - shift); 
    return str; 
}
```

## 🔒 Privacy

Your privacy is our top priority:

- No data is ever sent to any server
- All processing happens directly in your browser
- No cookies or local storage used
- No analytics or tracking
- No external requests after page load

## 📜 License

This project is [MIT](LICENSE) licensed.

---

*Made with ❤️ for database administrators everywhere*
