# cxl::TextWriter::WriteLine<char,char [24],char [61],int,char [46],ulong>(char const *,char const (&)[24],char const (&)[61],int const &,char const (&)[46],ulong const &)

- ea: `0x180016fbc`
- end: `0x18001702b`
- name: `??$WriteLine@D$$BY0BI@D$$BY0DN@DH$$BY0CO@DK@TextWriter@cxl@@QEAAXPEBDAEAY0BI@$$CBDAEAY0DN@$$CBDAEBHAEAY0CO@$$CBDAEBK@Z`
- size: `111`
- prototype: `__int64 __usercall@<rax>(struct cxl::TextWriter *@<rcx>, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001a364`

## callees

- `0x1800109bc`

## string_xrefs

- `0x180016ff0`: `ClusWmi::DataStore::MonitorThread::Initialize`
- `0x18001700a`: `nanoserver\base\cluster\wmiprovider\common\lib\datastore.cpp`

## pseudocode

```c
struct cxl::TextWriter *__fastcall cxl::TextWriter::WriteLine<char,char [24],char [61],int,char [46],unsigned long>(
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
  v8 = &cxl::ArgumentWriters<char [24],char [61],int,char [46],unsigned long>::`vftable';
  v10 = a7;
  v11 = "ClusWmi::DataStore::MonitorThread::Initialize";
  v12 = a5;
  v13 = "nanoserver\\base\\cluster\\wmiprovider\\common\\lib\\datastore.cpp";
  v14 = "m_ptrMonitor != nullptr";
  return cxl::ArgumentWriter::Format(
           (cxl::ArgumentWriter *)&v8,
           a1,
           "BUGCHECK: \"{0}\"; module: \"{1}\"; line: {2}; function: \"{3}\"; error \"{4}\"",
           1);
}

```

## disassembly

```asm
0x180016fbc  mov     r11, rsp
0x180016fbf  sub     rsp, 68h
0x180016fc3  mov     [rsp+68h+var_40], 5
0x180016fcb  lea     rax, ??_7?$ArgumentWriters@$$BY0BI@D$$BY0DN@DH$$BY0CO@DK@cxl@@6B@; const cxl::ArgumentWriters<char [24],char [61],int,char [46],ulong>::`vftable'
0x180016fd2  mov     [r11-48h], rax
0x180016fd6  lea     r8, aBugcheck0Modul; "BUGCHECK: \"{0}\"; module: \"{1}\"; lin"...
0x180016fdd  mov     rax, [rsp+68h+arg_30]
0x180016fe5  mov     rdx, rcx; struct cxl::TextWriter *
0x180016fe8  mov     [r11-38h], rax
0x180016fec  lea     rcx, [r11-48h]; this
0x180016ff0  lea     rax, aCluswmiDatasto; "ClusWmi::DataStore::MonitorThread::Init"...
0x180016ff7  mov     r9b, 1; bool
0x180016ffa  mov     [r11-30h], rax
0x180016ffe  mov     rax, [rsp+68h+arg_20]
0x180017006  mov     [r11-28h], rax
0x18001700a  lea     rax, aNanoserverBase; "nanoserver\\base\\cluster\\wmiprovider"...
0x180017011  mov     [r11-20h], rax
0x180017015  lea     rax, aMPtrmonitorNul; "m_ptrMonitor != nullptr"
0x18001701c  mov     [r11-18h], rax
0x180017020  call    ?Format@ArgumentWriter@cxl@@QEAAAEAVTextWriter@2@AEAV32@PEBD_N@Z; cxl::ArgumentWriter::Format(cxl::TextWriter &,char const *,bool)
0x180017025  add     rsp, 68h
0x180017029  retn
```
