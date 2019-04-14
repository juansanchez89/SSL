gcc hellow2 resultado:

hello2.c: In function 'main':
hello2.c:8:11: warning: implicit declaration of function 'prontf' [-Wimplicit-function-declaration]
 int i=42; prontf("La respuesta es %d\n");
           ^
hello2.c:8:1: error: expected declaration or statement at end of input
 int i=42; prontf("La respuesta es %d\n");

--------------------------------------------------------------------------------------------------------------------

gcc -save-temps hello2.c resultado:

hello2.c: In function 'main':
hello2.c:8:11: warning: implicit declaration of function 'prontf' [-Wimplicit-function-declaration]
 int i=42; prontf("La respuesta es %d\n");
           ^
hello2.c:8:1: error: expected declaration or statement at end of input
 int i=42; prontf("La respuesta es %d\n");
 ^

SE GEMERA UN .i Y UN .S

--------------------------------------------------------------------------------------------------------------------

gcc -save-temps hello3.c resultado:

gcc -save-temps hello3.c
hello3.c: In function 'main':
hello3.c:5:2: warning: implicit declaration of function 'prontf' [-Wimplicit-function-declaration]
  prontf("La respuesta es %d\n");
  ^
hello3.c:5:2: error: expected declaration or statement at end of input

EL CONTENIDO DEL .I ES 

# 1 "hello3.c"
# 1 "<built-in>"
# 1 "<command-line>"
# 1 "hello3.c"

int printf(const char *s, ...);
int main(void)
{ int i=42;
 prontf("La respuesta es %d\n");


EL CONTENIDO DEL .C ES

int printf(const char *s, ...);
int main(void)
{ int i=42;
 prontf("La respuesta es %d\n");

-------------------------------------------------------------------------------------------------------------------

gcc -save-temps hello4.c resultado:

	.file	"hello4.c"
	.def	__main;	.scl	2;	.type	32;	.endef
	.section .rdata,"dr"
.LC0:
	.ascii "La respuesta es %d\12\0"
	.text
	.globl	main
	.def	main;	.scl	2;	.type	32;	.endef
	.seh_proc	main
main:
	pushq	%rbp
	.seh_pushreg	%rbp
	movq	%rsp, %rbp
	.seh_setframe	%rbp, 0
	subq	$48, %rsp
	.seh_stackalloc	48
	.seh_endprologue
	call	__main
	movl	$42, -4(%rbp)
	leaq	.LC0(%rip), %rcx
	call	printf
	movl	$0, %eax
	addq	$48, %rsp
	popq	%rbp
	ret
	.seh_endproc
	.ident	"GCC: (tdm64-1) 5.1.0"
	.def	printf;	.scl	2;	.type	32;	.endef

-----------------------------------------------------------------------------------------------------------------------

La respuesta es 9835440


-----------------------------------------------------------------------------------------------------------------------

La respuesta es 42

-----------------------------------------------------------------------------------------------------------------------
Hello7.c

||=== Build file: "no target" in "no project" (compiler: unknown) ===|
C:\Users\JetBlack\source\gitsintaxis\ssl\SSL\01-CFases_de_la_Traducción_y_Errores\hello7.c||In function 'main':|
C:\Users\JetBlack\source\gitsintaxis\ssl\SSL\01-CFases_de_la_Traducción_y_Errores\hello7.c|3|warning: implicit declaration of function 'printf' [-Wimplicit-function-declaration]|
C:\Users\JetBlack\source\gitsintaxis\ssl\SSL\01-CFases_de_la_Traducción_y_Errores\hello7.c|3|warning: incompatible implicit declaration of built-in function 'printf'|
C:\Users\JetBlack\source\gitsintaxis\ssl\SSL\01-CFases_de_la_Traducción_y_Errores\hello7.c|3|note: include '<stdio.h>' or provide a declaration of 'printf'|
||=== Build finished: 0 error(s), 2 warning(s) (0 minute(s), 2 second(s)) ===|







