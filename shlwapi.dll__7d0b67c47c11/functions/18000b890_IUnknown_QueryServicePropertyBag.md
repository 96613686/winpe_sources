# IUnknown_QueryServicePropertyBag

- ea: `0x18000b890`
- end: `0x18000b91f`
- name: `IUnknown_QueryServicePropertyBag`
- size: `143`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000b890`
- `0x180012550`
- `0x180037010`

## import_xrefs

- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18000b8cc`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18000b8cc`

## pseudocode

```c
__int64 __fastcall IUnknown_QueryServicePropertyBag(IUnknown *a1, unsigned int a2, __int64 a3, __int64 a4)
{
  HRESULT v7; // ebx
  void *ppvOut; // [rsp+30h] [rbp-38h] BYREF

  ppvOut = 0;
  v7 = IUnknown_QueryService(
         a1,
         (const GUID *const)&SID_STopLevelBrowser,
         &GUID_dfbc7e30_f9e5_455f_88f8_fa98c1e494ca,
         &ppvOut);
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(void *, _QWORD, __int64, __int64))(*(_QWORD *)ppvOut + 152LL))(ppvOut, a2, a3, a4);
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000b890  push    rbx
0x18000b892  push    rbp
0x18000b893  push    rsi
0x18000b894  push    rdi
0x18000b895  sub     rsp, 48h
0x18000b899  mov     rax, cs:__security_cookie
0x18000b8a0  xor     rax, rsp
0x18000b8a3  mov     [rsp+68h+var_30], rax
0x18000b8a8  mov     rbp, r9
0x18000b8ab  mov     [rsp+68h+ppvOut], 0
0x18000b8b4  mov     rsi, r8
0x18000b8b7  lea     r9, [rsp+68h+ppvOut]; ppvOut
0x18000b8bc  mov     edi, edx
0x18000b8be  lea     r8, _GUID_dfbc7e30_f9e5_455f_88f8_fa98c1e494ca; riid
0x18000b8c5  lea     rdx, SID_STopLevelBrowser; guidService
0x18000b8cc  call    cs:__imp_IUnknown_QueryService
0x18000b8d2  mov     ebx, eax
0x18000b8d4  test    eax, eax
0x18000b8d6  js      short loc_18000B907
0x18000b8d8  mov     rcx, [rsp+68h+ppvOut]
0x18000b8dd  mov     r9, rbp
0x18000b8e0  mov     r8, rsi
0x18000b8e3  mov     edx, edi
0x18000b8e5  mov     rax, [rcx]
0x18000b8e8  mov     rax, [rax+98h]
0x18000b8ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8f4  mov     rcx, [rsp+68h+ppvOut]
0x18000b8f9  mov     ebx, eax
0x18000b8fb  mov     rax, [rcx]
0x18000b8fe  mov     rax, [rax+10h]
0x18000b902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b907  mov     eax, ebx
0x18000b909  mov     rcx, [rsp+68h+var_30]
0x18000b90e  xor     rcx, rsp; StackCookie
0x18000b911  call    __security_check_cookie
0x18000b916  add     rsp, 48h
0x18000b91a  pop     rdi
0x18000b91b  pop     rsi
0x18000b91c  pop     rbp
0x18000b91d  pop     rbx
0x18000b91e  retn
```
