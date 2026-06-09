# DllReallocSplMem

- ea: `0x1800047d0`
- end: `0x1800047f1`
- name: `DllReallocSplMem`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800047d0`
- `0x1800047f8`
- `0x180017010`

## pseudocode

```c
HLOCAL __fastcall DllReallocSplMem(newSpooler *a1, size_t a2, SIZE_T a3)
{
  if ( g_bSandbox )
    return newSpooler::DllReallocSplMem(a1, a2, a3);
  else
    return (HLOCAL)(*((__int64 (**)(void))g_pSpoolSvForwards + 111))();
}

```

## disassembly

```asm
0x1800047d0  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x1800047d7  jnz     short loc_1800047EC
0x1800047d9  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x1800047e0  mov     rax, [rax+378h]
0x1800047e7  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800047ec  jmp     ?DllReallocSplMem@newSpooler@@YAPEAXPEAXKK@Z; newSpooler::DllReallocSplMem(void *,ulong,ulong)
```
