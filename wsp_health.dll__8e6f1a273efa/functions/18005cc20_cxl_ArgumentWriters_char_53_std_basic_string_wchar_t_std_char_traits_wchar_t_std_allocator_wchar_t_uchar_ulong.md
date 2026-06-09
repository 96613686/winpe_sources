# cxl::ArgumentWriters<char [53],std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,uchar,ulong,ulong,ulong,S2DCacheMode,bool>::WriteParam<6>(cxl::TextWriter &,cxl::Format const &,cxl::ConstRefHolder<char [53],std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,uchar,ulong,ulong,ulong,S2DCacheMode,bool> const &)

- ea: `0x18005cc20`
- end: `0x18005cc8a`
- name: `??$WriteParam@$05@?$ArgumentWriters@$$BY0DF@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@EKKKW4S2DCacheMode@@_N@cxl@@SAXAEAVTextWriter@1@AEBUFormat@1@AEBU?$ConstRefHolder@$$BY0DF@DV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@EKKKW4S2DCacheMode@@_N@1@@Z`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18006f2b0`

## callees

- `0x18000e948`
- `0x18000e974`
- `0x18000ee1c`
- `0x18005cc20`

## string_xrefs

- `0x18005cc58`: `ReadWrite`
- `0x18005cc71`: `ReadOnly`
- `0x18005cc46`: `CacheMode({0})`
- `0x18005cc68`: `WriteOnly`

## pseudocode

```c
__int64 __fastcall cxl::ArgumentWriters<char [53],std::wstring,unsigned char,unsigned long,unsigned long,unsigned long,enum S2DCacheMode,bool>::WriteParam<6>(
        struct cxl::TextWriter *a1,
        __int64 a2,
        __int64 a3)
{
  int v3; // edx
  const char *v5; // rdx
  const char *v6; // rdx

  v3 = **(_DWORD **)(a3 + 8);
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
0x18005cc20  sub     rsp, 28h
0x18005cc24  mov     rax, [r8+8]
0x18005cc28  mov     edx, [rax]
0x18005cc2a  test    edx, edx
0x18005cc2c  jz      short loc_18005CC7A
0x18005cc2e  cmp     edx, 4
0x18005cc31  jz      short loc_18005CC71
0x18005cc33  cmp     edx, 8
0x18005cc36  jz      short loc_18005CC68
0x18005cc38  cmp     edx, 0Ch
0x18005cc3b  jz      short loc_18005CC58
0x18005cc3d  mov     [rsp+28h+arg_10], edx
0x18005cc41  lea     r8, [rsp+28h+arg_10]
0x18005cc46  lea     rdx, aCachemode0; "CacheMode({0})"
0x18005cc4d  call    ??$Write@DK$$V@TextWriter@cxl@@QEAAXPEBDAEBK@Z; cxl::TextWriter::Write<char,ulong,>(char const *,ulong const &)
0x18005cc52  add     rsp, 28h
0x18005cc56  retn
0x18005cc58  lea     rdx, aReadwrite; "ReadWrite"
0x18005cc5f  add     rsp, 28h
0x18005cc63  jmp     ??$Write@$09@TextWriter@cxl@@QEAAAEAV01@AEAY09$$CBD@Z; cxl::TextWriter::Write<10>(char const (&)[10])
0x18005cc68  lea     rdx, aWriteonly; "WriteOnly"
0x18005cc6f  jmp     short loc_18005CC5F
0x18005cc71  lea     rdx, aReadonly; "ReadOnly"
0x18005cc78  jmp     short loc_18005CC81
0x18005cc7a  lea     rdx, aDisabled; "Disabled"
0x18005cc81  add     rsp, 28h
0x18005cc85  jmp     ??$Write@$08@TextWriter@cxl@@QEAAAEAV01@AEAY08$$CBD@Z; cxl::TextWriter::Write<9>(char const (&)[9])
```
