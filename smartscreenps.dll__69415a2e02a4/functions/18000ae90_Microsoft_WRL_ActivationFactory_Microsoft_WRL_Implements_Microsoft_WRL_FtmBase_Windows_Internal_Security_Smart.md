# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`scalar deleting destructor'(uint)

- ea: `0x18000ae90`
- end: `0x18000aed0`
- name: `??_G?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `64`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001960`
- `0x180008828`
- `0x18000ae90`

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
0x18000ae90  mov     [rsp+arg_0], rbx
0x18000ae95  push    rdi
0x18000ae96  sub     rsp, 20h
0x18000ae9a  mov     rdi, rcx
0x18000ae9d  mov     dword ptr [rcx+44h], 0C0000001h
0x18000aea4  add     rcx, 20h ; ' '
0x18000aea8  mov     ebx, edx
0x18000aeaa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000aeaf  test    bl, 1
0x18000aeb2  jz      short loc_18000AEC1
0x18000aeb4  mov     edx, 60h ; '`'; unsigned __int64
0x18000aeb9  mov     rcx, rdi; void *
0x18000aebc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000aec1  mov     rbx, [rsp+28h+arg_0]
0x18000aec6  mov     rax, rdi
0x18000aec9  add     rsp, 20h
0x18000aecd  pop     rdi
0x18000aece  retn
```
