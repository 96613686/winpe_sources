# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)

- ea: `0x18000b470`
- end: `0x18000b4d9`
- name: `?Release@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAKXZ`
- size: `105`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b4e0`
- `0x18000b4f0`
- `0x18000b500`

## callees

- `0x18000b308`
- `0x18000b470`
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
0x18000b470  mov     [rsp+arg_0], rbx
0x18000b475  push    rdi
0x18000b476  sub     rsp, 20h
0x18000b47a  mov     r10, rcx
0x18000b47d  call    ?InternalRelease@?$RuntimeClassImpl@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@$00$0A@UIActivationFactory@@U?$Implements@VFtmBase@WRL@Microsoft@@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::InternalRelease(void)
0x18000b482  mov     ebx, [rcx+58h]
0x18000b485  mov     edi, eax
0x18000b487  and     ebx, 4
0x18000b48a  test    eax, eax
0x18000b48c  jnz     short loc_18000B4AB
0x18000b48e  test    rcx, rcx
0x18000b491  jz      short loc_18000B4A5
0x18000b493  mov     rcx, [rcx]
0x18000b496  lea     edx, [rdi+1]
0x18000b499  mov     rax, [rcx+38h]
0x18000b49d  mov     rcx, r10
0x18000b4a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4a5  test    ebx, ebx
0x18000b4a7  jz      short loc_18000B4CC
0x18000b4a9  jmp     short loc_18000B4B4
0x18000b4ab  test    ebx, ebx
0x18000b4ad  jnz     short loc_18000B4CC
0x18000b4af  cmp     edi, 1
0x18000b4b2  jnz     short loc_18000B4CC
0x18000b4b4  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000b4bb  test    rcx, rcx
0x18000b4be  jz      short loc_18000B4CC
0x18000b4c0  mov     rax, [rcx]
0x18000b4c3  mov     rax, [rax+10h]
0x18000b4c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4cc  mov     rbx, [rsp+28h+arg_0]
0x18000b4d1  mov     eax, edi
0x18000b4d3  add     rsp, 20h
0x18000b4d7  pop     rdi
0x18000b4d8  retn
```
