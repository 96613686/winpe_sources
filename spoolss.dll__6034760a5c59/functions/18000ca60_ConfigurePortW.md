# ConfigurePortW

- ea: `0x18000ca60`
- end: `0x18000caa3`
- name: `ConfigurePortW`
- size: `67`
- prototype: `BOOL __stdcall(LPWSTR pName, HWND hWnd, LPWSTR pPortName)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000ca60`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ca89`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ca89`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000ca96`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000ca96`

## string_xrefs

- `0x18000ca8f`: `ConfigurePortW`

## pseudocode

```c
BOOL __stdcall ConfigurePortW(LPWSTR pName, HWND hWnd, LPWSTR pPortName)
{
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(LPWSTR, HWND, LPWSTR))g_pSpoolSvForwards + 96))(pName, hWnd, pPortName);
  SetLastError(0x32u);
  OutputDebugStringA("ConfigurePortW");
  return 0;
}

```

## disassembly

```asm
0x18000ca60  sub     rsp, 28h
0x18000ca64  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000ca6b  jnz     short loc_18000CA84
0x18000ca6d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000ca74  mov     rax, [rax+300h]
0x18000ca7b  add     rsp, 28h
0x18000ca7f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca84  mov     ecx, 32h ; '2'; dwErrCode
0x18000ca89  call    cs:__imp_SetLastError
0x18000ca8f  lea     rcx, aConfigureportw_0; "ConfigurePortW"
0x18000ca96  call    cs:__imp_OutputDebugStringA
0x18000ca9c  xor     eax, eax
0x18000ca9e  add     rsp, 28h
0x18000caa2  retn
```
