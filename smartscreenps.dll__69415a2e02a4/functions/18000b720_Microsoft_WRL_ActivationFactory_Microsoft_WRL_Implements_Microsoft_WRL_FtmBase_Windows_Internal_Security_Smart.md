# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)

- ea: `0x18000b720`
- end: `0x18000b78a`
- name: `?Release@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAKXZ`
- size: `106`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b790`
- `0x18000b7a0`
- `0x18000b7b0`

## callees

- `0x18000b5b8`
- `0x18000b720`
- `0x18000e010`

## pseudocode

```c
__int64 Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release()
{
  _DWORD *v0; // rcx
  unsigned int v1; // edi
  __int64 v2; // r10
  int v3; // ebx

  v1 = Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::InternalRelease();
  v3 = v0[22] & 4;
  if ( v1 )
  {
    if ( v3 || v1 != 1 )
      return v1;
    goto LABEL_8;
  }
  if ( v0 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v0 + 56LL))(v2, 1);
  if ( v3 )
  {
LABEL_8:
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v1;
}

```

## disassembly

```asm
0x18000b720  mov     [rsp+arg_0], rbx
0x18000b725  push    rdi
0x18000b726  sub     rsp, 20h
0x18000b72a  mov     r10, rcx
0x18000b72d  call    ?InternalRelease@?$RuntimeClassImpl@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@$00$0A@UIActivationFactory@@U?$Implements@VFtmBase@WRL@Microsoft@@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::InternalRelease(void)
0x18000b732  mov     ebx, [rcx+58h]
0x18000b735  mov     edi, eax
0x18000b737  and     ebx, 4
0x18000b73a  test    eax, eax
0x18000b73c  jnz     short loc_18000B75B
0x18000b73e  test    rcx, rcx
0x18000b741  jz      short loc_18000B755
0x18000b743  mov     rcx, [rcx]
0x18000b746  lea     edx, [rdi+1]
0x18000b749  mov     rax, [rcx+38h]
0x18000b74d  mov     rcx, r10
0x18000b750  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b755  test    ebx, ebx
0x18000b757  jz      short loc_18000B77C
0x18000b759  jmp     short loc_18000B764
0x18000b75b  test    ebx, ebx
0x18000b75d  jnz     short loc_18000B77C
0x18000b75f  cmp     edi, 1
0x18000b762  jnz     short loc_18000B77C
0x18000b764  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000b76b  test    rcx, rcx
0x18000b76e  jz      short loc_18000B77C
0x18000b770  mov     rax, [rcx]
0x18000b773  mov     rax, [rax+10h]
0x18000b777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b77c  mov     rbx, [rsp+28h+arg_0]
0x18000b781  mov     eax, edi
0x18000b783  add     rsp, 20h
0x18000b787  pop     rdi
0x18000b788  retn
```
