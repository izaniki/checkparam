# checkparam
Fork of Checkparam addon for FFXI -- All Original Code credit goes to  @from20020516. Could not find their twitter account or the github for this addon. Some additional functionality has been added (view the changes below). Everything prior to the FORK README section is their original Readme.

** IF YOU ARE TRYING THIS OUT, DELETE/RENAME YOUR SETTINGS.XML FILE. IT WILL MESS UP A NUMBER OF STATS BEING CHECKED. THE ADDON WILL GENERATE A NEW ONE WITH THE NEW DEFAULTS AND THEN YOU CAN EDIT THEM. **


# checkparam
## English
- `/check` OR `/c` (in-game command)
  - Whenever you `/check` any player, displays the total of property of that players current equipments.(defined in `settings.xml`)
- `//checkparam` OR `//chp` (addon command)
    - same as /check <me>. you can use this command in equipment menu.


### data/settings.xml (auto-generated)
- Define the properties you want to be displayed for each job.
    - `|` divide each property
    -  `pet: ` define properties for all pets, which means avatar: wyvern: automaton: luopan:
- `<levelfilter>` ignore players with below the level `<number>` when `/check`. default value is 99.
    - **Tips:** if set `100`, ignore all players. you can still use `//cp` for yourself.
- If there’s something wrong,or something strange,  
please tell me on Twitter [@from20020516](https://twitter.com/from20020516) **with simple English**. Thank you!

## 日本語
- `/check` または `/c`（ゲーム内コマンド）
    - プレイヤーを「調べる」したとき、そのプレイヤーが装備しているアイテムの任意のプロパティを合計して表示します。(`settings.xml`で定義)
- `//checkparam` または `//chp`（アドオンコマンド）
    - /check <me> と同様ですが、装備変更画面でも使用できます。

### data/settings.xml (自動生成)
- 表示させたいプロパティをジョブごとに定義します。
    - `|` 区切り記号
    - `pet: ` 召喚獣: 飛竜: オートマトン: 羅盤: は代わりに`pet:`で指定します。
- `<levelfilter>`
    -「調べる」時に対象のレベルが設定値未満なら結果を表示しません。(初期値99)
    - **Tips:** `100`を設定すると「調べる」時の結果を表示しません。
-----------------
-----------------
FORK Readme:

![Screenshot 2026-04-06 035930](https://github.com/user-attachments/assets/4b553116-8049-4e2c-a875-046a064ba823)


**Commands changed to //chp from //cp

**Added abbreviations for various stats to reduce the amount of text shown.

**All caps for stats are based off of information from SE or the community's usual guidelines regarding the flooring of stats: SIRD is 102, gear haste is 26, DT is 52 (this was expressly stated by SE devs on their livestream that showed the solo Vagary fights).

**All stats have a set of abbreviations to reduce the amount of text added to chat whenever the addon is run.

**Quick Cast = quick magic and all forms of "occ. quickens spellcasting" that I could find. If there are other pieces of gear that have this stat that are not being added, I will change it to work.

**Damage Taken will be shown added to PDT and MDT automatically.

**MultiHit is a combination of DA/TA/QA for when you don't care which of them you have.

**Subtle Blow should correctly be capping each category at 50, while providing the total amount overall (so it will not give you a cap of 75 if you have SB1 at 65 and SB2 at 10).

**The following DW categories have been added to show how much DW is needed for various amounts of haste (the number) and whether you are getting haste samba from a DNC sub or main (S and M respectively). The cap shown will vary based on which you choose, it will have the amounts provided by traits automatically added, and then show how much you need to cap.
Stat Name = Cap
['dw0'] = 64,
['dw10'] = 60,
['dw15'] = 57,
['dw30'] = 46,
['dwcap']=26,
['dw0s'] = 62,
['dw10s'] = 57,
['dw15s'] = 54,
['dw30s'] = 40,
['dwcaps']=14,
['dw0m'] = 60,
['dw10m'] = 54,
['dw15m'] = 50,
['dw30m'] = 33,
['dwcapm']=0


**The following command has been added:

//chp (or //checkparam) <role>

This will set the parameters being checked by the addon to a certain preset that are defined in the .lua file. Some examples that are currently inside: 
idle, idle2(more in-depth stats added as well, but it gets long), dd, heal, tank, mage, range, pet, default. Added: dw, dws, dwm for when you have, respectively, no haste samba ('dw'), haste samba from a DNC sub ('dws'), and haste samba from a DNC main ('dwm').

These will allow you to quickly change what is checked by typing, for example, //chp idle and then checking a player. These parameters will remain until set back to the default by using //chp default OR //chp reset.

Be aware, that editing these roles will affect all jobs as well as the roles are being used as terms inside of those sets of parameters. If you want to change what shows for what jobs, I recommend adding it to the job instead of editing the role.

**The addon should be including ONLY one instance of "magic accuracy skill" to the "magic accuracy" stat.

**The addon should have "Phalanx" and "Phalanx received" as the same stat now, whereas it was previously separated.
