# UpdateBufferSize

- ea: `0x18000fff0`
- end: `0x180010055`
- name: `UpdateBufferSize`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000fff0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001002b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001002b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18001003e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18001003e`

## string_xrefs

- `0x180010037`: `UpdateBufferSize`

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
0x18000fff0  sub     rsp, 48h
0x18000fff4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000fffb  jnz     short loc_180010026
0x18000fffd  mov     r10, [rsp+48h+arg_28]
0x180010002  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x180010009  mov     [rsp+48h+var_20], r10
0x18001000e  mov     r10d, [rsp+48h+arg_20]
0x180010013  mov     [rsp+48h+var_28], r10d
0x180010018  mov     rax, [rax+468h]
0x18001001f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010024  jmp     short loc_18001004F
0x180010026  mov     ecx, 32h ; '2'; dwErrCode
0x18001002b  call    cs:__imp_SetLastError
0x180010032  nop     dword ptr [rax+rax+00h]
0x180010037  lea     rcx, aUpdatebuffersi_0; "UpdateBufferSize"
0x18001003e  call    cs:__imp_OutputDebugStringA
0x180010045  nop     dword ptr [rax+rax+00h]
0x18001004a  mov     eax, 32h ; '2'
0x18001004f  add     rsp, 48h
0x180010053  retn
```
