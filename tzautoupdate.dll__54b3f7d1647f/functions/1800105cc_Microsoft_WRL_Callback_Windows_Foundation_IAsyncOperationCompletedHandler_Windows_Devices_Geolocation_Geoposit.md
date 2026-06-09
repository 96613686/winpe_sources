# Microsoft::WRL::Callback_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Devices::Geolocation::Geoposition_____lambda_30b76a65ab4580a0f6a760f8949de8ce___

- ea: `0x1800105cc`
- end: `0x180010633`
- name: `Microsoft::WRL::Callback_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Devices::Geolocation::Geoposition_____lambda_30b76a65ab4580a0f6a760f8949de8ce___`
- size: `103`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800117d0`

## callees

- `0x1800027b8`
- `0x1800105cc`
- `0x1800106ac`
- `0x180010a7c`

## pseudocode

```c
__int64 *__fastcall Microsoft::WRL::Callback_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Devices::Geolocation::Geoposition_____lambda_30b76a65ab4580a0f6a760f8949de8ce___(
        __int64 *a1,
        __int64 a2)
{
  __int64 v4; // rbx
  void *v5; // rax
  __int64 *result; // rax
  void *v7; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  v5 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v5;
  if ( v5 )
  {
    v4 = Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::IAsyncOperationCompletedHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::Devices::Geolocation::Geoposition___Windows::Devices::Geolocation::IGeoposition_____::___Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus__::DelegateInvokeHelper_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Devices::Geolocation::Geoposition_____lambda_30b76a65ab4580a0f6a760f8949de8ce___1_Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus_::DelegateInvokeHelper_Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Devices::Geolocation::Geoposition_____lambda_30b76a65ab4580a0f6a760f8949de8ce___1_Windows::Foundation::IAsyncOperation_Windows::Devices::Geolocation::Geoposition______enum_ABI::Windows::Foundation::AsyncStatus_(
           v5,
           a2);
    v7 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::ITypedEventHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::Devices::Geolocation::Geolocator___Windows::Devices::Geolocation::IGeolocator____Windows::Foundation::Internal::AggregateType_Windows::Devices::Geolocation::PositionChangedEventArgs___Windows::Devices::Geolocation::IPositionChangedEventArgs_____::___Windows::Devices::Geolocation::IGeolocator___Windows::Devices::Geolocation::IPositionChangedEventArgs____::DelegateInvokeHelper_Windows::Foundation::ITypedEventHandler_Windows::Devices::Geolocation::Geolocator___Windows::Devices::Geolocation::PositionChangedEventArgs_____lambda_c300570cc2d0924e916db4b97c5536e3___1_Windows::Devices::Geolocation::IGeolocator___Windows::Devices::Geolocation::IPositionChangedEventArgs_____::_MakeAllocator_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::ITypedEventHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::Devices::Geolocation::Geolocator___Windows::Devices::Geolocation::IGeolocator____Windows::Foundation::Internal::AggregateType_Windows::Devices::Geolocation::PositionChangedEventArgs___Windows::Devices::Geolocation::IPositionChangedEventArgs_____::___Windows::Devices::Geolocation::IGeolocator___Windows::Devices::Geolocation::IPositionChangedEventArgs____::DelegateInvokeHelper_Windows::Foundation::ITypedEventHandler_Windows::Devices::Geolocation::Geolocator___Windows::Devices::Geolocation::PositionChangedEventArgs_____lambda_c300570cc2d0924e916db4b97c5536e3___1_Windows::Devices::Geolocation::IGeolocator___Windows::Devices::Geolocation::IPositionChangedEventArgs_____(&v7);
  result = a1;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x1800105cc  mov     [rsp+arg_8], rbx
0x1800105d1  mov     [rsp+arg_10], rsi
0x1800105d6  push    rdi
0x1800105d7  sub     rsp, 20h
0x1800105db  mov     rsi, rdx
0x1800105de  mov     rdi, rcx
0x1800105e1  xor     ebx, ebx
0x1800105e3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800105ea  lea     ecx, [rbx+18h]; unsigned __int64
0x1800105ed  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800105f2  mov     [rsp+28h+arg_0], rax
0x1800105f7  test    rax, rax
0x1800105fa  jz      short loc_180010613
0x1800105fc  mov     rdx, rsi
0x1800105ff  mov     rcx, rax
0x180010602  call    Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__Foundation__IAsyncOperationCompletedHandler_impl_Windows__Foundation__Internal__AggregateType_Windows__Devices__Geolocation__Geoposition___Windows__Devices__Geolocation__IGeoposition__________Windows__Foundation__IAsyncOperation_Windows__Devices__Geolocation__Geoposition______enum_ABI__Windows__Foundation__AsyncStatus____DelegateInvokeHelper_Windows__Foundation__IAsyncOperationCompletedHandler_Windows__Devices__Geolocation__Geoposition_____lambda_30b76a65ab4580a0f6a760f8949de8ce___1_Windows__Foundation__IAsyncOperation_Windows__Devices__Geolocation__Geoposition______enum_ABI__Windows__Foundation__AsyncStatus___DelegateInvokeHelper_Windows__Foundation__IAsyncOperationCompletedHandler_Windows__Devices__Geolocation__Geoposition_____lambda_30b76a65ab4580a0f6a760f8949de8ce___1_Windows__Foundation__IAsyncOperation_Windows__Devices__Geolocation__Geoposition______enum_ABI__Windows__Foundation__AsyncStatus_
0x180010607  mov     rbx, rax
0x18001060a  mov     [rsp+28h+arg_0], 0
0x180010613  lea     rcx, [rsp+28h+arg_0]
0x180010618  call    Microsoft__WRL__Details__MakeAllocator_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__Foundation__ITypedEventHandler_impl_Windows__Foundation__Internal__AggregateType_Windows__Devices__Geolocation__Geolocator___Windows__Devices__Geolocation__IGeolocator____Windows__Foundation__Internal__AggregateType_Windows__Devices__Geolocation__PositionChangedEventArgs___Windows__Devices__Geolocation__IPositionChangedEventArgs__________Windows__Devices__Geolocation__IGeolocator___Windows__Devices__Geolocation__IPositionChangedEventArgs______DelegateInvokeHelper_Windows__Foundation__ITypedEventHandler_Windows__Devices__Geolocation__Geolocator___Windows__Devices__Geolocation__PositionChangedEventArgs_____lambda_c300570cc2d0924e916db4b97c5536e3___1_Windows__Devices__Geolocation__IGeolocator___Windows__Devices__Geolocation__IPositionChangedEventArgs________MakeAllocator_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__Foundation__ITypedEventHandler_impl_Windows__Foundation__Internal__AggregateType_Windows__Devices__Geolocation__Geolocator___Windows__Devices__Geolocation__IGeolocator____Windows__Foundation__Internal__AggregateType_Windows__Devices__Geolocation__PositionChangedEventArgs___Windows__Devices__Geolocation__IPositionChangedEventArgs__________Windows__Devices__Geolocation__IGeolocator___Windows__Devices__Geolocation__IPositionChangedEventArgs______DelegateInvokeHelper_Windows__Foundation__ITypedEventHandler_Windows__Devices__Geolocation__Geolocator___Windows__Devices__Geolocation__PositionChangedEventArgs_____lambda_c300570cc2d0924e916db4b97c5536e3___1_Windows__Devices__Geolocation__IGeolocator___Windows__Devices__Geolocation__IPositionChangedEventArgs_____
0x18001061d  mov     rsi, [rsp+28h+arg_10]
0x180010622  mov     rax, rdi
0x180010625  mov     [rdi], rbx
0x180010628  mov     rbx, [rsp+28h+arg_8]
0x18001062d  add     rsp, 20h
0x180010631  pop     rdi
0x180010632  retn
```
