# DllReallocSplMem

- ea: `0x180004560`
- end: `0x180004581`
- name: `DllReallocSplMem`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180004560`
- `0x180004588`
- `0x180016010`

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
0x180004560  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x180004567  jnz     short loc_18000457C
0x180004569  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x180004570  mov     rax, [rax+378h]
0x180004577  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000457c  jmp     ?DllReallocSplMem@newSpooler@@YAPEAXPEAXKK@Z; newSpooler::DllReallocSplMem(void *,ulong,ulong)
```
