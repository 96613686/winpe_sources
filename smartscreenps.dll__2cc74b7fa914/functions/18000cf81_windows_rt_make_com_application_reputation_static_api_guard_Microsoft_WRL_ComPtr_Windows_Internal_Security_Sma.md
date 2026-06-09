# _windows::rt::make_com::application_reputation_static_api_guard_&_Microsoft::WRL::ComPtr_Windows::Internal::Security::SmartScreen::IAppReputationService__&__::_1_::dtor$0

- ea: `0x18000cf81`
- end: `0x18000cfa7`
- name: `_windows::rt::make_com::application_reputation_static_api_guard_&_Microsoft::WRL::ComPtr_Windows::Internal::Security::SmartScreen::IAppReputationService__&__::_1_::dtor$0`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a860`
- `0x18000cf81`

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
0x18000cf81  push    rbp
0x18000cf83  sub     rsp, 20h
0x18000cf87  mov     rbp, rdx
0x18000cf8a  mov     eax, [rbp+20h]
0x18000cf8d  and     eax, 1
0x18000cf90  test    eax, eax
0x18000cf92  jz      short loc_18000CFA1
0x18000cf94  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x18000cf98  mov     rcx, [rbp+40h]
0x18000cf9c  call    ??1?$ComPtr@Vapplication_reputation_static@com@@@WRL@Microsoft@@QEAA@XZ
0x18000cfa1  add     rsp, 20h
0x18000cfa5  pop     rbp
0x18000cfa6  retn
```
