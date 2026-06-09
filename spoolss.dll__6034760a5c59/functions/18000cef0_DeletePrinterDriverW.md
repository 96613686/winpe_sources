# DeletePrinterDriverW

- ea: `0x18000cef0`
- end: `0x18000cf33`
- name: `DeletePrinterDriverW`
- size: `67`
- prototype: `BOOL __stdcall(LPWSTR pName, LPWSTR pEnvironment, LPWSTR pDriverName)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000cef0`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cf19`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cf19`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cf26`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cf26`

## string_xrefs

- `0x18000cf1f`: `DeletePrinterDriverW`

## pseudocode

```c
BOOL __stdcall DeletePrinterDriverW(LPWSTR pName, LPWSTR pEnvironment, LPWSTR pDriverName)
{
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(LPWSTR, LPWSTR, LPWSTR))g_pSpoolSvForwards + 20))(
             pName,
             pEnvironment,
             pDriverName);
  SetLastError(0x32u);
  OutputDebugStringA("DeletePrinterDriverW");
  return 0;
}

```

## disassembly

```asm
0x18000cef0  sub     rsp, 28h
0x18000cef4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000cefb  jnz     short loc_18000CF14
0x18000cefd  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000cf04  mov     rax, [rax+0A0h]
0x18000cf0b  add     rsp, 28h
0x18000cf0f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf14  mov     ecx, 32h ; '2'; dwErrCode
0x18000cf19  call    cs:__imp_SetLastError
0x18000cf1f  lea     rcx, aDeleteprinterd_6; "DeletePrinterDriverW"
0x18000cf26  call    cs:__imp_OutputDebugStringA
0x18000cf2c  xor     eax, eax
0x18000cf2e  add     rsp, 28h
0x18000cf32  retn
```
