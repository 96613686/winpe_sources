# cxl::ArgumentWriters<bool,S2DCacheMode>::WriteParam<1>(cxl::TextWriter &,cxl::Format const &,cxl::ConstRefHolder<bool,S2DCacheMode> const &)

- ea: `0x18005c610`
- end: `0x18005c679`
- name: `??$WriteParam@$00@?$ArgumentWriters@_NW4S2DCacheMode@@@cxl@@SAXAEAVTextWriter@1@AEBUFormat@1@AEBU?$ConstRefHolder@_NW4S2DCacheMode@@@1@@Z`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18006f970`

## callees

- `0x18000e948`
- `0x18000e974`
- `0x18000ee1c`
- `0x18005c610`

## string_xrefs

- `0x18005c647`: `ReadWrite`
- `0x18005c660`: `ReadOnly`
- `0x18005c635`: `CacheMode({0})`
- `0x18005c657`: `WriteOnly`

## pseudocode

```c
__int64 __fastcall cxl::ArgumentWriters<bool,enum S2DCacheMode>::WriteParam<1>(
        struct cxl::TextWriter *a1,
        __int64 a2,
        int **a3)
{
  int v3; // edx
  const char *v5; // rdx
  const char *v6; // rdx

  v3 = **a3;
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
0x18005c610  sub     rsp, 28h
0x18005c614  mov     rax, [r8]
0x18005c617  mov     edx, [rax]
0x18005c619  test    edx, edx
0x18005c61b  jz      short loc_18005C669
0x18005c61d  cmp     edx, 4
0x18005c620  jz      short loc_18005C660
0x18005c622  cmp     edx, 8
0x18005c625  jz      short loc_18005C657
0x18005c627  cmp     edx, 0Ch
0x18005c62a  jz      short loc_18005C647
0x18005c62c  mov     [rsp+28h+arg_10], edx
0x18005c630  lea     r8, [rsp+28h+arg_10]
0x18005c635  lea     rdx, aCachemode0; "CacheMode({0})"
0x18005c63c  call    ??$Write@DK$$V@TextWriter@cxl@@QEAAXPEBDAEBK@Z; cxl::TextWriter::Write<char,ulong,>(char const *,ulong const &)
0x18005c641  add     rsp, 28h
0x18005c645  retn
0x18005c647  lea     rdx, aReadwrite; "ReadWrite"
0x18005c64e  add     rsp, 28h
0x18005c652  jmp     ??$Write@$09@TextWriter@cxl@@QEAAAEAV01@AEAY09$$CBD@Z; cxl::TextWriter::Write<10>(char const (&)[10])
0x18005c657  lea     rdx, aWriteonly; "WriteOnly"
0x18005c65e  jmp     short loc_18005C64E
0x18005c660  lea     rdx, aReadonly; "ReadOnly"
0x18005c667  jmp     short loc_18005C670
0x18005c669  lea     rdx, aDisabled; "Disabled"
0x18005c670  add     rsp, 28h
0x18005c674  jmp     ??$Write@$08@TextWriter@cxl@@QEAAAEAV01@AEAY08$$CBD@Z; cxl::TextWriter::Write<9>(char const (&)[9])
```
