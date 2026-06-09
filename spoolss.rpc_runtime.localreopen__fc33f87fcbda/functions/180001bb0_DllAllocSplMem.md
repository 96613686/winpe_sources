# DllAllocSplMem

- ea: `0x180001bb0`
- end: `0x180001be1`
- name: `DllAllocSplMem`
- size: `49`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180004df4`
- `0x180012b48`
- `0x180012bd0`
- `0x1800137a4`
- `0x180015aa4`
- `0x180015c64`

## callees

- `0x180001bb0`
- `0x180004850`
- `0x180017010`

## pseudocode

```c
void *__fastcall DllAllocSplMem(SIZE_T a1, unsigned int a2)
{
  if ( g_bSandbox )
    return newSpooler::DllAllocSplMem(a1, a2);
  else
    return (void *)(*((__int64 (**)(void))g_pSpoolSvForwards + 108))();
}

```

## disassembly

```asm
0x180001bb0  sub     rsp, 28h
0x180001bb4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x180001bbb  jnz     short loc_180001BDA
0x180001bbd  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x180001bc4  mov     rax, [rax+360h]
0x180001bcb  add     rsp, 28h
0x180001bcf  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180001bd4  add     rsp, 28h
0x180001bd8  retn
0x180001bda  call    ?DllAllocSplMem@newSpooler@@YAPEAXK@Z; newSpooler::DllAllocSplMem(ulong)
0x180001bdf  jmp     short loc_180001BD4
```
