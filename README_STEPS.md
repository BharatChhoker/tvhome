# TV Home: Sansui TV ke liye clean launcher

Android 4.4 par chalne wala halka home screen. Bade tiles, clock, remote se chalta hai.
Koi extra library nahi, isliye RAM bahut kam leta hai.

**Zaroori:** ye code abhi tak kisi TV par test nahi hua. Isliye pehle "Just once" se try karo,
"Always" mat chuno (neeche dekho).

## Ye kya karta hai
- Home par pinned apps ki row + "All Apps" tile
- Remote ke arrow keys se tile bada hota hai (zoom)
- OK dabake rakho: app ko Home par add / remove karo
- Back = All Apps se Home par wapas
- Purana Sansui launcher aur factory menu list me nahi dikhte (galti se khul na jaye)

---

## APK banane ke 2 tarike (koi ek chuno)

### Tarika 1: GitHub se (laptop par kuch install nahi karna)
1. github.com par free account banao.
2. **New repository** banao (naam: `tvhome`), **Public** rakho.
3. **uploading an existing file** par click karo, aur is zip ke andar ki **saari files aur folders** drag karo
   (`.github` folder bhi, ye zaroori hai). Commit karo.
4. Upar **Actions** tab kholo. "Build APK" chal rahi hogi (2-5 minute).
5. Hari tick aane par us run par click karo, neeche **Artifacts** me `TVHome-APK` download karo.
6. Download hui zip kholo, andar `app-debug.apk` milegi.

### Tarika 2: Android Studio se
1. Android Studio download karke install karo (developer.android.com/studio). Laptop me kam se kam 8 GB RAM chahiye.
2. **Open** par click karo aur `TVHome` folder chuno. Sync hone do (pehli baar download hota hai, wait karo).
   Agar "Upgrade Android Gradle Plugin" ka sawal aaye, to **mat** karo.
3. Menu: **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
4. APK yahan milegi: `app/build/outputs/apk/debug/app-debug.apk`

---

## TV par install karna

1. APK ko `platform-tools` folder me copy karo.
2. cmd me (pehle jaise `adb connect 192.168.1.44:5555` karke):
   ```
   adb install -r app-debug.apk
   ```
   `Success` aana chahiye.
3. TV ke remote par **Home** dabao. Popup aaye to **TV Home** chuno aur **Just once** dabao.
4. Test karo: arrow keys se tiles badal rahe hain? OK se app khulti hai? All Apps khulta hai?

## Agar kuch gadbad lage
- **Home** dabao aur popup me wapas **Sansui launcher** chuno.
- Ya hata do:
  ```
  adb uninstall com.bharat.tvlauncher
  ```

## Sab theek chale to default banana
Popup me **Always** chuno. Wapas purana launcher chahiye to:
Settings > Apps > TV Home > **Clear defaults**, phir Home dabake purana chuno.

**Purana Sansui launcher ko disable ya delete mat karna.**
