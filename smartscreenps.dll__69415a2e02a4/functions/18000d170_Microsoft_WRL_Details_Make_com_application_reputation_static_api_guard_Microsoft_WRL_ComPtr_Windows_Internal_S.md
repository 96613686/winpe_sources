# _Microsoft::WRL::Details::Make_com::application_reputation_static_api_guard_&_Microsoft::WRL::ComPtr_Windows::Internal::Security::SmartScreen::IAppReputationService__&__::_1_::dtor$0

- ea: `0x18000d170`
- end: `0x18000d19a`
- name: `_Microsoft::WRL::Details::Make_com::application_reputation_static_api_guard_&_Microsoft::WRL::ComPtr_Windows::Internal::Security::SmartScreen::IAppReputationService__&__::_1_::dtor$0`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000aadc`
- `0x18000d170`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::Details::Make_com::application_reputation_static_api_guard___Microsoft::WRL::ComPtr_Windows::Internal::Security::SmartScreen::IAppReputationService_____::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  _QWORD *result; // rax

  result = (_QWORD *)(*(_DWORD *)(a2 + 32) & 1);
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    return Microsoft::WRL::ComPtr<com::application_reputation_static>::~ComPtr<com::application_reputation_static>(*(_QWORD **)(a2 + 256));
  }
  return result;
}

```

## disassembly

```asm
0x18000d170  push    rbp
0x18000d172  sub     rsp, 20h
0x18000d176  mov     rbp, rdx
0x18000d179  mov     eax, [rbp+20h]
0x18000d17c  and     eax, 1
0x18000d17f  test    eax, eax
0x18000d181  jz      short loc_18000D193
0x18000d183  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x18000d187  mov     rcx, [rbp+100h]
0x18000d18e  call    ??1?$ComPtr@Vapplication_reputation_static@com@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<com::application_reputation_static>::~ComPtr<com::application_reputation_static>(void)
0x18000d193  add     rsp, 20h
0x18000d197  pop     rbp
0x18000d198  retn
```
