# DeletePrinterDriverExW

- ea: `0x18000da70`
- end: `0x18000dac8`
- name: `DeletePrinterDriverExW`
- size: `88`
- prototype: `BOOL __stdcall(LPWSTR pName, LPWSTR pEnvironment, LPWSTR pDriverName, DWORD dwDeleteFlag, DWORD dwVersionFlag)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000da70`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000daa1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000daa1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000dab4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000dab4`

## string_xrefs

- `0x18000daad`: `DeletePrinterDriverExW`

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
0x18000da70  sub     rsp, 38h
0x18000da74  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000da7b  jnz     short loc_18000DA9C
0x18000da7d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000da84  mov     r10d, [rsp+38h+dwVersionFlag]
0x18000da89  mov     [rsp+38h+var_18], r10d
0x18000da8e  mov     rax, [rax+0A8h]
0x18000da95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da9a  jmp     short loc_18000DAC2
0x18000da9c  mov     ecx, 32h ; '2'; dwErrCode
0x18000daa1  call    cs:__imp_SetLastError
0x18000daa8  nop     dword ptr [rax+rax+00h]
0x18000daad  lea     rcx, aDeleteprinterd_5; "DeletePrinterDriverExW"
0x18000dab4  call    cs:__imp_OutputDebugStringA
0x18000dabb  nop     dword ptr [rax+rax+00h]
0x18000dac0  xor     eax, eax
0x18000dac2  add     rsp, 38h
0x18000dac6  retn
```
