# RouterFindCompatibleDriver

- ea: `0x18000ef40`
- end: `0x18000eff0`
- name: `RouterFindCompatibleDriver`
- size: `176`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000ef40`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000efc0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000efc0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000efd3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000efd3`

## string_xrefs

- `0x18000efcc`: `RouterFindCompatibleDriver`

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
0x18000ef40  mov     [rsp+arg_0], rbx
0x18000ef45  push    rdi
0x18000ef46  sub     rsp, 50h
0x18000ef4a  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000ef51  mov     r11d, r9d
0x18000ef54  mov     rbx, rdx
0x18000ef57  mov     rdi, rcx
0x18000ef5a  jnz     short loc_18000EFBB
0x18000ef5c  mov     r9d, [rsp+58h+arg_30]
0x18000ef64  mov     r10, [rsp+58h+arg_40]
0x18000ef6c  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000ef73  mov     rdx, [rsp+58h+arg_28]
0x18000ef7b  mov     rcx, [rsp+58h+arg_20]
0x18000ef83  mov     [rsp+58h+var_18], r10
0x18000ef88  mov     r10, [rsp+58h+arg_38]
0x18000ef90  mov     rax, [rax+598h]
0x18000ef97  mov     [rsp+58h+var_20], r10
0x18000ef9c  mov     [rsp+58h+var_28], r9d
0x18000efa1  mov     r9d, r11d
0x18000efa4  mov     [rsp+58h+var_30], rdx
0x18000efa9  mov     rdx, rbx
0x18000efac  mov     [rsp+58h+var_38], rcx
0x18000efb1  mov     rcx, rdi
0x18000efb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efb9  jmp     short loc_18000EFE4
0x18000efbb  mov     ecx, 32h ; '2'; dwErrCode
0x18000efc0  call    cs:__imp_SetLastError
0x18000efc7  nop     dword ptr [rax+rax+00h]
0x18000efcc  lea     rcx, aRouterfindcomp_0; "RouterFindCompatibleDriver"
0x18000efd3  call    cs:__imp_OutputDebugStringA
0x18000efda  nop     dword ptr [rax+rax+00h]
0x18000efdf  mov     eax, 80070032h
0x18000efe4  mov     rbx, [rsp+58h+arg_0]
0x18000efe9  add     rsp, 50h
0x18000efed  pop     rdi
0x18000efee  retn
```
