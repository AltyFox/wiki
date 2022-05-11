---
sidebar: "false"
---

# サポート

## 目次

0. [更新情報](#_0-updates)
1. [Modがありませんか？](#_1-no-mods)
2. [Modによるゲーム自体の問題](#_2-game-issues-post-modding)
3. [よくある質問](#_3-common-questions)
4. [その他のトラブルシューティング](#_4-miscellaneous-troubleshooting)
5. [まだ問題が解決しませんか？](#_5-still-having-issues)

## 0. 更新情報
After an update, the BSMG discord [#modding-announcements](https://discord.com/channels/441805394323439646/612468002243477505) channel should have the most up to date information on the status of mods. 以下に、最も一般的な手順の詳細な手順を示します。

### アップデート後、Modが動きません。
**新しいアップデートで** 一度ゲームを実行します。 次に、Mod アシスタントなど、 [初心者ガイド](/beginners-guide)にリンクされているインストーラを使用して Mod を再インストールします。

## 1. Modがありませんか？

### その他の質問

#### 1.1 Mod が表示されません
まず、以下を確認してください:

* **Modをインストールする前に一度ゲームを実行してください**. BSIPAは、古いModが新しいバージョンにロードされないように、新たなアップデート後の最初の実行時にすべてのModを削除します。 この場合は Mod を再インストールしてください。
* Steam/OculusはModと **同じドライブ** からBeat Saberを起動します。 *例）DドライブにModがあるが、steamはCドライブからゲームを起動する場合* 正しくドライブの場所を設定してください。
* Modを手動でインストールした場合は、ダウンロードしたすべてのファイルが含まれていることを確認し、正しいフォルダに入れてください。 依存関係も同様です

#### 1.2 古いバージョンで Mod をインストールしましたが、アップデート後に何もロードされません
上記のセクション1.1を確認した場合は、以下の解決策を番号順に試してみてください。

##### 解決策1

* BSIPAを最新のバージョンに更新する(ModAssistantまたは手動で)
* Beat Saberフォルダに移動
* `IPA.exe` を実行する

##### 解決策 2 (Steam)

* [ゲームファイルの整合性を確認する](#verify-game-files-for-steam)
* BSIPAを最新のバージョンに更新する
* Beat Saberフォルダに移動
* `IPA.exe` を実行する

##### 解決策3

* Beat Saberフォルダに移動
* `UserData` フォルダのバックアップを作成します(任意)
* `UserData`を削除する

::: warning　警告
これらの方法はMODのすべての設定をリセットします!
:::

##### 解決策4

* [クリーンインストール](#clean-installation)を実行する

#### 1.2 Mod Assistantがプラグインをインストールしていません
インストーラーはModを `Beat Saber/IPA/Pending`にダウンロードし、ゲームを起動するとBSIPAはこれらのファイルをルートフォルダに移動します。 ゲームプラグインフォルダがまだ空の場合は、 `IPA.exe` を再度実行し、実行を妨げるものがないことを確認してください。例： アンチウイルス、管理者権限など。

## 2. Modによるゲームの問題

### ゲームが起動しません

#### 2.1 GetThreadContext Failedエラー
`GetThreadContext` のウィンドウが表示されたり、Windows のエラー音が聞こえたりする場合は、 Beat SaberのModを阻害するソフトウェアがPCにインストールされている可能性があります。 ESEAやFaceltのような多くのサードパーティのアンチチートソフトウェアは、実行していない場合でも、Beat SaberのModを適用するBSIPAを妨害します。 また、一部のアンチウィルスソフトも同様の動作をします。

この問題を解決するには

1. アンチチートソフトウェアをアンインストールします。
2. PCを再起動します。
3. `AppData` フォルダにソフトウェアが存在しないかを確認します。
4. ゲームを起動します。 それでも問題が残る場合は以下のように対処してください: `追記: Bsipaをブロックするプログラムや疑問視するプログラムがある場合、不許可や不承認の問題が残る場合があります。` Steam: [ゲームファイルの整合性を確認する](#verify-game-files-for-steam) Oculus: [クリーンインストール](#clean-installation)を実行する

これで問題が解決するはずです。

#### 2.2 起動時にフリーズしました
ゲームがHealth and Safetyの画面でフリーズしたり、コントロールできないTポーズのアバターが表示された場合、 Steamプレイヤーは[ファイルを有効にする](#verify-game-files-for-steam) でファイルを確認してください。もしくはOculus Homeでゲームを再インストールしてください。 [クリーンインストール](#clean-installation)を実行する

Clean Installationを参照してください これはModをインストールした後にBeat Saberを更新した場合に発生することがあります。クリーンインストールを使ったユーザーは例外です。

### フレームレートの問題

#### 2.3 Modインストール後、耐えられないほどゲームが重くなる
ゲームのラグがひどすぎて、Health & Safetyの画面で `Continue` ボタンをクリックすることができなくなった場合、 Steamでゲームをプレイしている場合はファイルを確認するか、Oculus Homeでゲームを再インストールしてください。 ゲームを起動しようとしたときにエラーメッセージが表示されない場合やゲームが起動されないときは同様に対応してください。

問題が解決しなかった場合は、セクション [2.4 フレームレートの改善](#_2-4-improving-framerate) を確認してください。

#### 2.4 フレームレートの改善
[2.3](#2-3-the-game-stutters-unbearably-after-installing-mods) でFPSが改善しなかった場合、お使いのPCがModによるストレスによって単純に重くなっている可能性があります。 フレームレートを向上させるために、いくつかの方法があります。

* NVIDIA GEFORCE EXPERIENCE で Beat Saber のレンダリングスケールがデフォルト設定の1.0を超えていないかを確認します。 GPUの負荷が大幅に増加する1.4または1.8に設定されている可能性があります。
* あまり複雑でないカスタムアバターを使用します。
* カスタムセイバー **Plasma Katanas** には多くのカスタムイベントがあり、あなたがミスをしたときににラグが発生することが知られています。
* Camera2やCameraPlusは非常に負荷がかかります。特に複数のカメラを表示したり、FOVを大きくすると非常に負荷が大きくなります。
* ゲーム内の設定でレンダリングスケールやアンチエイリアスをさげ、ミラー、霧の効果などをオフにします。
* Oculus CV1やRiftプレーヤー: 3+の代わりに2つのセンサーを使用することを検討してください。
* Modと曲を減らします。
* [クリーンインストール](#clean-installation)を実行する.
* フレームレートの低下は、アプリケーションのデータフォルダ内で問題が発生している場合にも起こりえます。 これを修正するには、 [AppData内のBeatsaberフォルダの削除](#deleting-your-save-in-appdata)を参照してください。
* 重たい原因になりやすいので、score counterやswing speedのようなCountersPlusカウンターを無効にします。
* HTTPStatus mod とDataPullerはラグを引き起こす可能性があります。 このMODを無効にしてラグが消えるかどうかをテストします。

VRはCPUに負荷がかかります。特にModを導入すると負荷が大きくなります。 あなたが望み通りのMODでゲームを実行するのに苦労している場合は、ハードウェアのアップグレードを検討してください。 Beat Saberは、視覚的にはかなりシンプルなゲームであるため、GPUをあまり利用していません。

## 3. よくある質問

### その他

#### 3.1 メニューやボタンが表示されない
ゲームのメインウィンドウが表示されない場合、保存ファイルが破損している可能性があります。 これを修正するためには[AppData内のBeatsaberファイルを削除する](#deleting-your-save-in-appdata)を参照してください。

::: warning
ローカルのスコアと統計情報が削除されます。
:::

#### 3.2 `xxxx` modはどのように使えばいいですか?
Mod アシスタントを使用している場合は、Modをクリックし、"Mod Info" ボタンを押します。 [BeatMods](http://beatmods.com)ではMore Infoボタンを押すことで詳細のデータが得られます。

#### 3.3 振動の問題
Gameplay Modifiers Plusにはコントローラーの振動有無を切り替える設定項目がありました。 もし無効にしたModを削除したい場合は手動で書き込む保存ファイルを変更する必要があります。 `%appdata%\..\LocalLow\Hyperbolic Magnetism\Beat Saber\settings.cfg` を開き、 `controllersRumbleEnabled` を `true` に設定します。

もしこれらの原因が当てはまらない場合は以下の項目を参照してください。

* 振動がとても小さい
* ノーツを切ったときの振動がない
* セイバーを重ね合わせた時の振動に遅れがある
* Oculusタッチコントローラーを使用している

Beat SaberがマザーボードのUSBコントローラーを過負荷にしている可能性があります。 OculusのデバイスがUSBコントローラを使う時にほとんどの帯域を使い果たしてしまうことがあります。ほとんどのマザーボードは安いコントローラを利用しています。 Beat Saberは他のどのゲームよりも負荷がかかるので他のゲームではうまく動いていてもBeatSaberではうまくいかないことがあります。 以下の方法は根本的な解決にはなりませんが、試してみてください。

* HMDのUSB接続を別のポートに切り替える
* 不要なUSBデバイスを取り外す
* PCI-E USBハブを購入する
* SteamVRを使用している場合は `-vrmode oculus` を使用し、代わりにOculus SDKを使用してください

### カスタムアバター

#### 3.4 カスタムアバターの表示(非表示に) について
ゲームにフォーカスした状態でキーボードの**Home**を押す事で、ヘッドセットでの表示が切り替わります。

#### 3.5 自分のアバターが壊れている
カスタムアバターmodが正しくインストールされ、更新されていることを確認してください。ハードやソフトの依存環境も確認してください。 あなたは破損したアバターを持っている可能性があります、1つのアバターが破損していると曲やほかのセイバーなども破損させる可能性があります。

### カスタム曲

#### 3.6 楽曲が見つかりません
`Beat Saber/Beat Saber_Data/` にある `CustomLevels`フォルダに曲が入っていることを確認してください。 これは、ゲームが基本的にカスタム曲を読み込むディレクトリです。

**** 古い `Beat Saber/CustomSongs` フォルダに曲をいれないでください。 カスタム曲の仕様が変更されたため、この場所は非推奨です。 もし古いフォーマットの曲 (`.json`や `.ogg` ファイルではなく`.dat`や `.egg`ファイル)がある場合 `Beat Saber/CustomSongs`フォルダのほうに入れておいてください。 BeatSaverから再度ダウンロードする必要があります。

あるいは、代わりに[Song Converter](https://github.com/lolPants/songe-converter)をつかって手動で書き出すことができます。しかしこの方法は自分でプログラムをコンパイルする必要があります。

#### 3.7 再生ボタンがグレーになっています
右上隅の青色の疑問符(?)ボタンをクリックします。 これはあなたがどのようなModが不足ししているのかを示すものです。 インストールしてもプレイできない場合は再インストールしてください。 もしくは[クリーンインストール](#clean-installation)を実行してください。

#### 3.8 楽曲の詳細が無限に読み込みを続けています
これが特定の譜面でのみ発生した場合、必要な Mod が導入されていないか、曲ファイルが壊れている可能性があります。 すべてのマップにこの問題が発生した場合は、 `Plugins` フォルダを削除し、新しくインストールし直してください。

### Camera2

#### 3.9 My desktop view only takes up a small section of the screen
Your Camera2 display isn't filling up your canvas. Either drag the corner to fit the screen, or right click the window and click "Fit to Canvas".

### BeatSaver Downloader

#### 3.10 BeatSaver Downloader More Songs Button
**The More Songs button is located in the main menu to the left under the Mods text.** If the button for More Songs is greyed out then make sure all your songs loaded first, as seen in by the rainbow progress bar on the main menu. If your Mods menu isn't there then make sure your mods and dependencies are working and installed properly, refer to the [No Mods?](#_1-no-mods) section.

#### 3.11 Nothing Showing Up In The More Songs Menu
The probable causes for BeatSaver Downloader not working are:

1. すべての曲が前にロードされていることを確認してください。そうでなければ、「More Song」ボタンがグレー表示されます。
2. アンチウイルスやファイアウォールで BeatSaver へのアクセスをブロックしている。
3. Beatsaverのレート制限に達している。もうしばらくおまちください。

### マルチプレイのエラーコード
Here is a list of known error codes, what they mean, and what you can do to fix them.

<!-- Disable line length rule because of table -->
<!-- markdownlint-disable MD013 -->
| Code&nbsp; | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|:---------- |:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| CFR-1      | Unknown Error Occurred. Try restarting the game.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| CFR-2      | The multiplayer connection was canceled.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| CFR-3      | Server is not reachable. There may be an issue with your internet connection or with Beat Saber's relay servers. Double check you are not offline and your firewall allows Beat Saber to connect to the internet. <details><summary>**Background Information**</summary>Beat Saber Multiplayer is peer-to-peer where you connect directly with each player in the lobby. When this is not possible Beat Saber starts a "relay" server to send the data. This error means both of these methods failed.</details> &nbsp; This can also be caused by using emojis or special characters in your username. |
| CFR-4      | The server already exists.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| CFR-5      | Server does not exist. The lobby you were connecting to might have closed as you were joining.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| CFR-6      | The server is full. Choose a different lobby.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| CFR-7      | You are on a version of the game that is not supported by the servers.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| CFR-8      | Lobby password is incorrect. Double check you are entering the right password.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| CFR-9      | The matchmaking servers Beat Games run, which keeps track of open public and private lobbies, is offline. Try again later.                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| CFR-10     | Your session key from Steam or Oculus is not valid. If you are playing on Quest and have modded your game, check out this [FAQ answer](/faq/README.md#does-multiplayer-have-crossplay) to work around this. Otherwise you are on a pirated copy of the game which is not supported.                                                                                                                                                                                                                                                                                                 |
| CFR-11     | Your internet connection is offline.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
<!-- markdownlint-enable MD013 -->

## 4. その他のトラブルシューティング

### ログの読み取り
If you're on Steam you can go to
> Beat Saber > Properties > General > の起動オプションに `--verbose`を追加してください。

If you're on Oculus then you will have to Right click on Beat Saber.exe and create a shortcut. Edit the Target to add "--verbose" to the end of it. e.g. `C:\Program Files\Oculus\Software\Software\hyperbolic-magnetism-beat-saber\Beat Saber.exe" --verbose`

After adding verbose to your game hopefully it will display any errors regarding your avatars, sabers, and songs

* しかしこのエラーは完全ではありません。最終的には原因と考えられるModやモデル、曲を一つずつ取り除いて検証していく必要があります。

These messages are also written to `Beat Saber/Logs`.

A list of common exceptions can be found [here](./exceptions.md).

### Steam用のゲームファイルの確認
To verify integrity of game files follow these steps:

1. SteamVRが閉じていることを確認してください。
2. Steamライブラリに行き、Beat Saberを探してください。
3. Beat Saberを右クリックし、プロパティをクリックしてください
4. プロパティの「ローカルファイル」タブに移動します
5. Verify Integrity of Game Fileオプションを選択します。
6. ファイルが検証され、不足しているファイルがあればどこからインストールできるかが表示されます。

Here is a [Video Guide](https://www.youtube.com/watch?v=EBFfT4-ZiIc) although it is on the old steam UI, the steps are still the same.

### クリーンインストール

1. (必要があれば)以下のフォルダのコピーを作成して、ダウンロードしたカスタム コンテンツをバックアップしてください。

* `Beat Saber\Beat Saber_Data\CustomLevels`
* `Beat Saber\CustomSabers`
* `Beat Saber\CustomPlatforms`
* `Beat Saber\CustomNotes`
* `Beat Saber\CustomAvatars`

2. **すべてのビートセイバーのファイルを削除する** これはSteamからアンインストールすることとは異なります。アンインストールゲームファイルが取り除かれないことがあります。

> Steam: ``\steamapps\common\Beat Saber\`
  Oculus:``\hyperbolic-magnetism-beat-saber\`

3. SteamまたはOculusストア経由でゲームを再インストールします
4. **Modを入れる前に、一度ゲームを起動してください**
5. Mod アシスタントを実行し、Modをインストールしてゲームを起動します。

(Optional) If you want to take it one step further, refer To: [Deleting The Beatsaber Folder Within Your AppData](#deleting-your-save-in-appdata)

### AppData 内のデータを削除する。
This will delete your scores and local data, but not your custom leaderboard/ScoreSaber stats. You can find the folder at
> `%appdata%/../locallow/hyperbolic magnetism/beat saber`

Copy and paste everything from inside the bar above and paste it to your address bar in file explorer and delete it.

You can also get to this folder by showing hidden items and navigating to your
> Users > "USER" > AppData > LocalLow > Hyperbolic Magnetism > beat saber

<YouTube url='https://youtu.be/ONxJcD3Ir3Q' />

::: warning
Deleting this folder in Appdata will also delete your local scores and statistics.
:::

#### Desperate Measures
::: warning
Disabling your anti-virus involves security risks, be sure to know what you're doing
(i.e don't download or open suspicious files while it's turned off)
and don't forget to re-enable it as soon as you finished these steps.
:::

* 現在のユーザーが **管理者であることを確認してください**
* ウイルス対策を**オフ** にします。
* ディスクドライブ内でファイルの作成、編集を行う権限があることを確認してください。 (最近ウィンドウのアップデートがこの権限の確認が必要になっているみたいです)
* ドライバが最新であることを確認してください
* ヘッドセットやOS、ハードウェア/ソフトウェアに問題がないことを確認してください
* インターネット接続を確認し、BeatSaberのModやSteamに関連する接続がブロックされていないことも確認してください。

## 5. まだ問題が解決しませんか？
If this page doesn't cover the bases, then feel free to ask a question in the discord! To increase the chance that you'll have your questions answered, consider the following:

* 正しいチャンネルを使用してください。 PCユーザーのための`#pc-help`とクエストユーザーのための `#quest-help`チャンネルがあります。 **アバター、プラットフォーム、ノーツ作成**に関することは`#pc-3d-modeling`か`#quest-3d-modeling`チャンネルを**譜面作成**にかかわることは`#mapping-discussion`チャンネルでお尋ねください。
* 礼儀正しく敬意を払って質問しましょう
* 問題を詳細に説明してください。 「うまくいかなかった」とだけ言うことは簡単ですが、それでは何も進展しません。 なにが動かなかったのか、どのようなことを試したのか。 画面に表示されるメッセージがあったか? 画面全体が明るい紫色に変わりましたか？

::: tip NOTE Those with the `Support` role are volunteers that might choose to help out in their free time. The support role is in recognition of the knowledge and effort they have put forth, but it doesn't necessarily mean that they'll be around to help just because they're online. :::

Credit to Saber-Chan for their hard work on this page.
