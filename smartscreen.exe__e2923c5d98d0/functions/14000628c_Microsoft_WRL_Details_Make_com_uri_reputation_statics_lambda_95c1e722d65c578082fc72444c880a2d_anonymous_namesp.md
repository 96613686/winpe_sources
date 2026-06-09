# Microsoft::WRL::Details::Make_com::uri_reputation_statics__lambda_95c1e722d65c578082fc72444c880a2d___anonymous_namespace_::waiting_api_guard_&_

- ea: `0x14000628c`
- end: `0x14000656f`
- name: `Microsoft::WRL::Details::Make_com::uri_reputation_statics__lambda_95c1e722d65c578082fc72444c880a2d___anonymous_namespace_::waiting_api_guard_&_`
- size: `739`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140006cc4`

## callees

- `0x140002e70`
- `0x140006220`
- `0x14000628c`
- `0x140006880`
- `0x140025fb4`
- `0x140025fc0`
- `0x140068010`

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
  v6 = (char *)operator new(0x128u, (const struct std::nothrow_t *)&std::nothrow);
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
    v12[0] = off_140069390;
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
    operator delete(v7);
  return a1;
}

```

## disassembly

```asm
0x14000628c  mov     [rsp-8+arg_8], rbx
0x140006291  mov     [rsp-8+arg_0], rcx
0x140006296  push    rbp
0x140006297  push    rsi
0x140006298  push    rdi
0x140006299  push    r14
0x14000629b  push    r15
0x14000629d  lea     rbp, [rsp-10h]
0x1400062a2  sub     rsp, 110h
0x1400062a9  mov     rdi, r8
0x1400062ac  mov     r14, rdx
0x1400062af  mov     rsi, rcx
0x1400062b2  mov     [rsp+130h+var_110], 0
0x1400062ba  mov     qword ptr [rcx], 0
0x1400062c1  mov     [rsp+130h+var_110], 1
0x1400062c9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400062d0  mov     ecx, 128h; unsigned __int64
0x1400062d5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400062da  mov     rbx, rax
0x1400062dd  mov     [rbp+30h+arg_18], rax
0x1400062e1  mov     [rbp+30h+var_38], rax
0x1400062e5  test    rax, rax
0x1400062e8  jz      loc_140006502
0x1400062ee  mov     [rbp+30h+var_30], rax
0x1400062f2  lea     rax, [rsp+130h+var_C0]
0x1400062f7  mov     [rbp+30h+var_28], rax
0x1400062fb  lea     rax, [rsp+130h+var_C0]
0x140006300  mov     [rsp+130h+var_108], rax
0x140006305  mov     [rbp+30h+var_88], 0
0x14000630d  mov     rcx, [rdi+38h]
0x140006311  test    rcx, rcx
0x140006314  jz      short loc_14000632A
0x140006316  mov     rax, [rcx]
0x140006319  lea     rdx, [rsp+130h+var_C0]
0x14000631e  mov     rax, [rax]
0x140006321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006326  mov     [rbp+30h+var_88], rax
0x14000632a  lea     rax, [rbp+30h+var_80]
0x14000632e  mov     [rsp+130h+var_108], rax
0x140006333  mov     [rbp+30h+var_48], 0
0x14000633b  mov     rcx, [rdi+78h]
0x14000633f  test    rcx, rcx
0x140006342  jz      short loc_140006357
0x140006344  mov     rax, [rcx]
0x140006347  lea     rdx, [rbp+30h+var_80]
0x14000634b  mov     rax, [rax]
0x14000634e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006353  mov     [rbp+30h+var_48], rax
0x140006357  mov     al, [rdi+80h]
0x14000635d  mov     [rbp+30h+var_40], al
0x140006360  lea     rax, off_140069390
0x140006367  mov     [rsp+130h+var_100], rax
0x14000636c  mov     rax, [r14]
0x14000636f  mov     [rsp+130h+var_F8], rax
0x140006374  lea     rax, [rsp+130h+var_100]
0x140006379  mov     [rsp+130h+var_C8], rax
0x14000637e  lea     r15, [rbx+8]
0x140006382  mov     rcx, r15; this
0x140006385  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x14000638a  mov     dword ptr [rbx+44h], 1
0x140006391  lea     rax, ??_7?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIUriReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'
0x140006398  mov     [rbx], rax
0x14000639b  lea     rax, ??_7?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIUriReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIUriReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@Details@23@@Details@12@@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>>'}
0x1400063a2  mov     [r15], rax
0x1400063a5  lea     rax, ??_7?$com_factory@UIUriReputationServiceStatics@SmartScreen@Security@Internal@Windows@@UIUriReputationService@2345@@shared@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIUriReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIUriReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@234@@Details@WRL@Microsoft@@@; const shared::com_factory<Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics,Windows::Internal::Security::SmartScreen::IUriReputationService>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>>'}
0x1400063ac  mov     [rbx+28h], rax
0x1400063b0  mov     qword ptr [rbx+50h], 0
0x1400063b8  mov     dword ptr [rbx+58h], 4
0x1400063bf  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1400063c6  test    rcx, rcx
0x1400063c9  jz      short loc_1400063D8
0x1400063cb  mov     rax, [rcx]
0x1400063ce  mov     rax, [rax+8]
0x1400063d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400063d7  nop
0x1400063d8  lea     rax, ??_7?$com_factory@UIUriReputationServiceStatics@SmartScreen@Security@Internal@Windows@@UIUriReputationService@2345@@shared@@6B@; const shared::com_factory<Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics,Windows::Internal::Security::SmartScreen::IUriReputationService>::`vftable'
0x1400063df  mov     [rbx], rax
0x1400063e2  lea     rax, ??_7?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIUriReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIUriReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@Details@23@@Details@12@@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>>'}
0x1400063e9  mov     [r15], rax
0x1400063ec  lea     rax, ??_7?$com_factory@UIUriReputationServiceStatics@SmartScreen@Security@Internal@Windows@@UIUriReputationService@2345@@shared@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIUriReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIUriReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@234@@Details@WRL@Microsoft@@@; const shared::com_factory<Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics,Windows::Internal::Security::SmartScreen::IUriReputationService>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>>'}
0x1400063f3  mov     [rbx+28h], rax
0x1400063f7  mov     qword ptr [rbx+98h], 0
0x140006402  mov     rcx, [rsp+130h+var_C8]
0x140006407  test    rcx, rcx
0x14000640a  jz      short loc_14000643B
0x14000640c  lea     rax, [rsp+130h+var_100]
0x140006411  cmp     rcx, rax
0x140006414  jnz     loc_14000654B
0x14000641a  mov     rax, [rcx]
0x14000641d  lea     rdx, [rbx+60h]
0x140006421  mov     rax, [rax+8]
0x140006425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000642a  mov     [rbx+98h], rax
0x140006431  lea     rcx, [rsp+130h+var_100]
0x140006436  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x14000643b  lea     rdi, [rbx+0A0h]
0x140006442  mov     qword ptr [rdi+38h], 0
0x14000644a  mov     rcx, [rbp+30h+var_88]
0x14000644e  test    rcx, rcx
0x140006451  jz      short loc_14000647E
0x140006453  lea     rax, [rsp+130h+var_C0]
0x140006458  cmp     rcx, rax
0x14000645b  jnz     loc_140006529
0x140006461  mov     rax, [rcx]
0x140006464  mov     rdx, rdi
0x140006467  mov     rax, [rax+8]
0x14000646b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006470  mov     [rdi+38h], rax
0x140006474  lea     rcx, [rsp+130h+var_C0]
0x140006479  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x14000647e  mov     qword ptr [rdi+78h], 0
0x140006486  mov     rcx, [rbp+30h+var_48]
0x14000648a  test    rcx, rcx
0x14000648d  jz      short loc_1400064B9
0x14000648f  lea     rax, [rbp+30h+var_80]
0x140006493  cmp     rcx, rax
0x140006496  jnz     loc_14000653A
0x14000649c  mov     rax, [rcx]
0x14000649f  lea     rdx, [rdi+40h]
0x1400064a3  mov     rax, [rax+8]
0x1400064a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400064ac  mov     [rdi+78h], rax
0x1400064b0  lea     rcx, [rbp+30h+var_80]
0x1400064b4  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x1400064b9  mov     al, [rbp+30h+var_40]
0x1400064bc  mov     [rdi+80h], al
0x1400064c2  lea     rcx, [rsp+130h+var_100]
0x1400064c7  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x1400064cc  lea     rcx, [rsp+130h+var_C0]; this
0x1400064d1  call    ??1api_guard@@QEAA@XZ; api_guard::~api_guard(void)
0x1400064d6  lea     rax, ??_7uri_reputation_statics@com@@6B@; const com::uri_reputation_statics::`vftable'
0x1400064dd  mov     [rbx], rax
0x1400064e0  lea     rax, ??_7uri_reputation_statics@com@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIUriReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@Details@23@@Details@WRL@Microsoft@@@; const com::uri_reputation_statics::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>>'}
0x1400064e7  mov     [r15], rax
0x1400064ea  lea     rax, ??_7uri_reputation_statics@com@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIUriReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIUriReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@234@@Details@WRL@Microsoft@@@; const com::uri_reputation_statics::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics>>'}
0x1400064f1  mov     [rbx+28h], rax
0x1400064f5  mov     rcx, [rsi]
0x1400064f8  test    rcx, rcx
0x1400064fb  jnz     short loc_140006560
0x1400064fd  mov     [rsi], rbx
0x140006500  xor     ebx, ebx
0x140006502  test    rbx, rbx
0x140006505  jz      short loc_14000650F
0x140006507  mov     rcx, rbx; Block
0x14000650a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000650f  mov     rax, rsi
0x140006512  mov     rbx, [rsp+130h+arg_8]
0x14000651a  add     rsp, 110h
0x140006521  pop     r15
0x140006523  pop     r14
0x140006525  pop     rdi
0x140006526  pop     rsi
0x140006527  pop     rbp
0x140006528  retn
0x140006529  mov     [rdi+38h], rcx
0x14000652d  mov     [rbp+30h+var_88], 0
0x140006535  jmp     loc_14000647E
0x14000653a  mov     [rdi+78h], rcx
0x14000653e  mov     [rbp+30h+var_48], 0
0x140006546  jmp     loc_1400064B9
0x14000654b  mov     [rbx+98h], rcx
0x140006552  mov     [rsp+130h+var_C8], 0
0x14000655b  jmp     loc_14000643B
0x140006560  mov     rax, [rcx]
0x140006563  mov     rax, [rax+10h]
0x140006567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000656c  jmp     short loc_1400064FD
```
