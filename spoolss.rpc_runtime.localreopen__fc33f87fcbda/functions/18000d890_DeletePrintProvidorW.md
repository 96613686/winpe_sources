# DeletePrintProvidorW

- ea: `0x18000d890`
- end: `0x18000d8e0`
- name: `DeletePrintProvidorW`
- size: `80`
- prototype: `BOOL __stdcall(LPWSTR pName, LPWSTR pEnvironment, LPWSTR pPrintProvidorName)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000d890`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d8b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d8b9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d8cc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d8cc`

## string_xrefs

- `0x18000d8c5`: `DeletePrintProvidorW`

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
0x18000d890  sub     rsp, 28h
0x18000d894  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000d89b  jnz     short loc_18000D8B4
0x18000d89d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000d8a4  mov     rax, [rax+358h]
0x18000d8ab  add     rsp, 28h
0x18000d8af  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8b4  mov     ecx, 32h ; '2'; dwErrCode
0x18000d8b9  call    cs:__imp_SetLastError
0x18000d8c0  nop     dword ptr [rax+rax+00h]
0x18000d8c5  lea     rcx, aDeleteprintpro_1; "DeletePrintProvidorW"
0x18000d8cc  call    cs:__imp_OutputDebugStringA
0x18000d8d3  nop     dword ptr [rax+rax+00h]
0x18000d8d8  xor     eax, eax
0x18000d8da  add     rsp, 28h
0x18000d8de  retn
```
