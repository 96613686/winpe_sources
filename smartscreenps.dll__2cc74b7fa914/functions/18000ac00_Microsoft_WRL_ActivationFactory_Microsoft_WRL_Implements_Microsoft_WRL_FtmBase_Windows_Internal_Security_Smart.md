# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`scalar deleting destructor'(uint)

- ea: `0x18000ac00`
- end: `0x18000ac3f`
- name: `??_G?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `63`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001960`
- `0x18000871c`
- `0x18000ac00`

## pseudocode

```c
void *__fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`scalar deleting destructor'(
        void *a1,
        char a2)
{
  *((_DWORD *)a1 + 17) = -1073741823;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)a1 + 4);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18000ac00  mov     [rsp+arg_0], rbx
0x18000ac05  push    rdi
0x18000ac06  sub     rsp, 20h
0x18000ac0a  mov     rdi, rcx
0x18000ac0d  mov     dword ptr [rcx+44h], 0C0000001h
0x18000ac14  add     rcx, 20h ; ' '
0x18000ac18  mov     ebx, edx
0x18000ac1a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000ac1f  test    bl, 1
0x18000ac22  jz      short loc_18000AC31
0x18000ac24  mov     edx, 60h ; '`'; unsigned __int64
0x18000ac29  mov     rcx, rdi; void *
0x18000ac2c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ac31  mov     rbx, [rsp+28h+arg_0]
0x18000ac36  mov     rax, rdi
0x18000ac39  add     rsp, 20h
0x18000ac3d  pop     rdi
0x18000ac3e  retn
```
