# SplCommitSpoolData

- ea: `0x18000f650`
- end: `0x18000f6c5`
- name: `SplCommitSpoolData`
- size: `117`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000f650`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f69e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f69e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000f6b1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000f6b1`

## string_xrefs

- `0x18000f6aa`: `SplCommitSpoolData`

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
0x18000f650  sub     rsp, 48h
0x18000f654  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000f65b  mov     r11d, r9d
0x18000f65e  jnz     short loc_18000F699
0x18000f660  mov     r10, [rsp+48h+arg_30]
0x18000f668  mov     r9, [rsp+48h+arg_20]
0x18000f66d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000f674  mov     [rsp+48h+var_18], r10
0x18000f679  mov     r10d, [rsp+48h+arg_28]
0x18000f67e  mov     [rsp+48h+var_20], r10d
0x18000f683  mov     rax, [rax+1E0h]
0x18000f68a  mov     [rsp+48h+var_28], r9
0x18000f68f  mov     r9d, r11d
0x18000f692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f697  jmp     short loc_18000F6BF
0x18000f699  mov     ecx, 32h ; '2'; dwErrCode
0x18000f69e  call    cs:__imp_SetLastError
0x18000f6a5  nop     dword ptr [rax+rax+00h]
0x18000f6aa  lea     rcx, aSplcommitspool_0; "SplCommitSpoolData"
0x18000f6b1  call    cs:__imp_OutputDebugStringA
0x18000f6b8  nop     dword ptr [rax+rax+00h]
0x18000f6bd  xor     eax, eax
0x18000f6bf  add     rsp, 48h
0x18000f6c3  retn
```
