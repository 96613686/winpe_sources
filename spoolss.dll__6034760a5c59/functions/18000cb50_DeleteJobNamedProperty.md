# DeleteJobNamedProperty

- ea: `0x18000cb50`
- end: `0x18000cb96`
- name: `DeleteJobNamedProperty`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000cb50`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cb79`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cb79`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cb86`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cb86`

## string_xrefs

- `0x18000cb7f`: `DeleteJobNamedProperty`

## pseudocode

```c
__int64 DeleteJobNamedProperty()
{
  if ( !g_bSandbox )
    return (*((__int64 (**)(void))g_pSpoolSvForwards + 199))();
  SetLastError(0x32u);
  OutputDebugStringA("DeleteJobNamedProperty");
  return 2147942450LL;
}

```

## disassembly

```asm
0x18000cb50  sub     rsp, 28h
0x18000cb54  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000cb5b  jnz     short loc_18000CB74
0x18000cb5d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000cb64  mov     rax, [rax+638h]
0x18000cb6b  add     rsp, 28h
0x18000cb6f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb74  mov     ecx, 32h ; '2'; dwErrCode
0x18000cb79  call    cs:__imp_SetLastError
0x18000cb7f  lea     rcx, aDeletejobnamed_0; "DeleteJobNamedProperty"
0x18000cb86  call    cs:__imp_OutputDebugStringA
0x18000cb8c  mov     eax, 80070032h
0x18000cb91  add     rsp, 28h
0x18000cb95  retn
```
