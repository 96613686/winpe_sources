# SymCryptSizeofEcpointEx

- ea: `0x180029ca8`
- end: `0x180029cbb`
- name: `SymCryptSizeofEcpointEx`
- size: `19`
- prototype: ``
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x180024744`
- `0x1800249c0`
- `0x180024ac0`
- `0x180024be8`
- `0x1800251cc`
- `0x180025888`
- `0x180026108`
- `0x180029420`
- `0x180029548`
- `0x180029fa0`
- `0x18002a4b0`
- `0x18002ab10`
- `0x18002efe8`
- `0x18002f1c0`
- `0x180030630`
- `0x180031610`
- `0x1800320c0`

## callees

- `0x180029ca8`

## pseudocode

```c
__int64 __fastcall SymCryptSizeofEcpointEx(int a1, int a2)
{
  if ( (unsigned int)(a2 - 1) > 3 )
    return 0;
  else
    return (unsigned int)(a2 * a1 + 32);
}

```

## disassembly

```asm
0x180029ca8  lea     eax, [rdx-1]
0x180029cab  cmp     eax, 3
0x180029cae  ja      short loc_180029CB8
0x180029cb0  imul    ecx, edx
0x180029cb3  lea     eax, [rcx+20h]
0x180029cb6  retn
0x180029cb8  xor     eax, eax
0x180029cba  retn
```
