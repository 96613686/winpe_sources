# DeletePrintProvidorW

- ea: `0x18000cd00`
- end: `0x18000cd43`
- name: `DeletePrintProvidorW`
- size: `67`
- prototype: `BOOL __stdcall(LPWSTR pName, LPWSTR pEnvironment, LPWSTR pPrintProvidorName)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000cd00`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cd29`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cd29`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cd36`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cd36`

## string_xrefs

- `0x18000cd2f`: `DeletePrintProvidorW`

## pseudocode

```c
BOOL __stdcall DeletePrintProvidorW(LPWSTR pName, LPWSTR pEnvironment, LPWSTR pPrintProvidorName)
{
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(LPWSTR, LPWSTR, LPWSTR))g_pSpoolSvForwards + 107))(
             pName,
             pEnvironment,
             pPrintProvidorName);
  SetLastError(0x32u);
  OutputDebugStringA("DeletePrintProvidorW");
  return 0;
}

```

## disassembly

```asm
0x18000cd00  sub     rsp, 28h
0x18000cd04  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000cd0b  jnz     short loc_18000CD24
0x18000cd0d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000cd14  mov     rax, [rax+358h]
0x18000cd1b  add     rsp, 28h
0x18000cd1f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd24  mov     ecx, 32h ; '2'; dwErrCode
0x18000cd29  call    cs:__imp_SetLastError
0x18000cd2f  lea     rcx, aDeleteprintpro_1; "DeletePrintProvidorW"
0x18000cd36  call    cs:__imp_OutputDebugStringA
0x18000cd3c  xor     eax, eax
0x18000cd3e  add     rsp, 28h
0x18000cd42  retn
```
