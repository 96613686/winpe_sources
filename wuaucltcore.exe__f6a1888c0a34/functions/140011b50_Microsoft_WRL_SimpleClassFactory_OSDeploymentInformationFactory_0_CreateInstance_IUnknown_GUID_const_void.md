# Microsoft::WRL::SimpleClassFactory<OSDeploymentInformationFactory,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x140011b50`
- end: `0x140011c48`
- name: `?CreateInstance@?$SimpleClassFactory@VOSDeploymentInformationFactory@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `248`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140011b50`
- `0x140018c14`
- `0x14001aa60`
- `0x14001ad2c`
- `0x1400206e0`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x140011b86`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x140011b86`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<OSDeploymentInformationFactory,0>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  OSDeploymentInformationFactory *v7; // rax
  int v8; // edi
  OSDeploymentInformationFactory *v9; // rbx
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD *); // rcx
  __int64 (__fastcall ***v11)(_QWORD, __int64, _QWORD *); // [rsp+20h] [rbp-28h] BYREF

  *a4 = 0;
  if ( a2 )
  {
    RoOriginateError(2147746064LL, 0);
    return 2147746064LL;
  }
  else
  {
    v11 = 0;
    v7 = (OSDeploymentInformationFactory *)operator new(0x1D8u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v7 )
    {
      v9 = OSDeploymentInformationFactory::OSDeploymentInformationFactory(v7);
      v8 = (**(__int64 (__fastcall ***)(OSDeploymentInformationFactory *, GUID *, _QWORD))v9)(
             v9,
             &GUID_00000000_0000_0000_c000_000000000046,
             &v11);
      (*(void (__fastcall **)(OSDeploymentInformationFactory *))(*(_QWORD *)v9 + 16LL))(v9);
      if ( v8 >= 0 )
        v8 = (**v11)(v11, a3, a4);
    }
    else
    {
      v8 = -2147024882;
    }
    v10 = v11;
    if ( v11 )
    {
      v11 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD *)))(*v10)[2])(v10);
    }
    return (unsigned int)v8;
  }
}

```

## disassembly

```asm
0x140011b50  mov     [rsp+arg_0], rbx
0x140011b55  push    rbp
0x140011b56  push    rsi
0x140011b57  push    rdi
0x140011b58  sub     rsp, 30h
0x140011b5c  mov     rax, cs:__security_cookie
0x140011b63  xor     rax, rsp
0x140011b66  mov     [rsp+48h+var_20], rax
0x140011b6b  mov     rsi, r9
0x140011b6e  mov     rbp, r8
0x140011b71  mov     qword ptr [r9], 0
0x140011b78  test    rdx, rdx
0x140011b7b  jz      short loc_140011B93
0x140011b7d  xor     edx, edx
0x140011b7f  mov     ebx, 80040110h
0x140011b84  mov     ecx, ebx
0x140011b86  call    cs:__imp_RoOriginateError
0x140011b8c  mov     eax, ebx
0x140011b8e  jmp     loc_140011C2E
0x140011b93  mov     [rsp+48h+var_28], 0
0x140011b9c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140011ba3  mov     ecx, 1D8h; unsigned __int64
0x140011ba8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140011bad  test    rax, rax
0x140011bb0  jnz     short loc_140011BB9
0x140011bb2  mov     edi, 8007000Eh
0x140011bb7  jmp     short loc_140011C0C
0x140011bb9  mov     rcx, rax; this
0x140011bbc  call    ??0OSDeploymentInformationFactory@@QEAA@XZ; OSDeploymentInformationFactory::OSDeploymentInformationFactory(void)
0x140011bc1  mov     rbx, rax
0x140011bc4  mov     rcx, [rax]
0x140011bc7  mov     rax, [rcx]
0x140011bca  lea     r8, [rsp+48h+var_28]
0x140011bcf  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x140011bd6  mov     rcx, rbx
0x140011bd9  call    _guard_dispatch_icall
0x140011bde  mov     edi, eax
0x140011be0  mov     rax, [rbx]
0x140011be3  mov     rcx, rbx
0x140011be6  mov     rax, [rax+10h]
0x140011bea  call    _guard_dispatch_icall
0x140011bef  nop
0x140011bf0  test    edi, edi
0x140011bf2  js      short loc_140011C0C
0x140011bf4  mov     rcx, [rsp+48h+var_28]
0x140011bf9  mov     rax, [rcx]
0x140011bfc  mov     r8, rsi
0x140011bff  mov     rdx, rbp
0x140011c02  mov     rax, [rax]
0x140011c05  call    _guard_dispatch_icall
0x140011c0a  mov     edi, eax
0x140011c0c  mov     rcx, [rsp+48h+var_28]
0x140011c11  test    rcx, rcx
0x140011c14  jz      short loc_140011C2C
0x140011c16  mov     [rsp+48h+var_28], 0
0x140011c1f  mov     rdx, [rcx]
0x140011c22  mov     rax, [rdx+10h]
0x140011c26  call    _guard_dispatch_icall
0x140011c2b  nop
0x140011c2c  mov     eax, edi
0x140011c2e  mov     rcx, [rsp+48h+var_20]
0x140011c33  xor     rcx, rsp; StackCookie
0x140011c36  call    __security_check_cookie
0x140011c3b  mov     rbx, [rsp+48h+arg_0]
0x140011c40  add     rsp, 30h
0x140011c44  pop     rdi
0x140011c45  pop     rsi
0x140011c46  pop     rbp
0x140011c47  retn
```
