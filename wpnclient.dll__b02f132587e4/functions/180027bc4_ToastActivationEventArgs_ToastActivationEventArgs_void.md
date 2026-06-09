# ToastActivationEventArgs::ToastActivationEventArgs(void)

- ea: `0x180027bc4`
- end: `0x180027cae`
- name: `??0ToastActivationEventArgs@@QEAA@XZ`
- size: `234`
- prototype: `ToastActivationEventArgs *__fastcall(ToastActivationEventArgs *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800277b0`
- `0x18002e7c4`

## callees

- `0x180027ad4`

## import_xrefs

- `api-ms-win-shcore-thread-l1-1-0!SHGetThreadRef` at `0x180027be6`
- `api-ms-win-shcore-thread-l1-1-0!SHGetThreadRef` at `0x180027be6`

## pseudocode

```c
ToastActivationEventArgs *__fastcall ToastActivationEventArgs::ToastActivationEventArgs(ToastActivationEventArgs *this)
{
  IUnknown **v2; // rcx
  ToastActivationEventArgs *result; // rax

  *(_QWORD *)this = &CThreadRefTaker::`vftable';
  v2 = (IUnknown **)((char *)this + 8);
  *v2 = 0;
  SHGetThreadRef(v2);
  Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,CActivatedEventArgsWithViewIdBase,Windows::ApplicationModel::Activation::IToastNotificationActivatedEventArgs,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueMarshalByPropertySet>>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,CActivatedEventArgsWithViewIdBase,Windows::ApplicationModel::Activation::IToastNotificationActivatedEventArgs,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueMarshalByPropertySet>>((char *)this + 16);
  *(_QWORD *)this = &ToastActivationEventArgs::`vftable'{for `CThreadRefTaker'};
  *((_QWORD *)this + 2) = &ToastActivationEventArgs::`vftable'{for `Microsoft::WRL::Details::Selector<CActivatedEventArgsBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<CActivatedEventArgsBase>,Windows::ApplicationModel::Activation::IApplicationViewActivatedEventArgs,Windows::ApplicationModel::Activation::IViewSwitcherProvider,Microsoft::WRL::CloakedIid<Windows::ApplicationModel::Activation::IMultiviewActivationProperties>>>'};
  *((_QWORD *)this + 3) = &ToastActivationEventArgs::`vftable'{for `Windows::ApplicationModel::Activation::IActivatedEventArgsWithUser'};
  *((_QWORD *)this + 4) = &ToastActivationEventArgs::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::CloakedIid<Windows::ApplicationModel::Activation::IInitializeActivatedEventArgs>,Microsoft::WRL::CloakedIid<Windows::ApplicationModel::Activation::IActivatedEventArgsInternal>,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 5) = &ToastActivationEventArgs::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::ApplicationModel::Activation::IActivatedEventArgsInternal>'};
  *((_QWORD *)this + 6) = &ToastActivationEventArgs::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 21) = &ToastActivationEventArgs::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::ApplicationModel::Activation::IApplicationViewActivatedEventArgs,Windows::ApplicationModel::Activation::IViewSwitcherProvider,Microsoft::WRL::CloakedIid<Windows::ApplicationModel::Activation::IMultiviewActivationProperties>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<CActivatedEventArgsBase>,Windows::ApplicationModel::Activation::IApplicationViewActivatedEventArgs,Windows::ApplicationModel::Activation::IViewSwitcherProvider,Microsoft::WRL::CloakedIid<Windows::ApplicationModel::Activation::IMultiviewActivationProperties>>>'};
  *((_QWORD *)this + 22) = &ToastActivationEventArgs::`vftable'{for `Windows::ApplicationModel::Activation::IViewSwitcherProvider'};
  *((_QWORD *)this + 23) = &ToastActivationEventArgs::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::CloakedIid<Windows::ApplicationModel::Activation::IMultiviewActivationProperties>>'};
  *((_QWORD *)this + 29) = &ToastActivationEventArgs::`vftable'{for `Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,CActivatedEventArgsWithViewIdBase,Windows::ApplicationModel::Activation::IToastNotificationActivatedEventArgs,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueMarshalByPropertySet>>'};
  *((_QWORD *)this + 30) = &ToastActivationEventArgs::`vftable'{for `Windows::ApplicationModel::Activation::IToastNotificationActivatedEventArgs'};
  *((_QWORD *)this + 31) = &ToastActivationEventArgs::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueMarshalByPropertySet>>'};
  result = this;
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 35) = 0;
  return result;
}

```

## disassembly

```asm
0x180027bc4  mov     [rsp+arg_0], rbx
0x180027bc9  push    rdi
0x180027bca  sub     rsp, 20h
0x180027bce  lea     rax, ??_7CThreadRefTaker@@6B@; const CThreadRefTaker::`vftable'
0x180027bd5  mov     rdi, rcx
0x180027bd8  mov     [rcx], rax
0x180027bdb  add     rcx, 8; ppunk
0x180027bdf  mov     qword ptr [rcx], 0
0x180027be6  call    cs:__imp_SHGetThreadRef
0x180027bec  lea     rcx, [rdi+10h]
0x180027bf0  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@VCActivatedEventArgsWithViewIdBase@@UIToastNotificationActivatedEventArgs@Activation@ApplicationModel@Windows@@U?$CloakedIid@UIValueMarshalByPropertySet@Internal@Marshaling@Foundation@Windows@@@23@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,CActivatedEventArgsWithViewIdBase,Windows::ApplicationModel::Activation::IToastNotificationActivatedEventArgs,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueMarshalByPropertySet>>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,CActivatedEventArgsWithViewIdBase,Windows::ApplicationModel::Activation::IToastNotificationActivatedEventArgs,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueMarshalByPropertySet>>(void)
0x180027bf5  mov     rbx, [rsp+28h+arg_0]
0x180027bfa  lea     rax, ??_7ToastActivationEventArgs@@6BCThreadRefTaker@@@; const ToastActivationEventArgs::`vftable'{for `CThreadRefTaker'}
0x180027c01  mov     [rdi], rax
0x180027c04  lea     rax, ??_7ToastActivationEventArgs@@6B?$Selector@VCActivatedEventArgsBase@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VCActivatedEventArgsBase@@@Details@23@UIApplicationViewActivatedEventArgs@Activation@ApplicationModel@Windows@@UIViewSwitcherProvider@789@U?$CloakedIid@UIMultiviewActivationProperties@Activation@ApplicationModel@Windows@@@23@@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@@; const ToastActivationEventArgs::`vftable'{for `Microsoft::WRL::Details::Selector<CActivatedEventArgsBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<CActivatedEventArgsBase>,Windows::ApplicationModel::Activation::IApplicationViewActivatedEventArgs,Windows::ApplicationModel::Activation::IViewSwitcherProvider,Microsoft::WRL::CloakedIid<Windows::ApplicationModel::Activation::IMultiviewActivationProperties>>>'}
0x180027c0b  mov     [rdi+10h], rax
0x180027c0f  lea     rax, ??_7ToastActivationEventArgs@@6BIActivatedEventArgsWithUser@Activation@ApplicationModel@Windows@@@; const ToastActivationEventArgs::`vftable'{for `Windows::ApplicationModel::Activation::IActivatedEventArgsWithUser'}
0x180027c16  mov     [rdi+18h], rax
0x180027c1a  lea     rax, ??_7ToastActivationEventArgs@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$CloakedIid@UIInitializeActivatedEventArgs@Activation@ApplicationModel@Windows@@@23@U?$CloakedIid@UIActivatedEventArgsInternal@Activation@ApplicationModel@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@@; const ToastActivationEventArgs::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::CloakedIid<Windows::ApplicationModel::Activation::IInitializeActivatedEventArgs>,Microsoft::WRL::CloakedIid<Windows::ApplicationModel::Activation::IActivatedEventArgsInternal>,Microsoft::WRL::FtmBase>'}
0x180027c21  mov     [rdi+20h], rax
0x180027c25  lea     rax, ??_7ToastActivationEventArgs@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIActivatedEventArgsInternal@Activation@ApplicationModel@Windows@@@Details@WRL@Microsoft@@@; const ToastActivationEventArgs::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::ApplicationModel::Activation::IActivatedEventArgsInternal>'}
0x180027c2c  mov     [rdi+28h], rax
0x180027c30  lea     rax, ??_7ToastActivationEventArgs@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const ToastActivationEventArgs::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180027c37  mov     [rdi+30h], rax
0x180027c3b  lea     rax, ??_7ToastActivationEventArgs@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIApplicationViewActivatedEventArgs@Activation@ApplicationModel@Windows@@UIViewSwitcherProvider@567@U?$CloakedIid@UIMultiviewActivationProperties@Activation@ApplicationModel@Windows@@@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VCActivatedEventArgsBase@@@Details@23@UIApplicationViewActivatedEventArgs@Activation@ApplicationModel@Windows@@UIViewSwitcherProvider@789@U?$CloakedIid@UIMultiviewActivationProperties@Activation@ApplicationModel@Windows@@@23@@234@@Details@WRL@Microsoft@@@; const ToastActivationEventArgs::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::ApplicationModel::Activation::IApplicationViewActivatedEventArgs,Windows::ApplicationModel::Activation::IViewSwitcherProvider,Microsoft::WRL::CloakedIid<Windows::ApplicationModel::Activation::IMultiviewActivationProperties>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<CActivatedEventArgsBase>,Windows::ApplicationModel::Activation::IApplicationViewActivatedEventArgs,Windows::ApplicationModel::Activation::IViewSwitcherProvider,Microsoft::WRL::CloakedIid<Windows::ApplicationModel::Activation::IMultiviewActivationProperties>>>'}
0x180027c42  mov     [rdi+0A8h], rax
0x180027c49  lea     rax, ??_7ToastActivationEventArgs@@6BIViewSwitcherProvider@Activation@ApplicationModel@Windows@@@; const ToastActivationEventArgs::`vftable'{for `Windows::ApplicationModel::Activation::IViewSwitcherProvider'}
0x180027c50  mov     [rdi+0B0h], rax
0x180027c57  lea     rax, ??_7ToastActivationEventArgs@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$CloakedIid@UIMultiviewActivationProperties@Activation@ApplicationModel@Windows@@@23@@Details@WRL@Microsoft@@@; const ToastActivationEventArgs::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::CloakedIid<Windows::ApplicationModel::Activation::IMultiviewActivationProperties>>'}
0x180027c5e  mov     [rdi+0B8h], rax
0x180027c65  lea     rax, ??_7ToastActivationEventArgs@@6B?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@VCActivatedEventArgsWithViewIdBase@@UIToastNotificationActivatedEventArgs@Activation@ApplicationModel@Windows@@U?$CloakedIid@UIValueMarshalByPropertySet@Internal@Marshaling@Foundation@Windows@@@23@@WRL@Microsoft@@@; const ToastActivationEventArgs::`vftable'{for `Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,CActivatedEventArgsWithViewIdBase,Windows::ApplicationModel::Activation::IToastNotificationActivatedEventArgs,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueMarshalByPropertySet>>'}
0x180027c6c  mov     [rdi+0E8h], rax
0x180027c73  lea     rax, ??_7ToastActivationEventArgs@@6BIToastNotificationActivatedEventArgs@Activation@ApplicationModel@Windows@@@; const ToastActivationEventArgs::`vftable'{for `Windows::ApplicationModel::Activation::IToastNotificationActivatedEventArgs'}
0x180027c7a  mov     [rdi+0F0h], rax
0x180027c81  lea     rax, ??_7ToastActivationEventArgs@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$CloakedIid@UIValueMarshalByPropertySet@Internal@Marshaling@Foundation@Windows@@@23@@Details@WRL@Microsoft@@@; const ToastActivationEventArgs::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueMarshalByPropertySet>>'}
0x180027c88  mov     [rdi+0F8h], rax
0x180027c8f  mov     rax, rdi
0x180027c92  mov     qword ptr [rdi+110h], 0
0x180027c9d  mov     qword ptr [rdi+118h], 0
0x180027ca8  add     rsp, 20h
0x180027cac  pop     rdi
0x180027cad  retn
```
