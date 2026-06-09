# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::AddRef(void)

- ea: `0x18000ad50`
- end: `0x18000ada5`
- name: `?AddRef@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAKXZ`
- size: `85`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000adb0`
- `0x18000adc0`
- `0x18000add0`

## callees

- `0x18000ad50`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::AddRef(
        __int64 a1)
{
  unsigned int v1; // ebx
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 68);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 68), v2 + 1, v2) )
    {
      v1 = v2 + 1;
      break;
    }
  }
  if ( (*(_BYTE *)(a1 + 88) & 4) == 0 && v1 == 2 && Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  return v1;
}

```

## disassembly

```asm
0x18000ad50  push    rbx
0x18000ad52  sub     rsp, 20h
0x18000ad56  mov     ebx, 7FFFFFFFh
0x18000ad5b  jmp     short loc_18000AD6B
0x18000ad5d  lea     edx, [r8+1]
0x18000ad61  mov     eax, r8d
0x18000ad64  lock cmpxchg [rcx+44h], edx
0x18000ad69  jz      short loc_18000AD76
0x18000ad6b  mov     r8d, [rcx+44h]
0x18000ad6f  cmp     r8d, ebx
0x18000ad72  jnz     short loc_18000AD5D
0x18000ad74  jmp     short loc_18000AD7A
0x18000ad76  lea     ebx, [r8+1]
0x18000ad7a  test    byte ptr [rcx+58h], 4
0x18000ad7e  jnz     short loc_18000AD9D
0x18000ad80  cmp     ebx, 2
0x18000ad83  jnz     short loc_18000AD9D
0x18000ad85  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000ad8c  test    rcx, rcx
0x18000ad8f  jz      short loc_18000AD9D
0x18000ad91  mov     rdx, [rcx]
0x18000ad94  mov     rax, [rdx+8]
0x18000ad98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad9d  mov     eax, ebx
0x18000ad9f  add     rsp, 20h
0x18000ada3  pop     rbx
0x18000ada4  retn
```
