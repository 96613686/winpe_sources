# SplCommitSpoolData

- ea: `0x18000e760`
- end: `0x18000e7c8`
- name: `SplCommitSpoolData`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000e760`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e7ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e7ae`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000e7bb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000e7bb`

## string_xrefs

- `0x18000e7b4`: `SplCommitSpoolData`

## pseudocode

```c
__int64 __fastcall SplCommitSpoolData(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        int a6,
        __int64 a7)
{
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, __int64, int, __int64))g_pSpoolSvForwards + 60))(
             a1,
             a2,
             a3,
             a4,
             a5,
             a6,
             a7);
  SetLastError(0x32u);
  OutputDebugStringA("SplCommitSpoolData");
  return 0;
}

```

## disassembly

```asm
0x18000e760  sub     rsp, 48h
0x18000e764  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000e76b  mov     r11d, r9d
0x18000e76e  jnz     short loc_18000E7A9
0x18000e770  mov     r10, [rsp+48h+arg_30]
0x18000e778  mov     r9, [rsp+48h+arg_20]
0x18000e77d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000e784  mov     [rsp+48h+var_18], r10
0x18000e789  mov     r10d, [rsp+48h+arg_28]
0x18000e78e  mov     [rsp+48h+var_20], r10d
0x18000e793  mov     rax, [rax+1E0h]
0x18000e79a  mov     [rsp+48h+var_28], r9
0x18000e79f  mov     r9d, r11d
0x18000e7a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7a7  jmp     short loc_18000E7C3
0x18000e7a9  mov     ecx, 32h ; '2'; dwErrCode
0x18000e7ae  call    cs:__imp_SetLastError
0x18000e7b4  lea     rcx, aSplcommitspool_0; "SplCommitSpoolData"
0x18000e7bb  call    cs:__imp_OutputDebugStringA
0x18000e7c1  xor     eax, eax
0x18000e7c3  add     rsp, 48h
0x18000e7c7  retn
```
