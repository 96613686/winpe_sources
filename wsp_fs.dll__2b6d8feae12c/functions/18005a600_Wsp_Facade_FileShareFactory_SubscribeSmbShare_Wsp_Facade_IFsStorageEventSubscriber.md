# Wsp::Facade::FileShareFactory::SubscribeSmbShare(Wsp::Facade::IFsStorageEventSubscriber *)

- ea: `0x18005a600`
- end: `0x18005a7f0`
- name: `?SubscribeSmbShare@FileShareFactory@Facade@Wsp@@UEAA?AV?$unique_ptr@VIFsStorageEventSubscription@Facade@Wsp@@U?$default_delete@VIFsStorageEventSubscription@Facade@Wsp@@@std@@@std@@PEAVIFsStorageEventSubscriber@23@@Z`
- size: `496`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation`

## callees

- `0x180002a70`
- `0x180002a94`
- `0x180005e68`
- `0x18000a6dc`
- `0x18000c284`
- `0x1800154e0`
- `0x180038fb8`
- `0x18003a710`
- `0x18004eed4`
- `0x180059c6c`
- `0x18005a3b4`
- `0x18005a600`
- `0x1800697b8`
- `0x18007bb7c`
- `0x18007c170`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005a68b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005a68b`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 *__fastcall Wsp::Facade::FileShareFactory::SubscribeSmbShare(__int64 a1, __int64 *a2, __int64 a3)
{
  __int128 *v5; // rax
  HANDLE CurrentThread; // rax
  unsigned int v7; // edx
  int v8; // r8d
  __int64 v9; // rcx
  void *v10; // rax
  __int64 v11; // rsi
  _QWORD *v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rdx
  void ***v16; // rdx
  __int64 v18; // [rsp+30h] [rbp-D8h] BYREF
  _QWORD v19[2]; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v21; // [rsp+50h] [rbp-B8h]
  __int64 v22; // [rsp+58h] [rbp-B0h] BYREF
  std::_Ref_count_base *v23; // [rsp+60h] [rbp-A8h]
  _BYTE v24[80]; // [rsp+68h] [rbp-A0h] BYREF
  void **v25; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v26; // [rsp+C0h] [rbp-48h]
  void ***v27; // [rsp+F0h] [rbp-18h]
  _BYTE v28[32]; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v29; // [rsp+158h] [rbp+50h] BYREF

  v29 = a3;
  v19[0] = a2;
  *a2 = 0;
  v5 = (__int128 *)_lambda_f9656dd82422a1f44b3ebded4e40a1a5_::_lambda_f9656dd82422a1f44b3ebded4e40a1a5_(&v22, a1, &v29);
  v27 = 0;
  v25 = &std::_Func_impl_no_alloc<_lambda_d82240b69d19b98b4de872dc518339bf_,bool,mismb::MSFT_SmbShareChangeEvent const &>::`vftable';
  v26 = *v5;
  v27 = &v25;
  v21 = 0;
  CurrentThread = GetCurrentThread();
  cxl::Token::OpenThreadToken((cxl::Token *)&v20, v7, v8, CurrentThread);
  Wsp::Facade::FileShareFactory::GetSmbSession(v9, &v22);
  std::wstring::wstring(v28, &base);
  mismb::MSFT_SmbShareChangeEvent::Subscribe(v24, &v22, v28, &v25);
  std::wstring::_Tidy_deallocate(v28);
  v10 = operator new(0x50u);
  v11 = mi::MiAsyncOperation::MiAsyncOperation(v10, v24);
  v18 = v11;
  mi::MiAsyncOperation::~MiAsyncOperation((mi::MiAsyncOperation *)v24);
  if ( *(_QWORD *)(v11 + 56) )
  {
    v12 = operator new(0x28u);
    v19[0] = v12;
    v13 = v21;
    v21 = 0;
    v18 = 0;
    *v12 = &Wsp::Facade::SmbFsStorageEventSubscription::`vftable';
    v12[1] = a3;
    v12[2] = v11;
    v12[4] = v13;
    v19[1] = 0;
    cxl::Token::Clear((cxl::Token *)v19);
    v15 = *a2;
    *a2 = (__int64)v12;
    if ( v15 )
      std::default_delete<Wsp::Facade::IFsStorageEventSubscription>::operator()(v14, v15);
  }
  std::unique_ptr<std::_Facet_base>::~unique_ptr<std::_Facet_base>(&v18);
  if ( v23 )
    std::_Ref_count_base::_Decref(v23);
  cxl::Token::Clear((cxl::Token *)&v20);
  if ( v27 )
  {
    v16 = &v25;
    LOBYTE(v16) = v27 != &v25;
    ((void (__fastcall *)(void ***, void ***))(*v27)[4])(v27, v16);
  }
  return a2;
}

```

## disassembly

```asm
0x18005a600  mov     rax, rsp
0x18005a603  mov     [rax+8], rbx
0x18005a607  mov     [rax+20h], rsi
0x18005a60b  mov     [rax+18h], r8
0x18005a60f  push    rbp
0x18005a610  push    rdi
0x18005a611  push    r14
0x18005a613  lea     rbp, [rax-38h]
0x18005a617  sub     rsp, 120h
0x18005a61e  mov     rax, cs:__security_cookie
0x18005a625  xor     rax, rsp
0x18005a628  mov     [rbp+30h+var_20], rax
0x18005a62c  mov     r14, r8
0x18005a62f  mov     rdi, rdx
0x18005a632  mov     [rsp+130h+var_100], rdx
0x18005a637  mov     dword ptr [rsp+130h+var_110], 0
0x18005a63f  mov     qword ptr [rdx], 0
0x18005a646  mov     dword ptr [rsp+130h+var_110], 1
0x18005a64e  lea     r8, [rbp+30h+arg_10]
0x18005a652  mov     rdx, rcx
0x18005a655  lea     rcx, [rsp+130h+var_E0]
0x18005a65a  call    ??0_lambda_f9656dd82422a1f44b3ebded4e40a1a5_@@QEAA@PEAV?$WspContextBase@UIFileShareSchema@smapi@@VFileShareContext@2@@wmi@@AEBQEBUWmiInstance@2@@Z; _lambda_f9656dd82422a1f44b3ebded4e40a1a5_::_lambda_f9656dd82422a1f44b3ebded4e40a1a5_(wmi::WspContextBase<smapi::IFileShareSchema,smapi::FileShareContext> *,wmi::WmiInstance const * const &)
0x18005a65f  mov     [rbp+30h+var_48], 0
0x18005a667  lea     rcx, ??_7?$_Func_impl_no_alloc@V_lambda_d82240b69d19b98b4de872dc518339bf_@@_NAEBVMSFT_SmbShareChangeEvent@mismb@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_d82240b69d19b98b4de872dc518339bf_,bool,mismb::MSFT_SmbShareChangeEvent const &>::`vftable'
0x18005a66e  mov     [rbp+30h+var_80], rcx
0x18005a672  movups  xmm0, xmmword ptr [rax]
0x18005a675  movdqu  [rbp+30h+var_78], xmm0
0x18005a67a  lea     rax, [rbp+30h+var_80]
0x18005a67e  mov     [rbp+30h+var_48], rax
0x18005a682  mov     [rsp+130h+var_E8], 0
0x18005a68b  call    cs:__imp_GetCurrentThread
0x18005a691  mov     r9, rax; void *
0x18005a694  lea     rcx, [rsp+130h+var_F0]; this
0x18005a699  call    ?OpenThreadToken@Token@cxl@@QEAAXKHPEAX@Z; cxl::Token::OpenThreadToken(ulong,int,void *)
0x18005a69e  lea     rdx, [rsp+130h+var_E0]
0x18005a6a3  call    ?GetSmbSession@FileShareFactory@Facade@Wsp@@AEAA?AV?$shared_ptr@VMiSession@mi@@@std@@XZ; Wsp::Facade::FileShareFactory::GetSmbSession(void)
0x18005a6a8  nop
0x18005a6a9  lea     rdx, base
0x18005a6b0  lea     rcx, [rbp+30h+var_40]
0x18005a6b4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18005a6b9  nop
0x18005a6ba  lea     r9, [rbp+30h+var_80]
0x18005a6be  lea     r8, [rbp+30h+var_40]
0x18005a6c2  lea     rdx, [rsp+130h+var_E0]
0x18005a6c7  lea     rcx, [rsp+130h+var_D0]
0x18005a6cc  call    ?Subscribe@MSFT_SmbShareChangeEvent@mismb@@SA?AVMiAsyncOperation@mi@@AEBV?$shared_ptr@VMiSession@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@6@AEBV?$function@$$A6A_NAEBVMSFT_SmbShareChangeEvent@mismb@@@Z@6@@Z; mismb::MSFT_SmbShareChangeEvent::Subscribe(std::shared_ptr<mi::MiSession> const &,std::wstring const &,std::function<bool (mismb::MSFT_SmbShareChangeEvent const &)> const &)
0x18005a6d1  mov     dword ptr [rsp+130h+var_110], 3
0x18005a6d9  lea     rcx, [rbp+30h+var_40]
0x18005a6dd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005a6e2  nop
0x18005a6e3  mov     ecx, 50h ; 'P'; Size
0x18005a6e8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005a6ed  mov     [rsp+130h+var_108], rax
0x18005a6f2  lea     rdx, [rsp+130h+var_D0]
0x18005a6f7  mov     rcx, rax
0x18005a6fa  call    ??0MiAsyncOperation@mi@@QEAA@$$QEAV01@@Z; mi::MiAsyncOperation::MiAsyncOperation(mi::MiAsyncOperation &&)
0x18005a6ff  mov     rsi, rax
0x18005a702  mov     [rsp+130h+var_108], rax
0x18005a707  mov     dword ptr [rsp+130h+var_110], 7
0x18005a70f  lea     rcx, [rsp+130h+var_D0]; this
0x18005a714  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18005a719  cmp     qword ptr [rsi+38h], 0
0x18005a71e  jz      short loc_18005A783
0x18005a720  mov     ecx, 28h ; '('; Size
0x18005a725  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005a72a  mov     rbx, rax
0x18005a72d  mov     [rsp+130h+var_100], rax
0x18005a732  mov     rcx, [rsp+130h+var_E8]
0x18005a737  mov     [rsp+130h+var_E8], 0
0x18005a740  mov     [rsp+130h+var_108], 0
0x18005a749  lea     rax, ??_7SmbFsStorageEventSubscription@Facade@Wsp@@6B@; const Wsp::Facade::SmbFsStorageEventSubscription::`vftable'
0x18005a750  mov     [rbx], rax
0x18005a753  mov     [rbx+8], r14
0x18005a757  mov     [rbx+10h], rsi
0x18005a75b  mov     [rbx+20h], rcx
0x18005a75f  mov     qword ptr [rsp+130h+var_F8], 0
0x18005a768  lea     rcx, [rsp+130h+var_100]; this
0x18005a76d  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x18005a772  mov     rdx, [rdi]
0x18005a775  mov     [rdi], rbx
0x18005a778  test    rdx, rdx
0x18005a77b  jz      short loc_18005A783
0x18005a77d  call    ??R?$default_delete@VIFsStorageEventSubscription@Facade@Wsp@@@std@@QEBAXPEAVIFsStorageEventSubscription@Facade@Wsp@@@Z; std::default_delete<Wsp::Facade::IFsStorageEventSubscription>::operator()(Wsp::Facade::IFsStorageEventSubscription *)
0x18005a782  nop
0x18005a783  lea     rcx, [rsp+130h+var_108]
0x18005a788  call    ??1?$unique_ptr@V_Facet_base@std@@U?$default_delete@V_Facet_base@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::_Facet_base>::~unique_ptr<std::_Facet_base>(void)
0x18005a78d  nop
0x18005a78e  mov     rcx, [rsp+130h+var_D8]; this
0x18005a793  test    rcx, rcx
0x18005a796  jz      short loc_18005A79E
0x18005a798  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005a79d  nop
0x18005a79e  lea     rcx, [rsp+130h+var_F0]; this
0x18005a7a3  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x18005a7a8  nop
0x18005a7a9  mov     rcx, [rbp+30h+var_48]
0x18005a7ad  test    rcx, rcx
0x18005a7b0  jz      short loc_18005A7C8
0x18005a7b2  mov     rdx, [rcx]
0x18005a7b5  mov     rax, [rdx+20h]
0x18005a7b9  lea     rdx, [rbp+30h+var_80]
0x18005a7bd  cmp     rcx, rdx
0x18005a7c0  setnz   dl
0x18005a7c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a7c8  mov     rax, rdi
0x18005a7cb  mov     rcx, [rbp+30h+var_20]
0x18005a7cf  xor     rcx, rsp; StackCookie
0x18005a7d2  call    __security_check_cookie
0x18005a7d7  lea     r11, [rsp+130h+var_10]
0x18005a7df  mov     rbx, [r11+20h]
0x18005a7e3  mov     rsi, [r11+38h]
0x18005a7e7  mov     rsp, r11
0x18005a7ea  pop     r14
0x18005a7ec  pop     rdi
0x18005a7ed  pop     rbp
0x18005a7ee  retn
```
