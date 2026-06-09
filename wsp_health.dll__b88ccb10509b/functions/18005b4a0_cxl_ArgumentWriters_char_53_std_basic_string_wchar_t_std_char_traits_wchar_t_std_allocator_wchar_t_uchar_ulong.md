# cxl::ArgumentWriters<char [53],std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,uchar,ulong,ulong,ulong,S2DCacheMode,bool>::WriteParam<6>(cxl::TextWriter &,cxl::Format const &,cxl::ConstRefHolder<char [53],std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,uchar,ulong,ulong,ulong,S2DCacheMode,bool> const &)

- ea: `0x18005b4a0`
- end: `0x18005b509`
- name: `??$WriteParam@$05@?$ArgumentWriters@$$BY0DF@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@EKKKW4S2DCacheMode@@_N@cxl@@SAXAEAVTextWriter@1@AEBUFormat@1@AEBU?$ConstRefHolder@$$BY0DF@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@EKKKW4S2DCacheMode@@_N@1@@Z`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18006da30`

## callees

- `0x18000e4b8`
- `0x18000e4e4`
- `0x18000e98c`
- `0x18005b4a0`

## string_xrefs

- `0x18005b4d7`: `ReadWrite`
- `0x18005b4f0`: `ReadOnly`
- `0x18005b4c6`: `CacheMode({0})`
- `0x18005b4e7`: `WriteOnly`

## pseudocode

```c
struct cxl::TextWriter *__fastcall cxl::ArgumentWriters<char [53],std::wstring,unsigned char,unsigned long,unsigned long,unsigned long,enum S2DCacheMode,bool>::WriteParam<6>(
        struct cxl::TextWriter *a1,
        __int64 a2,
        __int64 a3)
{
  int v3; // edx
  const char *v5; // rdx
  const char *v6; // rdx
  int v7; // [rsp+40h] [rbp+18h] BYREF

  v3 = **(_DWORD **)(a3 + 8);
  switch ( v3 )
  {
    case 0:
      v6 = "Disabled";
      return (struct cxl::TextWriter *)cxl::TextWriter::Write<9>((__int64)a1, (__int64)v6);
    case 4:
      v6 = "ReadOnly";
      return (struct cxl::TextWriter *)cxl::TextWriter::Write<9>((__int64)a1, (__int64)v6);
    case 8:
      v5 = "WriteOnly";
      break;
    case 12:
      v5 = "ReadWrite";
      break;
    default:
      v7 = **(_DWORD **)(a3 + 8);
      return cxl::TextWriter::Write<char,unsigned long,>(a1, "CacheMode({0})", (__int64)&v7);
  }
  return (struct cxl::TextWriter *)cxl::TextWriter::Write<10>((__int64)a1, (__int64)v5);
}

```

## disassembly

```asm
0x18005b4a0  sub     rsp, 28h
0x18005b4a4  mov     rax, [r8+8]
0x18005b4a8  mov     edx, [rax]
0x18005b4aa  test    edx, edx
0x18005b4ac  jz      short loc_18005B4F9
0x18005b4ae  cmp     edx, 4
0x18005b4b1  jz      short loc_18005B4F0
0x18005b4b3  cmp     edx, 8
0x18005b4b6  jz      short loc_18005B4E7
0x18005b4b8  cmp     edx, 0Ch
0x18005b4bb  jz      short loc_18005B4D7
0x18005b4bd  mov     [rsp+28h+arg_10], edx
0x18005b4c1  lea     r8, [rsp+28h+arg_10]
0x18005b4c6  lea     rdx, aCachemode0; "CacheMode({0})"
0x18005b4cd  call    ??$Write@DK$$V@TextWriter@cxl@@QEAAXPEBDAEBK@Z; cxl::TextWriter::Write<char,ulong,>(char const *,ulong const &)
0x18005b4d2  add     rsp, 28h
0x18005b4d6  retn
0x18005b4d7  lea     rdx, aReadwrite; "ReadWrite"
0x18005b4de  add     rsp, 28h
0x18005b4e2  jmp     ??$Write@$09@TextWriter@cxl@@QEAAAEAV01@AEAY09$$CBD@Z; cxl::TextWriter::Write<10>(char const (&)[10])
0x18005b4e7  lea     rdx, aWriteonly; "WriteOnly"
0x18005b4ee  jmp     short loc_18005B4DE
0x18005b4f0  lea     rdx, aReadonly; "ReadOnly"
0x18005b4f7  jmp     short loc_18005B500
0x18005b4f9  lea     rdx, aDisabled; "Disabled"
0x18005b500  add     rsp, 28h
0x18005b504  jmp     ??$Write@$08@TextWriter@cxl@@QEAAAEAV01@AEAY08$$CBD@Z; cxl::TextWriter::Write<9>(char const (&)[9])
```
