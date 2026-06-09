# SwapWordCopy

- ea: `0x18001b3b8`
- end: `0x18001b3f0`
- name: `SwapWordCopy`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001acbc`

## callees

- `0x18001b3b8`

## pseudocode

```c
__int64 __fastcall SwapWordCopy(__int64 a1, __int64 a2, unsigned __int16 a3)
{
  unsigned __int16 v3; // r9
  __int64 result; // rax
  __int64 v6; // r8

  v3 = 0;
  for ( result = 0; v3 < a3; *(_WORD *)(a1 + 2 * v6) = _byteswap_ushort(*(_WORD *)(a2 + 2 * v6)) )
  {
    v6 = v3++;
    result = *(unsigned __int8 *)(a2 + 2 * v6 + 1);
  }
  return result;
}

```

## disassembly

```asm
0x18001b3b8  xor     r9d, r9d
0x18001b3bb  xor     eax, eax
0x18001b3bd  movzx   r10d, r8w
0x18001b3c1  mov     r11, rcx
0x18001b3c4  cmp     ax, r8w
0x18001b3c8  jnb     short locret_18001B3EF
0x18001b3ca  movzx   r8d, r9w
0x18001b3ce  inc     r9w
0x18001b3d2  movzx   ecx, byte ptr [rdx+r8*2]
0x18001b3d7  movzx   eax, byte ptr [rdx+r8*2+1]
0x18001b3dd  shl     cx, 8
0x18001b3e1  or      cx, ax
0x18001b3e4  mov     [r11+r8*2], cx
0x18001b3e9  cmp     r9w, r10w
0x18001b3ed  jb      short loc_18001B3CA
0x18001b3ef  retn
```
