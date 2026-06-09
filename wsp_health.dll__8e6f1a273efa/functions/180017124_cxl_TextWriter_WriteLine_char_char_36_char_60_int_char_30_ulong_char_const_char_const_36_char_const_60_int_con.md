# cxl::TextWriter::WriteLine<char,char [36],char [60],int,char [30],ulong>(char const *,char const (&)[36],char const (&)[60],int const &,char const (&)[30],ulong const &)

- ea: `0x180017124`
- end: `0x180017193`
- name: `??$WriteLine@D$$BY0CE@D$$BY0DM@DH$$BY0BO@DK@TextWriter@cxl@@QEAAXPEBDAEAY0CE@$$CBDAEAY0DM@$$CBDAEBHAEAY0BO@$$CBDAEBK@Z`
- size: `111`
- prototype: `__int64 __usercall@<rax>(struct cxl::TextWriter *@<rcx>, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001a600`

## callees

- `0x1800109bc`

## string_xrefs

- `0x18001717d`: `!IsCurrentThreadExecutingCallBack()`
- `0x180017172`: `servercommon\internal\base\inc\cluster\cxlrtl\CxlWin32TP2.h`

## pseudocode

```c
struct cxl::TextWriter *__fastcall cxl::TextWriter::WriteLine<char,char [36],char [60],int,char [30],unsigned long>(
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
  v8 = &cxl::ArgumentWriters<char [36],char [60],int,char [30],unsigned long>::`vftable';
  v10 = a7;
  v11 = "cxl::tp2::TimerWorkItem::Join";
  v12 = a5;
  v13 = "servercommon\\internal\\base\\inc\\cluster\\cxlrtl\\CxlWin32TP2.h";
  v14 = "!IsCurrentThreadExecutingCallBack()";
  return cxl::ArgumentWriter::Format(
           (cxl::ArgumentWriter *)&v8,
           a1,
           "BUGCHECK: \"{0}\"; module: \"{1}\"; line: {2}; function: \"{3}\"; error \"{4}\"",
           1);
}

```

## disassembly

```asm
0x180017124  mov     r11, rsp
0x180017127  sub     rsp, 68h
0x18001712b  mov     [rsp+68h+var_40], 5
0x180017133  lea     rax, ??_7?$ArgumentWriters@$$BY0CE@D$$BY0DM@DH$$BY0BO@DK@cxl@@6B@; const cxl::ArgumentWriters<char [36],char [60],int,char [30],ulong>::`vftable'
0x18001713a  mov     [r11-48h], rax
0x18001713e  lea     r8, aBugcheck0Modul; "BUGCHECK: \"{0}\"; module: \"{1}\"; lin"...
0x180017145  mov     rax, [rsp+68h+arg_30]
0x18001714d  mov     rdx, rcx; struct cxl::TextWriter *
0x180017150  mov     [r11-38h], rax
0x180017154  lea     rcx, [r11-48h]; this
0x180017158  lea     rax, aCxlTp2Timerwor_2; "cxl::tp2::TimerWorkItem::Join"
0x18001715f  mov     r9b, 1; bool
0x180017162  mov     [r11-30h], rax
0x180017166  mov     rax, [rsp+68h+arg_20]
0x18001716e  mov     [r11-28h], rax
0x180017172  lea     rax, aServercommonIn_3; "servercommon\\internal\\base\\inc\\clus"...
0x180017179  mov     [r11-20h], rax
0x18001717d  lea     rax, aIscurrentthrea; "!IsCurrentThreadExecutingCallBack()"
0x180017184  mov     [r11-18h], rax
0x180017188  call    ?Format@ArgumentWriter@cxl@@QEAAAEAVTextWriter@2@AEAV32@PEBD_N@Z; cxl::ArgumentWriter::Format(cxl::TextWriter &,char const *,bool)
0x18001718d  add     rsp, 68h
0x180017191  retn
```
