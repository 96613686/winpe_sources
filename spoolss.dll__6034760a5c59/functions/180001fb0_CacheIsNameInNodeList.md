# CacheIsNameInNodeList

- ea: `0x180001fb0`
- end: `0x180001ff8`
- name: `CacheIsNameInNodeList`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001fb0`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001fde`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001fde`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001feb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001feb`

## string_xrefs

- `0x180001fe4`: `CacheIsNameInNodeList`

## pseudocode

```c
__int64 CacheIsNameInNodeList()
{
  if ( !g_bSandbox )
    return (*((__int64 (**)(void))g_pSpoolSvForwards + 173))();
  SetLastError(0x32u);
  OutputDebugStringA("CacheIsNameInNodeList");
  return 2147942450LL;
}

```

## disassembly

```asm
0x180001fb0  sub     rsp, 28h
0x180001fb4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x180001fbb  jnz     short loc_180001FD9
0x180001fbd  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x180001fc4  mov     rax, [rax+568h]
0x180001fcb  add     rsp, 28h
0x180001fcf  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180001fd4  add     rsp, 28h
0x180001fd8  retn
0x180001fd9  mov     ecx, 32h ; '2'; dwErrCode
0x180001fde  call    cs:__imp_SetLastError
0x180001fe4  lea     rcx, aCacheisnameinn_0; "CacheIsNameInNodeList"
0x180001feb  call    cs:__imp_OutputDebugStringA
0x180001ff1  mov     eax, 80070032h
0x180001ff6  jmp     short loc_180001FD4
```
