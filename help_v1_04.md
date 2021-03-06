TeXShop の日本語ヘルプファイルのアーカイブ (v1-4) です。

作業当時の日英対訳テキストをアップしています。

----
Version 1.35e
----

#Macros Help（マクロ・ヘルプ）

##Preliminaries（まえがき）

［☆］TeXShop macros and the Macro Editor are by Mitsuhiro Shishikura. Default Latex macros were created by Mitsuhiro Shishikura and Hirokazu Ogawa. Default Context macros were created by Hans Hagen.

【★】TeXShop マクロとマクロエディタは宍倉光広さんによるものです。デフォルトの LaTeX マクロは宍倉光広さんと小川弘和さんが作成しました。デフォルトの ConTeXt マクロは Hans Hagen によって作成されました。

［☆］The available Macros depend on the typesetting engine chosen. If this engine is LaTeX, then a series of macros suitable for LaTeX will be displayed. If the engine is ConTeXT, then macros for ConTeXt will be displayed. When TeXShop is first installed, it has macros for only these two engines; the LaTeX macros will be displayed for all engines except ConTeXt.

【★】タイプセット・エンジンの選択によって、利用できるマクロは異なります。エンジンを LaTeX にした場合、 LaTeX に適した一連のマクロが表示されます。エンジンを ConTeXT にすれば、 ConTeXt 用のマクロが表示されます。 TeXShop をインストールした当初は、この２つのエンジン用のマクロだけが入っています ； LaTeX 用のマクロは、 ConTeXt を除くすべてのエンジンに対して表示されます。

［☆］Macros come in two kinds. Some insert strings into the TeX source file; these macros are similar to buttons in the Latex panel. Other macros run Applescript scripts.

【★】マクロには２種類あります。ひとつは TeX のソースファイルに文字列を挿入するものです ； こうしたマクロは LaTeX パネルのボタンと似ています。もうひとつのマクロは AppleScript のスクリプトを実行します。

［☆］Macros are stored in ~/Library/TeXShop/Macros/Macros_Latex.plist and ~/Library/TeXShop/Macros/Macros_Context.plist. If these files are missing when TeXShop runs, default macro files are created there. These files are ordinary text files, so it can be opened and inspected with TeXShop. This is usually not necessary because the files are best manipulated with the Macro editor.

【★】マクロは ~/Library/TeXShop/Macros/Macros_Latex.plist と ~/Library/TeXShop/Macros/Macros_Context.plist に格納されています。 TeXShop を起動した際にこれらのファイルがなければ、デフォルト・マクロのファイルが前述の場所に作られます。これらのファイルはごく普通のテキストファイルなので、 TeXShop で開いたり調べたりできます。これは通常は不必要なことです──というのも、マクロエディタで扱うのがいちばんですから。

［☆］The Macro editor modifies macros stored in Macros_Latex.plist and Macros_Context.plist when one of these typesetting engines is chosen. But if another typesetting engine like TeX is chosen, then the Macro editor will replace the default Latex macro set with a set defined by the user for TeX, storing the results in Macros_Tex.plist and leaving Macros_Latex.plist unchanged.

【★】Macros_Latex.plist と Macros_Context.plist に格納されているマクロは、それぞれのタイプセット・エンジンが選択されているときにマクロエディタで修正できます。しかしもし TeX のような他のタイプセット・エンジンが選ばれているときには、マクロエディタは、デフォルトの LaTeX マクロのセットをユーザが TeX 用に定義したセットに置き換えます──その結果は Macros_Tex.plist に保存されますが、もとの Macros_Latex.plist は変更されずに残ります。

［☆］When you define useful Macros and wish to give them to others, simply open the Macro Editor and choose "Save selection to file..." in the Macro menu. This will create a file in any location you wish. To distribute your macros, send this file.

【★】あなたが便利なマクロを定義し、それを他の人たちに渡したいと思ったときは、マクロエディタを開き、マクロ・メニューから「選択したマクロをファイルに保存...」を選べばよいだけのことです。保存先はいずれの場所でもかまいません。マクロを配布するには、このファイルを送ります。

［☆］To add macros created by others to your list of macros, open the Macro Editor and choose "Add macros from file...". Then use the Macro Editor to arrange the macros as you desire.

【★】他の人たちが作成したマクロをマクロリストに追加するには、マクロエディタを開いたうえで「ファイルからマクロを追加...」を選択します。その後マクロエディタを使ってマクロを好きなように配列します。

##Understanding Default Macros（デフォルトのマクロを理解する）

［☆］The best way to understand default macros is to examine their definition with the Macro Editor. For example, consider the macro titled "Begin/End." Suppose you wish to use an environment like the theorem environment. Type the word "theorem" and select it. Then choose the "Begin/End" macro. The word "theorem" will be replaced with the text

【★】デフォルトのマクロを理解するいちばんいい方法は、その定義をマクロエディタで調べてみることです。たとえば「Begin/End」と題されたマクロについて考えてみましょう。 theorem 環境のような環境を使いたいとします。 「theorem」という単語を打ち込み、これを選択してください。そして「Begin/End」マクロを選びます。 「theorem」という語が、次のようなテキストに置き換えられます──

	\begin{theorem}
	
	\end{theorem}

［☆］with the cursor placed on the line between this pair.

【★】カーソルは begin と end の間に配置されています。

［☆］Now examine the begin/end macro code:

【★】では「Begin/End」というマクロのコードを調べてみます：

	\begin{#SEL#}
	#INS#
	\end{#SEL#}

［☆］Text in the macro will be inserted into the source file. Each occurrence of the string #SEL# will be replaced by the text selected when the macro was invoked. If no text was selected, #SEL# will be replaced with an empty string. The cursor will be placed at the end of the inserted text unless the text contains the string #INS#, in which case the cursor will be placed at that location.

【★】マクロ内のテキストがソースファイルに挿入される。#SEL# という文字列はそれぞれに、マクロが実行されたときに選択されていたテキストで置き換えられる。もしテキストが何も選択されていなければ、#SEL# は空っぽの文字列で置き換えられる。カーソルは挿入したテキストの最後に置かれるが、#INS# という文字列が含まれている場合には、そこにカーソルが配置される。

［☆］Using this knowledge, it is easy to understand and modify the default macros.

【★】これがわかっていれば、デフォルトのマクロを理解したり修正したりするのは簡単なことです。

##Rearranging the Macro Menu（マクロの項目名を並べ替える）

［☆］Open the Macro Editor and examine the macro menu on the left. It is shown in an outline view similar to the view of the file system obtained by choosing the middle button of the View tab in the Finder. To rearrange items, drag them from one spot to another. Notice that items can be placed at different levels by sliding left and right. To rename an item, select it in the outline view and type a new name in the field at the top right.

【★】マクロエディタを開き、左側にあるマクロの項目名の一覧を見てください。ファインダで表示ボタンの真ん中を押したときのファイルシステムの表示方法に似たアウトライン表示になっています。項目を並べ替えるには、ある場所から別の場所へと項目をドラッグします。参考──項目を左ないしは右にスライドさせることで異なる階層に置けます。項目名を変更するには、アウトライン表示の中でその項目を選択し、右上にある項目名のフィールドに新しい名前を入れます。

##Defining New Macros（新しいマクロを定義する）

［☆］New items, new submenus, and new separators can be created by the buttoms at the bottom left. A little practice illustrates the basic behavior of the editor. Submenus can be created to any level.

【★】新規の項目（新規マクロ）、新規のサブメニュー（サブメニュー）、新規の区切り線（区切り）などは、左下のボタンで作成できます。少しいじってみれば、エディタの基本的な動作は明らかになるでしょう。サブメニューはどの階層にも作成できます。

［☆］Any particular item can be assigned a keyboard equivalent using the buttons on the right side of the menu. The result will immediately appear in the outline view. However, these assignments cannot duplicate key combinations already used by TeXShop menus. If they do, the new keyboard shortcut will be ignored.

【★】いずれの項目にも、一覧表の右下にあるボタン類を使って個別にキー操作を割り当てることができます。結果はすぐにアウトライン表示内に示されます。しかしながら、こうした割り当ては、 TeXShop のメニューですでに使われているショートカットキーと重複させることはできません。もしも重複した場合は、新しいほうのショートカットは無視されます。

##AppleScript Macros（ AppleScript マクロ）

［☆］If a macro begins with the string

【★】マクロが次のいずれかの文字列で始まっている場合──

	--AppleScript

	--AppleScript direct

［☆］then the resulting applescript code will run when the Macro is chosen. For example, consider the macro titled "View pdf with Acrobat." Choosing this macro when the source file is active (and the pdf file has been created) will start Adobe Acrobat Reader and open the output pdf file in that program. The corresponding applescript code reads

【★】そのマクロを選択すると、 AppleScript のコードが実行されます。 たとえば「View pdf with Acrobat」と題されたマクロを考えてみます。 ソースファイルがアクティブになっている（加えて pdf ファイルもすでに生成済みになっている）ときにこのマクロを選択すると、 Adobe Acrobat Reader が立ち上がって pdf 出力ファイルを開きます。 この AppleScript のコードは、次のようになっています──

	--AppleScript direct
	tell application "Acrobat Reader 5.0"
		activate
		open POSIX file #PDFPATH#
	end tell

［☆］Commands beginning with "--AppleScript direct" are run directly by TeXShop. During the time this applescript is running, TeXShop's event loop is not active. Consequently, the script cannot call TeXShop to perform an action which might require user input. For example, it cannot ask TeXShop to run LaTeX, because if the LaTeX file has an error, the console will appear and wait for user input, but such input would not be recognized.

【★】「--AppleScript direct」で始まるコマンドは、 TeXShop により直接実行されます。この AppleScript が実行されている間は、 TeXShop のイベント・ループは有効になりません。したがってこのスクリプトには、 TeXShop を呼び出して、ユーザの入力を必要とするかもしれない動作を行なわせることはできません。たとえば、 TeXShop に LaTeX を実行するよう要請することができません──というのも、 LaTeX ファイルにエラーがあった場合、コンソールが表示されユーザの入力を待ちますが、そうした入力はできないのです。

［☆］Commands beginning with "--AppleScript" are run by a small auxiliary program in the TeXShop application bundle. Such commands can ask TeXShop to perform actions which might require user input, because in that case the auxiliary program will temporarily halt but TeXShop will remain active.

【★】「--AppleScript」で始まるコマンドは、 TeXShop に組み込まれている小さな補助プログラムにより実行されます。こうしたコマンドは、ユーザの入力を必要とするかもしれない動作を行なうことを TeXShop に要求できます──というのも、この場合、補助プログラムは一時的に停止しますが、 TeXShop はアクティブのままだからです。

［☆］Thus the syntax "--AppleScript direct" is appropriate for routine macros, but "--AppleScript" may be needed for fancy ones.

【★】なので「--AppleScript direct」構文はルーティン・マクロに適していますが、手の込んだマクロには「--AppleScript」が必要となるでしょう。

##Default AppleScript Macros（デフォルトの AppleScript マクロ）

［☆］TeXShop comes with an extended collection of Applescripts by Will Robertson, Claus Gerhardt and others. Some of these scripts automate workflow when a series of typesetting commands must be issued in sequence. By copying and modifying the scripts, users can construct scripts appropriate for their own workflow.

【★】TeXShop には Will Robertson や Claus Gerhardt その他の人たちによる AppleScript の広汎なコレクションが付属しています。これらのスクリプトのいくつかは、一連のタイプセット・コマンドが順を追って実行されるとき、ワークフローを自動化します。スクリプトを複製したり修正したりすることでユーザは、それぞれのワークフローに適したスクリプトを組み立てることができます。

［☆］In this section, we will describe some of these scripts.

【★】このセクションでは、こうしたスクリプトのいくつかについて述べます。

----

［☆］**Column Macros, Insert Reference, Open Quickly:**

【★】**Column Macros ・ Insert Reference ・ Open Quickly**

［☆］These macros are by Will Robertson. The first provides a very convenient way to construct an arbitrary matrix or table. The second searches through the current file for \label{...} commands and then pops up a list from which you may insert a reference label, wrapped in an (optional) customizable LaTeX command. The final macro allows you to rapidly open any file in the directory of the current source file.

【★】これらのマクロは Will Robertson によるものです。最初のものは、任意の行列やテーブルをこしらえるのにとても便利です。次のものは、現在のファイル全体から \label{...} コマンドを探し出してリスト表示するので、その中から参照ラベルを挿入したり、それを（任意の）カスタマイズ可能な LaTeX コマンドで囲んだりできます。最後のマクロは、作業中のソースファイルがあるディレクトリ内のファイルが手早く開けます。

----

［☆］**Convert to Mac, Convert to Unix, Convert to Windows:**

【★】**Convert to Mac ・ Convert to Unix ・ Convert to Windows**

［☆］In the early days, teletype terminals were used for communication. The ascii character set still has remnants from those days; for instance 0x07 rings the teletype bell. The character 0x0a was a line feed which turned the carriage to the next line and the character 0x0d was a carriage return which pulled the carriage back to the start of the line. To get a line feed, one used the sequence 0x0d 0x0a.

【★】初期の頃は、テレタイプ端末が通信に使われていました。 ascii 文字セットはいまだにその頃の名残りをとどめています ； たとえば 0x07 はテレタイプのベルを鳴らします。 0x0a というキャラクタはキャリッジを次行へ送るラインフィード（ LF ＝改行）でしたし、 0x0d というキャラクタはキャリッジを行の先頭まで引き戻すキャリッジ・リターン（ CR ＝行頭復帰）でした。行を改めるには、ひとつづきの 0x0d 0x0a を使いました。

［☆］After the age of teletypes ended, computer manufacturers selected different subsets of these characters to indicate a line feed. In the Unix world, 0x0a was used, in the Windows world 0x0d 0x0a was used, and in the old Macintosh Classic world 0x0d was used. Apple's guidelines for Mac OS X state that programs should be able to automatically open files using any of these conventions. Most programs including TextEdit, TeXShop, etc., follow these guidelines. In TeXShop, new files are created using Unix conventions, but if you load a file created with Mac OS Classic and then add extra lines, old portions of the document will be saved with the Classic convention and new sections will have the Unix convention.

【★】テレタイプの時代が終わると、コンピュータの製造者たちは、改行を示すのに、これらのキャラクタの異なる一部を選び取りました。 UNIX では 0x0a（ LF ）が使われ、 Windows では 0x0d 0x0a（ CR + LF ）が、そして昔の Macintosh Classic では 0x0d（ CR ）が使われました。 Mac OS X 用の Apple のガイドラインには、こうした仕様のいずれが用いられているファイルでも自動的に開けるようにすべきだ、と述べられています。 TextEdit や TeXShop などを含むほとんどのプログラムは、このガイドラインにしたがっています。 TeXShop では、新規書類は Unix の改行コードで作成されますが、 Mac OS Classic で作成したファイルを取り込んで新しい行を付け加えた場合、文書の古い部分は Classic の改行コードで保存され、新たな箇所は Unix の改行コードで保存されます。

［☆］These line feeds cause no trouble until you send a file to a friend using a different operating system. Many editors now understand multiple line feed conventions, so often you'll have no problems. But if you do, use the scripts above. Suppose the source file for a document is named MyFile.tex. Then "Convert to Mac" will create a new file named MyFile_Mac.tex with the same source code and Macintosh line feed conventions. "Convert to Unix" and "Convert to Windows" work the same way. All of these scripts call a binary program by Craig Stuart Sapp named "flip" in ~/Library/TeXShop/bin. See http://ccrma-www.stanford.edu/~craig/utility/flip/ for details.

【★】こうした改行コードは、異なるオペレーティング・システムを使っている人にファイルを送らないかぎりは、トラブルの種になったりはしません。多くのエディタが今では複数の改行コード仕様を理解しますから、そう頻繁に問題にはならないでしょう。けれども困ったことになった場合には、上記のスクリプトを使ってください。かりにソースファイルの名前を MyFile.tex としておきましょう。 「Convert to Mac」は、 MyFile_Mac.tex という名前の、ソースコードは同じで Macintosh の改行コードになっている新しいファイルを生成します。 「Convert to Unix」と「Convert to Windows」も同様に機能します。これらのスクリプトはすべて ~/Library/TeXShop/bin にある「flip」という、 Craig Stuart Sapp の作ったバイナリ・プログラムを呼び出します。詳細については http://ccrma-www.stanford.edu/~craig/utility/flip/ を参照してください。

----

［☆］**Other Scripts->Bibliography:**

【★】**Other Scripts->Bibliography**

［☆］Processing a file with a bibliography requires multiple typesetting operations. First Latex is run to create an .aux file. Then Bibtex is run and uses this file to create .bbl and .blg files. Latex is run again to add the bibliography to the document. Latex is run a final time to update the references to the bibliography in the text.

【★】参考文献目録のあるファイルを処理するには、数度のタイプセット操作が必要になります。最初に LaTeX を実行して .aux ファイルを作る。それから Bibtex を実行し、.aux ファイルを使って .bbl ファイルと .blg ファイルを作る。 LaTeX をふたたび実行して文書に参考文献目録を付け加える。最後に LaTeX を実行して本文中の目録の参照を更新する。

［☆］The "Bibliography" command does all of these things one by one. First it saves the file. Then it runs latex->bibtex->latex->latex. Finally it updates the preview display.

【★】「Bibliography」コマンドは、以上のことをひとつずつ行ないます。まず最初にファイルを保存します。そして latex -> bibtex -> latex -> latex の順に実行します。最後にプレビュー画面を更新します。

----

［☆］**htlatexc, htlatexr:**

【★】**htlatexc ・ htlatexr**

［☆］Tex4ht is a TeX program which converts a latex document into a web page. The source can be a standard Latex file and can include eps illustrations. The end result is an html page and a large number of gif files. The script command "htlatexc" saves the source documents, runs htlatex, and opens the resulting html file in Safari. Thus it behaves like a new TeXShop typesetting command, except that it was constructed by a user without waiting for new TeXShop code!

【★】Tex4ht は、 LaTeX 文書をウェブページに変換する TeX プログラムです。ソースは標準的な LaTeX ファイルでよく、 eps 形式のイラストを含んでいてもかまいません。最終的な結果は html ページとなり、多数の gif ファイルが含まれています。スクリプトコマンド「htlatexc」は、ソース文書を保存し、 htlatex を実行し、結果の html ファイルを Safari で開きます。つまりこれは、 TeXShop の新しいタイプセット・コマンドのように動作します── TeXShop の新しいコードを待たずにユーザによって構築される、ということを除けば！

［☆］When using these scripts, it is not necessary to use the package text4ht since this package will automatically be loaded. The script htlatexc calls htlatex without additional options. The script htlatexr calls it with the option "-r", which tells the program to recreate any .gifs which already exist.

【★】これらのスクリプトを使う際には、 Tex4ht パッケージを使用する必要はありません──このパッケージは自動的に読み込まれます。スクリプト htlatexc は、追加オプションなしで htlatex を呼び出します。スクリプト htlatexr は、をオプション「-r」を付けて呼び出します──これはすでにあるすべての .gif ファイルを再生成するようプログラムに命じます。

----

［☆］**pdfselectc:**

【★】**pdfselectc**

［☆］This script runs the shell script pdfselect to create pdf files containing only certain selected pages of a document. When it is run, a dialog appears asking for the number of pdf files to be created. Suppose we answer 3. Next a dialog appears asking for the range for the first document. Suppose we answer 5:8. A dialog appears asking for the range of the second document. Suppose we answer 10. A dialog asks for the range of the third document. Suppose we answer 20:30. We will then obtain three documents, one containing pages 5 - 8 of the original, one containing page 10, and one containing pages 20 - 30.

【★】このスクリプトは、シェルスクリプト pdfselect を実行し、文書の中から選択したページのみを含む pdf ファイルを作成します。これを実行すると、作成する pdf ファイルの数を尋ねるダイアログが表示されます。ためしに 3 としてみましょう。つづいて最初の文書のページ範囲を尋ねるダイアログが表示されます。これを 5:8 とします。次に第２の文書のページ範囲を尋ねるダイアログが表示されます。これを 10 とします。最後に第３の文書のページ範囲を尋ねるダイアログが表示されます。これを 20:30 とします。これで３つの文書が得られることになります──ひとつには元の文書の５〜８ページが、もうひとつには10ページ目が、そして最後のひとつには20〜30ページが含まれています。

----

［☆］**mpostc, mpostcpl, latex-makeindex-mpost:**

【★】**mpostc・mpostcpl ・ latex-makeindex-mpost**

［☆］The script mpostc runs mpost and then pdflatex; the script mpostcpl runs pdflatex, and then mpost, and then pdflatex again. See the TeXShop help file Advanced: Context and Metapost for an example of the use of these three commands in sequence.

【★】スクリプト mpostc は mpost を実行した後で pdflatex を実行します ； スクリプト mpostcpl は pdflatex を実行した後で mpost を実行し、ふたたび pdflatex を実行します。この３つのコマンドを順々に用いる例については、 TeXShop ヘルプの「上級向けのヘルプ」にある「ConTeXt と MetaPost」を参照してください。

［☆］The script latex-makeindex-mpost saves the source and runs pdflatex, makeindex, mpost, and pdflatex again, opening relevant log files in the process.

【★】スクリプト latex-makeindex-mpost は、ソースを保存し、 pdflatex, makeindex, mpost, そしてもう一度 pdflatex を実行し、その過程で当該のログファイルを開きます。

##Defining AppleScript Macros（ AppleScript マクロを定義する）

［☆］AppleScript syntax is a subject all its own. To learn more about it, read one of several books on the subject. If you installed the developer tools which come with Mac OS X, there is an online book about AppleScript in the Developer folder.

【★】AppleScript の文法はそれ自体でひとつのテーマです。 AppleScript についてさらに学ぶには、関連本をどれか１冊読んでみてください。 Mac OS X に付属するデベロッパー・ツールズをインストールしているのであれば、 AppleScript についてのオンライン本が Developer フォルダの中に入っています。

［☆］When TeXShop interpretes an applescript macro, it first replaces any string #FILEPATH#, #PDFPATH#, #DVIPATH#, #PSPATH#, #LOGPATH#, #AUXPATH# with the complete path name of the source tex file, pdf file, dvi file, ps file, log file, or aux file respectively. Similarly, the strings #INDPATH#, #BBLPATH#, and #HTMLPATH# are replaced with the complete path name of the ind file, bbl file, or html file.

【★】TeXShop が AppleScript マクロを実行するときには、最初に #FILEPATH#, #PDFPATH#, #DVIPATH#, #PSPATH#, #LOGPATH#, #AUXPATH# といった文字列をすべて、 TeX ソースファイル、 pdf ファイル、 dvi ファイル、 ps ファイル、 log ファイル、あるいは aux ファイルそれぞれの完全パス名で置き換えます。同様に文字列 #INDPATH# ・ #BBLPATH# ・ #HTMLPATH# は、 ind ファイル、 bbl ファイル、 html ファイルの完全パス名に置き換えられます。

［☆］In addition, any string #NAMEPATH# is replaced with the complete path name of the source tex file minus its extension, and any string #DOCUMENTNAME# is replaced with the display name of the current document. This last replacement is somewhat subtle; it gives the title of the document as shown at the top of the source window. If a document was saved with the "hide extension" box checked, #DOCUMENTNAME# will contain only the document name. But if the document was saved without checking "hide extension", #DOCUMENTNAME# will contain the document name and extension. This information can be used to locate the calling document for Applescript code as follows:

【★】加えて、文字列 #NAMEPATH# はすべて、 TeX ソースファイルの拡張子を省いた完全パス名で置き換えられますし、文字列 #DOCUMENTNAME# はすべて、現在の文書の表示名で置き換えられます。この最後の置き換えは、いくぶん微妙なものです ； ソースウィンドウの上部に示されている文書のタイトルが使われるのです。もし「拡張子を隠す」にチェックを入れて文書を保存していた場合には、#DOCUMENTNAME# は文書名のみになります。けれども「拡張子を隠す」にチェックを入れずに文書を保存していれば、#DOCUMENTNAME# には文書名＋拡張子が入ります。このことは、次のように AppleScript コードで呼び出す文書を見つけるのに使えます：

	tell document #DOCUMENTNAME# of application "TeXShop"
	latex
	end tell

［☆］There are at least two ways to write Applescript commands. Applescript can run shell commands, so after preliminary processing with an applescript, a shell command can be called to do the actual work. TeXShop comes with several examples of this technique; some of these examples will be explained in a later help section. Applescript commands can also call build-in TeXShop commands and thus work directly. A later section will give examples of this technique.

【★】AppleScript コマンドを書く方法は、少なくとも２つあります。 AppleScript はシェルコマンドを実行できるので、 AppleScript で前処理をした後、シェルコマンドを呼び出して実作業をさせることができます。 TeXShop にはこの手法についての例がいくつか付属しています ； こうした例の中には、ヘルプの後節で説明するものもあります。 AppleScript コマンドは、 TeXShop に組み込まれているコマンドを呼び出して直接作動させることもできます。後節ではこちらの手法の例について触れます。

［☆］TeXShop understands the following commands:

【★】TeXShop は以下のコマンドを理解します：

* typeset
* latex
* tex
* context
* bibtex
* makeindex
* metapost
* typesetinteractive
* latexinteractive
* texinteractive
* contextinteractive
* bibtexinteractive
* makeindexinteractive
* metapostinteractive
* taskdone
* refreshpdf
* refreshtext
* goto line

［☆］The first seven commands call TeXShop typesetting routines. These commands typeset continuously without stopping at errors. The next seven commands also call TeXShop typesetting commands, but this time if there is an error, the user is allowed to interact with the console. When a typesetting command is called, control returns to the applescript immediately without waiting until the operation is complete. The "taskdone" call returns NO if typesetting is still running, and YES when it is done. The calls "refreshpdf" and "refreshtext" cause pdf and text documents to display the latest version of their files on the screen. The "goto line" command tells the editor to select a given line; for example:

【★】最初の７つのコマンドは TeXShop のタイプセット・ルーチンを呼び出します。これらのコマンドはエラー箇所で止まることなしにタイプセットを継続します。次の７つのコマンドもまた TeXShop のタイプセット・コマンドですが、こちらはもしエラーがあれば、コンソールで対話的に作業を行なえます。タイプセット・コマンドが呼び出されると、作業が完了するのを待たずに、コントロールはすぐに AppleScript に戻ります。 「taskdone」は、タイプセット中は NO を返し、完了すると YES を返します。 「refreshpdf」と「refreshtext」は、 pdf およびテキスト文書を最新の状態で画面に表示します。 「goto line」コマンドは、指定の行を選択するようエディタに命じます ； たとえば：

	tell document #DOCUMENTNAME# of application "TeXShop"
	goto line 37
	end tell

##Creating Dialogs（ダイアログを作る）

［☆］AppleScript can create dialogs and act on user input. For example, insert the following script and test its behavior.

【★】AppleScript でダイアログを作成し、ユーザの入力に応じて動作するようにできます。たとえば、以下のスクリプトを書き入れて、ふるまいを試してみてください。

	-- AppleScript
	-- Use a dialog to enter user defined information into an applescript.
	-- ダイアログを使い、ユーザの定めるデータを AppleScript に取り込みます。
	-- There are two feedbacks possible 'text' and "choice of buttons".
	-- 「テキスト」と「ボタン選択」による２つのフィードバックが利用可能です。
	-- The returned information can be used to define corresponding variables.
	-- 返されたデータは該当する変数を定義するのに使えます。
	-- The number of buttons may not exceed three.
	-- ボタンの数は３つを超えないように。
	-- In the three examples below it is shown how to use text return, button return, and both.
	-- 以下の３つの例では、テキスト、ボタン、テキスト＆ボタンの使い方について示しています。
	
	activate
	display dialog "Test dialog: type something below" default answer▼
	 "Hello World!" buttons {"A", "B", "C"} default button "B"
	set theText to (the text returned of the result)
	
	display dialog "Test dialog: type something below" default answer▼
	 "Hello World!" buttons {"A", "B", "C"} default button "B"
	set theButton to (the button returned of the result)
	
	display dialog "Test dialog: type something below" default answer▼
	 "Hello World!" buttons {"A", "B", "C"} default button "B"
	set {theText, theButton} to {the text returned of the result,▼
 	the button returned of the result}

* 補足：▼に改行を挿入しました。本来はひとつながりです。

［☆］One command in this example, "activate", requires comment. When TeXShop is asked to run an AppleScript, it calls a separate program to run the script. That program, Scriptrunner, is in the TeXShop bundle. Any dialogs created by the script will be displayed by Scriptrunner rather than by TeXShop. The "activate" command brings Scriptrunner to the front so dialogs will appear on top of other windows.

【★】この例にあるコマンド「activate」には解説が必要です。 AppleScript を実行するよう要請されるとTeXShop は、別のプログラムを呼び出してスクリプトを実行します。そのプログラム── Scriptrunner は、 TeXShop に組み込まれています。スクリプトで作成したダイアログはすべて、 TeXShop ではなく Scriptrunner で表示されます。 「activate」コマンドは Scriptrunner を前面に持ってくるので、ダイアログは他のウィンドウよりも手前に表示されます。

##Writing Scripts with TeXShop Typesetting Commands（ TeXShop のタイプセット・コマンドでスクリプトを書く）

［☆］If a TeX project contains a bibliography, a sequence of typesetting commands must be run to update the bibliography. Latex is run first to create an .aux file. Bibtex is run to create .bbl and .blg files from this .aux file. Latex is run again to add the bibliography to the document. Latex is run a final time to update the references to the bibliography in the document.

【★】TeX プロジェクトが参考文献目録を含んでいる場合には、一連のタイプセット・コマンドを実行して目録をアップデートしなければなりません。まず LaTeX を実行して .aux ファイルを作成する。 BibTeX を実行して .aux ファイルから .bbl および .blg ファイルを作成する。再度 LaTeX を実行して参考文献目録を文書に付け加える。 LaTeX を最終的に実行して目録に対する文書内の参照をアップデートする。

［☆］Your projects may contain similar sequences of typesetting commands. It is possible to use applescript to automate these sequences.

【★】複数のプロジェクトに、一連の同様なタイプセット・コマンドが含まれていることもあるでしょう。 AppleScript を使えば、こうした作業を自動化することができます。

［☆］To see how to do that we'll examine the OtherScripts->Bibliography command which comes with TeXShop. Here is the body of that command

【★】どんなふうにすればいいのか、 TeXShop に付属する「OtherScripts->Bibliography」というコマンドを例に調べてみます。このコマンドの本体は次のようになっています。

	--Applescript
	
	set fileName to #FILEPATH#
	if fileName is equal to ""
	activate
	display dialog "Please save the file first" buttons {"OK"} default button "OK"
	return
	end if
	
	set frontName to #DOCUMENTNAME#
	tell application "TeXShop"
	save document frontName
	end tell
	
	tell document frontName of application "TeXShop"
	
		latexinteractive
	
		repeat
			delay 2
			if taskdone
			exit repeat
			end if
		end repeat
	
		bibtex
	
	repeat
			delay 2
			if taskdone
			exit repeat
			end if
		end repeat
	
		latex
	
		repeat
			delay 2
			if taskdone
			exit repeat
			end if
		end repeat
	
		latex
	
	end tell

［☆］The first line of this command indicates that this is an AppleScript macro. The next lines check #FILEPATH#, a parameter which gives the full path to the tex source. This parameter is an empty string when a new document has been created and not yet saved. In that case the user is asked to save the document and the script ends.

【★】コマンドの第１行目は、これが AppleScript マクロであることを示しています。次の行では #FILEPATH#（ TeX ソースのフルパス名を与えるパラメータ）をチェックしています。このパラメータは、新規書類が作成されていながらまだ保存されていないと、空っぽの文字列になります。その場合、ユーザは文書を保存するように言われ、スクリプトは終了します。

［☆］The next line tells TeXShop to save the document. Notice that we use #DOCUMENTNAME# to refer to the document in question.

【★】次につづく行では、文書を保存するよう TeXShop に命じています。対象となる文書を参照するのに #DOCUMENTNAME# を使っていることに注意します。

［☆］The remaining commands run latexinteractive, bibtex, latex, and latex. Recall that control returns to applescript immediately after calling a typesetting command before the typesetting job is over. The repeat loop tells the script to check whether the job is complete before running another typesetting task. The line "delay 2" causes applescript to pause rather than continually asking if the task is done and thereby slowing the entire computer down.

【★】残りのコマンドで latexinteractive, bibtex, latex, それに latex を実行しています。タイプセット・コマンドを呼び出した後、タイプセット作業が完了する前に、コントロールはすぐに AppleScript に戻ることを思い出してください。 repeat のループ部分では、次のタイプセット処理が実行される前に、先立つ作業が完了したかどうかをチェックするようスクリプトに命じています。 「delay 2」という行は、作業が完了したかどうかを絶えず問い合わせつづけることでコンピュータ全体の速度を低下させないよう AppleScript に間合いを取らせています。

##Writing Scripts with Shell Commands（シェルコマンドでスクリプトを書く）

［☆］We will use the AppleScript "pdflatexc" by Claus Gerhardt to illustrate the principles involved in calling a Unix shell script from an Applescript. This particular shell script isn't very interesting; it adds the location of the teTeX binary files to the $PATH variable and calls pdflatex to typeset.

【★】Claus Gerhardt による AppleScript 「pdflatexc」を使って、 AppleScript から UNIX のシェルコマンドを呼び出す原理を例示してみましょう。このシェルスクリプト自体は大しておもしろくありません ； teTeX のバイナリの場所を $PATH 変数に加え、 pdflatex を呼び出してタイプセットを行なっています。

［☆］The shell script itself is independent of TeXShop and can be run from the Terminal by typing "pdflatexc myfile.tex" provided the directory holding pdflatexc is in the search path for binaries. Here is that shell script:

【★】シェルスクリプトそのものは、 TeXShop には依存していませんし、 pdflatexc を含むディレクトリがバイナリの検索パスにあれば「pdflatexc myfile.tex」と打ち込むことで Terminal からも実行できます。これがそのシェルスクリプトです：

	#!/bin/tcsh
	# pdflatexc
	# Claus Gerhardt
	#
	# Usage
	# pdflatexc filename.tex
	
	set path= ($path /usr/local/teTeX/bin/powerpc-apple-darwin-current /usr/local/bin)
	
	pdflatex --shell-escape "$1"

［☆］Of course you are likely to write a more complicated script which performs several operations in sequence. That is when these techniques become useful.

【★】もちろん、いくつもの作業を次々とこなしてゆくような、より複雑なスクリプトを書くこともあるでしょう。そういうときにこそ、こうした技法が役に立つようになります。

［☆］The AppleScript used to call this shell script is more interesting. Here it is:

【★】このシェルスクリプトを呼び出すのに使う AppleScript はもうちょっとおもしろいものです。まずはご覧ください：

	--Applescript
	-- Apply only to an already saved file.
	-- すでに保存済みのファイルにのみ適用すること。
	-- Claus Gerhardt, Nov. 2003
	
	set scriptPath to (do shell script "dirname " & "~/Library/TeXShop/Scripts/ex")
	set scriptPath to scriptPath & "/setname.scpt"
	set scriptName to POSIX file scriptPath as alias
	set scriptLiB to (load script scriptName)
	tell scriptLib
	set frontName to setname(#NAMEPATH#,#TEXPATH#)
	end tell
	
	set fileName to #TEXPATH#
	set n to (number of characters of contents of fileName)
	set fileNamequoted to quoted form of fileName
	set baseName to do shell script "basename " & fileNamequoted
	set m to (number of characters of contents of baseName)
	set dirName to quoted form of (characters 1 thru (n - m - 1) of fileName as string)
	
	set shellScript to "cd " & dirName & ";"
	set shellScript to shellScript & "~/Library/TeXShop/bin/pdflatexc " & baseName
	do shell script shellScript
	
	tell document frontName
	refreshpdf
	end tell

［☆］Ignoring the introductory comments, the first seven lines of this script are a magic recipe by Claus Gerhardt to save the source file and find the name of the document in question, setting "frontName" to this name. This recipe uses a compiled script named "setpath.scpt" in ~/Library/TeXShop/Scripts to do all the hard work. Careful reading shows that these lines find the path ~/Library/TeXShop/Scripts/setname.scpt and call this script with parameters #NAMEPATH# and #TEXPATH#.

【★】前置きのコメントはさておき、このスクリプトの冒頭７行は、 Claus Gerhardt の魔法のレシピです──ソースファイルを保存し、処理しようとしている文書の名前を見つけて「frontName」にセットしています。このレシピでは、 ~/Library/TeXShop/Scripts にある「setpath.scpt」というコンパイル済みのスクリプトを使ってハードな作業すべてをこなしています。注意深く読み解いてみれば、この数行は ~/Library/TeXShop/Scripts/setname.scpt というパスを見つけ、パラメータ #NAMEPATH# と #TEXPATH# でスクリプトを呼び出していることがわかります。

［☆］In many AppleScripts all of this could be accomplished in an earier way using the commands:

【★】多くの AppleScript では、これはすべて、次のようなコマンドを使う簡単な方法で済ませられます：

	set frontName to #DOCUMENTNAME#
	tell document frontName of application "TeXShop"
	save
	end tell

［☆］However, Gerhardt's script has two advantages. First, his script can be called when the front document is a log file, say /Users/koch/Examples/myfile.log, that is, in a case when the front document is not the document which should receive later commands. Second, if the file has never been saved, Gerhardt's script returns an error when trying to save, while the "save" command would cause TeXShop to hang after it put up a save dialog (see the help document Writing Scripts with TeXShop Typesetting Commands for details.)

【★】しかしながら Gerhardt のスクリプトには長所が２つあります。ひとつは、前面にある文書がログファイル（たとえば /Users/koch/Examples/myfile.log のようなもの）であっても──換言すれば、これ以降のコマンドを受け入れないような種類の文書だったとしても──スクリプトを呼び出せる、ということです。もうひとつは、ファイルが一度も保存されていなかった場合、 Gerhardt のスクリプトは保存を行なおうとしてエラーを返します──その一方で「保存」コマンドにより、保存ダイアログを出して TeXShop は保留状態になります（詳しくはヘルプの「TeXShop のタイプセット・コマンドでスクリプトを書く」を参照してください）。

［☆］The next six lines of the script define the variables dirName and baseName. If the source file is "/Users/koch/This directory/Stuff/myfile.tex", dirName is " '/Users/koch/This directory/Stuff' ", including the single and double quotation marks, and baseName is "myfile.tex." A lot of this work is required so spaces can occur in the names of folders. As always, tex does not allow spaces in the final file name.

【★】つづく６行では、変数 dirName と baseName を定義しています。ソースファイルが「/Users/koch/This directory/Stuff/myfile.tex」の場合、 dirName は、シングルクオートとダブルクオートを含めて「" '/Users/koch/This directory/Stuff' "」となり、 baseName は「myfile.tex」となります。この作業部分が必要なのは、フォルダ名にスペースがあってもいいようにです。依然として TeX は、最終的なファイル名にあるスペースを容認しません。

［☆］The next three line call the shell script. The result is the same as typing "cd dirName; ~/Library/TeXShop/bin/pdflatexc baseName" in a Terminal, although, to be absolutely precise, dirName would have to be replaced by its unquoted form, i.e., if we use the example above, by '/Users/koch/This directory/Stuff' including the single quotes because of the space in the name of one directory.

【★】そのまた次の３行がシェルスクリプトを呼び出しています。結果的には Terminal で「cd dirName; ~/Library/TeXShop/bin/pdflatexc baseName」と打ち込むのと同じとはいえ、はるかに正確です──というのも、 dirName は引用ではない形（つまり、上の例で言えば、途中のディレクトリにスペースがあるのでシングルクオートを含めて「'/Users/koch/This directory/Stuff'」）に置き換えねばならないのです。

［☆］Shell commands in AppleScript are issued in the form

【★】 AppleScript におけるシェルスクリプトは次のような形で発令されます──

	do shell script "cmd input"

［☆］If one wants to combine several shell scripts, it is better to write the command in an equivalent form

【★】複数のシェルスクリプトを結合させたいのであれば、対等につなぐ形式で書くのがいいでしょう──

	do shell script "cmd " & "input"

［☆］Notice the space behind cmd and the quotes. The ampersand is a binary concatenation operator, i.e.,

【★】cmd と引用符の間の半角スペースに注意してください。アンパサンド（＆記号）はバイナリの連結演算子です。つまりこういうことです──

	"cmd " & "input" = "cmd input"

［☆］When the shell is called via an applescript, the default working directory is the root directory. The command

【★】シェルが AppleScript で呼び出される場合、デフォルトの作業ディレクトリはルートディレクトリです。

	do shell script "cd " dirName

［☆］changes the directory to the directory specified in dirName; dirName is already quoted so that additional quotes are not needed.

【★】上のコマンドでは、ディレクトリを dirName で定められているディレクトリに変更しています ； dirName はすでに引用済みなので引用符を加える必要はありません。

［☆］If one would like to keep the working directory and issue further commands, then these commands may not be stated in the form "do shell script", since then a new shell would be invoked. In the terminal one would separate consecutive commands by semicolons, in AppleScript one does it by concatenating ";", i.e.,

【★】作業ディレクトリを動かさずにさらにコマンドを入れたいのであれば、 「do shell script」の形では記述できません──それだと新規シェルが呼び出されてしまいます。 Terminal では連続するコマンドをセミコロンで区切りますが、 AppleScript では「";"」を使います。つまりこういうふうに──

	do shell script "cmd(1) " & "input(1)" & ";" & "cmd(2) " & "input(2)"

［☆］This is done in the above example: cmd(1) = cd, "input(1)" = dirName, cmd(2) = ~/Library/TeX/bin/pdflatexc - calling the shell script -, and "input(2)" = baseName.

【★】上記の例で言うならこれは、こういうことです： cmd(1) = cd ・ "input(1)" = dirName ・ cmd(2) = ~/Library/TeX/bin/pdflatexc（シェルスクリプトを呼び出しています） ・ "input(2)" = baseName。

［☆］The lines

	set shellScript to "cd " & dirName & ";"
	set shellScript to shellScript & "~/Library/TeX/bin/pdflatexc " & baseName

［☆］are simply a convenient way to concatenate this sequence of commands and input into one variable.

【★】──という２行は単に、ひとつながりのコマンドを変数ごとに分かち書きしているだけのことです。

［☆］The final three lines update the Preview window.

【★】最後の３行でプレビューウィンドウを更新しています。

［☆］To be sure, several of these lines are complicated, but these lines can be copied without change into new scripts.

【★】たしかに複雑な行もいくつかありますが、そうしたものでも、そのままコピーして新しいスクリプトに使えます。

----
[もくじ](README.md)
