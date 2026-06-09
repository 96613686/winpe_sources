# DeletePrinterIC

- ea: `0x18000db30`
- end: `0x18000db80`
- name: `DeletePrinterIC`
- size: `80`
- prototype: `BOOL __stdcall(HANDLE hPrinterIC)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000db30`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000db59`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000db59`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000db6c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000db6c`

## string_xrefs

- `0x18000db65`: `DeletePrinterIC`

## pseudocode

```c
BOOL __stdcall DeletePrinterIC(HANDLE hPrinterIC)
{
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(HANDLE))g_pSpoolSvForwards + 101))(hPrinterIC);
  SetLastError(0x32u);
  OutputDebugStringA("DeletePrinterIC");
  return 0;
}

```

## disassembly

```asm
0x18000db30  sub     rsp, 28h
0x18000db34  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000db3b  jnz     short loc_18000DB54
0x18000db3d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000db44  mov     rax, [rax+328h]
0x18000db4b  add     rsp, 28h
0x18000db4f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000db54  mov     ecx, 32h ; '2'; dwErrCode
0x18000db59  call    cs:__imp_SetLastError
0x18000db60  nop     dword ptr [rax+rax+00h]
0x18000db65  lea     rcx, aDeleteprinteri_0; "DeletePrinterIC"
0x18000db6c  call    cs:__imp_OutputDebugStringA
0x18000db73  nop     dword ptr [rax+rax+00h]
0x18000db78  xor     eax, eax
0x18000db7a  add     rsp, 28h
0x18000db7e  retn
```
