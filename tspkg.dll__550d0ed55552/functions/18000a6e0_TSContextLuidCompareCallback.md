# TSContextLuidCompareCallback

- ea: `0x18000a6e0`
- end: `0x18000a6fe`
- name: `TSContextLuidCompareCallback`
- size: `30`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a548`
- `0x18000a5d4`

## callees

- `0x18000a6e0`

## pseudocode

```c
__int64 __fastcall TSContextLuidCompareCallback(_DWORD *a1, __int64 a2)
{
  int v2; // eax

  v2 = a1[1];
  if ( v2 <= *(_DWORD *)(a2 + 28) )
  {
    if ( v2 < *(_DWORD *)(a2 + 28) )
      return 0xFFFFFFFFLL;
    if ( *a1 <= *(_DWORD *)(a2 + 24) )
      return (unsigned int)-(*a1 < *(_DWORD *)(a2 + 24));
  }
  return 1;
}

```

## disassembly

```asm
0x18000a6e0  mov     eax, [rcx+4]
0x18000a6e3  cmp     eax, [rdx+1Ch]
0x18000a6e6  jg      short loc_18000A6F8
0x18000a6e8  jl      short loc_18000A6F4
0x18000a6ea  mov     eax, [rcx]
0x18000a6ec  cmp     eax, [rdx+18h]
0x18000a6ef  ja      short loc_18000A6F8
0x18000a6f1  sbb     eax, eax
0x18000a6f3  retn
0x18000a6f4  or      eax, 0FFFFFFFFh
0x18000a6f7  retn
0x18000a6f8  mov     eax, 1
0x18000a6fd  retn
```
