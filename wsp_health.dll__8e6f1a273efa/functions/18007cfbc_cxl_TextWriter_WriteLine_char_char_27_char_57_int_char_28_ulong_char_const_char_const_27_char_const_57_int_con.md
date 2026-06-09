# cxl::TextWriter::WriteLine<char,char [27],char [57],int,char [28],ulong>(char const *,char const (&)[27],char const (&)[57],int const &,char const (&)[28],ulong const &)

- ea: `0x18007cfbc`
- end: `0x18007d02b`
- name: `??$WriteLine@D$$BY0BL@D$$BY0DJ@DH$$BY0BM@DK@TextWriter@cxl@@QEAAXPEBDAEAY0BL@$$CBDAEAY0DJ@$$CBDAEBHAEAY0BM@$$CBDAEBK@Z`
- size: `111`
- prototype: `__int64 __usercall@<rax>(struct cxl::TextWriter *@<rcx>, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18007d4b0`

## callees

- `0x1800109bc`

## string_xrefs

- `0x18007d00a`: `servercommon\internal\base\inc\cluster\cxlrtl\CxlToken.h`
- `0x18007cff0`: `cxl::Token::DuplicateHandle`

## pseudocode

```c
struct cxl::TextWriter *__fastcall cxl::TextWriter::WriteLine<char,char [27],char [57],int,char [28],unsigned long>(
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
  v8 = &cxl::ArgumentWriters<char [27],char [57],int,char [28],unsigned long>::`vftable';
  v10 = a7;
  v11 = "cxl::Token::DuplicateHandle";
  v12 = a5;
  v13 = "servercommon\\internal\\base\\inc\\cluster\\cxlrtl\\CxlToken.h";
  v14 = "ERROR_INVALID_HANDLE != rc";
  return cxl::ArgumentWriter::Format(
           (cxl::ArgumentWriter *)&v8,
           a1,
           "BUGCHECK: \"{0}\"; module: \"{1}\"; line: {2}; function: \"{3}\"; error \"{4}\"",
           1);
}

```

## disassembly

```asm
0x18007cfbc  mov     r11, rsp
0x18007cfbf  sub     rsp, 68h
0x18007cfc3  mov     [rsp+68h+var_40], 5
0x18007cfcb  lea     rax, ??_7?$ArgumentWriters@$$BY0BL@D$$BY0DJ@DH$$BY0BM@DK@cxl@@6B@; const cxl::ArgumentWriters<char [27],char [57],int,char [28],ulong>::`vftable'
0x18007cfd2  mov     [r11-48h], rax
0x18007cfd6  lea     r8, aBugcheck0Modul; "BUGCHECK: \"{0}\"; module: \"{1}\"; lin"...
0x18007cfdd  mov     rax, [rsp+68h+arg_30]
0x18007cfe5  mov     rdx, rcx; struct cxl::TextWriter *
0x18007cfe8  mov     [r11-38h], rax
0x18007cfec  lea     rcx, [r11-48h]; this
0x18007cff0  lea     rax, aCxlTokenDuplic; "cxl::Token::DuplicateHandle"
0x18007cff7  mov     r9b, 1; bool
0x18007cffa  mov     [r11-30h], rax
0x18007cffe  mov     rax, [rsp+68h+arg_20]
0x18007d006  mov     [r11-28h], rax
0x18007d00a  lea     rax, aServercommonIn_0; "servercommon\\internal\\base\\inc\\clus"...
0x18007d011  mov     [r11-20h], rax
0x18007d015  lea     rax, aErrorInvalidHa_0; "ERROR_INVALID_HANDLE != rc"
0x18007d01c  mov     [r11-18h], rax
0x18007d020  call    ?Format@ArgumentWriter@cxl@@QEAAAEAVTextWriter@2@AEAV32@PEBD_N@Z; cxl::ArgumentWriter::Format(cxl::TextWriter &,char const *,bool)
0x18007d025  add     rsp, 68h
0x18007d029  retn
```
