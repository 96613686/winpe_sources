# DeleteFormW

- ea: `0x18000d630`
- end: `0x18000d680`
- name: `DeleteFormW`
- size: `80`
- prototype: `BOOL __stdcall(HANDLE hPrinter, LPWSTR pFormName)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000d630`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d659`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d659`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d66c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d66c`

## string_xrefs

- `0x18000d665`: `DeleteFormW`

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
0x18000d630  sub     rsp, 28h
0x18000d634  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000d63b  jnz     short loc_18000D654
0x18000d63d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000d644  mov     rax, [rax+2C8h]
0x18000d64b  add     rsp, 28h
0x18000d64f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000d654  mov     ecx, 32h ; '2'; dwErrCode
0x18000d659  call    cs:__imp_SetLastError
0x18000d660  nop     dword ptr [rax+rax+00h]
0x18000d665  lea     rcx, aDeleteformw_0; "DeleteFormW"
0x18000d66c  call    cs:__imp_OutputDebugStringA
0x18000d673  nop     dword ptr [rax+rax+00h]
0x18000d678  xor     eax, eax
0x18000d67a  add     rsp, 28h
0x18000d67e  retn
```
