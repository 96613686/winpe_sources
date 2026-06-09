# DeletePrinterDriverW

- ea: `0x18000dad0`
- end: `0x18000db20`
- name: `DeletePrinterDriverW`
- size: `80`
- prototype: `BOOL __stdcall(LPWSTR pName, LPWSTR pEnvironment, LPWSTR pDriverName)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000dad0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000daf9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000daf9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000db0c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000db0c`

## string_xrefs

- `0x18000db05`: `DeletePrinterDriverW`

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
0x18000dad0  sub     rsp, 28h
0x18000dad4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000dadb  jnz     short loc_18000DAF4
0x18000dadd  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000dae4  mov     rax, [rax+0A0h]
0x18000daeb  add     rsp, 28h
0x18000daef  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000daf4  mov     ecx, 32h ; '2'; dwErrCode
0x18000daf9  call    cs:__imp_SetLastError
0x18000db00  nop     dword ptr [rax+rax+00h]
0x18000db05  lea     rcx, aDeleteprinterd_6; "DeletePrinterDriverW"
0x18000db0c  call    cs:__imp_OutputDebugStringA
0x18000db13  nop     dword ptr [rax+rax+00h]
0x18000db18  xor     eax, eax
0x18000db1a  add     rsp, 28h
0x18000db1e  retn
```
