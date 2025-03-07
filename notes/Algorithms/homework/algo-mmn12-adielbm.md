**ממן 12** 
אלגוריתמים 25א
___
# שאלה 1

- נתון גרף מכוון $G=(V,E)$, עם $w(e)>0$ לכל $e\in E$, ומקור $s\in V$.
- נתון כי לכל $v\in V$, קיים מסלול $P_{s,v}$ מ-$s$ ל-$v$.
- $w(P)=\sum_{e\in P}w(e)$
- אם $w(P_{s,v})\leq w(P'_{s,v})$ לכל מסלול $P'_{s,v}$, אזי $P_{s,v}$ הוא מסלול מזערי מ-$s$ ל-$v$.
- אם $w_1<w_2<\ldots<w_k$ הם המשקלים האפשריים של מסלולים מ-$s$ ל-$v$, אזי לכל מסלול מזערי $P_{s,v}$, מתקיים $w(P_{s,v})=w_1$. המסלולים עם המשקל $w_2$ נקראים **מסלול כמעט-מזערי**
- אם צלע $e=(u,v)\in E$ היא הצלע האחרונה במסלול מזערי $P_{s,v}$, היא נקראת **צלע שימושית**.

- **(א) מסלולים עם צלעות שימושיות בלבד הם מסלולים מזעריים**
	- **מקרה בסיסי ($k=1$)**:
		- מסלול עם $k = 1$ משמעו $P_{s,v}$ מכיל צלע אחת בלבד, אשר היא שימושית, ולכן מסלול מזערי, היות והוא המסלול היחיד מ-$s$ ל-$v$.
	- **הנחת האינדוקציה**:
		- נניח כי לכל מסלול $P_{s,v}$ באורך $k-1$, אם כל הצלעות שלו שימושיות, אזי $P_{s,v}$ הוא מסלול מזערי.
	- **צעד האינדוקציה**:
		- נסתכל על מסלול $P_{s,v}$ באורך $k$, שכל צלעותיו שימושיות.
		- תהי $e = (u, v)$ הצלע האחרונה של $P_{s,v}$. כלומר $P_{s,v} = P_{s,u} \cup \{e\}$, כאשר $P_{s,u}$ הוא מסלול מ-$s$ ל-$u$ באורך $k-1$.
		- מהנחת האינדוקציה, $P_{s,u}$ הוא מסלול מזערי היות וכל צלעותיו שימושיות.
		- כעת, בהוספת $e$, שהיא גם שימושית, לפי הגדרת השימושיות, הוספת $e$ למסלול המזערי $P_{s,u}$ מ-$s$ ל-$u$ יוצרת את המסלול המזערי $P_{s,v}$ מ-$s$ ל-$v$.
		- המשקל הכולל של $P_{s,v}$ הוא $w(P_{s,v}) = w(P_{s,u}) + w(e)$.
		- אף מסלול חלופי מ-$s$ ל-$v$ לא יכול להיות בעל משקל נמוך יותר כי $P_{s,u}$ כבר המזערי ל-$u$ ו-$e$ שימושית.
		- לכן, $P_{s,v}$ הוא מסלול מזערי.

- **(ב) מסלולים המכילים צלעות לא שימושיות אינם מסלולים מזעריים**
	- יהי $P_{s,v}$ מסלול מ-$s$ ל-$v$ באורך כלשהו $k$. נניח כי $P_{s,v}$ מכיל צלע לא שימושית $e = (x, y)$.
	- לפי ההגדרה, צלע היא לא שימושית אם קיים מסלול $P'_{s,y}$ מ-$s$ ל-$y$ שאינו משתמש ב-$e$ ו-$w(P'_{s,y}) < w(P_{s,y})$.
	- נגדיר מסלול חדש $P''_{s,v} = P'_{s,y} \cup P_{y,v}$.
	- מכיוון ש-$w(P'_{s,y}) < w(P_{s,y})$, אזי $w(P''_{s,v}) < w(P_{s,v})$.
	- לכן, $P_{s,v}$ אינו יכול להיות מסלול מזערי.

- **(ג) אם $P_{s,v}$ הוא מסלול כמעט-מזערי, אז יש לו בדיוק צלע לא שימושית אחת**
	- המסלול $P_{s,v}$ הוא כמעט-מזערי אם $w(P_{s,v}) = w_2>w_1$, כאשר $w_1$ הוא משקל המסלול המזערי. לכן, $P_{s,v}$ אינו מסלול מזערי. לפיכך, $P_{s,v}$ חייב להכיל לפחות צלע לא שימושית אחת. (לפי א)
	- נניח כי $P_{s,v}$ מכיל יותר מצלע לא שימושית אחת. יהיו $e_1=(x_1,y_1)$ ו-$e_2=(x_2,y_2)$ שתי הצלעות הלא שימושיות ב-$P_{s,v}=P_{s,x_1}\cup\{e_1\}\cup P_{y_1,x_2}\cup\{e_2\}\cup P_{y_2,v}$.
	- יהי $P'_{s,v}$ מסלול המזערי מ-$s$ ל-$v$.
	- מכיוון ש-$e_1$ ו-$e_2$ לא שימושיות, קיימים מסלולים $P'_{s,y_1}$ ו-$P'_{s,y_2}$ הקצרים מ-$P_{s,y_1}$ ו-$P_{s,y_2}$, בהתאמה.
	- לכן, המסלול $P''_{s,v}=P'_{s,y_1}\cup P_{y_1,x_2}\cup\{e_2\}\cup P_{y_2,v}\neq P_{s,v}$ מקיים:
		- גם: $w(P'_{s,v})<w(P''_{s,v})$ (כי $w(P'_{y_1,v})<w(P_{y_1,v})$)
		- וגם: $w(P''_{s,v})<w(P_{s,v})$ (כי $w(P'_{s,y_1})<w(P_{s,y_1})$)
	- לכן $w(P'_{s,v})<w(P''_{s,v})<w(P_{s,v})$, מה שסותר את ההנחה ש $P_{s,v}$ הוא כמעט-מזערי.

- **(ד) הרישא של $P_{s,v}=P_{s,u_1}\cup\{e\}\cup P_{u_2,v}$ מ-$s$ ל-$u_1$ היא מסלול מזערי, והסיפא מ-$u_2$ ל-$v$ היא מסלול מזערי**
	- לפי סעיף א, הן הרישא והן הסיפא הם מסלולים מזעריים כי הם מכילים רק צלעות שימושיות.

- **(ה)  אלגוריתם למציאת מסלול כמעט-מזערי מ-$s$ ל-$t$ בסיבוכיות זמן $\Theta(|E|\cdot \log |V|)$**
	- נמצא מסלול מזערי $P_{s,t}$ בעזרת דייקסטרה מ-$s$.
	- נגדיר $w_{sec}=\infty$ ו-$e_{sec}=\emptyset$.
	- לכל צלע $e=(u,v)$ שעבורה `pred[v]!=u` (כלומר $e$ אינה שימושית) נבצע:
		- אם $w(P_{s,u})+w(e)+w(P_{v,t})<w_{sec}$ אזי:
		    - גם: $w_{sec}=w(P_{s,u})+w(e)+w(P_{v,t})$
		    - וגם:  $e_{sec}=e$
	- אם $e_{sec}=\emptyset$ או $w_{sec}=w(P_{s,t})$ אזי אין מסלול כמעט-מזערי מ-$s$ ל-$t$. אחרת, יש מסלול כמעט-מזערי $P_{s,u}\cup\{e_{sec}\}\cup P_{v,t}$.

# שאלה 2

- נתון גרף בלתי מכוון קשיר $G=(V,E)$ עם $w(e)>0$ שהם ערכים שלמים ושונים זה מזה.
- הגרף $T^1$ הוא עמ"מ מ-$s$ לכל שאר הקודקודים ב-$G$. ו-$T^2$ הוא עפ"מ של $G$.
- (א) הוכיחו כי $T^1$ ו-$T^2$ חולקים לפחות צלע אחת.
	- נניח בשלילה כי $T^1=(V,E_1)$ ו-$T^2=(V,E_2)$ אינם חולקים צלעות משותפות.
	- כלומר, $E_1\cap E_2=\emptyset$.
	- ניקח צלע כלשהי $e=(s,v)$ ב-$T^2$ שאינה ב-$T^1$.
	- מאחר ו-$T^1$ הוא עמ"מ, קיים מסלול $P_{s,v}$ מ-$s$ ל-$v$ ב-$T^1$ כך ש-$w(P_{s,v})\leq w((s,v))$.
	- נסמן את הגרף $\overline{T^2}$ כגרף הזהה ל-$T^2$ אך עם הוספת המסלול $P_{s,v}=s \rightsquigarrow p \rightsquigarrow v$ והסרת הצלע $(s,v)$ והסרת צלע אחרת $(p,q)$. (שבהכרח הייתה שם כדי לחבר את $p$ לעפ"מ)
	- לפיכך, $w(P_{s,v}) < w((s,v)) + w((p,q))$. (מאחר ו-$w((p,q))>0$)
	- כך שיש לנו עץ פורש $\overline{T^2}$ כך ש-$w(\overline{T^2})<w(T^2)$, מה שסותר את ההנחה כי $T^2$ הוא עפ"מ.
- (ב) הציגו סדרה של גרפים $G_n=(V_n,E_n)$ עם $n=|V_n|$ וקודקוד מוצא $s_n\in V$ ומשקלים חיוביים שלמים ושונים כך שלגרף $G_n$ יש עמ"מ $T^1_n$ ועפ"מ $T^2_n$ שיש להם בדיוק צלע אחת משותפת. #TODO

# שאלה 4


- **הוכיחו כי עבור כל עץ בינארי לחלוטין (_full_) מושרש $T$ עם $n \geq 2$ עלים, קיימת סדרת שכיחויות $f_1,f_2,\ldots,f_n$ כך שאחד מעצי הופמן עבור סדרת השכיחויות הזו הוא $T$.**
	- נשתמש באינדוקציה על מספר העלים $n$ בעץ $T$.
	- מקרה בסיס ($n = 2$): 
		- עץ בינארי מלא עם $n = 2$ עלים מורכב משורש יחיד עם שני צאצאים (העלים). האלגוריתם עם שתי שכיחויות $f_1$ ו-$f_2$, תמיד חבנה עץ שבו שני העלים מאוחדים לשורש..
	- הנחת האינדוקציה: 
		- נניח כי עבור כל עץ בינארי מלא $T$ עם $n \geq 2$ עלים, קיימת סדרת שכיחויות $f_1, f_2, \ldots, f_{n}$ כך שהאלגוריתם של הופמן מייצר איתה את $T$.
	- צעד האינדוקציה:
		- נבחר שני עלים $a$ ו-$b$ בעומק המרבי. נניח שהורה של עלים אלו הוא $v$.
		- אם נסיר את $a$ ו-$b$ מ-$T$ ונחליף את ההורה שלהם $v$ בעלה חדש $m$, ניצור עץ חדש $T'$ עם $n - 1$ עלים.
		- על פי הנחת האינדוקציה, קיימת סדרת שכיחויות $f'_1, f'_2, \ldots, f'_{n-1}$ עבור העלים של $T'$ כך שהאלגוריתם של הופמן יכול לבנות את $T'$.
		- נגדיר את השכיחויות של $a$ ו-$b$ כ-$f_a$ ו-$f_b$, כך ש-$f_a + f_b = f_m$, כאשר $f_m$ היא השכיחות של $m$ ב-$T'$. נבחר את $f_a$ ו-$f_b$ כך שיהיו שונים וקטנים מכל שאר השכיחויות ב-$T'$.
		- בהרצת של האלגוריתם של הופמן, שתי השכיחויות הקטנות ביותר $f_a$ ו-$f_b$ יאוחדו ל-$m$, מה שייצור את $T'$. ואז על פי הנחת האינדוקציה, זה יבנה את $T'$, כלומר בסך הכל נקבל את $T$.

___
תודה רבה :)
