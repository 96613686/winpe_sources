# cxl::TextWriter::WriteLine<char,char [48],char [57],int,char [39],ulong>(char const *,char const (&)[48],char const (&)[57],int const &,char const (&)[39],ulong const &)

- ea: `0x18001bbe4`
- end: `0x18001bc52`
- name: `??$WriteLine@D$$BY0DA@D$$BY0DJ@DH$$BY0CH@DK@TextWriter@cxl@@QEAAXPEBDAEAY0DA@$$CBDAEAY0DJ@$$CBDAEBHAEAY0CH@$$CBDAEBK@Z`
- size: `110`
- prototype: `__int64 __usercall@<rax>(struct cxl::TextWriter *@<rcx>, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001c6f0`

## callees

- `0x1800104d8`

## string_xrefs

- `0x18001bc32`: `servercommon\internal\base\inc\cluster\cxlrtl\CxlToken.h`
- `0x18001bc3d`: `::SetThreadToken( NULL, userToken_.GetValue() )`
- `0x18001bc18`: `cxl::ImpersonateUser::~ImpersonateUser`

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
0x18001bbe4  mov     r11, rsp
0x18001bbe7  sub     rsp, 68h
0x18001bbeb  mov     [rsp+68h+var_40], 5
0x18001bbf3  lea     rax, ??_7?$ArgumentWriters@$$BY0DA@D$$BY0DJ@DH$$BY0CH@DK@cxl@@6B@; const cxl::ArgumentWriters<char [48],char [57],int,char [39],ulong>::`vftable'
0x18001bbfa  mov     [r11-48h], rax
0x18001bbfe  lea     r8, aBugcheck0Modul; "BUGCHECK: \"{0}\"; module: \"{1}\"; lin"...
0x18001bc05  mov     rax, [rsp+68h+arg_30]
0x18001bc0d  mov     rdx, rcx; struct cxl::TextWriter *
0x18001bc10  mov     [r11-38h], rax
0x18001bc14  lea     rcx, [r11-48h]; this
0x18001bc18  lea     rax, aCxlImpersonate; "cxl::ImpersonateUser::~ImpersonateUser"
0x18001bc1f  mov     r9b, 1; bool
0x18001bc22  mov     [r11-30h], rax
0x18001bc26  mov     rax, [rsp+68h+arg_20]
0x18001bc2e  mov     [r11-28h], rax
0x18001bc32  lea     rax, aServercommonIn_0; "servercommon\\internal\\base\\inc\\clus"...
0x18001bc39  mov     [r11-20h], rax
0x18001bc3d  lea     rax, aSetthreadtoken; "::SetThreadToken( NULL, userToken_.GetV"...
0x18001bc44  mov     [r11-18h], rax
0x18001bc48  call    ?Format@ArgumentWriter@cxl@@QEAAAEAVTextWriter@2@AEAV32@PEBD_N@Z; cxl::ArgumentWriter::Format(cxl::TextWriter &,char const *,bool)
0x18001bc4d  add     rsp, 68h
0x18001bc51  retn
```
