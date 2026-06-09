# _Microsoft::WRL::Details::Make_com::application_reputation_static_api_guard_&_Microsoft::WRL::ComPtr_Windows::Internal::Security::SmartScreen::IAppReputationService__&__::_1_::dtor$2

- ea: `0x18000d1b2`
- end: `0x18000d1cf`
- name: `_Microsoft::WRL::Details::Make_com::application_reputation_static_api_guard_&_Microsoft::WRL::ComPtr_Windows::Internal::Security::SmartScreen::IAppReputationService__&__::_1_::dtor$2`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x18000ac10`

## pseudocode

```c
void __fastcall Microsoft::WRL::Details::Make_com::application_reputation_static_api_guard___Microsoft::WRL::ComPtr_Windows::Internal::Security::SmartScreen::IAppReputationService_____::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  operator delete(*(void **)(a2 + 56), *(void **)(a2 + 48));
}

```

## disassembly

```asm
0x18000d1b2  push    rbp
0x18000d1b4  sub     rsp, 20h
0x18000d1b8  mov     rbp, rdx
0x18000d1bb  mov     rdx, [rbp+30h]; void *
0x18000d1bf  mov     rcx, [rbp+38h]; void *
0x18000d1c3  call    ??3@YAXPEAX0@Z; operator delete(void *,void *)
0x18000d1c8  add     rsp, 20h
0x18000d1cc  pop     rbp
0x18000d1cd  retn
```
