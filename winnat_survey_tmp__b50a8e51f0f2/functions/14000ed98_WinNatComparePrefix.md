# WinNatComparePrefix

- ea: `0x14000ed98`
- end: `0x14000eddb`
- name: `WinNatComparePrefix`
- size: `67`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140010750`

## callees

- `0x14000ed98`

## pseudocode

```c
bool __fastcall WinNatComparePrefix(_BYTE *a1, _BYTE *a2, unsigned int a3)
{
  while ( a3 > 8 )
  {
    if ( *a1 != *a2 )
      return 0;
    ++a2;
    ++a1;
    a3 -= 8;
  }
  return !a3 || *a1 >> (8 - a3) == *a2 >> (8 - a3);
}

```

## disassembly

```asm
0x14000ed98  mov     r9, rdx
0x14000ed9b  mov     r10d, 8
0x14000eda1  cmp     r8d, r10d
0x14000eda4  jbe     short loc_14000EDBD
0x14000eda6  mov     al, [r9]
0x14000eda9  cmp     [rcx], al
0x14000edab  jnz     short loc_14000EDB9
0x14000edad  inc     r9
0x14000edb0  inc     rcx
0x14000edb3  add     r8d, 0FFFFFFF8h
0x14000edb7  jmp     short loc_14000EDA1
0x14000edb9  xor     al, al
0x14000edbb  retn
0x14000edbd  test    r8d, r8d
0x14000edc0  jz      short loc_14000EDD8
0x14000edc2  mov     dl, [rcx]
0x14000edc4  sub     r10b, r8b
0x14000edc7  mov     al, [r9]
0x14000edca  mov     cl, r10b
0x14000edcd  shr     al, cl
0x14000edcf  shr     dl, cl
0x14000edd1  cmp     dl, al
0x14000edd3  setz    al
0x14000edd6  retn
0x14000edd8  mov     al, 1
0x14000edda  retn
```
