# __anonymous_namespace_::get_instance_Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics__anonymous_namespace_::smartscreen__::_1_::dtor$0

- ea: `0x18000d1f9`
- end: `0x18000d205`
- name: `__anonymous_namespace_::get_instance_Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics__anonymous_namespace_::smartscreen__::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000aad0`

## pseudocode

```c
__int64 __fastcall _anonymous_namespace_::get_instance_Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics__anonymous_namespace_::smartscreen__::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return Microsoft::WRL::ComPtr<IClassFactory>::~ComPtr<IClassFactory>((__int64 *)(a2 + 80));
}

```

## disassembly

```asm
0x18000d1f9  lea     rcx, [rdx+50h]
0x18000d200  jmp     ??1?$ComPtr@UIClassFactory@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IClassFactory>::~ComPtr<IClassFactory>(void)
```
