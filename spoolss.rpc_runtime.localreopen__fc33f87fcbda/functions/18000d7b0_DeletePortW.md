# DeletePortW

- ea: `0x18000d7b0`
- end: `0x18000d80b`
- name: `DeletePortW`
- size: `91`
- prototype: `BOOL __stdcall(LPWSTR pName, HWND hWnd, LPWSTR pPortName)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000d7b0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d7f6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d7f6`

## pseudocode

```c
BOOL __stdcall DeletePortW(LPWSTR pName, HWND hWnd, LPWSTR pPortName)
{
  BOOL v3; // ebx
  __int64 (__fastcall *v5)(LPWSTR, HWND, LPWSTR); // rax

  v3 = 0;
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(LPWSTR, HWND, LPWSTR))g_pSpoolSvForwards + 97))(pName, hWnd, pPortName);
  v5 = (__int64 (__fastcall *)(LPWSTR, HWND, LPWSTR))*((_QWORD *)g_pWinSpoolForwards + 12);
  if ( v5 )
    return v5(pName, hWnd, pPortName);
  SetLastError(0x7Fu);
  return v3;
}

```

## disassembly

```asm
0x18000d7b0  push    rbx
0x18000d7b2  sub     rsp, 20h
0x18000d7b6  xor     ebx, ebx
0x18000d7b8  cmp     cs:?g_bSandbox@@3_NA, bl; bool g_bSandbox
0x18000d7be  jnz     short loc_18000D7D8
0x18000d7c0  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000d7c7  mov     rax, [rax+308h]
0x18000d7ce  add     rsp, 20h
0x18000d7d2  pop     rbx
0x18000d7d3  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7d8  mov     rax, cs:?g_pWinSpoolForwards@@3PEAU_ForwardedWinSpoolFunctions@@EA; _ForwardedWinSpoolFunctions * g_pWinSpoolForwards
0x18000d7df  mov     rax, [rax+60h]
0x18000d7e3  test    rax, rax
0x18000d7e6  jz      short loc_18000D7F1
0x18000d7e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7ed  mov     ebx, eax
0x18000d7ef  jmp     short loc_18000D802
0x18000d7f1  mov     ecx, 7Fh; dwErrCode
0x18000d7f6  call    cs:__imp_SetLastError
0x18000d7fd  nop     dword ptr [rax+rax+00h]
0x18000d802  mov     eax, ebx
0x18000d804  add     rsp, 20h
0x18000d808  pop     rbx
0x18000d809  retn
```
