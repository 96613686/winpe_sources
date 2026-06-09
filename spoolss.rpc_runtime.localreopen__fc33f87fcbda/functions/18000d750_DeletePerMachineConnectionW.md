# DeletePerMachineConnectionW

- ea: `0x18000d750`
- end: `0x18000d7a0`
- name: `DeletePerMachineConnectionW`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000d750`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d779`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d779`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d78c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d78c`

## string_xrefs

- `0x18000d785`: `DeletePerMachineConnectionW`

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
0x18000d750  sub     rsp, 28h
0x18000d754  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000d75b  jnz     short loc_18000D774
0x18000d75d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000d764  mov     rax, [rax+1C8h]
0x18000d76b  add     rsp, 28h
0x18000d76f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000d774  mov     ecx, 32h ; '2'; dwErrCode
0x18000d779  call    cs:__imp_SetLastError
0x18000d780  nop     dword ptr [rax+rax+00h]
0x18000d785  lea     rcx, aDeletepermachi_0; "DeletePerMachineConnectionW"
0x18000d78c  call    cs:__imp_OutputDebugStringA
0x18000d793  nop     dword ptr [rax+rax+00h]
0x18000d798  xor     eax, eax
0x18000d79a  add     rsp, 28h
0x18000d79e  retn
```
