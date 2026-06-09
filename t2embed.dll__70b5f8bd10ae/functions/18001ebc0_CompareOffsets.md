# CompareOffsets

- ea: `0x18001ebc0`
- end: `0x18001ec17`
- name: `CompareOffsets`
- size: `87`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001ebc0`

## pseudocode

```c
__int64 __fastcall CompareOffsets(unsigned __int8 *a1, unsigned __int8 *a2)
{
  unsigned int v2; // r8d
  unsigned int v3; // ecx

  v2 = a1[11] | ((a1[10] | ((a1[9] | (a1[8] << 8)) << 8)) << 8);
  v3 = a2[11] | ((a2[10] | ((a2[9] | (a2[8] << 8)) << 8)) << 8);
  if ( v2 >= v3 )
    return v2 != v3;
  else
    return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x18001ebc0  movzx   eax, byte ptr [rcx+9]
0x18001ebc4  movzx   r8d, byte ptr [rcx+8]
0x18001ebc9  shl     r8d, 8
0x18001ebcd  or      r8d, eax
0x18001ebd0  movzx   eax, byte ptr [rcx+0Ah]
0x18001ebd4  shl     r8d, 8
0x18001ebd8  or      r8d, eax
0x18001ebdb  movzx   eax, byte ptr [rcx+0Bh]
0x18001ebdf  movzx   ecx, byte ptr [rdx+8]
0x18001ebe3  shl     ecx, 8
0x18001ebe6  shl     r8d, 8
0x18001ebea  or      r8d, eax
0x18001ebed  movzx   eax, byte ptr [rdx+9]
0x18001ebf1  or      ecx, eax
0x18001ebf3  movzx   eax, byte ptr [rdx+0Ah]
0x18001ebf7  shl     ecx, 8
0x18001ebfa  or      ecx, eax
0x18001ebfc  movzx   eax, byte ptr [rdx+0Bh]
0x18001ec00  shl     ecx, 8
0x18001ec03  or      ecx, eax
0x18001ec05  cmp     r8d, ecx
0x18001ec08  jnb     short loc_18001EC0E
0x18001ec0a  or      eax, 0FFFFFFFFh
0x18001ec0d  retn
0x18001ec0e  xor     eax, eax
0x18001ec10  cmp     r8d, ecx
0x18001ec13  setnz   al
0x18001ec16  retn
```
