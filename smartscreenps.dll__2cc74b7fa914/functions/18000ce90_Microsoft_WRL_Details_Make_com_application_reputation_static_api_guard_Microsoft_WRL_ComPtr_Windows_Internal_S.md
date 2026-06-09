# _Microsoft::WRL::Details::Make_com::application_reputation_static_api_guard_&_Microsoft::WRL::ComPtr_Windows::Internal::Security::SmartScreen::IAppReputationService__&__::_1_::dtor$0

- ea: `0x18000ce90`
- end: `0x18000ceb9`
- name: `_Microsoft::WRL::Details::Make_com::application_reputation_static_api_guard_&_Microsoft::WRL::ComPtr_Windows::Internal::Security::SmartScreen::IAppReputationService__&__::_1_::dtor$0`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a860`
- `0x18000ce90`

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
0x18000ce90  push    rbp
0x18000ce92  sub     rsp, 20h
0x18000ce96  mov     rbp, rdx
0x18000ce99  mov     eax, [rbp+20h]
0x18000ce9c  and     eax, 1
0x18000ce9f  test    eax, eax
0x18000cea1  jz      short loc_18000CEB3
0x18000cea3  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x18000cea7  mov     rcx, [rbp+100h]
0x18000ceae  call    ??1?$ComPtr@Vapplication_reputation_static@com@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<com::application_reputation_static>::~ComPtr<com::application_reputation_static>(void)
0x18000ceb3  add     rsp, 20h
0x18000ceb7  pop     rbp
0x18000ceb8  retn
```
