TeXShop の日本語ヘルプファイルのアーカイブ (v1-5) です。

作業当時の日英対訳テキストをアップしています。

----
Version 1.35e
----

#How do I configue TeXShop?（ TeXShop の設定はどうすればよいか？）

##Preliminaries（まえがき）

［☆］Please read only the first two sections below if you are a new user installing TeXShop for the first time. If you are upgrading from a previous version, read these two and the next four sections. If you are familiar with TeXShop and want to customize it, read the remaining sections.

【★】もしあなたが TeXShop を初めてインストールする新規のユーザなら、最初の２つのセクションだけをお読みください。以前のバージョンからアップグレードする場合は、この２つに加えてその後の４つのセクションを読んでください。 TeXShop のことをよくわかっていてカスタマイズしたいのであれば、残りのセクションも読んでください。

［☆］When TeXShop first runs, it places default preference items, macros, templates, and typesetting engines in the user's library folder. If the program is later updated, these preference items, macros, etc. are not modified because the user may have edited them. In a few cases, important changes were made in the default items; these changes are listed here so users of previous versions can modify preferences and templates appropriately.

【★】TeXShop を初めて起動すると、デフォルトの設定項目やマクロ、テンプレート、タイプセット・エンジンなどが、ユーザのライブラリ・フォルダの中に置かれます。後々アプリケーションをアップグレードしても、これらの設定項目やマクロなどは更新されません──というのも、ユーザが編集している可能性があるからです。いくつかのケースにおいては、重要な変更がデフォルトの項目で行なわれました：そうした変更はここに挙げていますので、以前のバージョンからのユーザは初期設定やテンプレートを適切に修正できます。

［☆］TeXShop has a few hidden preferences for power users. Such users can also modify program behavior by installing various plist files. Details are provided below.

【★】TeXShop にはいくつかの隠れた環境設定が、パワーユーザ用にあります。こうしたユーザは種々の plist ファイルを設定してプログラムのふるまいを修正することができます。詳細は以下に示してあります。

［☆］New versions of TeXShop sometimes require additional menu items and other interface components. These new items appear in English even when the rest of the interface has been localized for another language. If users write me with appropriate translations, I will immediately make the changes in the copy of TeXShop on my web site. Write koch@math.uoregon.edu.

【★】TeXShop の新しいバージョンでは、追加のメニュー項目やその他のインターフェイス・コンポーネントが必要になることがあります。新しい項目については、その部分が他の言語にローカライズされるまでは、英語で表示されます。適当な翻訳を書き送ってくれれば、私のウェブサイトにある TeXShop のコピーにすぐに変更を施します。宛先は koch@math.uoregon.edu です。

##Did You Install Correctly（きちんとインストールしましたか？）

［☆］Starting with version 1.34 and continuing with version 1.35, TeXShop has a feature called pdfsync: clicking on a spot in the preview window activates the corresponding source window with the appropriate source line selected. This feature requires that files named "pdfsync.sty", "pdfsync.tex", and "pdfsync4context.tex" be installed ~/Library/texmf/tex/latex, ~/Library/texmf/tex/plain, and ~/Library/texmf/tex/context, respectively. Remove the old "pdfsync.sty" from ~/Library/texmf/tex/latex if it exists. Then find these new files in the TeXShop distribution and drag them to the appropriate folders. Here ~/Library is the Library folder in your home directory. You may have to create some or all of the folders texmf, tex, latex, plain, context.

【★】バージョン1.34以降ひきつづき1.35でも、 TeXShop には pdfsync という機能があります：プレビューウィンドウ上の一点をクリックすると、その箇所に応じてソースウィンドウをアクティブにするとともに、ソースコード内の相当する行を選択します。この機能を使うには 「pdfsync.sty」 「pdfsync.tex」 「pdfsync4context.tex」といったファイルを ~/Library/texmf/tex/latex ・ ~/Library/texmf/tex/plain および ~/Library/texmf/tex/context にそれぞれインストールしておく必要があります。もし古い「pdfsync.sty」があるなら、 ~/Library/texmf/tex/latex から取り除いておいてください。そのうえで、 TeXShop のディストリビューション内にある新しいファイルを、それぞれ適切なフォルダにドラッグしてください。 ~/Library はユーザのホーム・ディレクトリにあるライブラリ・フォルダのことです。 texmf ・ tex ・ latex ・ plain ・ context といったフォルダを作らねばならないかもしれません。

【補足】
* 上記以外にも、~/texmf 内の対応する各フォルダ（~/texmf/tex/latex ・ ~/texmf/tex/plain ・ ~/texmf/tex/context）にインストールすることで利用可能になるようです。
* また最新の小川版パッケージには pdfsync.sty が収録されていますので、改めてインストールする必要はありません。

［☆］TeXShop 1.35 comes with additional applescripts by Claus Gerhardt and Will Robertson. If you upgrade from a previous version, you will not automatically see those new scripts.

【★】TeXShop 1.35 には Claus Gerhardt と Will Robertson による追加の AppleScript が付属しています。前のバージョンからアップグレードした場合、これらは自動では現われません。

［☆］If you never edited the default macro set, you can obtain the new macros by going to the folder ~/Library/TeXShop and removing the entire Macros folder inside. The next time TeXShop starts, it will recreate this folder with the latest macros. It is not enough to remove the contents of the Macros folder; the entire folder must be removed.

【★】デフォルトのマクロ・セットを少しもいじっていないのであれば、 ~/Library/TeXShop 内の Macros フォルダを丸ごと取り除くことで、新しいマクロを導入できます。 TeXShop を立ち上げると、最新のマクロといっしょにこのフォルダを作り直します。 Macros フォルダの中のファイルを取り除くだけでは不十分です ； フォルダ自体を取り除かねばなりません。

［☆］If you have edited the default macros and want to add the new macro set, remove the Macros folder temporarily and let TeXShop create a new macro set. Then add your old macros using the Macro Editor.

【★】もしデフォルトのマクロを編集しており、そのうえで新しいマクロセットを追加したいのであれば、いったん Macros フォルダを取り除き、 TeXShop に新しいマクロセットを作成させます。その後で古いマクロを、マクロエディタを使って追加してください。

［☆］TeXShop 1.35 comes with new templates by Will Robertson. These templates will not automatically be installed. You can obtain them by going to the folder ~/Library/TeXShop and moving the entire Templates folder inside to the Desktop. The next time TeXShop starts, it will recreate this folder with the latest Templates. You can then move old Templates you have edited from the folder on the desktop to the newly created folder ~/Library/TeXShop/Templates.

【★】TeXShop 1.35には Will Robertson による新しいテンプレート集が付属しています。このテンプレートは自動ではインストールされません。 ~/Library/TeXShop 内のテンプレート・フォルダを丸ごとデスクトップに移動させることで手に入れます。次回 TeXShop を起動した際に、最新のテンプレートを含んだテンプレート・フォルダが作り直されます。その後、自分で編集した古いテンプレートを、デスクトップに置いたフォルダから新しく作られたフォルダ ~/Library/TeXShop/Templates へ移します。

##Recommended Preference Changes（おすすめの設定変更）

［☆］Users should consider changing a small number of default preferences provided by TeXShop. Some of these changes depend on characteristics of individual displays and cannot be set until you use the program.

【★】TeXShop が提供するデフォルトの環境設定のいくつかは変更したほうがよいでしょう。こうした変更の中には、個々のモニタの特質に依存していて、実際に使ってみるまでは設定しかねるものもあります。

［☆］By default, TeXShop opens source and preview windows in the spot they last appeared. This only makes sense when you deal with one document at a time. It is usually better to open source and preview windows in a predetermined optimal position. To make that happen, typeset a simple document. Then arrange the position and size of the source and preview windows. Side by side is best if your screen is large enough. Open TeXShop preferences. In the "Document" tab, select "All Windows Start At Fixed Position" and click "Set With Current Position." Make the same change in the "Preview" tab.

【★】デフォルトでは、ソースウィンドウとプレビューウィンドウは、最後に閉じたときの位置で開かれます。１度に１つの文書しか扱わないときは、これでもいいでしょう。しかし通常は、前もって決めておいた最適な位置でソースウィンドウとプレビューウィンドウを開くのがいいでしょう。位置決めのために、簡単な文書をタイプセットします。そしてソースウィンドウとプレビューウィンドウの位置とサイズを調節してください。使っているモニタが十分に大きければ、横に並べて配置するのが最良です。 TeXShop の環境設定を開きます。 「書類」タブで「いつも同じ位置で開く」を選び、 「現在の位置に設定」をクリックしてください。 「プレビュー」タブでも同じ変更を行ないます。

［☆］This is a good time to set the magnification in the preview window. Use the Scale button at the top of this window to select the optimal magnification. Under the "Preview" tab of Preferences, type the appropriate magnification and push the "Set" button and then the "OK" button.

【★】プレビューウィンドウの倍率を設定するのにもいい機会です。プレビューウィンドウの上部にあるスケール・ボタンで最適な倍率を選んでください。そして環境設定の「プレビュー」タブで倍率を入力して「設定」ボタンを押します──そのうえで「ＯＫ」ボタンを押してください。

［☆］Finally, you may wish to deal with a security issue. By default, TeXShop is configured to permit pdftex and pdflatex to call other programs during typesetting. When pdftex finds a graphic illustration in a format it cannot understand, it will automatically call a conversion program to convert the graphic to a useful format. For example, eps files will be converted to pdf and tif files will be converted to png.

【★】最後に、セキュリティ問題に触れるべきかもしれません。デフォルトで TeXShop は、タイプセット時に他のプログラムを呼び出すことを pdftex と pdflatex に許可しています。処理できない形式のグラフィック・イラストがあると pdftex は、自動的に変換プログラムを呼び出して利用可能な形式の画像ファイルに変換します。たとえば、 eps ファイルは pdf に変換され、 tif ファイルは png ファイルに変換されます。

［☆］However, the configuration allows pdftex to call ANY program. Conceivable, a user could mail you a tex source file which does unpleasant things to your system during typesetting. If this is a concern, go to the "Engine" tab in Preferences and check the box labeled "Shell Escape Warning." When this button is checked, a dialog will appear the first time a file is typeset during a TeXShop session, allowing you to turn off this feature for that file so pdftex cannot call other programs during typesetting. Thus you can use automatic conversion for your own files, but play it safe with source files from others.

【★】かしながらこの設定では pdftex に、''いかなる''プログラムを呼び出すことをも許可してしまいます。あるユーザがあなたに TeX のソースファイルをメールで送ってきて、タイプセット中にそれが、あなたのシステムに対してよからぬことをしでかす──というのも、ありうることではあります。これが心配な場合には、環境設定の「内部設定」タブで「Shell Escape を警告」と書いてあるボックスにチェックを入れてください。このチェックが入っていると、あるファイルを TeXShop で初めてタイプセットするときに、そのファイルに対してこの機能をオフにできるダイアログボックスが表示されます──そのため pdftex は、タイプセット時に他のプログラムを呼び出せなくなります。したがってあなた自身のファイルについては自動変換が使えますが、他人からのソースファイルに対しては安全を講じることができます。

##Converting Graphic Formats Automatically（画像形式を自動的に変換する）

［☆］Support for tiff files has been removed from the latest versions of pdftex and pdflatex. However, it is possible to configure TeXShop so it will automatically convert graphics in tiff format to png format during typesetting. As a bonus, the program will convert graphics in eps format to pdf format during typesetting. In both cases the original graphic file is preserved and a new file with appropriate format is created. Tiff files must still have extension ".tif" rather than ".tiff".

【★】pdftex と pdflatex の最新バージョンでは tiff ファイルのサポートがなくなりました。しかしながら TeXShop では設定可能なので、 tiff 形式の画像はタイプセット時に自動的に png 形式に変換されます。加えて eps 形式のグラフィックもタイプセット時には pdf 形式に変換されます。どちらの場合にも、もともとの画像ファイルはそのままで、新しいファイルがそれぞれのフォーマットで作成されます。 tiff ファイルはいまだに拡張子が「.tiff」ではなく「.tif」でなければなりませんが。

［☆］New installations of TeXShop are already configured appropriately. Users who are upgrading should make the changes listed in the next two sections. They should also use Gerben Wierda's i-Installer to install the following packages, if not already present:

【★】新規にインストールした TeXShop では、あらかじめ適切な設定になっています。アップグレードするユーザは、次の２つのセクションで挙げている変更を行なってください。また Gerben Wierda の i-Installer を使って、以下のパッケージをインストールしておきます──まだ入れていなければですが：

* Ghostscript 8
* Freetype 2
* wmf and iconv conversion support
* ImageMagick

##Default Preference Items（初期設定について）

［☆］TeXShop 1.35 comes with a new Find panel, which requires system 1.3 or later. Other users will still see the old panel. It is possible to revert to the old panel using TeXShop preferences, but most users will find that the new panel is more powerful; it supports regular expressions. At first this panel may not behave as you expect, but the panel remembers the various choices it presents, and you should be able to configure it to behave as you expect.

【★】TeXShop 1.35 には新しい検索パネルがあります──これにはシステム10.3以降が必要となります。それ以外では依然として従来のパネルが表示されます。 TeXShop の環境設定で、従来の Apple 標準のパネルに切り替えることができますが、新しい検索パネルのほうがよりパワフルなはずです ； 正規表現をサポートしているのです。最初のうちは予期したように動作しないかもしれませんが、パネルはそこに表示されている各種の選択を記憶していますし、思いどおりに動作するよう調整できることでしょう。

［☆］The remaining comments are for users with versions before 1.33, who may not have made these changes earlier. In the TeXShop preference panel with the Engine tab, the following changes should be made:

【★】残りの解説は、 1.33以前のバージョンのユーザ用のものです──以下の変更を前もって行なっていないかもしれないので。 TeXShop の環境設定パネルには「内部設定」タブがありますが、次のように変更してください：

* 	1.  The pdftex preference should be
* 	1.  pdftex の設定は──
	pdftex --shell-escape

* 	2.  The pdflatex preference should be
* 	2.  pdflatex の設定は──
	pdflatex --shell-escape

* 	3.  The altpdftex preference should be
* 	3.  altpdftex の設定は──
	altpdftex --maxpfb

* 	4.  The altpdflatex preference should be
* 	4.  altpdflatex の設定は──
	altpdflatex --maxpfb

［☆］Japanese users of TeXShop 1.26 or earlier should replace the file ~/Library/TeXShop/LatexPanel/completion.plist with the English version, because a modification for Japanese(ShiftJIS ¥) is no longer necessary. To make this happen, remove the completion.plist file from the folder; a new file will be created the next time TeXShop starts.

【★】TeXShop 1.26 以前からの日本のユーザは、 ~/Library/TeXShop/LatexPanel/completion.plist というファイルを英語版のものと差し替えてください── Japanese(ShiftJIS ¥) 用の修正はすでに不要となりました。あるいはこの completion.plist ファイルをフォルダから取り除いても同じことです ； 新しいファイルは、次に TeXShop を起動したときに作られます。

----

日本語環境で TeXShop 1.35 にアップグレードする際の注意点

TeXShop 1.35 では、日本語 pTeX 用の設定プロファイルが変更されました。以前のバージョンを使っていた方は、

	~/Library/TeXShop/bin

（つまりホーム・ディレクトリの「ライブラリ」フォルダの中の「TeXShop 」フォルダ内にある「bin」というフォルダ）

を一度削除してから TeXShop を起動し直して下さい。このフォルダが古いままでは、新しい設定プロファイルを利用できませんし、タイプセットが行なえないこともあります。

##Default Latex Template（デフォルトの LaTeX テンプレート）

［☆］The file LatexTemplate.tex in ~/Library/TeXShop/Templates should contain the following lines if they are not already present:

【★】~/Library/TeXShop/Templates に置かれている LatexTemplate.tex というファイルには、以下の数行が含まれていなければなりません──もしもない場合にはですが：

	\usepackage{graphicx}
	\usepackage{epstopdf}
	\DeclareGraphicsRule{.tif}{png}{.png}{`convert #1 `basename #1 .tif`.png}

##Hidden Preference Items（隠れた環境設定項目）

［☆］TeXShop adds lines which begin with the words \section, \subsection, \subsubsection, or \chapter to the Tag menu. To turn this off, run Terminal and type the following command. Change the word NO to YES to turn the behavior back on.

【★】TeXShop では、\section ・ \subsection ・ \subsubsection あるいは \chapter という語で始まっている行をタグ・メニューに追加します。これをオフにするには、ターミナルを起動し、以下のコマンドを打ち込みます。 NO を YES に変えれば、動作はまた元に戻ります。

	defaults write TeXShop TagSections NO

［☆］When syntax coloring is on, comments are colored red, commands are colored blue, and the symbols $, {, and } are colored dark green. These colors can be changed. A color is determined by the red, green, and blue components of the color; each is a number between 0.00 and 1.00. To change the color of $, {, and } to bright green, issue the following commands in Terminal:

【★】ソースウィンドウで「ソースのカラー表示」がオンになっていると、コメントは赤、コマンドは青、 「 $ 」 「 { 」 「 } 」といった記号は暗緑色になります。これらの色合いは変更できます。色は、赤・緑・青（Ｒ・Ｇ・Ｂ）の成分で決定されています ； 各成分は 0.0 から 1.0 までの数です。 「 $ 」 「 { 」 「 } 」の色を明るい緑色に変えるには、 Terminal から次のようなコマンドを送ります──

	defaults write TeXShop markerred 0.0
	defaults write TeXShop markergreen 1.0
	defaults write TeXShop markerblue 0.0

［☆］To change the comment color, replace "marker" with "comment"; to change the command color, replace "marker" with "command".

【★】コメントの色を変更するには「marker」を「comment」に置き換えます ； コマンドの色を変えるには「marker」を「command」に置き換えます。

［☆］The background color of the source window can be changed. For example, to set this background to (r, g, b) = (.42, .39, .77), issue the following commands in Terminal:

【★】ソースウィンドウの背景色を変えることができます。たとえば、背景色を (r, g, b) = (.42, .39, .77) にするには、次のコマンドを Terminal から送ります：

	defaults write TeXShop background_R 0.42
	defaults write TeXShop background_G 0.39
	defaults write TeXShop background_B 0.77

［☆］The text color of the source window can be changed. This change requires that syntax coloring be on. For example, to set this foreground color for text to (r, g, b) = (.42, .39, .77), issue the following commands in Terminal:

【★】またソースウィンドウの文字色を変えることもできます。この設定は「ソースのカラー表示」がオンになっているときにのみ有効です。前面の色を (r, g, b) = (.42, .39, .77) にするには、次のコマンドを Terminal から送ります：

	defaults write TeXShop foreground_R 0.42
	defaults write TeXShop foreground_G 0.39
	defaults write TeXShop foreground_B 0.77

［☆］By using the previous pairs in combination, the source window can be made to display white text on a black background or other coloring schemes as desired.

【★】上記の設定を組みにして同時に使うことで、黒い背景に白い文字、あるいはその他の色の組み合わせといったことがエディタで可能になります。

［☆］The background color of the preview window can also be changed. For example, to set this background to (r, g, b) = (.42, .39, .77), issue the following commands in Terminal. Change these numbers to 1 to convert back to a white background. It may be easier to view colored TeX documents with a gray background. The background color will not affect printing.

【★】プレビューウィンドウの背景色も変えることができます。たとえば、背景色を (r, g, b) = (.42, .39, .77) にするには、下記のコマンドを Terminal から送ります。これらの数字をすべて１にすると、背景は白に戻ります。カラー化した TeX 文書を見るには、背景が灰色になっているほうが見やすいでしょう。背景色は印刷には影響を与えません。

	defaults write TeXShop Pdfbackground_R 0.42
	defaults write TeXShop Pdfbackground_G 0.39
	defaults write TeXShop Pdfbackground_B 0.77

［☆］The transparency of the source, preview, and console windows can be changed. For example,

【★】ソース、プレビュー、コンソールの各ウィンドウの透明度を変更することができます。

	defaults write TeXShop ConsoleWindowAlpha 0.75
	defaults write TeXShop SourceWindowAlpha 0.75
	defaults write TeXShop PreviewWindowAlpha 0.75

［☆］Here an alpha value of 0.00 is completely transparent and an alpha value of 1.00 is completely opaque. Using these commands cautiously.

【★】ここでアルファ値が 0.00 なら完全に透明となり、アルファ値が 1.00 なら完全に不透明となります。これらのコマンドは用心してお使いください。

［☆］TeXShop can be configured to save a backup file whenever it saves or typesets a source file. To turn this on, run Terminal and type the following command. Change YES to NO to turn it off.

【★】ファイルを保存したりタイプセットしたりする際にかならずバックアップファイルを作成するよう TeXShop を設定することができます。これをオンにするには、 Terminal を起動し、以下のコマンドを打ち込みます。オフにするには YES を NO に変えてください。

	defaults write TeXShop SaveBackup YES

［☆］Occasionally during typesetting, the .aux files, .log files, and other files created automatically by TeX become corrupted and must be removed. TeXShop has a "Trash AUX Files" menu item and associated button in the console window. When either item is selected, TeXShop moves to the trash all files in the folder containing the source file with the same name as the source name, and extensions .aux, .bbl, .blg, .brf, .glo, .idx, .ilg, .ind, .ioa, .log, .log, .lot, .mtc, .mlf, .out, .pdfsync, and .toc. Other extensions can be added to this list, one by one. For instance, to add .dvi files to this list:

【★】タイプセットの際に時たま、 TeX によって自動的に生成される .aux ファイルや .log ファイル、その他のファイルがおかしくなったりして、取り除かねばならないことがあります。 TeXShop には「作業ファイルを削除」というメニュー項目があり、さらにコンソール・ウィンドウにもこれと連動しているボタンがあります。このいずれかを選択すると TeXShop は、ソースファイルを含むフォルダ内にあって、ソースと同じ名前で、拡張子が aux ・ blg ・ brf ・ ccs ・ ent ・ fff ・ glo ・ idx ・ idv ・ ilg ・ ind ・ ioa ・ lg ・ log ・ lot ・ mtc ・ mlf ・ out ・ pdfsync ・ toc ・ ttt ・ wrm ・ xref ・ 4ct ・ 4tc となっているファイルをすべてゴミ箱へと移動します。このリストには、その他の拡張子を、ひとつずつ追加することができます。例として、.dvi ファイルを加えるには：

	defaults write TeXShop OtherTrashExtensions -array-add "dvi"


［☆］To remove all added extensions and return to the original list:

【★】追加した拡張子を取り除いて元々のリストに戻すには──

	defaults write TeXShop OtherTrashExtensions -array

［☆］Sometimes a more extensive cleanup is desirable. If the option key is held down while choosing "Trash AUX Files," TeXShop uses the %&SourceDoc and "Set Project Root" mechanisms to find the root file. It then moves all files in the folder of this file and any subfolders of this folder to the trash if they have appropriate extensions, regardless of the names of the files. This behavior can be made the default behavior for "Trash AUX Files" without using the option key; issue the command

【★】時として、さらに徹底したクリーンナップが望ましいことがあります。オプションキーを押しながら「作業ファイルを削除」を選択すると TeXShop は、%&SourceDoc および「プロジェクトルートの設定」機能を使ってルートファイルを探し当てます。そしてルートファイルのあるフォルダ内、およびこのフォルダ内のサブフォルダの中にあり、該当する拡張子の付いたすべてのファイルを、そのファイル名の如何に関わらず、ゴミ箱に移します。 「作業ファイルを削除」の動作を、オプションキーを押すことなく上述のようにすることもできます ； 次のようなコマンドを入れてください──

	defaults write TeXShop AggressiveTrashAUX YES

［☆］TeXShop can be configured to automatically refresh pdf views when the pdf file changes. To do this, once a second it examines the date and time when the pdf was last written to see if this information has changed. The time interval between these checks can be modified. To do this, run Terminal and type the following command. Change 1.00 to the number of seconds desired.

【★】pdf ファイルが変更されたときに pdf 画面を自動的に更新するよう TeXShop を設定することができます。自動更新のためにTeXShop は、１秒に１度、 pdf が最後に書き変えられた日付と時刻に変更があったかどうかチェックします。このチェックの間隔は変更することができます。 Terminal を立ち上げ、次のコマンドを打ち込みます。 1.00 をお好みの秒数に変えてください。

	defaults write TeXShop RefreshTime 1.00

［☆］Automatic refresh for pdf views is useful if TeXShop is configured to use an external editor, or if a tex file is opened by "Open For Preview...". In these cases, a .tex file is opened, but TeXShop only shows the associated pdf file. TeXShop also allows pdf files to be opened directly; this is useful for a brief glance at illustrations before embedding them in a TeX document. If you want pdf files opened for an external editor to be refreshed automatically, but pdf files opened for a brief glance to be left alone, run Terminal and type the following command. The default value of this preference is YES.

【★】pdf の自動更新は、外部エディタを使うよう設定しているか、あるいは「プレビューを開く...」で TeX ファイルを開いたときに便利です。これらの場合には、.tex ファイルは開かれていますが、 TeXShop ではただ関連づけの行なわれた pdf ファイルを表示しているにすぎません。 TeXShop はまた、 pdf ファイルを直接開くこともできます ； これはイラストを TeX 文書に埋め込む前に一瞥しておくのに便利です。外部エディタのために開いた pdf ファイルは自動的に更新させたいけれども、一瞥するために開いた pdf ファイルは自動更新させたくない場合には、 Terminal を立ち上げ、以下のコマンドを打ち込みます。この設定のデフォルトの値は YES です。

	defaults write TeXShop PdfFileRefresh NO

［☆］When TeXShop opens a .tex file for an external editor, it checks the dates of the tex and pdf files to make sure that the pdf output is up to date. If this output is not up to date or does not exist at all, TeXShop typesets the .tex file again. To turn off this behavior, run Terminal and type the following command.

【★】外部エディタで .tex ファイルを開いた際に、 TeXShop は TeX ファイルと pdf ファイルの日付をチェックし、 pdf 出力が最新の状態になっているかどうか確認します。もし出力が古くなっているか、まったく存在しないようなら、 TeXShop は .tex ファイルを改めてタイプセットします。この動作をオフにするには、 Terminal を立ち上げ、以下のコマンドを打ち込みます。

	defaults write TeXShop ExternalEditorTypesetAtStart NO

［☆］There is a hidden preference to set the default size of the matrix in the Matrix Panel:

【★】行列パネルにおける行列のデフォルトのサイズを設定する隠れた環境設定があります：

	defaults write TeXShop matrixsize 12


［☆］There is a new checkbox tool for the Preview window named "ShowSync." It is not part of the default toolkit for this window. When this item is checked, synchronization spots are show in the Preview document. The item is not shown when a preview window first appears, but this changed be changed via:

【★】「Sync」という名前の新しいチェックボックスが、プレビュー・ウィンドウ用ツールにあります。これはデフォルトのツール・キットの一部にはなっていません。この項目がチェックされると、シンクロ・スポットをプレビュー文書内で見ることができます。プレビュー・ウィンドウが最初に表示された際は見えませんが、これを以下のようにして変更できます：

	defaults write TeXShop ShowSyncMarks YES

［☆］When the preview window is updated after typesetting, it comes to the front. This behavior causes trouble for uses with an X11 editor running in Apple's X11 Window Manager. For these users, the behavior can be turned off via:

【★】タイプセット後にプレビュー・ウィンドウが更新されると、ウィンドウは前面に来ます。この動作は、 Apple の X11 Window Manager で実行させている X11 エディタの使用でトラブルの種になります。そうした場合には、以下のようにしてこの動作をオフにできます：

	defaults write TeXShop BringPdfFrontOnAutomaticUpdate NO

##.plist Files（ .plist ファイル）

［☆］Mac OS X makes extensive use of xml files; xml is a structured language closely related to html.

【★】Mac OS X は xml ファイルを広汎に利用しています ； xml は html と密接な関連のある構造化言語です。
［☆］TeXShop uses five xml files for configuration: completion.plist, autocompletion.plist, KeyEquivalents.plist, Macros_Latex.plist, and Macros_Context.plist. These files are used to configure the Latex Panel, Auto Completion, the Keyboard Menu Shortcuts, and the Macros menu. Details are given below. These files are automatically created in subfolders of ~/Library/TeXShop when TeXShop first runs.

【★】TeXShop は５つの xml ファイルを設定のために用いています： completion.plist ・ autocompletion.plist ・ KeyEquivalents.plist ・ Macros_Latex.plist それに Macros_Context.plist です。これらのファイルは LaTeX パネル、オートコンプリート、メニュー項目のショートカット・キー、マクロ・メニューなどの設定に利用されています。詳細については後述します。これらのファイルは TeXShop を初めて起動する際に ~/Library/TeXShop のサブフォルダの中に作られます。

［☆］Files of type plist are ordinary text files. They can be opened and edited with TeXShop, TextEdit, or other text editors. Each of the files except Macros.plist has a comment at the top explaining the file format. Editing is straightforward, but somewhat tedious. Macros_Latex.plist and Macros_Context.plist will never need to be edited because TeXShop has a Macro Editor built in.

【★】plist 形式のファイルはごく普通のテキストファイルです。 TeXShop や TextEdit あるいはその他のテキストエディタで開いたり編集したりできます。 Macros.plist 以外は、それぞれのファイルの最初にファイル形式について説明されています。編集は簡単ですが、いくぶん退屈です。 Macros_Latex.plist と Macros_Context.plist の２つは、編集の必要はないでしょう── TeXShop にはマクロエディタがあるのですから。

［☆］If a plist file contains unicode characters, it needs to be edited and saved in UTF-8 format. Before opening such a file in TeXShop, change the TeXShop encoding preference to UTF-8. Then edit and save the file. Then change the encoding preference back to the original value. The default value is MacOSRoman if you did not reset it earlier.

【★】もし plist ファイルが Unicode 文字を含んでいるのであれば、 UTF-8 形式で編集し保存する必要があります。 TeXShop でそうしたファイルを開く前に、 TeXShop のエンコーディング設定を UTF-8 に変更してください。そのうえでファイルを編集したり保存したりします。その後エンコーディング設定は元に戻しておきます。もし以前に設定しなおしていないなら、デフォルトでは MacOSRoman です。

［☆］Users with the Developer distribution installed will discover that double clicking a .plist file opens the file in a program named Property List Editor. Property List Editor is useful for editing plist files, but it is buggy and does not display the comments. So it is better to use TeXShop.

【★】Developer Tools をインストールしたユーザーなら、.plist ファイルをダブルクリックすると、 Property List Editor というプログラムでファイルが開かれることでしょう。 Property List Editor は plist ファイルを編集するのに便利ですが、バグだらけですし、コメントを表示できません。 TeXShop を使うほうがいいでしょう。

##Modifying the Latex Panel（ LaTeX パネルを一部変更する）

［☆］The Latex panel contains a "Custom" tab; up to sixteen user-defined buttons can be placed on this tab. Other buttons in the Latex panel cannot be changed, but the text inserted when the button is pressed can be changed.

【★】LaTeX パネルには「カスタム」というタブがあります ； このタブには最大で16個のユーザ定義用のボタンが配置されています。 LaTeX パネルにある、その他のボタンは変更できません──が、ボタンが押されたときに挿入されるテキストを変更することはできます。

［☆］The comments at the start of the file "completions.plist" explain how to make these changes. To do so, edit the file ~/Library/TeXShop/LatexPanel/completions.plist with TeXShop. Be sure to edit and save in UTF-8 format if you use Unicode characters.

【★】「completions.plist」というファイルの最初にあるコメントに、どうやって変更するのかが説明されています。変更するには、 ~/Library/TeXShop/LatexPanel/completions.plist というファイルを TeXShop で編集します。もし Unicode 文字を使用するのであれば、かならず UTF-8 形式で編集し保存してください。

##Modifying Auto Completion（オートコンプリートを変更する）

［☆］The preference panel contains a checkbox to turn auto completion on or off; by default it is off. When auto completion is on, typing certain characters inserts an entire string in the source file. For instance, typing ^ inserts ^{ }, with the cursor positioned inside the brackets.

【★】環境設定パネルにはオートコンプリートをオン／オフするチェックボックスがあります ； デフォルトではオフになっています。オートコンプリートをオンにすると、特定の文字を打ち込むことで一連の文字列をソースファイルに挿入することができます。たとえば、^ を打ち込むと、カーソルを間に挟んだ括弧── ^{ } が挿入されます。

［☆］Auto completion elements can be modified and created by editing the file "autocompletion.plist". The comments at the start of this file explain how to make changes. To do so, edit the file ~/Library/TeXShop/Keyboard/autocompletions.plist with TeXShop. Be sure to edit and save in UTF-8 format if you use Unicode characters.

【★】オートコンプリートの内容は「autocompletion.plist」というファイルを編集することで修正したり新たに作成したりできます。このファイルの最初にあるコメントに、どのように変更すべきかが説明されています。このファイル── ~/Library/TeXShop/Keyboard/autocompletions.plist を TeXShop で編集してください。もし Unicode 文字を使用するのであれば、かならず UTF-8 形式で編集し保存してください。

##Redefining Keyboard Menu Shortcuts（メニュー項目のショートカット・キーを再定義する）

［☆］The keyboard menu shortcuts for TeXShop can be redefined. To do this, read the comments at the top of the file "KeyEquivalents.plist" and make appropriate changes. To do so, edit the file ~/Library/TeXShop/Menus/KeyEquivalents.plist with TeXShop. Be sure to edit and save in UTF-8 format if you use Unicode characters.

【★】TeXShop のメニュー項目のショートカット・キーは再定義することができます。再定義するには「KeyEquivalents.plist」というファイルの冒頭にあるコメントを読み、適切な変更を施します。 TeXShop を使ってファイル── ~/Library/TeXShop/Menus/KeyEquivalents.plist を編集します。もし Unicode 文字を使用するのであれば、かならず UTF-8 形式で編集し保存してください。

##Modifying the Macros Menu（マクロ・メニューを変更する）

［☆］TeXShop contains a Macro Editor, so it should never be necessary to directly modify the Macros.plist file.

【★】TeXShop にはマクロエディタがあるので、 Macros.plist ファイルを直接いじる必要はありません。


----
[もくじ](README.md)
