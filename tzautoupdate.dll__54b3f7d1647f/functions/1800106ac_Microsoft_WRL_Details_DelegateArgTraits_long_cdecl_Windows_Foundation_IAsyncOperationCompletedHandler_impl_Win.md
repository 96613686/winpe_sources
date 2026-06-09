# Microsoft::WRL::Details::DelegateArgTraits_long_(__cdecl_Windows::Foundation::IAsyncOperationCompletedHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::Devices::Geolocation::Geoposition___Windows::Devices::Geolocation::IGeoposition_____::_)(Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus)_::DelegateInvokeHelper_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Devices::Geolocation::Geoposition_____lambda_30b76a65ab4580a0f6a760f8949de8ce___1_Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus_::DelegateInvokeHelper_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Devices::Geolocation::Geoposition_____lambda_30b76a65ab4580a0f6a760f8949de8ce___1_Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus_

- ea: `0x1800106ac`
- end: `0x18001070f`
- name: `Microsoft::WRL::Details::DelegateArgTraits_long_(__cdecl_Windows::Foundation::IAsyncOperationCompletedHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::Devices::Geolocation::Geoposition___Windows::Devices::Geolocation::IGeoposition_____::_)(Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus)_::DelegateInvokeHelper_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Devices::Geolocation::Geoposition_____lambda_30b76a65ab4580a0f6a760f8949de8ce___1_Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus_::DelegateInvokeHelper_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Devices::Geolocation::Geoposition_____lambda_30b76a65ab4580a0f6a760f8949de8ce___1_Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus_`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800105cc`

## callees

- `0x1800106ac`
- `0x18001d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::IAsyncOperationCompletedHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::Devices::Geolocation::Geoposition___Windows::Devices::Geolocation::IGeoposition_____::___Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus__::DelegateInvokeHelper_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Devices::Geolocation::Geoposition_____lambda_30b76a65ab4580a0f6a760f8949de8ce___1_Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus_::DelegateInvokeHelper_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Devices::Geolocation::Geoposition_____lambda_30b76a65ab4580a0f6a760f8949de8ce___1_Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus_(
        __int64 a1,
        _QWORD *a2)
{
  *(_QWORD *)a1 = &Windows::Foundation::ITypedEventHandler<Windows::Devices::Geolocation::Geolocator *,Windows::Devices::Geolocation::PositionChangedEventArgs *>::`vftable';
  *(_DWORD *)(a1 + 12) = 1;
  *(_QWORD *)a1 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>>::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)(a1 + 16) = *a2;
  *(_QWORD *)a1 = &off_18001EC38;
  return a1;
}

```

## disassembly

```asm
0x1800106ac  mov     [rsp+arg_0], rbx
0x1800106b1  push    rdi
0x1800106b2  sub     rsp, 20h
0x1800106b6  mov     rdi, rdx
0x1800106b9  mov     rbx, rcx
0x1800106bc  lea     rax, ??_7?$ITypedEventHandler@PEAVGeolocator@Geolocation@Devices@Windows@@PEAVPositionChangedEventArgs@234@@Foundation@Windows@@6B@; const Windows::Foundation::ITypedEventHandler<Windows::Devices::Geolocation::Geolocator *,Windows::Devices::Geolocation::PositionChangedEventArgs *>::`vftable'
0x1800106c3  mov     [rcx], rax
0x1800106c6  mov     dword ptr [rcx+0Ch], 1
0x1800106cd  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>>::`vftable'
0x1800106d4  mov     [rcx], rax
0x1800106d7  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800106de  test    rcx, rcx
0x1800106e1  jz      short loc_1800106F0
0x1800106e3  mov     rax, [rcx]
0x1800106e6  mov     rax, [rax+8]
0x1800106ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106ef  nop
0x1800106f0  mov     rax, [rdi]
0x1800106f3  mov     [rbx+10h], rax
0x1800106f7  lea     rax, off_18001EC38
0x1800106fe  mov     [rbx], rax
0x180010701  mov     rax, rbx
0x180010704  mov     rbx, [rsp+28h+arg_0]
0x180010709  add     rsp, 20h
0x18001070d  pop     rdi
0x18001070e  retn
```
