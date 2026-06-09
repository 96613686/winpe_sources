# cxl::TextWriter::WriteLine<char,char [11],char [44],int,char [29],ulong>(char const *,char const (&)[11],char const (&)[44],int const &,char const (&)[29],ulong const &)

- ea: `0x180013be4`
- end: `0x180013c52`
- name: `??$WriteLine@D$$BY0L@D$$BY0CM@DH$$BY0BN@DK@TextWriter@cxl@@QEAAXPEBDAEAY0L@$$CBDAEAY0CM@$$CBDAEBHAEAY0BN@$$CBDAEBK@Z`
- size: `110`
- prototype: `__int64 __usercall@<rax>(struct cxl::TextWriter *@<rcx>, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013f94`

## callees

- `0x1800104d8`

## string_xrefs

- `0x180013c18`: `cxl::Token::OpenProcessToken`
- `0x180013c32`: `servercommon\base\cluster\cxlrtl\CxlToken.h`

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
0x180013be4  mov     r11, rsp
0x180013be7  sub     rsp, 68h
0x180013beb  mov     [rsp+68h+var_40], 5
0x180013bf3  lea     rax, ??_7?$ArgumentWriters@$$BY0L@D$$BY0CM@DH$$BY0BN@DK@cxl@@6B@; const cxl::ArgumentWriters<char [11],char [44],int,char [29],ulong>::`vftable'
0x180013bfa  mov     [r11-48h], rax
0x180013bfe  lea     r8, aBugcheck0Modul; "BUGCHECK: \"{0}\"; module: \"{1}\"; lin"...
0x180013c05  mov     rax, [rsp+68h+arg_30]
0x180013c0d  mov     rdx, rcx; struct cxl::TextWriter *
0x180013c10  mov     [r11-38h], rax
0x180013c14  lea     rcx, [r11-48h]; this
0x180013c18  lea     rax, aCxlTokenOpenpr; "cxl::Token::OpenProcessToken"
0x180013c1f  mov     r9b, 1; bool
0x180013c22  mov     [r11-30h], rax
0x180013c26  mov     rax, [rsp+68h+arg_20]
0x180013c2e  mov     [r11-28h], rax
0x180013c32  lea     rax, aServercommonBa_0; "servercommon\\base\\cluster\\cxlrtl\\Cx"...
0x180013c39  mov     [r11-20h], rax
0x180013c3d  lea     rax, aIsvalid; "!IsValid()"
0x180013c44  mov     [r11-18h], rax
0x180013c48  call    ?Format@ArgumentWriter@cxl@@QEAAAEAVTextWriter@2@AEAV32@PEBD_N@Z; cxl::ArgumentWriter::Format(cxl::TextWriter &,char const *,bool)
0x180013c4d  add     rsp, 68h
0x180013c51  retn
```
