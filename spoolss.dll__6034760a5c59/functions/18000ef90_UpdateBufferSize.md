# UpdateBufferSize

- ea: `0x18000ef90`
- end: `0x18000efe8`
- name: `UpdateBufferSize`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000ef90`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000efcb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000efcb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000efd8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000efd8`

## string_xrefs

- `0x18000efd1`: `UpdateBufferSize`

## pseudocode

```c
__int64 __fastcall UpdateBufferSize(__int64 a1, __int64 a2)
{
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(__int64, __int64))g_pSpoolSvForwards + 141))(a1, a2);
  SetLastError(0x32u);
  OutputDebugStringA("UpdateBufferSize");
  return 50;
}

```

## disassembly

```asm
0x18000ef90  sub     rsp, 48h
0x18000ef94  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000ef9b  jnz     short loc_18000EFC6
0x18000ef9d  mov     r10, [rsp+48h+arg_28]
0x18000efa2  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000efa9  mov     [rsp+48h+var_20], r10
0x18000efae  mov     r10d, [rsp+48h+arg_20]
0x18000efb3  mov     [rsp+48h+var_28], r10d
0x18000efb8  mov     rax, [rax+468h]
0x18000efbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efc4  jmp     short loc_18000EFE3
0x18000efc6  mov     ecx, 32h ; '2'; dwErrCode
0x18000efcb  call    cs:__imp_SetLastError
0x18000efd1  lea     rcx, aUpdatebuffersi_0; "UpdateBufferSize"
0x18000efd8  call    cs:__imp_OutputDebugStringA
0x18000efde  mov     eax, 32h ; '2'
0x18000efe3  add     rsp, 48h
0x18000efe7  retn
```
