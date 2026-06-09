# ImpersonatePrinterClient

- ea: `0x180001e00`
- end: `0x180001e30`
- name: `ImpersonatePrinterClient`
- size: `48`
- prototype: `BOOL __stdcall(HANDLE hToken)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800048b4`
- `0x18000a440`
- `0x18000a610`
- `0x1800111f0`
- `0x180011b94`

## callees

- `0x180001e00`
- `0x180001e38`
- `0x180016010`

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
0x180001e00  sub     rsp, 28h
0x180001e04  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x180001e0b  jnz     short loc_180001E29
0x180001e0d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x180001e14  mov     rax, [rax+338h]
0x180001e1b  add     rsp, 28h
0x180001e1f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180001e24  add     rsp, 28h
0x180001e28  retn
0x180001e29  call    PrvImpersonatePrinterClient
0x180001e2e  jmp     short loc_180001E24
```
