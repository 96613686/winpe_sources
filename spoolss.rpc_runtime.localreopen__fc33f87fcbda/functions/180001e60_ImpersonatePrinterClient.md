# ImpersonatePrinterClient

- ea: `0x180001e60`
- end: `0x180001e91`
- name: `ImpersonatePrinterClient`
- size: `49`
- prototype: `BOOL __stdcall(HANDLE hToken)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180004bf4`
- `0x18000acb0`
- `0x18000aeb0`
- `0x18001285c`
- `0x18001329c`

## callees

- `0x180001e60`
- `0x180001e98`
- `0x180017010`

## pseudocode

```c
BOOL __stdcall ImpersonatePrinterClient(HANDLE hToken)
{
  if ( g_bSandbox )
    return PrvImpersonatePrinterClient(hToken);
  else
    return (*((__int64 (__fastcall **)(HANDLE))g_pSpoolSvForwards + 103))(hToken);
}

```

## disassembly

```asm
0x180001e60  sub     rsp, 28h
0x180001e64  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x180001e6b  jnz     short loc_180001E8A
0x180001e6d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x180001e74  mov     rax, [rax+338h]
0x180001e7b  add     rsp, 28h
0x180001e7f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180001e84  add     rsp, 28h
0x180001e88  retn
0x180001e8a  call    PrvImpersonatePrinterClient
0x180001e8f  jmp     short loc_180001E84
```
