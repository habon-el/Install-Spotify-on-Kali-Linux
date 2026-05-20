# Install-Spotify-on-Kali-Linux

View the README
View the LICENSE
The README is short and beginner-friendly: four steps to install, how to open Spotify, and a small "having a problem?" section for the key error and the harmless warnings. Nothing complicated.
To put it on GitHub, run these in your Kali terminal (save both files into a folder called spotify-kali-guide first):

sudo apt install gh
gh auth login
cd ~/spotify-kali-guide
git init
git add README.md LICENSE
git commit -m "Spotify on Kali Linux install guide"
gh repo create spotify-kali-guide --public --source=. --push


# How to Install Spotify on Kali Linux

A simple, beginner-friendly guide. Just follow the steps in order and you'll
have Spotify running in a few minutes.

---

## Steps

Open a terminal and run these commands one at a time.

**1. Add Spotify's key**

```bash
curl -sS https://download.spotify.com/debian/pubkey_C85668DF69375001.gpg | sudo gpg --dearmor --yes -o /etc/apt/trusted.gpg.d/spotify.gpg
```

**2. Add the Spotify repository**

```bash
echo "deb https://repository.spotify.com stable non-free" | sudo tee /etc/apt/sources.list.d/spotify.list
```

**3. Update your package list**

```bash
sudo apt update
```

**4. Install Spotify**

```bash
sudo apt install spotify-client
```

That's it — Spotify is installed.

---

## Open Spotify

Either search for **Spotify** in your applications menu and click the icon, or
type this in a terminal:

```bash
spotify
```

Then log in with your Spotify account and enjoy your music.

---

## Having a problem?

**You see a "Missing key" error after `sudo apt update`.**
Spotify changed its key. Run the command below (use the key code from your own
error message if it's different), then run `sudo apt update` again:

```bash
sudo gpg --no-default-keyring --keyring /etc/apt/trusted.gpg.d/spotify.gpg --keyserver hkps://keyserver.ubuntu.com --recv-keys E1096BCBFF6D418796DE78515384CE82BA52C83A
```

**You see warnings when you run `spotify` in the terminal.**
Messages about `libayatana-appindicator` or `maxDynamicUniformBuffers` are
harmless. Spotify is working fine — you can ignore them.

**Spotify won't open and you're logged in as `root`.**
Spotify doesn't run as the root user. Use a normal user account instead.

---

## Don't want to install anything?

You can use Spotify right in your browser at <https://open.spotify.com>.

---

*This is an unofficial community guide. Spotify is a trademark of Spotify AB.*
