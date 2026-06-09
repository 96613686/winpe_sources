# SymCryptFdefRawIsEqualUint32

- ea: `0x18002c284`
- end: `0x18002c2b1`
- name: `SymCryptFdefRawIsEqualUint32`
- size: `45`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180022c8c`
- `0x180023e94`
- `0x180024ac0`
- `0x180024be8`
- `0x180025888`
- `0x180028790`
- `0x180028e98`
- `0x180029fa0`
- `0x18002a4b0`
- `0x18002b020`
- `0x18002b700`

## callees

- `0x18002c284`

## pseudocode

```c
__int64 __fastcall SymCryptFdefRawIsEqualUint32(_DWORD *a1, int a2, int a3)
{
  unsigned int v3; // r8d
  unsigned int v4; // r9d
  unsigned int v5; // edx
  __int64 v6; // rax

  v3 = *a1 ^ a3;
  v4 = 1;
  v5 = 16 * a2;
  if ( v5 > 1 )
  {
    do
    {
      v6 = v4++;
      v3 |= a1[v6];
    }
    while ( v4 < v5 );
  }
  return (unsigned int)~((unsigned __int64)-(__int64)v3 >> 32);
}

```

## disassembly

```asm
0x18002c284  xor     r8d, [rcx]
0x18002c287  mov     r9d, 1
0x18002c28d  shl     edx, 4
0x18002c290  cmp     edx, r9d
0x18002c293  jbe     short loc_18002C2A4
0x18002c295  mov     eax, r9d
0x18002c298  inc     r9d
0x18002c29b  or      r8d, [rcx+rax*4]
0x18002c29f  cmp     r9d, edx
0x18002c2a2  jb      short loc_18002C295
0x18002c2a4  mov     eax, r8d
0x18002c2a7  neg     rax
0x18002c2aa  shr     rax, 20h
0x18002c2ae  not     eax
0x18002c2b0  retn
```
