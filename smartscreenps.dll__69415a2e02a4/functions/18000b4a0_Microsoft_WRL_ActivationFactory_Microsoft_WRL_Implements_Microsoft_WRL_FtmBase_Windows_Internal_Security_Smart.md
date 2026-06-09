# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetTrustLevel(TrustLevel *)

- ea: `0x18000b4a0`
- end: `0x18000b4cd`
- name: `?GetTrustLevel@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJPEAW4TrustLevel@@@Z`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b4e0`

## callees

- `0x18000b4a0`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetTrustLevel(
        __int64 a1,
        int *a2)
{
  __int64 v2; // rax
  int v4; // eax

  v2 = *(_QWORD *)(a1 + 80);
  if ( v2 )
    v4 = (*(__int64 (**)(void))(v2 + 16))();
  else
    v4 = 2;
  *a2 = v4;
  return 0;
}

```

## disassembly

```asm
0x18000b4a0  push    rbx
0x18000b4a2  sub     rsp, 20h
0x18000b4a6  mov     rax, [rcx+50h]
0x18000b4aa  mov     rbx, rdx
0x18000b4ad  test    rax, rax
0x18000b4b0  jz      short loc_18000B4BD
0x18000b4b2  mov     rax, [rax+10h]
0x18000b4b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4bb  jmp     short loc_18000B4C2
0x18000b4bd  mov     eax, 2
0x18000b4c2  mov     [rbx], eax
0x18000b4c4  xor     eax, eax
0x18000b4c6  add     rsp, 20h
0x18000b4ca  pop     rbx
0x18000b4cb  retn
```
