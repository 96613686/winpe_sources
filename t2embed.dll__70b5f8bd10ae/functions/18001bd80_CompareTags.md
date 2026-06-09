# CompareTags

- ea: `0x18001bd80`
- end: `0x18001bdd5`
- name: `CompareTags`
- size: `85`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001bd80`

## pseudocode

```c
__int64 __fastcall CompareTags(unsigned __int8 *a1, unsigned __int8 *a2)
{
  unsigned int v2; // r8d
  unsigned int v3; // ecx

  v2 = a1[3] | ((a1[2] | ((a1[1] | (*a1 << 8)) << 8)) << 8);
  v3 = a2[3] | ((a2[2] | ((a2[1] | (*a2 << 8)) << 8)) << 8);
  if ( v2 >= v3 )
    return v2 != v3;
  else
    return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x18001bd80  movzx   eax, byte ptr [rcx+1]
0x18001bd84  movzx   r8d, byte ptr [rcx]
0x18001bd88  shl     r8d, 8
0x18001bd8c  or      r8d, eax
0x18001bd8f  movzx   eax, byte ptr [rcx+2]
0x18001bd93  shl     r8d, 8
0x18001bd97  or      r8d, eax
0x18001bd9a  movzx   eax, byte ptr [rcx+3]
0x18001bd9e  movzx   ecx, byte ptr [rdx]
0x18001bda1  shl     ecx, 8
0x18001bda4  shl     r8d, 8
0x18001bda8  or      r8d, eax
0x18001bdab  movzx   eax, byte ptr [rdx+1]
0x18001bdaf  or      ecx, eax
0x18001bdb1  movzx   eax, byte ptr [rdx+2]
0x18001bdb5  shl     ecx, 8
0x18001bdb8  or      ecx, eax
0x18001bdba  movzx   eax, byte ptr [rdx+3]
0x18001bdbe  shl     ecx, 8
0x18001bdc1  or      ecx, eax
0x18001bdc3  cmp     r8d, ecx
0x18001bdc6  jnb     short loc_18001BDCC
0x18001bdc8  or      eax, 0FFFFFFFFh
0x18001bdcb  retn
0x18001bdcc  xor     eax, eax
0x18001bdce  cmp     r8d, ecx
0x18001bdd1  setnz   al
0x18001bdd4  retn
```
