TeXShop の日本語ヘルプファイルのアーカイブ (v2-6) です。

作業当時の日英対訳テキストをアップしています。

----
Version 2.10b
----

#Credits（クレジット）

［☆］**TeXShop is produced under the GPL public license. **

【★】**TeXShop は GPL 公有使用許諾のもとに提供されます。**

［☆］**Coordination by:**
【★】**コーディネーター：**

* Richard Koch
* Dirk Olmes
* Gerben Wierda

［☆］**Code by:**
【★】**コード開発：**

* Richard Koch
* Dirk Olmes
* Gerben Wierda
* Mitsuhiro Shishikura （宍倉光広）
* Seiji Zenitani （銭谷誠司）
* Isao Sonobe （園部勳）
* Martin Kerz
* Michael Witten
* Norman Gall
* Anton Leuski
* Jérôme Laurens
* Piero D'Ancona
* Geoffroy Lenglin
* Jonas Zimmermann
* Sean Luke
* Max Horn
* John Nairn
* Greg Landweber
* Nicolás Ojeda Bär
* Martin Heusse
* Sarah Childers
* Makoto Inoue （井上真）
* Sven A. Schmidt
* Georg Klein
* David Reitter
* Maarten Sneep
* Kevin Ballard
* Elliott Hughes
* Claus Gerhardt
* Sebastian Siedentopf
* Will Robertson
* Stefan Walsen
* Yu Itoh （伊東悠）
* iNOUE Koich! （井上浩一）

［☆］**Localization by:**
【★】**ローカライズ：**

* Maarten Sneep
* Jérôme Laurens
* Hendrik Chaltin
* Keith J. Schultz
* Sascha Beverungen
* Martin Kerz
* Max Horn
* Giuseppe Carlino
* Nicola Vitacolonna
* Seiji Zenitani （銭谷誠司）
* Yoshihisa Okazaki （岡崎祥久）
* Paulo Abreu
* Andrei Teleman
* Roxana Tenea Teleman
* Juan Luis Varona Malumbres

［☆］**Contact Information:**
【★】**連絡先：**

* Richard Koch
	* Mathematics Department University of Oregon Eugene, Oregon 97403
	* koch@math.uoregon.edu
* Dirk Olmes
	* dirk@xanthippe.ping.de
* Gerben Wierda （for teTeX only ─ teTeX についてのみ）
	* Gerben_Wierda@rna.nl

#What’s New?（更新履歴）

##Version 1.42 ＆ 2.05

###──New features in 2.05（バージョン 2.05 での新機能）：

* ［☆］TeXShop 2.05 is now a Universal Binary, containing code for both the PowerPC and Intel processors. The system automatically runs the correct version of the code.
* 【★】TeXShop 2.05 でユニバーサル・バイナリ（Universal Binary）になりました──PowerPC 用とインテル・プロセッサ用コードの両方が含まれています。システムにより自動的に適切な方のコードが実行されます。

* ［☆］The default TeXShop preference for the teTeX binary directory is /usr/local/teTeX/bin/powerpc-apple-darwin-current. But if users have installed Gerben Wierda's latest TeX redistribution, they also have Intel binaries. On Intel machines, the teTeX binary directory should then be /usr/local/teTeX/bin/i386-apple-darwin-current. TeXShop now has code to make this change automatically. When the program first starts, it calls "uname -p" to determine the current processor. If the result is "i386", then TeXShop permanently changes the above preference to /usr/local/teTeX/bin/i386-apple-darwin-current. However this change is not made if the user has manually changed the default /usr/local/teTeX/bin/powerpc-apple-darwin-current to some other location. Thus if a user has the Fink teTeX distribution or some other distribution and has set the teTeX binary directory preference to point to it, the preference will not be changed.
* 【★】TeXShop のデフォルトの環境設定では、teTeX バイナリのディレクトリは、/usr/local/teTeX/bin/powerpc-apple-darwin-current です。しかし Gerben Wierda さんの最新の TeX ディストリビューションをインストールしている場合は、インテル用のバイナリが入っていることもあります。なのでインテル機では、teTeX バイナリのディレクトリは、/usr/local/teTeX/bin/i386-apple-darwin-current になるはずです。TeXShop ではこの変更を自動で行なうコードを組み込みました。最初にプログラムを起動した際に「uname -p」をコールして作動中のプロセッサを判定します。その結果が「i386」ならTeXShop は、上述の設定を /usr/local/teTeX/bin/i386-apple-darwin-current へと恒久的に 変更します。とはいえこの変更は、デフォルトの /usr/local/teTeX/bin/powerpc-apple-darwin-current をユーザが手ずから他のロケーションへと書き変えていた場合には行なわれません。なのでもし Fink の teTeX ディストリビューションないしはその他のディストリビューションを入れており、それを teTeX バイナリのディレクトリ設定で指定していれば、環境設定は変更されません。

* ［☆］When TeXShop was first released on Tiger, users ran into an annoying bug which caused the program to gradually slow to a crawl after several typesetting actions. This bug was fixed a couple of days after the release. The problem occurred when a new pdf file was loaded into the PdfKitView in the Preview window. According to Apple documentation, this should have released the previous data structure from memory. The release did occur, but it caused the program slowdown. So the bug fix consisted of tricking the system into believing that the data structures were still being used so the system didn't try to release them.
* 【★】TeXShop を最初に Tiger 上でリリースした際にユーザが遭遇した厄介なバグは、タイプセットを数度実行した後、プログラムが次第にノロノロしてくるというものでした。このバグは公開して数日で修正しました。新しい PDF ファイルがプレビューウインドウ内の PdfKitView にロードされる際に問題が生じていました。Apple のドキュメントによれば、古いデータ・ストラクチャがメモリから解放されるはずだとのことでした。解放は起こっていました、が、それがプログラムのスローダウンを引き起こしていたのです。なのでバグフィックスはシステムをごまかしてデータ・ストラクチャがまだ使用中であると思い込ませ、システムが解放しようとしないようにさせました。

* ［☆］A side effect was that memory gradually filled up and some users learned that they needed to quit TeXShop and restart after each day's work.
* 【★】副作用としてメモリが次第にいっぱいになってしまうので、毎日の作業が済んだ後 TeXShop を終了する必要があると覚ったユーザもいました。

* ［☆］Recent investigation seems to show that this bug is fixed in Tiger 10.4.3. Consequently the latest version of TeXShop tests which system is running and releases the old data structures when the system is at least 10.4.3, but not otherwise.
* 【★】最近の検証ではこのバグは Tiger 10.4.3 で直っているようです。したがって最新の TeXShop ではどのシステムが稼働しているか調べ、10.4.3 以降であれば古いデータ・ストラクチャを解放するようにしますが、そうでなければせずにおきます。

* ［☆］This behavior is controlled by a new hidden Preference item:
* 【★】この挙動は隠れた環境設定の新項目で制御できます：

	defaults write TeXShop ReleaseDocumentClasses 0

* ［☆］The default value is 0, causing the program to behave as just described. If the value is 1, the old data structures are never released and the program behaves exactly as earlier versions of TeXShop 2. If the value is 2, old data structures are always released.
* 【★】デフォルトの値は 0 です──プログラムは上述のように機能します。値が 1 なら、古いデータストラクチャは解放されず、プログラムは以前のバージョンの TeXShop 2 とまったく同じにふるまいます。もし値が 2 であれば、古いデータストラクチャは常に解放されます。

* ［☆］Thus if you find that the program becomes sluggish after several typesetting jobs, change ReleaseDocumentClasses to 1 and then report the behavior to me with as many details as possible.
* 【★】ですから、何回かタイプセット作業をした後でプログラムが遅くなってしまうようであれば、ReleaseDocumentClasses を 1 に変更して、できるだけ詳しい状況を私（作者）に報告してください。

* ［☆］Michael Witten, a student at MIT, added multiple wrapping modes to TeXShop. Users can choose "no wrapping" so lines continue right until the user pushes ENTER, or "word wrapping" so text is wrapped at word boundaries (this was the prior behavior), or "character wrapping" so text wraps exactly at the last possible character. Not that these wrappings are "soft"; resizing the window will change the wrapping. The default wrapping is "word wrapping" but a menu command allows the wrapping to be changed. Moreover, a hidden preference allows the default wrapping to be changed:
* 【★】Michael Witten さんは MIT の学生ですが、複数の折り返しモードを TeXShop に追加してくれました。「折り返しなし」を選ぶとユーザが ENTER キーを押すまで行は右に伸びてゆきますし、「ワード毎」を選べばテキストは単語の区切りで折り返し（これが以前までの動作でした）、「文字毎」を選択するとテキストはギリギリ最後の文字できっちりと折り返します。以上の折り返しは「ソフト」というわけではありません──ウインドウのサイズを変更すれば折り返し位置も変更されます。デフォルトの折り返し表示は「ワード毎」になっていますが、メニューコマンドで折り返しを変更できます。さらに、隠れた環境設定でデフォルトの折り返し表示を変えておくことができます──

	defaults write TeXShop LineBreakMode 1

* ［☆］where "None" = 0, "Word Wrap" = 1, and "Character Wrap" = 2. Wrapping is done at the right side of the window unless the ruler is active; if it is, wrapping is done at the "right marker"
* 【★】「折り返しなし」は「 0 」で、「ワード毎」は「 1 」、そして「文字毎」が「 2 」です。折り返しは通常ウインドウの右端で行なわれます──が、もしルーラーがアクティブになっている場合には「右マーカー」の位置で折り返します。

* ［☆］Witten also added the command "Hard Wrap". If a paragraph is selected, this command inserts hard wrapping commands at the right side of this paragraph. After this step, resizing the window leaves the wraps fixed. This is useful if you send source to a colleague whose editor has fixed width and no wrapping. If the "Hard Wrap" command is chosen but no selection has been made, the hard wrap applies to the entire document. Note that "Hard Wrap" is undoable.
* 【★】Witten さんはまた「改行を挿入」コマンドも追加してくれました。段落を選択している場合、このコマンドにより段落の右端に改行が挿入されます。この後でウインドウをリサイズしても折り返し位置はそのまま残ります。これが便利なのは、たとえば仲間にソースを送るとして、先方のエディタの幅が固定されていて折り返しがないようなときでしょう。「改行を挿入」コマンドを実行する際に選択部分がなければ、文書全体にわたってハードラップがかけられます。注意したいのは、「改行を挿入」はアンドゥがきかないということです。

* ［☆］The TeXShop Application Bundle now contains Norman Gall's TeX-mdimporter Spotlight importer. Files with extensions .tex, .latex, .ltx, .ctx. and .texi will be indexed by Spotlight when saved. In systems 10.4 through 10.4.2, TeXShop files were automatically indexed because they have type TEXT, but Apple changed this procedure in 10.4.3. So the importer is now required to index files. The system automatically recognizes the importer when TeXShop is first installed. It is then used to index .tex, .ltx, etc. files even if TeXShop is not running.
* 【★】TeXShop のアプリケーションバンドルに Norman Gall さんの TeX-mdimporter が入りました。ファイルの拡張子が .tex・.latex・.ltx・.ctx・texi であれば、保存時に Spotlight によって索引が作成されます。システム 10.4 から 10.4.2 までは、ファイルタイプが TEXT なので TeXShop ファイルは自動的に索引が作成されていましたが、10.4.3 で Apple がやり方を変えてしまいました。なので索引作成にインポーターが必要となったのです。TeXShop をインストールする際に、システムが自動でインポーターを認識します。そしてそれ以降、TeXShop が起動しておらずとも .tex や .ltx などのファイルの索引作成に利用されます。

* ［☆］If Gall later updates the importer and you install the new version in ~/Library/Spotlight or other canonical spots, the updated version will be used rather than the version in the TeXShop bundle because Apple's importer search routines use importers in bundles as a last resort.
* 【★】もし後々 Gall さんがインポーターをアップデートし、ユーザが新しいバージョンを ~/Library/Spotlight やその他の標準的な場所にインストールした場合には、TeXShop のバンドルに含まれているバージョンではなく、アップデートされたバージョンの方が使用されます──というのも Apple のインポーター検出ルーチンは、バンドルに含まれるインポーターについては最後の手段として用いるからです。

* ［☆］Gall's importer was not written with TeXShop in mind, but is instead designed to be used by all TeX editors and front-ends; the hope is that there will be a universal importer rather than a different one for each front end. For the latest version, see http://www.spookyhill.net/~gall/latex.
* 【★】Gall さんのインポーターは TeXShop を念頭に置いて書かれているわけではありませんが、その代わりにすべての TeX エディタやフロントエンドで利用できるように設計されています；普遍的なインポーターの方が、それぞれのフロントエンド用に特化したものよりも望ましいでしょう。最新版については http://www.spookyhill.net/~gall/latex をご覧ください。

* ［☆］The commands "altpdftex" and "altpdflatex" in Gerben Wierda's TeX distribution have changed to "simpdftex tex" and "simpdftex latex". These are now the default preference values for new TeXShop installations.
* 【★】Gerben Wierda さんの TeX ディストリビューションに含まれていた altpdftex, altpdflatex の２つのコマンドが、simldftex tex と smpdftex latex に変更されています。TeXShop でも、これらのコマンドをデフォルトの設定値に変更しました。

* ［☆］Moreover, the first time a user tries to typeset in the "tex + ghostscript" mode, TeXShop will check these preference items, and change them if necessary. It does this by determining whether "simpdftex" is in the TeX binary directory. If so, and if the command in the TeX + dvips + distiller "TeX Program" field in the TeXShop Engine Preferences is "altpdftex", then this field is changed to "simpdftex tex". Any additional flags in the preference field are retained. At the same time, the "Latex Program" field is changed. If it is "altpdflatex", it is changed to "simpdftex latex", retaining any additional flags.
* 【★】さらに、ユーザが「TeX＋Ghostscript」モードで最初にタイプセットを試みる際に、TeXShop が上記の設定項目をチェックし、必要であれば変更しておきます。この動作の実行は TeX バイナリのディレクトリにおける「simpdftex」の有無によって判定します。もし「simpdftex」があり、「TeXShop 環境設定」の「内部設定」で、「TeX + dvips + distiller」の欄が「altpdftex」になっていれば、「simpdftex tex」へと書き換えられます。環境設定内であらかじめ変更を加えてあった箇所についてはそのままにしておきます。同時に「LaTeX プログラム」欄も書き換えられます。もしも「altpdflatex」になっていれば「simpdftex latex」へと書き換えられますが、あらかじめ変更してあった箇所についてはそのままにしておきます。

* ［☆］Added ISO Latin 9 encoding
* 【★】ISO Latin 9 エンコーディングを追加しました。

* ［☆］Now (apple)-[ and (apple)-] act differently in the editing window and preview window. In the editing window they are "unindent" and "indent". In the preview window they are "back" and "forward". A disadvantage is that it was not possible to add these commands to the menus, so users need to remember these abbreviations. This change was requested by users with German and other keyboards on which (apple)-< and (apple)-> cycle through windows. Users with English keyboards cycle through windows with (apple)-`.
* 【★】コマンド＋「 [ 」およびコマンド＋「 ] 」について、ソースウインドウとプレビューウインドウとでは別々の動作をするようにしました。ソースウインドウ内では「左シフト」と「右シフト」となります。プレビューウインドウ内では「戻る」と「進む」です。デメリットとしては、これらのコマンドをメニューに付け加えられないので、ユーザがショートカットを覚えておかなければなりません。この変更はドイツ語版およびその他のキーボードで、コマンド＋「 < 」およびコマンド＋「 > 」がウインドウの巡回に割り当てられいるユーザの要望によるものでした。英語版キーボードのユーザは、ウインドウの巡回にはコマンド＋「 ` 」が割り当てられています。

* ［☆］Added a new hidden preference
* 【★】新しい隠れた環境設定を追加しました

	defaults write TeXShop LeftRightArrowsAlwaysPage YES

* ［☆］The default value is NO. When set to YES, the left and right arrows scroll by a page even if the horizontal school bar is active.
* 【★】デフォルトの値は NO です。YES にすると、水平スクロールバーが表示されていても、左矢印・右矢印でページごとにスクロールします。

* ［☆］Changed the English under the Preview tab of Preferences from "After Window Review" to "Magnification Style" and changed "Preview Window Magnification" to "Preview Window Fixed Magnification" to more carefully explain the function of these preference items. Notice that TeXShop only uses the Preview Magnification value if the Magnification Style has been set to "Fixed Magnification".
* 【★】「環境設定」の「プレビュー」タブ内の英語表記を「After Window Review」から「Magnification Style」にし、「Preview Window Magnification」を「Preview Window Fixed Magnification」に変更することで、これらの環境設定項目の機能をより詳しく言い表わすようにしました。注意してほしいのは、TeXShop が「プレビューウインドウの倍率」の数値を利用するのは「ウインドウのリサイズ後」の項目が「固定倍率」に設定されている時だけだということです。

* ［☆］Added a new item
* 【★】新しい項目を追加──

	%!TEX projectfile =

* ［☆］which can be added to the top of TeX source files. This change is primarily for ConTeXt users so they can use the new sync method. When synching from the preview window to the source window, TeXShop needs to know all sources file for the document being previewed so it can open source files not currently open if necessary. It does this by parsing the root document, looking for \include and \input lines. But ConTeXt uses different commands to input files. The new syntax allows ConTeXt users to directly indicate in the root document which additional source files need to be searched. Here are examples:
* 【★】これは TeX のソースファイルの冒頭に付記できます。この変更は主に ConTeXt ユーザが新しい方式のシンクロナイゼーションを利用できるようにするためのものです。プレビューウインドウからソースウインドウへのシンクロの際、TeXShop は、まだ開かれていないソースファイルを必要に応じて開けるようにするために、プレビュー中の文書に関連するソースファイルをすべて把握しておく必要があります。これはルートファイルを解析し、\include と \input のある行を見つけることで行なっています。けれども ConTeXt では、ファイルを挿入するのに異なるコマンドを用いています。新しい構文では、検索に必要な追加のソースファイルを、ConTeXt ユーザがルートファイル内で直接指示できるようになります。以下に例を挙げておきます──

	%!TEX projectfile = /Users/koch/MyDoc/chapter1.tex
	%!TEX projectfile = chapter2.tex
	%!TEX projectfile = ../chapter3.tex

* ［☆］Added .Rnw as an extension TeXShop can edit. This was a request of Paolo Bosetti, who uses TeX and R and Sweave together.
* 【★】「.Rnw」を TeXShop で編集できる拡張子として追加しました。これは Paolo Bosetti さんの要望でしたが、彼は TeX と R と Sweave をいっしょに使っています。

* ［☆］When a user tries to open a .dvi file, TeXShop runs a script to convert the dvi file to a pdf file. In previous versions, it ran a different script when the .dvi was in a writable directory than when its directory was not writable. But Gerben Wierda has revised the simpdftex script to handle both cases, so now TeXShop always calls simpdftex to do the conversion. Actually it calls the TeX + dvips + distiller script which is set in Preferences; this preference will be simpdftex if the user has a fairly recent TeX distribution.
* 【★】ユーザが拡張子「.dvi」のファイルを開こうとすると、TeXShop は DVI ファイルを PDF ファイルに変換するスクリプトを走らせます。以前のバージョンでは、「.dvi」ファイルが書き込み可能なディレクトリにある場合と書き込み不可のディレクトリにある場合とでは異なるスクリプトを実行していました。けれども Gerben Wierda さんが simpdftex のスクリプトを改善して両方のケースを扱えるようにしたので、TeXShop では変換するにあたって常に simpdftex をコールするようになりました。実を言えば「環境設定」で設定した「TeX + dvips + distiller」のスクリプトをコールしているわけです──ユーザがごく最近の TeX ディストリビューションを持っていれば、この環境設定は simpdftex になっていることでしょう。

* ［☆］Added a new hidden Preference
* 【★】新しい隠れた環境設定を追加しました──

	defaults write TeXShop RedConsoleAfterError NO

* ［☆］If this default is YES, then after the first error the remaining text in the console will be red. The default value is NO.
* 【★】この初期値が YES ならば、コンソールの最初のエラー部分より後ろのテキストは赤色で表示されます。デフォルト値は NO です。

* ［☆］Slightly modified the appearance of the Console window, particularly in English. More work is needed here. Note that the console window can be resized and relocated, and the system will remember this new size and location when TeXShop is restarted.
* 【★】コンソールウインドウのアピアランスを微妙に修正しました──とりわけ英語表記ですが。これについてはさらなる作業が必要とされています。コンソールウインドウはサイズが変更でき、場所も移動できますが、TeXShop を再起動してもシステムは変更後のサイズと場所を覚えていることに注意してください。

* ［☆］In version 2.05, fixed "undo past a save" using the new Tiger command [textView breakUndoCoalescing]. Previous versions of TeXShop allowed users to undo past a save command. But this required "tricky code" and one effect of the trick was that TeXShop sometimes lost track of whether the current state of the document had previously been saved, and so didn't save the document before typesetting, giving strange results in the preview window.
* 【★】バージョン 2.05 では、「最後に保存した状態に戻す」について、Mac OS X Tiger の新しいコマンド「textView breakUndoCoalescing」を利用して修正しました。以前のバージョンのTeXShop でも、最後に保存した状態に戻せるようにするコマンドは使えました。けれどもこれには「トリッキーなコード」が必要で、このトリックの影響のひとつとして TeXShop はたまに、文書の現在の状態が既に保存したものだったかどうかわからなくなり、タイプセットする前に保存をしないことがあり、プレビューウインドウに表示される結果が変になっていました。

* ［☆］Versions 2.00 through 2.04 of TeXShop sometimes had trouble remembering new preference settings; it was necessary to set them several times before they "took." This is fixed.
* 【★】バージョン 2.00 から 2.04 までの TeXShop では時おり、新しい環境設定を覚えておくという厄介事がありました──「定着」するまで何度か設定してやる必要があったのです。これを修正しました。


###──New features in 1.42 and 2.05（バージョン 1.42 と 2.05 共通の新機能）：

* ［☆］The commands "altpdftex" and "altpdflatex" in Gerben Wierda's TeX distribution have changed to "simpdftex tex" and "simpdftex latex". These are now the default preference values for new TeXShop installations.
* 【★】Gerben Wierda さんの TeX ディストリビューションに含まれている "altpdftex" と "altpdflatex" のコマンドが、それぞれ "simpdftex tex" と "simpdftex latex" に変更されています。TeXShop を新しくインストールした場合は、これらのコマンドがデフォルトで設定されるようになりました。

* ［☆］Moreover, the first time a user tries to typeset in the "tex + ghostscript" mode, TeXShop will check these preference items, and change them if necessary. It does this by determining whether "simpdftex" is in the TeX binary directory. If so, and if the command in the TeX + dvips + distiller "TeX Program" field in the TeXShop Engine Preferences is "altpdftex", then this field is changed to "simpdftex tex". Any additional flags in the preference field are retained. At the same time, the "Latex Program" field is changed. If it is "altpdflatex", it is changed to "simpdftex latex", retaining any additional flags.
* 【★】さらに、ユーザが「TeX＋Ghostscript」モードで最初にタイプセットを試みる際に、TeXShop が上記の設定項目をチェックし、必要であれば変更しておきます。この動作の実行は TeX バイナリのディレクトリにおける「simpdftex」の有無によって判定します。もし「simpdftex」があり、「TeXShop 環境設定」の「内部設定」で、「TeX + dvips + distiller」の欄が「altpdftex」になっていれば、「simpdftex tex」へと書き換えられます。環境設定内であらかじめ変更を加えてあった箇所についてはそのままにしておきます。同時に「LaTeX プログラム」欄も書き換えられます。もしも「altpdflatex」になっていれば「simpdftex latex」へと書き換えられますが、あらかじめ変更してあった箇所についてはそのままにしておきます。

* ［☆］Added ISO Latin 9 encoding
* 【★】ISO Latin 9 エンコーディングを追加しました。

* ［☆］New German localization and help files.
* 【★】新しいドイツ語ローカライズとヘルプファイル。

* ［☆］New Japanese Help by Yoshihisa Okazaki with help from Seiji Zenitani.
* 【★】銭谷誠司さんから助力を得た岡崎祥久さんによる新しい日本語ヘルプ。

* ［☆］New Spanish help files and localization.
* 【★】新しいスペイン語ヘルプファイルとローカライズ。

* ［☆］Uses version 1.2.4 of OgreKit.
* 【★】バージョン 1.2.4 の OgreKit を使用。

* ［☆］Conversion of eps, ps, and dvi files to pdf (caused by opening such a file) now works even if the path to the file has folders whose names contain spaces. In all three cases, the file can now be in a folder without write permission.
* 【★】ファイルパスのフォルダ名にスペース文字が含まれている場合も、eps, ps, dvi ファイルを pdf に変換できるようになりました。この変換機能は、これらのファイルをダブルクリックで開いたときに動作します。書き込み権限のないディレクトリにファイルがある場合も、pdf への変換が動作するようになりました。

* ［☆］Trash AUX files now removes files with more extensions: cos, idv, 4ct, 4tc, lg, xref, ttt, fff, ent, wrm.
* 【★】「作業ファイルを除去」によって取り除かれるファイルの拡張子を追加：cos・idv・4ct・4tc・lg・xref・ttt・fff・ent・wrm 。

* ［☆］If the user tries to open a file with UTF-8 Unicode encoding, but the file is not a legal utf8 file, a dialog now appears warning of the problem, and the file is opened with MacOSXRoman encoding.
* 【★】ユーザが UTF-8 Unicode エンコーディングのファイルを開こうとしても、そのファイルがきちんとした UTF-8 ファイルではなかった場合には、問題を告げるダイアログが表示され、ファイルは MacOSXRoman エンコーディングで開かれるようにしました。

* ［☆］Bib files are promoted to full class citizens; text can be dragged to them, syntax coloring works, etc.
* 【★】Bib ファイルの処遇を向上させました──テキストをドラッグできるようにする、シンタックス・カラーリングを機能させる、等々。

* ［☆］A remark: users have reported that they can no longer "find" words in the console window. Actually, they can. This window has two portions. When typesetting ends, the bottom portion is active, so the find panel searches that portion. To activate the top, click on it. Then "find" works.
* 【★】ひとこと：コンソールウインドウ内で語句を「検索」することができなくなったとの報告がユーザから寄せられました。でも実際のところは、検索できます。このウインドウは２つの部分から成り立っています。タイプセットが終了した時点では、下側の部分がアクティブになっていますから、検索パネルはこの部分を検索対象にします。上の部分をアクティブにするには、一度クリックしておきます。そうすれば「検索」が機能します。

* ［☆］Added a preference to control first mouse behavior: "Select on Activate." When this is YES, a click in the source window will also set the insertion point to the click point. If it is NO, a second click is required to change the insertion point.
* 【★】マウスの初動をコントロールする環境設定項目を追加しました。「選択時にカーソルを移動」がそうです。もしこれにチェックが入っていれば、ソースウインドウをクリックした際に、クリックをした位置に挿入ポイントが置かれます。もしチェックが入っていなければ、もう一度クリックして挿入ポイントを移動させることになります。

* ［☆］Added pdf to the types of files TeXShop can edit, and added a pdf icon. This allows TeXShop to be chosen as the default pdf viewer.
* 【★】TeXShop で編集可能なファイルタイプに pdf を追加し、pdf アイコンも追加しました。これにより TeXShop をデフォルトの PDF ビューワに指定することができるようになりました。

* ［☆］Added Lilypond, abc, and bst as extensions that can be edited.
* 【★】Lilypond・abc・bst を編集可能な拡張子として追加しました。

* ［☆］Added code by David Reitter so that selecting the word \int, etc., selects the beginning "\" as well.
* 【★】David Reitter さんのコードを追加することで、\int 等の語の選択において、最初の「\」も選択に含まれるようになりました。


###──Bugs fixed in 1.42 and 2.05（バージョン 1.42 と 2.05 でのバグ修正）：

* ［☆］Japanese Image Copy Type Preference failed due to incorrect localization. Now fixed.
* 【★】日本語環境では、環境設定項目の「コピー」項目がローカライズ時の手違いで動作しませんでした。この件を修正しました。

* ［☆］Command Completion's configuration file is now loaded and saved in UTF-8 Unicode.
* 【★】コマンド補完用の設定ファイルが UTF-8 Unicode で読み出され保存されるようになりました。

* ［☆］Errors fixed in pdfsync.
* 【★】pdfsync におけるエラーを修正しました。

* ［☆］When typesetting engines are called, they are now passed the program filename with extension, rather than just the filename.
* 【★】タイプセットエンジンをコールする際に、たんにファイル名だけでなく、拡張子付きのファイル名を渡すようにしました。

* ［☆］In 1.35, it was only possible to switch between the OgreKit Find panel and the Apple Find panel in the English localization. This is fixed.
* 【★】バージョン 1.35 では、OgreKit の検索パネルと Apple の検索パネルとの切り替えが、英語版ローカライズでのみ可能でした。これを修正しました。

* ［☆］The menu item to bring up the statistics panel was only in the English version. Now it is in all versions.
* 【★】統計パネルを取り出すためのメニュー項目が英語版にしかありませんでした。これがすべてのバージョンで利用可能となりました。

* ［☆］In all display modes except single page mode, a black border is drawn around each pdf page. Previously this border was slightly inside the page, cutting off a slight border around the page. Now it is just outside the page. Thanks to Scott Ranby for pointing out this error.
* 【★】「ページレイアウト」が「単一ページ」以外のモードになっていると、各 PDF ページの周囲に黒い境界線が引かれます。以前はこの境界線がわずかにページ内に食い込んでおり、ページの周囲を微妙にへずっていました。今ではページのちょうど外側になっています。このエラーを指摘してくれた Scott Ranby さんに感謝。

* ［☆］The "%!TEX TS-program" and "%!TEX root =" commands now when when used with an external editor.
* 【★】コマンド「%!TEX TS-program」と「%!TEX root =」を外部エディタで利用できるようにしました。


##Version 1.41 ＆ 2.04

* ［☆］These versions of TeXShop are in the first release of the TeX install package MacTeX.pkg, but were never otherwise released.
* 【★】バージョン1.41 と 2.04 の TeXShop は、TeX インストールパッケージ「MacTeX.pkg」の最初のリリースに同梱されていますが、それ以外では公開されませんでした。


##Version 1.40 ＆ 2.03

###──Changes in 2.03（バージョン 2.03 での変更点）

* ［☆］Improved the PDFsearch code (i.e., sync) for \include{file}, \input{file}, and \import{file}. Users who had trouble using sync with large projects may find that it works now.
* 【★】PDF 検索（つまりシンクロ）のコードを改善し、\include{file}・\input{file}・\import{file} に対応しました。規模の大きなプロジェクトでシンクロナイゼーションを利用してトラブルに見舞われていたユーザは、これが機能するようになったことに気付くかもしれません。

* ［☆］When the Find panel is opened with command-F, the previous search phrase is now hilighted so users can erase it by just typing a new search phrase.
* 【★】コマンド＋Ｆで検索パネルを開いた際、前回の検索語句がハイライト表示されるようになったので、新しい検索語句をタイプするだけで書き換えることができます。

* ［☆］Command-left-arrow and command-right-arrow perform page up and page down when the Preview window is open, but they now move the editor to the start or end of the current line, restoring a keyboard shortcut which was inadvertently broken in 2.01.
* 【★】コマンド＋左矢印（⌘＋←）とコマンド＋右矢印（⌘＋→）は、プレビューウインドウが開いている際にはページアップとページダウンとして動作しますが、エディタでは行頭・行末への移動となります──バージョン 2.01 でうっかり除いてしまったキーボードショートカットを復元しました。

* ［☆］New Spanish localization and Spanish Help by Juan Luis Verona.
* 【★】Juan Luis Verona さんによる新しいスペイン語ローカライズとヘルプ。

* ［☆］Additions to the German localization by Martin Kerz.
* 【★】Martin Kerz さんによるドイツ語ローカライズへの追加修正。


###──Changes in 1.40（バージョン 1.40 での変更点）

* ［☆］When the Find panel is opened with command-F, the previous search phrase is now hilighted so users can erase it by just typing a new search phrase.
* 【★】コマンド＋Ｆで検索パネルを開いた際、前回の検索語句がハイライト表示されるようになったので、新しい検索語句をタイプするだけで書き換えることができます。


##Version 1.39 ＆ 2.02

###──Changes in 2.02（バージョン 2.02 での変更点）

* ［☆］Added command left arrow for previous page, command right arrow for next page, command [ for back, and command ] for forward. These keyboard shortcuts are also used by Apple's Preview. To make room for these shortcuts, the shortcuts for indent and unindent were changed to command < and command >, and the shortcuts for comment and uncomment were changed to command { and command }.
* 【★】ショートカットキーを追加しました──コマンド＋左カーソルキーで前ページへ移動、コマンド＋右カーソルキーで次ページへ移動、コマンド＋「 [ 」キーで「戻る」、コマンド＋「 ] 」キーで「進む」となります。上記のショートカットキーはアップルのプレビュー（Preview.app）でも用いられています。この追加に伴い、「行を右シフト」と「行を左シフト」のショートカットキーはそれぞれコマンド＋「 < 」とコマンド＋「 > 」へと変更され、「コメント」と「コメントを外す」はそれぞれコマンド＋「 { 」とコマンド＋「 } 」とに変更されました。

* ［☆］The left and right arrows scroll left and right if the horizontal scroll bar is active, but page up and down otherwise. This behavior copies the behavior of Apple's Preview.
* 【★】水平方向のスクロールバーがアクティブになっているときには、左右のカーソルキーはそれぞれ左右へのスクロールとなりますが、そうでないときには上下のページ移動となります。この動作はアップルのプレビュー（Preview.app）に倣ったものです。

* ［☆］When the cursor is over a link in the Preview window, clicking on the link will activate the link regardless of the active tool at that moment.
* 【★】プレビューウインドウでリンク箇所をクリックしたときは、使用中のツールの種類（スクロールやテキスト、拡大鏡ツールなど）に関わらず、リンク先にジャンプするようになりました。

* ［☆］The magnification toolbar item and page number toolbar item now have no surrounding outline, so they shrink to small size and look cleaner than before.
* 【★】ツールバー項目の「倍率」と「ページ」の背景の囲みをなくしましたので、サイズも小さくなり、以前よりハッキリと見えるようになりました。

* ［☆］Enlarged the number of files searched by the new sync method from 20 to 60.
* 【★】新しいシンクロナイゼーション方法で検索するファイルの数を 20 から 60 に増やしました。

* ［☆］Fixed OgreKit permissions.
* 【★】OgreKit のパーミッションを修復。

* ［☆］Japanese Localization by Yoshihisa Okazaki.
* 【★】岡崎祥久さんによる日本語版ローカライズ。

###──Changes in 1.39（バージョン 1.39 での変更点）

* ［☆］Japanese Localization by Yoshihisa Okazaki.
* 【★】岡崎祥久さんによる日本語版ローカライズ。

* ［☆］Spanish localization by Juan Luis Varona Malumbres.
* 【★】Juan Luis Varona Malumbres さんによるスペイン語版ローカライズ。

* ［☆］Fixed OgreKit permissions
* 【★】OgreKit のパーミッションを修復。


##Version 1.38 ＆ 2.01

###──Changes in 2.01（バージョン 2.01 での変更点）

* ［☆］A missing default preference caused the background color of the pdf window to be black. This is fixed.
* 【★】デフォルトの設定の欠落により PDF ウインドウの背景色が黒くなっていました。これを修正。

* ［☆］The beachball could appear after typesetting a document, causing a substantial delay before the editor became accessible. Fixed.
* 【★】書類のタイプセット後にビーチボールが現われ、エディタが使えるようになるまでに相当の遅れの出ることがありました。修正しました。

* ［☆］The preference to set the location and size of the preview window broke. Now fixed.
* 【★】プレビューウインドウの位置とサイズを定める環境設定が壊れていました。修正済みです。

* ［☆］Changing the default magnification did not immediately change the magnification in open windows. Fixed.
* 【★】デフォルトの倍率を変更しても、開いているウインドウでは即座に変更されませんでした。修正しました。

* ［☆］Dragging a portion of text from one spot of the source to another broke. This is fixed.
* 【★】ソースコードのテキストの一部を、ある箇所から別の箇所にドラッグする操作が Tiger ではうまく動作しませんでした。これを修正。

* ［☆］TeXShop and TeXShop Help are now localized in German.
* 【★】TeXShop および TeXShopヘルプがドイツ語にローカライズされました。

* ［☆］The twelve point book heading macro contained a spurious letter. This is fixed for new users, but other users need to remove the letter using the Macro editor.
* 【★】マクロ > Headings > 12pt > book ──つまり、文字サイズ 12 ポイントの「book」クラスのヘッダを挿入するマクロに、誤った文字が入っていました。新規ユーザであればこれは修正されていることになりますが、それ以外のユーザはマクロエディタを使ってこの文字を取り除いておく必要があります。


###──Changes in 1.38（バージョン 1.38 での変更点）

* ［☆］Dragging a portion of text from one spot of the source to another broke in Tiger. This is fixed.
* 【★】ソースコードのテキストの一部を、ある箇所から別の箇所にドラッグする操作が Tiger ではうまく動作しませんでした。これを修正。

* ［☆］Minor additions were made to the German localization.
* 【★】ドイツ語版ローカライズにいくらか追加が行なわれました。

* ［☆］The twelve point book heading macro contained a spurious letter. This is fixed for new users, but other users need to remove the letter using the Macro editor.
* 【★】マクロ > Headings > 12pt > book ──つまり、文字サイズ 12 ポイントの「book」クラスのヘッダを挿入するマクロに、誤った文字が入っていました。新規ユーザであればこれは修正されていることになりますが、それ以外のユーザはマクロエディタを使ってこの文字を取り除いておく必要があります。


*ヘルプファイルから削除した昔の更新履歴

##Version 1.37 ＆ 2.00

［☆］Versions 1.37 and 2.00 add extra features to TeXShop and fix some bugs.

【★】バージョン 1.37 と 2.00 では TeXShop にさらなる機能を追加し、いくつかのバグを修正しました。

###──New features in 2.00（バージョン2.00のみの新機能）

* ［☆］A new synchronization method has been added to TeXShop, using the ability in Tiger to search for strings in pdf files. The new method does not require including a pdfsync.sty file, so it works out of the box on files typeset using any engine: pdftex or pdflatex, TeX + ghoscript or LaTeX + ghostscript, XeTeX, and other engines.
* 【★】シンクロナイゼーションの新しい手法を TeXShop に追加しました── これは PDF ファイル内の文字列を検索する Tiger の機能を利用しています。 この新しい手法では pdfsync.sty を必要としないので、 どのエンジンを使ってファイルをタイプセットしてあってもうまく機能します： pdfTeX・pdfLaTeX・TeX＋Ghostscript あるいは LaTeX＋Ghostscript ないしは XeTeX その他のエンジンでも。

* ［☆］Click on a word or phrase in the source file. TeXShop will scroll the preview window to the corresponding phrase and circle it in red. Click on a word or phrase in the preview window. TeXShop will open the corresponding source file if it is not already open, scroll the source to the appropriate spot, and highlight the source phrase in yellow.
* 【★】ソース文書内で単語ないしは語句をクリックします── TeXShop は対応する語句までプレビューウインドウをスクロールさせ、赤で丸を付けます。 プレビューウインドウ内で単語ないしは語句をクリックします── TeXShop は（それがまだ開かれていなければ）対応するソースファイルを開き、 適切な位置までソースをスクロールさせ、 ソース内の語句を黄色でハイライトします。

* ［☆］A new TeXShop preference item selects the synchronization method to be used: the old pdfsync method, the new search method, or a combination in which the new search is used, but the program falls back on pdfsync if the new search does not succeed.
* 【★】新しい TeXShop の環境設定項目では、 利用するシンクロナイゼーションの方式を選択できます： 従来の pdfsync 方式、新しい検索方式、 あるいはその組み合わせ—— 新しい検索方式が用いられものの、 うまくゆかない場合には pdfsync をあてにすることができる、というもの。

* ［☆］TeXShop 2.00 uses Apple's PDFKit to display the pdf preview window. This software is introduced in system 10.4.0 (Tiger), so TeXShop 2.00 requires Tiger. PDFKit makes the following new features possible:
* 【★】eXShop 2.00 では、 pdf プレビューウインドウの表示に Apple の PDFKit を利用しています。 このソフトウェアはシステム 10.4.0（Tiger）で導入されました。 PDFKit によって、以下のような新機能が利用可能になります：

* ［☆］TeXShop supports hyperlinks. To activate this feature, add the line
* 【★】TeXShop はハイパーリンクおよび TeX の hyperref パッケージをサポートします。 この機能を有効にするには、 次のような１行をソース文書のヘッダ部分に追加します。

	\usepackage[colorlinks=true, pdfstartview=FitV, linkcolor=blue, citecolor=blue, urlcolor=blue]{hyperref}

* ［☆］to the heading of the source document. Links to external web sites can then be added to tex documents using commands like
* 【★】外部のウェブサイトへのリンクを TeX 文書に付け加えるには、 次のようなコマンドを使います。

	\href{http://www.uoregon.edu/~koch/}{Koch homepage}

* ［☆］Links to other portions of the tex document can be added using commands like
* 【★】TeX 文書内の別の箇所へリンクさせるには、 以下のようなコマンドを使います。

	\hyperlink{lemniscate}{Graph of Lemniscate}

* ［☆］where the tag "lemniscate" is created using a command like
* 【★】"lemniscate" というタグの位置は、 下記のようなコマンドを使って作成します。

	\hypertarget{lemniscate}{}

* ［☆］To navigate with these links, choose the new "text" tool and clink on the colored links.
* 【★】こうしたリンクを利用して移動を行なうには、 新しい「テキスト」ツールを選択した上で色の付いたリンク部分をクリックします。

* ［☆］The preview window toolbar contains "Back" and "Forward" buttons so one can jump to a spot using a link, and then jump back.
* 【★】プレビューウインドウのツールバーに、 「戻る」「進む」というボタンがあるので、 リンク先に移動した後でもすぐに戻ることができます。

* ［☆］Hyperref.sty automatically adds links to citations, so readers can rapidly jump from a citation to the corresponding bibliography entry.
* 【★】hyperref.sty は引用部分に自動でリンクを追加するので、 読者は引用部分から参考文献目録の項目へと即座にジャンプすることができます。 目次へのリンクも自動で付け加えられるので、 読者は対応するセクションにジャンプすることができます。

* ［☆］The hyperref package also creates a document outline. For example, the main outline of a book is a list of chapters; each chapter entry contains a list of sections, and so forth. To see this outline and navigate through the document with it, use the new "drawer" tool to display the pdf window's drawer.
* 【★】hyperref パッケージは文書のアウトラインを生成します。 たとえば、 書籍の主要なアウトラインはチャプターの一覧です； そして各チャプターにはセクションの一覧が含まれる、などなど。 このアウトラインを参照し、文書内を移動するには、 新しい「ドロワー・ツール」を使ってプレビューウインドウのドロワーを表示させます。

* ［☆］The text tool can be used to select a portion of text in the preview window and copy this selection to an editor. This differs from the "pdf selection tool" which copies a portion of the document as a pdf illustration --- the text tool copies editable text.
* 【★】テキストツールを使ってプレビューウインドウ内のテキストの一部分を選択できますが、 この選択部分はエディタにコピーすることができます。 このテキストツールでは「PDF選択ツール」とは異なり、 文書の一部を pdf 形式の図像としてコピーするのではなく、 編集可能なテキストとしてコピーします。

* ［☆］Searching the pdf preview is supported. Use the search tools in the bottom half of the window's drawer.
* 【★】pdf プレビューの検索をサポートしました。 プレビューウインドウのドロワーの下方にある検索ツールを用いてください。

* ［☆］PDFKit brings additional polish to the display of pdf documents. It supports documents with isolated rotated pages, and correctly prints rotated pages in landscape mode. It supports liveupdate of window resizing if the magnification preference is set to "fit to window." Etc.
* 【★】PDFKit により PDF 文書の表示がさらに洗練されました。 個別に回転させたページを含む文書をサポートし、 横置きモードでも回転させたページをきちんと印刷できます。 また、ズーム倍率を「ウインドウに合わせる」に設定しておけば、 ウインドウをリサイズする際のライプ・アップデートもサポートします。 さらに、キーボード・ショートカットのサポートも向上しています： カーソルキー、page up キーや page down キーなどです。


###──New features in 2.00 and 1.37（バージョン2.00と1.37共通の新機能）

［☆］The remaining new features are available in both new versions.

【★】残りの新機能は 2.00 と 1.37 いずれでも利用可能です。

* ［☆］Earlier versions of TeXShop allowed users to set the typesetting engine of a file, its encoding, and its root file by adding appropriate comments to the top of the source file. For example, the following commands set the typesetting engine to xelatex, the encoding to UTF-8 Unicode, and the root file to ../Main.tex:
* 【★】以前のバージョンの TeXShop では、 文書のタイプセット・エンジン、 エンコーディング方式、 ルートファイルを設定するのに、 ソースファイルの冒頭にしかるべきコメントを付加していました。 たとえば、 以下の一連のコマンドは、 タイプセット・エンジンを XeLaTeX に、 エンコーディングを UTF-8 Unicode に、 ルートファイルを ../Main.tex に設定するものでした：

	%&xelatex
	%&encoding= UTF-8 Unicode
	%SourceDoc ../Main.tex

* ［☆］But this syntax was a mistake because the symbols "%&" are reserved for the use of TeX.
* 【★】けれどもこの構文は誤りでした—— というのも「%&」という記号は、 TeX で使用するため予約済みだったのです。

* ［☆］In versions 1.37 and 2.00 of TeXShop, the syntax has been changed to the following:
* 【★】バージョン 1.37 と 2.00 の TeXShop では、 以下のように構文を変更しました：

	%!TEX TS-program = xelatex
	%!TEX encoding = UTF-8 Unicode
	%!TEX root = ../Main.tex

* ［☆］It you used the earlier facility, you need to change your old source files to the new syntax. I'm very sorry to cause this work, but the change is really necessary.
* 【★】この機能を利用していた人は、 これまでのソースファイルを新しい構文に変更する必要があります。 このような作業をしてもらわねばならないのは心苦しいことですが、 ほんとうに必要な変更なのです。

* ［☆］If you are in the middle of a project and cannot make the change now, you can temporarily set a hidden preference to revert to the old syntax. To do so, open Apple's Terminal program and type
* 【★】もしもプロジェクトの最中で今すぐ変更ができない場合は、 隠れた環境設定で一時的に古い構文に戻すことができます。 戻すには、Terminal を起動して次のようにタイプします——

	defaults write TeXShop UseOldHeadingCommands YES

* ［☆］Once this is done, the new commands will be recognized but the old commands will also work. However, I recommend turning this preference off as soon as possible.
* 【★】こうすれば、 新しいコマンドが認識されるだけでなく、 古いコマンドも同様に機能します。 ですが、 この環境設定はなるべく早いうちにオフにするようにしてください。

* ［☆］Commands have been added to the default Macros menu which insert the symbols "%!TEX TS-program = " and "%!TEX encoding = " and "%!TEX root = " into the source document; new users will see these entries. Users who are upgrading can easily add these symbols as well. To add the program entry, choose "Open Macro Editor" under the Macro menu. Click the "New Item" button, name the item "Program" and set its content to
* 【★】「%!TEX TS-program = 」 「%!TEX encoding = 」 「%!TEX root = 」 という符号をソース文書に挿入するコマンドを、 デフォルトのマクロメニューに追加しました； 新規のユーザはこれらの項目を確認できることでしょう。 アップグレードしたユーザもまた容易に追加できます。 「プログラム」という項目を追加するには、 「マクロ」メニューから「マクロエディタを開く...」を選択して、 「新規マクロ」ボタンをクリックし、 項目名を「プログラム」として内容を以下のように設定します——

	%!TEX TS-program = #INS#

* ［☆］Repeat for the "Encoding" and "Root" items.
* 【★】「エンコーディング」と「ルート」についても同様にします。

* ［☆］Martin Kerz added a "Check for Updates..." command to TeXShop. He also designed the new TeXShop web page. Thanks!
* 【★】Martin Kerz により「アップデートを確認...」というコマンドが TeXShop に追加されました。 彼はまた TeXShop の新しいウェブサイトのデザインも手がけました。 ありがとう！

* ［☆］OgreKit for searching has been upgraded to the latest 2.0.1 version.
* 【★】検索用の OgreKit を最新のバージョン 2.0.1 にアップグレードしました。

* ［☆］Additional filetypes can be edited, including files with extensions "abc", "bst", "bib", "lp", and "pdf". The addition of "pdf" allows TeXShop to be chosen as the default pdf viewer. A new pdf icon has been created so the system can use it on pdf files it will display in TeXShop.
* 【★】編集可能なファイルタイプを追加しました—— 拡張子が「abc」「bst」「bib」「lp」それに「pdf」となっているファイルです。 「pdf」の追加により TeXShop をデフォルトの PDF ビューワとして選択できるようになりました。 新しい PDF アイコンを作成したので、システムの方でも、 TeXShop で表示する pdf ファイルにはそのアイコンが使用されます。

* ［☆］TeXShop has always had a "Revert To Saved" item under the File menu, but it has never worked! Sorry. This is fixed.
* 【★】TeXShop の「ファイル」メニュー内に「最後に保存した状態に戻す」という項目がありますが、 これは機能していませんでした！ すみません。 これを修正しました。

* ［☆］David Reitter modified the selection code so if the user clicks on a control word like \gamma, the initial "\" symbol will also be chosen.
* 【★】David Reitter が文字列選択のコードを改良したので、 \gamma のような制御綴り上で複数回クリックすれば、 先頭の「\」という記号もいっしょに選択されます。

* ［☆］A new preference item "Select on Activate" was added. When this item is checked, a mouse click on the text window will select this window and also place the cursor at the spot that was clicked. If the item is not checked, the initial mouse click will only activate the window. A separate click is then needed to position the cursor.
* 【★】新しい環境設定項目「選択時にカーソルを移動」を追加しました。 この項目にチェックを入れ、 ソースウインドウ上でマウスクリックをすると、 ウインドウが選択されるのと同時にクリックした位置にカーソルが挿入されます。 この項目にチェックを入れていない場合は、 最初のクリックではウインドウをアクティブにするだけなので、 カーソルを置くにはまた別にクリックをする必要があります。

* ［☆］New hidden preferences were added for users who change the default foreground and background colors of the editing window. These preferences set the color of the insertion point (without these preferences, the insertion point could become invisible). To set the insertion point to white, for example,
* 【★】ソースウインドウでデフォルトの文字色と背景色を変更しているユーザ用に、 隠れた環境設定項目を新たに追加しました。 この新しい項目で挿入ポインタの色を設定します。 この設定なしでは、挿入ポインタが見えなくなってしまいかねませんでした。 挿入ポインタをたとえば白に設定するには、次のようにします——

	defaults write TeXShop insertionpoint_R 1.0
	defaults write TeXShop insertionpoint_G 1.0
	defaults write TeXShop insertionpoint_B 1.0

* ［☆］When a file is typeset, all open changed files with the same root are first saved.
* 【★】文書をタイプセットする際、 ルートが同じで、開いて編集したすべてのファイルを最初に保存します。

* ［☆］Improvements were made in the pdfsync code.
* 【★】pdfsync のコードを改善しました。

* ［☆］In previous versions, it was possible to add a Macro button to the Preview Window Toolbar in English, but not in other localizations. This is fixed thanks to Juan Luis Varona.
* 【★】先のバージョンでは、 英語版でのみプレビューウインドウのツールバーにマクロボタンを追加することができましたが、 他国語へのローカライズ版ではできませんでした。 これを修正しました——Juan Luis Varona に感謝。

* ［☆］New Japanese Help by Yoshihisa Okazaki with help from Seiji Zenitani.
* 【★】銭谷誠司さんの助力を得て、 岡崎祥久さんが新しい日本語ヘルプを追加しました。

* ［☆］A proxy icon is now added to the title of the preview window. This icon can be dragged to the desktop or other folders to create a copy of the pdf file. The source window has always had a proxy icon. Thanks to Rene Donner for suggesting this feature and explaining how to implement it.
* 【★】プレビューウインドウのタイトル部分にプロキシ・アイコンを付け加えました。 このアイコンをドラッグして、 デスクトップや他のフォルダに PDF ファイルのコピーを作ることができます。 ソースウインドウには前々からプロキシ・アイコンがあります。 この機能を提案し、どう実装すればいいのか説明してくれた Rene Donner に感謝します。
	

##Version 1.36

* ［☆］Version 1.36 was never released.
* 【★】バージョン1.36 は公開されませんでした。

##Version 1.35

* ［☆］Version 1.35 adds extra features to TeXShop and fixes some bugs.
* 【★】バージョン1.35では TeXShop にさらなる機能を追加し、いくつかのバグを修正しました。

###──New features（新機能）

* ［☆］An important recent development is the release of XeTeX and XeLaTeX by Jonathan Kew. See
* 【★】最近の重要な開発は、 Jonathan Kew による XeTeX と XeLaTeX のリリースです。以下を参照のこと。

* -http://scripts.sil.org/xetex

* ［☆］XeTeX is not part of Gerben Wierda's standard installation, but it is available with Wierda's i-Installer as an optional install directly from Jonathan Kew. XeTeX can access Macintosh fonts directly, so TeX documents can be written with Lucida Grande, Zapfino, and any other Mac font. Moreover, XeTeX understands Unicode, so for example users can type Arabic into the source window from right to left, typeset with TeX, and obtain Arabic in the output window. In particular, XeTeX source documents have UTF-8 Unicode encoding.
* 【★】XeTeX は Gerben Wierda による標準的なインストールには含まれていませんが、 Wierda の i-Installer を使い、オプション・インストールとして Jonathan Kew のところから入手できます。 XeTeX は Macintosh のフォントに直接アクセスできるので、 TeX 文書を Lucida Grande や Zapfino その他のフォントを使って書くことができます。さらに XeTeX は Unicode を理解するので、たとえばアラビア語を右から左へとソースウインドウに打ち込んで TeX でタイプセットし、出力ウインドウでアラビア語を得ることができます。具体的には、 XeTeX のソース文書は UTF-8 Unicode 形式になっています。

* ［☆］TeXShop 1.35 supports XeTeX directly as follows:
* 【★】TeXShop 1.35 では XeTeX を以下のように直接サポートします：

* ［☆］a) XeTeX and XeLaTeX are now available in the pull-down typesetting menu on the source window
* 【★】XeTeX と XeLaTeX は、ソースウインドウのプルダウンメニュー「タイプセット」から利用可能です

* ［☆］b) Using preferences, a user can make XeTeX or XeLaTeX the default typesetting option
* 【★】環境設定を使って、 XeTeX と XeLaTeX をデフォルトのタイプセット・エンジンにすることができます

* ［☆］c) If one of the first ten lines of the source has the form
* 【★】ソースの冒頭10行以内に次のような書式がある場合──

	%!TEX encoding = UTF-8 Unicode

* ［☆］then that file will be loaded and saved with UTF-8 Unicode encoding, regardless of the default encoding chosen for other documents
* 【★】他の文書用に選択したデフォルトのエンコーディング方式に関わらず、 UTF-8 Unicode でファイルが読み込まれ保存されます

* ［☆］d) If the first line of the source has the form
* 【★】もしソースの第１行目が次のいずれかの書式になっている場合──

	%!TEX TS-program = xetex
	%!TEX TS-program = xelatex

* ［☆］then the appropriate program will be used regardless of the typesetting option chosen.
* 【★】タイプセット・オプションでの選択によらず、特定のプログラムが用いられます

* ［☆］These XeTeX features form a special case of a new general method for adding typesetting engines to TeXShop. There is a now a folder in ~/Library/TeXShop named Engines; the files in this folder are shell scripts which call typesetting programs. When TeXShop first starts, it examines this folder and adds the script names of files it contains to the pull-down typesetting menu. Choosing one of these items and pushing the Typeset button calls the script. Users can write their own scripts and add them to the Engines folder.
* 【★】こうした XeTeX の特徴は、 TeXShop にタイプセット・エンジンを追加する新しい一般的な方法の特例となっています。 ~/Library/TeXShop 内に「Engines」という名前のフォルダがあります ； このフォルダに入っているファイルは、タイプセット・プログラムを呼び出せるシェル・スクリプトです。 TeXShop を最初に起動すると、このフォルダを調べ、ファイルのスクリプト名を加え、プルダウンメニュー「タイプセット」に含めます。この中から１つを選んでタイプセット・ボタンを押せば、スクリプトが呼び出されます。ユーザは自分で独自のスクリプトを書き、それを「Engines」フォルダに追加することができます。

* ［☆］Items in ~/Library/TeXShop/Engines can be chosen as default typesetting method in TeXShop Preferences.
* 【★】~/Library/TeXShop/Engines 内の項目は、環境設定でデフォルトのタイプセット・エンジンに指定できます。

* ［☆］The typesetting program can be set in the source code by writing one of the following on any of the first twenty lines of the source:
* 【★】ソースコードの冒頭20行以内のどこかに、 下記のいずれかを書き込んでおくことで、 タイプセット・プログラムを設定することができます——

	%!TEX TS-program = tex
	%!TEX TS-program = latex
	%!TEX TS-program = pdftex
	%!TEX TS-program = pdflatex
	%!TEX TS-program = personaltex
	%!TEX TS-program = personallatex

* ［☆］This new syntax also works for any new typesetting engine added to ~/Library/TeXShop/Engines. For example, %!TEX TS-program = xelatex chooses XeLaTeX.
* 【★】この新しい構文は、 ~/Library/TeXShop/Engines に追加した新規のタイプセット・エンジンに対しても機能します。 たとえば、 %!TEX TS-program = xelatex と書けば XeLaTeX が選定されます。

* ［☆］The encoding used to open or save a file can be set by writing a line of the form
* 【★】ファイルを開いたり保存したりするのに用いるエンコーディング方式は、次のような１行を、

	%!TEX encoding = UTF-8 Unicode

* ［☆］as one of the first 20 lines of a source document. Any supported encoding is allowed; TeXShop's Help Files list the string which must appear on the right for each of these encodings. To bypass this behavior, hold down the option key while opening a file.
* 【★】ソース文書の冒頭20行以内に含めることで設定できます。サポートしているいずれのエンコーディング方式でもこれは可能です ； TeXShop のヘルプ・ファイルには、それぞれのエンコーディング方式の正確な文字列を載せてあります。この動作を回避するには、オプションキーを押しながらファイルを開きます。

* ［☆］The old SourceDoc syntax has been modified to conform with the above changes. For example, to set the root file to ../Main.tex, write
* 【★】上述の変更と一致させるために、 以前の SourceDoc 構文を修正しました。 たとえば、 ../Main.tex をルートファイルに設定するには、

	%!TEX root = ../Main.tex

* ［☆］(The old syntax is still supported for setting the program, encoding, and SourceDoc, but users are urged to switch to this new syntax.)
* 【★】と書きます。
（ プログラム、エンコーディング方式、SourceDoc の設定に関しては、 古い構文もまだサポートされてはいますが、 新しい構文に変更することをお勧めします。 ）

* ［☆］TeXShop has a new Find panel by Isao Sonobe. This panel supports regular expressions. Users can switch between the new panel and the original one in Preferences. The Find panel depends on OgreKit, a Cocoa framework for handling regular expressions by Sonobe. See
* 【★】TeXShop には園部勲さんによる新しい検索パネルがあります。このパネルは正規表現をサポートしています。環境設定で新しいパネルと従来の Apple 標準のパネルとを切り替えることができます。新しい検索パネルは園部さんの OgreKit ──正規表現を扱うための Cocoa フレームワーク、に依存しています。以下を参照のこと──

* -http://www-gauge.scphys.kyoto-u.ac.jp/~sonobe/OgreKit/

* ［☆］OgreKit is distributed using a slightly modified version of the BSD license. This license can be found in the Documentation included directly in the OgreKit Framework folder in the TeXShop source distribution. OgreKit requires Panther, so the new panel will only appear on machines running Panther.
* 【★】OgreKit は BSD ライセンスをやや修正したライセンスに基づいて配布されています。同ライセンスは、 TeXShop ソースのディストリビューション内の OgreKit Framework フォルダの中にあるドキュメントで見られます。 OgreKit には Panther が必要になりますので、新しいパネルは Panther を稼働させているマシンでのみ表示されます。

* ［☆］There are many nice features in this new Find panel, which users can discover for themselves. OgreKit modifies the "Find" menu submenu of the TeXShop Edit menu, replacing it with a more extensive menu. This might be confusing to Localizers, because the menu in the TeXShop nib file is not the menu they will see when TeXShop is running. The Find menu in the nib file should not be modified because it will be active in system 10.2. Instead the corresponding menu in OgreKit needs to be localized in the TeXShop source. The Find panel presents buttons controlling how it will find words; the settings of the buttons will be remembered from session to session. Adjust them until Find works as expected and then relax.
* 【★】ユーザが自身で発見できることですが、新しい検索パネルには多くの素晴らしい機能があります。 OgreKit は TeXShop の「編集」メニューの「検索」サブメニューを変更し、より拡張されたメニューに置き換えます。これは各国語版へのローカライズ作業を混乱させるかもしれません──というのも、 TeXShop の nib ファイル内のメニューは、 TeXShop を実行しているときのものではないからです。 nib ファイルの「検索」メニューは変更すべきではありません──システム10.2で表示されてしまうからです。それをせずに OgreKit のメニューに対応するには、 TeXShop のソースでのローカライズが必要になります。検索パネルには、どのように検索を行なうかを制御するボタン類があります ； これらのボタンの設定は次回以降にも引き継がれます。思ったとおりに語句を見つけ出せるようになるまで調整したら、後はリラックスしてください。

* ［☆］TeXShop 1.35 is distributed with the latest pdfsync.sty by Piero d'Ancona and J. Laurens. This fixes typesetting problems caused by the version distributed with TeXShop 1.34. TeXShop did not keep up with the changes by d'Ancona and Laurens for several months; sorry!
* 【★】TeXShop 1.35 は、 Piero D'Ancona と J. Laurens による最新の pdfsync.sty とともに配布されています。最新版は TeXShop 1.34 で同梱したバージョンに起因するタイプセットの問題を解消しています。 TeXShop では、 Piero D'Ancona と J. Laurens による更新に、数カ月ほど追随していませんでした ； ごめんなさい！

* ［☆］In the new version, \include and \input are supported; to use the second, the syntax \input{thisfile} must be used rather than the syntax \input thisfile. The new version supports \pdfsync, \pdfsyncstart, and \pdfsyncstop. Use the first of these commands at any spot where you want to reference a point. If pdfsync breaks your code, enclose the offending section in a \pdfsyncstop, \pdfsyncstart pair.
* 【★】新バージョンでは、\include と \input をサポートしています ； 後者を用いるには「\input thisfile」ではなく「\input{thisfile}」という構文を使わねばなりません。新バージョンでは「\pdfsync」 「\pdfsyncstart」 「\pdfsyncstop」をサポートします。これらのコマンドのうち、最初のものは、ポイントを参照したい任意の場所で使ってください。もし pdfsync がコードを止めてしまうようなら、原因となるセクションを「\pdfsyncstop」と「\pdfsyncstart」のペアで括ってください。

* ［☆］Suppose you are typesetting myfile.tex. Pdfsync creates a file named myfile.pdfsync containing synchronization data. Roughly speaking, each data entry describes a synchronization point as follows:
* 【★】myfile.tex をタイプセットするとします。シンクロナイゼーション用のデータを格納するために pdfsync は、 myfile.pdfsync という名前のファアイルを生成します。大まかに言って、各データ・エントリにはシンクロナイゼーション・ポイントが以下のように記述されています：

* ［☆］the page number of the output where the point occurs
* 【★】ポイントの置かれたプレビュー文書のページ番号

* ［☆］the location on this page
* 【★】このページ上の位置

* ［☆］the name of the source file producing this particular output
* 【★】この特定の出力を生成するソースファイルの名前

* ［☆］the line number in this source file for this particular output
* 【★】このソースファイル内の該当する行番号

* ［☆］There is a way to get TeXShop to display these synchronization points. The preview window toolbar has a new checkbox item called SyncMarks. By default, this item is not shown; use Customize Toolbar in the Window menu to select it. When the checkbox is checked, synchornization points are shown.
* 【★】こうしたシンクロナイゼーション・ポイントを TeXShop で表示させる方法があります。プレビューウインドウのツールバーには「Sync」という新しいチェックボックスがあります。デフォルトでは見えていません ； 「ウインドウ」メニューにある「ツールバーをカスタマイズ...」を使って選び取ってください。チェックボックスをチェックすると、シンクロナイゼーション・ポイントが見えるようになります。

* ［☆］By default, this item will not be checked when the Preview window first appears. A hidden preference item can change this:
* 【★】デフォルトでは、プレビューウインドウが最初に表示された際にこのチェックは入っていません。隠れた環境設定でこれを変更できます：

	defaults write TeXShop ShowSyncMarks YES

* ［☆］TeXShop 1.35 has new matrix code by Jonas Zimmermann. The Matrix Panel now makes tables. Examine the panel to find all of the new features. There is a hidden preference to set the default size of the matrix:
* 【★】TeXShop 1.35 には Jonas Zimmermann による新しい行列コードが含まれています。行列パネルでテーブルが作成できるようになりました。パネルを試して新機能を見出してください。行列のデフォルトのサイズを設定する隠れた環境設定があります：

	defaults write TeXShop matrixsize 12

* ［☆］A very small number of users may have modified "matrixpanel.plist" in ~/Library/TeXShop/MatrixPanel. This plist has been extended; the new list is called "matrixpanel_1.plist". Please edit this file to add your changes.
* 【★】ごく少数のユーザは ~/Library/TeXShop/MatrixPanel にある「matrixpanel.plist」を変更しているかもしれません。この plist は拡張されています ； 新しいリストは「matrixpanel_1.plist」です。独自の変更を加えるにはこちらのファイルを編集してください。

* ［☆］In previous versions of TeXShop, if you clicked elsewhere and then clicked on the edit window to edit, you would need to click twice to correctly position the cursor. This is now changed; the first click in the edit text is recognized and positions the cursor.
* 【★】以前のバージョンの TeXShop では、どこか他の場所をクリックした後でテキスト編集をしようとして編集ウインドウをクリックした場合、カーソルを正しい位置に入れるには、クリックを２度しなければなりませんでした。これが変更されました ； 編集テキスト上で１度だけクリックすれば、位置が認識されカーソルが入ります。

* ［☆］When applescript runs under the Macro menu, it starts a small second application embedded in the TeXShop folder to actually run the script. That is because when a command like "latex" runs, and there is an error on the source, the console appears to accept user input, but the TeXShop event loop is not running during the applescript action, so no user input can occur.
* 【★】マクロメニュー下で AppleScript を実行させると、 TeXShop フォルダに組み込まれている小さな補助アプリケーションが起動してスクリプトを実行します。なぜかというと「latex」のようなコマンドを実行して、もしソースにエラーがあった場合、コンソールが表示されユーザからの入力に応じようとしますが、 TeXShop のイベント・ループは AppleScript の動作中は実行されず、ユーザ入力ができないからです。

* ［☆］Many applescripts do not have this problem. TeXShop now allows users to begin applescript macros with the command
* 【★】多くの AppleScript では、この問題はありません。 TeXShop では今回から AppleScript マクロを次のコマンドで書き始められるようになったということです──

	-- applescript direct

* ［☆］When written this way, the script will be run directly by TeXShop rather than by the second small application.
* 【★】この方法で書かれた場合、スクリプトは、小さな補助アプリケーションではなく、直接 TeXShop で実行されるのです。

* ［☆］Added a menu command "Trash AUX Files" and a button on the console "Trash AUX Files." When involked, these commands move to the trash all files in the current source directory with the same name as the source file and extensions aux, bbl, blg, brf, glo, idx, ilg, ind, ioa, lof, log, lot, mtc, mlf, out, pdfsync, and toc. Thanks to Will Robertson for suggesting this command and producing this list of extensions.
* 【★】「作業ファイルを削除」というメニューコマンドが追加され、コンソールにも「作業ファイルを削除」というボタンが付きました。実行するとこれらのコマンドは、現在のソースがあるディレクトリ内にあり、ソースと名前が同じで、拡張子に aux ・ bbl ・ blg ・ brf ・ glo ・ idx ・ idv ・ ilg ・ ind ・ ioa ・ lof ・ log ・ lot ・ mtc ・ mlf ・ out ・ pdfsync ・ toc が付いたファイルをすべてゴミ箱に移動させます。このコマンドの提案と拡張子のリストの作成を Will Robertson に感謝します。

* ［☆］Additional extensions can be added to this list with a hidden preference. To add "dvi" to the list
* 【★】隠れた環境設定で追加の拡張子をこのリストに加えることができます。 「dvi」を加えるには──

	defaults write TeXShop OtherTrashExtensions -array-add "dvi"

* ［☆］Several such extensions can be added in this way, one by one. To remove all additions
* 【★】こうした拡張子をひとつずつこの方法で追加できます。追加したものを取り除くには──

	defaults write TeXShop OtherTrashExtensions -array

* ［☆］The original list of extensions above will always remain active.
* 【★】上記のオリジナルの拡張子リストは常に有効なままとなっています。

* ［☆］Suppose a book project has a main.tex file in a folder, and then chapters in subfolders which are accessed using commands like \include{chapter1/chapter1.tex}. When this book is typeset, main.aux and other files will appear in the primary folder, and chapter1.aux will appear in a subfolder. So the "Trash AUX Files" command does not do a complete cleanup. But if the option key is pressed when the menu item is chosen or the button on the console window is pressed, then
* 【★】書籍のプロジェクトを想定してください──あるフォルダの中に main.tex というファイルがあり、\include{chapter1/chapter1.tex} のようなコマンドを使ってアクセスしているサブフォルダ内に各章があるとします。この書籍をタイプセットすると、 main.aux やその他のファイルがメインフォルダ内に現われ、サブフォルダ内には chapter1.aux が現われます。そうなると「作業ファイルを削除」コマンドは、完全なクリーンナップを行なうことができません。けれども、このメニューアイテムを選択するとき、またはコンソールウインドウのボタンを押すときに、オプションキーを押さえておくと、

* ［☆］a) SourceDoc and Root File information will be used to find the root document
* 【★】SourceDoc とルートファイルの情報をもとにしてルート文書を探します

* ［☆］b) All files with appropriate extensions listed above will be moved to the trash from this folder and all subfolders, even if the name does not agree with the name of the root file.
* 【★】上記の該当する拡張子の付いたファイルはいずれも、ルートファイルの名前と一致せずとも、メインフォルダとすべてのサブフォルダの中からゴミ箱へと移されます

* ［☆］Some users may want to throw caution to the winds and arrange that "Trash AUX Files" always performs this more extensive cleanup. A hidden preference allows this:
* 【★】「作業ファイルを削除」で常にこの広範囲なクリーンナップを行なえるようにしたがる、向こう見ずなユーザもいるかもしれません。隠れた環境設定でこれができます：

	defaults write TeXShop AggressiveTrashAUX YES

* ［☆］Added new templates by Will Robertson. These are heavily commented. It is intended that users will edit them to fit their own requirements. The templates are only installed if TeXShop is running for the first time, or if the Templates folder is completely removed from ~/Library/TeXShop. But Will's templates are in a folder named "More" in the TeXShop distribution; old users can obtain them by moving "More" to ~/Library/TeXShop/Templates.
* 【★】Will Robertson により、新しいテンプレート集が追加されました。これにはたっぷりとコメントが付けられています。ユーザが自分自身の要求に見合うように編集するのを意図してのことです。テンプレートは TeXShop を最初に起動したときにのみ──あるいは、テンプレート・フォルダが ~/Library/TeXShop から完全に取り除かれていると、インストールされます。が、 Will のテンプレートは、 TeXShop ディストリビューション内の「More」という名前のフォルダの中にも入っています ； 以前からのユーザは「More」フォルダを ~/Library/TeXShop/Templates に移すことでテンプレートを入手できます。

* ［☆］Added new macros by Will Robertson to create tables and arrays, to insert a reference, and to open other project files quickly. These macros have been praised on the TeX-On-MacOSX mailing list. The macros are available for new users; older users can obtain them by following simple instructions which come with TeXShop 1.35.
* 【★】テーブルや配列を作成したり、参照を挿入したり、他のプロジェクト・ファイルを手早く開くための新しいマクロが、 Will Robertson によって追加されました。これらのマクロは TeX-On-MacOSX メーリングリストで賞賛されているものです。このマクロは新規のユーザが利用可能となっています ； 以前からのユーザは、 TeXShop 1.35 に付属している簡単な指示に従って入手することができます。

* ［☆］Added a macro to examine files in the teTeX tree. For example, if "article.sty" is typed in the dialog produced by the Macro, kpsewhich is used to find this file in the tree and open it in TeXShop.
* 【★】teTeX ツリー内のファイルを調べるためのマクロが追加されました。たとえば、マクロが提示するダイアログに「article.sty」と打ち込むと、 kpsewhitch を使ってこのファイルをツリー内で見つけ出し、 TeXShop で開きます。

* ［☆］There are hidden preferences to set the color of the text in the source window
* 【★】ソースウインドウのテキストの色を設定する隠れた環境設定があります──

	defaults write TeXShop foreground_R 0.3
	defaults write TeXShop foreground_G 0.3
	defaults write TeXShop foreground_B 0.3

* ［☆］This color will show if syntax coloring is on; otherwise it will be black and then color can be selected in the Font menu.
* 【★】この色は「ソースのカラー表示」がオンになっていると現われます ； でなければ黒になり、フォントメニューで色を選択できます。

* ［☆］When used with existing hidden preferences to set the source window background color, these commands can be used to write source as white on black, or with other color schemes. TeXShop has new macros to set the source window colors, and to reset to default colors.
* 【★】ソースウインドウの背景色を設定する既存の隠れた環境設定といっしょに使えば、黒地に白文字やその他の色の組み合わせでソースを書くのに、上記のコマンドを使えます。 TeXShop にはソースウインドウの色を設定したり、またデフォルトの色に戻したりするマクロがあります。

* ［☆］There are hidden preferences to make the source, preview, and console windows partly transparent.
* 【★】ソース、プレビュー、コンソールの各ウインドウの透明度をそれぞれに設定する隠れた環境設定があります。

	defaults write TeXShop ConsoleWindowAlpha 0.75
	defaults write TeXShop SourceWindowAlpha 0.75
	defaults write TeXShop PreviewWindowAlpha 0.75

* ［☆］Here an alpha value of 0.00 is completely transparent and an alpha value of 1.00 is completely opaque. Use these commands cautiously!
* 【★】ここでアルファ値が 0.00 なら完全に透明となり、アルファ値が 1.00 なら完全に不透明となります。これらのコマンドは用心してお使いください！

* ［☆］TeXShop now has a Statistics panel, which lists the number of words, lines, and characters in a document. This is obtained by calling
* 【★】TeXShop に「文書情報」が用意されました──これは文書内の単語数や行数、文字数を表示します。これは次のようなコールで得られるものです──

	detex myfile | wc

* ［☆］When first called, the document on disk is tested. After changes are made to the document, the "update" button saves the document and calls detex again. The detex command removes tex commands, but the word count is still only approximate. Input and include files are counted by this command.
* 【★】最初の呼び出しで、ディスク上の文書がテストされます。文書に変更が施された後、 「アップデート」ボタンで文書を保存し、 detex を再度呼び出します。 detex コマンドが TeX のコマンドを取り除きますが、ワード・カウントは今のところ概算でしかありません。 input ないしは include されたファイルもこのコマンドで勘定されます。

* ［☆］New German Help by Martin Kerz. Kerz also redesigned the TeXShop Help Window to follow Apple's current guidelines. These changes appear in English and German, but may not appear in other localizations.
* 【★】Martin Kerz による新しいドイツ語版のヘルプ。 Kerz はまた TeXShop ヘルプのウインドウを、 Apple の現行のガイドラインに沿ってデザインし直してくれました。この変更は英語版とドイツ語版で見ることができますが、その他のローカライズ版では見られないかもしれません。（日本語版も新デザインになっています。）

* ［☆］When a file is drag-and-dropped, any alias is now resolved. Thus alias graphic files (and other files) can be used provided they are dragged and dropped to the source. Alias files will not work if their names are typed directly because the tex engine does not understand aliases (it does understand symbolic links).
* 【★】ファイルをドラッグ＆ドロップした際に、エイリアスが解決されるようになりました。なので、グラフィック（またはその他の）ファイルのエイリアスを、ソースにドラッグ＆ドロップして利用することができます。エイリアス書類の名前をじかに入力しても機能しません──というのも、 TeX エンジンはエイリアスを理解しないからです（シンボリックリンクは理解しますが）。

* ［☆］Several changes were made in the Japanese portions of the code by Seiji Zenitani, with help from Yu Itoh and Koichi Inoue. There is a new Japanese encoding, Shift JIS X0213, which will become a new standard in Japan. There is now utf.sty support for pTeX. Before this change, Japanese pTeX supported only 6000 Kanji characters, but utf.sty supports more than 20,300 characters. This support is turned on by a preference item in Misc. When on, TeXShop exports non-ptex chracters as utf.sty codes. For example, unicode characters become \UTF(Hex code) and non-unicode characters become \CID(glyph ID).
* 【★】伊東悠さんと銭谷誠司さんのコードにより、日本語環境でいくつかの変更が行なわれました。日本語エンコーディングに新しく Shift JIS X0213 が用意されました──これは日本での新しい標準となるものです。 pTeX 用に utf.sty もサポートされるようになりました。この変更以前には、日本語 pTeX は 6,000 字の漢字しかサポートしていませんでしたが、 uft.sty は 20,300 以上もの文字をサポートします。これは環境設定項目の「詳細」でオンにできます。オンにすると、 TeXShop は pTeX が対応していない文字を utf.sty のコードとして書き出します。たとえば、 Unicode 文字は \UTF{Hex code} となり、非-Unicode 文字は \CID{glyph ID} となります。

* ［☆］Zenitani also added new Japanese default settings. Previously, Japanese ptex distributors provided their own "altpdflatex" scripts, which was confusing for beginning users. This new version of TeXShop bundles "altpdflatex-for-ptex" scripts and installs them in ~/Library/TeXShop/bin. The new Japanese default settings in Preferences automatically set up TeXShop to use these new scripts.
* 【★】銭谷さんはまた、日本語用の新しいデフォルト設定も追加しました。これまで日本語 pTeX のディストリビューションは、個々に「altpdflatex」を提供していましたが、これが初心者には混乱をもたらしていました。 TeXShop の新しいバージョンには pTeX でタイプセットするスクリプト（井上浩一さん提供）が組み込まれており、 ~/Library/TeXShop/bin にインストールされます。環境設定にある日本語用の新しいデフォルト設定が、新しいスクリプトを利用できるよう TeXShop を自動的にセットアップします。

* ［☆］Added the following Chinese encodings at the request of Adam Si: Mac Chinese Traditional, Mac Chinese Simplified, DOS Chinese Traditional, DOS Chinese Simplified, GBK, GB 2312, and GB 18030.
* 【★】Adam Si のリクエストにより、以下の中国語エンコーディングが追加されました：Mac Chinese Traditional ・ Mac Chinese Simplified ・ DOS Chinese Traditional ・ DOS Chinese Simplified ・ GBK ・ GB 2312 ・ GB 18030

* ［☆］Added a new Japanese help system by Yoshihisa Okazaki.
* 【★】岡崎祥久さんにより、新しく日本語ヘルプが追加されました。

* ［☆］Added new Spanish localization and help.
* 【★】新規のスペイン語版ローカライズとヘルプが追加されました。

* ［☆］TeXShop can now open and write files with extension .dn and .engine.
* 【★】拡張子 「.dn」 「.engine」の付いた書類を TeXShop で読み書きできるようになりました。

* ［☆］There is a hidden preference
* 【★】隠れた環境設定──

	defaults write TeXShop BringPdfFrontOnAutomaticUpdate NO

* ［☆］which causes the pdf window to remain where it is when it automatically updates and is used with an external editor. This preference was requested by a user with an X11 editor and only seems necessary in this case.
* 【★】これにより、自動更新や、外部エディタ使用の際に、プレビューウインドウの位置をそのままにします。この環境設定は X11 エディタを使っているユーザからリクエストされたもので、これ以外では需要はなさそうです。

* ［☆］Users sometimes upgrade Mac OS X via "archive and install". After the installation, TeXShop remains but teTeX is blown away. The first time such users typeset a file, they see an error dialog reporting that "pdflatex cannot be found." This error dialog has been revised to explain more clearly the likely cause, and resolution, of the problem.
* 【★】ユーザは時として「アーカイブとインストール」によって Mac OS X をアップグレードします。インストール後、 TeXShop は残っていますが、 teTeX はかき消えています。こうしたユーザが初めてタイプセットを行なおうとすると、 「pdflatex が見つかりません」とエラー・ダイアログに告げられます。このエラー・ダイアログを改訂し、この問題に関してありえそうな原因、および解決法について、より明瞭に説明するようにしました。

* ［☆］The TeXShop web page now contains a "LaTeX Documentation" section listing recommended books and links to free LaTeX guides on the internet. The web page also makes available a number of short LaTeX example files by Will Robertson.
* 【★】TeXShop の WEB ページに「LaTeX Documentation」というセクションを設け、おすすめの書籍の一覧を載せたり、インターネット上にあるフリーの LaTeX ガイドにリンクを張ったりしました。 WEB ページではまた、 Will Robertson による数多くの簡潔な LaTeX サンプルも利用可能となっています。

###──Bugs fixed（修正されたバグ）

* ［☆］When a large number of windows were open, switching from one window to another took a long time and yielded a spinning disk; TeXShop was completely unresponsive during this time. This slowdown was caused by a bug in the Macro code. The problem is now fixed.
* 【★】多数のウインドウを開いていると、ひとつのウインドウから他のウインドウに切り替えるのに長く時間がかかり、ディスクの急回転を引き起こしていました ； この間、 TeXShop は完全に反応しなくなっていました。このスローダウンはマクロ・コードのバグに起因するものでした。この問題が解消されました。

* ［☆］If a dvi file was opened in a directory without write permission, TeXShop could not create and display a corresponding pdf file. Now it will create the pdf file in a temporary directory and display it.
* 【★】書き込み権限のないディレクトリで dvi ファイルを開くと、 TeXShop は対応する pdf ファイルを生成して表示することができませんでした。そこで pdf ファイルをテンポラリー・ディレクトリに生成して表示するようにしました。

* ［☆］If the abort button was pushed in the console and the user later typed and pushed RETURN, the program crashed. Fixed.
* 【★】コンソールにある強制終了ボタンを押し、その後でユーザが入力を行なってリターンを押すと、プログラムがクラッシュしていました。これを修正。

* ［☆］Two minor error dialogs, which should have appeared in a window, instead appeared on the desktop with an inoperable "OK" button. This is fixed.
* 【★】ウインドウ内に表示されるべき２つの地味なエラー・ダイアログが、操作不能の「OK」ボタンとともにデスクトップに表示されていました。これを修正。

* ［☆］In localizations other than English, attempts to get the applescript dictionary crashed TeXShop. Fixed.
* 【★】英語以外のローカライズ版において、 AppleScript 辞書を取得しようとするとTeXShop がクラッシュしていました。これを修正。

* ［☆］The Bibtex, etc., tools in the source window did not work if a file had a root file. Fixed.
* 【★】文書にルートファイルがあると、ソースウインドウにある Bibtex などのツールが機能しませんでした。これを修正。

* 環境設定 > コピー > フォーマットを選択できない不具合が修正されました。（1.35c 日本語版）


##Version 1.34

* ［☆］Version 1.34 adds extra features to TeXShop and fixes some bugs.
* 【★】バージョン1.34では TeXShop にさらなる機能を追加し、いくつかのバグを修正しました。

###──New features（新機能）

* ［☆］Added a Matrix Panel by Jonas Zimmermann, zimmerleut@gmx.de. Many thanks.
* 【★】Jonas Zimmermann （ zimmerleut@gmx.de ）による行列パネルの追加。大変ありがとう。

* ［☆］At the request of Claus Gerhardt, added an extra applescript command, "goto line". For instance
* 【★】Claus Gerhardt のリクエストにより、AppleScript コマンド「 goto line 」を追補。例──

		tell front document of application "TeXShop"
		goto line 15
		end tell

* ［☆］Added a first cut at pdfsync. Clicking on a spot in the pdf file while holding down the command key takes the user to the corresponding point in the source file. If the source file has include files, this operation will open the appropriate include file and take the user to a point in that file. Read the help file "General Help: Pdfsync" for important details. This change depends on pdfsync.sty, a file create by Piero D'Ancona with improvements by Jérôme Laurens.
* 【★】pdfsync を初めて搭載。コマンドキーを押しながらプレビューウインドウの一点をクリックすると、ソースファイル内の相当する位置に移動します。ソースファイルに「 include 」されているファイルがあった場合は、対応するファイルを開き、そのファイル内の箇所に移動します。詳細については「全般的なヘルプ」の「 Pdfsync 」の項を参照のこと。この機能は pdfsync.sty に依存します── pdfsync.sty は Piero D'Ancona が作成し Jérôme Laurens によって改良されました。

* ［☆］Also added pdfsync the other way. Clicking on a spot in the source file (including source files with root files) while holding down the command key will select the corresponding page in the pdf file.
* 【★】さらに pdfsync には別の使い方も。ソースファイル（ルートファイルを設定したものも含む）内の一点を、コマンドキーを押しながらクリックすると、pdf ファイルの対応するページを表示します。

###──Bugs fixed（修正されたバグ）

* ［☆］The TeX, Latex, Bibtex, Makeindex, Metapost, Context, and Metafont buttons on the toolbar reset the default typesetting engine. This no longer happens. Thus it is possible to hit the Bibtex button and then hit command-T to typeset again.
* 【★】TeX、LaTeX、BibTeX、MakeIndex、MetaPost、ConTeXt、それに MetaFont といったツールバーのボタンが、デフォルトのタイプセット・エンジンをリセットしてしまう。これはもう生じません。なので、BibTeX ボタンを押した後、command + T で再度タイプセットを行なうことが可能です。

* ［☆］The abort button on the console window did not stay fixed when the window was resized. Thanks to Sean Luke for pointing out these first two errors.
* 【★】コンソールのウインドウサイズを変えると「 abort 」ボタンがズレてしまう。以上２つのエラーの指摘を Sean Luke に感謝。

* ［☆］The command-1 keystroke switches back and forth between the source and preview windows. In previous versions, this did not work when a source window had a root file set by myfile.texshop or %SourceDoc. This is now fixed. Clicking command-1 while in the source brings up the corresponding preview window. Clicking command-1 again brings up the original source file. A given preview window may have several source files. Command-1 will bring up the last source file which was switched to the preview using command-1, or the root source file if there was no previous switch.
* 【★】command + 1 のキー操作でソースとプレビューウインドウを交互に切り替え可能です。以前のバージョンでは、myfile.texshop あるいは %SourceDoc でルートファイルが設定されているソースウインドウでは、これが機能しませんでした。それを修正。ソースファイルで command + 1 を押すと、対応するプレビューウインドウを前面にします。再び command + 1 を押せば、元のソースファイルが前面になります。プレビューウインドウは複数のソースファイルに対応しているかもしれないので、command + 1 で前面に来るのは、プレビューウインドウへの切り替えを最後に command + 1 で行なったソースファイルとなります──以前に切り替えを行なったソースがなければ、ルートソースになります。

* ［☆］New Spanish help files by Juan Luis Varona Malumbres. Thanks.
* 【★】Juan Luis Varona Malumbres による新規のスペイン語ヘルプ。ありがとう。

* ［☆］Printing now respects the "scale" setting in Page Setup. It does not respect the "paper size" setting since paper size is set in teTeX. Printing works like this: the dimensions of the printed document are set by tex and encoded in the pdf file; this pdf is resized by the scale factor if this factor is not 100%, but otherwise is placed full size and centered on the printed page; usually the document size and printed page size are the same, but in rare cases when they are not, the edges of the document might be cut off.
* 【★】印刷時に、ページ設定での「拡大縮小」を順守するようにしました。「用紙サイズ」については、teTeX 内で設定されるので顧慮していません。印刷は次のように行なわれます：印刷する文書の寸法は TeX で設定され、pdf ファイル内にコード化される；pdf は拡大縮小率が100％でない場合はリサイズされるが、そうでなければフルサイズで用紙中央に配置される；通常は文書のサイズと用紙のサイズは同じですが、違っている場合には、文書のふちを切り落とすことになるかもしれません。

##Version 1.33

* ［☆］Version 1.33 adds extra features to TeXShop and fixes some bugs.
* 【★】バージョン1.33では TeXShop にさらなる機能を追加し、いくつかのバグを修正しました。

###──New features（新機能）

* ［☆］The changes in version 1.33 support improved apple scripting, better macro support, and improved interaction with external editors.
* 【★】バージョン1.33の改良点は、AppleScript の拡充、マクロのサポートの向上、外部エディタとの相互関係の改善です。

* ［☆］Improved macro support was prompted by Claus Gerhardt, who wrote several useful scripts included with version 1.33. For example, one script calls htlatex to typeset a latex file for the web. The script saves the source, typesets, and opens the resulting html file in Safari. Thus the script behaves exactly like the Latex typesetting button except that it creates an html rather than a pdf, and displays the html in Safari rather than TeXShop. An advantage of this approach is that users can create their own scripts similarly and thus add features to TeXShop without waiting for new program code.
* 【★】マクロのサポートの改善は Claus Gerhardt により促されました──彼はバージョン1.33に含まれるいくつかの便利なスクリプトを書きました。たとえば、あるスクリプトは htlatex を呼び出して LaTeX ファイルをウェブ用にタイプセットします。スクリプトは、ソースを保存し、タイプセットし、結果の html ファイルを Safari で開きます。つまりちょうど LaTeX のタイプセット・ボタンのように動作するわけですが、違っているのは、pdf ファイルではなく html ファイルを生成し、TeXShop ではなく Safari で html を表示するということです。この取り組みの優れている点は、ユーザ自身がスクリプトを書くことで同様に、新しいプログラムコードを待たずとも TeXShop に機能を追加できることです。

* ［☆］TeX typesetting often requires a sequence of operations. To process a file with a bibliography, the source must be run through latex, bibtex must be run, and latex must be run twice more. A script is included to do this automatically. The script saves the source before the first latex run and updates the preview display at the end. Users can easily customize this script for their own workflow.
* 【★】TeX のタイプセットではしばしば、連続的な操作が必要になります。参考文献目録を含むファイルを処理するには、LaTeX に次いで BibTeX を実行し、さらにもう２度 LaTeX を実行させねばなりません。これを自動的に行なうスクリプトが入っています。このスクリプトは最初に LaTeX を実行する前にソースを保存し、最後にプレビュー画面を更新します。ユーザはそれぞれのワークフローに合わせて簡単にこのスクリプトをカスタマイズできます。

* ［☆］Additional scripts convert the tex source file to a file with Windows line feed convention, or a file with Macintosh 9 line feed conventions, or a file with Unix line feed conventions. Mac OS X understands all line feeds without help, but many computers are not so smart; the conversions are useful when sending files to friends. The "flip" binary used to do these conversions was written by Craig Stuart Sapp. See http://ccrma-www.stanford.edu/~craig/utility/flip/ for details.
* 【★】追加されたスクリプトには、ソースファイルを Windows の改行コードに変換したり、Mac OS 9 の改行コードや UNIX の改行コードに変換したりするものもあります。Mac OS X はいずれの改行コードでもそのまま理解しますが、多くのコンピュータはそれほどスマートではありません；改行コードの変換は、ファイルを友人に送る際に重宝します。こうした変換は Craig Stuart Sapp の作ったバイナリ「 flip 」を利用しています。詳細については http://ccrma-www.stanford.edu/~craig/utility/flip/ を参照のこと。

* ［☆］A script is included to call pdfselect and extract portions of pdf documents. A user could request one file containing pages 3 through 7 of the tex document, one containing page 29, and one containing pages 31 through 36. The advantage of placing this code in the Macros menu is that a user interface is provided, so users don't need to remember calling conventions for pdfselect and don't need to switch to the Terminal.
* 【★】pdfselect を呼び出すスクリプトも入っており、これは pdf 文書の一部を抜粋します。１つ目のファイルには TeX 文書の３〜７ページが含まれ、２つ目の文書には29ページが、３つ目のファイルには31〜36ページが含まれる、というようなことが可能です。このコードをマクロメニューに入れておく利点は、ユーザ・インターフェースが用意されているということです──ユーザは pdfselect を呼び出すときの約束事を覚えておかずともよいし、Terminal に切り替える必要もありません。

* ［☆］A #DOCUMENTNAME# variable was added to the Macro editor, giving applescript commands the name of the calling document.
* 【★】#DOCUMENTNAME# 変数がマクロエディタに追加されました──これは呼び出す文書の名前を AppleScript コマンドに渡します。

* ［☆］The following applescript commands were added to TeXShop. Consult the TeXShop help files for details about writing your own scripts using these commands.
* 【★】以下の AppleScript コマンドが TeXShop に追加されました。これらのコマンドを用いてスクリプトを書くための詳細については、TeXShop ヘルプをお調べください。

	* typeset
	* latex
	* tex
	* bibtex
	* context
	* metapost
	* makeindex
	* typesetinteractive
	* latexinteractive
	* texinteractive
	* bibtexinteractive
	* contextinteractive
	* metapostinteractive
	* makeindexinteractive
	* typeset
	* refreshpdf
	* refreshtext
	* taskdone

* ［☆］Improved support was added for external editors, following prodding by Joachim Kock. Several changes have been made:
* 【★】Joachim Kock からの促しにより、外部エディタに対するサポートを改善。いくつかの変更が行なわれました：

* ［☆］There is now a preference to turn on continuous updating of the preview window if the user is running in external editor mode. Once each second the program checks to see if the pdf file has been updated. If so, it refreshes the pdf display.
* 【★】外部エディタ・モードで作業しているのであれば、プレビューウインドウを継続的に更新する環境設定をオンにできるようになりました。TeXShop は１秒に１度、pdf ファイルが更新されているかどうかをチェックします。更新されていれば、pdf 画面が再描画されます。

* ［☆］The interval between refresh checks is controlled by a hidden preference item named RefreshTime. To reset to another interval in seconds (say every 2.19 seconds)
* 【★】更新チェックの間隔は、RefreshTime という隠れた環境設定項目でコントロールできます。秒単位で間隔を（たとえば2.19秒ごとに）変更するには次のようにします──

	defaults write TeXShop RefreshTime 2.19

* ［☆］Applescript command support has been added to TeXShop so external applications can send commands to it. For external editors, the important script commands are
* 【★】AppleScript コマンドのサポートが追加されたので、外部のアプリケーションから TeXShop にコマンドを送れるようになりました。外部エディタで重要となるのは以下のようなスクリプト・コマンドです──

	* latexinteractive
	* texinteractive
	* bibtexinteractive
	* contextinteractive
	* metapostinteractive
	* makeindexinteractive
	* typesetinteractive
	* refreshpdf
	* taskdone
	* open_for_externaleditor

* ［☆］The first seven commands call TeXShop's typesetting engine. When one of these commands is called, control immediately returns to the calling program even though the typesetting operation is not complete. The taskdone command returns FALSE while this operation continues and TRUE when it is done, so a calling program wishing to send several commands can send one command and then test that it has been completed before sending another command.
* 【★】最初の７つのコマンドは、TeXShop のタイプセット・エンジンを呼び出します。これらのコマンドの１つが呼び出されると、タイプセット処理が完了していなくても、コントロールはすぐに呼び出し側のプログラムに戻ります。taskdone は、処理中は FALSE を返し、完了すれば TRUE を返します──なので、呼び出し側のプログラムでいくつかのコマンドを送りたい場合にも、ひとつのコマンドを送った後、それが完了したかどうかを調べてから、次のコマンドを送ることができます。

* ［☆］Refreshpdf updates the preview display, and can be used instead of continuous updating to control that display. Typesetting commands automatically update the display upon completion.
* 【★】Refreshpdf はプレビュー画面を更新しますが、継続的な自動更新の代わりに、これを使って画面をコントロールできます。処理が終了次第、タイプセット・コマンドが自動的に画面を更新します。

* ［☆］The open_for_externaleditor command opens a .tex file, calling "Open for Preview..."
* 【★】open_for_externaleditor コマンドは「プレビューを開く...」で .tex ファイルを開きます。

* ［☆］Additional features not related to scripting or external editors have also been added:
* 【★】スクリプティングや外部エディタとは関連しない機能も追加されました：

* ［☆］"Select All" can be used to select the full page of pdf output in selection mode. There is one restriction; in Multi-Page and Double-Multi-Page mode, select all is only active if the document has at most 20 pages, since otherwise the selected pdf will be enormous and bring the machine to a crawl.
* 【★】プレビューのマウスモードが「選択」になっている状態で「全てを選択」を使って pdf 出力の全ページを選択できます。ただし制限事項が１つあります；ページレイアウトが連続ページもしくは連続見開きページになっているときは、文書が最大で20ページの場合にのみ全てを選択することができます──そうでないと、選択した pdf が巨大になり、マシンの速度を低下させるので。

* ［☆］A preference item now allows users to distill with Apple's pstopdf rather than ghostscript. This only works in Panther because pstopdf is only in Panther. If the preference is chosen but Panther is not running, the old ghostscript code will be used. When the preference is chosen, ghostscript is no longer needed for internal TeXShop scripts, but it may still be required for teTeX style files. One such case is epstopdf.sty, used to automatically convert eps files to pdf format during typesetting.
* 【★】ghostscript ではなく Apple の pstopdf で pdf を生成するよう環境設定項目で選べるようになりました。これは Panther でのみ機能します── pstopdf が Panther 固有のものなので。環境設定で選択したにもかかわらず Panther が機能しないようなら、従来の ghostscript コードが使われます。この環境設定を選択した場合、ghostscript はもう TeXShop 内部のスクリプトには必要ありませんが、teTeX のスタイルファイルではまだ必要とされるかもしれません。一例として epstopdf.sty がありますが、これはタイプセット時に eps ファイルを pdf 形式へと自動的に変換するのに用いられます。

* ［☆］Zenitani provided additional drag and drop support. The new version reports an error if the filename of the dropped file contains a space. The new code also permits customization, in a somewhat strange way. To customize drag and drop code, add a new submenu to the Macros menu titled "Drag & Drop". Inside this folder, insert items for file types and make the text of each item be the code to be produced by drag and drop. For example, one item might be called ".pdf" and the body of this item might be "\includegraphics[#INS#]{%r}" where neither item would include the quotation marks. In these inclusions,
* 【★】銭谷さんにより、さらなるドラッグ＆ドロップのサポートが提供されました。新しいバージョンでは、ドロップしたファイルの名前にスペースが含まれているとエラーが出されます。新しいコードは、いくぶん奇妙な方法でカスタマイズも可能です。ドラッグ＆ドロップのコードをカスタマイズするには、マクロメニューに「 Drag & Drop 」という名前で新しいサブメニューを追加します。このフォルダ内に、ファイルタイプ（拡張子）ごとに項目を立て、各項目の「内容」をドラッグ＆ドロップされたときに実行されるコードにします。たとえば、ある項目が「 pdf 」だった場合、この項目のコード部分は "\includegraphics[#INS#]{%r}" となるでしょう──どの項目でも引用符は含みません。こうした取り込み用に、次のような短縮形を利用してもらえます：
* 訳注：In these inclusions, 以下に the following abbreviations may be used: を補足。
	%F = full path of an dropped file ──ドロップされたファイル名（絶対パス）
	%f = dropped filename ──ドロップされたファイル名
	%r = relative path of the dropped file ──ドロップされたファイル名（相対パス）
	%n = filename without extension ──拡張子なしのファイル名
	%e = extension ──拡張子

* ［☆］If an extension is not listed in the Drag & Drop menu, or if there is no such menu, then drag and drop behaves as Zenitani prescribed, so most users won't need to customize the code.  German help has been updated by Martin Kerz, the Italian localization has been updated by Nicola Vitacolonna, the Spanish help was updated by Juan Luis Varona Malumbres, the French localization was updated by Hendrik Chaltin, and a Romanian localization was added by Andrei Teleman. Thanks!
* 【★】拡張子が Drag & Drop メニューに挙げられていなければ、あるいはこのメニュー自体がなければ、ドラッグ＆ドロップは銭谷さんが規定しておいたように動作します──なので、ほとんどのユーザはコードをカスタマイズする必要はないでしょう。
* 【★】Martin Kerz によりドイツ語版のヘルプがアップデート、Nicola Vitacolonna によりイタリア語版のローカライズがアップデート、Juan Luis Varona Malumbres によりスペイン語版のヘルプがアップデート、Hendrik Chaltin によりフランス語版のローカライズがアップデート、Andrei Teleman によりルーマニア語版のローカライズが追加されました。ありがとう！

* ［☆］Macros can now be called when the preview window is active; commands which insert text will be deactivated in this mode. A toolbar item for the Preview window was added so the Preview toolbar can display a Macros button.
* 【★】プレビューウインドウがアクティブになっているときにもマクロを呼び出せるようになりました；ここではテキストを挿入するコマンドは無効になります。プレビューウインドウ用のツールバー項目が追加されたので、プレビューのツールバーにマクロ・ボタンを表示できます。

* ［☆］An "Abort" button was added to the console for people who want to stop the typesetting program in midstream. This is a minor change.
* 【★】途中でタイプセット・プログラムを止めたいユーザ用に「 Abort 」ボタンが追加されました。これはマイナー・チェンジです。

* ［☆］Code by Elliott Hughes was added to clean up some of the code calling a latex, tex, bibtex, etc., task. If the binary file is not found, the program now puts up an error message explaining the error and asking if the preferences bin path is correct. This will be useful for those running fink who forget to change the preference.
* 【★】Elliott Hughes によるコードが追加され、LaTeX、TeX、BibTeX などを呼び出すコードがクリーンアップされました。バイナリ・ファイルが見つからない場合、プログラムはエラー状況を説明するエラーメッセージを出し、環境設定の bin パスが正しいかどうかを問い合わせます。これは Fink を使っていて環境設定を変更し忘れたユーザの役に立ちます。

* ［☆］At the request of Joachim Kock, when TeXShop opens a file for Preview, or is in external editor mode and opens a file, the program now compares the dates of the source and preview files. If the preview file is not up to date or does not exist at all, the source file is automatically typeset. There is a hidden preference to turn this behavior off, but it is on by default: To turn it off
* 【★】Joachim Kock のリクエストにより、「プレビューを開く...」でファイルを開いた場合や、TeXShop を外部エディタ・モードにしてファイルを開いた場合に、ソースとプレビュー・ファイルの日付を比較するようにしました。もしプレビュー・ファイルが古くなっていたり、まるっきり存在していなかった場合には、自動的にソースファイルをタイプセットします。この動作はデフォルトでオンになっていますが、オフにする隠れた環境設定があります：オフにするには──

	defaults write TeXShop ExternalEditorTypesetAtStart NO

###──Bugs fixed（修正されたバグ）

* ［☆］A few users reported that their printers added a slight yellow background to the page. Only a few printers had that problem. Frank Stengel discovered that it was caused by a NSEraseRect call in the print drawing routine. This call has been removed; now TeXShop prints using only one line, the vanilla Cocoa call [myRep draw].
* 【★】幾人かのユーザからの報告では、プリンターが薄黄色の背景をページに付け加えてしまうとのことでした。少数のプリンターでのみこの問題が生じていました。Frank Stengel により、これはプリント描画ルーチンにおける NSEraseRect の呼び出しに起因するものとわかりました。このコールは取り除かれました；今では TeXShop は、Cocoa の vanilla コール [myRep draw] １行だけで印刷を行なっています。

* ［☆］In Panther, all Text objects offer word completion. If a portion of a word is typed and option-escape is typed, the system will offer a list of possible completions. This works in TeXShop, TextEdit, and other Cocoa programs. But TeXShop's Command completion was broken in Panther, and made it impossible to use this new feature. This is fixed.
* 【★】Panther では、すべてのテキスト・オブジェクトに単語の補完が用意されています。単語の一部を入力して option + escape を押せば、補完可能なリストをシステムが提示します。これは TeXShop や TextEdit、その他の Cocoa プログラムで機能します。しかし TeXShop のコマンド補完が Panther で不具合となり、この新しい機能を使えませんでした。これを修正しました。

* ［☆］TeXShop has an applescript command to add text, but this command did not update the undo stack. This was fixed by Stefan Walsen; his patch is in version 1.33.
* 【★】TeXShop にはテキストを追加する AppleScript コマンドがありますが、このコマンドが undo stack を更新していませんでした。これは Stefan Walsen により修正されました；彼のパッチがバージョン1.33に入っています。

* ［☆］If the user printed the source and later printed the typeset document, the document would be lowered on the page. This is fixed.
* 【★】ソースを印刷した後で、タイプセットした文書を印刷した場合、文書が下がってしまう。これを修正しました。

* ［☆］Jerry Keough found a strange bug when using TeXShop in Jaguar. If the user's preference setting asked that no empty document appear at startup and if the user opened a document, made the pdf window active, and then reached over and closed the source window, the next menu use would crash the program. This bug did not occur in Panther. It is fixed.
* 【★】Jerry Keough が TeXShop を Jaguar で使用中に奇妙なバグを発見。環境設定で起動時に新しいファイルを作成しないよう設定していた場合に、文書を開いて pdf ウインドウをアクティブにし、その後でソースウインドウを閉じると、次に使うメニュー項目がプログラムをクラッシュさせてしまう。このバグは Panther では生じません。修正しました。

##Version 1.32

* ［☆］Version 1.32 adds two extra features to TeXShop and fixes some bugs.
* 【★】バージョン1.32では TeXShop に２つの機能をさらに追加し、いくつかのバグを修正しました。

###──New features（新機能）

* ［☆］There is a new menu item, "New Tag", which inserts an empty tag in the source text and positions the cursor so the user can add the name of the tag. As a corollary, there is now a keystroke to add a new tag; the keystroke is command-2.
* 【★】新しいメニュー項目「タグを追加」は、ソーステキストに空のタグを挿入し、タグの名前を追加できるようカーソルを配置します。そのうえで、新しいタグを追加するキー操作を用意しました；command + 2 です。

* ［☆］In Applescript macros, the terms #LOGPATH#, #AUXPATH#, #INDPATH#, #BBLPATH#, and #HTMLPATH# will now be recognized; this has been added at the request of Claus Gerhardt.
* 【★】AppleScript マクロにおいて、#LOGPATH#、#AUXPATH#、#INDPATH#、#BBLPATH#、#HTMLPATH# が認識されるようになりました；これは Claus Gerhardt のリクエストにより追加。

* ［☆］There is a new option to set the program called by MetaPost. See the TeXShop help file for an explanation.
* 【★】MetaPost で呼び出すプログラムの設定用に、新しいオプションを用意しました。解説については TeXShop ヘルプをご覧ください。

* ［☆］The drag and drop code has been improved by Seiji Zenitani. Dropping files of types pdf, jpg, jpeg, tif, tiff, eps, or ps on the source document will produce \includegraphics and a reference to the file. Dropping a file of type cls, sty, or bib will \documentclass, \usepackage, or \bibliographystyle and a file reference. Dropping any other text file will produce \input and a file reference.
* 【★】ドラッグ＆ドロップのコードが銭谷誠司さんにより改善されました。pdf、jpg、jpeg、tif、tiff、eps、ps といった形式のファイルをソース文書にドロップすると、\includegraphics コマンドが挿入され、ファイルへの参照が行なわれます。cls、sty、bib 形式のファイルをドロップすれば、\documentclass、\usepackage、\bibliographystyle コマンドが挿入され、ファイルへの参照が行なわれます。その他のテキスト・ファイルをドロップした場合には、\input コマンドが挿入され、ファイルへの参照が行なわれます。

###──Bugs fixed（修正されたバグ）

* ［☆］Although the magnification level can increase to 1000 in version 1.31, the arrow keys next to the magnification control only allowed values up to 400. This is fixed.
* 【★】バージョン1.31でズーム倍率が1000まで引き上げられましたが、倍率コントロールの隣りにある矢印では400までしか上げられませんでした。これを修正。

* ［☆］If the preview window's toolbar was in text-only mode and the magnification panel was selected, the resulting small dialog window would not go away in 1.31. This is fixed.
* 【★】プレビューウインドウのツールバーを「テキストのみ」の表示にしてズーム倍率を選択すると、倍率を入力する小窓が1.31ではずっと残ってしまっていました。これを修正。

* ［☆］In Preferences, if the user set the tab size or the preview window magnification and then cancelled, the new values would still appear when the Preference panel was again displayed. This is fixed.
* 【★】環境設定において、タブ幅の文字数、あるいはプレビューウインドウのズーム倍率を設定してキャンセルすると、ふたたび環境設定パネルを開いたときに、キャンセルしたはずの設定がそのまま残っていました。これを修正。

* ［☆］Suppose the preference to place the first page on the right side is active. In 1.31, the left arrow key did now work in double page mode, and the right arrow key stopped one page before the end. In double multipage mode, the end key, the page down key, and the right arrow key stopped before displaying the last page. All of these problems are fixed.
* 【★】環境設定で見開きページが「右からスタート（片面）」になっているとします。1.31において、左矢印キーはまあ「見開きページ」で機能していましたが、右矢印キーは最後の１ページ手前で止まってしまっていました。「複数見開きページ」では、end キー、ページダウン・キー、それに右矢印キーが最終ページを表示する手前で止まっていました。こうした問題をすべて修正。

##Version 1.31

* ［☆］Version 1.31 adds some extra features to TeXShop and fixes several bugs.
* 【★】バージョン1.31では TeXShop にさらなる機能を追加し、いくつかのバグを修正しました。

###──New features（新機能）

* ［☆］Macros items are now specific to the typesetting engine set in the current window. Two default sets are created when TeXShop first starts, one for Latex and one for Context. (The Context set was created by Hans Hagen; thanks!). Suppose a different engine is selected, say TeX. When it starts, it will have the default Latex macros. But if this set of Macros is edited with the Macro editor, the new set will always be associated with TeX, while the old Latex macros will continue to be associated with Latex. Of course the Latex macros can also be changed.
* 【★】現在のウインドウで設定されているタイプセット・エンジンごとに、マクロ項目をそれぞれ特有のものにできるようになりました。TeXShop を最初に起動した際に、２つのデフォルトのマクロ・セットが作成されます──ひとつは LaTeX 用で、もうひとつは ConTeXt 用です（ ConTeXt 用のセットは Hans Hagen により作成されました；ありがとう！）。違うタイプセット・エンジン（たとえば TeX ）が選択されたとします。当初はデフォルトの LaTeX 用のセットになっています。が、このマクロ・セットをマクロエディタで編集すると、編集したセットが TeX 使用時には使われるようになります──以前の LaTeX マクロはそのまま LaTeX で使われます。もちろん LaTeX マクロも編集可能です。

* ［☆］A new preference item allows the first page in the two double page modes to be either on the left or on the right. Books usually put this page on the right, so that is the default preference.
* 【★】新しい環境設定項目により、見開きページモードの最初のページを、左始まり右始まりのいずれにもできるようになりました。書籍では通常、最初のページは右にあるので、デフォルトの設定は右始まりになっています。

* ［☆］The preference dialog has a new pulldown menu to reset preferences to default values. This addition was requested by Seiji Zenitani for users in Japan who must cope with three different versions of pTeX. These users can now rapidly set preferences without consulting documentation on web sites.
* 【★】環境設定ダイアログに新しいプルダウンメニューを設け、設定プロファイルをデフォルト値にリセットできるようにしました。この追加は銭谷誠司さんからのリクエストによるもので、３つの異なる版の pTeX に対応する必要がある日本のユーザ向けです。日本のユーザのみなさんは、ウェブサイトにあるドキュメントを調べずとも、素早く環境設定を行なえるようになりました。

* ［☆］The largest possible magnification in the preview window is now 1000 (previously it was 400).
* 【★】プレビューウインドウでの最大ズーム倍率が1000になりました（以前は400でした）。

* ［☆］Additional French menu translations by Hendrik Chaltin; thanks!
* 【★】Hendrik Chaltin によりフランス語訳のメニューを追加；ありがとう！

###──Bugs fixed（修正されたバグ）

* ［☆］Three Panther problems are fixed. A few interface changes were made to improve appearance in Panther. This release is essential for Panther.
* 【★】Panther がらみの問題を３つ修正。Panther での外観を改善するために、いくつかのインターフェイスを変更しました。今回のリリースは Panther への対応に欠くことのできないものです。

	* ［☆］In Panther, older versions of TeXShop refuse to create new files, although they can open existing files. This was fixed by adding two lines to the "displayName" code.
	* 【★】Panther において、古いバージョンの TeXShop が、既存のファイルは開くものの、新規書類を作成しない──これは「 displayName 」コードに２行追加して修正しました。

	* ［☆］In Panther, the small yellow tags which display the current page when scrolling in multipage and double multipage display formats were blank. Also, the small yellow tags which display the size of a selection rectangle to copy a portion of the pdf window were blank. This is fixed.
	* 【★】Panther では、「見開きページ」もしくは「複数見開きページ」でスクロールをかけたときに、現在のページ数を表示する小さな黄色いタグが空白になっていました。また、プレビューウインドウの一部をコピーしようとして選択した方形部分のサイズを表示する小さな黄色いタグも空白なっていました。これを修正。

	* ［☆］On my system, Panther spellchecking often fails for all programs. This happens at boot time. The computer boots up, but even if the first program used is TextEdit or Mail, it refuses to "spell check as you type" and the "Spelling dialog" refuses to appear. I suspect this is due to a defective third party program on my disk, since other Panther users haven't seen the problem. But I haven't been able to isolate the bug. Once the problem occurs, TextEdit and Mail have minor text input glitches which are cured by turning off continuous spell checking. TeXShop had more serious glitches in this situation. So in 1.31, extra code has been added to turn off continuous spell checking when TeXShop starts if the spell checker is not available.
	* 【★】私のシステムでは、いずれのプログラムにおいても頻繁に Panther のスペルチェックがうまく機能しなくなります。これは起動時に発生します。コンピュータは起動しますが、最初に使うプログラムが TextEdit ないしは Mail であっても、「あなたが入力するのに合わせてスペルチェック」してくれませんし、「スペル・ダイアログ」も出してくれません。これは私のディスク上にあるサードパーティ製のプログラムの不具合ではないかと思われます──よその Panther ユーザはこの問題に遭遇していないのです。しかし、私は今のところバグを発見できていません。いったん問題が発生すると、TextEdit と Mail でのテキスト入力に些細な支障が生じますが、これは入力中の自動スペルチェックをオフにすることで直ります。こうした状況で、TeXShop にはもっと深刻な障害がありました。なので1.31では、スペルチェックが利用可能でない場合に、TeXShop 起動時に入力中の自動スペルチェックをオフにする余分なコードを追加しました。

* ［☆］Fixed a bug reported by Luis Sequeira: when text was dragged within the source window, it was always copied and pasted. It should have been cut and pasted unless the option key was down. This is fixed.
* 【★】Luis Sequeira により報告されたバグの修正：ソースウインドウ内でテキストをドラッグした際に、コピーされペーストされる。オプションキーを押しながらでないかぎり、カットされペーストされるべきである。これを修正。

* ［☆］Juan Luis Varona Malumbres slightly improved Spanish help (small icon for the list of help files in the drawer).
* 【★】Juan Luis Varona Malumbres がスペイン語ヘルプをいくらか改善（ドロワーに表示されるヘルプ・ファイルのリストの小アイコン）。

* ［☆］In two page mode, typesetting no longer scrolls to the first page.
* 【★】見開きページで表示しているとき、タイプセット後に最初のページに移動しないようにしました。

* ［☆］The new page and magnification buttons retain firstResponder status (as before 1.29) so users can experiment with several settings without clicking again for each experiment.
* 【★】新しいページ表示ボタンおよびズーム倍率ボタンでは（1.29以前のように）テキストフィールドが選択された状態〔 firstResponder 〕になっているので、いちいちクリックすることなく、いろいろな設定を試してみることができます。

* ［☆］In version 1.30 and before, if the user input an impossible line into the "Go To Line" dialog, the program could crash; this is fixed. Thanks to Eric Seidel for the bug report.
* 【★】バージョン1.30以前では、「移動行指定」ダイアログで不可能な行数を入力した場合、プログラムがクラッシュすることがありました；これを修正。このバグの報告を Eric Seidel に感謝。

* ［☆］Kevin Ballard, kevin@sb.org, contributed a new English.lproj folder with revised placement of interface items in preferences, slightly revised menu items, and other changes to improve the look of the interface in Panther. Many thanks!
* 【★】環境設定項目のインターフェイスの配置を見直し、メニュー項目をいくらか修正し、その他にも Panther でのインターフェイスを改善した新しい English.lproj フォルダを Kevin Ballard（ kevin@sb.org ）に提供してもらいました。どうもありがとう！

* ［☆］Made spacing changes for Panther in the German preference panel. Thanks to Martin Kerz for the suggestions.
* 【★】ドイツ語版の環境設定パネルで Panther 用にスペースを変更。Martin Kerz の提案に感謝。

* ［☆］There is a hidden preference item to turn off tag computation: "defaults write TeXShop TagSections NO" but this preference was disabled somewhere along the line and certainly in 1.30. It is enabled again.
* 【★】タグの自動追加機能をオフにする隠れた環境設定を用意しました：「 defaults write TeXShop TagSections NO 」がそれですが、この環境設定はいつの間にか（1.30では確実に）使えなくなっていました。これが再び使用可能になりました。

* ［☆］The Preference window is no longer hidden when the program is deactivated.
* 【★】TeXShop がアクティブでないときにも環境設定ウインドウが隠れなくなりました。

----
