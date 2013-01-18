%==============================================================================
% dinfunisc - classe de documento com padr�es do DINF/UNISC
% baseado no padrao iiufrgs - classe de documento com padr�es do II/UFRGS
% $Id: dinfunisc.cls,v 1.0.1 2006/03/02 19:12:24 aguiar $
% $Id: iiufrgs.cls,v 4.17 2005/01/14 19:12:24 avila Exp $
%
% Copyright (C) 2006 TeX Users Group of University of Santa Cruz - TUGUSC
% Copyright (C) 2001-2005 UFRGS TeX Users Group
%
% This program is free software; you can redistribute it and/or modify
% it under the terms of the GNU General Public License as published by
% the Free Software Foundation; either version 2 of the License, or
% (at your option) any later version.
%
% This program is distributed in the hope that it will be useful,
% but WITHOUT ANY WARRANTY; without even the implied warranty of
% MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
% GNU General Public License for more details.
%
% You should have received a copy of the GNU General Public License
% along with this program; if not, write to the Free Software
% Foundation, Inc., 59 Temple Place, Suite 330, Boston, MA  02111-1307  USA
%
% UFRGS TeX Users Group
% Institute of Informatics --- UFRGS
% Porto Alegre, Brazil
% http://www.inf.ufrgs.br/utug
% Discussion list: utug-l@inf.ufrgs.br
%
%
% TeX Users Group of University of Santa Cruz
% Department of Informatics --- UNISC
% Santa Cruz do Sul,RS - Brazil
% http://menhis.unisc.br/tugusc
% Discussion list: tugusc@yahoogrupos.com.br
%==============================================================================

%==============================================================================
% Identifica��o
%==============================================================================
\NeedsTeXFormat{LaTeX2e}
\ProvidesClass{dinfunisc-propostatc}[2006/04/02 v1.0.2 Formatacao de documentos para o DINF/UNISC]
%==============================================================================
% Declara��o de op��es
%==============================================================================
\newcommand{\iiu@novodoc}[1]{\DeclareOption{#1}{\AtEndOfClass{\input{#1.def}}}}
\iiu@novodoc{tc} %por enquanto, so temos modelo para trabalhos de conclusao.
\DeclareOption{english}{\@englishtrue\OptionNotUsed}\newif\if@english
\DeclareOption{oneside}{\AtEndOfClass{\@twosidefalse}\OptionNotUsed}
\DeclareOption*{\PassOptionsToClass{\CurrentOption}{report}}
\ProcessOptions\relax

%==============================================================================
% Heran�a da classe `report' e inclus�o de pacotes e arquivos necess�rios
%==============================================================================
\LoadClass[12pt,a4paper,twoside,ifthen]{report}
\RequirePackage[english,brazilian]{babel}
\input{brazilian.babel}
\input{english.babel}
\if@english
        \selectlanguage{english}
        \AtBeginDocument{\selectlanguage{english}}
\fi
\RequirePackage{lastpage}
\RequirePackage{indentfirst}
\RequirePackage{iidefs}
\RequirePackage{natbib}
\RequirePackage{chngcntr} %modifica contadores da classe report
\RequirePackage{setspace} %seta espa�o entre as linhas 

%==============================================================================
% Margens do texto
%==============================================================================
\newlength{\ii@topmargin}\setlength{\ii@topmargin}{27mm}
\newlength{\ii@pagenummargin}\setlength{\ii@pagenummargin}{20mm}
\newlength{\ii@bottommargin}\setlength{\ii@bottommargin}{20mm}
%\newlength{\ii@sidemargin}\setlength{\ii@sidemargin}{25mm}
\newlength{\ii@leftmargin}\setlength{\ii@leftmargin}{30mm}
\newlength{\ii@rightmargin}\setlength{\ii@rightmargin}{25mm}
\setlength{\marginparwidth}{25mm}

% ajuste das medidas verticais
\setlength{\topmargin}{\ii@pagenummargin}
        \addtolength{\topmargin}{-0cm} % isto � +- a altura do n�m. da p�gina
        \addtolength{\topmargin}{-1in}
\setlength{\headheight}{1em}
\setlength{\headsep}{\ii@topmargin}
        \addtolength{\headsep}{-\ii@pagenummargin}
\setlength{\textheight}{\paperheight}
        \addtolength{\textheight}{-\ii@topmargin}
        \addtolength{\textheight}{-\ii@bottommargin}
\setlength{\footskip}{\ii@bottommargin}

% ajuste das medidas horizontais
\setlength{\oddsidemargin}{\ii@leftmargin}
        \addtolength{\oddsidemargin}{-1in}
\setlength{\evensidemargin}{\oddsidemargin}
\setlength{\textwidth}{\paperwidth}
        \addtolength{\textwidth}{-2\ii@rightmargin}
%\setlength{\marginparsep}{\ii@sidemargin}
 %       \addtolength{\marginparsep}{-\marginparwidth}
%        \setlength{\marginparsep}{.5\marginparsep}

%Redefine the first level of enumerate
\renewcommand{\theenumi}{\Roman{enumi}}
\renewcommand{\labelenumi}{\parindent=1cm\theenumi.}

%==============================================================================
% Numera��o das p�ginas
%==============================================================================
\def\ps@iiufrgs{
        \let\@oddfoot\@empty
        \let\@evenfoot\@empty
        %\def\@evenhead{\hspace*{\fill}{\small\thepage}}
        \def\@evenhead{\hspace*{8cm}{\small\thepage}}
        %\def\@oddhead{\hspace*{\fill}{\small\thepage}}
        \def\@oddhead{\hspace*{8cm}{\small\thepage}}
}
\pagestyle{empty}
\let\ps@plain\ps@empty
%==============================================================================
% Defini��o de autor(es), orientador e co-orientador
%==============================================================================
\newcounter{ii@authorcount}
\renewcommand{\author}[2]{
        \addtocounter{ii@authorcount}{1}
        \expandafter\gdef\csname @author\alph{ii@authorcount}last\endcsname{#1}
        \expandafter\gdef\csname @author\alph{ii@authorcount}first\endcsname{#2}
        \expandafter\gdef\csname @author\alph{ii@authorcount}\endcsname{#2 #1}
}
\DeclareRobustCommand{\advisor}[3][]{
        \gdef\@advisorlast{#2}
        \gdef\@advisorfirst{#3}
        \gdef\@advisor{#1~#3 #2}
        \gdef\@advisornamethis{\advisorname}
}
\DeclareRobustCommand{\advisorF}[3][]{
        \gdef\@advisorlast{#2}
        \gdef\@advisorfirst{#3}
        \gdef\@advisor{#1~#3 #2}
        \gdef\@advisornamethis{\advisornamef}
}
\DeclareRobustCommand{\coadvisor}[3][]{
        \gdef\@coadvisorlast{#2}
        \gdef\@coadvisorfirst{#3}
        \gdef\@coadvisor{#1~#3 #2}
        \gdef\@coadvisornamethis{\coadvisorname}
}
\DeclareRobustCommand{\coadvisorF}[3][]{
        \gdef\@coadvisorlast{#2}
        \gdef\@coadvisorfirst{#3}
        \gdef\@coadvisor{#1~#3 #2}
        \gdef\@coadvisornamethis{\coadvisornamef}
}
\newcounter{ii@reviewercount}
\DeclareRobustCommand{\reviewer}[3][]{
				\addtocounter{ii@reviewercount}{1}
        \expandafter\gdef\csname @reviewer\alph{ii@reviewercount}last\endcsname{#1}
        \expandafter\gdef\csname @reviewer\alph{ii@reviewercount}first\endcsname{#2}
        \expandafter\gdef\csname @reviewer\alph{ii@reviewercount}\endcsname{#2 #1}
        \expandafter\gdef\csname @reviewernamethis\alph{ii@reviewercount}\endcsname{\reviewername}
}
\DeclareRobustCommand{\reviewerF}[3][]{
				\addtocounter{ii@reviewercount}{1}
        \expandafter\gdef\csname @reviewer\alph{ii@reviewercount}last\endcsname{#1}
        \expandafter\gdef\csname @reviewer\alph{ii@reviewercount}first\endcsname{#2}
        \expandafter\gdef\csname @reviewer\alph{ii@reviewercount}\endcsname{#2 #1}
        \expandafter\gdef\csname @reviewernamethis\alph{ii@reviewercount}\endcsname{\reviewernamef}
}

%==============================================================================
% Defini��o do Departamento relacionado ao documento
% deve ser definido como `ina' ou `int'
%==============================================================================
\newcommand{\dept}[1]{\gdef\@dept{#1}}


%==============================================================================
% Redefini��o da data (para ter m�s e ano separados)
%==============================================================================
%\renewcommand{\date}[2]{
%        \gdef\@publmonth{#1}
%        \gdef\@publyear{#2}
%}
%\date{\monthname}{\number\year}
\renewcommand{\date}[3]{
				\gdef\@publday{#1}
        \gdef\@publmonth{#2}
        \gdef\@publyear{#3}
}
\date{\number\day}{\monthname}{\number\year}

%==============================================================================
% Defini��o padr�o da folha de rosto.
% Os dados espec�ficos do tipo de trabalho (disserta��o, tese, etc.) s�o
% informados definindo-se o comando \titlepagespecificinfo. Veja os
% arquivos .def inclu�dos com a classe.
%==============================================================================
\newlength{\titlepagewinwidth}\setlength{\titlepagewinwidth}{160mm}
\newlength{\titlepagewinheight}\setlength{\titlepagewinheight}{110mm}
\newlength{\titlepagewinvoffset}\setlength{\titlepagewinvoffset}{20mm}
\newcommand{\location}[2]{
        \gdef\@city{#1}
        \gdef\@state{#2}
}
\location{Porto~Alegre}{RS}
\renewcommand{\maketitle}{%
        \begin{titlepage}
                \thetitlepage
        \end{titlepage}%
        \clearpage
        \setcounter{page}{2}%
        
        \@ifundefined{@coadvisor}{}{
        				\begin{titlepage}
                \thetitlepage
       					\end{titlepage}%
        				\clearpage
        }%
        
        \@ifundefined{@reviewera}{}{
        				\begin{titlepage}
        						\gdef\@reviewer{\@reviewera}
        						\gdef\@reviewernamethis{\@reviewernamethisa}
                		\thetitlepage
        				\end{titlepage}%
        				\clearpage
        }%
       
        \@ifundefined{@reviewerb}{}{
        				\begin{titlepage}
        				  	\gdef\@reviewer{\@reviewerb}
        				  	\gdef\@reviewernamethis{\@reviewernamethisb}
                		\thetitlepage
        				\end{titlepage}%
        				\clearpage
        }%
        
        \@ifundefined{@reviewerc}{}{
        				\begin{titlepage}
        				  	\gdef\@reviewer{\@reviewerc}
        				  	\gdef\@reviewernamethis{\@reviewernamethisc}
                		\thetitlepage
        				\end{titlepage}%
        				\clearpage
        }%
}
\newcommand{\thetitlepage}{%
        \noindent\@topbox\\
        \vfill
        \vfill
        \@ifundefined{@advisor}{}{
								\begin{center}
									\titlepageadvisorinfo
								\end{center}
								%\vfill
                %\@ifundefined{@reviewerb}{\vfill}{}%
                
        }
        \centerline{\@city, \ii@date}
}
\def\@topbox{%
        \parbox[t]{\textwidth}{%
                \centering%
                \vbox to \titlepagewinvoffset{%
                        \titlepagetopinfo\vfill\setstretch{1.5}\@winbox
                }
        }
}
\def\@winbox{%
%       \fbox{
        \parbox[b]{\titlepagewinwidth}{%
        \centering\vbox to \titlepagewinheight{%
                %\vspace*{\fill}
                %\@ifundefined{@reviewerb}{\vspace*{\fill}}{\vspace*{4cm}}%  
                \vspace*{6cm}
                \vspace{\stretch{3}}
                {\textbf{\MakeUppercase{\@title}}\par}
                \temppropname\\
                %\@ifundefined{@reviewerb}{\vspace*{\fill}}{\vspace*{1cm}}%                
                \vspace*{1cm}
                \byname\\
                %\@ifundefined{@reviewerb}{\vspace*{\fill}}{\vspace*{1cm}}%                
                \vspace*{1cm}
                \@authora\\
                \@ifundefined{@authorb}{}{\MakeUppercase{\@authorb}\\}%
                \@ifundefined{@authorc}{}{\MakeUppercase{\@authorc}\\}%
                \@ifundefined{@authord}{}{\MakeUppercase{\@authord}\\}%
                %\@ifundefined{@reviewerb}{\vspace*{\fill}}{\vspace*{0.5cm}}%                
                \vspace*{1cm}
                \proptcspecificinfo\\
                \vspace*{1cm}
                %\@ifundefined{@reviewer}{\vspace*{\fill}}{\vspace*{1cm}}%   
                %\vspace*{-2cm}
        }}%
%       }%
}
\newcommand{\course}[1]{\gdef\@course{#1}}
\course{\cgec}
\newcommand{\titlepagetopinfo}{%
        \MakeUppercase{\ufrgs}\\
        \MakeUppercase{\ii}\\
        \@ifundefined{@dept}{}{\MakeUppercase{\csname dept\@dept\endcsname}\\}%
        \MakeUppercase{\@course}\\
}
\newcommand{\titlepageadvisorinfo}{%
\@ifundefined{@reviewer}{\vspace*{9cm}}{\vspace*{8cm}}
        \@ifundefined{@advisor}{}{\@advisor\\\@advisornamethis\\}
        \@ifundefined{@coadvisor}{}{\vspace*{1cm}\@coadvisor\\\@coadvisornamethis\\}
        \vspace*{1cm}
        %\vspace*{\fill}
        \@ifundefined{@reviewer}{}{\@reviewer\\\@reviewernamethis\\\vspace*{1cm}}
        %\@ifundefined{@reviewerb}{}{
%        		\@reviewerb\\\reviewername\\\vspace*{1cm}
%        		\@ifundefined{@reviewerc}{\vspace*{1cm}}{\@reviewerc\\\reviewername\\\vspace*{1cm}}
%        }
				\vspace*{\fill}
}
%==============================================================================
% Defini��o da pagina de assinaturas.
%==============================================================================
\newcommand{\makesignature}{%       
\begin{flushright}
\@city, \ii@dateday
\vspace*{2cm}\\
{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}\\
\@authora
\vspace*{2cm}\\
{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}\\
\@advisor
\@ifundefined{@coadvisor}{}{
\vspace*{2cm}\\
{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}{\_}\\
\@coadvisor
}
\end{flushright}
}

%==============================================================================
% Formata��o dos cap�tulos.
% Os comandos \@chapter e \@schapter s�o redefinidos para que a
% numera��o de p�ginas seja correta (deve aparecer somente a partir do
% primeiro cap�tulo do texto, mas n�o nas p�ginas iniciais de
% cap�tulos).
% Os comandos \@makechapterhead e \@makeschapterhead fazem a
% formata��o dos t�tulos propriamente ditos.
%==============================================================================
\newcommand{\ii@chapterfont}{\@setfontsize\Large{12}{20}}
\def\@chapapp{}
\def\@chapter[#1]#2{% 
\setstretch{1.5} %espa�amento entre linhas
				\par
        \refstepcounter{chapter}%
        \addcontentsline{toc}{chapter}{\protect\numberline{\@chapapp\thechapter}#1}%
        %\addtocontents{lof}{\protect\addvspace{10\p@}}%
        \addtocontents{lof}{\protect}%
        %\addtocontents{lot}{\protect\addvspace{10\p@}}%
        \addtocontents{lot}{\protect}%
        \pagestyle{iiufrgs}\let\ps@plain\ps@iiufrgs%
				\@makechapterhead{#2}\@afterheading\let\@afterindentfalse\@afterindenttrue
\@afterindenttrue\parindent=1cm\setlength{\parskip}{12pt plus 0pt minus 0pt}
}

\def\@makechapterhead#1{%
        \vspace*{15mm} 
\reset@font{\ii@chapterfont\begin{center}\textbf{\@chapapp\hspace{0.8em}\MakeUppercase{#1}}\end{center}\par}
        \addvspace{1cm}
}
\def\@schapter#1{%
        \if@aftertoc\addcontentsline{toc}{chapter}{#1}\fi%
        \addtocontents{lof}{\protect\addvspace{10\p@}}%
        \addtocontents{lot}{\protect\addvspace{10\p@}}%
        \@makeschapterhead{#1}\@afterheading\parindent=1cm\setlength{\parskip}{6pt plus 0pt minus 0pt}
}
\def\@makeschapterhead#1{%
        %\vspace*{1pt}\sffamily
        \vspace*{10mm}
        \reset@font\centerline{\ii@chapterfont\textbf{\MakeUppercase{#1}}}
        %\addvspace{42pt}
        \addvspace{1cm}
}
\renewcommand{\appendix}[1][\appendixname]{%
        \setcounter{chapter}{0}%
        \renewcommand{\thechapter}{\Alph{chapter}}%
        \setcounter{tocdepth}{0}%
        \@captionlistingfalse%
        \gdef\@chapapp{\MakeUppercase{#1}\space}%
        \addtocontents{toc}{%
          \settowidth{\ii@chapnumindent}{{\sffamily\textbf{\@chapapp}}}
          \addtolength{\ii@chapnumindent}{1.8em}
        }%
}
\newcommand{\annex}{\appendix[\annexname]}

%==============================================================================
% Formata��o das se��es
%==============================================================================
\setcounter{secnumdepth}{4}
\renewcommand{\section}{%
\setstretch{1.5} %espa�amento entre linhas
\parindent=1cm %identacao do paragrafo
\setlength\parskip{17pt plus 0pt minus 0pt}
        \@startsection{section}{1}{29pt}{15pt}{3pt}{\reset@font\bfseries}
}
\renewcommand{\subsection}{%
\setstretch{1.5}
\parindent=1cm
\setlength\parskip{17pt plus 0pt minus 0pt}
        \@startsection{subsection}{2}{29pt}{15pt}{3pt}{\reset@font\bfseries}
}
\renewcommand{\subsubsection}{%
\setstretch{1.5}
\parindent=1cm
\setlength\parskip{17pt plus 0pt minus 0pt}
        \@startsection{subsubsection}{3}{29pt}{15pt}{3pt}{\reset@font\bfseries}
}
\renewcommand{\paragraph}{%
        \@startsection{paragraph}{4}{0pt}{12pt}{6pt}{\reset@font}
}
\renewcommand{\subparagraph}{%				
		\@startsection{subparagraph}{5}{0pt}{1ex}{-1em}{\reset@font\bfseries}
}
%==============================================================================
% Redefini��o do conte�do das listas de figuras e tabelas
%==============================================================================  
\counterwithout{figure}{chapter} %contador figure sequencial no documento inteiro
\counterwithout{table}{chapter}  %contador table  sequencial no documento inteiro
\def\fnumx@figure{\thefigure}
\def\fnumx@table{\thetable}

\newif\if@captionlisting\@captionlistingtrue
\long\def\@caption#1[#2]#3{%
  \par
  \setstretch{1}
  \if@captionlisting%
    \addcontentsline{\csname ext@#1\endcsname}{#1}%
        {\protect\numberline{\csname fnumx@#1\endcsname}{\ignorespaces #2}}%
  \fi%
  \begingroup
    \@parboxrestore
    \if@minipage
      \@setminipage
    \fi
    \normalsize
    \@makecaption{\csname fnum@#1\endcsname}{\ignorespaces #3}\par
  \endgroup%
}
\renewcommand*{\l@figure}{\@dottedtocline{1}{0em}{1.5em}}
\let\l@table\l@figure

%==============================================================================
% Redefini��o do formato de cita��es longas
%==============================================================================
\renewenvironment{quote}{%		
				\par				
        \begin{list}{}{\setlength{\leftmargin}{40mm}\item\small}
        \setstretch{1}
}{%			
				\vspace{-0.2cm}
				\par
        \end{list}{}
}

%==============================================================================
% Ajuste do formato das cita��es e refer�ncias
%==============================================================================
\setlength{\bibhang}{0pt}
\let\cite\citep

%
% comandos DEPRECATED
% mantidos aqui somente para compatibilidade, nao constam mais do exemplo
% sugere-se remove-los a partir de julho/2003
% 07/dez/2002 - avila
%
\newcommand{\cip}{}
\newenvironment{dedicatoria}{%
        \clearpage%
        \mbox{}\vfill\begin{flushright}
}{
        \end{flushright}
}
\newenvironment{agradecimentos}{\chapter*{Agradecimentos}}{}

