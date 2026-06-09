# IUnknown_QueryServiceExec

- ea: `0x18000e3d0`
- end: `0x18000e477`
- name: `IUnknown_QueryServiceExec`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000e3d0`
- `0x180012550`
- `0x180037010`

## import_xrefs

- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18000e415`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18000e415`

## pseudocode

```c
__int64 __fastcall IUnknown_QueryServiceExec(
        IUnknown *a1,
        const GUID *a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7)
{
  HRESULT v9; // ebx
  void *ppvOut; // [rsp+40h] [rbp-38h] BYREF

  ppvOut = 0;
  v9 = IUnknown_QueryService(a1, a2, &GUID_b722bccb_4e68_101b_a2bc_00aa00404770, &ppvOut);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(void *, __int64, _QWORD, _QWORD, __int64, __int64))(*(_QWORD *)ppvOut + 32LL))(
           ppvOut,
           a3,
           a4,
           a5,
           a6,
           a7);
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000e3d0  push    rbx
0x18000e3d2  push    rbp
0x18000e3d3  push    rsi
0x18000e3d4  push    rdi
0x18000e3d5  push    r14
0x18000e3d7  sub     rsp, 50h
0x18000e3db  mov     rax, cs:__security_cookie
0x18000e3e2  xor     rax, rsp
0x18000e3e5  mov     [rsp+78h+var_30], rax
0x18000e3ea  mov     rbp, [rsp+78h+arg_28]
0x18000e3f2  mov     esi, r9d
0x18000e3f5  mov     r14, [rsp+78h+arg_30]
0x18000e3fd  lea     r9, [rsp+78h+ppvOut]; ppvOut
0x18000e402  mov     rdi, r8
0x18000e405  mov     [rsp+78h+ppvOut], 0
0x18000e40e  lea     r8, _GUID_b722bccb_4e68_101b_a2bc_00aa00404770; riid
0x18000e415  call    cs:__imp_IUnknown_QueryService
0x18000e41b  mov     ebx, eax
0x18000e41d  test    eax, eax
0x18000e41f  js      short loc_18000E45D
0x18000e421  mov     rcx, [rsp+78h+ppvOut]
0x18000e426  mov     r8d, esi
0x18000e429  mov     r9d, [rsp+78h+arg_20]
0x18000e431  mov     rdx, rdi
0x18000e434  mov     [rsp+78h+var_50], r14
0x18000e439  mov     [rsp+78h+var_58], rbp
0x18000e43e  mov     rax, [rcx]
0x18000e441  mov     rax, [rax+20h]
0x18000e445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e44a  mov     rcx, [rsp+78h+ppvOut]
0x18000e44f  mov     ebx, eax
0x18000e451  mov     rax, [rcx]
0x18000e454  mov     rax, [rax+10h]
0x18000e458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e45d  mov     eax, ebx
0x18000e45f  mov     rcx, [rsp+78h+var_30]
0x18000e464  xor     rcx, rsp; StackCookie
0x18000e467  call    __security_check_cookie
0x18000e46c  add     rsp, 50h
0x18000e470  pop     r14
0x18000e472  pop     rdi
0x18000e473  pop     rsi
0x18000e474  pop     rbp
0x18000e475  pop     rbx
0x18000e476  retn
```
