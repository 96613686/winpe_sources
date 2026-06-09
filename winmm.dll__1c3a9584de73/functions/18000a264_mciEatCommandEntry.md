# mciEatCommandEntry

- ea: `0x18000a264`
- end: `0x18000a297`
- name: `mciEatCommandEntry`
- size: `51`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010504`
- `0x180011610`
- `0x180012364`
- `0x1800127ac`
- `0x180012f30`
- `0x180013408`

## callees

- `0x18000a264`

## pseudocode

```c
__int64 __fastcall mciEatCommandEntry(_WORD *a1, _DWORD *a2, _DWORD *a3)
{
  _WORD *v3; // r9
  unsigned __int16 *v5; // rax

  v3 = a1;
  while ( *v3++ )
    ;
  if ( a2 )
    *a2 = *(_DWORD *)v3;
  v5 = v3 + 2;
  if ( a3 )
    *a3 = *v5;
  return (unsigned int)((_DWORD)v5 - (_DWORD)a1 + 2);
}

```

## disassembly

```asm
0x18000a264  mov     r10, rcx
0x18000a267  mov     r9, rcx
0x18000a26a  movzx   eax, word ptr [r9]
0x18000a26e  lea     r9, [r9+2]
0x18000a272  test    ax, ax
0x18000a275  jnz     short loc_18000A26A
0x18000a277  test    rdx, rdx
0x18000a27a  jz      short loc_18000A281
0x18000a27c  mov     eax, [r9]
0x18000a27f  mov     [rdx], eax
0x18000a281  lea     rax, [r9+4]
0x18000a285  test    r8, r8
0x18000a288  jz      short loc_18000A290
0x18000a28a  movzx   ecx, word ptr [rax]
0x18000a28d  mov     [r8], ecx
0x18000a290  sub     eax, r10d
0x18000a293  add     eax, 2
0x18000a296  retn
```
