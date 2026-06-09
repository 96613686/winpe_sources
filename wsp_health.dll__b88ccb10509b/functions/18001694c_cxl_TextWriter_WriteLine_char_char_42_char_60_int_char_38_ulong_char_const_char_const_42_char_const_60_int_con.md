# cxl::TextWriter::WriteLine<char,char [42],char [60],int,char [38],ulong>(char const *,char const (&)[42],char const (&)[60],int const &,char const (&)[38],ulong const &)

- ea: `0x18001694c`
- end: `0x1800169ba`
- name: `??$WriteLine@D$$BY0CK@D$$BY0DM@DH$$BY0CG@DK@TextWriter@cxl@@QEAAXPEBDAEAY0CK@$$CBDAEAY0DM@$$CBDAEBHAEAY0CG@$$CBDAEBK@Z`
- size: `110`
- prototype: `__int64 __usercall@<rax>(struct cxl::TextWriter *@<rcx>, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001a010`

## callees

- `0x1800104d8`

## string_xrefs

- `0x18001699a`: `servercommon\internal\base\inc\cluster\cxlrtl\CxlWin32TP2.h`
- `0x180016980`: `cxl::tp2::WorkItemBase::MoveToWaiting`
- `0x1800169a5`: `oldState == idle || oldState == completed`

## pseudocode

```c
struct cxl::TextWriter *__fastcall cxl::TextWriter::WriteLine<char,char [42],char [60],int,char [38],unsigned long>(
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
  v8 = &cxl::ArgumentWriters<char [42],char [60],int,char [38],unsigned long>::`vftable';
  v10 = a7;
  v11 = "cxl::tp2::WorkItemBase::MoveToWaiting";
  v12 = a5;
  v13 = "servercommon\\internal\\base\\inc\\cluster\\cxlrtl\\CxlWin32TP2.h";
  v14 = "oldState == idle || oldState == completed";
  return cxl::ArgumentWriter::Format(
           (cxl::ArgumentWriter *)&v8,
           a1,
           "BUGCHECK: \"{0}\"; module: \"{1}\"; line: {2}; function: \"{3}\"; error \"{4}\"",
           1);
}

```

## disassembly

```asm
0x18001694c  mov     r11, rsp
0x18001694f  sub     rsp, 68h
0x180016953  mov     [rsp+68h+var_40], 5
0x18001695b  lea     rax, ??_7?$ArgumentWriters@$$BY0CK@D$$BY0DM@DH$$BY0CG@DK@cxl@@6B@; const cxl::ArgumentWriters<char [42],char [60],int,char [38],ulong>::`vftable'
0x180016962  mov     [r11-48h], rax
0x180016966  lea     r8, aBugcheck0Modul; "BUGCHECK: \"{0}\"; module: \"{1}\"; lin"...
0x18001696d  mov     rax, [rsp+68h+arg_30]
0x180016975  mov     rdx, rcx; struct cxl::TextWriter *
0x180016978  mov     [r11-38h], rax
0x18001697c  lea     rcx, [r11-48h]; this
0x180016980  lea     rax, aCxlTp2Workitem_3; "cxl::tp2::WorkItemBase::MoveToWaiting"
0x180016987  mov     r9b, 1; bool
0x18001698a  mov     [r11-30h], rax
0x18001698e  mov     rax, [rsp+68h+arg_20]
0x180016996  mov     [r11-28h], rax
0x18001699a  lea     rax, aServercommonIn_3; "servercommon\\internal\\base\\inc\\clus"...
0x1800169a1  mov     [r11-20h], rax
0x1800169a5  lea     rax, aOldstateIdleOl; "oldState == idle || oldState == complet"...
0x1800169ac  mov     [r11-18h], rax
0x1800169b0  call    ?Format@ArgumentWriter@cxl@@QEAAAEAVTextWriter@2@AEAV32@PEBD_N@Z; cxl::ArgumentWriter::Format(cxl::TextWriter &,char const *,bool)
0x1800169b5  add     rsp, 68h
0x1800169b9  retn
```
