# DeletePrinterConnectionW

- ea: `0x18000cda0`
- end: `0x18000cde3`
- name: `DeletePrinterConnectionW`
- size: `67`
- prototype: `BOOL __stdcall(LPWSTR pName)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011c00`

## callees

- `0x18000cda0`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cdc9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cdc9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cdd6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cdd6`

## string_xrefs

- `0x18000cdcf`: `DeletePrinterConnectionW`

## pseudocode

```c
BOOL __stdcall DeletePrinterConnectionW(LPWSTR pName)
{
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(LPWSTR))g_pSpoolSvForwards + 16))(pName);
  SetLastError(0x32u);
  OutputDebugStringA("DeletePrinterConnectionW");
  return 0;
}

```

## disassembly

```asm
0x18000cda0  sub     rsp, 28h
0x18000cda4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000cdab  jnz     short loc_18000CDC4
0x18000cdad  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000cdb4  mov     rax, [rax+80h]
0x18000cdbb  add     rsp, 28h
0x18000cdbf  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdc4  mov     ecx, 32h ; '2'; dwErrCode
0x18000cdc9  call    cs:__imp_SetLastError
0x18000cdcf  lea     rcx, aDeleteprinterc_0; "DeletePrinterConnectionW"
0x18000cdd6  call    cs:__imp_OutputDebugStringA
0x18000cddc  xor     eax, eax
0x18000cdde  add     rsp, 28h
0x18000cde2  retn
```
