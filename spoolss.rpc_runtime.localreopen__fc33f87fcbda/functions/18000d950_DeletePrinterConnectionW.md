# DeletePrinterConnectionW

- ea: `0x18000d950`
- end: `0x18000d9a0`
- name: `DeletePrinterConnectionW`
- size: `80`
- prototype: `BOOL __stdcall(LPWSTR pName)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180013310`

## callees

- `0x18000d950`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d979`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d979`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d98c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d98c`

## string_xrefs

- `0x18000d985`: `DeletePrinterConnectionW`

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
0x18000d950  sub     rsp, 28h
0x18000d954  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000d95b  jnz     short loc_18000D974
0x18000d95d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000d964  mov     rax, [rax+80h]
0x18000d96b  add     rsp, 28h
0x18000d96f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000d974  mov     ecx, 32h ; '2'; dwErrCode
0x18000d979  call    cs:__imp_SetLastError
0x18000d980  nop     dword ptr [rax+rax+00h]
0x18000d985  lea     rcx, aDeleteprinterc_0; "DeletePrinterConnectionW"
0x18000d98c  call    cs:__imp_OutputDebugStringA
0x18000d993  nop     dword ptr [rax+rax+00h]
0x18000d998  xor     eax, eax
0x18000d99a  add     rsp, 28h
0x18000d99e  retn
```
