# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<1>,Windows::Internal::Security::SmartScreen::IAppReputationService,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<1>,Windows::Internal::Security::SmartScreen::IAppReputationService,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics,Microsoft::WRL::FtmBase>(void)

- ea: `0x140006020`
- end: `0x140006132`
- name: `??0?$RuntimeClass@U?$RuntimeClassFlags@$00@WRL@Microsoft@@UIAppReputationService@SmartScreen@Security@Internal@Windows@@UIAppReputationServiceStatics@5678@VFtmBase@23@@WRL@Microsoft@@QEAA@XZ`
- size: `274`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140005e80`

## callees

- `0x140006020`
- `0x140025aa0`
- `0x140068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x140006062`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x140006062`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<1>,Windows::Internal::Security::SmartScreen::IAppReputationService,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<1>,Windows::Internal::Security::SmartScreen::IAppReputationService,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics,Microsoft::WRL::FtmBase>(
        _QWORD *a1)
{
  LPUNKNOWN v2; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbp
  __int64 v4; // rcx
  LPUNKNOWN v5; // rcx
  LPUNKNOWN ppunkMarshal; // [rsp+20h] [rbp-28h] BYREF

  a1[3] = &Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::Security::SmartScreen::AppReputationResult>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::Security::SmartScreen::AppReputationResult>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  a1[6] = 0;
  ppunkMarshal = 0;
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v2 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    v4 = a1[6];
    if ( v4 )
    {
      a1[6] = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
    ((void (__fastcall *)(LPUNKNOWN, GUID *, _QWORD *))QueryInterface)(
      v2,
      &GUID_00000003_0000_0000_c000_000000000046,
      a1 + 6);
  }
  v5 = ppunkMarshal;
  if ( ppunkMarshal )
  {
    ppunkMarshal = 0;
    ((void (__fastcall *)(LPUNKNOWN))v5->lpVtbl->Release)(v5);
  }
  a1[8] = 1;
  *a1 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<1>,Windows::Internal::Security::SmartScreen::IAppReputationService,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Internal::Security::SmartScreen::IAppReputationService'};
  a1[1] = &com::application_reputation::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics,Microsoft::WRL::FtmBase>'};
  a1[2] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<1>,Windows::Internal::Security::SmartScreen::IAppReputationService,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics'};
  a1[3] = &com::application_reputation::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  return a1;
}

```

## disassembly

```asm
0x140006020  mov     [rsp+arg_8], rbx
0x140006025  mov     [rsp+arg_10], rbp
0x14000602a  push    rsi
0x14000602b  push    rdi
0x14000602c  push    r14
0x14000602e  sub     rsp, 30h
0x140006032  mov     rax, cs:__security_cookie
0x140006039  xor     rax, rsp
0x14000603c  mov     [rsp+48h+var_20], rax
0x140006041  mov     rdi, rcx
0x140006044  lea     rax, ??_7?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x14000604b  mov     [rcx+18h], rax
0x14000604f  xor     r14d, r14d
0x140006052  mov     [rcx+30h], r14
0x140006056  mov     [rsp+48h+ppunkMarshal], r14
0x14000605b  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x140006060  xor     ecx, ecx; punkOuter
0x140006062  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x140006068  test    eax, eax
0x14000606a  js      short loc_1400060A8
0x14000606c  mov     rbx, [rsp+48h+ppunkMarshal]
0x140006071  mov     rax, [rbx]
0x140006074  mov     rbp, [rax]
0x140006077  mov     rcx, [rdi+30h]
0x14000607b  test    rcx, rcx
0x14000607e  jz      short loc_140006091
0x140006080  mov     [rdi+30h], r14
0x140006084  mov     rdx, [rcx]
0x140006087  mov     rax, [rdx+10h]
0x14000608b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006090  nop
0x140006091  lea     r8, [rdi+30h]
0x140006095  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x14000609c  mov     rcx, rbx
0x14000609f  mov     rax, rbp
0x1400060a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400060a7  nop
0x1400060a8  mov     rcx, [rsp+48h+ppunkMarshal]
0x1400060ad  test    rcx, rcx
0x1400060b0  jz      short loc_1400060C4
0x1400060b2  mov     [rsp+48h+ppunkMarshal], r14
0x1400060b7  mov     rax, [rcx]
0x1400060ba  mov     rax, [rax+10h]
0x1400060be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400060c3  nop
0x1400060c4  mov     qword ptr [rdi+40h], 1
0x1400060cc  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$00@WRL@Microsoft@@UIAppReputationService@SmartScreen@Security@Internal@Windows@@UIAppReputationServiceStatics@5678@VFtmBase@23@@WRL@Microsoft@@6BIAppReputationService@SmartScreen@Security@Internal@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<1>,Windows::Internal::Security::SmartScreen::IAppReputationService,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Internal::Security::SmartScreen::IAppReputationService'}
0x1400060d3  mov     [rdi], rax
0x1400060d6  lea     rax, ??_7application_reputation@com@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@@; const com::application_reputation::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics,Microsoft::WRL::FtmBase>'}
0x1400060dd  mov     [rdi+8], rax
0x1400060e1  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$00@WRL@Microsoft@@UIAppReputationService@SmartScreen@Security@Internal@Windows@@UIAppReputationServiceStatics@5678@VFtmBase@23@@WRL@Microsoft@@6BIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<1>,Windows::Internal::Security::SmartScreen::IAppReputationService,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics'}
0x1400060e8  mov     [rdi+10h], rax
0x1400060ec  lea     rax, ??_7application_reputation@com@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const com::application_reputation::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1400060f3  mov     [rdi+18h], rax
0x1400060f7  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1400060fe  test    rcx, rcx
0x140006101  jz      short loc_14000610F
0x140006103  mov     rax, [rcx]
0x140006106  mov     rax, [rax+8]
0x14000610a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000610f  mov     rax, rdi
0x140006112  mov     rcx, [rsp+48h+var_20]
0x140006117  xor     rcx, rsp; StackCookie
0x14000611a  call    __security_check_cookie
0x14000611f  mov     rbx, [rsp+48h+arg_8]
0x140006124  mov     rbp, [rsp+48h+arg_10]
0x140006129  add     rsp, 30h
0x14000612d  pop     r14
0x14000612f  pop     rdi
0x140006130  pop     rsi
0x140006131  retn
```
