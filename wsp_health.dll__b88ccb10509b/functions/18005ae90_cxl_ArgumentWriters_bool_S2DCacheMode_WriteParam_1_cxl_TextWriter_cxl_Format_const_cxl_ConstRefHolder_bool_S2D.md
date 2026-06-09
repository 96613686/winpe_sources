# cxl::ArgumentWriters<bool,S2DCacheMode>::WriteParam<1>(cxl::TextWriter &,cxl::Format const &,cxl::ConstRefHolder<bool,S2DCacheMode> const &)

- ea: `0x18005ae90`
- end: `0x18005aef8`
- name: `??$WriteParam@$00@?$ArgumentWriters@_NW4S2DCacheMode@@@cxl@@SAXAEAVTextWriter@1@AEBUFormat@1@AEBU?$ConstRefHolder@_NW4S2DCacheMode@@@1@@Z`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18006e0f0`

## callees

- `0x18000e4b8`
- `0x18000e4e4`
- `0x18000e98c`
- `0x18005ae90`

## string_xrefs

- `0x18005aec6`: `ReadWrite`
- `0x18005aedf`: `ReadOnly`
- `0x18005aeb5`: `CacheMode({0})`
- `0x18005aed6`: `WriteOnly`

## pseudocode

```c
struct cxl::TextWriter *__fastcall cxl::ArgumentWriters<bool,enum S2DCacheMode>::WriteParam<1>(
        struct cxl::TextWriter *a1,
        __int64 a2,
        int **a3)
{
  int v3; // edx
  const char *v5; // rdx
  const char *v6; // rdx
  int v7; // [rsp+40h] [rbp+18h] BYREF

  v3 = **a3;
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
      v7 = **a3;
      return cxl::TextWriter::Write<char,unsigned long,>(a1, "CacheMode({0})", (__int64)&v7);
  }
  return (struct cxl::TextWriter *)cxl::TextWriter::Write<10>((__int64)a1, (__int64)v5);
}

```

## disassembly

```asm
0x18005ae90  sub     rsp, 28h
0x18005ae94  mov     rax, [r8]
0x18005ae97  mov     edx, [rax]
0x18005ae99  test    edx, edx
0x18005ae9b  jz      short loc_18005AEE8
0x18005ae9d  cmp     edx, 4
0x18005aea0  jz      short loc_18005AEDF
0x18005aea2  cmp     edx, 8
0x18005aea5  jz      short loc_18005AED6
0x18005aea7  cmp     edx, 0Ch
0x18005aeaa  jz      short loc_18005AEC6
0x18005aeac  mov     [rsp+28h+arg_10], edx
0x18005aeb0  lea     r8, [rsp+28h+arg_10]
0x18005aeb5  lea     rdx, aCachemode0; "CacheMode({0})"
0x18005aebc  call    ??$Write@DK$$V@TextWriter@cxl@@QEAAXPEBDAEBK@Z; cxl::TextWriter::Write<char,ulong,>(char const *,ulong const &)
0x18005aec1  add     rsp, 28h
0x18005aec5  retn
0x18005aec6  lea     rdx, aReadwrite; "ReadWrite"
0x18005aecd  add     rsp, 28h
0x18005aed1  jmp     ??$Write@$09@TextWriter@cxl@@QEAAAEAV01@AEAY09$$CBD@Z; cxl::TextWriter::Write<10>(char const (&)[10])
0x18005aed6  lea     rdx, aWriteonly; "WriteOnly"
0x18005aedd  jmp     short loc_18005AECD
0x18005aedf  lea     rdx, aReadonly; "ReadOnly"
0x18005aee6  jmp     short loc_18005AEEF
0x18005aee8  lea     rdx, aDisabled; "Disabled"
0x18005aeef  add     rsp, 28h
0x18005aef3  jmp     ??$Write@$08@TextWriter@cxl@@QEAAAEAV01@AEAY08$$CBD@Z; cxl::TextWriter::Write<9>(char const (&)[9])
```
