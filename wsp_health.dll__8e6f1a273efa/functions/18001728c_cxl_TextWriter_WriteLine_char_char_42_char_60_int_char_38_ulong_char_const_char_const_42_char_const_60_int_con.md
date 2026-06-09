# cxl::TextWriter::WriteLine<char,char [42],char [60],int,char [38],ulong>(char const *,char const (&)[42],char const (&)[60],int const &,char const (&)[38],ulong const &)

- ea: `0x18001728c`
- end: `0x1800172fb`
- name: `??$WriteLine@D$$BY0CK@D$$BY0DM@DH$$BY0CG@DK@TextWriter@cxl@@QEAAXPEBDAEAY0CK@$$CBDAEAY0DM@$$CBDAEBHAEAY0CG@$$CBDAEBK@Z`
- size: `111`
- prototype: `__int64 __usercall@<rax>(struct cxl::TextWriter *@<rcx>, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001aa60`

## callees

- `0x1800109bc`

## string_xrefs

- `0x1800172da`: `servercommon\internal\base\inc\cluster\cxlrtl\CxlWin32TP2.h`
- `0x1800172c0`: `cxl::tp2::WorkItemBase::MoveToWaiting`
- `0x1800172e5`: `oldState == idle || oldState == completed`

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
0x18001728c  mov     r11, rsp
0x18001728f  sub     rsp, 68h
0x180017293  mov     [rsp+68h+var_40], 5
0x18001729b  lea     rax, ??_7?$ArgumentWriters@$$BY0CK@D$$BY0DM@DH$$BY0CG@DK@cxl@@6B@; const cxl::ArgumentWriters<char [42],char [60],int,char [38],ulong>::`vftable'
0x1800172a2  mov     [r11-48h], rax
0x1800172a6  lea     r8, aBugcheck0Modul; "BUGCHECK: \"{0}\"; module: \"{1}\"; lin"...
0x1800172ad  mov     rax, [rsp+68h+arg_30]
0x1800172b5  mov     rdx, rcx; struct cxl::TextWriter *
0x1800172b8  mov     [r11-38h], rax
0x1800172bc  lea     rcx, [r11-48h]; this
0x1800172c0  lea     rax, aCxlTp2Workitem_3; "cxl::tp2::WorkItemBase::MoveToWaiting"
0x1800172c7  mov     r9b, 1; bool
0x1800172ca  mov     [r11-30h], rax
0x1800172ce  mov     rax, [rsp+68h+arg_20]
0x1800172d6  mov     [r11-28h], rax
0x1800172da  lea     rax, aServercommonIn_3; "servercommon\\internal\\base\\inc\\clus"...
0x1800172e1  mov     [r11-20h], rax
0x1800172e5  lea     rax, aOldstateIdleOl; "oldState == idle || oldState == complet"...
0x1800172ec  mov     [r11-18h], rax
0x1800172f0  call    ?Format@ArgumentWriter@cxl@@QEAAAEAVTextWriter@2@AEAV32@PEBD_N@Z; cxl::ArgumentWriter::Format(cxl::TextWriter &,char const *,bool)
0x1800172f5  add     rsp, 68h
0x1800172f9  retn
```
