# DllAllocSplStr

- ea: `0x1800049e0`
- end: `0x180004a01`
- name: `DllAllocSplStr`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000dbf0`

## callees

- `0x1800049e0`
- `0x180004a08`
- `0x180017010`

## pseudocode

```c
unsigned __int16 *__fastcall DllAllocSplStr(newSpooler *a1, const unsigned __int16 *a2)
{
  if ( g_bSandbox )
    return newSpooler::DllAllocSplStr(a1, a2);
  else
    return (unsigned __int16 *)(*((__int64 (**)(void))g_pSpoolSvForwards + 113))();
}

```

## disassembly

```asm
0x1800049e0  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x1800049e7  jnz     short loc_1800049FC
0x1800049e9  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x1800049f0  mov     rax, [rax+388h]
0x1800049f7  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800049fc  jmp     ?DllAllocSplStr@newSpooler@@YAPEAGPEBG@Z; newSpooler::DllAllocSplStr(ushort const *)
```
