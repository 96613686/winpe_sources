# SdbpMergeCompareIndexes

- ea: `0x14001c640`
- end: `0x14001c6c3`
- name: `SdbpMergeCompareIndexes`
- size: `131`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14001c640`

## pseudocode

```c
__int64 __fastcall SdbpMergeCompareIndexes(__int64 *a1, __int64 *a2)
{
  __int64 v2; // r8
  __int64 v3; // r9
  int v4; // ecx
  int v6; // eax
  int v7; // ecx
  int v8; // edx

  v2 = *a1;
  v3 = *a2;
  v4 = *(_DWORD *)(*a1 + 32) & 1;
  if ( (*(_DWORD *)(*a2 + 32) & 1) != v4 )
    return 2 * (v4 ^ 1u) - 1;
  v6 = *(unsigned __int16 *)(v2 + 4);
  if ( (_WORD)v6 != *(_WORD *)(v3 + 4) )
    return v6 - (unsigned int)*(unsigned __int16 *)(v3 + 4);
  v7 = *(unsigned __int16 *)(v2 + 6);
  if ( v7 == 24587 )
  {
    v7 = 0x10000;
  }
  else if ( *(_WORD *)(v2 + 6) == 24608 )
  {
    v7 = 0x20000;
  }
  v8 = *(unsigned __int16 *)(v3 + 6);
  if ( v8 == 24587 )
  {
    v8 = 0x10000;
  }
  else if ( *(_WORD *)(v3 + 6) == 24608 )
  {
    v8 = 0x20000;
  }
  return (unsigned int)(v7 - v8);
}

```

## disassembly

```asm
0x14001c640  mov     r8, [rcx]
0x14001c643  mov     r9, [rdx]
0x14001c646  mov     ecx, [r8+20h]
0x14001c64a  mov     eax, [r9+20h]
0x14001c64e  and     ecx, 1
0x14001c651  and     eax, 1
0x14001c654  cmp     eax, ecx
0x14001c656  jz      short loc_14001C663
0x14001c658  xor     ecx, 1
0x14001c65b  lea     eax, ds:0FFFFFFFFFFFFFFFFh[rcx*2]
0x14001c662  retn
0x14001c663  movzx   eax, word ptr [r8+4]
0x14001c668  cmp     ax, [r9+4]
0x14001c66d  jz      short loc_14001C677
0x14001c66f  movzx   ecx, word ptr [r9+4]
0x14001c674  sub     eax, ecx
0x14001c676  retn
0x14001c677  movzx   ecx, word ptr [r8+6]
0x14001c67c  mov     r10d, 10000h
0x14001c682  mov     edx, ecx
0x14001c684  mov     r11d, 20000h
0x14001c68a  sub     edx, 600Bh
0x14001c690  jz      short loc_14001C69C
0x14001c692  cmp     edx, 15h
0x14001c695  jnz     short loc_14001C69F
0x14001c697  mov     ecx, r11d
0x14001c69a  jmp     short loc_14001C69F
0x14001c69c  mov     ecx, r10d
0x14001c69f  movzx   edx, word ptr [r9+6]
0x14001c6a4  mov     r8d, edx
0x14001c6a7  sub     r8d, 600Bh
0x14001c6ae  jz      short loc_14001C6BB
0x14001c6b0  cmp     r8d, 15h
0x14001c6b4  jnz     short loc_14001C6BE
0x14001c6b6  mov     edx, r11d
0x14001c6b9  jmp     short loc_14001C6BE
0x14001c6bb  mov     edx, r10d
0x14001c6be  sub     ecx, edx
0x14001c6c0  mov     eax, ecx
0x14001c6c2  retn
```
