# Microsoft::WRL::Details::DelegateArgTraits_long_(__cdecl_Windows::Foundation::IAsyncOperationCompletedHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::Devices::Geolocation::Geoposition___Windows::Devices::Geolocation::IGeoposition_____::_)(Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus)_::DelegateInvokeHelper_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Devices::Geolocation::Geoposition_____lambda_30b76a65ab4580a0f6a760f8949de8ce___1_Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus_::Invoke

- ea: `0x180011ab0`
- end: `0x180011ad4`
- name: `Microsoft::WRL::Details::DelegateArgTraits_long_(__cdecl_Windows::Foundation::IAsyncOperationCompletedHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::Devices::Geolocation::Geoposition___Windows::Devices::Geolocation::IGeoposition_____::_)(Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus)_::DelegateInvokeHelper_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Devices::Geolocation::Geoposition_____lambda_30b76a65ab4580a0f6a760f8949de8ce___1_Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus_::Invoke`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180010c34`
- `0x180010d90`
- `0x180011ab0`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::IAsyncOperationCompletedHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::Devices::Geolocation::Geoposition___Windows::Devices::Geolocation::IGeoposition_____::___Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus__::DelegateInvokeHelper_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Devices::Geolocation::Geoposition_____lambda_30b76a65ab4580a0f6a760f8949de8ce___1_Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus_::Invoke(
        __int64 a1)
{
  int v1; // eax
  unsigned int v2; // ebx

  v1 = lambda_30b76a65ab4580a0f6a760f8949de8ce_::operator()(a1 + 16);
  v2 = v1;
  if ( v1 < 0 )
    Microsoft::WRL::DelegateTraits<-1>::EnsureStackSnapshot((unsigned int)v1);
  return v2;
}

```

## disassembly

```asm
0x180011ab0  push    rbx
0x180011ab2  sub     rsp, 20h
0x180011ab6  add     rcx, 10h
0x180011aba  call    _lambda_30b76a65ab4580a0f6a760f8949de8ce___operator__
0x180011abf  mov     ebx, eax
0x180011ac1  test    eax, eax
0x180011ac3  jns     short loc_180011ACC
0x180011ac5  mov     ecx, eax
0x180011ac7  call    ?EnsureStackSnapshot@?$DelegateTraits@$0?0@WRL@Microsoft@@SAXJ@Z; Microsoft::WRL::DelegateTraits<-1>::EnsureStackSnapshot(long)
0x180011acc  mov     eax, ebx
0x180011ace  add     rsp, 20h
0x180011ad2  pop     rbx
0x180011ad3  retn
```
