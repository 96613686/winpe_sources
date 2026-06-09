# __anonymous_namespace_::get_instance_Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics__anonymous_namespace_::smartscreen__::_1_::dtor$1

- ea: `0x18000d20b`
- end: `0x18000d232`
- name: `__anonymous_namespace_::get_instance_Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics__anonymous_namespace_::smartscreen__::_1_::dtor$1`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000aad0`
- `0x18000d20b`

## pseudocode

```c
__int64 __fastcall _anonymous_namespace_::get_instance_Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics__anonymous_namespace_::smartscreen__::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 64) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 64) &= ~1u;
    return Microsoft::WRL::ComPtr<IClassFactory>::~ComPtr<IClassFactory>(*(__int64 **)(a2 + 72));
  }
  return result;
}

```

## disassembly

```asm
0x18000d20b  push    rbp
0x18000d20d  sub     rsp, 20h
0x18000d211  mov     rbp, rdx
0x18000d214  mov     eax, [rbp+40h]
0x18000d217  and     eax, 1
0x18000d21a  test    eax, eax
0x18000d21c  jz      short loc_18000D22B
0x18000d21e  and     dword ptr [rbp+40h], 0FFFFFFFEh
0x18000d222  mov     rcx, [rbp+48h]
0x18000d226  call    ??1?$ComPtr@UIClassFactory@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IClassFactory>::~ComPtr<IClassFactory>(void)
0x18000d22b  add     rsp, 20h
0x18000d22f  pop     rbp
0x18000d230  retn
```
