# cxl::ArgumentWriters<char [52],std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,uchar,ulong,ulong,ulong,S2DCacheMode,unsigned __int64,bool,cxl::DateTime>::WriteParam<6>(cxl::TextWriter &,cxl::Format const &,cxl::ConstRefHolder<char [52],std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,uchar,ulong,ulong,ulong,S2DCacheMode,unsigned __int64,bool,cxl::DateTime> const &)

- ea: `0x18005b430`
- end: `0x18005b499`
- name: `??$WriteParam@$05@?$ArgumentWriters@$$BY0DE@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@EKKKW4S2DCacheMode@@_K_NUDateTime@cxl@@@cxl@@SAXAEAVTextWriter@1@AEBUFormat@1@AEBU?$ConstRefHolder@$$BY0DE@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@EKKKW4S2DCacheMode@@_K_NUDateTime@cxl@@@1@@Z`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18006d700`

## callees

- `0x18000e4b8`
- `0x18000e4e4`
- `0x18000e98c`
- `0x18005b430`

## string_xrefs

- `0x18005b467`: `ReadWrite`
- `0x18005b480`: `ReadOnly`
- `0x18005b456`: `CacheMode({0})`
- `0x18005b477`: `WriteOnly`

## pseudocode

```c
struct cxl::TextWriter *__fastcall cxl::ArgumentWriters<char [52],std::wstring,unsigned char,unsigned long,unsigned long,unsigned long,enum S2DCacheMode,unsigned __int64,bool,cxl::DateTime>::WriteParam<6>(
        struct cxl::TextWriter *a1,
        __int64 a2,
        __int64 a3)
{
  int v3; // edx
  const char *v5; // rdx
  const char *v6; // rdx
  int v7; // [rsp+40h] [rbp+18h] BYREF

  v3 = **(_DWORD **)(a3 + 24);
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
      v7 = **(_DWORD **)(a3 + 24);
      return cxl::TextWriter::Write<char,unsigned long,>(a1, "CacheMode({0})", (__int64)&v7);
  }
  return (struct cxl::TextWriter *)cxl::TextWriter::Write<10>((__int64)a1, (__int64)v5);
}

```

## disassembly

```asm
0x18005b430  sub     rsp, 28h
0x18005b434  mov     rax, [r8+18h]
0x18005b438  mov     edx, [rax]
0x18005b43a  test    edx, edx
0x18005b43c  jz      short loc_18005B489
0x18005b43e  cmp     edx, 4
0x18005b441  jz      short loc_18005B480
0x18005b443  cmp     edx, 8
0x18005b446  jz      short loc_18005B477
0x18005b448  cmp     edx, 0Ch
0x18005b44b  jz      short loc_18005B467
0x18005b44d  mov     [rsp+28h+arg_10], edx
0x18005b451  lea     r8, [rsp+28h+arg_10]
0x18005b456  lea     rdx, aCachemode0; "CacheMode({0})"
0x18005b45d  call    ??$Write@DK$$V@TextWriter@cxl@@QEAAXPEBDAEBK@Z; cxl::TextWriter::Write<char,ulong,>(char const *,ulong const &)
0x18005b462  add     rsp, 28h
0x18005b466  retn
0x18005b467  lea     rdx, aReadwrite; "ReadWrite"
0x18005b46e  add     rsp, 28h
0x18005b472  jmp     ??$Write@$09@TextWriter@cxl@@QEAAAEAV01@AEAY09$$CBD@Z; cxl::TextWriter::Write<10>(char const (&)[10])
0x18005b477  lea     rdx, aWriteonly; "WriteOnly"
0x18005b47e  jmp     short loc_18005B46E
0x18005b480  lea     rdx, aReadonly; "ReadOnly"
0x18005b487  jmp     short loc_18005B490
0x18005b489  lea     rdx, aDisabled; "Disabled"
0x18005b490  add     rsp, 28h
0x18005b494  jmp     ??$Write@$08@TextWriter@cxl@@QEAAAEAV01@AEAY08$$CBD@Z; cxl::TextWriter::Write<9>(char const (&)[9])
```
