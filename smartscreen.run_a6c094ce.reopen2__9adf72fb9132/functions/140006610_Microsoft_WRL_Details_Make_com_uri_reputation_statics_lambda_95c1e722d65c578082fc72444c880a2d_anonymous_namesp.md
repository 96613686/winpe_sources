# Microsoft::WRL::Details::Make_com::uri_reputation_statics__lambda_95c1e722d65c578082fc72444c880a2d___anonymous_namespace_::waiting_api_guard_&_

- ea: `0x140006610`
- end: `0x1400068f9`
- name: `Microsoft::WRL::Details::Make_com::uri_reputation_statics__lambda_95c1e722d65c578082fc72444c880a2d___anonymous_namespace_::waiting_api_guard_&_`
- size: `745`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140007068`

## callees

- `0x140002f70`
- `0x1400065a0`
- `0x140006610`
- `0x140006c10`
- `0x140027084`
- `0x140027134`
- `0x14006a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall Microsoft::WRL::Details::Make_com::uri_reputation_statics__lambda_95c1e722d65c578082fc72444c880a2d___anonymous_namespace_::waiting_api_guard___(
        _QWORD *a1,
        _QWORD *a2,
        __int64 a3)
{
  char *v6; // rax
  char *v7; // rbx
  __int64 (__fastcall ***v8)(_QWORD, _BYTE *); // rcx
  __int64 (__fastcall ***v9)(_QWORD, _BYTE *); // rcx
  _QWORD *v10; // r15
  _QWORD v12[7]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v13; // [rsp+68h] [rbp-98h]
  _BYTE v14[56]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE *v15; // [rsp+A8h] [rbp-58h]
  _BYTE v16[56]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE *v17; // [rsp+E8h] [rbp-18h]
  char v18; // [rsp+F0h] [rbp-10h]
  char *v19; // [rsp+F8h] [rbp-8h]
  char *v20; // [rsp+100h] [rbp+0h]
  _BYTE *v21; // [rsp+108h] [rbp+8h]

  *a1 = 0;
  v6 = (char *)operator new(0x128u, (const struct std::nothrow_t *)std::nothrow);
  v7 = v6;
  v19 = v6;
  if ( v6 )
  {
    v20 = v6;
    v21 = v14;
    v15 = 0;
    v8 = *(__int64 (__fastcall ****)(_QWORD, _BYTE *))(a3 + 56);
    if ( v8 )
      v15 = (_BYTE *)(**v8)(v8, v14);
    v17 = 0;
    v9 = *(__int64 (__fastcall ****)(_QWORD, _BYTE *))(a3 + 120);
    if ( v9 )
      v17 = (_BYTE *)(**v9)(v9, v16);
    v18 = *(_BYTE *)(a3 + 128);
    v12[0] = off_14006B390;
    v12[1] = *a2;
    v13 = v12;
    v10 = v7 + 8;
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v7 + 8));
    *((_DWORD *)v7 + 17) = 1;
    *(_QWORD *)v7 = &Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable';
    *((_QWORD *)v7 + 1) = &Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>>'};
    *((_QWORD *)v7 + 5) = &shared::com_factory<Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics,Windows::Internal::Security::SmartScreen::IUriReputationService>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>>'};
    *((_QWORD *)v7 + 10) = 0;
    *((_DWORD *)v7 + 22) = 4;
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v7 = &shared::com_factory<Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics,Windows::Internal::Security::SmartScreen::IUriReputationService>::`vftable';
    *v10 = &Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>>'};
    *((_QWORD *)v7 + 5) = &shared::com_factory<Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics,Windows::Internal::Security::SmartScreen::IUriReputationService>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>>'};
    *((_QWORD *)v7 + 19) = 0;
    if ( v13 )
    {
      if ( v13 == v12 )
      {
        *((_QWORD *)v7 + 19) = (*(__int64 (__fastcall **)(_QWORD *, char *))(*v13 + 8LL))(v13, v7 + 96);
        std::_Func_class<void,>::~_Func_class<void,>(v12);
      }
      else
      {
        *((_QWORD *)v7 + 19) = v13;
        v13 = 0;
      }
    }
    *((_QWORD *)v7 + 27) = 0;
    if ( v15 )
    {
      if ( v15 == v14 )
      {
        *((_QWORD *)v7 + 27) = (*(__int64 (__fastcall **)(_BYTE *, char *))(*(_QWORD *)v15 + 8LL))(v15, v7 + 160);
        std::_Func_class<void,>::~_Func_class<void,>(v14);
      }
      else
      {
        *((_QWORD *)v7 + 27) = v15;
        v15 = 0;
      }
    }
    *((_QWORD *)v7 + 35) = 0;
    if ( v17 )
    {
      if ( v17 == v16 )
      {
        *((_QWORD *)v7 + 35) = (*(__int64 (__fastcall **)(_BYTE *, char *))(*(_QWORD *)v17 + 8LL))(v17, v7 + 224);
        std::_Func_class<void,>::~_Func_class<void,>(v16);
      }
      else
      {
        *((_QWORD *)v7 + 35) = v17;
        v17 = 0;
      }
    }
    v7[288] = v18;
    std::_Func_class<void,>::~_Func_class<void,>(v12);
    api_guard::~api_guard((api_guard *)v14);
    *(_QWORD *)v7 = &com::uri_reputation_statics::`vftable';
    *v10 = &com::uri_reputation_statics::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>>'};
    *((_QWORD *)v7 + 5) = &com::uri_reputation_statics::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>>'};
    if ( *a1 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
    *a1 = v7;
    v7 = 0;
  }
  if ( v7 )
    operator delete(v7, (const struct std::nothrow_t *)1);
  return a1;
}

```

## disassembly

```asm
0x140006610  mov     [rsp-8+arg_8], rbx
0x140006615  mov     [rsp-8+arg_0], rcx
0x14000661a  push    rbp
0x14000661b  push    rsi
0x14000661c  push    rdi
0x14000661d  push    r14
0x14000661f  push    r15
0x140006621  lea     rbp, [rsp-10h]
0x140006626  sub     rsp, 110h
0x14000662d  mov     rdi, r8
0x140006630  mov     r14, rdx
0x140006633  mov     rsi, rcx
0x140006636  mov     [rsp+130h+var_110], 0
0x14000663e  mov     qword ptr [rcx], 0
0x140006645  mov     [rsp+130h+var_110], 1
0x14000664d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140006654  mov     ecx, 128h; unsigned __int64
0x140006659  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000665e  mov     rbx, rax
0x140006661  mov     [rbp+30h+arg_18], rax
0x140006665  mov     [rbp+30h+var_38], rax
0x140006669  test    rax, rax
0x14000666c  jz      loc_140006886
0x140006672  mov     [rbp+30h+var_30], rax
0x140006676  lea     rax, [rsp+130h+var_C0]
0x14000667b  mov     [rbp+30h+var_28], rax
0x14000667f  lea     rax, [rsp+130h+var_C0]
0x140006684  mov     [rsp+130h+var_108], rax
0x140006689  mov     [rbp+30h+var_88], 0
0x140006691  mov     rcx, [rdi+38h]
0x140006695  test    rcx, rcx
0x140006698  jz      short loc_1400066AE
0x14000669a  mov     rax, [rcx]
0x14000669d  lea     rdx, [rsp+130h+var_C0]
0x1400066a2  mov     rax, [rax]
0x1400066a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400066aa  mov     [rbp+30h+var_88], rax
0x1400066ae  lea     rax, [rbp+30h+var_80]
0x1400066b2  mov     [rsp+130h+var_108], rax
0x1400066b7  mov     [rbp+30h+var_48], 0
0x1400066bf  mov     rcx, [rdi+78h]
0x1400066c3  test    rcx, rcx
0x1400066c6  jz      short loc_1400066DB
0x1400066c8  mov     rax, [rcx]
0x1400066cb  lea     rdx, [rbp+30h+var_80]
0x1400066cf  mov     rax, [rax]
0x1400066d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400066d7  mov     [rbp+30h+var_48], rax
0x1400066db  mov     al, [rdi+80h]
0x1400066e1  mov     [rbp+30h+var_40], al
0x1400066e4  lea     rax, off_14006B390
0x1400066eb  mov     [rsp+130h+var_100], rax
0x1400066f0  mov     rax, [r14]
0x1400066f3  mov     [rsp+130h+var_F8], rax
0x1400066f8  lea     rax, [rsp+130h+var_100]
0x1400066fd  mov     [rsp+130h+var_C8], rax
0x140006702  lea     r15, [rbx+8]
0x140006706  mov     rcx, r15; this
0x140006709  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x14000670e  mov     dword ptr [rbx+44h], 1
0x140006715  lea     rax, ??_7?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIUriReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'
0x14000671c  mov     [rbx], rax
0x14000671f  lea     rax, ??_7?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIUriReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIUriReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@Details@23@@Details@12@@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>>'}
0x140006726  mov     [r15], rax
0x140006729  lea     rax, ??_7?$com_factory@UIUriReputationServiceStatics@SmartScreen@Security@Internal@Windows@@UIUriReputationService@2345@@shared@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIUriReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIUriReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@234@@Details@WRL@Microsoft@@@; const shared::com_factory<Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics,Windows::Internal::Security::SmartScreen::IUriReputationService>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>>'}
0x140006730  mov     [rbx+28h], rax
0x140006734  mov     qword ptr [rbx+50h], 0
0x14000673c  mov     dword ptr [rbx+58h], 4
0x140006743  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14000674a  test    rcx, rcx
0x14000674d  jz      short loc_14000675C
0x14000674f  mov     rax, [rcx]
0x140006752  mov     rax, [rax+8]
0x140006756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000675b  nop
0x14000675c  lea     rax, ??_7?$com_factory@UIUriReputationServiceStatics@SmartScreen@Security@Internal@Windows@@UIUriReputationService@2345@@shared@@6B@; const shared::com_factory<Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics,Windows::Internal::Security::SmartScreen::IUriReputationService>::`vftable'
0x140006763  mov     [rbx], rax
0x140006766  lea     rax, ??_7?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIUriReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIUriReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@Details@23@@Details@12@@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>>'}
0x14000676d  mov     [r15], rax
0x140006770  lea     rax, ??_7?$com_factory@UIUriReputationServiceStatics@SmartScreen@Security@Internal@Windows@@UIUriReputationService@2345@@shared@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIUriReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIUriReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@234@@Details@WRL@Microsoft@@@; const shared::com_factory<Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics,Windows::Internal::Security::SmartScreen::IUriReputationService>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>>'}
0x140006777  mov     [rbx+28h], rax
0x14000677b  mov     qword ptr [rbx+98h], 0
0x140006786  mov     rcx, [rsp+130h+var_C8]
0x14000678b  test    rcx, rcx
0x14000678e  jz      short loc_1400067BF
0x140006790  lea     rax, [rsp+130h+var_100]
0x140006795  cmp     rcx, rax
0x140006798  jnz     loc_1400068D5
0x14000679e  mov     rax, [rcx]
0x1400067a1  lea     rdx, [rbx+60h]
0x1400067a5  mov     rax, [rax+8]
0x1400067a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400067ae  mov     [rbx+98h], rax
0x1400067b5  lea     rcx, [rsp+130h+var_100]
0x1400067ba  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x1400067bf  lea     rdi, [rbx+0A0h]
0x1400067c6  mov     qword ptr [rdi+38h], 0
0x1400067ce  mov     rcx, [rbp+30h+var_88]
0x1400067d2  test    rcx, rcx
0x1400067d5  jz      short loc_140006802
0x1400067d7  lea     rax, [rsp+130h+var_C0]
0x1400067dc  cmp     rcx, rax
0x1400067df  jnz     loc_1400068B3
0x1400067e5  mov     rax, [rcx]
0x1400067e8  mov     rdx, rdi
0x1400067eb  mov     rax, [rax+8]
0x1400067ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400067f4  mov     [rdi+38h], rax
0x1400067f8  lea     rcx, [rsp+130h+var_C0]
0x1400067fd  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x140006802  mov     qword ptr [rdi+78h], 0
0x14000680a  mov     rcx, [rbp+30h+var_48]
0x14000680e  test    rcx, rcx
0x140006811  jz      short loc_14000683D
0x140006813  lea     rax, [rbp+30h+var_80]
0x140006817  cmp     rcx, rax
0x14000681a  jnz     loc_1400068C4
0x140006820  mov     rax, [rcx]
0x140006823  lea     rdx, [rdi+40h]
0x140006827  mov     rax, [rax+8]
0x14000682b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006830  mov     [rdi+78h], rax
0x140006834  lea     rcx, [rbp+30h+var_80]
0x140006838  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x14000683d  mov     al, [rbp+30h+var_40]
0x140006840  mov     [rdi+80h], al
0x140006846  lea     rcx, [rsp+130h+var_100]
0x14000684b  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x140006850  lea     rcx, [rsp+130h+var_C0]; this
0x140006855  call    ??1api_guard@@QEAA@XZ; api_guard::~api_guard(void)
0x14000685a  lea     rax, ??_7uri_reputation_statics@com@@6B@; const com::uri_reputation_statics::`vftable'
0x140006861  mov     [rbx], rax
0x140006864  lea     rax, ??_7uri_reputation_statics@com@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIUriReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@Details@23@@Details@WRL@Microsoft@@@; const com::uri_reputation_statics::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>>'}
0x14000686b  mov     [r15], rax
0x14000686e  lea     rax, ??_7uri_reputation_statics@com@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIUriReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIUriReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@234@@Details@WRL@Microsoft@@@; const com::uri_reputation_statics::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>>'}
0x140006875  mov     [rbx+28h], rax
0x140006879  mov     rcx, [rsi]
0x14000687c  test    rcx, rcx
0x14000687f  jnz     short loc_1400068EA
0x140006881  mov     [rsi], rbx
0x140006884  xor     ebx, ebx
0x140006886  test    rbx, rbx
0x140006889  jz      short loc_140006898
0x14000688b  mov     edx, 1; struct std::nothrow_t *
0x140006890  mov     rcx, rbx; void *
0x140006893  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140006898  mov     rax, rsi
0x14000689b  mov     rbx, [rsp+130h+arg_8]
0x1400068a3  add     rsp, 110h
0x1400068aa  pop     r15
0x1400068ac  pop     r14
0x1400068ae  pop     rdi
0x1400068af  pop     rsi
0x1400068b0  pop     rbp
0x1400068b1  retn
0x1400068b3  mov     [rdi+38h], rcx
0x1400068b7  mov     [rbp+30h+var_88], 0
0x1400068bf  jmp     loc_140006802
0x1400068c4  mov     [rdi+78h], rcx
0x1400068c8  mov     [rbp+30h+var_48], 0
0x1400068d0  jmp     loc_14000683D
0x1400068d5  mov     [rbx+98h], rcx
0x1400068dc  mov     [rsp+130h+var_C8], 0
0x1400068e5  jmp     loc_1400067BF
0x1400068ea  mov     rax, [rcx]
0x1400068ed  mov     rax, [rax+10h]
0x1400068f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400068f6  jmp     short loc_140006881
```
