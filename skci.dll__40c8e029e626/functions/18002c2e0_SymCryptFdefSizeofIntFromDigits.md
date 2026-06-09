# SymCryptFdefSizeofIntFromDigits

- ea: `0x18002c2e0`
- end: `0x18002c2f5`
- name: `SymCryptFdefSizeofIntFromDigits`
- size: `21`
- prototype: ``
- caller_count: `31`
- callee_count: `1`
- tags: ``

## callers

- `0x180022c8c`
- `0x180023030`
- `0x1800231c4`
- `0x180023390`
- `0x180023ce0`
- `0x180023e94`
- `0x180024744`
- `0x1800249c0`
- `0x180024be8`
- `0x1800251cc`
- `0x180025514`
- `0x180025888`
- `0x180026108`
- `0x180027604`
- `0x180027b68`
- `0x180027c78`
- `0x180027e64`
- `0x1800282c0`
- `0x180028790`
- `0x180028e98`
- `0x180029120`
- `0x180029548`
- `0x180029fa0`
- `0x18002a4b0`
- `0x18002b020`
- `0x18002c0f4`
- `0x18002c2b8`
- `0x180030630`
- `0x180031610`
- `0x1800320c0`
- `0x1800323d0`

## callees

- `0x18002c2e0`

## pseudocode

```c
__int64 __fastcall SymCryptFdefSizeofIntFromDigits(int a1)
{
  if ( (unsigned int)(a1 - 1) > 0x7FF )
    return 0;
  else
    return (unsigned int)((a1 << 6) + 32);
}

```

## disassembly

```asm
0x18002c2e0  lea     eax, [rcx-1]
0x18002c2e3  cmp     eax, 7FFh
0x18002c2e8  ja      short loc_18002C2F2
0x18002c2ea  shl     ecx, 6
0x18002c2ed  lea     eax, [rcx+20h]
0x18002c2f0  retn
0x18002c2f2  xor     eax, eax
0x18002c2f4  retn
```
