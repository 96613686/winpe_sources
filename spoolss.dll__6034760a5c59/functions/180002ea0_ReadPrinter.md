# ReadPrinter

- ea: `0x180002ea0`
- end: `0x180002ef1`
- name: `ReadPrinter`
- size: `81`
- prototype: `BOOL __stdcall(HANDLE hPrinter, LPVOID pBuf, DWORD cbBuf, LPDWORD pNoBytesRead)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002ea0`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002ee3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002ee3`

## pseudocode

```c
BOOL __stdcall ReadPrinter(HANDLE hPrinter, LPVOID pBuf, DWORD cbBuf, LPDWORD pNoBytesRead)
{
  BOOL v4; // ebx
  __int64 (__fastcall *v6)(HANDLE, LPVOID, DWORD, LPDWORD); // rax

  v4 = 0;
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(HANDLE, LPVOID, DWORD, LPDWORD))g_pSpoolSvForwards + 50))(
             hPrinter,
             pBuf,
             cbBuf,
             pNoBytesRead);
  v6 = (__int64 (__fastcall *)(HANDLE, LPVOID, DWORD, LPDWORD))*((_QWORD *)g_pWinSpoolForwards + 9);
  if ( v6 )
    return v6(hPrinter, pBuf, cbBuf, pNoBytesRead);
  SetLastError(0x7Fu);
  return v4;
}

```

## disassembly

```asm
0x180002ea0  push    rbx
0x180002ea2  sub     rsp, 30h
0x180002ea6  xor     ebx, ebx
0x180002ea8  cmp     cs:?g_bSandbox@@3_NA, bl; bool g_bSandbox
0x180002eae  jnz     short loc_180002EC5
0x180002eb0  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x180002eb7  mov     rax, [rax+190h]
0x180002ebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ec3  jmp     short loc_180002EEB
0x180002ec5  mov     rax, cs:?g_pWinSpoolForwards@@3PEAU_ForwardedWinSpoolFunctions@@EA; _ForwardedWinSpoolFunctions * g_pWinSpoolForwards
0x180002ecc  mov     rax, [rax+48h]
0x180002ed0  test    rax, rax
0x180002ed3  jz      short loc_180002EDE
0x180002ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002eda  mov     ebx, eax
0x180002edc  jmp     short loc_180002EE9
0x180002ede  mov     ecx, 7Fh; dwErrCode
0x180002ee3  call    cs:__imp_SetLastError
0x180002ee9  mov     eax, ebx
0x180002eeb  add     rsp, 30h
0x180002eef  pop     rbx
0x180002ef0  retn
```
