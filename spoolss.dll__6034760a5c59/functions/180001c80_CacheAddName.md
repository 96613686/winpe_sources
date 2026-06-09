# CacheAddName

- ea: `0x180001c80`
- end: `0x180001cc8`
- name: `CacheAddName`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001c80`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001cae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001cae`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001cbb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001cbb`

## string_xrefs

- `0x180001cb4`: `CacheAddName`

## pseudocode

```c
__int64 CacheAddName()
{
  if ( !g_bSandbox )
    return (*((__int64 (**)(void))g_pSpoolSvForwards + 171))();
  SetLastError(0x32u);
  OutputDebugStringA("CacheAddName");
  return 2147942450LL;
}

```

## disassembly

```asm
0x180001c80  sub     rsp, 28h
0x180001c84  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x180001c8b  jnz     short loc_180001CA9
0x180001c8d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x180001c94  mov     rax, [rax+558h]
0x180001c9b  add     rsp, 28h
0x180001c9f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180001ca4  add     rsp, 28h
0x180001ca8  retn
0x180001ca9  mov     ecx, 32h ; '2'; dwErrCode
0x180001cae  call    cs:__imp_SetLastError
0x180001cb4  lea     rcx, aCacheaddname_0; "CacheAddName"
0x180001cbb  call    cs:__imp_OutputDebugStringA
0x180001cc1  mov     eax, 80070032h
0x180001cc6  jmp     short loc_180001CA4
```
