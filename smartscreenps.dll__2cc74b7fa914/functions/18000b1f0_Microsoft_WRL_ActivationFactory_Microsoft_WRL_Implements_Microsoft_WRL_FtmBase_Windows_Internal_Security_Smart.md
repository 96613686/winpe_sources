# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetTrustLevel(TrustLevel *)

- ea: `0x18000b1f0`
- end: `0x18000b21c`
- name: `?GetTrustLevel@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJPEAW4TrustLevel@@@Z`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b230`

## callees

- `0x18000b1f0`
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
0x18000b1f0  push    rbx
0x18000b1f2  sub     rsp, 20h
0x18000b1f6  mov     rax, [rcx+50h]
0x18000b1fa  mov     rbx, rdx
0x18000b1fd  test    rax, rax
0x18000b200  jz      short loc_18000B20D
0x18000b202  mov     rax, [rax+10h]
0x18000b206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b20b  jmp     short loc_18000B212
0x18000b20d  mov     eax, 2
0x18000b212  mov     [rbx], eax
0x18000b214  xor     eax, eax
0x18000b216  add     rsp, 20h
0x18000b21a  pop     rbx
0x18000b21b  retn
```
