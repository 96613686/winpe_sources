# DllAllocSplMem

- ea: `0x180001ba0`
- end: `0x180001bd0`
- name: `DllAllocSplMem`
- size: `48`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180004aa8`
- `0x1800114cc`
- `0x180012044`
- `0x180012380`
- `0x1800141a4`
- `0x180014360`

## callees

- `0x180001ba0`
- `0x1800045e0`
- `0x180016010`

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
0x180001ba0  sub     rsp, 28h
0x180001ba4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x180001bab  jnz     short loc_180001BC9
0x180001bad  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x180001bb4  mov     rax, [rax+360h]
0x180001bbb  add     rsp, 28h
0x180001bbf  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180001bc4  add     rsp, 28h
0x180001bc8  retn
0x180001bc9  call    ?DllAllocSplMem@newSpooler@@YAPEAXK@Z; newSpooler::DllAllocSplMem(ulong)
0x180001bce  jmp     short loc_180001BC4
```
