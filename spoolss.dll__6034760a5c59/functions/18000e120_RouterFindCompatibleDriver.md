# RouterFindCompatibleDriver

- ea: `0x18000e120`
- end: `0x18000e1c3`
- name: `RouterFindCompatibleDriver`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000e120`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e1a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e1a0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000e1ad`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000e1ad`

## string_xrefs

- `0x18000e1a6`: `RouterFindCompatibleDriver`

## pseudocode

```c
__int64 __fastcall RouterFindCompatibleDriver(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6,
        int a7,
        __int64 a8,
        __int64 a9)
{
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, __int64, __int64, int, __int64, __int64))g_pSpoolSvForwards
            + 179))(
             a1,
             a2,
             a3,
             a4,
             a5,
             a6,
             a7,
             a8,
             a9);
  SetLastError(0x32u);
  OutputDebugStringA("RouterFindCompatibleDriver");
  return 2147942450LL;
}

```

## disassembly

```asm
0x18000e120  mov     [rsp+arg_0], rbx
0x18000e125  push    rdi
0x18000e126  sub     rsp, 50h
0x18000e12a  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000e131  mov     r11d, r9d
0x18000e134  mov     rbx, rdx
0x18000e137  mov     rdi, rcx
0x18000e13a  jnz     short loc_18000E19B
0x18000e13c  mov     r9d, [rsp+58h+arg_30]
0x18000e144  mov     r10, [rsp+58h+arg_40]
0x18000e14c  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000e153  mov     rdx, [rsp+58h+arg_28]
0x18000e15b  mov     rcx, [rsp+58h+arg_20]
0x18000e163  mov     [rsp+58h+var_18], r10
0x18000e168  mov     r10, [rsp+58h+arg_38]
0x18000e170  mov     rax, [rax+598h]
0x18000e177  mov     [rsp+58h+var_20], r10
0x18000e17c  mov     [rsp+58h+var_28], r9d
0x18000e181  mov     r9d, r11d
0x18000e184  mov     [rsp+58h+var_30], rdx
0x18000e189  mov     rdx, rbx
0x18000e18c  mov     [rsp+58h+var_38], rcx
0x18000e191  mov     rcx, rdi
0x18000e194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e199  jmp     short loc_18000E1B8
0x18000e19b  mov     ecx, 32h ; '2'; dwErrCode
0x18000e1a0  call    cs:__imp_SetLastError
0x18000e1a6  lea     rcx, aRouterfindcomp_0; "RouterFindCompatibleDriver"
0x18000e1ad  call    cs:__imp_OutputDebugStringA
0x18000e1b3  mov     eax, 80070032h
0x18000e1b8  mov     rbx, [rsp+58h+arg_0]
0x18000e1bd  add     rsp, 50h
0x18000e1c1  pop     rdi
0x18000e1c2  retn
```
