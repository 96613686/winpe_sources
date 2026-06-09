# cxl::TextWriter::WriteLine<char,char [11],char [44],int,char [29],ulong>(char const *,char const (&)[11],char const (&)[44],int const &,char const (&)[29],ulong const &)

- ea: `0x18001432c`
- end: `0x18001439b`
- name: `??$WriteLine@D$$BY0L@D$$BY0CM@DH$$BY0BN@DK@TextWriter@cxl@@QEAAXPEBDAEAY0L@$$CBDAEAY0CM@$$CBDAEBHAEAY0BN@$$CBDAEBK@Z`
- size: `111`
- prototype: `__int64 __usercall@<rax>(struct cxl::TextWriter *@<rcx>, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014708`

## callees

- `0x1800109bc`

## string_xrefs

- `0x180014360`: `cxl::Token::OpenProcessToken`
- `0x18001437a`: `servercommon\base\cluster\cxlrtl\CxlToken.h`

## pseudocode

```c
struct cxl::TextWriter *__fastcall cxl::TextWriter::WriteLine<char,char [11],char [44],int,char [29],unsigned long>(
        struct cxl::TextWriter *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7)
{
  void **v8; // [rsp+20h] [rbp-48h] BYREF
  int v9; // [rsp+28h] [rbp-40h]
  __int64 v10; // [rsp+30h] [rbp-38h]
  const char *v11; // [rsp+38h] [rbp-30h]
  __int64 v12; // [rsp+40h] [rbp-28h]
  const char *v13; // [rsp+48h] [rbp-20h]
  const char *v14; // [rsp+50h] [rbp-18h]

  v9 = 5;
  v8 = &cxl::ArgumentWriters<char [11],char [44],int,char [29],unsigned long>::`vftable';
  v10 = a7;
  v11 = "cxl::Token::OpenProcessToken";
  v12 = a5;
  v13 = "servercommon\\base\\cluster\\cxlrtl\\CxlToken.h";
  v14 = "!IsValid()";
  return cxl::ArgumentWriter::Format(
           (cxl::ArgumentWriter *)&v8,
           a1,
           "BUGCHECK: \"{0}\"; module: \"{1}\"; line: {2}; function: \"{3}\"; error \"{4}\"",
           1);
}

```

## disassembly

```asm
0x18001432c  mov     r11, rsp
0x18001432f  sub     rsp, 68h
0x180014333  mov     [rsp+68h+var_40], 5
0x18001433b  lea     rax, ??_7?$ArgumentWriters@$$BY0L@D$$BY0CM@DH$$BY0BN@DK@cxl@@6B@; const cxl::ArgumentWriters<char [11],char [44],int,char [29],ulong>::`vftable'
0x180014342  mov     [r11-48h], rax
0x180014346  lea     r8, aBugcheck0Modul; "BUGCHECK: \"{0}\"; module: \"{1}\"; lin"...
0x18001434d  mov     rax, [rsp+68h+arg_30]
0x180014355  mov     rdx, rcx; struct cxl::TextWriter *
0x180014358  mov     [r11-38h], rax
0x18001435c  lea     rcx, [r11-48h]; this
0x180014360  lea     rax, aCxlTokenOpenpr; "cxl::Token::OpenProcessToken"
0x180014367  mov     r9b, 1; bool
0x18001436a  mov     [r11-30h], rax
0x18001436e  mov     rax, [rsp+68h+arg_20]
0x180014376  mov     [r11-28h], rax
0x18001437a  lea     rax, aServercommonBa_0; "servercommon\\base\\cluster\\cxlrtl\\Cx"...
0x180014381  mov     [r11-20h], rax
0x180014385  lea     rax, aIsvalid; "!IsValid()"
0x18001438c  mov     [r11-18h], rax
0x180014390  call    ?Format@ArgumentWriter@cxl@@QEAAAEAVTextWriter@2@AEAV32@PEBD_N@Z; cxl::ArgumentWriter::Format(cxl::TextWriter &,char const *,bool)
0x180014395  add     rsp, 68h
0x180014399  retn
```
