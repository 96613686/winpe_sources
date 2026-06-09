# DeletePerMachineConnectionW

- ea: `0x18000cbf0`
- end: `0x18000cc33`
- name: `DeletePerMachineConnectionW`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000cbf0`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cc19`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cc19`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cc26`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cc26`

## string_xrefs

- `0x18000cc1f`: `DeletePerMachineConnectionW`

## pseudocode

```c
__int64 DeletePerMachineConnectionW()
{
  if ( !g_bSandbox )
    return (*((__int64 (**)(void))g_pSpoolSvForwards + 57))();
  SetLastError(0x32u);
  OutputDebugStringA("DeletePerMachineConnectionW");
  return 0;
}

```

## disassembly

```asm
0x18000cbf0  sub     rsp, 28h
0x18000cbf4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000cbfb  jnz     short loc_18000CC14
0x18000cbfd  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000cc04  mov     rax, [rax+1C8h]
0x18000cc0b  add     rsp, 28h
0x18000cc0f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc14  mov     ecx, 32h ; '2'; dwErrCode
0x18000cc19  call    cs:__imp_SetLastError
0x18000cc1f  lea     rcx, aDeletepermachi_0; "DeletePerMachineConnectionW"
0x18000cc26  call    cs:__imp_OutputDebugStringA
0x18000cc2c  xor     eax, eax
0x18000cc2e  add     rsp, 28h
0x18000cc32  retn
```
