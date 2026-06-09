# DllAllocSplStr

- ea: `0x1800046b0`
- end: `0x1800046d1`
- name: `DllAllocSplStr`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000cfe0`

## callees

- `0x1800046b0`
- `0x1800046d8`
- `0x180016010`

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
0x1800046b0  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x1800046b7  jnz     short loc_1800046CC
0x1800046b9  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x1800046c0  mov     rax, [rax+388h]
0x1800046c7  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800046cc  jmp     ?DllAllocSplStr@newSpooler@@YAPEAGPEBG@Z; newSpooler::DllAllocSplStr(ushort const *)
```
