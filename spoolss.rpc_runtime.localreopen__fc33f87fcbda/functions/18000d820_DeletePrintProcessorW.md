# DeletePrintProcessorW

- ea: `0x18000d820`
- end: `0x18000d87b`
- name: `DeletePrintProcessorW`
- size: `91`
- prototype: `BOOL __stdcall(LPWSTR pName, LPWSTR pEnvironment, LPWSTR pPrintProcessorName)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000d820`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d866`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d866`

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
0x18000d820  push    rbx
0x18000d822  sub     rsp, 20h
0x18000d826  xor     ebx, ebx
0x18000d828  cmp     cs:?g_bSandbox@@3_NA, bl; bool g_bSandbox
0x18000d82e  jnz     short loc_18000D848
0x18000d830  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000d837  mov     rax, [rax+0C8h]
0x18000d83e  add     rsp, 20h
0x18000d842  pop     rbx
0x18000d843  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000d848  mov     rax, cs:?g_pWinSpoolForwards@@3PEAU_ForwardedWinSpoolFunctions@@EA; _ForwardedWinSpoolFunctions * g_pWinSpoolForwards
0x18000d84f  mov     rax, [rax+10h]
0x18000d853  test    rax, rax
0x18000d856  jz      short loc_18000D861
0x18000d858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d85d  mov     ebx, eax
0x18000d85f  jmp     short loc_18000D872
0x18000d861  mov     ecx, 7Fh; dwErrCode
0x18000d866  call    cs:__imp_SetLastError
0x18000d86d  nop     dword ptr [rax+rax+00h]
0x18000d872  mov     eax, ebx
0x18000d874  add     rsp, 20h
0x18000d878  pop     rbx
0x18000d879  retn
```
