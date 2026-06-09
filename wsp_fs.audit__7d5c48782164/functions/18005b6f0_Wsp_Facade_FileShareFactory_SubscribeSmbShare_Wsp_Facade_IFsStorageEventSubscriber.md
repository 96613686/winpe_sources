# Wsp::Facade::FileShareFactory::SubscribeSmbShare(Wsp::Facade::IFsStorageEventSubscriber *)

- ea: `0x18005b6f0`
- end: `0x18005b8e1`
- name: `?SubscribeSmbShare@FileShareFactory@Facade@Wsp@@UEAA?AV?$unique_ptr@VIFsStorageEventSubscription@Facade@Wsp@@U?$default_delete@VIFsStorageEventSubscription@Facade@Wsp@@@std@@@std@@PEAVIFsStorageEventSubscriber@23@@Z`
- size: `497`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation`

## callees

- `0x180002ad0`
- `0x180002af4`
- `0x180005fdc`
- `0x18000aa10`
- `0x18000c5c4`
- `0x180015be4`
- `0x18003a300`
- `0x18004ff6c`
- `0x1800506b0`
- `0x18005ad6c`
- `0x18005b4b4`
- `0x18005b6f0`
- `0x18006aab8`
- `0x18007d950`
- `0x18007df78`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005b77b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005b77b`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall Wsp::Facade::FileShareFactory::SubscribeSmbShare(__int64 a1, _QWORD *a2, __int64 a3)
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
  void ***v14; // rdx
  __int64 v16; // [rsp+30h] [rbp-D8h] BYREF
  _QWORD v17[2]; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v18; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+50h] [rbp-B8h]
  __int64 v20; // [rsp+58h] [rbp-B0h] BYREF
  std::_Ref_count_base *v21; // [rsp+60h] [rbp-A8h]
  _BYTE v22[80]; // [rsp+68h] [rbp-A0h] BYREF
  void **v23; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v24; // [rsp+C0h] [rbp-48h]
  void ***v25; // [rsp+F0h] [rbp-18h]
  _BYTE v26[32]; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v27; // [rsp+158h] [rbp+50h] BYREF

  v27 = a3;
  v17[0] = a2;
  *a2 = 0;
  v5 = (__int128 *)_lambda_f9656dd82422a1f44b3ebded4e40a1a5_::_lambda_f9656dd82422a1f44b3ebded4e40a1a5_(&v20, a1, &v27);
  v25 = 0;
  v23 = &std::_Func_impl_no_alloc<_lambda_d82240b69d19b98b4de872dc518339bf_,bool,mismb::MSFT_SmbShareChangeEvent const &>::`vftable';
  v24 = *v5;
  v25 = &v23;
  v19 = 0;
  CurrentThread = GetCurrentThread();
  cxl::Token::OpenThreadToken((cxl::Token *)&v18, v7, v8, CurrentThread);
  Wsp::Facade::FileShareFactory::GetSmbSession(v9, &v20);
  std::wstring::wstring(v26, &base);
  mismb::MSFT_SmbShareChangeEvent::Subscribe(v22, &v20, v26, &v23);
  std::wstring::_Tidy_deallocate(v26);
  v10 = operator new(0x50u);
  v11 = mi::MiAsyncOperation::MiAsyncOperation(v10, v22);
  v16 = v11;
  mi::MiAsyncOperation::~MiAsyncOperation((mi::MiAsyncOperation *)v22);
  if ( *(_QWORD *)(v11 + 56) )
  {
    v12 = operator new(0x28u);
    v17[0] = v12;
    v13 = v19;
    v19 = 0;
    v16 = 0;
    *v12 = &Wsp::Facade::SmbFsStorageEventSubscription::`vftable';
    v12[1] = a3;
    v12[2] = v11;
    v12[4] = v13;
    v17[1] = 0;
    cxl::Token::Clear((cxl::Token *)v17);
    std::unique_ptr<Wsp::Facade::IFsStorageEventSubscription>::reset(a2, v12);
  }
  std::unique_ptr<std::_Facet_base>::~unique_ptr<std::_Facet_base>(&v16);
  if ( v21 )
    std::_Ref_count_base::_Decref(v21);
  cxl::Token::Clear((cxl::Token *)&v18);
  if ( v25 )
  {
    v14 = &v23;
    LOBYTE(v14) = v25 != &v23;
    ((void (__fastcall *)(void ***, void ***))(*v25)[4])(v25, v14);
  }
  return a2;
}

```

## disassembly

```asm
0x18005b6f0  mov     rax, rsp
0x18005b6f3  mov     [rax+8], rbx
0x18005b6f7  mov     [rax+20h], rsi
0x18005b6fb  mov     [rax+18h], r8
0x18005b6ff  push    rbp
0x18005b700  push    rdi
0x18005b701  push    r14
0x18005b703  lea     rbp, [rax-38h]
0x18005b707  sub     rsp, 120h
0x18005b70e  mov     rax, cs:__security_cookie
0x18005b715  xor     rax, rsp
0x18005b718  mov     [rbp+30h+var_20], rax
0x18005b71c  mov     r14, r8
0x18005b71f  mov     rdi, rdx
0x18005b722  mov     [rsp+130h+var_100], rdx
0x18005b727  mov     dword ptr [rsp+130h+var_110], 0
0x18005b72f  mov     qword ptr [rdx], 0
0x18005b736  mov     dword ptr [rsp+130h+var_110], 1
0x18005b73e  lea     r8, [rbp+30h+arg_10]
0x18005b742  mov     rdx, rcx
0x18005b745  lea     rcx, [rsp+130h+var_E0]
0x18005b74a  call    ??0_lambda_f9656dd82422a1f44b3ebded4e40a1a5_@@QEAA@PEAV?$WspContextBase@UIFileShareSchema@smapi@@VFileShareContext@2@@wmi@@AEBQEBUWmiInstance@2@@Z; _lambda_f9656dd82422a1f44b3ebded4e40a1a5_::_lambda_f9656dd82422a1f44b3ebded4e40a1a5_(wmi::WspContextBase<smapi::IFileShareSchema,smapi::FileShareContext> *,wmi::WmiInstance const * const &)
0x18005b74f  mov     [rbp+30h+var_48], 0
0x18005b757  lea     rcx, ??_7?$_Func_impl_no_alloc@V_lambda_d82240b69d19b98b4de872dc518339bf_@@_NAEBVMSFT_SmbShareChangeEvent@mismb@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_d82240b69d19b98b4de872dc518339bf_,bool,mismb::MSFT_SmbShareChangeEvent const &>::`vftable'
0x18005b75e  mov     [rbp+30h+var_80], rcx
0x18005b762  movups  xmm0, xmmword ptr [rax]
0x18005b765  movdqu  [rbp+30h+var_78], xmm0
0x18005b76a  lea     rax, [rbp+30h+var_80]
0x18005b76e  mov     [rbp+30h+var_48], rax
0x18005b772  mov     [rsp+130h+var_E8], 0
0x18005b77b  call    cs:__imp_GetCurrentThread
0x18005b782  nop     dword ptr [rax+rax+00h]
0x18005b787  mov     r9, rax; void *
0x18005b78a  lea     rcx, [rsp+130h+var_F0]; this
0x18005b78f  call    ?OpenThreadToken@Token@cxl@@QEAAXKHPEAX@Z; cxl::Token::OpenThreadToken(ulong,int,void *)
0x18005b794  lea     rdx, [rsp+130h+var_E0]
0x18005b799  call    ?GetSmbSession@FileShareFactory@Facade@Wsp@@AEAA?AV?$shared_ptr@VMiSession@mi@@@std@@XZ; Wsp::Facade::FileShareFactory::GetSmbSession(void)
0x18005b79e  nop
0x18005b79f  lea     rdx, base
0x18005b7a6  lea     rcx, [rbp+30h+var_40]
0x18005b7aa  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18005b7af  nop
0x18005b7b0  lea     r9, [rbp+30h+var_80]
0x18005b7b4  lea     r8, [rbp+30h+var_40]
0x18005b7b8  lea     rdx, [rsp+130h+var_E0]
0x18005b7bd  lea     rcx, [rsp+130h+var_D0]
0x18005b7c2  call    ?Subscribe@MSFT_SmbShareChangeEvent@mismb@@SA?AVMiAsyncOperation@mi@@AEBV?$shared_ptr@VMiSession@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@6@AEBV?$function@$$A6A_NAEBVMSFT_SmbShareChangeEvent@mismb@@@Z@6@@Z; mismb::MSFT_SmbShareChangeEvent::Subscribe(std::shared_ptr<mi::MiSession> const &,std::wstring const &,std::function<bool (mismb::MSFT_SmbShareChangeEvent const &)> const &)
0x18005b7c7  mov     dword ptr [rsp+130h+var_110], 3
0x18005b7cf  lea     rcx, [rbp+30h+var_40]
0x18005b7d3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005b7d8  nop
0x18005b7d9  mov     ecx, 50h ; 'P'; Size
0x18005b7de  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005b7e3  mov     [rsp+130h+var_108], rax
0x18005b7e8  lea     rdx, [rsp+130h+var_D0]
0x18005b7ed  mov     rcx, rax
0x18005b7f0  call    ??0MiAsyncOperation@mi@@QEAA@$$QEAV01@@Z; mi::MiAsyncOperation::MiAsyncOperation(mi::MiAsyncOperation &&)
0x18005b7f5  mov     rsi, rax
0x18005b7f8  mov     [rsp+130h+var_108], rax
0x18005b7fd  mov     dword ptr [rsp+130h+var_110], 7
0x18005b805  lea     rcx, [rsp+130h+var_D0]; this
0x18005b80a  call    ??1MiAsyncOperation@mi@@UEAA@XZ; mi::MiAsyncOperation::~MiAsyncOperation(void)
0x18005b80f  cmp     qword ptr [rsi+38h], 0
0x18005b814  jz      short loc_18005B874
0x18005b816  mov     ecx, 28h ; '('; Size
0x18005b81b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005b820  mov     rbx, rax
0x18005b823  mov     [rsp+130h+var_100], rax
0x18005b828  mov     rcx, [rsp+130h+var_E8]
0x18005b82d  mov     [rsp+130h+var_E8], 0
0x18005b836  mov     [rsp+130h+var_108], 0
0x18005b83f  lea     rax, ??_7SmbFsStorageEventSubscription@Facade@Wsp@@6B@; const Wsp::Facade::SmbFsStorageEventSubscription::`vftable'
0x18005b846  mov     [rbx], rax
0x18005b849  mov     [rbx+8], r14
0x18005b84d  mov     [rbx+10h], rsi
0x18005b851  mov     [rbx+20h], rcx
0x18005b855  mov     qword ptr [rsp+130h+var_F8], 0
0x18005b85e  lea     rcx, [rsp+130h+var_100]; this
0x18005b863  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x18005b868  mov     rdx, rbx
0x18005b86b  mov     rcx, rdi
0x18005b86e  call    ?reset@?$unique_ptr@VIFsStorageEventSubscription@Facade@Wsp@@U?$default_delete@VIFsStorageEventSubscription@Facade@Wsp@@@std@@@std@@QEAAXPEAVIFsStorageEventSubscription@Facade@Wsp@@@Z; std::unique_ptr<Wsp::Facade::IFsStorageEventSubscription>::reset(Wsp::Facade::IFsStorageEventSubscription *)
0x18005b873  nop
0x18005b874  lea     rcx, [rsp+130h+var_108]
0x18005b879  call    ??1?$unique_ptr@V_Facet_base@std@@U?$default_delete@V_Facet_base@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::_Facet_base>::~unique_ptr<std::_Facet_base>(void)
0x18005b87e  nop
0x18005b87f  mov     rcx, [rsp+130h+var_D8]; this
0x18005b884  test    rcx, rcx
0x18005b887  jz      short loc_18005B88F
0x18005b889  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005b88e  nop
0x18005b88f  lea     rcx, [rsp+130h+var_F0]; this
0x18005b894  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x18005b899  nop
0x18005b89a  mov     rcx, [rbp+30h+var_48]
0x18005b89e  test    rcx, rcx
0x18005b8a1  jz      short loc_18005B8B9
0x18005b8a3  mov     rdx, [rcx]
0x18005b8a6  mov     rax, [rdx+20h]
0x18005b8aa  lea     rdx, [rbp+30h+var_80]
0x18005b8ae  cmp     rcx, rdx
0x18005b8b1  setnz   dl
0x18005b8b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b8b9  mov     rax, rdi
0x18005b8bc  mov     rcx, [rbp+30h+var_20]
0x18005b8c0  xor     rcx, rsp; StackCookie
0x18005b8c3  call    __security_check_cookie
0x18005b8c8  lea     r11, [rsp+130h+var_10]
0x18005b8d0  mov     rbx, [r11+20h]
0x18005b8d4  mov     rsi, [r11+38h]
0x18005b8d8  mov     rsp, r11
0x18005b8db  pop     r14
0x18005b8dd  pop     rdi
0x18005b8de  pop     rbp
0x18005b8df  retn
```
