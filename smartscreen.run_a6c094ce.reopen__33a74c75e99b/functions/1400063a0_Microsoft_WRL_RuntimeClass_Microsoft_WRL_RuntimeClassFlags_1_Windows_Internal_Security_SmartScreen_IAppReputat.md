# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<1>,Windows::Internal::Security::SmartScreen::IAppReputationService,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<1>,Windows::Internal::Security::SmartScreen::IAppReputationService,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics,Microsoft::WRL::FtmBase>(void)

- ea: `0x1400063a0`
- end: `0x1400064b9`
- name: `??0?$RuntimeClass@U?$RuntimeClassFlags@$00@WRL@Microsoft@@UIAppReputationService@SmartScreen@Security@Internal@Windows@@UIAppReputationServiceStatics@5678@VFtmBase@23@@WRL@Microsoft@@QEAA@XZ`
- size: `281`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140006200`

## callees

- `0x1400063a0`
- `0x140026c20`
- `0x14006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1400063e2`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1400063e2`

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
0x1400063a0  mov     [rsp+arg_8], rbx
0x1400063a5  mov     [rsp+arg_10], rbp
0x1400063aa  push    rsi
0x1400063ab  push    rdi
0x1400063ac  push    r14
0x1400063ae  sub     rsp, 30h
0x1400063b2  mov     rax, cs:__security_cookie
0x1400063b9  xor     rax, rsp
0x1400063bc  mov     [rsp+48h+var_20], rax
0x1400063c1  mov     rdi, rcx
0x1400063c4  lea     rax, ??_7?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x1400063cb  mov     [rcx+18h], rax
0x1400063cf  xor     r14d, r14d
0x1400063d2  mov     [rcx+30h], r14
0x1400063d6  mov     [rsp+48h+ppunkMarshal], r14
0x1400063db  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x1400063e0  xor     ecx, ecx; punkOuter
0x1400063e2  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1400063e9  nop     dword ptr [rax+rax+00h]
0x1400063ee  test    eax, eax
0x1400063f0  js      short loc_14000642E
0x1400063f2  mov     rbx, [rsp+48h+ppunkMarshal]
0x1400063f7  mov     rax, [rbx]
0x1400063fa  mov     rbp, [rax]
0x1400063fd  mov     rcx, [rdi+30h]
0x140006401  test    rcx, rcx
0x140006404  jz      short loc_140006417
0x140006406  mov     [rdi+30h], r14
0x14000640a  mov     rdx, [rcx]
0x14000640d  mov     rax, [rdx+10h]
0x140006411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006416  nop
0x140006417  lea     r8, [rdi+30h]
0x14000641b  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x140006422  mov     rcx, rbx
0x140006425  mov     rax, rbp
0x140006428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000642d  nop
0x14000642e  mov     rcx, [rsp+48h+ppunkMarshal]
0x140006433  test    rcx, rcx
0x140006436  jz      short loc_14000644A
0x140006438  mov     [rsp+48h+ppunkMarshal], r14
0x14000643d  mov     rax, [rcx]
0x140006440  mov     rax, [rax+10h]
0x140006444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006449  nop
0x14000644a  mov     qword ptr [rdi+40h], 1
0x140006452  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$00@WRL@Microsoft@@UIAppReputationService@SmartScreen@Security@Internal@Windows@@UIAppReputationServiceStatics@5678@VFtmBase@23@@WRL@Microsoft@@6BIAppReputationService@SmartScreen@Security@Internal@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<1>,Windows::Internal::Security::SmartScreen::IAppReputationService,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Internal::Security::SmartScreen::IAppReputationService'}
0x140006459  mov     [rdi], rax
0x14000645c  lea     rax, ??_7application_reputation@com@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@@; const com::application_reputation::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics,Microsoft::WRL::FtmBase>'}
0x140006463  mov     [rdi+8], rax
0x140006467  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$00@WRL@Microsoft@@UIAppReputationService@SmartScreen@Security@Internal@Windows@@UIAppReputationServiceStatics@5678@VFtmBase@23@@WRL@Microsoft@@6BIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<1>,Windows::Internal::Security::SmartScreen::IAppReputationService,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics'}
0x14000646e  mov     [rdi+10h], rax
0x140006472  lea     rax, ??_7application_reputation@com@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const com::application_reputation::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x140006479  mov     [rdi+18h], rax
0x14000647d  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x140006484  test    rcx, rcx
0x140006487  jz      short loc_140006495
0x140006489  mov     rax, [rcx]
0x14000648c  mov     rax, [rax+8]
0x140006490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006495  mov     rax, rdi
0x140006498  mov     rcx, [rsp+48h+var_20]
0x14000649d  xor     rcx, rsp; StackCookie
0x1400064a0  call    __security_check_cookie
0x1400064a5  mov     rbx, [rsp+48h+arg_8]
0x1400064aa  mov     rbp, [rsp+48h+arg_10]
0x1400064af  add     rsp, 30h
0x1400064b3  pop     r14
0x1400064b5  pop     rdi
0x1400064b6  pop     rsi
0x1400064b7  retn
```
