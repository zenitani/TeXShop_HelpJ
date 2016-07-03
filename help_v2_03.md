TeXShop の日本語ヘルプファイルのアーカイブ (v2-3) です。

作業当時の日英対訳テキストをアップしています。

----
Version 2.10b
----

#Advanced Help（上級向けのヘルプ）（その２）

##Unicode（ユニコード）

［☆］Unicode is a format which can simultaneously encode characters from languages across the world: Arabic, Chinese, Greek, Hebrew, Japanese, Roman, Russian, and a host of others. Cocoa can produce Unicode, so TeXShop can as well. To experiment, open the International preference in the System Preferences program, choose the Input Menu tab, and add additional selections to the items already selected. It is illuminating to select Greek (because it is familiar), Hebrew (because it is written from right to left), Arabic (because it is written from right to left and makes extensive use of ligatures, so characters have different shapes at the ends of words than in the middle) and Chinese. A new menu item will appear with a flag indicating the current input language.


【★】Unicode は世界の主要な言語（アラビア語、中国語、ギリシア語、ヘブライ語、日本語、ローマ字、ロシア語、その他の多くの言語）の文字を、単一の文字コード体系で処理する仕組みです。 Cocoa のテキスト処理は Unicode がベースになっているので、 TeXShop でもそのまま Unicode を扱うことができます。 Unicode が実際にどんな感じなのか試してみるには、 「システム環境設定」から「言語環境」を開き、 「入力メニュー」タブで、すでに「入」になっているものに加えて別の言語を選んでみてください。たとえば、ギリシア語（よく知られていますね）、ヘブライ語（右から左へ書きます）、アラビア語（右から左へ書くうえ、リガチャ〔合字〕を広範に使用するので語末と語中とでは字体が異なります）、あるいは中国語などを選んでみるとわかりやすいでしょう。追加した入力メニューは、現在の入力言語を示す国旗で表示されます。

［☆］Type some characters, switch to another language, and type some more.

【★】数文字打ち込んでみてから、他の言語に変え、さらにまた打ち込んでみます。

［☆］There are several formats for Unicode files. A preference item allows users to select two of them. Standard OS X Unicode is the usual code used by Mac OS X, but I do not know if this is useful in the TeX world. UTF-8 Unicode is a popular format because ordinary ascii characters appear as they usually do. If a file is saved in UTF-8 format, TeX can process it, but it will convert Unicode characters to question marks.

【★】Unicode ファイルにはいくつかの形式があります。環境設定項目ではそのうちの２つを選べます。標準的な OS X Unicode は Mac OS X ではよく使われますが、これが TeX の世界で有用なのかどうかについてはわかりません。 UTF-8 Unicode は、普通の ASCII キャラクターが普通に表示されるので人気の高い方式です。 UTF-8 形式でファイルを保存すれば TeX で処理することができますが、 Unicode 文字は疑問符に置き換えられてしまいます。

［☆］There is a TeX package which accepts UTF-8 Unicode input files; see

【★】UTF-8 Unicode で入力されたファイルを扱える TeX パッケージもあります ； 下記を参照してください──

* http://www.ctan.org/tex-archive/macros/latex/contrib/supported/unicode/

* 補足：リンク不全。以下を参照
* http://www.ctan.org/tex-archive/macros/latex/contrib/unicode/

----
「UTF パッケージ対応」について

TeXShop 1.35 では、pTeX 用にUTF パッケージ（utf.sty）がサポートされるようになりました。

環境設定パネルの「詳細」タブ内に「UTF パッケージ対応」という項目があります。ここにチェックを入れることで TeXShop は、pTeX が対応してない文字（JIS X0208 以外の文字）を utf.sty の形式に変換します。たとえば、Unicode 文字は \UTF{Hex code} となり、非-Unicode 文字は \CID{glyph ID} となります。

この機能がサポートされたことによる利点は、TeXShop 内蔵のエディタで「鷗」や「閒」といった文字を直に入力できる、ということです。言い換えれば、コード表を調べたうえで本文中に \UTF{9DD7} や \UTF{9592}（ないしは \CID{07646} や \CID{08685} ）などと書く手間が省けるということです。

利用するにあたっては、utf.sty をインストールしたうえで、プリアンブル部に、

	 \usepackage{utf}

と記述する必要があります。
（ otf.sty についても、利用可能のようです。）

UTF パッケージ・OTF パッケージについてのさらに詳しい情報は、以下をご覧ください。

* http://psitau.kitunebi.com/

【補足】
* 小川版の pTeX パッケージを導入した場合は、インストール時に組み込まれるので、改めて utf.sty をインストールする必要はありません。
* 「UTF パッケージ対応」機能は、日本語系のすべてのエンコーディング方式で利用可能ですが、SJISX0213 については、これに対応した pTeX パッケージを利用する必要があります。
* グリフ機能（CID）を使うときには、ヒラギノフォントを用いるのが無難でしょう。

##BibTeX（ BibTeX ）

［☆］BibTeX is a tool used to create bibliographies in LaTeX documents. The tool assumes that you have a large database of references which you often quote. Simple commands allow you to cite certain of these references in your LaTeX source, and BibTeX then creates a bibliography for your article containing only the items cited.

【★】BibTeX は LaTeX 文書内に参考文献目録を作成するためのツールです。このツールは、しばしば引用する文献を集成したデータベースがあることを前提としています。シンプルなコマンドを使って LaTeX ソース内で文献の一部を参照することができます──BibTeX は、論文内で参照した項目だけを含んだ参考文献目録を作成します。

（訳注：pTeX ディストリビューションには日本語に対応した jBibTeX が含まれています。TeXShop の環境設定パネルでは、BibTeX の代わりに jBibTeX を使うよう、設定することができます。）

［☆］Here is a brief example taken from The LaTeX Companion by Goossens, Mittelbach, and Samarin. Consult this book for many additional details. Suppose the database is a file called "mybibliography.bib" containing the text shown below. In this text, the entries "Felici:1991, Knuth:WEB," and "Liang:1983" are key values used to cite the articles in the LaTeX source.

【★】ここに Goossens さん・ Mittelbach さん・ Samarin さんの共著『The LaTeX Companion』から取った短い例があります。より詳しいことについてはこの本でお調べください。データベースは「mybibliography.bib」という名前のファイルで、以下に示すテキストを含むものとします。このテキスト内の、登録項目「Felici:1991」 「Knuth:WEB」 「Liang:1983」は、 LaTeX ソース内で論文を参照するのに使われる鍵値（参照名）です。

* 補足：『The LaTeX コンパニオン』アスキー書籍編集部監訳（1998年）

	@article{Felici:1991,
	author ={James Felici},
	title ={{PostScript versus TrueType}},
	journal ={Macworld},
	volume =8, pages={195--201},
	month =sep, year = 1991 }
	@techreport{Knuth:WEB,
	title ={{The \textsf{WEB} System of
	Structured Documentation}},
	month =sep, year = 1983,
	author ={Donald E. Knuth},
	address ={Stanford, CA 94305},
	number ={STAN-CS-83-980},
	institution={Department of Computer
	Science, Stanford University} }
	@phdthesis{Liang:1983,
	author ={Franklin Mark Liang},
	month =jun, year = 1983,
	school ={Stanford University},
	address ={Stanford, CA 94305},
	title ={{Word Hy-phen-a-tion by
	Com-pu-ter}},
	note ={Also available as Stanford
	University, Department of
	Computer Science Report
	No. STAN-CS-83-977} }

［☆］Suppose the LaTeX source file is called "myfile.tex" and contains the following text:

【★】LaTeX のソースファイルは「myfile.tex」という名前で、以下のテキストを含むものとします：

	\begin{document}
	Consider the argument of Felici~\cite{Felici:1991} in light of these comments.
	\nocite{Liang:1983} We provide further remarks later.
	\bibliographystyle{plain}
	\bibliography{mybibliography}
	\end{document}

［☆］When this source is typeset, a reference to Felici's article will appear in the text, and a bibliography will be created at the end of the text containing the articles of Felici and Liang, but not the article of Knuth.

【★】このソースをタイプセットすると、 Felici の論文への参照が文章内に示され、参考文献目録が文章の最後に作成されます──そこには Felici と Liang の論文はありますが、 Knuth の論文は見あたりません。

［☆］TeXShop can be used with this example in the following way. First edit and typeset the document "myfile.tex" as usual. Citations will appear in the output as "[?]" and the bibliography will be missing. Then select "BibTeX" under the Program button and run BibTeX. Next select "LaTeX" and typeset again. Citations will still appear as "[?]", but the bibliography will be added to the output. Typeset a final time, and citations will have their correct values.

【★】TeXShop では次に示す方法でこの例を利用できます。最初に「myfile.tex」という文書をいつも通りに編集してタイプセットします。参照は「 [?] 」として出力結果に示され、参考文献目録は欠落します。そのままプログラム・ボタンにある「BibTeX」を選択して実行します。次に「LaTeX」を選んで再度タイプセットします。参照はなおも「 [?] 」と表示されますが、参考文献目録は出力に付け加わります。最終的にタイプセットすると、参照も正しい値になっています。

［☆］The file "mybibliography.bib" can be opened and edited by TeXShop. If you use TeXShop to create the file "mybibliography.bib" in the first place, use the pulldown tag labeled "file format" to save the file as a bib file rather than as a tex file.

【★】「mybibliography.bib」というファイルは、 TeXShop で開いたり編集したりできます。もし最初から TeXShop を使って「mybibliography.bib」を作成するのであれば、保存画面の「フォーマット：」と表示のあるプルダウンメニューで、 tex ファイルではなく bib ファイルとして保存します。

##MakeIndex（ MakeIndex ）

［☆］MakeIndex is a tool used to add an index to a LaTeX document. To create such an index, you should

【★】MakeIndex は LaTeX 文書に索引（インデックス）を付けるのに使われるツールです。索引を作成するには、以下のようにします──

* ［☆］a. Add the command "\usepackage{makeidx}" to the top of the source file
* 【★】a. ソースファイルの冒頭にコマンド「\usepackage{makeidx}」を加える

* ［☆］b. Put a "\makeindex" command in the document preamble
* 【★】b. 「\makeindex」コマンドをプリアンブルに入れる

* ［☆］c. Put a "\printindex" command where the index should appear, often just before "\end{document}"
* 【★】c. 索引を表示させたい場所に「\printindex」コマンドを入れる──たいていは「\end{document}」の手前

* ［☆］d. Put index references in the source document, as in the example below:
* 【★】d. ソース内で索引語を指示する──下の例のように：

	"There are many animals in the world\index{animal}. Examples include bears\index{animal!bear}
	and tigers\index{animal!tiger} and various insects\index{insect|see{animal}}."
	
	「世界には数多くの動物がいます\index{どうぶつ@動物}。動物にはクマ\index{どうぶつ@動物!クマ}や
	トラ\index{どうぶつ@動物!トラ}、それに多種多様な昆虫\index{こんちゅう@昆虫|see{どうぶつ@動物}}
	も含まれます。」

* 訳注：日本語部分は mendex 用のコマンドに置き換えました。

［☆］To create the index, typeset the document as usual. Then run MakeIndex. Then typeset again.

【★】索引を作成するには、いつも通りに文書をタイプセットします。つづけて MakeIndex を実行します。その後で再度タイプセットを行ないます。

［☆］Many additional details can be found in The LaTeX Companion by Goossens, Mittelbach, and Samarin.

【★】さらに詳しいことについては、 Goossens さん・ Mittelbach さん・ Samarin さんの共著『The LaTeX Companion』に書かれています。

* 補足：『The LaTeX コンパニオン』アスキー書籍編集部監訳（1998年）

##Making and Using New TeX Formats（新規フォーマットファイルの作成と利用）

［☆］**Using formats**

【★】**フォーマットの利用**

［☆］When TeX typesets a document, it must process the document header, which may contain a large number of \input, \include, and \usepackage statements. Every time the document is typeset, this process is repeated even though large portions of the header did not change.

【★】TeX がタイプセットを行なう際には、文書のヘッダを処理しなければなりませんが、そこには \input や \includde あるいは \usepackage などの命令が数多く含まれているかもしれません。文書をタイプセットするたびに、このプロセスはくり返されます──ヘッダの大部分に変化がなかったとしてもです。

［☆］TeX has a built-in mechanism to speed up this process. It can be instructed to process lines of source and output the result to a "format file." When TeX typesets after that, it can rapidly read the format and then typeset the document. LaTeX is constructed in this manner; the format file is created when TeX is installed on your machine and the command "latex file" tells TeX to read this format and then typeset "file".

【★】TeX にはこのプロセスを高速化するための機構が組み込まれています。それにより、ソースを処理した結果を「フォーマットファイル」に出力するよう指示することができます。そうしておいてから TeX でタイプセットを実行すると、素早くフォーマットを読み込んだ上で文書をタイプセットすることができます。LaTeX はこの方法で構築されています── TeX をコンピュータにインストールする際にフォーマットファイルが生成されますが、コマンド「latex file」が TeX に対してこのフォーマットを読み込むよう命じ、その上で「ファイル」をタイプセットするのです。

［☆］When machines were slower, users often created their own format files to speed up typesetting. This is done less often today, but dealing with format files may still be useful. For instance, some organizations create and distribute a format to be used by everyone working on a common project. In this section we'll explain how to use a format file provided by someone else, and how to create a format.

【★】マシン速度がまだ遅かった時分には、ユーザはよく独自のフォーマットファイルを作成してタイプセットのスピードを上げていました。これは今日ではあまり行なわれないのですが、フォーマットファイルの利用は今でもなお有用なことかもしれません。たとえば、ある組織で、共通のプロジェクトに参加する各員が利用できるよう、フォーマットを作成して配布する、というように。この章では、他から提供されたフォーマットを利用する方法、およびどのようにしてフォーマットを作成するのかについて説明しましょう。

［☆］A typical format file has extension "fmt". Suppose a department of the University of Oregon has provided a format "uo.fmt". To use this format, follow the steps below:

【★】典型的なフォーマットファイルの拡張子は「fmt」です。たとえばオレゴン大学の学部がフォーマット「uo.fmt」を配布したとしましょう。このフォーマットを使用するには、以下のようなステップを踏みます──

* ［☆］Move uo.fmt to "~/Library/texmf/web2c/uo.fmt". You may need to create some of these directories.
* 【★】「uo.fmt」を ~/Library/texmf/web2c/uo.fmt へと移します。このうちのいくつかのディレクトリは新たに作成する必要があるかもしません。

* ［☆］Create a new "engine file" by going to ~/Library/TeXShop/Engines and duplicating the file XeLaTeX.engine. Engine files need to have the execute bit set, and this duplication step automatically does that.
* 【★】新しい「エンジンファイル」を作成します── ~/Library/TeXShop/Engines へ行き「XeLaTeX.engine」というファイルを複製してください。エンジンファイルには実行ビットセットが必要ですが、この複製の過程で自動的に備わります。

* ［☆］Rename this new file. The name need not match the name of the format. Since the name will appear in the TeXShop interface, it should make sense to a user. We'll choose "Oregon.engine".
* 【★】複製したファイルの名称を変更します。この名称をフォーマット名と同じにする必要はありません。名称は TeXShop のインターフェイスに表示されるので、ユーザにとってわかりやすいものにします。ここでは「Oregon.engine」とします。

* ［☆］Open Oregon.engine in TeXShop and edit it to read as follows
* 【★】「Oregon.engine」を TeXShop で開き、下記のように編集します──

	#!/bin/tcsh
	set path= ($path /usr/local/teTeX/bin/powerpc-apple-darwin-current /usr/local/bin)
	pdflatex -fmt uo "$1"

* ［☆］The first two lines will already be present, so it may only be necessary to change the third line. However if your machine has an Intel processor, the word "powerpc" in the second line should be changed to "i386".
* 【★】最初の２行は既存のものですから、書き換えが必要なのは３行目だけでしょう。ただし、インテルのプロセッサーを載せたマシンでは、２行目の「powerpc」を「i386」に変えてやらねばなりません。

［☆］This completes the installation. The next time you start TeXShop, the pulldown menu beside the typeset button on the Source Window Toolbar will list "Oregon" as an option. Choose this to typeset using the uo.fmt format. If you want this typesetting method to be the default, go to TeXShop preferences under the Typesetting tab, and in the Default Command box select "Command Listed Below" and fill in the edit box with the word Oregon.

【★】これで導入作業は済みました。次回 TeXShop を起動すると、ソースウインドウのツールバーにあるタイプセットボタン脇のプルダウンメニューに「Oregon」がタイプセット・オプションとして入っています。これを選択し「uo.fmt」フォーマットを使用してタイプセットします。もしもこのタイプセット方法をデフォルトにしたければ、TeXShop 環境設定を開き、「タイプセット」タブのところにある「デフォルトのコマンド」から「次のコマンドを利用」を選択し、テキストボックスに“Oregon”と書き入れておきます。

［☆］It is also possible to select the Oregon format for a particular document without changing the typesetting option. To do that, add the following line to the top of the source file:

【★】ある特定の文書用に、タイプセット・オプションを変更することなく「Oregon」フォーマットを指定することもできます。そのためには、ソースファイルの冒頭に、次のような１行を追加します──

	%!TEX TS-program = Oregon

［☆］Then uo.fmt will be used for that document regardless of the typesetting option chosen.

【★】これで、タイプセット・オプションの選択の如何に関わらず、この文書には「uo.fmt」が用いられます。

［☆］The above instructions assume you have a format for pdflatex. You can also make formats for plain tex; in that case change "pdflatex" to "pdftex" in the engine file.

【★】以上の解説は、ユーザが既に pdflatex 用のフォーマットを所持しているものと想定しています。ユーザが plain TeX 用のフォーマットを作成することもできます──この場合にはエンジンファイルを「pdflatex」ではなく「pdftex」としておきます。

［☆］It is also possible to use formats when you are typesetting with tex + ghostscript. TeXShop assumes that an engine file contains one or more command line instructions and ultimately produces a pdf file. So the engine file must contain the commands which convert the dvi file to a pdf file. Here is a typical engine file for uo.fmt in that case:

【★】「TeX + Ghostscript」でタイプセットする場合でも、フォーマットを利用することはできます。TeXShop では、エンジンファイルに１つないしはそれ以上のコマンドライン指定が含まれており、最終的には pdf ファイルを生成するものと想定しています。そのためエンジンファイルには、dvi ファイルを pdf ファイルに変換するためのコマンドが含まれていなければなりません。こういった場合における「uo.fmt」用の典型的なエンジンファイルは以下のようなものです──

	#!/bin/tcsh
	set path= ($path /usr/local/teTeX/bin/powerpc-apple-darwin-current /usr/local/bin)
	latex -fmt uolatex "$1"
	set filename = "$1"
	dvips "${filename:r}.dvi"
	pstopdf "${filename:r}.ps"
	
［☆］**Making formats**

【★】**フォーマットの作成**

［☆］Format files contain the internal binary representation of typeset lines of source. This representation depends on the processor and particular TeX implementation. Thus it is rarely possible to use a format file from someone else unless that person has the same machine and TeX installation that you do.

【★】フォーマットファイルには、ソースのタイプセットについて、内部におけるバイナリの再現性（リプリゼンテーション）が含まれています。この再現性はプロセッサと個々の TeX の実装に依存します。ですから他から提供されたフォーマットファイルが利用可能なことは滅多にありません──先方でも同じマシンを持っていて、そっくり同じように TeX をインストールしてあるのでない限りは。

［☆］However, it is common for organizations to distribute the source lines needed to construct a format. In that case you'll be told to make the format using "initTeX". For example, suppose this source text is "uo.tex". To make the format, open Apple's Terminal program and change to the directory containing the source for the format. Then type

【★】しかしながら、フォーマットを生成するために必要なソースを組織で配布することは、ごく普通に行なわれています。こうした場合には「initTeX」を使ってフォーマットを作成するように、と言われることでしょう。そこで、たとえばフォーマット用のソーステキストを「uo.tex」としてみましょう。フォーマットを作るには、Apple の Terminal.app を起動し、フォーマット用のソースがあるディレクトリへ移動します。そして次のようにタイプします──

	pdflatex -ini

［☆］You will get a ** prompt. Type the following line at the prompt

【★】すると前に ** の付いたプロンプトになります。プロンプトのところで次のように打ち込みます──

	&pdflatex uo

［☆］and press return. The format file will be created. At the end you may have to issue a "\dump" command if the format source doesn't contain it. This will produce the required "uo.fmt".

【★】そしてリターンキーを押します。これでフォーマットファイルが作成されます。もしフォーマットのソースに「\dump」が含まれていなかった場合には、最後に「\dump」コマンドを打ち込んでやらなければならないかもしれません。これで必要な「uo.fmt」が作られます。

［☆］You might like to try this with the follow "uo.tex" file:

【★】以下のような「uo.tex」で試してみるのもいいかもしれません──

	\documentclass[11pt]{article}
	\usepackage{geometry}
	\geometry{letterpaper}
	\usepackage[parfill]{parskip}
	\usepackage{graphicx}
	\usepackage{amssymb}
	\usepackage{epstopdf}
	\DeclareGraphicsRule{.tif}{png}{.png}{`convert #1 `dirname #1`/`basename #1 .tif`.png}
	\dump

##Opening Other Files with TeXShop（その他のファイルを TeXShop で開く）

［☆］TeXShop can open most files for editing. This facility has been provided so users can read TeX-related files with extensions ".log", ".aux", etc. Files with extensions ".jpg", ".tif", ".eps", or ".pdf" are opened as graphic files.

【★】TeXShop では編集用にたいていのファイルを開くことができます。これにより「.log」や「.aux」などの拡張子が付いた TeX 関連ファイルを読むことができます。 「.jpg」 「.tif」 「.eps」あるいは「.pdf」などの拡張子が付いたファイルはグラフィック・ファイルとして開かれます。

［☆］TeXShop can also open ".dvi" and ".ps" files. In these cases, it converts the file to pdf and displays this pdf file.

【★】TeXShop はまた「.dvi」と「.ps」ファイルを開くこともできます。この場合、ファイルは pdf に変換され、 pdf ファイルが表示されます。

［☆］TeXShop can open ".ins", ".dts", ".sty", ".cls", "mf", ".def", ".fd", ".ltx", ".clo", and "mp" files for processing. It can open any text file.

【★】TeXShop は「.ins」 「.dts」 「.sty」 「.cls」 「mf」 「.def」 「.fd」 「.ltx」 「.clo」それに「mp」形式のファイルを開いて処理することができます。テキストファイルならどのようなものでも開けます。

［☆］It is not a good idea to use TeXShop as a general editor. TeXShop can read files written in UniCode and other formats, but it saves files in the format chosen in Preferences. Consequently, information may be lost if TeXShop is used to edit files which really aren't related to TeX.

【★】TeXShop を一般的なエディタとして使おうというのは、よい考えではありません。 TeXShop では Unicode やその他の形式で書かれたファイルを読み込むことができますが、ファイルの保存は環境設定で選択した形式になります。したがって、 TeX とはまるで関係のないファイルを編集するのに TeXShop を用いると、情報が失われる可能性があります。

##Mathematica（ Mathematica ）

［☆］Mathematica can save images in eps format. These files can be used by either typesetting option; as explained above, they are automatically converted to pdf if typeset with pdflatex.

【★】Mathematica は eps 形式でイメージを保存することができます。このファイルは、いずれのタイプセット方式でも利用できます ； 先に説明したように、 pdflatex でタイプセットを行なえば、自動的に pdf へと変換されます。

［☆］The eps files produced by Mathematica use the Macintosh line feed conventions. Earlier versions of TeXShop and teTeX required that these files be converted to use Unix line feeds before converting them to pdf format, but that is no longer necessary.

【★】Mathematica で作成した eps ファイルでは、 Macintosh の改行コード（ CR ）が用いられます。 TeXShop および teTeX の初期のバージョンでは、 pdf 形式へと変換する前に UNIX の改行コード（ LF ）に変換しておかねばなりませんでしたが、今はもう不要になりました。

##Localizations（各国語版へのローカライズ ）

［☆］TeXShop contains a Dutch localization Maarten Sneep, a French localization by Jerome Laurens, a German localization by Keith J. Schultz, Sascha Beverungen, Martin Kerz, and Max Horn, an Italian localization by Giuseppe Carlino, a Japanese localization by Seiji Zenitani, a Spanish localization by Juan L. Varona, and a Portuguese localization by Paulo T. Abreu. Thanks!

【★】TeXShop には以下のローカライズが含まれます── Maarten Sneep さんによるオランダ語版、 Jérôme Laurens さんによるフランス語版、 Keith J. Schultz さん・ Sascha Beverungen さん・ Martin Kerz さん・ Max Horn さんによるドイツ語版、 Giuseppe Carlino さんによるイタリア語版、銭谷誠司さんによる日本語版、 Juan L. Varona さんによるスペイン語版、そして Paulo T. Abreu さんによるポルトガル語版です。ありがとう！

［☆］In Japan, modified versions of TeX and LaTeX called ptex and platex are sometimes used. TeXShop has been modified by Makoto Inoue, Seiji Zenitani, and Mitsuhiro Shishikura to deal with these versions. See files in the TeXShop distribution folder on my web site. See http://macwiki.sourceforge.jp/cgi-bin/wiki.cgi?TeXShop for further details. Ptex and platex are available at http://www.ascii.co.jp/pb/ptex/. Dvipdfmx is available at http://project.ktug.or.kr/dvipdfmx/. A dvi previewer for Japanese is available at http://macptex.appi.keio.ac.jp/~uchiyama/macptex.html.

【★】日本では、 TeX と LaTeX を修正したバージョン── pTeX と pLaTeX が使われることもあります。これらのバージョンに対応するために TeXShop は、井上真さん、銭谷誠司さん、そして宍倉光広さんによる修正を施しました。私のサイトにある TeXShop ディストリビューションのフォルダ内にあるファイルを見てください。さらに詳しいことについては、http://macwiki.sourceforge.jp/cgi-bin/wiki.cgi?TeXShop を参照してください。 pTeX と pLaTeX は http://www.ascii.co.jp/pb/ptex/ で手に入れられます。 dvipdfm は http://project.ktug.or.kr/dvipdfmx/ にあります。日本語用の dvi プレビューワは http://macptex.appi.keio.ac.jp/~uchiyama/macptex.html にあります。

##Syntax Colors（ソースのカラー表示）

［☆］When syntax coloring turned on in the source window, comments will be colored red, commands will be colored blue, and the symbols $, {, and } will be colored dark green. A few users may wish to change these colors. Each color is determined by setting its red, green, and blue components; these components are real numbers between 0.0 and 1.0. Suppose we wish to change the color of $, {, and } to bright green, a color with components (r, g, b) = (0.0, 1.0, 0.0). To do so, open the Terminal window and type the following commands

【★】ソースウインドウでソースのカラー表示（構文の色分け）が有効になっているときは、コメントは赤、コマンドは青、 「 $ 」 「 { 」 「 } 」といった記号は暗緑色になります。これらの色合いを変更したいユーザもいるかもしれません。それぞれの色は、赤・緑・青（Ｒ・Ｇ・Ｂ）の成分の割合を調整することで決定されています ； 各成分は 0.0 から 1.0 までの実数です。たとえば「 $ 」 「 { 」 「 } 」の色を明るい緑色──成分で言えば (r, g, b) = (0.0, 1.0, 0.0) ──に変えたいとします。そうするには、 Terminal のウインドウを開き、次のようなコマンドを打ち込みます──

	defaults write TeXShop markerred 0.0
	defaults write TeXShop markergreen 1.0
	defaults write TeXShop markerblue 0.0

［☆］The corresponding preference items for comments are commentred, commentgreen, commentblue; the items for commands are commandred, commandgreen, commandblue.

【★】コメントの色を指定する設定項目は commentred ・ commentgreen ・ commentblue です ； コマンドについては commandred ・ commandgreen ・ commandblue です。

##Shell Escape Protection（ Shell-Escape の保護）

［☆］The default commands for pdftex and pdflatex are now "pdftex --shell-escape" and "pdflatex --shell-escape." The "shell-escape" portion of this text tells pdftex that it is legal to run other programs during typesetting. This is useful because if tex finds a graphic file in an unsupported format, it can automatically call another program to convert it to supported format. For example, the default Latex template automatically converts tif files to png and automatically converts eps files to pdf.

【★】pdftex と pdflatex のデフォルトコマンドは「pdftex --shell-escape」と「pdflatex --shell-escape」です。このテキストの「shell-escape」の部分はタイプセット中に pdftex が他のプログラムを実行するのを許可しています。これが有用なのは、もし TeX がサポートしていない形式のグラフィック・ファイルがあった場合に、他のプログラムを呼び出して自動的にサポートしている形式に変換することができるからです。たとえば、デフォルトの LaTeX テンプレートでは tif ファイルを自動的に png に変換し、 eps ファイルを pdf に変換します。

［☆］This creates one difficulty that may worry some users. The "shell-escape" flag allows pdftex to run ANY program. Thus a disgruntled student could send you a tex source file by email and when you typeset it you would discover that some of the files in your directory had been erased.

【★】これによって生じる問題を心配するユーザもいるかもしれません。 「shell-escape」フラグは pdftex がどのようなプログラムを実行することでも許可してしまいます。それゆえ、不満を抱く学生がＥメールで送り付けてきた TeX ソースをタイプセットしたら、あなたのディレクトリにあったファイルが消されてしまっている──といったことも、ないではありません。

［☆］I believe the danger is slight. A source file which did harm would have to be created deliberately, but sending a "virus" via tex source seems somewhat esoteric. Nevertheless, there are two ways that you can protect yourself. The first and easiest is to remove the letters "--shell-escape" from the two spots they occur in Preferences and then convert all of your graphic files by hand.

【★】その危険性は軽微なものだ──と私は思います。害を為すソースファイルは意図的に作成しなければならないでしょうが、 TeX ソースを通じて「ウィルス」を送り付けるというのは、いささか難儀なことに思われます。それはともかく、ユーザが自身を守るための方法が２つあります。最初にして最も簡単な方法は、環境設定内の２箇所にある「--shell-escape」という文字列を削除してしまい、グラフィック・ファイルの変換をすべて手動で行なうことです。

［☆］TeXShop now provides a different protection. A preference item under the Engine tab is labeled "Shell Escape Warning." This item is off when TeXShop is delivered. If the item is on and "shell-escape" is active, then the first time a file is typeset during a TeXShop session, a warning dialog will appear allowing you to turn shell-escape off for that particular file. This dialog will not appear again during the session for that particular file. Thus you can typeset your own files using "shell-escape" and typeset files received in the mail without "shell-escape."

【★】TeXShop では、それとは異なる保護も提供しています。環境設定パネルの「内部設定」タブにある「Shell Escape を警告」がそれです。この項目は当初はオフになっています。これをオンにし「shell-escape」が有効になっていれば、あるファイルを TeXShop で初めてタイプセットするときに、その特定のファイルに対して shell-escape をオフにすることができる警告ダイアログが現われます。このダイアログは、 TeXShop の起動中には、その特定のファイルに対してくりかえし表示されることはありません。なので、ユーザ自身のファイルは「shell-escape」を使ってタイプセットでき、メールで受け取ったファイルは「shell-escape」を用いずにタイプセットできます。

##Colored Text in TeX（ TeX における文字の色指定）

［☆］It has always been possible to color TeX output. To do so, add the line

【★】TeX の出力をカラー化することができます。そうするには、プリアンブルに次の１行を加えます──

	\usepackage{color}

［☆］to the preamble, and insert a line like

【★】そして、タイプセットを始める前に次のような１行を挿入します──

	\color{blue}

［☆］before typesetting begins. To color a limited section of text, use a command like

【★】テキストの特定の部分に色を付けたいときは、コマンドを次のように使います──

	{\color{red} This is very important!}
	{\color{red} これはとても重要だ！}

［☆］To define custom colors, use a command like

【★】カスタム・カラーを定義するには、次のようなコマンドを使います──

	\definecolor{mycolor}{rgb}{0.2, 0.7, 0.8}

［☆］Users may be familiar with a list of defined colors with names like "BrickRed"; these named colors were defined automatically for the dvips driver. To use them generally, use the syntax

【★】あるいはユーザは、 "BrickRed" のように名前で定義された色見本になじんでいるかもしれません； 名前付きの色は dvips ドライバ用に事前に定義されているものです。 こうした色を使うには一般に次のような構文を用います──

	\usepackage[dvipsnames,usenames]{color}

［☆］When output is colored, the output may be difficult to read on the preview screen. TeXShop has hidden preferences to set the background color of the preview window. This background color will not appear when the document is printed. To set the background to gray, issue the following commands in Terminal:

【★】出力をカラーにした場合、プレビューウインドウで判読しにくくなるかもしれません。 TeXShop には、プレビューウインドウの背景色を変えられる隠れた環境設定があります。この背景色は、文書を印刷するときには現われません。背景を灰色にするには、 Terminal から次のようなコマンドを送ります：

	defaults write TeXShop Pdfbackground_R 0.5
	defaults write TeXShop Pdfbackground_G 0.5
	defaults write TeXShop Pdfbackground_B 0.5

［☆］Change 0.5 to 1 to get back to white. If you find yourself changing the background often, create an Applescript macro named "PDF background gray" with the Macro Editor using the following text:

【★】白に戻すには 0.5 を１に変えます。もし頻繁に背景を変えるようなら、 「PDF background gray」という名前で AppleScript マクロをこしらえておきます──マクロエディタを使って以下のテキストを入れます：

	--AppleScript
	do shell script "defaults write TeXShop Pdfbackground_R 0.5"
	do shell script "defaults write TeXShop Pdfbackground_G 0.5"
	do shell script "defaults write TeXShop Pdfbackground_B 0.5"

［☆］and create a similar macro named "PDF background white".

【★】同様に「PDF background white」という名前のマクロもこしらえておきます。

##More About teTeX（ teTeX についてさらに）

［☆］teTeX is installed in the directory /usr/local/teTeX, which is not visible from the Finder. But the installer creates a symbolic link to this directory in /Library/teTeX. Therefore, go to /Library/teTeX to inspect files in teTeX.

【★】teTeX は /usr/local/teTeX というディレクトリにインストールされますが、ファインダからは見ることができません。けれどもインストーラは、このディレクトリのシンボリック・リンクを /Library/teTeX に作ります。なので teTeXの ファイルを調べるには /Library/teTeX に行きます。

［☆］The documentation for teTeX is in /Library/teTeX/share/texmf/doc/tetex. In particular, examine the files

【★】teTeX についてのドキュメント類は /Library/teTeX/share/texmf/doc/tetex にあります。特に、次のファイルを調べてみてください──

* TETEXDOC.pdf
* teTeX-FAQ

［☆］Additional documentation for Gerben Wierda's Mac OS X compilation is in

【★】Gerben Wierda さんによる Mac OS X への移植についての追加のドキュメント類は次の場所にあります──

	/Library/teTeX/README.macosx

［☆］It is possible to store additional style files, fonts, etc., in teTeX itself. But teTeX is owned by root and lives in /usr/local/teTeX, which isn't visible in the Finder. Moreover, it is a good idea to keep this directory pure so it can be upgraded easily when later versions are released. It is better to construct a mirror image of the teTeX directory structure inside your Library folder and store your personal files there.

【★】追加のクラスファイルやフォントなどを teTeX そのものに格納しておくことができます。けれども teTeX は所有者がルート・ユーザになっており、/usr/local/teTeX にあるのでファインダからは見ることができません。さらに言えば、このディレクトリはいじらずにおくほうがいいでしょう──後に新しいバージョンがリリースされたときにアップグレードが簡単にできますから。 teTeX のディレクトリ構造とまったく同じ物をユーザのライブラリ・フォルダに作り、そこに個人的なファイルを入れておくのがよいでしょう。

［☆］The files must be in appropriate directories. teTeX uses a directory structure invented by the TeX working group. Suppose you want to add a extra style file named new.sty to the style files used by LaTeX. Look inside teTeX and notice that a natural spot for this file would be

【★】ファイルは適切なディレクトリに置いてやらねばなりません。 teTeX は TeX ワーキンググループの考案したディレクトリ構造を用いています。 new.sty という名前の特別なスタイルファイルを、 LaTeX で使えるように追加したいとします。 teTeX の中を見ると、このファイルを収める自然な場所は以下のようだとわかることでしょう──

	/usr/local/teTeX/share/texmf/tex/latex/misc/

［☆］So inside your home directory's Library folder, make a series of subdirectories as follows:

【★】ということで、ホーム・ディレクトリのライブラリ・フォルダ内に、次のような一連のサブディレクトリを作成してください：

	Library --> texmf --> tex --> latex --> misc

［☆］and store "new.sty" inside this misc directory.

【★】そのうえで「new.sty」をこの misc ディレクトリに格納します。

##Coexisting with Fink（ Fink との共存）

［☆］Mac OS X can also run X-windows applications using free third party software. These applications run side by side with regular Mac OS X programs. Fink is a system which can download and compile these applications on Mac OS X. For details, see http://fink.sourceforge.net. In particular, Fink can install ghostview, xdvi, and xemacs.

【★】Mac OS X では、サードパーティ製のフリーソフトウェアを使うことで、 X-window アプリケーション（＝Ｘアプリケーション）を実行させることもできます（訳注：現在では Apple 純正の X11 があります）。Ｘアプリケーションは通常の Mac OS X プログラムと並行して実行されます。 Fink は Mac OS X 上でＸアプリケーションをダウンロードしてコンパイルすることができます。詳しいことについては http://fink.sourceforge.net を参照してください。 Fink ではとりわけ ghostview ・ xdvi それに xemacs をインストールすることができます。

［☆］Fink installs software in /sw/bin. One of the packages Fink can install is teTeX. In the past this caused problems because users had duplicate copies of teTeX, configured one of the copies, and then found that the configuration did not affect the other copy. The latest version of Fink gives the option of using Gerben Wierda's teTeX with symbolic links in /sw/bin rather than installing a second copy. We recommend that you choose that option.

【★】Fink はソフトウェアを /sw/bin にインストールします。 Fink によってインストールできるパッケージのひとつが teTeX です。このことで過去に問題が起きました──ユーザが teTeX の重複したコピーを持っており、コピーのひとつで設定を行ない、しばらくしてもう一方のコピーには設定が反映されていないことに気付いたのです。 Fink の最新のバージョンでは、２つめのコピーをインストールしないようにし、/sw/bin 内にシンボリック・リンクを作成することで Gerben Wierda の teTeX を使用するオプションがあります。このオプションを選択することをお勧めします。

##Coexisting with Other TeX Distributions（他の TeX ディストリビューションとの共存）

［☆］Problems may arise when multiple TeX distributions are available on a system, especially if they set environment variables. This may lead to hard to detect problems where other files are used than the ones you expect.

【★】ひとつのシステム上で複数の TeX ディストリビューションが利用可能になっていると、問題が起こるかもしれません──ことに環境変数が設定されている場合には。このことは、期せずして使用されているファイルに存する問題を見つけ出すのを難しくする可能性があります。

##ConTeXt and MetaPost（ ConTeXt と MetaPost ）

［☆］ConTeXt is a general purpose TeX macro package by Hans Hagen; for some, it will be a serious alternative to LaTeX. See http://www.pragma-ade.com/ for details.

【★】ConTeXt は Hans Hagen の作成した汎用的な TeX マクロパッケージです ； 人によってはこれは、 LaTeX に取って代わるものでしょう。詳しくは http://www.pragma-ade.com/ を参照してください。

［☆］MetaPost is a MetaFont like system by John Hobby which can output postscript and pdf files. The package can be used to draw elaborate postscript illustrations. See http://cm.bell-labs.com/who/hobby/MetaPost.html for more details. Interesting metapost examples can be found at many web sites; for instance see http://www.cs.ucc.ie/~dongen/mpost/mpost.html. TeXShop now supports MetaPost.

【★】MetaPost は MetaFont に類似したシステムで、 John Hobby さんにより作成されましたが、ポストスクリプトと pdf のファイルを出力できます。このパッケージは精巧なポストスクリプトのイラストを描くのに使えます。詳しいことについては http://cm.bell-labs.com/who/hobby/MetaPost.html を参照してください。 MetaPost を使ったおもしろい作例はあちこちのサイトで見つけられます ； たとえば http://www.cs.ucc.ie/~dongen/mpost/mpost.html をご覧ください。 TeXShop は MetaPost をサポートしています。

［☆］Here is a sample MetaPost file:

【★】ここに MetaPost ファイルのサンプルがあります：

	prologues:=2;
	color yellow; yellow = green + red;
	
	def star (expr size, n, pos, color)=
	for a=0 step 360/n until 360:
	draw (origin -- (size/2,0))
	rotatedaround (origin, a)
	shifted pos withcolor color;
	endfor ;
	enddef;
	
	beginfig(1);
	pickup pencircle scaled 2mm; star (2cm,5,origin,red);
	endfig;
	
	beginfig(2);
	pickup pencircle scaled 2mm; star (2cm,7,origin,yellow);
	endfig;
	
	beginfig(3);
	pickup pencircle scaled 2mm; star (2cm,11,origin,green);
	endfig;
	
	beginfig(4);
	pickup pencircle scaled 2mm; star (2cm,13,origin,blue);
	endfig;
	
	end

［☆］Suppose this file is named "metademo.mp." When the file is processed by MetaPost, it will generate four different postscript files, named metademo.1, metademo.2, metademo.3, metademo.4. These names are determined by the number parameter of "beginfig()." If this number is nonnegative, like beginfig(0) or beginfig(10), the resulting file will be named metademo.0 or metademo.10. If this number is negative, like beginfig(-10), the resulting file will be named metademo.ps, overwriting any earlier metademo.ps file created by the source.

【★】このファイルの名前を「metademo.mp」とします。これを MetaPost で処理すると、 metademo.1, metademo.2, metademo.3, metademo.4 という４つの異なるポストスクリプト・ファイルが生成されます。ファイル名は「beginfig()」という番号パラメータで決定されています。この番号が beginfig(0) あるいは beginfig(10) というように負ではない整数（自然数）なら、結果として生じるファイルの名前は metademo.0 あるいは metademo.10 となります。もしこの番号が beginfig(-10) のように負の数だった場合には、生成されるファイルの名前は metademo.ps となり、それ以前にソースから作られていたすべての metademo.ps ファイルを上書きします。

［☆］In its default configuration, TeXShop assumes that one of the numbers is zero. TeXShop calls the script pstopdf, which runs MetaPost and thus creates all of these postscript files. The script then converts each postscript file to a pdf file. Finally, the script renames the zeroth pdf file to the name of the source with extension "pdf", for instance metademo.pdf and displays this figure in the preview screen.

【★】このデフォルトの設定で、番号のひとつがゼロになっていると仮定します。 TeXShop はスクリプト pstopdf を呼び出します── MetaPost が実行されたことで全番号分のポストスクリプト・ファイルが作られています。スクリプトは各ポストスクリプト・ファイルを、それぞれに pdf ファイルに変換します。最後に、ゼロ番目の pdf ファイルの名前を、ソースの名前に拡張子「pdf」を付けたもの（この例では metademo.pdf ）に変え、この図をプレビュー画面に表示します。

［☆］When you are editing a MetaPost file, change the number of the figure being edited from positive to zero. TeXShop will then display this figure as it is being debugged. When you are satisfied with this figure, change its number back to positive and change the number of another figure from positive to zero.

【★】MetaPost ファイルを編集しているときに、編集中の図の番号を正の数からゼロに変えてみてください。 TeXShop はこの図をデバッグ中のものとして表示します。この図が満足のゆくものになったら、番号を正の数に戻し、他の図の番号を正の数からゼロに変えます。

［☆］Once MetaPost files have been created, then can be displayed like any other illustration. Pdflatex can be used if the illustrations are converted to pdf form, or TeX and Ghostscript can be used to include the postscript illustrations without conversion. For example, the four illustrations created by the above MetaPost file can be displayed by typesetting the following file with TeX and Ghostscript:

【★】いったん MetaPost ファイルが作られれば、他のイラストと同様に表示できます。イラストが pdf 形式に変換されていれば pdflatex で扱えますし、 TeX＋Ghostscript ならポストスクリプトのイラストを変換なしで扱えます。たとえば、上記の MetaPost ファイルから作られた４つのイラストは、次のようなファイルを TeX＋Ghostscript でタイプセットすることで表示できます：

	\documentclass[11pt] {article}
	\usepackage{graphicx}
	\begin{document}
	Here are some illustrations.
	\vspace{.2in}
	\includegraphics[width=1cm]{metademo.1}
	\hfill
	\includegraphics[width=1cm]{metademo.2}
	\hfill
	\includegraphics[width=1cm]{metademo.3}
	\hfill
	\includegraphics[width=1cm]{metademo.4}
	\hfill
	\end{document}

［☆］It is also possible to embed MetaPost source code directly in a Latex document using the package mfpic. When this method is used, the MetaPost preference should be set to "mpost" rather than "mptopdf" in the Preferences dialog so MetaPost will run directly when the MetaPost engine is selected. A document containing MetaPost source code is first typeset with pdflatex or latex, creating a mp source file with all of the document's illustrations. This file is then compiled with MetaPost. Finally, the document is typeset again with pdflatex or latex to show the resulting illustrations.

【★】mfpic パッケージを使うことで、 MetaPost のソースコードを LaTeX 文書に直接埋め込むこともできます。この方法を用いる際には、環境設定ダイアログで、 MetaPost の設定を「mptopdf」ではなく「mpost」にしておきます──このように MetaPost エンジンが選択されていると MetaPost が直接実行されます。 MetaPost のソースコードを含む文書は、最初に pdflatex ないしは latex でタイプセットし、文書にあるすべてのイラストをひとまとめにした mp ソースファイルを作成します。そしてこのファイルを MetaPost でコンパイルします。最後に、文書を再度 pdflatex または latex でタイプセットしてイラストを表示します。

［☆］Below is an example created by Claus Gerhardt. Save this example as "MetaPostTest". Notice the line "\opengraphsfile{MetaPostTest}" in the source. Although the mfpic package permits any name for this graph file, its name must be the same as the document name to use the following procedure in TeXShop. Typeset the document once, switch to MetaPost and typeset again, switch back to LaTeX and typeset a final time. In this process, either pdflatex or latex + ghostscript can be used for the first and third steps.

【★】下にあるのは Claus Gerhardt による作例です。この例を「MetaPostTest」として保存します。ソース内の「\opengraphsfile{MetaPostTest}」と書かれた行に注目してください。 mfpic パッケージはこのグラフィック・ファイルがどのような名前であってもかまわないとはいえ、 TeXShop で次のような手順を踏むにあたっては、文書と同じ名前でなければなりません。いったん文書をタイプセットしたら、 MetaPost に切り替えて再度タイプセットを行ない、もう一度 LaTeX に戻して最終的にタイプセットします。この過程において、１番目と３番目のステップでは、 pdflatex または latex＋ghostscript のいずれを用いてもかまいません。

	* 補足：作例のソースコードは割愛しました。ヘルプファイルには載っています。

［☆］The following example, also provided by Claus Gerhardt, shows the power of MetaPost.

【★】下の例もまた Claus Gerhardt さんの提供によるもので、 MetaPost の威力を示しています。

	* 補足：このソースコードについてもここで載せるにはいささか長いので割愛しました。ヘルプファイルには載っています。

##Plist Files（ Plist ファイル）

［☆］Mac OS X makes extensive use of xml files; xml is a structured language closely related to html.

【★】Mac OS X は xml ファイルを広汎に利用しています ； xml は html と密接な関連のある構造化言語です。

［☆］TeXShop uses five xml files for configuration: completion.plist, autocompletion.plist, KeyEquivalents.plist, Macros_Latex.plist, and Macros_Context.plist. These files reside inside your personal library in a folder called ~/Library/TeXShop created when TeXShop first runs. If you have modified the default TeXShop configuration and want to move TeXShop to another machine preserving your modifications, copy ~/Library/TeXShop to the new machine.

【★】TeXShop では５つの xml ファイルを設定のために用いています： completion.plist ・ autocompletion.plist ・ KeyEquivalents.plist ・ Macros_Latex.plist それに Macros_Context.plist です。これらのファイルはユーザ個人のライブラリ内にある ~/Library/TeXShop というフォルダ内に置かれています──このフォルダは TeXShop が初めて起動した際に作られます。もし TeXShop のデフォルト設定をいじっており、それをそのまま他のマシンに移行させたいのであれば、 ~/Library/TeXShop をコピーしてください。

［☆］The files are used to configure the Latex Panel, Auto Completion, the Keyboard Menu Shortcuts, and the Macro menu. Details are given elsewhere in this document.

【★】ファイルは、 LaTeX パネル、オートコンプリート、メニュー項目のショートカットキー、マクロメニューなどの設定に利用されています。詳細についてはこのドキュメントの別の場所で述べてあります。

［☆］Files of type plist are ordinary text files, so they can be opened and edited with TeXShop, TextEdit, or other text editors. Editing the file is straightforward, but somewhat tedious.

【★】plist 形式のファイルはごく普通のテキストファイルなので、 TeXShop や TextEdit ないしは他のテキストエディタで開いたり編集したりできます。ファイルを編集するのは簡単ですが、いくぶん退屈です。

［☆］If a plist file contains unicode characters, it needs to be edited and saved in UTF-8 format. Before opening such a file in TeXShop, change the TeXShop encoding preference to UTF-8. Then edit and save the file. Then change the encoding preference back to the original value. The default value is MacOSRoman if you did not reset it earlier.

【★】もし plist ファイルに Unicode 文字が含まれているなら、 UTF-8 形式で編集し保存する必要があります。 TeXShop でそうしたファイルを開く前に、 TeXShop のエンコーディング設定を UTF-8 に変更してください。そのうえでファイルを編集したり保存したりします。その後エンコーディング設定は元に戻しておきます。もし以前に設定しなおしていないなら、デフォルトでは MacOSRoman です。

［☆］If you installed the Developer distribution of Mac OS X and you double click a .plist file, it will open in a program named Property List Editor. This program is useful for editing plist files, but it is buggy and does not display all file information. In particular, comments are missing. It is better to use TeXShop.

【★】Mac OS X の Developer Tools をインストールしているのであれば、.plist ファイルをダブルクリックすると、 Property List Editor というプログラムで開かれると思います。このプログラムは plist ファイルを編集するのに便利ですが、バグだらけですし、ファイルのすべての情報を表示できません。ことに、コメントが欠けてしまいます。 TeXShop を使うほうがいいでしょう。

##Redefining Keyboard Menu Shortcuts（メニュー項目のショートカットキーを再定義する）

［☆］It is possible to redefine all keyboard menu shortcuts used by TeXShop. To do so, open the file ~/Library/TeXShop/Menus/KeyEquivalents.plist with TeXShop, read the comments at the top of the file, and edit the file to redefine selected menu shortcuts. Be sure to edit and save in UTF-8 format if you use Unicode characters.

【★】TeXShop で使われているメニュー項目のすべてのショートカットキーは再定義することができます。 ~/Library/TeXShop/Menus/KeyEquivalents.plist というファイルを TeXShop で開き、ファイルの冒頭にあるコメントを読んだうえでファイルを編集し、メニュー項目のショートカットを再定義します。 Unicode 文字を使用するのであれば、かならず UTF-8 形式で編集し保存するようにしてください。

----
[もくじ](README.md)
