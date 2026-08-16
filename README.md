# Zhou House NAS

The following is a setup guide for joining the Zhou House Family NAS. This is an invite-only NAS for relatives of the Zhou family :)

**What is a NAS (Network Attached Storage)?** It's a computer whose sole purpose is to store files. Think of it as our own private Google Drive or iCloud, at a fraction of the cost.

## One-Time Setup

### Install Tailscale

Tailscale is a small app that creates a private, encrypted connection between your devices and our home server. That way you can reach the family files from anywhere without any of it being exposed to the internet.

1. **Accept the email invite** I sent you.
2. **Download the app:** [tailscale.com/download](https://tailscale.com/download) — or search "Tailscale" in the App Store.
3. **Sign in** with the same Google/Apple/Microsoft account you used on the invite. No new password.
4. **Turn it on.** Allow the VPN prompt on phones — that's normal.

You should now see **zhou-house-nas** in the app's device list.

**Leave it connected always.** It uses almost no battery. When not connected, you will lose access to your files, but they will still exist on the NAS.

## Day-To-Day Usage

There are two ways to access files on the NAS.

### Nextcloud

**Computer:** go to `https://zhou-house-nas.tail3c8d88.ts.net:8443` and bookmark it.

**iPhone/Android:** install the **Nextcloud** app, tap Log in, and enter that same address. Tap Grant access when the browser opens.

Log in with the Nextcloud username and password Eddy give you — *not* your Google/Apple account.

**Photo backup:** Nextcloud app → Settings → Auto upload. Your camera roll backs up automatically on Wi-Fi.

### SMB

SMB mounts the NAS as a network drive, so it shows up in your computer's Finder or File Explorer like a USB stick. Better for dragging around large files.

**This uses a different username and password** than Nextcloud. Eddy can give you both.

**Mac:** Finder → **Go → Connect to Server** (⌘K) → enter `smb://zhou-house-nas` → Connect → pick a share.

**Windows:** File Explorer → right-click **This PC** → **Map network drive** → enter `\\zhou-house-nas\zhou-house-shared` → tick *Reconnect at sign-in*.

If the name doesn't work, use the IP instead: `100.122.178.68`

## Shares

Shares are the top-level folders on the NAS. The same folders appear under friendlier names in Nextcloud:

| In Nextcloud | Over SMB | What it is |
|---|---|---|
| Family Shared | `zhou-house-shared` | Shared family files — everyone can read and write |
| Eddy's Drive | `user-eddy-zhou` | Eddy's private folder |
| Joe's Drive | `user-joe-zhou` | Joe's private folder |
| Qingbo's Drive | `user-qingbo-wu` | Qingbo's private folder |
| Zhengren's Drive | `user-zhengren-zhou` | Zhengren's private folder |

Anything in **Family Shared** is visible to everyone. Your own Drive is private — nobody else can see inside it.

## Troubleshooting

**Can't connect?** Open Tailscale and check if it says Connected.

**Password rejected?** Nextcloud and SMB have separate logins.

**Still stuck?** Text Eddy with a screenshot.
