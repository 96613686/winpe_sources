# SclOSIsValid

- ea: `0x18000de94`
- end: `0x18000dee5`
- name: `SclOSIsValid`
- size: `81`
- prototype: `char __fastcall(__int64)`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x180001de0`
- `0x180002010`
- `0x180002640`
- `0x180002a60`
- `0x180002b98`
- `0x180003374`
- `0x180003408`
- `0x18000438c`
- `0x180004428`
- `0x180004844`
- `0x180005a90`
- `0x180005da0`
- `0x180006484`
- `0x1800065f8`

## callees

- `0x18000de94`

## pseudocode

```c
char __fastcall SclOSIsValid(__int64 a1)
{
  char v2; // dl
  bool v3; // zf

  if ( !a1 )
    return 1;
  v2 = 1;
  if ( !*(_DWORD *)a1 )
    return 0;
  if ( *(_DWORD *)a1 == 1 )
  {
    if ( *(_QWORD *)(a1 + 8)
      || *(_QWORD *)(a1 + 16)
      || *(_QWORD *)(a1 + 24)
      || *(_QWORD *)(a1 + 32)
      || *(_QWORD *)(a1 + 40)
      || *(_QWORD *)(a1 + 48) )
    {
      return 0;
    }
    v3 = *(_QWORD *)(a1 + 56) == 0;
  }
  else
  {
    v3 = *(_DWORD *)a1 == 2;
  }
  if ( !v3 )
    return 0;
  return v2;
}

```

## disassembly

```asm
0x18000de94  xor     r9d, r9d
0x18000de97  test    rcx, rcx
0x18000de9a  jnz     short loc_18000DE9F
0x18000de9c  mov     al, 1
0x18000de9e  retn
0x18000de9f  mov     r8d, [rcx]
0x18000dea2  mov     dl, 1
0x18000dea4  test    r8d, r8d
0x18000dea7  jz      short loc_18000DEDF
0x18000dea9  sub     r8d, 1
0x18000dead  jz      short loc_18000DEB5
0x18000deaf  cmp     r8d, 1
0x18000deb3  jmp     short loc_18000DEDD
0x18000deb5  cmp     [rcx+8], r9
0x18000deb9  jnz     short loc_18000DEDF
0x18000debb  cmp     [rcx+10h], r9
0x18000debf  jnz     short loc_18000DEDF
0x18000dec1  cmp     [rcx+18h], r9
0x18000dec5  jnz     short loc_18000DEDF
0x18000dec7  cmp     [rcx+20h], r9
0x18000decb  jnz     short loc_18000DEDF
0x18000decd  cmp     [rcx+28h], r9
0x18000ded1  jnz     short loc_18000DEDF
0x18000ded3  cmp     [rcx+30h], r9
0x18000ded7  jnz     short loc_18000DEDF
0x18000ded9  cmp     [rcx+38h], r9
0x18000dedd  jz      short loc_18000DEE2
0x18000dedf  mov     dl, r9b
0x18000dee2  mov     al, dl
0x18000dee4  retn
```
