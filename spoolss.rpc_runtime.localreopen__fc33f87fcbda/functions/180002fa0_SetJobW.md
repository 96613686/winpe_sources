# SetJobW

- ea: `0x180002fa0`
- end: `0x180003005`
- name: `SetJobW`
- size: `101`
- prototype: `BOOL __stdcall(HANDLE hPrinter, DWORD JobId, DWORD Level, LPBYTE pJob, DWORD Command)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002fa0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002ff1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002ff1`

## pseudocode

```c
BOOL __stdcall SetJobW(HANDLE hPrinter, DWORD JobId, DWORD Level, LPBYTE pJob, DWORD Command)
{
  __int64 (__fastcall *v6)(HANDLE, DWORD, DWORD, LPBYTE, DWORD); // rax

  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(HANDLE, DWORD, DWORD, LPBYTE, DWORD))g_pSpoolSvForwards + 3))(
             hPrinter,
             JobId,
             Level,
             pJob,
             Command);
  v6 = (__int64 (__fastcall *)(HANDLE, DWORD, DWORD, LPBYTE, DWORD))*((_QWORD *)g_pWinSpoolForwards + 22);
  if ( v6 )
    return v6(hPrinter, JobId, Level, pJob, Command);
  SetLastError(0x7Fu);
  return 0;
}

```

## disassembly

```asm
0x180002fa0  sub     rsp, 38h
0x180002fa4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x180002fab  mov     r11, rcx
0x180002fae  jnz     short loc_180002FCC
0x180002fb0  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x180002fb7  mov     r10d, [rsp+38h+Command]
0x180002fbc  mov     [rsp+38h+var_18], r10d
0x180002fc1  mov     rax, [rax+18h]
0x180002fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fca  jmp     short loc_180002FFF
0x180002fcc  mov     rax, cs:?g_pWinSpoolForwards@@3PEAU_ForwardedWinSpoolFunctions@@EA; _ForwardedWinSpoolFunctions * g_pWinSpoolForwards
0x180002fd3  mov     rax, [rax+0B0h]
0x180002fda  test    rax, rax
0x180002fdd  jz      short loc_180002FEC
0x180002fdf  mov     ecx, [rsp+38h+Command]
0x180002fe3  mov     [rsp+38h+var_18], ecx
0x180002fe7  mov     rcx, r11
0x180002fea  jmp     short loc_180002FC5
0x180002fec  mov     ecx, 7Fh; dwErrCode
0x180002ff1  call    cs:__imp_SetLastError
0x180002ff8  nop     dword ptr [rax+rax+00h]
0x180002ffd  xor     eax, eax
0x180002fff  add     rsp, 38h
0x180003003  retn
```
