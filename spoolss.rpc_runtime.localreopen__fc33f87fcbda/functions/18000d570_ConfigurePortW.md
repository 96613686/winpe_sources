# ConfigurePortW

- ea: `0x18000d570`
- end: `0x18000d5c0`
- name: `ConfigurePortW`
- size: `80`
- prototype: `BOOL __stdcall(LPWSTR pName, HWND hWnd, LPWSTR pPortName)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000d570`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d599`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d599`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d5ac`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d5ac`

## string_xrefs

- `0x18000d5a5`: `ConfigurePortW`

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
0x18000d570  sub     rsp, 28h
0x18000d574  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000d57b  jnz     short loc_18000D594
0x18000d57d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000d584  mov     rax, [rax+300h]
0x18000d58b  add     rsp, 28h
0x18000d58f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000d594  mov     ecx, 32h ; '2'; dwErrCode
0x18000d599  call    cs:__imp_SetLastError
0x18000d5a0  nop     dword ptr [rax+rax+00h]
0x18000d5a5  lea     rcx, aConfigureportw_0; "ConfigurePortW"
0x18000d5ac  call    cs:__imp_OutputDebugStringA
0x18000d5b3  nop     dword ptr [rax+rax+00h]
0x18000d5b8  xor     eax, eax
0x18000d5ba  add     rsp, 28h
0x18000d5be  retn
```
