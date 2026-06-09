# DeletePrinterDriverExW

- ea: `0x18000ce90`
- end: `0x18000cedb`
- name: `DeletePrinterDriverExW`
- size: `75`
- prototype: `BOOL __stdcall(LPWSTR pName, LPWSTR pEnvironment, LPWSTR pDriverName, DWORD dwDeleteFlag, DWORD dwVersionFlag)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000ce90`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cec1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cec1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cece`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cece`

## string_xrefs

- `0x18000cec7`: `DeletePrinterDriverExW`

## pseudocode

```c
BOOL __stdcall DeletePrinterDriverExW(
        LPWSTR pName,
        LPWSTR pEnvironment,
        LPWSTR pDriverName,
        DWORD dwDeleteFlag,
        DWORD dwVersionFlag)
{
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(LPWSTR, LPWSTR, LPWSTR, DWORD, DWORD))g_pSpoolSvForwards + 21))(
             pName,
             pEnvironment,
             pDriverName,
             dwDeleteFlag,
             dwVersionFlag);
  SetLastError(0x32u);
  OutputDebugStringA("DeletePrinterDriverExW");
  return 0;
}

```

## disassembly

```asm
0x18000ce90  sub     rsp, 38h
0x18000ce94  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000ce9b  jnz     short loc_18000CEBC
0x18000ce9d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000cea4  mov     r10d, [rsp+38h+dwVersionFlag]
0x18000cea9  mov     [rsp+38h+var_18], r10d
0x18000ceae  mov     rax, [rax+0A8h]
0x18000ceb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ceba  jmp     short loc_18000CED6
0x18000cebc  mov     ecx, 32h ; '2'; dwErrCode
0x18000cec1  call    cs:__imp_SetLastError
0x18000cec7  lea     rcx, aDeleteprinterd_5; "DeletePrinterDriverExW"
0x18000cece  call    cs:__imp_OutputDebugStringA
0x18000ced4  xor     eax, eax
0x18000ced6  add     rsp, 38h
0x18000ceda  retn
```
