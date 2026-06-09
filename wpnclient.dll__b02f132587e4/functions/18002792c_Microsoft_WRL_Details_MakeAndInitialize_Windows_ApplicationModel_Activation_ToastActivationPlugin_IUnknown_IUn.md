# Microsoft::WRL::Details::MakeAndInitialize<Windows::ApplicationModel::Activation::ToastActivationPlugin,IUnknown,>(IUnknown * *)

- ea: `0x18002792c`
- end: `0x1800279e5`
- name: `??$MakeAndInitialize@VToastActivationPlugin@Activation@ApplicationModel@Windows@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180028220`

## callees

- `0x1800132a4`
- `0x18001bf84`
- `0x180020350`
- `0x18002792c`
- `0x180032010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<Windows::ApplicationModel::Activation::ToastActivationPlugin,IUnknown,>(
        _QWORD *a1)
{
  void *v2; // rax
  void *v3; // rbx
  unsigned int v4; // edi
  void *v6; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v2 = operator new(0x10u, (const struct std::nothrow_t *)std::nothrow);
  v3 = v2;
  v6 = v2;
  if ( v2 )
  {
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IActivationBrokerPlugin>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IActivationBrokerPlugin>(v2);
    *(_QWORD *)v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IActivationBrokerPlugin>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v3 = &Windows::ApplicationModel::Activation::ToastActivationPlugin::`vftable';
    v6 = 0;
    v4 = ((__int64 (__fastcall *)(void *, GUID *, _QWORD *))Windows::ApplicationModel::Activation::ToastActivationPlugin::`vftable')(
           v3,
           &GUID_00000000_0000_0000_c000_000000000046,
           a1);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v3 + 16LL))(v3);
  }
  else
  {
    v4 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Internal::Notifications::CToastActivator_AppLaunch>::~MakeAllocator<Windows::Internal::Notifications::CToastActivator_AppLaunch>(&v6);
  return v4;
}

```

## disassembly

```asm
0x18002792c  mov     [rsp+arg_8], rbx
0x180027931  push    rdi
0x180027932  sub     rsp, 20h
0x180027936  mov     rdi, rcx
0x180027939  mov     qword ptr [rcx], 0
0x180027940  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180027947  mov     ecx, 10h; unsigned __int64
0x18002794c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180027951  mov     rbx, rax
0x180027954  mov     [rsp+28h+arg_0], rax
0x180027959  test    rax, rax
0x18002795c  jnz     short loc_180027965
0x18002795e  mov     edi, 8007000Eh
0x180027963  jmp     short loc_1800279CE
0x180027965  mov     rcx, rbx
0x180027968  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIActivationBrokerPlugin@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IActivationBrokerPlugin>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IActivationBrokerPlugin>(void)
0x18002796d  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIActivationBrokerPlugin@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IActivationBrokerPlugin>::`vftable'
0x180027974  mov     [rbx], rcx
0x180027977  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18002797e  test    rcx, rcx
0x180027981  jz      short loc_180027990
0x180027983  mov     rax, [rcx]
0x180027986  mov     rax, [rax+8]
0x18002798a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002798f  nop
0x180027990  lea     rax, ??_7ToastActivationPlugin@Activation@ApplicationModel@Windows@@6B@; const Windows::ApplicationModel::Activation::ToastActivationPlugin::`vftable'
0x180027997  mov     [rbx], rax
0x18002799a  mov     [rsp+28h+arg_0], 0
0x1800279a3  mov     r8, rdi
0x1800279a6  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800279ad  mov     rcx, rbx
0x1800279b0  mov     rax, cs:??_7ToastActivationPlugin@Activation@ApplicationModel@Windows@@6B@; const Windows::ApplicationModel::Activation::ToastActivationPlugin::`vftable'
0x1800279b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279bc  mov     edi, eax
0x1800279be  mov     rcx, [rbx]
0x1800279c1  mov     rax, [rcx+10h]
0x1800279c5  mov     rcx, rbx
0x1800279c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279cd  nop
0x1800279ce  lea     rcx, [rsp+28h+arg_0]
0x1800279d3  call    ??1?$MakeAllocator@VCToastActivator_AppLaunch@Notifications@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::Notifications::CToastActivator_AppLaunch>::~MakeAllocator<Windows::Internal::Notifications::CToastActivator_AppLaunch>(void)
0x1800279d8  mov     eax, edi
0x1800279da  mov     rbx, [rsp+28h+arg_8]
0x1800279df  add     rsp, 20h
0x1800279e3  pop     rdi
0x1800279e4  retn
```
