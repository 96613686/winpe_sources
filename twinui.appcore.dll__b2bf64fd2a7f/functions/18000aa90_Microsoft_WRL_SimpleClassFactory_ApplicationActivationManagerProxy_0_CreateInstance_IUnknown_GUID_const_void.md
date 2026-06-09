# Microsoft::WRL::SimpleClassFactory<ApplicationActivationManagerProxy,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000aa90`
- end: `0x18000adfa`
- name: `?CreateInstance@?$SimpleClassFactory@VApplicationActivationManagerProxy@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `874`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000aa90`
- `0x18000ae00`
- `0x18000afc0`
- `0x18001cc38`
- `0x18002b1e0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000aaf3`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000aaf3`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000ad66`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000ad66`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<ApplicationActivationManagerProxy,0>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  char *v6; // rdi
  LPUNKNOWN v7; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // r15
  __int64 v9; // rcx
  LPUNKNOWN v10; // rcx
  unsigned int v11; // ebx
  signed __int32 j; // edx
  __int64 v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // rbx
  __int64 v16; // rcx
  __int64 v17; // rbx
  __int64 v18; // rcx
  signed __int32 i; // edx
  __int64 v21; // [rsp+20h] [rbp-48h] BYREF
  __int64 v22; // [rsp+28h] [rbp-40h]
  __int64 v23; // [rsp+30h] [rbp-38h]
  char *v24; // [rsp+38h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  LPUNKNOWN ppunkMarshal; // [rsp+78h] [rbp+10h] BYREF

  *a4 = 0;
  if ( a2 )
  {
    RoOriginateError(2147746064LL, 0);
    return 2147746064LL;
  }
  else
  {
    v6 = (char *)operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v6 )
    {
      *((_QWORD *)v6 + 4) = &CActivatedEventArgsBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
      *((_QWORD *)v6 + 7) = 0;
      ppunkMarshal = 0;
      if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
      {
        v7 = ppunkMarshal;
        QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
        v9 = *((_QWORD *)v6 + 7);
        if ( v9 )
        {
          *((_QWORD *)v6 + 7) = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        }
        ((void (__fastcall *)(LPUNKNOWN, GUID *, char *))QueryInterface)(
          v7,
          &GUID_00000003_0000_0000_c000_000000000046,
          v6 + 56);
      }
      v10 = ppunkMarshal;
      if ( ppunkMarshal )
      {
        ppunkMarshal = 0;
        ((void (__fastcall *)(LPUNKNOWN))v10->lpVtbl->Release)(v10);
      }
      *((_DWORD *)v6 + 17) = 1;
      *(_QWORD *)v6 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IApplicationActivationManager,IApplicationActivationManagerPriv,IServiceProvider,IObjectWithSite,Microsoft::WRL::FtmBase>::`vftable';
      *((_QWORD *)v6 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IApplicationActivationManager,IApplicationActivationManagerPriv,IServiceProvider,IObjectWithSite,Microsoft::WRL::FtmBase>::`vftable'{for `IApplicationActivationManagerPriv'};
      *((_QWORD *)v6 + 2) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IApplicationActivationManager,IApplicationActivationManagerPriv,IServiceProvider,IObjectWithSite,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IServiceProvider,IObjectWithSite,Microsoft::WRL::FtmBase>'};
      *((_QWORD *)v6 + 3) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IApplicationActivationManager,IApplicationActivationManagerPriv,IServiceProvider,IObjectWithSite,Microsoft::WRL::FtmBase>::`vftable'{for `IObjectWithSite'};
      *((_QWORD *)v6 + 4) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IApplicationActivationManager,IApplicationActivationManagerPriv,IServiceProvider,IObjectWithSite,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
      if ( Microsoft::WRL::Details::ModuleBase::module_ )
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
      *(_QWORD *)v6 = &ApplicationActivationManagerProxy::`vftable';
      *((_QWORD *)v6 + 1) = &ApplicationActivationManagerProxy::`vftable'{for `IApplicationActivationManagerPriv'};
      *((_QWORD *)v6 + 2) = &ApplicationActivationManagerProxy::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IServiceProvider,IObjectWithSite,Microsoft::WRL::FtmBase>'};
      *((_QWORD *)v6 + 3) = &ApplicationActivationManagerProxy::`vftable'{for `IObjectWithSite'};
      *((_QWORD *)v6 + 4) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IApplicationActivationManager,IApplicationActivationManagerPriv,IServiceProvider,IObjectWithSite,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
      *((_QWORD *)v6 + 9) = 0;
      *((_QWORD *)v6 + 10) = 0;
      *((_QWORD *)v6 + 11) = 0;
      *((_QWORD *)v6 + 12) = 0;
      wil::CoCreateInstanceExNoThrow<IApplicationActivationManager,IApplicationActivationManagerPriv,IObjectWithSite>(&v21);
      v11 = (unsigned int)v24;
      if ( (int)v24 >= 0 )
      {
        v13 = v23;
        v23 = 0;
        v14 = *((_QWORD *)v6 + 10);
        if ( v14 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        *((_QWORD *)v6 + 10) = v13;
        v15 = v22;
        v22 = 0;
        v16 = *((_QWORD *)v6 + 12);
        if ( v16 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        *((_QWORD *)v6 + 12) = v15;
        v17 = v21;
        v21 = 0;
        v18 = *((_QWORD *)v6 + 11);
        if ( v18 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        *((_QWORD *)v6 + 11) = v17;
        std::tuple<long,std::tuple<wil::com_ptr_t<IApplicationActivationManager,wil::err_returncode_policy>,wil::com_ptr_t<IApplicationActivationManagerPriv,wil::err_returncode_policy>,wil::com_ptr_t<IObjectWithSite,wil::err_returncode_policy>>>::~tuple<long,std::tuple<wil::com_ptr_t<IApplicationActivationManager,wil::err_returncode_policy>,wil::com_ptr_t<IApplicationActivationManagerPriv,wil::err_returncode_policy>,wil::com_ptr_t<IObjectWithSite,wil::err_returncode_policy>>>(&v21);
        (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
        for ( i = *((_DWORD *)v6 + 17); i != 0x7FFFFFFF; i = *((_DWORD *)v6 + 17) )
        {
          if ( i == _InterlockedCompareExchange((volatile signed __int32 *)v6 + 17, i - 1, i) )
            break;
        }
        if ( i == 1 )
        {
          (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v6 + 48LL))(v6, 1);
          if ( Microsoft::WRL::Details::ModuleBase::module_ )
            (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                                 + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
        }
        v11 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v6)(v6, a3, a4);
        (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x36,
          (unsigned int)"onecoreuap\\shell\\twinui\\activation\\lib\\applicationactivationmanagerproxy.cpp",
          (const char *)(unsigned int)v24,
          v21);
        std::tuple<long,std::tuple<wil::com_ptr_t<IApplicationActivationManager,wil::err_returncode_policy>,wil::com_ptr_t<IApplicationActivationManagerPriv,wil::err_returncode_policy>,wil::com_ptr_t<IObjectWithSite,wil::err_returncode_policy>>>::~tuple<long,std::tuple<wil::com_ptr_t<IApplicationActivationManager,wil::err_returncode_policy>,wil::com_ptr_t<IApplicationActivationManagerPriv,wil::err_returncode_policy>,wil::com_ptr_t<IObjectWithSite,wil::err_returncode_policy>>>(&v21);
        for ( j = *((_DWORD *)v6 + 17); j != 0x7FFFFFFF; j = *((_DWORD *)v6 + 17) )
        {
          if ( j == _InterlockedCompareExchange((volatile signed __int32 *)v6 + 17, j - 1, j) )
            break;
        }
        if ( j == 1 )
        {
          (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v6 + 48LL))(v6, 1);
          if ( Microsoft::WRL::Details::ModuleBase::module_ )
            (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                                 + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
        }
      }
    }
    else
    {
      return (unsigned int)-2147024882;
    }
    return v11;
  }
}

```

## disassembly

```asm
0x18000aa90  mov     [rsp+arg_0], rbx
0x18000aa95  mov     [rsp+arg_10], rbp
0x18000aa9a  push    rsi
0x18000aa9b  push    rdi
0x18000aa9c  push    r12
0x18000aa9e  push    r14
0x18000aaa0  push    r15
0x18000aaa2  sub     rsp, 40h
0x18000aaa6  mov     r14, r9
0x18000aaa9  mov     rbp, r8
0x18000aaac  xor     r12d, r12d
0x18000aaaf  mov     [r9], r12
0x18000aab2  test    rdx, rdx
0x18000aab5  jnz     loc_18000AD5F
0x18000aabb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000aac2  mov     ecx, 68h ; 'h'; unsigned __int64
0x18000aac7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000aacc  mov     rdi, rax
0x18000aacf  test    rax, rax
0x18000aad2  jz      loc_18000ADBC
0x18000aad8  lea     rax, ??_7CActivatedEventArgsBase@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const CActivatedEventArgsBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000aadf  mov     [rdi+20h], rax
0x18000aae3  mov     [rdi+38h], r12
0x18000aae7  mov     [rsp+68h+ppunkMarshal], r12
0x18000aaec  lea     rdx, [rsp+68h+ppunkMarshal]; ppunkMarshal
0x18000aaf1  xor     ecx, ecx; punkOuter
0x18000aaf3  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18000aaf9  test    eax, eax
0x18000aafb  js      short loc_18000AB39
0x18000aafd  mov     rbx, [rsp+68h+ppunkMarshal]
0x18000ab02  mov     rax, [rbx]
0x18000ab05  mov     r15, [rax]
0x18000ab08  mov     rcx, [rdi+38h]
0x18000ab0c  test    rcx, rcx
0x18000ab0f  jz      short loc_18000AB22
0x18000ab11  mov     [rdi+38h], r12
0x18000ab15  mov     rdx, [rcx]
0x18000ab18  mov     rax, [rdx+10h]
0x18000ab1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab21  nop
0x18000ab22  lea     r8, [rdi+38h]
0x18000ab26  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18000ab2d  mov     rcx, rbx
0x18000ab30  mov     rax, r15
0x18000ab33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab38  nop
0x18000ab39  mov     rcx, [rsp+68h+ppunkMarshal]
0x18000ab3e  test    rcx, rcx
0x18000ab41  jz      short loc_18000AB55
0x18000ab43  mov     [rsp+68h+ppunkMarshal], r12
0x18000ab48  mov     rax, [rcx]
0x18000ab4b  mov     rax, [rax+10h]
0x18000ab4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab54  nop
0x18000ab55  mov     dword ptr [rdi+44h], 1
0x18000ab5c  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIApplicationActivationManager@@UIApplicationActivationManagerPriv@@UIServiceProvider@@UIObjectWithSite@@VFtmBase@23@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IApplicationActivationManager,IApplicationActivationManagerPriv,IServiceProvider,IObjectWithSite,Microsoft::WRL::FtmBase>::`vftable'
0x18000ab63  mov     [rdi], rax
0x18000ab66  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIApplicationActivationManager@@UIApplicationActivationManagerPriv@@UIServiceProvider@@UIObjectWithSite@@VFtmBase@23@@WRL@Microsoft@@6BIApplicationActivationManagerPriv@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IApplicationActivationManager,IApplicationActivationManagerPriv,IServiceProvider,IObjectWithSite,Microsoft::WRL::FtmBase>::`vftable'{for `IApplicationActivationManagerPriv'}
0x18000ab6d  mov     [rdi+8], rax
0x18000ab71  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIApplicationActivationManager@@UIApplicationActivationManagerPriv@@UIServiceProvider@@UIObjectWithSite@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIServiceProvider@@UIObjectWithSite@@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IApplicationActivationManager,IApplicationActivationManagerPriv,IServiceProvider,IObjectWithSite,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IServiceProvider,IObjectWithSite,Microsoft::WRL::FtmBase>'}
0x18000ab78  mov     [rdi+10h], rax
0x18000ab7c  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIApplicationActivationManager@@UIApplicationActivationManagerPriv@@UIServiceProvider@@UIObjectWithSite@@VFtmBase@23@@WRL@Microsoft@@6BIObjectWithSite@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IApplicationActivationManager,IApplicationActivationManagerPriv,IServiceProvider,IObjectWithSite,Microsoft::WRL::FtmBase>::`vftable'{for `IObjectWithSite'}
0x18000ab83  mov     [rdi+18h], rax
0x18000ab87  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIApplicationActivationManager@@UIApplicationActivationManagerPriv@@UIServiceProvider@@UIObjectWithSite@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IApplicationActivationManager,IApplicationActivationManagerPriv,IServiceProvider,IObjectWithSite,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000ab8e  mov     [rdi+20h], rax
0x18000ab92  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000ab99  test    rcx, rcx
0x18000ab9c  jz      short loc_18000ABAB
0x18000ab9e  mov     rax, [rcx]
0x18000aba1  mov     rax, [rax+8]
0x18000aba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abaa  nop
0x18000abab  lea     rax, ??_7ApplicationActivationManagerProxy@@6B@; const ApplicationActivationManagerProxy::`vftable'
0x18000abb2  mov     [rdi], rax
0x18000abb5  lea     rax, ??_7ApplicationActivationManagerProxy@@6BIApplicationActivationManagerPriv@@@; const ApplicationActivationManagerProxy::`vftable'{for `IApplicationActivationManagerPriv'}
0x18000abbc  mov     [rdi+8], rax
0x18000abc0  lea     rax, ??_7ApplicationActivationManagerProxy@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIServiceProvider@@UIObjectWithSite@@VFtmBase@23@@Details@WRL@Microsoft@@@; const ApplicationActivationManagerProxy::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IServiceProvider,IObjectWithSite,Microsoft::WRL::FtmBase>'}
0x18000abc7  mov     [rdi+10h], rax
0x18000abcb  lea     rax, ??_7ApplicationActivationManagerProxy@@6BIObjectWithSite@@@; const ApplicationActivationManagerProxy::`vftable'{for `IObjectWithSite'}
0x18000abd2  mov     [rdi+18h], rax
0x18000abd6  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIApplicationActivationManager@@UIApplicationActivationManagerPriv@@UIServiceProvider@@UIObjectWithSite@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IApplicationActivationManager,IApplicationActivationManagerPriv,IServiceProvider,IObjectWithSite,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000abdd  mov     [rdi+20h], rax
0x18000abe1  mov     [rdi+48h], r12
0x18000abe5  mov     [rdi+50h], r12
0x18000abe9  mov     [rdi+58h], r12
0x18000abed  mov     [rdi+60h], r12
0x18000abf1  lea     rcx, [rsp+68h+var_48]
0x18000abf6  call    ??$CoCreateInstanceExNoThrow@UIApplicationActivationManager@@UIApplicationActivationManagerPriv@@UIObjectWithSite@@@wil@@YA?A_PAEBU_GUID@@W4tagCLSCTX@@@Z
0x18000abfb  mov     ebx, dword ptr [rsp+68h+var_30]
0x18000abff  test    ebx, ebx
0x18000ac01  jns     short loc_18000AC51
0x18000ac03  mov     rcx, [rsp+68h]; this
0x18000ac08  mov     r9d, ebx; char *
0x18000ac0b  lea     r8, aOnecoreuapShel_16; "onecoreuap\\shell\\twinui\\activation\\"...
0x18000ac12  mov     edx, 36h ; '6'; void *
0x18000ac17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ac1c  lea     rcx, [rsp+68h+var_48]
0x18000ac21  call    ??1?$tuple@JV?$tuple@V?$com_ptr_t@UIApplicationActivationManager@@Uerr_returncode_policy@wil@@@wil@@V?$com_ptr_t@UIApplicationActivationManagerPriv@@Uerr_returncode_policy@wil@@@2@V?$com_ptr_t@UIObjectWithSite@@Uerr_returncode_policy@wil@@@2@@std@@@std@@QEAA@XZ; std::tuple<long,std::tuple<wil::com_ptr_t<IApplicationActivationManager,wil::err_returncode_policy>,wil::com_ptr_t<IApplicationActivationManagerPriv,wil::err_returncode_policy>,wil::com_ptr_t<IObjectWithSite,wil::err_returncode_policy>>>::~tuple<long,std::tuple<wil::com_ptr_t<IApplicationActivationManager,wil::err_returncode_policy>,wil::com_ptr_t<IApplicationActivationManagerPriv,wil::err_returncode_policy>,wil::com_ptr_t<IObjectWithSite,wil::err_returncode_policy>>>(void)
0x18000ac26  mov     edx, [rdi+44h]
0x18000ac29  cmp     edx, 7FFFFFFFh
0x18000ac2f  jz      short loc_18000AC41
0x18000ac31  lea     ecx, [rdx-1]
0x18000ac34  mov     eax, edx
0x18000ac36  lock cmpxchg [rdi+44h], ecx
0x18000ac3b  jnz     loc_18000ADA8
0x18000ac41  lea     eax, [rdx-1]
0x18000ac44  test    eax, eax
0x18000ac46  jz      loc_18000AD73
0x18000ac4c  jmp     loc_18000AD01
0x18000ac51  mov     rbx, [rsp+68h+var_38]
0x18000ac56  mov     [rsp+68h+var_38], r12
0x18000ac5b  mov     rcx, [rdi+50h]
0x18000ac5f  test    rcx, rcx
0x18000ac62  jnz     loc_18000ADC6
0x18000ac68  mov     [rdi+50h], rbx
0x18000ac6c  mov     rbx, [rsp+68h+var_40]
0x18000ac71  mov     [rsp+68h+var_40], r12
0x18000ac76  mov     rcx, [rdi+60h]
0x18000ac7a  test    rcx, rcx
0x18000ac7d  jnz     loc_18000ADD7
0x18000ac83  mov     [rdi+60h], rbx
0x18000ac87  mov     rbx, [rsp+68h+var_48]
0x18000ac8c  mov     [rsp+68h+var_48], r12
0x18000ac91  mov     rcx, [rdi+58h]
0x18000ac95  test    rcx, rcx
0x18000ac98  jnz     loc_18000ADE8
0x18000ac9e  mov     [rdi+58h], rbx
0x18000aca2  lea     rcx, [rsp+68h+var_48]
0x18000aca7  call    ??1?$tuple@JV?$tuple@V?$com_ptr_t@UIApplicationActivationManager@@Uerr_returncode_policy@wil@@@wil@@V?$com_ptr_t@UIApplicationActivationManagerPriv@@Uerr_returncode_policy@wil@@@2@V?$com_ptr_t@UIObjectWithSite@@Uerr_returncode_policy@wil@@@2@@std@@@std@@QEAA@XZ; std::tuple<long,std::tuple<wil::com_ptr_t<IApplicationActivationManager,wil::err_returncode_policy>,wil::com_ptr_t<IApplicationActivationManagerPriv,wil::err_returncode_policy>,wil::com_ptr_t<IObjectWithSite,wil::err_returncode_policy>>>::~tuple<long,std::tuple<wil::com_ptr_t<IApplicationActivationManager,wil::err_returncode_policy>,wil::com_ptr_t<IApplicationActivationManagerPriv,wil::err_returncode_policy>,wil::com_ptr_t<IObjectWithSite,wil::err_returncode_policy>>>(void)
0x18000acac  nop
0x18000acad  mov     rax, [rdi]
0x18000acb0  mov     rcx, rdi
0x18000acb3  mov     rax, [rax+8]
0x18000acb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acbc  nop
0x18000acbd  mov     edx, [rdi+44h]
0x18000acc0  cmp     edx, 7FFFFFFFh
0x18000acc6  jz      short loc_18000ACD4
0x18000acc8  lea     ecx, [rdx-1]
0x18000accb  mov     eax, edx
0x18000accd  lock cmpxchg [rdi+44h], ecx
0x18000acd2  jnz     short loc_18000AD4B
0x18000acd4  lea     eax, [rdx-1]
0x18000acd7  test    eax, eax
0x18000acd9  jz      short loc_18000AD1D
0x18000acdb  mov     rax, [rdi]
0x18000acde  mov     r8, r14
0x18000ace1  mov     rdx, rbp
0x18000ace4  mov     rcx, rdi
0x18000ace7  mov     rax, [rax]
0x18000acea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acef  mov     ebx, eax
0x18000acf1  mov     rcx, [rdi]
0x18000acf4  mov     rax, [rcx+10h]
0x18000acf8  mov     rcx, rdi
0x18000acfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad00  nop
0x18000ad01  mov     eax, ebx
0x18000ad03  mov     rbx, [rsp+68h+arg_0]
0x18000ad08  mov     rbp, [rsp+68h+arg_10]
0x18000ad10  add     rsp, 40h
0x18000ad14  pop     r15
0x18000ad16  pop     r14
0x18000ad18  pop     r12
0x18000ad1a  pop     rdi
0x18000ad1b  pop     rsi
0x18000ad1c  retn
0x18000ad1d  mov     rax, [rdi]
0x18000ad20  mov     edx, 1
0x18000ad25  mov     rcx, rdi
0x18000ad28  mov     rax, [rax+30h]
0x18000ad2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad31  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000ad38  test    rcx, rcx
0x18000ad3b  jz      short loc_18000ACDB
0x18000ad3d  mov     rax, [rcx]
0x18000ad40  mov     rax, [rax+10h]
0x18000ad44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad49  jmp     short loc_18000ACDB
0x18000ad4b  mov     edx, [rdi+44h]
0x18000ad4e  cmp     edx, 7FFFFFFFh
0x18000ad54  jnz     loc_18000ACC8
0x18000ad5a  jmp     loc_18000ACD4
0x18000ad5f  xor     edx, edx
0x18000ad61  mov     ecx, 80040110h
0x18000ad66  call    cs:__imp_RoOriginateError
0x18000ad6c  mov     eax, 80040110h
0x18000ad71  jmp     short loc_18000AD03
0x18000ad73  mov     rax, [rdi]
0x18000ad76  mov     edx, 1
0x18000ad7b  mov     rcx, rdi
0x18000ad7e  mov     rax, [rax+30h]
0x18000ad82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad87  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000ad8e  test    rcx, rcx
0x18000ad91  jz      loc_18000AC4C
0x18000ad97  mov     rdx, [rcx]
0x18000ad9a  mov     rax, [rdx+10h]
0x18000ad9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ada3  jmp     loc_18000AC4C
0x18000ada8  mov     edx, [rdi+44h]
0x18000adab  cmp     edx, 7FFFFFFFh
0x18000adb1  jnz     loc_18000AC31
0x18000adb7  jmp     loc_18000AC41
0x18000adbc  mov     ebx, 8007000Eh
0x18000adc1  jmp     loc_18000AC4C
0x18000adc6  mov     rax, [rcx]
0x18000adc9  mov     rax, [rax+10h]
0x18000adcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000add2  jmp     loc_18000AC68
0x18000add7  mov     rax, [rcx]
0x18000adda  mov     rax, [rax+10h]
0x18000adde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ade3  jmp     loc_18000AC83
0x18000ade8  mov     rax, [rcx]
0x18000adeb  mov     rax, [rax+10h]
0x18000adef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adf4  jmp     loc_18000AC9E
```
