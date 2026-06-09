# SclRegApplyRename

- ea: `0x18000ab90`
- end: `0x18000ac1f`
- name: `SclRegApplyRename`
- size: `143`
- prototype: `__int64 __fastcall(_BYTE *, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000acec`
- `0x18000b21c`
- `0x18000b530`

## callees

- `0x18000ab90`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall SclRegApplyRename(_BYTE *a1, __int64 a2, __int64 a3)
{
  int v5; // r9d
  int v6; // r9d
  __int64 (__fastcall *v7)(HANDLE); // r9
  __int64 v8; // rcx
  __int64 result; // rax

  if ( !a1 )
    return 3221225485LL;
  if ( !a2 )
    return 3221225485LL;
  if ( !a3 )
    return 3221225485LL;
  v5 = *(_DWORD *)(a3 + 8);
  if ( !v5 || !*(_QWORD *)(a3 + 16) || !*(_QWORD *)(a3 + 24) )
    return 3221225485LL;
  v6 = v5 - 1;
  if ( !v6 )
  {
    v7 = SclRegRenameValue;
    v8 = 1216;
    goto LABEL_11;
  }
  if ( v6 != 1 )
    return 3221225485LL;
  v7 = (__int64 (__fastcall *)(HANDLE))&SclRegRenameKey;
  v8 = 1200;
LABEL_11:
  result = 0;
  if ( &a1[v8] )
    ++*(_QWORD *)&a1[v8];
  if ( *a1 )
    return ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD))v7)(a2, *(_QWORD *)(a3 + 16), *(_QWORD *)(a3 + 24));
  return result;
}

```

## disassembly

```asm
0x18000ab90  mov     r10, r8
0x18000ab93  mov     r8, rcx
0x18000ab96  mov     r11, rdx
0x18000ab99  test    rcx, rcx
0x18000ab9c  jz      short loc_18000AC19
0x18000ab9e  test    rdx, rdx
0x18000aba1  jz      short loc_18000AC19
0x18000aba3  test    r10, r10
0x18000aba6  jz      short loc_18000AC19
0x18000aba8  mov     r9d, [r10+8]
0x18000abac  test    r9d, r9d
0x18000abaf  jz      short loc_18000AC19
0x18000abb1  cmp     qword ptr [r10+10h], 0
0x18000abb6  jz      short loc_18000AC19
0x18000abb8  cmp     qword ptr [r10+18h], 0
0x18000abbd  jz      short loc_18000AC19
0x18000abbf  test    r9d, r9d
0x18000abc2  jz      short loc_18000AC19
0x18000abc4  sub     r9d, 1
0x18000abc8  jz      short loc_18000ABDE
0x18000abca  cmp     r9d, 1
0x18000abce  jnz     short loc_18000AC19
0x18000abd0  lea     r9, SclRegRenameKey
0x18000abd7  mov     ecx, 4B0h
0x18000abdc  jmp     short loc_18000ABEA
0x18000abde  lea     r9, SclRegRenameValue
0x18000abe5  mov     ecx, 4C0h
0x18000abea  xor     eax, eax
0x18000abec  lea     rdx, [rcx+r8]
0x18000abf0  test    rdx, rdx
0x18000abf3  jz      short loc_18000AC01
0x18000abf5  mov     rcx, [rdx]
0x18000abf8  inc     rcx
0x18000abfb  mov     [rdx], rcx
0x18000abfe  mov     rcx, [rdx]
0x18000ac01  cmp     [r8], al
0x18000ac04  jz      short locret_18000AC1E
0x18000ac06  mov     r8, [r10+18h]
0x18000ac0a  mov     rcx, r11
0x18000ac0d  mov     rdx, [r10+10h]
0x18000ac11  mov     rax, r9
0x18000ac14  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac19  mov     eax, 0C000000Dh
0x18000ac1e  retn
```
