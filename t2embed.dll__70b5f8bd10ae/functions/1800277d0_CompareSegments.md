# CompareSegments

- ea: `0x1800277d0`
- end: `0x1800277f5`
- name: `CompareSegments`
- size: `37`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800277d0`

## pseudocode

```c
__int64 __fastcall CompareSegments(_WORD *a1, _WORD *a2)
{
  if ( *a1 > *a2 || a1[1] < a2[1] )
    return a1[1] < a2[1] ? -1 : 1;
  else
    return 0;
}

```

## disassembly

```asm
0x1800277d0  movzx   eax, word ptr [rdx]
0x1800277d3  cmp     [rcx], ax
0x1800277d6  ja      short loc_1800277E5
0x1800277d8  movzx   eax, word ptr [rdx+2]
0x1800277dc  cmp     [rcx+2], ax
0x1800277e0  jb      short loc_1800277E5
0x1800277e2  xor     eax, eax
0x1800277e4  retn
0x1800277e5  movzx   eax, word ptr [rdx+2]
0x1800277e9  cmp     [rcx+2], ax
0x1800277ed  sbb     eax, eax
0x1800277ef  and     eax, 0FFFFFFFEh
0x1800277f2  inc     eax
0x1800277f4  retn
```
