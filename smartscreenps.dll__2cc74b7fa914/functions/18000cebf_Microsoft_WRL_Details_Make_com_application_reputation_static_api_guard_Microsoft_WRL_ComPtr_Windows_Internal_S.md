# _Microsoft::WRL::Details::Make_com::application_reputation_static_api_guard_&_Microsoft::WRL::ComPtr_Windows::Internal::Security::SmartScreen::IAppReputationService__&__::_1_::dtor$1

- ea: `0x18000cebf`
- end: `0x18000cecb`
- name: `_Microsoft::WRL::Details::Make_com::application_reputation_static_api_guard_&_Microsoft::WRL::ComPtr_Windows::Internal::Security::SmartScreen::IAppReputationService__&__::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a890`

## pseudocode

```c
void __fastcall Microsoft::WRL::Details::Make_com::application_reputation_static_api_guard___Microsoft::WRL::ComPtr_Windows::Internal::Security::SmartScreen::IAppReputationService_____::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  Microsoft::WRL::Details::MakeAllocator<com::application_reputation_static>::~MakeAllocator<com::application_reputation_static>((void **)(a2 + 40));
}

```

## disassembly

```asm
0x18000cebf  lea     rcx, [rdx+28h]
0x18000cec6  jmp     ??1?$MakeAllocator@Vapplication_reputation_static@com@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<com::application_reputation_static>::~MakeAllocator<com::application_reputation_static>(void)
```
