# cxl::ArgumentWriters<char [52],std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,uchar,ulong,ulong,ulong,S2DCacheMode,unsigned __int64,bool,cxl::DateTime>::WriteParam<6>(cxl::TextWriter &,cxl::Format const &,cxl::ConstRefHolder<char [52],std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,uchar,ulong,ulong,ulong,S2DCacheMode,unsigned __int64,bool,cxl::DateTime> const &)

- ea: `0x18005cbb0`
- end: `0x18005cc1a`
- name: `??$WriteParam@$05@?$ArgumentWriters@$$BY0DE@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@EKKKW4S2DCacheMode@@_K_NUDateTime@cxl@@@cxl@@SAXAEAVTextWriter@1@AEBUFormat@1@AEBU?$ConstRefHolder@$$BY0DE@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@EKKKW4S2DCacheMode@@_K_NUDateTime@cxl@@@1@@Z`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18006ef80`

## callees

- `0x18000e948`
- `0x18000e974`
- `0x18000ee1c`
- `0x18005cbb0`

## string_xrefs

- `0x18005cbe8`: `ReadWrite`
- `0x18005cc01`: `ReadOnly`
- `0x18005cbd6`: `CacheMode({0})`
- `0x18005cbf8`: `WriteOnly`

## pseudocode

```c
__int64 __fastcall cxl::ArgumentWriters<char [52],std::wstring,unsigned char,unsigned long,unsigned long,unsigned long,enum S2DCacheMode,unsigned __int64,bool,cxl::DateTime>::WriteParam<6>(
        struct cxl::TextWriter *a1,
        __int64 a2,
        __int64 a3)
{
  int v3; // edx
  const char *v5; // rdx
  const char *v6; // rdx

  v3 = **(_DWORD **)(a3 + 24);
  switch ( v3 )
  {
    case 0:
      v6 = "Disabled";
      return cxl::TextWriter::Write<9>(a1, v6);
    case 4:
      v6 = "ReadOnly";
      return cxl::TextWriter::Write<9>(a1, v6);
    case 8:
      v5 = "WriteOnly";
      break;
    case 12:
      v5 = "ReadWrite";
      break;
    default:
      return cxl::TextWriter::Write<char,unsigned long,>(a1, "CacheMode({0})");
  }
  return cxl::TextWriter::Write<10>(a1, v5);
}

```

## disassembly

```asm
0x18005cbb0  sub     rsp, 28h
0x18005cbb4  mov     rax, [r8+18h]
0x18005cbb8  mov     edx, [rax]
0x18005cbba  test    edx, edx
0x18005cbbc  jz      short loc_18005CC0A
0x18005cbbe  cmp     edx, 4
0x18005cbc1  jz      short loc_18005CC01
0x18005cbc3  cmp     edx, 8
0x18005cbc6  jz      short loc_18005CBF8
0x18005cbc8  cmp     edx, 0Ch
0x18005cbcb  jz      short loc_18005CBE8
0x18005cbcd  mov     [rsp+28h+arg_10], edx
0x18005cbd1  lea     r8, [rsp+28h+arg_10]
0x18005cbd6  lea     rdx, aCachemode0; "CacheMode({0})"
0x18005cbdd  call    ??$Write@DK$$V@TextWriter@cxl@@QEAAXPEBDAEBK@Z; cxl::TextWriter::Write<char,ulong,>(char const *,ulong const &)
0x18005cbe2  add     rsp, 28h
0x18005cbe6  retn
0x18005cbe8  lea     rdx, aReadwrite; "ReadWrite"
0x18005cbef  add     rsp, 28h
0x18005cbf3  jmp     ??$Write@$09@TextWriter@cxl@@QEAAAEAV01@AEAY09$$CBD@Z; cxl::TextWriter::Write<10>(char const (&)[10])
0x18005cbf8  lea     rdx, aWriteonly; "WriteOnly"
0x18005cbff  jmp     short loc_18005CBEF
0x18005cc01  lea     rdx, aReadonly; "ReadOnly"
0x18005cc08  jmp     short loc_18005CC11
0x18005cc0a  lea     rdx, aDisabled; "Disabled"
0x18005cc11  add     rsp, 28h
0x18005cc15  jmp     ??$Write@$08@TextWriter@cxl@@QEAAAEAV01@AEAY08$$CBD@Z; cxl::TextWriter::Write<9>(char const (&)[9])
```
