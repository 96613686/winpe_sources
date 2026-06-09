# DeleteFormW

- ea: `0x18000cb00`
- end: `0x18000cb43`
- name: `DeleteFormW`
- size: `67`
- prototype: `BOOL __stdcall(HANDLE hPrinter, LPWSTR pFormName)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000cb00`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cb29`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cb29`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cb36`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cb36`

## string_xrefs

- `0x18000cb2f`: `DeleteFormW`

## pseudocode

```c
BOOL __stdcall DeleteFormW(HANDLE hPrinter, LPWSTR pFormName)
{
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(HANDLE, LPWSTR))g_pSpoolSvForwards + 89))(hPrinter, pFormName);
  SetLastError(0x32u);
  OutputDebugStringA("DeleteFormW");
  return 0;
}

```

## disassembly

```asm
0x18000cb00  sub     rsp, 28h
0x18000cb04  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000cb0b  jnz     short loc_18000CB24
0x18000cb0d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000cb14  mov     rax, [rax+2C8h]
0x18000cb1b  add     rsp, 28h
0x18000cb1f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb24  mov     ecx, 32h ; '2'; dwErrCode
0x18000cb29  call    cs:__imp_SetLastError
0x18000cb2f  lea     rcx, aDeleteformw_0; "DeleteFormW"
0x18000cb36  call    cs:__imp_OutputDebugStringA
0x18000cb3c  xor     eax, eax
0x18000cb3e  add     rsp, 28h
0x18000cb42  retn
```
