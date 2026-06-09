# CControlPacket::GetString(ushort const *,ushort const *,ulong,ushort * *)

- ea: `0x1800120c8`
- end: `0x180012104`
- name: `?GetString@CControlPacket@@QEAAKPEBG0KPEAPEAG@Z`
- size: `60`
- prototype: `unsigned int __fastcall(CControlPacket *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int16 **)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010c74`
- `0x180013b90`
- `0x180015094`
- `0x18001518c`
- `0x1800151c8`
- `0x1800152b4`

## callees

- `0x180011bd4`
- `0x1800120c8`

## import_xrefs

- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x1800120f2`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x1800120f2`

## pseudocode

```c
unsigned int __fastcall CControlPacket::GetString(
        CControlPacket *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 **a5)
{
  unsigned int result; // eax
  int v6; // [rsp+20h] [rbp-38h]
  int v7; // [rsp+28h] [rbp-30h]
  int v8; // [rsp+30h] [rbp-28h]
  const unsigned __int16 *v9; // [rsp+40h] [rbp-18h] BYREF

  v9 = 0;
  result = CControlPacket::GetVariable<unsigned short>(this, a2, a3, a4, v6, v7, v8, (__int64)&v9);
  if ( !result )
    return DuplicateStringW(v9, a5);
  return result;
}

```

## disassembly

```asm
0x1800120c8  sub     rsp, 58h
0x1800120cc  and     [rsp+58h+var_18], 0
0x1800120d2  lea     rax, [rsp+58h+var_18]
0x1800120d7  mov     [rsp+58h+var_20], rax
0x1800120dc  call    ??$GetVariable@G@CControlPacket@@QEAAKPEBG0KKKKPEAPEAG@Z; CControlPacket::GetVariable<ushort>(ushort const *,ushort const *,ulong,ulong,ulong,ulong,ushort * *)
0x1800120e1  test    eax, eax
0x1800120e3  jnz     short loc_1800120FE
0x1800120e5  mov     rdx, [rsp+58h+arg_20]
0x1800120ed  mov     rcx, [rsp+58h+var_18]
0x1800120f2  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x1800120f9  nop     dword ptr [rax+rax+00h]
0x1800120fe  add     rsp, 58h
0x180012102  retn
```
