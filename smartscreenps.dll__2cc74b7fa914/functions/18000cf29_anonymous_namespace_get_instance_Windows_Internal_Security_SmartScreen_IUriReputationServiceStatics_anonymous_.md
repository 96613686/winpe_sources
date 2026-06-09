# __anonymous_namespace_::get_instance_Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics__anonymous_namespace_::smartscreen__::_1_::dtor$1

- ea: `0x18000cf29`
- end: `0x18000cf4f`
- name: `__anonymous_namespace_::get_instance_Windows::Internal::Security::SmartScreen::IUriReputationServiceStatics__anonymous_namespace_::smartscreen__::_1_::dtor$1`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a854`
- `0x18000cf29`

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
0x18000cf29  push    rbp
0x18000cf2b  sub     rsp, 20h
0x18000cf2f  mov     rbp, rdx
0x18000cf32  mov     eax, [rbp+40h]
0x18000cf35  and     eax, 1
0x18000cf38  test    eax, eax
0x18000cf3a  jz      short loc_18000CF49
0x18000cf3c  and     dword ptr [rbp+40h], 0FFFFFFFEh
0x18000cf40  mov     rcx, [rbp+48h]
0x18000cf44  call    ??1?$ComPtr@UIClassFactory@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IClassFactory>::~ComPtr<IClassFactory>(void)
0x18000cf49  add     rsp, 20h
0x18000cf4d  pop     rbp
0x18000cf4e  retn
```
