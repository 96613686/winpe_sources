# ReadPrinter

- ea: `0x180003040`
- end: `0x180003098`
- name: `ReadPrinter`
- size: `88`
- prototype: `BOOL __stdcall(HANDLE hPrinter, LPVOID pBuf, DWORD cbBuf, LPDWORD pNoBytesRead)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003040`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003083`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003083`

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
0x180003040  push    rbx
0x180003042  sub     rsp, 30h
0x180003046  xor     ebx, ebx
0x180003048  cmp     cs:?g_bSandbox@@3_NA, bl; bool g_bSandbox
0x18000304e  jnz     short loc_180003065
0x180003050  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x180003057  mov     rax, [rax+190h]
0x18000305e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003063  jmp     short loc_180003091
0x180003065  mov     rax, cs:?g_pWinSpoolForwards@@3PEAU_ForwardedWinSpoolFunctions@@EA; _ForwardedWinSpoolFunctions * g_pWinSpoolForwards
0x18000306c  mov     rax, [rax+48h]
0x180003070  test    rax, rax
0x180003073  jz      short loc_18000307E
0x180003075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000307a  mov     ebx, eax
0x18000307c  jmp     short loc_18000308F
0x18000307e  mov     ecx, 7Fh; dwErrCode
0x180003083  call    cs:__imp_SetLastError
0x18000308a  nop     dword ptr [rax+rax+00h]
0x18000308f  mov     eax, ebx
0x180003091  add     rsp, 30h
0x180003095  pop     rbx
0x180003096  retn
```
