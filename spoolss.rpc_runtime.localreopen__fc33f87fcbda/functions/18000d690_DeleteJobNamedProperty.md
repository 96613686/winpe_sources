# DeleteJobNamedProperty

- ea: `0x18000d690`
- end: `0x18000d6e3`
- name: `DeleteJobNamedProperty`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000d690`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d6b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d6b9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d6cc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d6cc`

## string_xrefs

- `0x18000d6c5`: `DeleteJobNamedProperty`

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
0x18000d690  sub     rsp, 28h
0x18000d694  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000d69b  jnz     short loc_18000D6B4
0x18000d69d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000d6a4  mov     rax, [rax+638h]
0x18000d6ab  add     rsp, 28h
0x18000d6af  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6b4  mov     ecx, 32h ; '2'; dwErrCode
0x18000d6b9  call    cs:__imp_SetLastError
0x18000d6c0  nop     dword ptr [rax+rax+00h]
0x18000d6c5  lea     rcx, aDeletejobnamed_0; "DeleteJobNamedProperty"
0x18000d6cc  call    cs:__imp_OutputDebugStringA
0x18000d6d3  nop     dword ptr [rax+rax+00h]
0x18000d6d8  mov     eax, 80070032h
0x18000d6dd  add     rsp, 28h
0x18000d6e1  retn
```
