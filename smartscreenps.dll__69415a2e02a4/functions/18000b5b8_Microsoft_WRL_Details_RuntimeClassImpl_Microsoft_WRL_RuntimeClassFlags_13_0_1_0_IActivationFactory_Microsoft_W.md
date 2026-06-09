# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::InternalRelease(void)

- ea: `0x18000b5b8`
- end: `0x18000b5dc`
- name: `?InternalRelease@?$RuntimeClassImpl@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@$00$0A@UIActivationFactory@@U?$Implements@VFtmBase@WRL@Microsoft@@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAKXZ`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b720`

## callees

- `0x18000b5b8`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::InternalRelease(
        __int64 a1)
{
  signed __int32 v1; // r8d

  do
    v1 = *(_DWORD *)(a1 + 68);
  while ( v1 != 0x7FFFFFFF && v1 != _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 68), v1 - 1, v1) );
  return (unsigned int)(v1 - 1);
}

```

## disassembly

```asm
0x18000b5b8  mov     r9d, 7FFFFFFFh
0x18000b5be  jmp     short loc_18000B5CE
0x18000b5c0  lea     edx, [r8-1]
0x18000b5c4  mov     eax, r8d
0x18000b5c7  lock cmpxchg [rcx+44h], edx
0x18000b5cc  jz      short loc_18000B5D7
0x18000b5ce  mov     r8d, [rcx+44h]
0x18000b5d2  cmp     r8d, r9d
0x18000b5d5  jnz     short loc_18000B5C0
0x18000b5d7  lea     eax, [r8-1]
0x18000b5db  retn
```
