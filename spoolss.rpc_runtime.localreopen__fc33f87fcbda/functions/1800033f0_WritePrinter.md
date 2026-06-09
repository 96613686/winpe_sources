# WritePrinter

- ea: `0x1800033f0`
- end: `0x180003448`
- name: `WritePrinter`
- size: `88`
- prototype: `BOOL __stdcall(HANDLE hPrinter, LPVOID pBuf, DWORD cbBuf, LPDWORD pcWritten)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800033f0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003433`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003433`

## pseudocode

```c
BOOL __stdcall WritePrinter(HANDLE hPrinter, LPVOID pBuf, DWORD cbBuf, LPDWORD pcWritten)
{
  BOOL v4; // ebx
  __int64 (__fastcall *v6)(HANDLE, LPVOID, DWORD, LPDWORD); // rax

  v4 = 0;
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(HANDLE, LPVOID, DWORD, LPDWORD))g_pSpoolSvForwards + 35))(
             hPrinter,
             pBuf,
             cbBuf,
             pcWritten);
  v6 = (__int64 (__fastcall *)(HANDLE, LPVOID, DWORD, LPDWORD))*((_QWORD *)g_pWinSpoolForwards + 6);
  if ( v6 )
    return v6(hPrinter, pBuf, cbBuf, pcWritten);
  SetLastError(0x7Fu);
  return v4;
}

```

## disassembly

```asm
0x1800033f0  push    rbx
0x1800033f2  sub     rsp, 30h
0x1800033f6  xor     ebx, ebx
0x1800033f8  cmp     cs:?g_bSandbox@@3_NA, bl; bool g_bSandbox
0x1800033fe  jnz     short loc_180003415
0x180003400  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x180003407  mov     rax, [rax+118h]
0x18000340e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003413  jmp     short loc_180003441
0x180003415  mov     rax, cs:?g_pWinSpoolForwards@@3PEAU_ForwardedWinSpoolFunctions@@EA; _ForwardedWinSpoolFunctions * g_pWinSpoolForwards
0x18000341c  mov     rax, [rax+30h]
0x180003420  test    rax, rax
0x180003423  jz      short loc_18000342E
0x180003425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000342a  mov     ebx, eax
0x18000342c  jmp     short loc_18000343F
0x18000342e  mov     ecx, 7Fh; dwErrCode
0x180003433  call    cs:__imp_SetLastError
0x18000343a  nop     dword ptr [rax+rax+00h]
0x18000343f  mov     eax, ebx
0x180003441  add     rsp, 30h
0x180003445  pop     rbx
0x180003446  retn
```
