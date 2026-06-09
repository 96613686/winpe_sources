# com::application_reputation_static::application_reputation_static(api_guard,Microsoft::WRL::ComPtr<Windows::Internal::Security::SmartScreen::IAppReputationService>)

- ea: `0x18000a710`
- end: `0x18000a84d`
- name: `??0application_reputation_static@com@@QEAA@Vapi_guard@@V?$ComPtr@UIAppReputationService@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@@Z`
- size: `317`
- prototype: `__int64 __fastcall(__int64, api_guard *, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009ec0`

## callees

- `0x18000871c`
- `0x18000a5c4`
- `0x18000a668`
- `0x18000a710`
- `0x18000a918`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall com::application_reputation_static::application_reputation_static(
        __int64 a1,
        api_guard *a2,
        _QWORD *a3)
{
  _QWORD *v6; // rbx
  _QWORD *v7; // rdi
  __int64 (__fastcall ***v8)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v9)(_QWORD, GUID *, __int64); // rbx

  v6 = (_QWORD *)(a1 + 8);
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(a1 + 8));
  *(_DWORD *)(a1 + 68) = 1;
  *(_QWORD *)a1 = &Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable';
  *v6 = &Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>>'};
  *(_QWORD *)(a1 + 40) = &Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>>'};
  *(_QWORD *)(a1 + 80) = 0;
  *(_DWORD *)(a1 + 88) = 4;
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)a1 = &com::application_reputation_static::`vftable';
  *v6 = &com::application_reputation_static::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>>'};
  *(_QWORD *)(a1 + 40) = &com::application_reputation_static::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>>'};
  std::function<void (void)>::function<void (void)>(a1 + 96, a2);
  std::function<void (void)>::function<void (void)>(a1 + 160, (char *)a2 + 64);
  *(_BYTE *)(a1 + 224) = *((_BYTE *)a2 + 128);
  v7 = (_QWORD *)(a1 + 232);
  *(_QWORD *)(a1 + 232) = 0;
  if ( (_QWORD *)(a1 + 232) != a3 )
  {
    *v7 = *a3;
    *a3 = 0;
  }
  *(_QWORD *)(a1 + 240) = 0;
  v8 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))*v7;
  v9 = **v8;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1 + 240);
  *(_DWORD *)(a1 + 248) = v9(v8, &GUID_343baa78_e34f_466c_9ffa_81af5ce4cd34, a1 + 240);
  api_guard::~api_guard(a2);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a3);
  return a1;
}

```

## disassembly

```asm
0x18000a710  mov     [rsp+arg_18], rbx
0x18000a715  push    rbp
0x18000a716  push    rsi
0x18000a717  push    rdi
0x18000a718  push    r14
0x18000a71a  push    r15
0x18000a71c  sub     rsp, 20h
0x18000a720  mov     r15, r8
0x18000a723  mov     rbp, rdx
0x18000a726  mov     r14, rcx
0x18000a729  lea     rbx, [rcx+8]
0x18000a72d  mov     rcx, rbx; this
0x18000a730  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18000a735  mov     dword ptr [r14+44h], 1
0x18000a73d  lea     rax, ??_7?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'
0x18000a744  mov     [r14], rax
0x18000a747  lea     rax, ??_7?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@Details@23@@Details@12@@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>>'}
0x18000a74e  mov     [rbx], rax
0x18000a751  lea     rax, ??_7?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@234@@Details@12@@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>>'}
0x18000a758  mov     [r14+28h], rax
0x18000a75c  mov     qword ptr [r14+50h], 0
0x18000a764  mov     dword ptr [r14+58h], 4
0x18000a76c  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000a773  test    rcx, rcx
0x18000a776  jz      short loc_18000A785
0x18000a778  mov     rax, [rcx]
0x18000a77b  mov     rax, [rax+8]
0x18000a77f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a784  nop
0x18000a785  lea     rax, ??_7application_reputation_static@com@@6B@; const com::application_reputation_static::`vftable'
0x18000a78c  mov     [r14], rax
0x18000a78f  lea     rax, ??_7application_reputation_static@com@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@Details@23@@Details@WRL@Microsoft@@@; const com::application_reputation_static::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>>'}
0x18000a796  mov     [rbx], rax
0x18000a799  lea     rax, ??_7application_reputation_static@com@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@234@@Details@WRL@Microsoft@@@; const com::application_reputation_static::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>>'}
0x18000a7a0  mov     [r14+28h], rax
0x18000a7a4  mov     rdx, rbp
0x18000a7a7  lea     rcx, [r14+60h]
0x18000a7ab  call    ??0?$function@$$A6AXXZ@std@@QEAA@$$QEAV01@@Z; std::function<void (void)>::function<void (void)>(std::function<void (void)> &&)
0x18000a7b0  lea     rdx, [rbp+40h]
0x18000a7b4  lea     rcx, [r14+0A0h]
0x18000a7bb  call    ??0?$function@$$A6AXXZ@std@@QEAA@$$QEAV01@@Z; std::function<void (void)>::function<void (void)>(std::function<void (void)> &&)
0x18000a7c0  mov     al, [rbp+80h]
0x18000a7c6  mov     [r14+0E0h], al
0x18000a7cd  lea     rdi, [r14+0E8h]
0x18000a7d4  mov     qword ptr [rdi], 0
0x18000a7db  cmp     rdi, r15
0x18000a7de  jz      short loc_18000A7ED
0x18000a7e0  mov     rax, [r15]
0x18000a7e3  mov     [rdi], rax
0x18000a7e6  mov     qword ptr [r15], 0
0x18000a7ed  lea     rsi, [r14+0F0h]
0x18000a7f4  mov     qword ptr [rsi], 0
0x18000a7fb  mov     rdi, [rdi]
0x18000a7fe  mov     rax, [rdi]
0x18000a801  mov     rbx, [rax]
0x18000a804  mov     rcx, rsi
0x18000a807  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a80c  mov     r8, rsi
0x18000a80f  lea     rdx, _GUID_343baa78_e34f_466c_9ffa_81af5ce4cd34
0x18000a816  mov     rcx, rdi
0x18000a819  mov     rax, rbx
0x18000a81c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a821  nop
0x18000a822  mov     [r14+0F8h], eax
0x18000a829  mov     rcx, rbp; this
0x18000a82c  call    ??1api_guard@@QEAA@XZ; api_guard::~api_guard(void)
0x18000a831  mov     rcx, r15
0x18000a834  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a839  mov     rax, r14
0x18000a83c  mov     rbx, [rsp+48h+arg_18]
0x18000a841  add     rsp, 20h
0x18000a845  pop     r15
0x18000a847  pop     r14
0x18000a849  pop     rdi
0x18000a84a  pop     rsi
0x18000a84b  pop     rbp
0x18000a84c  retn
```
