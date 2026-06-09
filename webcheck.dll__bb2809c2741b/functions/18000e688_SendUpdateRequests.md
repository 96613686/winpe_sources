# SendUpdateRequests

- ea: `0x18000e688`
- end: `0x18000e7f2`
- name: `SendUpdateRequests`
- size: `362`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000a6d4`
- `0x18000f2c0`
- `0x180014450`
- `0x180018570`
- `0x180018810`

## callees

- `0x18000e688`
- `0x18001ba08`
- `0x18001ba40`
- `0x18002a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000e6df`
- `ole32!CoCreateInstance` at `0x18000e6df`
- `ole32!CoUninitialize` at `0x18000e7d7`
- `ole32!CoUninitialize` at `0x18000e7d7`
- `ole32!CoInitialize` at `0x18000e6b2`
- `ole32!CoInitialize` at `0x18000e6b2`

## pseudocode

```c
__int64 __fastcall SendUpdateRequests(__int64 a1, void *a2, unsigned int a3)
{
  HRESULT v5; // ebx
  void *v6; // rdi
  void *v7; // rax
  LPVOID ppv; // [rsp+30h] [rbp-10h] BYREF
  __int64 v10; // [rsp+60h] [rbp+20h] BYREF
  __int64 v11; // [rsp+78h] [rbp+38h] BYREF

  v10 = a1;
  ppv = 0;
  v5 = CoInitialize(0);
  if ( v5 >= 0 )
  {
    v5 = CoCreateInstance(&CLSID_SubscriptionMgr, 0, 1u, &IID_ISubscriptionMgr2, &ppv);
    if ( v5 < 0 )
    {
LABEL_16:
      CoUninitialize();
      return (unsigned int)v5;
    }
    LODWORD(v10) = a3;
    if ( a2 )
    {
      v6 = a2;
    }
    else
    {
      v11 = 0;
      v5 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)ppv + 112LL))(ppv, 0, &v11);
      if ( v5 < 0 )
        goto LABEL_15;
      v6 = 0;
      (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 56LL))(v11, &v10);
      if ( (_DWORD)v10 )
      {
        v7 = operator new(saturated_mul((unsigned int)v10, 0x10u));
        v6 = v7;
        if ( v7 )
          v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, void *, __int64 *))(*(_QWORD *)v11 + 24LL))(
                 v11,
                 (unsigned int)v10,
                 v7,
                 &v10);
        else
          v5 = -2147024882;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      if ( v5 < 0 )
        goto LABEL_13;
      a3 = v10;
    }
    v5 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, void *))(*(_QWORD *)ppv + 120LL))(ppv, 0, a3, v6);
    if ( !a2 )
    {
LABEL_13:
      if ( v6 )
        operator delete(v6);
    }
LABEL_15:
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    goto LABEL_16;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000e688  mov     [rsp-18h+arg_8], rbx
0x18000e68d  mov     [rsp-18h+arg_10], rsi
0x18000e692  mov     [rsp-18h+arg_0], rcx
0x18000e697  push    rbp
0x18000e698  push    rdi
0x18000e699  push    r14
0x18000e69b  mov     rbp, rsp
0x18000e69e  sub     rsp, 40h
0x18000e6a2  xor     ecx, ecx; pvReserved
0x18000e6a4  mov     [rbp+var_10], 0
0x18000e6ac  mov     esi, r8d
0x18000e6af  mov     r14, rdx
0x18000e6b2  call    cs:__imp_CoInitialize
0x18000e6b8  mov     ebx, eax
0x18000e6ba  test    eax, eax
0x18000e6bc  js      loc_18000E7DD
0x18000e6c2  xor     edx, edx; pUnkOuter
0x18000e6c4  lea     rax, [rbp+var_10]
0x18000e6c8  lea     r9, IID_ISubscriptionMgr2; riid
0x18000e6cf  mov     [rsp+40h+ppv], rax; ppv
0x18000e6d4  lea     rcx, CLSID_SubscriptionMgr; rclsid
0x18000e6db  lea     r8d, [rdx+1]; dwClsContext
0x18000e6df  call    cs:__imp_CoCreateInstance
0x18000e6e5  mov     ebx, eax
0x18000e6e7  test    eax, eax
0x18000e6e9  js      loc_18000E7D7
0x18000e6ef  mov     dword ptr [rbp+arg_0], esi
0x18000e6f2  test    r14, r14
0x18000e6f5  jnz     loc_18000E798
0x18000e6fb  mov     rcx, [rbp+var_10]
0x18000e6ff  lea     r8, [rbp+arg_18]
0x18000e703  mov     [rbp+arg_18], r14
0x18000e707  xor     edx, edx
0x18000e709  mov     rax, [rcx]
0x18000e70c  mov     rax, [rax+70h]
0x18000e710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e715  mov     ebx, eax
0x18000e717  test    eax, eax
0x18000e719  js      loc_18000E7C7
0x18000e71f  mov     rcx, [rbp+arg_18]
0x18000e723  lea     rdx, [rbp+arg_0]
0x18000e727  xor     edi, edi
0x18000e729  mov     rax, [rcx]
0x18000e72c  mov     rax, [rax+38h]
0x18000e730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e735  mov     eax, dword ptr [rbp+arg_0]
0x18000e738  test    eax, eax
0x18000e73a  jz      short loc_18000E77F
0x18000e73c  mov     ecx, eax
0x18000e73e  lea     eax, [rdi+10h]
0x18000e741  mul     rcx
0x18000e744  lea     rcx, [rdi-1]
0x18000e748  cmovb   rax, rcx
0x18000e74c  mov     rcx, rax; dwBytes
0x18000e74f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e754  mov     rdi, rax
0x18000e757  test    rax, rax
0x18000e75a  jz      short loc_18000E77A
0x18000e75c  mov     rcx, [rbp+arg_18]
0x18000e760  lea     r9, [rbp+arg_0]
0x18000e764  mov     edx, dword ptr [rbp+arg_0]
0x18000e767  mov     r8, rdi
0x18000e76a  mov     rax, [rcx]
0x18000e76d  mov     rax, [rax+18h]
0x18000e771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e776  mov     ebx, eax
0x18000e778  jmp     short loc_18000E77F
0x18000e77a  mov     ebx, 8007000Eh
0x18000e77f  mov     rcx, [rbp+arg_18]
0x18000e783  mov     rax, [rcx]
0x18000e786  mov     rax, [rax+10h]
0x18000e78a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e78f  test    ebx, ebx
0x18000e791  js      short loc_18000E7BA
0x18000e793  mov     esi, dword ptr [rbp+arg_0]
0x18000e796  jmp     short loc_18000E79B
0x18000e798  mov     rdi, r14
0x18000e79b  mov     rcx, [rbp+var_10]
0x18000e79f  mov     r9, rdi
0x18000e7a2  mov     r8d, esi
0x18000e7a5  xor     edx, edx
0x18000e7a7  mov     rax, [rcx]
0x18000e7aa  mov     rax, [rax+78h]
0x18000e7ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7b3  mov     ebx, eax
0x18000e7b5  test    r14, r14
0x18000e7b8  jnz     short loc_18000E7C7
0x18000e7ba  test    rdi, rdi
0x18000e7bd  jz      short loc_18000E7C7
0x18000e7bf  mov     rcx, rdi; lpMem
0x18000e7c2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e7c7  mov     rcx, [rbp+var_10]
0x18000e7cb  mov     rax, [rcx]
0x18000e7ce  mov     rax, [rax+10h]
0x18000e7d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7d7  call    cs:__imp_CoUninitialize
0x18000e7dd  mov     rsi, [rsp+40h+arg_10]
0x18000e7e2  mov     eax, ebx
0x18000e7e4  mov     rbx, [rsp+40h+arg_8]
0x18000e7e9  add     rsp, 40h
0x18000e7ed  pop     r14
0x18000e7ef  pop     rdi
0x18000e7f0  pop     rbp
0x18000e7f1  retn
```
