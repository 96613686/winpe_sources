# com::application_reputation_static::application_reputation_static(api_guard,Microsoft::WRL::ComPtr<Windows::Internal::Security::SmartScreen::IAppReputationService>)

- ea: `0x18000a98c`
- end: `0x18000aaca`
- name: `??0application_reputation_static@com@@QEAA@Vapi_guard@@V?$ComPtr@UIAppReputationService@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@@Z`
- size: `318`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a100`

## callees

- `0x180008828`
- `0x18000a838`
- `0x18000a8dc`
- `0x18000a98c`
- `0x18000aba0`
- `0x18000e010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall com::application_reputation_static::application_reputation_static(
        __int64 a1,
        api_guard *a2,
        __int64 *a3)
{
  _QWORD *v6; // rbx
  __int64 *v7; // rdi
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
  v7 = (__int64 *)(a1 + 232);
  *(_QWORD *)(a1 + 232) = 0;
  if ( (__int64 *)(a1 + 232) != a3 )
  {
    *v7 = *a3;
    *a3 = 0;
  }
  *(_QWORD *)(a1 + 240) = 0;
  v8 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))*v7;
  v9 = **v8;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)(a1 + 240));
  *(_DWORD *)(a1 + 248) = v9(v8, &GUID_343baa78_e34f_466c_9ffa_81af5ce4cd34, a1 + 240);
  api_guard::~api_guard(a2);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a3);
  return a1;
}

```

## disassembly

```asm
0x18000a98c  mov     [rsp+arg_18], rbx
0x18000a991  push    rbp
0x18000a992  push    rsi
0x18000a993  push    rdi
0x18000a994  push    r14
0x18000a996  push    r15
0x18000a998  sub     rsp, 20h
0x18000a99c  mov     r15, r8
0x18000a99f  mov     rbp, rdx
0x18000a9a2  mov     r14, rcx
0x18000a9a5  lea     rbx, [rcx+8]
0x18000a9a9  mov     rcx, rbx; this
0x18000a9ac  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18000a9b1  mov     dword ptr [r14+44h], 1
0x18000a9b9  lea     rax, ??_7?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'
0x18000a9c0  mov     [r14], rax
0x18000a9c3  lea     rax, ??_7?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@Details@23@@Details@12@@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>>'}
0x18000a9ca  mov     [rbx], rax
0x18000a9cd  lea     rax, ??_7?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@234@@Details@12@@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>>'}
0x18000a9d4  mov     [r14+28h], rax
0x18000a9d8  mov     qword ptr [r14+50h], 0
0x18000a9e0  mov     dword ptr [r14+58h], 4
0x18000a9e8  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000a9ef  test    rcx, rcx
0x18000a9f2  jz      short loc_18000AA01
0x18000a9f4  mov     rax, [rcx]
0x18000a9f7  mov     rax, [rax+8]
0x18000a9fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa00  nop
0x18000aa01  lea     rax, ??_7application_reputation_static@com@@6B@; const com::application_reputation_static::`vftable'
0x18000aa08  mov     [r14], rax
0x18000aa0b  lea     rax, ??_7application_reputation_static@com@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@Details@23@@Details@WRL@Microsoft@@@; const com::application_reputation_static::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>>'}
0x18000aa12  mov     [rbx], rax
0x18000aa15  lea     rax, ??_7application_reputation_static@com@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@234@@Details@WRL@Microsoft@@@; const com::application_reputation_static::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>>'}
0x18000aa1c  mov     [r14+28h], rax
0x18000aa20  mov     rdx, rbp
0x18000aa23  lea     rcx, [r14+60h]
0x18000aa27  call    ??0?$function@$$A6AXXZ@std@@QEAA@$$QEAV01@@Z; std::function<void (void)>::function<void (void)>(std::function<void (void)> &&)
0x18000aa2c  lea     rdx, [rbp+40h]
0x18000aa30  lea     rcx, [r14+0A0h]
0x18000aa37  call    ??0?$function@$$A6AXXZ@std@@QEAA@$$QEAV01@@Z; std::function<void (void)>::function<void (void)>(std::function<void (void)> &&)
0x18000aa3c  mov     al, [rbp+80h]
0x18000aa42  mov     [r14+0E0h], al
0x18000aa49  lea     rdi, [r14+0E8h]
0x18000aa50  mov     qword ptr [rdi], 0
0x18000aa57  cmp     rdi, r15
0x18000aa5a  jz      short loc_18000AA69
0x18000aa5c  mov     rax, [r15]
0x18000aa5f  mov     [rdi], rax
0x18000aa62  mov     qword ptr [r15], 0
0x18000aa69  lea     rsi, [r14+0F0h]
0x18000aa70  mov     qword ptr [rsi], 0
0x18000aa77  mov     rdi, [rdi]
0x18000aa7a  mov     rax, [rdi]
0x18000aa7d  mov     rbx, [rax]
0x18000aa80  mov     rcx, rsi
0x18000aa83  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000aa88  mov     r8, rsi
0x18000aa8b  lea     rdx, _GUID_343baa78_e34f_466c_9ffa_81af5ce4cd34
0x18000aa92  mov     rcx, rdi
0x18000aa95  mov     rax, rbx
0x18000aa98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa9d  nop
0x18000aa9e  mov     [r14+0F8h], eax
0x18000aaa5  mov     rcx, rbp; this
0x18000aaa8  call    ??1api_guard@@QEAA@XZ; api_guard::~api_guard(void)
0x18000aaad  mov     rcx, r15
0x18000aab0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000aab5  mov     rax, r14
0x18000aab8  mov     rbx, [rsp+48h+arg_18]
0x18000aabd  add     rsp, 20h
0x18000aac1  pop     r15
0x18000aac3  pop     r14
0x18000aac5  pop     rdi
0x18000aac6  pop     rsi
0x18000aac7  pop     rbp
0x18000aac8  retn
```
