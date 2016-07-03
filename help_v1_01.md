TeXShop の日本語ヘルプファイルのアーカイブ (v1-1) です。

作業当時の日英対訳テキストをアップしています。

----
Version 1.35e
----

#Basic Help（基本的なヘルプ）（その１）

##Preliminaries（まえがき）

［☆］TeXShop is a Mac OS X program which can typeset TeX and LaTeX files and preview the output on the screen. The program usually typesets using pdftex or pdflatex instead of tex or latex. These programs output pdf files rather than dvi files. Since pdf is the native graphics format of Mac OS X, it is easy to display the output on the screen. Pdftex and pdflatex were written by Han The Thanh, Petr Sojka, and Jiri Zlatuska.

【★】TeXShop は Mac OS Ｘ用のプログラムです── TeX および LaTeX ファイルをタイプセット（組版）し、出力結果を画面上でプレビューすることができます。 TeXShop は通常、 TeX や LaTeX の代わりに pdftex あるいは pdflatex を使ってタイプセットを行ないます。これらのプログラムは dvi ファイルではなく pdf ファイルを出力します。というのも pdf は Mac OS Ｘのネイティブなグラフィック・フォーマットなので、画面上に出力を表示するのが容易なのです。 pdftex と pdflatex は Han The Thanh ・ Petr Sojka および Jiri Zlatuska によって作成されました。

［☆］The pdf files created by TeXShop are standard pdf files which can be given to other people and displayed on a variety of computer systems. For example, they can be displayed by Adobe Acrobat.

【★】TeXShop によって生成される pdf ファイルは、標準的な pdf ファイルなので、他の人々に渡したり、いろいろなコンピュータ・システムで表示させたりできます。たとえば Adobe Acrobat で表示させることができます。

［☆］TeXShop does not include TeX. Instead it uses the standard TeX distribution teTeX, a wonderful collection of the entire suite of TeX programs, files, and utilities created by Thomas Esser. This collection (the standard version of TeX on Linux systems) has been compiled for Mac OS X by Gerben Wierda. Instructions for obtaining it are given below.

【★】TeXShop に TeX は含まれていません。その代わり TeX の標準的なディストリビューションである teTeXを用います── teTeX は TeX プログラム、ファイル、ユーティリティなどを一式取り揃えた素晴らしいコレクションで、 Thomas Esser によって作成されたものです。このコレクション（ Linux システムにおける TeX の標準版）が、 Gerben Wierda によって Mac OS Ｘ 用に移植されました。 teTeX を手に入れるための手引きを次に示します。

【★】その前に、日本語ユーザ用に pTeX の導入について、次項「pTeX と TeXShop で日本語環境を構築する」で簡単に述べておきます。

##pTeX と TeXShop で日本語環境を構築する（ Getting started with pTeX and TeXShop ）

くりかえしますが、 TeXShop に TeX は含まれていません。なので TeXShop とは別に TeX パッケージをインストールしておく必要があります。英語環境では Gerben Wierda による i-Installer でのインストールが推奨されていますが、日本語による TeX 文書の作成もお望みなら、 pTeX を含むパッケージを用いるべきでしょう。 pTeX（ Publishing TeX ）は、横組みだけでなく縦組みの日本語機能も追加した日本語TeX で、アスキーにより作成されました。詳細については http://www.ascii.co.jp/pb/ptex/index.html をご覧ください。

上記のウェブサイトでもソースファイルを配布していますが、 pTeX 以外にも dvipdfmx や Ghostscript といった関連プログラムをインストールする必要があります。幸いなことに Mac OS X 用にコンパイル済みのバイナリ・パッケージがいくつか配布されており、これらを使うことで、容易にインストールできるようになっています。主要なパッケージについて以下に示します。

* pTeX package パッケージ（桐木版）
	* http://www.r.dendai.ac.jp/kiriki/tex/
	* 日本国内の定番 pTeX パッケージです。利用しているユーザーも多く、アップデートは年度ごとに１回となっています。 Ghostscript まで含まれたオールインワンの ptex package をダウンロードしてインストールしてください。東京電機大学の桐木紳（ Shin Kiriki ）さんにより配布されています。

* pTeX(sjis) + JMacros package for Mac OS X（小川版）
	* http://www2.kumagaku.ac.jp/teacher/herogw/
	* Big と Small ２つの pTeXパッケージが用意されていますが、 Big［160MB］の選択をお勧めします（コンポーネントの要不要の判別がつかない初心者の方も pdftex を必要とする理工系の方も）。これに加えて Ghostscript もダウンロードしてインストールします。更新やバグ修正が早いことに加え、 「文系縦組用」に便利なツール類が含まれています。熊本学園大学の小川弘和（ Hirokazu Ogawa ）さんにより配布されています。

* MacOS X用pTeX, GhostScript, TeXShop関連パッケージ（井上版）
	* http://www.ns.musashi-tech.ac.jp/~inoue/Pages/MacOSX/macosx.ptex.html
	* 多数のサブパッケージに分かれており、こまかい機能調整が可能な上級者向けパッケージです。 pTeX ・ Ghostscript などが必要です（一括取得用コマンドもあるようです）。武蔵工業大学の井上浩一（ iNOUE Koich! ）さんにより配布されています。

この３つのパッケージ以外にも利用可能なものがあります。

* Easy Package for Mac OS X 
	* http://www.ie.u-ryukyu.ac.jp/darwin2/
	* ネットワーク経由のインストーラです。 pTeX 以外にも、さまざまな UNIX 系ツールをネットワーク経由でインストールできます。白土浩（ Hiroshi Shiratsuchi ）さんにより配布されています。

* ［改訂第３版］LaTeX2e美文書作成入門
	* http://oku.edu.mie-u.ac.jp/~okumura/texfaq/bibun3/
	* 奥村晴彦（ Haruhiko Okumura ）さんによる書籍です。日本語TeX 利用における重要な解説書のひとつです。付録 CD-ROM に pTeX と ghostscript のコンパイル済みバイナリ・パッケージが収録されています。

桐木版、小川版、井上版をインストールした場合、 TeXShop バージョン 1.34 では、環境設定の「設定プロファイル」でそれぞれの版を選択して初期設定を行なっていましたが、バージョン 1.35 ではこれが変更されました。【重要】以前のバージョンからのユーザはかならず「アップグレード時の注意」にしたがって、適切な変更を行なってください。各プロファイルの詳細に関してはヘルプ項目「環境設定」を参照してください。さらに日本語エンコーディングについて知るには、ヘルプ項目「日本語エンコーディングと \ ¥ 文字の扱い」を参照します。

pTeX + TeXShop で日本語TeX文書を作成する際の注意点について述べておかねばなりません。 TeXShop には「pdfTeX」 「TeX + Ghostscript」 「パーソナルスクリプト」の３種類のモードがあり、それぞれにタイプセットの方式が異なっています。日本語環境では「**TeX＋Ghostscript**」を使うとよいでしょう。 TeX ファイルは pTeX によって dvi ファイルに変換され、さらに dvipdfmx によって pdf ファイルに変換されます。 「TeX＋Ghostscript」モードで利用できる画像形式は、基本的には eps と ps ですが、 dvipdfmx 自体は pdf ・ jpg ・ png ・ mps を扱うことも可能です（ jpg ・ png ・ pdf 画像の扱いについては、ヘルプ項目「画像を入れる」を参照してください）。

「TeX + Ghostscript」が＋記号で結ばれていることに触れておくべきかもしれません──これはシェルスクリプトにより platex -> dvipdfmx という動作が実行されているにすぎないことを意味しています。つまり、たとえば目次の作成などのように複数回のタイプセットが必要な場合には、いくぶん無駄が生じる、ということです。こうした無駄を省きたいユーザは、 platex -> platex -> dvipdfmx というように動作するマクロ・スクリプトを利用することができます。マクロについて詳しく知りたい場合は「マクロ・ヘルプ」をお調べください。

「pdfTeX」モードは、 pdftex プログラムを利用して tex ファイルを直接 pdf ファイルに変換します。 「TeX＋Ghostscript」モードよりも高速にタイプセットを行なうことができます。しかし残念なことに日本語には対応していません──科学系の学術論文など、英文だけを扱う場合に使うと便利でしょう。 「pdfTeX」モードでは pdf ・ jpg ・ png ・ mps 形式の画像ファイルを貼り込むことができます。 eps や tif といった形式のファイルは、直接は扱えませんが、タイプセット時に自動的に pdf ないしは png 形式に変換する仕組みが用意されています（詳細はヘルプ項目の「画像を入れる」 「画像形式を自動的に変換する」を参照してください）。

タイプセットモードは メニューバーの「タイプセット」メニューで書類ごとに設定することができます。また、環境設定パネルの「タイプセット > デフォルトのスクリプト」で デフォルトのタイプセットモードを変更することができます。

以下にそれぞれの違いをまとめておきます。

| タイプセットモード | pdfTeX | TeX + Ghostscript |
|--------------------|--------|-------------------|
| タイプセット       | 高速   | やや遅い          |
| 日本語 | 不可 | 可 |
| 画像形式 | pdf、jpg、png、mps (※) | eps、ps |

※ mps ・・・ MetaPost 出力の eps 形式

TeXShop のインストールそのものは、難しいことではありません──「TeXShop の入手とインストール」に詳しいことが書かれていますが、要するにアプリケーション本体を、通常はアプリケーション・フォルダにコピーするだけです。 TeXShop と pTeX のインストールは、どちらが先でもかまいません。

これらのパッケージを使って pTeX をインストールした場合、次の「teTeX の入手とインストール」は読み飛ばしてかまいません── TeX はもう既にインストールされていますから。

##Getting and Installing teTeX（ teTeX の入手とインストール）

［☆］Gerben Wierda has compiled the latest teTeX for MacOSX. His version also includes updated programs from the TeX User's Group's distribution TeXLive. To obtain these files and programs, go to Wierda's site

【★】Gerben Wierda は最新の teTeX を MacOSX に移植しています。彼のバージョンには、 TeXLive（ TeX Users Group によるディストリビューション）が提供するアップデートされたプログラムも含まれています。これらのファイルやプログラムを手に入れるには、 Wierda のサイトへ行きます──

* http://www.rna.nl/tex.html

［☆］and obtain i-Installer, the TeX installer. You'll find it in the downloadable package II2.dmg. Run the installer and install the following packages in the following order:

【★】そのうえで i-Installer （TeX のインストーラ）を取得してください。II2.dmgというダウンロード可能なパッケージに収められています。インストーラを実行し、以下のパッケージを順序通りインストールします：

* FreeType 2
* libiconv (on System 10.2; skip this on System 10.3 or higher)
* libwmf
* Ghostscript 8
* ImageMagick
* FontForge
* TeX

［☆］More detailed installation instructions can be found on Wierda's site, and on the TeXShop web site listed later.

【★】さらに詳しいインストールについての解説は Wierda のサイトにありますが、 TeXShop のウェブサイトにも掲載しました。

##Getting and Installing TeXShop （ TeXShop の入手とインストール）

［☆］Log onto the web site

【★】ウェブサイトへログオンします──

* http://www.uoregon.edu/~koch/texshop/texshop.html

［☆］and click the TeXShop link to download the file TeXShop.dmg. Double click on this file; a folder will appear containing TeXShop and other files which can be read or discarded. Drag TeXShop to the Applications folder. If you intend to use it often, drag its icon to the Dock.

【★】そして TeXShop のリンクをクリックして TeXShop.dmg というファイルをダウンロードしてください。このファイルをダブルクリックします ； フォルダが１つ現われますが、この中に TeXShop とその他の読んだり処分したりできるファイルが入っています。 TeXShop をアプリケーション・フォルダにドラッグしてください。もし頻繁に使うようであれば、アイコンをドックにドラッグしておきます。

［☆］TeXShop has a feature called pdfsync: clicking on a spot in the preview window activates the corresponding source window with the appropriate source line selected. This feature requires that files named "pdfsync.sty", "pdfsync.tex", and "pdfsync4context.tex" be installed in teTeX. these files in the TeXShop distribution and drag them to ~/Library/texmf/tex/latex, ~/Library/texmf/tex/plain, and ~/Library/texmf/tex/context. Here ~/Library is the Library folder in your home directory. You may have to create some or all of the folders texmf, tex, latex, and plain.

【★】TeXShop には pdfsync という機能があります：プレビューウィンドウ上の一点をクリックすると、その箇所に応じてソースウィンドウをアクティブにするとともにソースコードの相当する行を選択します。この機能を使うには 「pdfsync.sty」 「pdfsync.tex」 「pdfsync4context.tex」 といったファイルを teTeX にインストールしておく必要があります。 TeXShop のディストリビューション内にあるファイルを ~/Library/texmf/tex/latex ・ ~/Library/texmf/tex/plain および ~/Library/texmf/tex/context にそれぞれドラッグしてください。 ~/Library はホーム・ディレクトリのライブラリ・フォルダのことです。 texmf ・ tex ・ latex ・ plain ・ context といったフォルダを作らねばならないかもしれません。

	* 補足：この機能に関しては、 「command＋クリック」によりプレビューとソース間で相互に照応できますが、 pdflatex でタイプセットする必要があり、 「TeX＋ghostscript」では使えません。

［☆］TeXShop 1.35 comes with additional applescripts by Will Robertson and Claus Gerhardt. If you upgrade from a previous version, you will not automatically see those new scripts.

【★】TeXShop 1.35には Will Robertson と Claus Gerhardt による追加の AppleScript が付属しています。以前のバージョンからアップグレードした場合、これらの新しいスクリプトは自動では現われません。

［☆］If you never edited the default macro set, you can obtain the new macros by going to the folder ~/Library/TeXShop and removing the entire Macros folder inside. The next time TeXShop starts, it will recreate this folder with the latest macros. It is not enough to remove the contents of the Macros folder; the entire folder must be removed.

【★】デフォルトのマクロ・セットを少しもいじっていないのであれば、 ~/Library/TeXShop 内の Macros フォルダを丸ごと取り除くことで、新しいマクロを導入できます。 TeXShop を立ち上げると、最新のマクロといっしょにこのフォルダを作り直します。 Macros フォルダの内容物を取り除くだけでは不十分です ； フォルダ自体を取り除かねばなりません。

［☆］If you have edited the default macros and want to add the new macro set, remove the Macros folder temporarily and let TeXShop create a new macro set. Then add your old macros using the Macro Editor.

【★】もしデフォルトのマクロを編集しており、そのうえで新しいマクロセットを追加したいのであれば、いったん Macros フォルダを取り除き、 TeXShop に新しいマクロ・セットを作成させます。その後で古いマクロをマクロエディタを使って追加してください。

［☆］TeXShop 1.35 comes with new templates by Will Robertson. These templates will not automatically be installed. You can obtain them by going to the folder ~/Library/TeXShop and moving the entire Templates folder inside to the Desktop. The next time TeXShop starts, it will recreate this folder with the latest Templates. You can then move old Templates you have edited from the folder on the desktop to the newly created folder ~/Library/TeXShop/Templates.

【★】TeXShop 1.35には Will Robertson による新しいテンプレート集が付属しています。このテンプレートは自動ではインストールされません。 ~/Library/TeXShop 内のテンプレート・フォルダを丸ごとデスクトップに移動させることで手に入れます。次回 TeXShop を起動した際に、最新のテンプレートを含んだテンプレート・フォルダが作り直されます。その後、自分で編集した古いテンプレートを、デスクトップに置いたフォルダから新しく作られたフォルダ ~/Library/TeXShop/Templates へ移します。

##Typesetting Documents（ドキュメントをタイプセットする）

［☆］To use TeXShop, type your LaTeX input in the editing window it provides. Then push the "Typeset" button at the top of the window. The input will be saved and pdflatex will run. A second window will open displaying messages from tex. If there are errors, pdflatex will halt; type "return" to skip the errors one by one, or one of the standard TeX inputs to quit, run continuously, etc. After the document has been typeset, a new window will appear showing the resulting pdf file. You can switch between the two windows by typing command-1.

【★】TeXShop を使うには、備え付けの編集ウィンドウに LaTeX のソースコードを打ち込みます。そしてウィンドウ上部にある「タイプセット」ボタンを押します。入力したものが保存され、 pdflatex が実行されます。もうひとつウィンドウが開き、 TeX からのメッセージを表示します。もしエラーがあれば pdflatex は止まります ； エラーをひとつずつスキップするには「リターン」をタイプしますが、終了させたり、実行を継続させたり、などといったことをするには、標準的な TeX インプットを打ち込みます。文書がタイプセットされると、出力結果の pdf ファイルを表示する新しいウィンドウが開きます。２つのウィンドウは command + 1 で切り替えることができます。

［☆］Press the mouse on a section of the pdf output display to magnify the region near the cursor. Double click to magnify a larger region; triple click to magnify a still larger region. Notice that the default region size can be selected using an element of the toolbar at the top of the page.

【★】pdf の出力結果の画面でマウスをプレスするとカーソルの付近一帯が拡大されます。ダブルクリックするとより広い範囲が拡大されます ； トリプルクリックではさらに広い範囲が拡大されます。ページ上部のツールバーのボタンでデフォルトの（プレスしたときの）拡大範囲サイズを選択することができます。

［☆］To typeset a TeX document, push the button labeled LaTeX and select TeX instead of LaTeX. If you usually use TeX, choose it as your default program in the Preferences Dialog.

【★】TeX 文書のタイプセットを行なうには、 LaTeX と表示されているボタンを押して LaTeX の代わりに TeX を選択します。もし普段から TeX を用いるのであれば、環境設定ダイアログでデフォルトのプログラムを TeX にしてください。

［☆］If you notice an error, you can immediately fix it in the editing window and push the "Typeset" button again without halting the first invocation of pdflatex. The program will kill that invocation and run another.

【★】エラーに気付いた場合、すぐに編集ウィンドウでエラーを修正し、再度「タイプセット」ボタンを押すことができます──動いている pdflatex を止める必要はありません。プログラムは初めのものを中断して次を実行し始めます。

［☆］TeXShop remembers the source lines of the first twenty errors. To cycle through these lines in the source file, choose "Go To Error" in the Edit menu or type the keyboard shortcut for this menu item.

【★】TeXShop は初めの20個のエラーのソース行をおぼえています。ソースファイルでこれらの行を繰り返し表示させるには、編集メニューから「エラー箇所へ移動」を選択するか、このメニューアイテムのショートカット・キーをタイプします。

［☆］When you fix errors and typeset again, the viewer will remember the page you were previously viewing.

【★】エラーを直して再度タイプセットを行なった場合も、ビューワはそれまで見ていたページをおぼえています。

［☆］If a line in the source begins with the characters "%:", TeXShop interprets the remaining word or words on the line as a "tag" and adds these words to the Tag pulldown menu. Choosing a tag entry in this menu will scroll to the appropriate line in the source file. Lines which begin with the words \section, \subsection, \subsubsection, or \chapter are automatically added to the Tag menu. However, this behavior can be changed by typing the following command in Apple's Terminal program:

【★】もしソース行が「 %: 」という文字列で始まっていると、 TeXShop はその行にある単語あるいは文を「タグ」として解釈し、プルダウンメニュー「タグ」に追加します。プルダウンメニューでタグ項目を選択すれば、ソースファイル内の該当する行へとスクロールします。また \section ・ \subsection ・ \subsubsection あるいは \chapter で始まる行も自動でタグメニューに追加されます。が、この動作は、 Apple の Terminal プログラムで次のコマンドをタイプして変更することができます：

	defaults write TeXShop TagSections NO

［☆］TeXShop can show multiple documents. If you choose "New" or "Open," your original document will remain and additional windows for the new document will open. If you open a TeX file in a folder which contains a pdf file with the same name, this pdf will also appear.

【★】TeXShop は複数の文書を表示させることができます。 「新規」ないしは「開く...」を選択すると、もともとの文書はそのままにして、新しい文書用に追加のウィンドウが開きます。フォルダ内に同じ名前の pdf ファイルがある TeX ファイルを開けば、 pdf も表示されます。

［☆］Some users like to divide their source into multiple files controlled by a master file using an \input command. TeXShop always saves the source file before typesetting. If the preference item "During File Save, Save Related Files" is checked, the master file will be searched before typesetting and any input file open in TeXShop will also be saved. This feature is due to John Nairn.

【★】ソースを複数のファイルに分割し、\input コマンドを使ってマスターファイルで管理するのを好むユーザもいます。 TeXShop は常にタイプセット前にはソースファイルを保存します。環境設定で「ファイル保存時に関連ファイルも保存する」の項目がチェックされていれば、タイプセット前にマスターファイルを探し、 TeXShop で開くどの入力ファイルについても同じように保存されます。この機能は John Nairn のおかげです。

［☆］You can start TeXShop by double clicking on a document with extension ".tex". The program will open that input document and (if it exists) the associated pdf document.

【★】拡張子が「.tex」の文書をダブルクリックすることで TeXShop を立ち上げることができます。プログラムはその入力文書と（もしそれが存在すれば）関連する pdf 文書とを開きます。

［☆］You can close the pdf window at any time. It will reappear when the document is typeset again. If you close the input window then both the input and output windows will close (windows from other TeX documents will remain open). Therefore, if an input source window is cluttering the screen, hide it instead of closing it.

【★】pdf ウインドウはいつでも閉じることができます。文書を再度タイプセットすれば改めて表示されます。入力ウィンドウを閉じた場合には、入力・出力の両方のウィンドウが閉じられます（他の TeX 文書のウィンドウは開いたままです）。なので、もしソース入力のウィンドウが画面上に散乱しているのであれば、閉じずに隠しておきます。

［☆］pdftex and pdflatex are unix programs derived from Knuth's TeX program. The syntax of TeX does not allow spaces in filenames, so source files created with TeXShop should be given names without spaces. TeXShop itself has no problem with spaces in filenames.

【★】pdftex と pdflatex は Knuth の TeX プログラムから派生した UNIX プログラムです。 TeX の構文はファイル名でのスペースを容認しません──なのでTeXShop で作成するソースファイルもスペースなしで命名します。 TeXShop 自体はファイル名にスペースがあっても問題はありません。

［☆］The preview window's behavior can be changed using the "Magnification" and "Display Format" items in the Preview menu. For example, you can configure the scroller to scroll through all of the document pages; the preview window can show two pages at a time; resizing the window can be made to change the preview magnification. Experiment until you find the mode you prefer, and then select this mode in preferences to make it permanent.

【★】プレビューウィンドウの挙動は「プレビュー」メニューの「ズーム倍率」と「ページレイアウト」項目で変更できます。たとえば、スクロール方法を調整して、文章のすべてのページをスクロールさせるようにできます ； プレビューウィンドウは見開き２ページを同時に表示できます ； ウィンドウをリサイズすることで拡大表示の倍率を変更させられます。気に入る表示方式が見つかるまで試してみてから、その方式を環境設定で選択し固定させてください。

##Alternate Typesetting Mode（もうひとつのタイプセット方式）

［☆］There is another way to typeset with TeXShop; in this alternate mode, eps illustrations can be input directly without conversion. To use the alternate method, choose "TeX and Ghostscript" in the Typeset menu. Then TeXShop will typeset by calling tex or latex to produce a ".dvi" file, calling dvips to convert it to a postscript file, and calling ps2pdf to convert the postscript file to pdf. The method chosen in the typeset menu will only affect the topmost file; other documents will continue to be typeset with pdftex or pdflatex. The primary method used when a document is first opened can be selected in the preference dialog.

【★】TeXShop でタイプセットを行なう方法が他にもあります ； この方法では eps 形式のイラストを変換なしでじかに入力できます。このもうひとつの方式を使うには、タイプセット・メニューから「TeX+Ghostscript」を選びます。すると TeXShop は TeX ないしは LaTeX を呼び出してタイプセットを行ない「dvi」ファイルを生成し、 dvips を呼び出してポストスクリプト・ファイルに変換し、そのうえで ps2pdf を呼び出してポストスクリプト・ファイルを pdf に変換します。タイプセット・メニューで選択した方式は、最前面のファイルにのみ作用します ； その他の書類はひきつづき pdftex もしくは pdflatex でタイプセットされます。書類を開いた時点で最初に用いられる方式は環境設定ダイアログで選択できます。

［☆］The "TeX and Ghostscript" method should be used for old projects with many eps illustrations, and for TeX files with postscript special commands, and for TeX files that include bitmapped fonts which do not display correctly when typeset with pdflatex. Experimentation will show which is the preferable typesetting engine.

【★】「TeX＋Ghostscript」方式は、多数の eps 形式のイラストがある昔のプロジェクト、あるいはポストスクリプト・スペシャル・コマンドを使った TeX ファイル、ないしは pdflatex でタイプセットすると正しく表示されないビットマップ・フォントを含む TeX ファイルに対して用いられるべきです。実験してみればいずれのタイプセット・エンジンが望ましいかわかることでしょう。

［☆］There is a way to permanently set the typesetting method of a document regardless of preference choices. If the first line of a document is %&tex or %&program=tex, with no initial spaces on the line, then tex + ghostscript will be used. If the first line is %&latex or %&program=latex, then latex + ghostscript will be used. If the first line is %&pdftex or %&program=pdftex, or %&pdflatex or %&program=pdflatex, then pdftex or pdflatex will be used. If the first line is %&personaltex or %&program=personaltex, or %&personallatex or %&program=personallatex, then the personal script will be used as set in the preference dialog.

【★】環境設定における選択の如何によらず、ある文書のタイプセット方式を常に固定する方法があります。文書の第１行目が %&tex ないしは **%&program=tex** となっていれば──行頭にスペースは入れません── TeX＋Ghostscript が使われます。第１行目が %&latex ないしは **%&program=latex** になっていれば LaTeX＋Ghostscript となります。第１行目が %&pdftex か **%&program=pdftex** もしくは %&pdflatex か **%&program=pdflatex** となっていれば、 pdftex もしくは pdflatex が使われます。そしてもし最初の１行が %&personaltex ないしは **%&program=personaltex** または %&personallatex ないしは **%&program=personallatex** となっていた場合には、環境設定ダイアログでの設定にしたがってパーソナルスクリプトが用いられます。

##Checking Spelling（スペルをチェックする）

［☆］Cocoa programs automatically inherit spell checking technology by Apple, but the Apple spell checker does not understand LaTeX. However, other spelling services can be added to the Apple technology; they then become available in all Cocoa programs.

【★】Cocoa プログラムには Apple の提供するスペルチェック技術が自動的に具わりますが、 Apple のスペルチェッカーは LaTeX を理解しません。しかしながら、他のスペルサービスを Apple の技術に付け加えることができます ； そうするとすべての Cocoa プログラムで利用できるようになります。

［☆］TeXShop supports continuous spell checking, which can be toggled on or off with a menu command. A preference item selects the initial position of this toggle.

【★】TeXShop は自動スペルチェックをサポートします──メニューコマンドで入・切ができます。環境設定で入・切の初期状態を選定します。

［☆］Aspell is "a more intelligent Ispell" for Unix machines written by Kevin Adkinson. His program has been ported to Mac OS X and made into a spelling service by Anton Leuski. The new speller supports LaTeX. To obtain it, go to

【★】Aspell は Unix マシン用に Kevin Adkinson が作成した「より賢い Ispell」です。それが Anton Leuski によって Mac OS X に移植され、スペルサービス化されました。この新しいスペルチェッカーは LaTeX をサポートしています。これを入手するには以下のサイトを訪れます──

* http://cocoaspell.leuski.net/

［☆］An alternate LaTeX spell checker named Excalibur is often used. This spell checker was written by Rick Zaccone; it can open TeXShop files. To obtain it, go to

【★】もうひとつ、 Excalibur という LaTeX スペルチェッカーがよく使われています。このスペルチェッカーは Rick Zaccone により作成されました ； これは TeXShop ファイルを開くことができます。入手するには、以下のサイトを訪れます──

* http://www.eg.bucknell.edu/~excalibr/excalibur.html

##Latex Panel（ LaTeX パネル）

［☆］Under the Windows menu, there is an item named "Latex Panel..." Choosing this item will open a panel containing a large number of mathematical symbols, Greek letters, international characters, and typesetting environments. Clicking on a symbol will insert the corresponding text into your LaTeX source file. This wonderful panel is the work of Geoffroy Lenglin, who can be reached at geoffroy.lenglin@m4x.org.

【★】「ウィンドウ」メニュー下には「LaTeX パネル...」という項目があります。この項目を選択すると数多くの数学記号、ギリシア文字、国際文字、それにタイプセット環境などを含むパネルが開きます。シンボルをクリックすると、それに応じたテキストが LaTeX のソースファイルに挿入されます。この素晴らしいパネルは Geoffroy Lenglin（ geoffroy.lenglin@m4x.org ）の功績です。

［☆］Some symbols in the panel require the line

【★】LaTeX パネルにあるシンボルの中には、ソースファイルの冒頭に、次の１行が必要となるものもあります。

	\usepackage{amssymb}

［☆］at the top of the source file.

【★】──

［☆］It is possible to customize the behavior of the panel. When TeXShop first runs, it creates a file ~/Library/TeXShop/LatexPanel/completion.plist inside your personal Library folder. This file is an ordinary text file which can be opened and edited by TeXShop. The file contains all strings inserted into the source code when a Palette item is chosen. If such a string contains #SEL#, then the current selection will replace this expression in the inserted string. If a string contains #INS#, then the cursor will be set to this position when the string is inserted. To customize panel behavior, edit completion.plist.

【★】パネルの動作はカスタマイズすることができます。初めて起動するときに TeXShop は、 ~/Library/TeXShop/LatexPanel/completion.plist というファイルをユーザ個人のライブラリ・フォルダ内に作成します。このファイルはごく普通のテキストファイルなので TeXShop で開いたり編集したりできます。ファイルには、パレットの項目が選択された際にソースコードに挿入される文字列がすべて書かれています。文字列に #SEL# が含まれているときは、これを現在の選択部分と差し替えた文字列が挿入されます。文字列が #INS# を含んでいれば、文字列が挿入された後カーソルがこの位置に来ます。パネルの動作を変更するには、 completion.plist を編集してください。

［☆］Editing plist files is slightly tricky; see the item about them at the end of this help file. Be sure to edit and save in UTF-8 format if you use Unicode characters.

【★】plist ファイルを編集するのはいくぶん裏技的なことです ； そのことについてはこのヘルプファイルの終わりにある事項を参照してください。ユニコード文字を使用するのであれば、かならず UTF-8 形式で編集し保存するようにします。

［☆］Users can add up to sixteen additional items to the Latex Panel by editing completion.plist. These are displayed on the "Custom" subpanel of the Latex Panel. See comments in completion.plist for details about adding such items.

【★】ユーザは completion.plist を編集することで最大16個までの項目を LaTeX パネルに付け加えることができます。これらは LaTeX パネルの「カスタム」というサブパネルに表示されます。項目追加に関しての詳細は completion.plist 内のコメントを参照してください。

##Matrix Panel（行列パネル）

［☆］The Windows menu contains an item "Matrix Panel...". Choosing this item will open a panel allowing easy creation of matrices. Only a small space is provided for each matrix entry, but larger items can be edited elsewhere and pasted into the matrix. This wonderful panel is the work of Jonas Zimmermann, who can be reached at zimmerleut@gmx.de.

【★】「ウィンドウ」メニューに「行列パネル」という項目があります。これを選択すると、行列を簡単に作成できるパネルが開きます。行列の各入力部分は小さなものですが、長いものでもどこか別の場所で編集してからペーストすることができます。この素晴らしいパネルは Jonas Zimmermann （ zimmerleut@gmx.de ）の業績です。

［☆］In TeXShop 1.35, the Matrix Panel can also create tables. This panel can be configured using the file "matrixpanel_1.plist" in ~/Library/TeXShop/MatrixPanel. The structure of this file was revised in 1.35; an old "matrixpanel.plist" file may remain from TeXShop 1.34.

【★】TeXShop 1.35 では、行列パネルで表（テーブル）を作成することもできます。このパネルは ~/Library/TeXShop/MatrixPanel にある「matrixpanel_1.plist」というファイルを使って設定できます。このファイルの構成は 1.35 で見直されました ； 古い「matrixpanel.plist」ファイルは TeXShop 1.34 からのまま残っていても差し支えありません。

［☆］There is a hidden preference item to set the default size of matrices created by the panel. To change the default

【★】パネルで作成するデフォルトの行列のサイズを設定する隠れた環境設定があります。デフォルトを変えるには──

 defaults write TeXShop matrixsize 12


##Macros（マクロ）

［☆］There is an alternate mechanism to insert commonly used TeX commands in your source document. Find the command in the Macro menu or the Macro button on the toolbar and choose it. In addition, some macros run AppleScript commands. A Macro Editor is provided which allows you to examine current macros, modify them, and add your own macros. For details, see the "About Macros" document in the Help menu. The TeXShop Macro commands and the Macro Editor were created by Mitsuhiro Shishikura. Default macros were created by Mitsuhiro Shishikura and Hirokazu Ogawa.

【★】よく使う TeX コマンドをソース・ドキュメントに挿入する仕組みが他にもあります。マクロ・メニューまたはツールバーのマクロ・ボタンから見つけてコマンドを選び取ってください。なお、 AppleScript コマンドを実行するマクロもあります。マクロエディタを備え付けてありますから、現行のマクロを調べたり、修正したり、独自のマクロを追加することが可能です。詳細については、ヘルプメニューにある「マクロ・ヘルプ」を参照してください。 TeXShop のマクロ・コマンドとマクロエディタは宍倉光広さんによって作成されました。デフォルト・マクロは宍倉光広さんと小川弘和さんによって作成されたものです。

 * 補足：「 About Macros 」は後出の「 Macros Help 」のことだと思われます。
 * これはヘルプがHTML化される前の名残りですね。次の機会に報告しておきます。

［☆］Macros are stored in the file ~/Library/TeXShop/Macros/Macros.plist. This is an ordinary text file which can be copied and sent to others; thus you can distribute macros you have created. The Macro Editor has a command to read a plist file and add macros in it to existing macros.

【★】マクロは ~/Library/TeXShop/Macros/Macros.plist というファイルに格納されています。これはごく普通のテキストファイルですから、コピーしたり他の人に送ったりできます ； したがって、ユーザの作成したマクロを配布することが可能です。マクロエディタには plist ファイルを読み込んでマクロを追加するためのコマンドがあります。

##Toolbar and AppleScript（ツールバーと AppleScript ）

［☆］The selection and location of tools at the top of the TeX Source and PDF Preview windows can be modified using the menu item "Customize Toolbar." This toolbar support is entirely the work of Anton Leuski. Thanks!

【★】TeX ソースウィンドウや PDF プレビューウィンドウの上部にあるツールの選定や配置は「ツールバーをカスタマイズ...」というメニュー項目で変更できます。このツールバーのサポートは完全に Anton Leuski のおかげです。ありがとう！

［☆］TeXShop supports Applescript. This is also the work of Anton Leuski.

【★】TeXShop は AppleScript をサポートしています。これも同じく Anton Leuski のおかげです。

##Including Graphics（画像を入れる）

「TeX＋Ghostscript」モードで jpg ・ png および pdf 形式の画像を挿入するには、 dvipdfmx を使用します。プリアンブルに次の１行を追加しておいてください。

	\usepackage[dvipdfm]{graphicx}

dvipdfmx を使用する際も、パッケージのオプション部分は [dvipdfm] としておくことに注意します。

そのうえで画像を入れたい箇所に、たとえば次のように書きます。この例では filename.jpg というのが画像ファイルです（ png ・ pdf ファイルについても同様です）。

	\includegraphics[width=3cm, bb=0 0 640 480]{filename.jpg}

width により紙面上の画像の横幅を３cmと指定してありますが、指定しない場合は不要です。 640と480は画像ファイルの横と縦のピクセル数です。文字列「bb=0 0 640 480」は .bbファイル（ BoundingBoxファイル）から得られる情報です。 filename.jpg に対する .bbファイルを取得するには、 Terminal を起動し、画像ファイルのあるディレクトリに移動後、以下のコマンドを打ち込みます。

	ebb filename.jpg

これで filename.bb が生成されます（ ebb: Command not found.となる場合は/usr/local/bin/ebb filename.jpg としてみてください）。.bbファイルは短いテキストファイルです。たとえばこのような──

	%%Title: ./filename.jpg
	%%Creator: ebb Version 0.5.2 (+ArtBox)
	%%BoundingBox: 0 0 640 480
	%%CreationDate: Fri Jul 16 11:11:11 2004

BoundingBox の情報をここからコピーして使用することができます。この場合、 filename.bb は不要になります。あるいは .bbファイルを保持したまま、コードを縮めることもできます。こんなふうに──

	\includegraphics[width=3cm]{filename}

紙面上の横幅を指定するオプションも不要なら、さらに簡潔にできるでしょう。

	\includegraphics{filename}

画像の寸法については、[scale=0.8] というような指定も可能です。

----

［☆］The programs pdftex and pdflatex can use graphic files produced in pdf, jpg, png, or mps format. If you are using the default latex template and installed the graphic conversion packages from Gerben Wierda's distribution, you can also use graphic files produced in eps or tif format; they will automatically be converted to pdf or png formats during typesetting. One peculiarity is that tiff files must have extension ".tif" rather than ".tiff". The native graphics format of Mac OS X is pdf (portable document format) and such files print well at any size. It is likely that most future Mac graphics programs will output pdf.

【★】プログラム pdftex と pdflatex では、 pdf ・ jpg ・ png ないしは mps 形式の画像ファイルを使用できます。デフォルトの LaTeX テンプレートを使っており、 Gerben Wierda のディストリビューションから画像変換パッケージをインストールしているのであれば、 eps あるいは tif 形式の画像ファイルも同じように使用できます ； タイプセット時にこれらは自動的に pdf または png 形式に変換されます。ひとつ変わっている点は、 tiff ファイルは拡張子が「.tiff」ではなく「.tif」でなくてはならないことです。 Mac OS X のネイティブなグラフィック・フォーマットは pdf （ portable document format ）なので、この形式のファイルならどんなサイズでも印刷がうまくゆきます。おそらくこの先、 Mac のグラフィックス・プログラムのほとんどが pdf を出力するようになりそうです。

［☆］If you used TeX in the past, your illustrations may be in eps format. These files must be converted to pdf format before being typeset with pdftex and pdflatex. As explained above, this will happen automatically if you use the default latex template. You can also convert an eps illustration by opening it in TeXShop. The illustration will appear in a graphic window and TeXShop will simultaneously write the corresponding pdf file to disk. Ghostscript also contains a command line program to convert; indeed TeXShop calls this program. To convert myfile.eps to myfile.pdf within Terminal, type

【★】過去に TeX を使ったことがある場合、イラストが eps 形式になっているかもしれません。この形式のファイルは、 pdftex や pdflatex でタイプセットする前に、 pdf 形式に変換されねばなりません。上で説明したように、デフォルトの LaTeX テンプレートを使っていれば、これは自動で行なわれます。 TeXShop で開くことによってもまた、 eps 形式のイラストを変換することができます。イラストがグラフィック・ウィンドウに表示されるのと同時に、当該する pdf ファイルを TeXShop がディスクに書き込みます。 Ghostscript にも変換用のコマンドライン・プログラムがあります ； 実際に TeXShop でもこのプログラムを呼び出します。 myfile.eps を myfile.pdf に変換するには、 Terminal で次のように打ち込みます──

	epstopdf myfile.eps

［☆］The authors of pdflatex and the authors of the graphics package graphicx have made it easy to include graphic files in a LaTeX document typeset with pdflatex, even if the document will later be typeset by standard latex and converted to a dvi file for distribution to other people. At the top of such a LaTeX input file, include the line:

【★】pdflatex の作者とグラフィックス・パッケージ graphicx の作者は、 pdflatex でタイプセットする LaTeX 文書の中に画像ファイルを含めるのを容易にしました──たとえその書類が後に、標準的な LaTeX でタイプセットされ、他の人たちに配布するための dvi ファイルに書き出されるとしても、です。こうした LaTeX 入力ファイルの冒頭には、次の１行を含めておきます──

	\usepackage{graphicx}

［☆］When you wish to include a graphic file, say "f1.pdf ", use the command

【★】たとえば「f1.pdf」という画像ファイルを含めたいときは、次のようなコマンドを用います──

	\includegraphics[width=2in]{f1}

［☆］This command will cause tex to input the graphic file "f1.pdf" when the text is typeset with pdflatex, but input the file "f1.eps" when the text is typeset with latex.

【★】このコマンドは TeX に対し、 pdflatex でテキストをタイプセットするときには画像ファイル「f1.pdf」を入力させますが、 LaTeX でタイプセットする際には画像ファイル「f1.eps」を入力させます。

［☆］If you upgraded from a previous version of TeXShop and want to use automatic conversion of eps and tif files during typesetting, make certain that

【★】もし以前のバージョンの TeXShop からアップグレードしており、タイプセット時に eps および tif ファイルの自動変換をお望みなら、次の点を確認してください──

* ［☆］a.  You have installed Ghostscript 8, Freetype 2, wmf and iconv conversion support, and ImageMagick with Gerben Wierda's installer
* 【★】a.  Gerben Wierda のインストーラで Ghostscript 8 ・ Freetype 2 ・ wmf ・ iconv conversion support それから ImageMagick をインストールしてある。

* ［☆］b.  The pdflatex program preference is "pdflatex --shell-escape"
* 【★】b.  pdflatex プログラムの設定が「pdflatex --shell-escape」になっている。

* ［☆］c.  The Latex header contains the following lines
* 【★】c.  LaTeX ヘッダに以下の行が含まれている──

	\usepackage{graphicx}
	\usepackage{epstopdf}
	\DeclareGraphicsRule{.tif}{png}{.png}{`convert #1 `basename #1 .tif`.png}

##Printing（印刷）

［☆］To print a TeX output file, select the "Print" menu item. To print TeX source, select the "Print Source" menu item.

【★】TeX による出力結果を印刷するには、メニュー項目の「プリント...」を選びます。 TeX ソースを印刷するには「ソースをプリント...」を選択してください。

##Setting Preferences（環境設定）

［☆］Several items can be changed using the Preference menu: the default font for the input window, the default magnification for the output window, and the default position of these windows when they first appear. You can configure the console so it always appears when typesetting, or only appears when there is an error.

【★】いくつかの項目は「環境設定...」メニューを使って変更できます：ソースウィンドウのデフォルト・フォント、プレビューウィンドウの倍率、それにこの２つのウィンドウが最初に表示されるデフォルトの位置などです。コンソールも配置できます──タイプセット時に常に表示するか、もしくはエラーがあったときにだけ表示するか。

［☆］The preference dialog can also be used to change the commands executed when the "TeX" and "LaTeX" buttons are pushed. This is useful because some users prefer a version of TeX called etex, and there are pdf versions of etex called pdfetex and pdfelatex. Obviously the substituted command must produce a pdf output file. If the new programs are in the teTeX binary directory, it is enough to name them in the preference dialog; the dialog will also accept fully qualified path names for files which live elsewhere.

【★】環境設定ダイアログでは「TeX」と「LaTeX」ボタンが押されたときに実行するコマンドを変更することもできます。これが役に立つのは、 eTeX と呼ばれるバージョンの TeX を好むユーザもいるからですが、 eTeX には、 pdfetex と pdfelatex という pdf 版もあります。この代替コマンドは言うまでもなく pdf 出力ファイルを生成します。新しいプログラムが teTeX バイナリのディレクトリにあるのであれば、環境設定ダイアログで名前を書き込んでやるだけで十分です ； ダイアログではその他のところにあるファイルのフルパス名にも対応します。

［☆］TeXShop editing is done with Apple's Cocoa editing class, which uses Unicode for internal work. When TeXShop files are written to disk, they are usually converted to 8-bit ascii because TeX expects to receive such a file. There are several ways to do the conversion: Mac OS Roman, Iso Latin 1, Iso Latin 2, and others. A preference item selects the method used. For many users, the choice will make no difference. Some TeX packages allow users to type accented European characters directly on the keyboard; these packages require the Iso Latin conversion. Thanks to Martin Heusse for providing the original code for this preference. The conversion method can also be selected directly from the Open and Save panels.

【★】TeXShop でのテキスト編集には Apple の Cocoa の編集クラスが用いられており、内部処理は Unicode で行なわれています。 TeXShop 書類がディスクに書き込まれるときには、通常８ビットの ASCII コードにエンコーディングされます──というのも TeX のほうでそうしたファイルを受け取ることを想定しているからです。エンコーディングには方式がいくつかあります ； Mac OS Roman ・ Iso Latin 1 ・ Iso Latin 2 ・ その他です。環境設定項目で使用するエンコーディング方式を選択します。多くのユーザにとっては、どれを選択しても違いはないでしょう。アクセント記号のついたヨーロッパ文字をキーボードからじかに入力できる TeX パッケージもあります ； こうしたパッケージには Iso Latin エンコーディングが必要となります。この環境設定のオリジナルコードは Martin Heusse に提供していただきました。エンコーディング方式は「開く...」と「保存」のパネルで直接選択することもできます。

［☆］Users in Japan and Korea will use other conversion preferences, also provided.

【★】日本や韓国のユーザは他のエンコード方式を使うでしょうが、それらも入っています。

［☆］It is possible to reset the background color of the source window. The preference dialog does not have an interface to make this change. To set the background to (r, g, b) = (.42, .39, .77), issue the following commands in Terminal:

【★】ソースウィンドウの背景色は変えることができます。環境設定ダイアログにはこの変更を行なうためのインターフェイスはありません。背景色を (r, g, b) = (.42, .39, .77) にするには、次のコマンドを Terminal から送ります：

	defaults write TeXShop background_R 0.42
	defaults write TeXShop background_G 0.39
	defaults write TeXShop background_B 0.77

［☆］It is also possible to set the text color in the source window. This preference will only be recognized if syntax coloring is on. To set the forground color to (r, g, b) = (.42, .39, .77), issue the following commands in Terminal:

【★】またソースウィンドウの文字色を変えることもできます。この設定は「ソースのカラー表示」がオンになっているときにのみ有効です。前景色を (r, g, b) = (.42, .39, .77) にするには、次のコマンドを Terminal から送ります：

 defaults write TeXShop foreground_R 0.42
 defaults write TeXShop foreground_G 0.39
 defaults write TeXShop foreground_B 0.77

［☆］By using the previous sets of preferences simultaneously, it is possible to edit white text on a black background, or use other coloring schemes in the editor.

【★】上記の設定を組みにして同時に使うことで、黒地に白文字、あるいはその他の色の組み合わせといったことがエディタで可能になります。

［☆］There are hidden preferences to set the transparency of the source, preview, and console windows:

【★】ソース、プレビュー、コンソールの各ウィンドウの透明度を設定する隠れた環境設定もあります。

 defaults write TeXShop ConsoleWindowAlpha 0.75
 defaults write TeXShop SourceWindowAlpha 0.75
 defaults write TeXShop PreviewWindowAlpha 0.75

［☆］Here an alpha value of 0.00 is completely transparent and an alpha value of 1.00 is completely opaque. Use these commands cautiously!

【★】ここでアルファ値が 0.00 なら完全に透明となり、アルファ値が 1.00 なら完全に不透明となります。用心してお使いください！

［☆］A pulldown menu at the bottom of the Preferences Panel can be used to reset preferences to their default values. This is mainly useful in Japan, since different defaults are available for users of various pTeX distributions.

【★】環境設定パネルの左下にある「設定プロファイル」メニューを使うと、設定をデフォルト値にリセットすることができます。これは主に日本で有用です──というのも、各種の pTeX ディストリビューションのユーザ用に異なるデフォルトが利用可能だからです。

----

TeXShop バージョン 1.35 では、下のような設定プロファイルが搭載されており、日本語 pTeX ディストリビューションでそのまま使うことができます。

|設定箇所 | Shift JIS | EUC |
|---------|-----------|-----|
|書類 > エンコーディング| Japanese (Shift JIS ＼) | Japanese (EUC)  |
|プレビュー > 見開きページ| 左からスタート（両面） |== |
|内部設定 > パス設定 > (pdf)TeX| /usr/local/bin |== |
|内部設定 > distiller > TeX プログラム|~/Library/TeXShop/bin/ptex2pdf-sjis|~/Library/TeXShop/bin/ptex2pdf-euc |
|内部設定 > distiller > LaTeX プログラム|~/Library/TeXShop/bin/platex2pdf-sjis|~/Library/TeXShop/bin/platex2pdf-euc |
|詳細 > BibTeX| jbibtex |== |
|タイプセット > デフォルトのスクリプト | TeX + Ghostscript |== |

※：これらの設定は 1.34 までのものから変更されていますのでご注意ください。

##日本語エンコーディングと \ ¥ 文字の扱い

* 日本語版独自のヘルプ項目

----

TeXShop は下の５種類の日本語エンコーディングに対応しています。これらは環境設定パネルの「書類 > エンコーディング」で設定できます。

* Japanese (JIS)
* Japanese (EUC)
* Japanese (ShiftJIS \)
* Japanese (ShiftJIS ¥)
* Japanese (ShiftJIS X0213)

このうち「Japanese (ShiftJIS ¥)」と「Japanese (ShiftJIS X0213)」では TeX 記号が ¥ で表示されます。
一方、他のエンコーディングでは、TeX 記号が \ で表示されます。
（「Japanese (ShiftJIS \)」と「Japanese (ShiftJIS ¥)」は TeX 記号の表示が違うだけです）

TeX 記号の \ を入力するとき、手元に \ キーがなければ
代わりに ¥ キーを押して下さい。編集画面には \ が入力されるでしょう。
逆に、TeX 記号が ¥ と表示されていて、手元に ¥ キーがないときは（US キーボード）
\ キーを押して下さい。つまり、\・¥ のどちらのキーを押しても、
そのときの TeX 記号に TeXShop が自動変換してくれます。
また、他のアプリケーションからコピー＆ペーストした文字列に
\ や ¥ が含まれている場合も、適切な TeX 記号に変換されます。

また、TeXShop から他のアプリケーションにテキストをペーストする際に、
\ や ¥ を自動変換することもできます。
「編集」メニューの一番下に次のオプション項目があって、
クリップボード中の \ ¥ 文字を調整することができます。
お使いの環境にあわせて調整して下さい。

| エンコーディング                    |  メニュー項目名                 |  デフォルト  |
|-------------------------------------|---------------------------------|--------------|
|Japanese (ShiftJIS \ EUC JIS)        |  クリップボードで \ を ¥ に変換 |  ON  |
|Japanese (ShiftJIS ¥ ShiftJIS X0213) |  クリップボードで ¥ を \ に変換 |  OFF |

こうした \ ⇔ ¥ の自動変換機能は、宍倉光弘さんによって実装されました。
なお、これらの機能は TeXShop で
日本語エンコーディング（上記５つ）を設定している場合にのみ動作します。

----
[もくじ](README.md)
