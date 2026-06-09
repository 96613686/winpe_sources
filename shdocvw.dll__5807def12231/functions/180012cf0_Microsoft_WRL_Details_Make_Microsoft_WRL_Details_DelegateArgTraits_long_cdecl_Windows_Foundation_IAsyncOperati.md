# Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long_(__cdecl_Windows::Foundation::IAsyncOperationCompletedHandler_impl_enum_Windows::Internal::Security::SmartScreen::AppReputationResult_::_)(Windows::Foundation::IAsyncOperation_enum_Windows::Internal::Security::SmartScreen::AppReputationResult____enum_ABI::Windows::Foundation::AsyncStatus)_::DelegateInvokeHelper_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__Windows::Foundation::IAsyncOperationCompletedHandler_enum_Windows::Internal::Security::SmartScreen::AppReputationResult__IUnknown___lambda_9561cba1c609edf37800408a549a8f14___1_Windows::Foundation::IAsyncOperation_enum_Windows::Internal::Security::SmartScreen::AppReputationResult____enum_ABI::Windows::Foundation::AsyncStatus___lambda_9561cba1c609edf37800408a549a8f14___

- ea: `0x180012cf0`
- end: `0x180012db2`
- name: `Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long_(__cdecl_Windows::Foundation::IAsyncOperationCompletedHandler_impl_enum_Windows::Internal::Security::SmartScreen::AppReputationResult_::_)(Windows::Foundation::IAsyncOperation_enum_Windows::Internal::Security::SmartScreen::AppReputationResult____enum_ABI::Windows::Foundation::AsyncStatus)_::DelegateInvokeHelper_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__Windows::Foundation::IAsyncOperationCompletedHandler_enum_Windows::Internal::Security::SmartScreen::AppReputationResult__IUnknown___lambda_9561cba1c609edf37800408a549a8f14___1_Windows::Foundation::IAsyncOperation_enum_Windows::Internal::Security::SmartScreen::AppReputationResult____enum_ABI::Windows::Foundation::AsyncStatus___lambda_9561cba1c609edf37800408a549a8f14___`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800133e4`

## callees

- `0x18000872c`
- `0x180012cf0`
- `0x1800142e8`
- `0x180014b44`
- `0x1800186c0`
- `0x180029010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::IAsyncOperationCompletedHandler_impl_enum_Windows::Internal::Security::SmartScreen::AppReputationResult_::___Windows::Foundation::IAsyncOperation_enum_Windows::Internal::Security::SmartScreen::AppReputationResult____enum_ABI::Windows::Foundation::AsyncStatus__::DelegateInvokeHelper_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__Windows::Foundation::IAsyncOperationCompletedHandler_enum_Windows::Internal::Security::SmartScreen::AppReputationResult__IUnknown___lambda_9561cba1c609edf37800408a549a8f14___1_Windows::Foundation::IAsyncOperation_enum_Windows::Internal::Security::SmartScreen::AppReputationResult____enum_ABI::Windows::Foundation::AsyncStatus___lambda_9561cba1c609edf37800408a549a8f14___(
        _QWORD *a1,
        _QWORD *a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  _QWORD *v7; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v4 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  v7 = v4;
  if ( v4 )
  {
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::Security::SmartScreen::AppReputationResult>,IUnknown>>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::Security::SmartScreen::AppReputationResult>,IUnknown>>(v4);
    *v5 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::Security::SmartScreen::AppReputationResult>,IUnknown>>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::Security::SmartScreen::AppReputationResult>'};
    v5[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::Security::SmartScreen::AppReputationResult>,IUnknown>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IUnknown>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v5[5] = *a2;
    *v5 = &off_18002A230;
    v5[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::Security::SmartScreen::AppReputationResult>,IUnknown>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IUnknown>'};
    if ( *a1 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::Security::SmartScreen::AppReputationResult>,IUnknown>>::Release();
    *a1 = v5;
    v7 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator__anonymous_namespace_::Window_::_MakeAllocator__anonymous_namespace_::Window_(&v7);
  return a1;
}

```

## disassembly

```asm
0x180012cf0  mov     [rsp+arg_8], rbx
0x180012cf5  mov     [rsp+arg_10], rsi
0x180012cfa  push    rdi
0x180012cfb  sub     rsp, 20h
0x180012cff  mov     rsi, rdx
0x180012d02  mov     rdi, rcx
0x180012d05  mov     qword ptr [rcx], 0
0x180012d0c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012d13  mov     ecx, 30h ; '0'; unsigned __int64
0x180012d18  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180012d1d  mov     rbx, rax
0x180012d20  mov     [rsp+28h+arg_0], rax
0x180012d25  test    rax, rax
0x180012d28  jz      short loc_180012D95
0x180012d2a  mov     rcx, rax
0x180012d2d  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@UIUnknown@@@23@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>,IUnknown>>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>,IUnknown>>(void)
0x180012d32  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@UIUnknown@@@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>,IUnknown>>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>'}
0x180012d39  mov     [rbx], rcx
0x180012d3c  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@UIUnknown@@@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIUnknown@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>,IUnknown>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IUnknown>'}
0x180012d43  mov     [rbx+8], rax
0x180012d47  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180012d4e  test    rcx, rcx
0x180012d51  jz      short loc_180012D60
0x180012d53  mov     rax, [rcx]
0x180012d56  mov     rax, [rax+8]
0x180012d5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d5f  nop
0x180012d60  mov     rax, [rsi]
0x180012d63  mov     [rbx+28h], rax
0x180012d67  lea     rax, off_18002A230
0x180012d6e  mov     [rbx], rax
0x180012d71  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@UIUnknown@@@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIUnknown@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>,IUnknown>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IUnknown>'}
0x180012d78  mov     [rbx+8], rax
0x180012d7c  mov     rcx, [rdi]
0x180012d7f  test    rcx, rcx
0x180012d82  jz      short loc_180012D89
0x180012d84  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@UIUnknown@@@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>,IUnknown>>::Release(void)
0x180012d89  mov     [rdi], rbx
0x180012d8c  mov     [rsp+28h+arg_0], 0
0x180012d95  lea     rcx, [rsp+28h+arg_0]
0x180012d9a  call    Microsoft__WRL__Details__MakeAllocator__anonymous_namespace___Window____MakeAllocator__anonymous_namespace___Window_
0x180012d9f  mov     rax, rdi
0x180012da2  mov     rbx, [rsp+28h+arg_8]
0x180012da7  mov     rsi, [rsp+28h+arg_10]
0x180012dac  add     rsp, 20h
0x180012db0  pop     rdi
0x180012db1  retn
```
