# DeletePrinter

- ea: `0x18000d8f0`
- end: `0x18000d93d`
- name: `DeletePrinter`
- size: `77`
- prototype: `BOOL __stdcall(HANDLE hPrinter)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000d8f0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d916`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d916`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d929`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d929`

## string_xrefs

- `0x18000d922`: `DeletePrinter`

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
0x18000d8f0  sub     rsp, 28h
0x18000d8f4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000d8fb  jnz     short loc_18000D911
0x18000d8fd  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000d904  mov     rax, [rax+40h]
0x18000d908  add     rsp, 28h
0x18000d90c  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000d911  mov     ecx, 32h ; '2'; dwErrCode
0x18000d916  call    cs:__imp_SetLastError
0x18000d91d  nop     dword ptr [rax+rax+00h]
0x18000d922  lea     rcx, aDeleteprinter_0; "DeletePrinter"
0x18000d929  call    cs:__imp_OutputDebugStringA
0x18000d930  nop     dword ptr [rax+rax+00h]
0x18000d935  xor     eax, eax
0x18000d937  add     rsp, 28h
0x18000d93b  retn
```
