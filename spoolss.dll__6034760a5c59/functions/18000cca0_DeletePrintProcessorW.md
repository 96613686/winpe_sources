# DeletePrintProcessorW

- ea: `0x18000cca0`
- end: `0x18000ccf4`
- name: `DeletePrintProcessorW`
- size: `84`
- prototype: `BOOL __stdcall(LPWSTR pName, LPWSTR pEnvironment, LPWSTR pPrintProcessorName)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000cca0`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cce6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cce6`

## pseudocode

```c
BOOL __stdcall DeletePrintProcessorW(LPWSTR pName, LPWSTR pEnvironment, LPWSTR pPrintProcessorName)
{
  BOOL v3; // ebx
  __int64 (__fastcall *v5)(LPWSTR, LPWSTR, LPWSTR); // rax

  v3 = 0;
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(LPWSTR, LPWSTR, LPWSTR))g_pSpoolSvForwards + 25))(
             pName,
             pEnvironment,
             pPrintProcessorName);
  v5 = (__int64 (__fastcall *)(LPWSTR, LPWSTR, LPWSTR))*((_QWORD *)g_pWinSpoolForwards + 2);
  if ( v5 )
    return v5(pName, pEnvironment, pPrintProcessorName);
  SetLastError(0x7Fu);
  return v3;
}

```

## disassembly

```asm
0x18000cca0  push    rbx
0x18000cca2  sub     rsp, 20h
0x18000cca6  xor     ebx, ebx
0x18000cca8  cmp     cs:?g_bSandbox@@3_NA, bl; bool g_bSandbox
0x18000ccae  jnz     short loc_18000CCC8
0x18000ccb0  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000ccb7  mov     rax, [rax+0C8h]
0x18000ccbe  add     rsp, 20h
0x18000ccc2  pop     rbx
0x18000ccc3  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccc8  mov     rax, cs:?g_pWinSpoolForwards@@3PEAU_ForwardedWinSpoolFunctions@@EA; _ForwardedWinSpoolFunctions * g_pWinSpoolForwards
0x18000cccf  mov     rax, [rax+10h]
0x18000ccd3  test    rax, rax
0x18000ccd6  jz      short loc_18000CCE1
0x18000ccd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccdd  mov     ebx, eax
0x18000ccdf  jmp     short loc_18000CCEC
0x18000cce1  mov     ecx, 7Fh; dwErrCode
0x18000cce6  call    cs:__imp_SetLastError
0x18000ccec  mov     eax, ebx
0x18000ccee  add     rsp, 20h
0x18000ccf2  pop     rbx
0x18000ccf3  retn
```
