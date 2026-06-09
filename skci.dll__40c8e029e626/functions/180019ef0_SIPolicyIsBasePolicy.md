# SIPolicyIsBasePolicy

- ea: `0x180019ef0`
- end: `0x180019f38`
- name: `SIPolicyIsBasePolicy`
- size: `72`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001961c`
- `0x18001c0a8`
- `0x18001c380`
- `0x18001c7f0`
- `0x18002056c`
- `0x180020880`
- `0x180047a80`
- `0x1800492f8`
- `0x180049860`
- `0x18004e5b8`

## callees

- `0x180019ef0`

## pseudocode

```c
bool __fastcall SIPolicyIsBasePolicy(__int64 a1)
{
  unsigned int v1; // eax
  _QWORD *v2; // r8
  _QWORD *v3; // rdx
  __int64 v4; // rcx

  v1 = *(_DWORD *)(a1 + 40);
  v2 = (_QWORD *)(a1 + (-(__int64)(v1 < 6) & 0xFFFFFFFFFFFFFD40uLL) + 720);
  v3 = (_QWORD *)(a1 + 704 + (-(__int64)(v1 < 6) & 0xFFFFFFFFFFFFFD50uLL));
  v4 = *v3 - *v2;
  if ( *v3 == *v2 )
    v4 = v3[1] - v2[1];
  return v4 == 0;
}

```

## disassembly

```asm
0x180019ef0  mov     eax, [rcx+28h]
0x180019ef3  cmp     eax, 6
0x180019ef6  sbb     r8, r8
0x180019ef9  and     r8, 0FFFFFFFFFFFFFD40h
0x180019f00  add     r8, 2D0h
0x180019f07  add     r8, rcx
0x180019f0a  cmp     eax, 6
0x180019f0d  sbb     rdx, rdx
0x180019f10  add     rcx, 2C0h
0x180019f17  and     rdx, 0FFFFFFFFFFFFFD50h
0x180019f1e  add     rdx, rcx
0x180019f21  mov     rcx, [rdx]
0x180019f24  sub     rcx, [r8]
0x180019f27  jnz     short loc_180019F31
0x180019f29  mov     rcx, [rdx+8]
0x180019f2d  sub     rcx, [r8+8]
0x180019f31  test    rcx, rcx
0x180019f34  setz    al
0x180019f37  retn
```
