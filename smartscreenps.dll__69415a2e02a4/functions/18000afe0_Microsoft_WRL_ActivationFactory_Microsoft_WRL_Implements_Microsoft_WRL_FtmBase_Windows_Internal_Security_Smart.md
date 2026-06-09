# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::AddRef(void)

- ea: `0x18000afe0`
- end: `0x18000b036`
- name: `?AddRef@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAKXZ`
- size: `86`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b040`
- `0x18000b050`
- `0x18000b060`

## callees

- `0x18000afe0`
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
0x18000afe0  push    rbx
0x18000afe2  sub     rsp, 20h
0x18000afe6  mov     ebx, 7FFFFFFFh
0x18000afeb  jmp     short loc_18000AFFB
0x18000afed  lea     edx, [r8+1]
0x18000aff1  mov     eax, r8d
0x18000aff4  lock cmpxchg [rcx+44h], edx
0x18000aff9  jz      short loc_18000B006
0x18000affb  mov     r8d, [rcx+44h]
0x18000afff  cmp     r8d, ebx
0x18000b002  jnz     short loc_18000AFED
0x18000b004  jmp     short loc_18000B00A
0x18000b006  lea     ebx, [r8+1]
0x18000b00a  test    byte ptr [rcx+58h], 4
0x18000b00e  jnz     short loc_18000B02D
0x18000b010  cmp     ebx, 2
0x18000b013  jnz     short loc_18000B02D
0x18000b015  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000b01c  test    rcx, rcx
0x18000b01f  jz      short loc_18000B02D
0x18000b021  mov     rdx, [rcx]
0x18000b024  mov     rax, [rdx+8]
0x18000b028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b02d  mov     eax, ebx
0x18000b02f  add     rsp, 20h
0x18000b033  pop     rbx
0x18000b034  retn
```
