# DeletePrinterIC

- ea: `0x18000cf40`
- end: `0x18000cf83`
- name: `DeletePrinterIC`
- size: `67`
- prototype: `BOOL __stdcall(HANDLE hPrinterIC)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000cf40`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cf69`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cf69`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cf76`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cf76`

## string_xrefs

- `0x18000cf6f`: `DeletePrinterIC`

## pseudocode

```c
BOOL __stdcall DeletePrinterIC(HANDLE hPrinterIC)
{
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(HANDLE))g_pSpoolSvForwards + 101))(hPrinterIC);
  SetLastError(0x32u);
  OutputDebugStringA("DeletePrinterIC");
  return 0;
}

```

## disassembly

```asm
0x18000cf40  sub     rsp, 28h
0x18000cf44  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000cf4b  jnz     short loc_18000CF64
0x18000cf4d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000cf54  mov     rax, [rax+328h]
0x18000cf5b  add     rsp, 28h
0x18000cf5f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf64  mov     ecx, 32h ; '2'; dwErrCode
0x18000cf69  call    cs:__imp_SetLastError
0x18000cf6f  lea     rcx, aDeleteprinteri_0; "DeletePrinterIC"
0x18000cf76  call    cs:__imp_OutputDebugStringA
0x18000cf7c  xor     eax, eax
0x18000cf7e  add     rsp, 28h
0x18000cf82  retn
```
