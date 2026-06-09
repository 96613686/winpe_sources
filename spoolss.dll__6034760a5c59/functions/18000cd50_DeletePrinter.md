# DeletePrinter

- ea: `0x18000cd50`
- end: `0x18000cd90`
- name: `DeletePrinter`
- size: `64`
- prototype: `BOOL __stdcall(HANDLE hPrinter)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000cd50`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cd76`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cd76`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cd83`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cd83`

## string_xrefs

- `0x18000cd7c`: `DeletePrinter`

## pseudocode

```c
BOOL __stdcall DeletePrinter(HANDLE hPrinter)
{
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(HANDLE))g_pSpoolSvForwards + 8))(hPrinter);
  SetLastError(0x32u);
  OutputDebugStringA("DeletePrinter");
  return 0;
}

```

## disassembly

```asm
0x18000cd50  sub     rsp, 28h
0x18000cd54  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000cd5b  jnz     short loc_18000CD71
0x18000cd5d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000cd64  mov     rax, [rax+40h]
0x18000cd68  add     rsp, 28h
0x18000cd6c  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd71  mov     ecx, 32h ; '2'; dwErrCode
0x18000cd76  call    cs:__imp_SetLastError
0x18000cd7c  lea     rcx, aDeleteprinter_0; "DeletePrinter"
0x18000cd83  call    cs:__imp_OutputDebugStringA
0x18000cd89  xor     eax, eax
0x18000cd8b  add     rsp, 28h
0x18000cd8f  retn
```
