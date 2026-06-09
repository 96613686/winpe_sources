# DeletePortW

- ea: `0x18000cc40`
- end: `0x18000cc94`
- name: `DeletePortW`
- size: `84`
- prototype: `BOOL __stdcall(LPWSTR pName, HWND hWnd, LPWSTR pPortName)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000cc40`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cc86`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cc86`

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
0x18000cc40  push    rbx
0x18000cc42  sub     rsp, 20h
0x18000cc46  xor     ebx, ebx
0x18000cc48  cmp     cs:?g_bSandbox@@3_NA, bl; bool g_bSandbox
0x18000cc4e  jnz     short loc_18000CC68
0x18000cc50  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000cc57  mov     rax, [rax+308h]
0x18000cc5e  add     rsp, 20h
0x18000cc62  pop     rbx
0x18000cc63  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc68  mov     rax, cs:?g_pWinSpoolForwards@@3PEAU_ForwardedWinSpoolFunctions@@EA; _ForwardedWinSpoolFunctions * g_pWinSpoolForwards
0x18000cc6f  mov     rax, [rax+60h]
0x18000cc73  test    rax, rax
0x18000cc76  jz      short loc_18000CC81
0x18000cc78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc7d  mov     ebx, eax
0x18000cc7f  jmp     short loc_18000CC8C
0x18000cc81  mov     ecx, 7Fh; dwErrCode
0x18000cc86  call    cs:__imp_SetLastError
0x18000cc8c  mov     eax, ebx
0x18000cc8e  add     rsp, 20h
0x18000cc92  pop     rbx
0x18000cc93  retn
```
