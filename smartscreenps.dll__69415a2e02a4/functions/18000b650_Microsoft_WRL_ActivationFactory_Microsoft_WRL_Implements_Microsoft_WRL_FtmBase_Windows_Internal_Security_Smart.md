# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000b650`
- end: `0x18000b6c5`
- name: `?QueryInterface@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `117`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b6d0`
- `0x18000b6e0`

## callees

- `0x18000b090`
- `0x18000b588`
- `0x18000b650`
- `0x18000e010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::QueryInterface(
        __int64 a1,
        const struct _GUID *a2,
        _QWORD *a3)
{
  const struct _GUID *v3; // rcx
  _QWORD *v4; // r8
  __int64 v5; // r9
  __int64 v6; // r10
  int CanCastTo; // ebx
  _QWORD *v8; // r8

  *a3 = 0;
  if ( (unsigned int)InlineIsEqualGUID(a2, &GUID_00000000_0000_0000_c000_000000000046)
    || (unsigned int)InlineIsEqualGUID(v3, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90) )
  {
    *v4 = v5;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
    return 0;
  }
  else
  {
    CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(
                  v5,
                  v6);
    if ( CanCastTo >= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 8LL))(*v8);
  }
  return (unsigned int)CanCastTo;
}

```

## disassembly

```asm
0x18000b650  push    rbx
0x18000b652  sub     rsp, 20h
0x18000b656  mov     r10, rdx
0x18000b659  mov     r9, rcx
0x18000b65c  mov     qword ptr [r8], 0
0x18000b663  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x18000b66a  mov     rcx, r10; struct _GUID *
0x18000b66d  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000b672  test    eax, eax
0x18000b674  jnz     short loc_18000B6A8
0x18000b676  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; struct _GUID *
0x18000b67d  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000b682  test    eax, eax
0x18000b684  jnz     short loc_18000B6A8
0x18000b686  mov     rdx, r10
0x18000b689  mov     rcx, r9
0x18000b68c  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@U?$Implements@VFtmBase@WRL@Microsoft@@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(_GUID const &,void * *,bool *)
0x18000b691  mov     ebx, eax
0x18000b693  test    eax, eax
0x18000b695  js      short loc_18000B6BC
0x18000b697  mov     rcx, [r8]
0x18000b69a  mov     rax, [rcx]
0x18000b69d  mov     rax, [rax+8]
0x18000b6a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6a6  jmp     short loc_18000B6BC
0x18000b6a8  mov     [r8], r9
0x18000b6ab  mov     rax, [r9]
0x18000b6ae  mov     rcx, r9
0x18000b6b1  mov     rax, [rax+8]
0x18000b6b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6ba  xor     ebx, ebx
0x18000b6bc  mov     eax, ebx
0x18000b6be  add     rsp, 20h
0x18000b6c2  pop     rbx
0x18000b6c3  retn
```
