# DeletePrinterKeyW

- ea: `0x18000db90`
- end: `0x18000dbe3`
- name: `DeletePrinterKeyW`
- size: `83`
- prototype: `DWORD __stdcall(HANDLE hPrinter, LPCWSTR pKeyName)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000db90`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dbb9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dbb9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000dbcc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000dbcc`

## string_xrefs

- `0x18000dbc5`: `DeletePrinterKeyW`

## pseudocode

```c
DWORD __stdcall DeletePrinterKeyW(HANDLE hPrinter, LPCWSTR pKeyName)
{
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(HANDLE, LPCWSTR))g_pSpoolSvForwards + 46))(hPrinter, pKeyName);
  SetLastError(0x32u);
  OutputDebugStringA("DeletePrinterKeyW");
  return 50;
}

```

## disassembly

```asm
0x18000db90  sub     rsp, 28h
0x18000db94  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000db9b  jnz     short loc_18000DBB4
0x18000db9d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000dba4  mov     rax, [rax+170h]
0x18000dbab  add     rsp, 28h
0x18000dbaf  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbb4  mov     ecx, 32h ; '2'; dwErrCode
0x18000dbb9  call    cs:__imp_SetLastError
0x18000dbc0  nop     dword ptr [rax+rax+00h]
0x18000dbc5  lea     rcx, aDeleteprinterk_0; "DeletePrinterKeyW"
0x18000dbcc  call    cs:__imp_OutputDebugStringA
0x18000dbd3  nop     dword ptr [rax+rax+00h]
0x18000dbd8  mov     eax, 32h ; '2'
0x18000dbdd  add     rsp, 28h
0x18000dbe1  retn
```
