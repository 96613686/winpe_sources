# cxl::TextWriter::WriteLine<char,char [48],char [57],int,char [39],ulong>(char const *,char const (&)[48],char const (&)[57],int const &,char const (&)[39],ulong const &)

- ea: `0x18001c70c`
- end: `0x18001c77b`
- name: `??$WriteLine@D$$BY0DA@D$$BY0DJ@DH$$BY0CH@DK@TextWriter@cxl@@QEAAXPEBDAEAY0DA@$$CBDAEAY0DJ@$$CBDAEBHAEAY0CH@$$CBDAEBK@Z`
- size: `111`
- prototype: `__int64 __usercall@<rax>(struct cxl::TextWriter *@<rcx>, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001d234`

## callees

- `0x1800109bc`

## string_xrefs

- `0x18001c75a`: `servercommon\internal\base\inc\cluster\cxlrtl\CxlToken.h`
- `0x18001c740`: `cxl::ImpersonateUser::~ImpersonateUser`
- `0x18001c765`: `::SetThreadToken( NULL, userToken_.GetValue() )`

## pseudocode

```c
struct cxl::TextWriter *__fastcall cxl::TextWriter::WriteLine<char,char [48],char [57],int,char [39],unsigned long>(
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
  v8 = &cxl::ArgumentWriters<char [48],char [57],int,char [39],unsigned long>::`vftable';
  v10 = a7;
  v11 = "cxl::ImpersonateUser::~ImpersonateUser";
  v12 = a5;
  v13 = "servercommon\\internal\\base\\inc\\cluster\\cxlrtl\\CxlToken.h";
  v14 = "::SetThreadToken( NULL, userToken_.GetValue() )";
  return cxl::ArgumentWriter::Format(
           (cxl::ArgumentWriter *)&v8,
           a1,
           "BUGCHECK: \"{0}\"; module: \"{1}\"; line: {2}; function: \"{3}\"; error \"{4}\"",
           1);
}

```

## disassembly

```asm
0x18001c70c  mov     r11, rsp
0x18001c70f  sub     rsp, 68h
0x18001c713  mov     [rsp+68h+var_40], 5
0x18001c71b  lea     rax, ??_7?$ArgumentWriters@$$BY0DA@D$$BY0DJ@DH$$BY0CH@DK@cxl@@6B@; const cxl::ArgumentWriters<char [48],char [57],int,char [39],ulong>::`vftable'
0x18001c722  mov     [r11-48h], rax
0x18001c726  lea     r8, aBugcheck0Modul; "BUGCHECK: \"{0}\"; module: \"{1}\"; lin"...
0x18001c72d  mov     rax, [rsp+68h+arg_30]
0x18001c735  mov     rdx, rcx; struct cxl::TextWriter *
0x18001c738  mov     [r11-38h], rax
0x18001c73c  lea     rcx, [r11-48h]; this
0x18001c740  lea     rax, aCxlImpersonate; "cxl::ImpersonateUser::~ImpersonateUser"
0x18001c747  mov     r9b, 1; bool
0x18001c74a  mov     [r11-30h], rax
0x18001c74e  mov     rax, [rsp+68h+arg_20]
0x18001c756  mov     [r11-28h], rax
0x18001c75a  lea     rax, aServercommonIn_0; "servercommon\\internal\\base\\inc\\clus"...
0x18001c761  mov     [r11-20h], rax
0x18001c765  lea     rax, aSetthreadtoken; "::SetThreadToken( NULL, userToken_.GetV"...
0x18001c76c  mov     [r11-18h], rax
0x18001c770  call    ?Format@ArgumentWriter@cxl@@QEAAAEAVTextWriter@2@AEAV32@PEBD_N@Z; cxl::ArgumentWriter::Format(cxl::TextWriter &,char const *,bool)
0x18001c775  add     rsp, 68h
0x18001c779  retn
```
