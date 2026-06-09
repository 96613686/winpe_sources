# _windows::rt::make_com::application_reputation_static_api_guard_&_Microsoft::WRL::ComPtr_Windows::Internal::Security::SmartScreen::IAppReputationService__&__::_1_::dtor$0

- ea: `0x18000d264`
- end: `0x18000d28b`
- name: `_windows::rt::make_com::application_reputation_static_api_guard_&_Microsoft::WRL::ComPtr_Windows::Internal::Security::SmartScreen::IAppReputationService__&__::_1_::dtor$0`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000aadc`
- `0x18000d264`

## pseudocode

```c
_QWORD *__fastcall windows::rt::make_com::application_reputation_static_api_guard___Microsoft::WRL::ComPtr_Windows::Internal::Security::SmartScreen::IAppReputationService_____::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  _QWORD *result; // rax

  result = (_QWORD *)(*(_DWORD *)(a2 + 32) & 1);
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    return Microsoft::WRL::ComPtr<com::application_reputation_static>::~ComPtr<com::application_reputation_static>(*(_QWORD **)(a2 + 64));
  }
  return result;
}

```

## disassembly

```asm
0x18000d264  push    rbp
0x18000d266  sub     rsp, 20h
0x18000d26a  mov     rbp, rdx
0x18000d26d  mov     eax, [rbp+20h]
0x18000d270  and     eax, 1
0x18000d273  test    eax, eax
0x18000d275  jz      short loc_18000D284
0x18000d277  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x18000d27b  mov     rcx, [rbp+40h]
0x18000d27f  call    ??1?$ComPtr@Vapplication_reputation_static@com@@@WRL@Microsoft@@QEAA@XZ
0x18000d284  add     rsp, 20h
0x18000d288  pop     rbp
0x18000d289  retn
```
