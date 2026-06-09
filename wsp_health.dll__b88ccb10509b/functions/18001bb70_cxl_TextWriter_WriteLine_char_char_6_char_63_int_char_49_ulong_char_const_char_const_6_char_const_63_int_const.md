# cxl::TextWriter::WriteLine<char,char [6],char [63],int,char [49],ulong>(char const *,char const (&)[6],char const (&)[63],int const &,char const (&)[49],ulong const &)

- ea: `0x18001bb70`
- end: `0x18001bbde`
- name: `??$WriteLine@D$$BY05D$$BY0DP@DH$$BY0DB@DK@TextWriter@cxl@@QEAAXPEBDAEAY05$$CBDAEAY0DP@$$CBDAEBHAEAY0DB@$$CBDAEBK@Z`
- size: `110`
- prototype: `__int64 __usercall@<rax>(struct cxl::TextWriter *@<rcx>, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18008548c`

## callees

- `0x1800104d8`

## string_xrefs

- `0x18001bbbe`: `nanoserver\base\cluster\wmiprovider\common\lib\taskmanager.cpp`
- `0x18001bba4`: `ClusWmi::TaskManager::ScheduledTask::ExecuteTask`

## pseudocode

```c
struct cxl::TextWriter *__fastcall cxl::TextWriter::WriteLine<char,char [6],char [63],int,char [49],unsigned long>(
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
  v8 = &cxl::ArgumentWriters<char [6],char [63],int,char [49],unsigned long>::`vftable';
  v10 = a7;
  v11 = "ClusWmi::TaskManager::ScheduledTask::ExecuteTask";
  v12 = a5;
  v13 = "nanoserver\\base\\cluster\\wmiprovider\\common\\lib\\taskmanager.cpp";
  v14 = "false";
  return cxl::ArgumentWriter::Format(
           (cxl::ArgumentWriter *)&v8,
           a1,
           "BUGCHECK: \"{0}\"; module: \"{1}\"; line: {2}; function: \"{3}\"; error \"{4}\"",
           1);
}

```

## disassembly

```asm
0x18001bb70  mov     r11, rsp
0x18001bb73  sub     rsp, 68h
0x18001bb77  mov     [rsp+68h+var_40], 5
0x18001bb7f  lea     rax, ??_7?$ArgumentWriters@$$BY05D$$BY0DP@DH$$BY0DB@DK@cxl@@6B@; const cxl::ArgumentWriters<char [6],char [63],int,char [49],ulong>::`vftable'
0x18001bb86  mov     [r11-48h], rax
0x18001bb8a  lea     r8, aBugcheck0Modul; "BUGCHECK: \"{0}\"; module: \"{1}\"; lin"...
0x18001bb91  mov     rax, [rsp+68h+arg_30]
0x18001bb99  mov     rdx, rcx; struct cxl::TextWriter *
0x18001bb9c  mov     [r11-38h], rax
0x18001bba0  lea     rcx, [r11-48h]; this
0x18001bba4  lea     rax, aCluswmiTaskman; "ClusWmi::TaskManager::ScheduledTask::Ex"...
0x18001bbab  mov     r9b, 1; bool
0x18001bbae  mov     [r11-30h], rax
0x18001bbb2  mov     rax, [rsp+68h+arg_20]
0x18001bbba  mov     [r11-28h], rax
0x18001bbbe  lea     rax, aNanoserverBase_0; "nanoserver\\base\\cluster\\wmiprovider"...
0x18001bbc5  mov     [r11-20h], rax
0x18001bbc9  lea     rax, aFalse; "false"
0x18001bbd0  mov     [r11-18h], rax
0x18001bbd4  call    ?Format@ArgumentWriter@cxl@@QEAAAEAVTextWriter@2@AEAV32@PEBD_N@Z; cxl::ArgumentWriter::Format(cxl::TextWriter &,char const *,bool)
0x18001bbd9  add     rsp, 68h
0x18001bbdd  retn
```
