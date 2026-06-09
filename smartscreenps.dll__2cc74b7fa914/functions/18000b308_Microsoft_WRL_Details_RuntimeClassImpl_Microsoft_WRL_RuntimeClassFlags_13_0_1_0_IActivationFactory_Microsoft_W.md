# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::InternalRelease(void)

- ea: `0x18000b308`
- end: `0x18000b32c`
- name: `?InternalRelease@?$RuntimeClassImpl@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@$00$0A@UIActivationFactory@@U?$Implements@VFtmBase@WRL@Microsoft@@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAKXZ`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b470`

## callees

- `0x18000b308`

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
0x18000b308  mov     r9d, 7FFFFFFFh
0x18000b30e  jmp     short loc_18000B31E
0x18000b310  lea     edx, [r8-1]
0x18000b314  mov     eax, r8d
0x18000b317  lock cmpxchg [rcx+44h], edx
0x18000b31c  jz      short loc_18000B327
0x18000b31e  mov     r8d, [rcx+44h]
0x18000b322  cmp     r8d, r9d
0x18000b325  jnz     short loc_18000B310
0x18000b327  lea     eax, [r8-1]
0x18000b32b  retn
```
