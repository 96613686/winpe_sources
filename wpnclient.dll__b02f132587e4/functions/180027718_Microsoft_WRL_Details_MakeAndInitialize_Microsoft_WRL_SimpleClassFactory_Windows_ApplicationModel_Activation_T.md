# Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<Windows::ApplicationModel::Activation::ToastActivationPlugin,0>,Microsoft::WRL::SimpleClassFactory<Windows::ApplicationModel::Activation::ToastActivationPlugin,0>,>(Microsoft::WRL::SimpleClassFactory<Windows::ApplicationModel::Activation::ToastActivationPlugin,0> * *)

- ea: `0x180027718`
- end: `0x1800277a8`
- name: `??$MakeAndInitialize@V?$SimpleClassFactory@VToastActivationPlugin@Activation@ApplicationModel@Windows@@$0A@@WRL@Microsoft@@V123@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$SimpleClassFactory@VToastActivationPlugin@Activation@ApplicationModel@Windows@@$0A@@12@@Z`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800274f0`

## callees

- `0x18001bf84`
- `0x180020350`
- `0x180027718`
- `0x180027ba0`
- `0x180032010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<Windows::ApplicationModel::Activation::ToastActivationPlugin,0>,Microsoft::WRL::SimpleClassFactory<Windows::ApplicationModel::Activation::ToastActivationPlugin,0>,>(
        __int64 *a1)
{
  void *v2; // rax
  unsigned int v3; // ebx
  __int64 v4; // rax
  __int64 v5; // rbx
  void *v7; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v2 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
  v7 = v2;
  if ( v2 )
  {
    v4 = Microsoft::WRL::SimpleClassFactory<Windows::ApplicationModel::Activation::ToastActivationPlugin,0>::SimpleClassFactory<Windows::ApplicationModel::Activation::ToastActivationPlugin,0>(v2);
    v5 = v4;
    v7 = 0;
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
    *a1 = v5;
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    v3 = 0;
  }
  else
  {
    v3 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Internal::Notifications::CToastActivator_AppLaunch>::~MakeAllocator<Windows::Internal::Notifications::CToastActivator_AppLaunch>(&v7);
  return v3;
}

```

## disassembly

```asm
0x180027718  mov     [rsp+arg_8], rbx
0x18002771d  push    rdi
0x18002771e  sub     rsp, 20h
0x180027722  mov     rdi, rcx
0x180027725  mov     qword ptr [rcx], 0
0x18002772c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180027733  mov     ecx, 18h; unsigned __int64
0x180027738  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002773d  mov     [rsp+28h+arg_0], rax
0x180027742  test    rax, rax
0x180027745  jnz     short loc_18002774E
0x180027747  mov     ebx, 8007000Eh
0x18002774c  jmp     short loc_180027791
0x18002774e  mov     rcx, rax
0x180027751  call    ??0?$SimpleClassFactory@VToastActivationPlugin@Activation@ApplicationModel@Windows@@$0A@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::SimpleClassFactory<Windows::ApplicationModel::Activation::ToastActivationPlugin,0>::SimpleClassFactory<Windows::ApplicationModel::Activation::ToastActivationPlugin,0>(void)
0x180027756  mov     rbx, rax
0x180027759  mov     [rsp+28h+arg_0], 0
0x180027762  test    rax, rax
0x180027765  jz      short loc_180027777
0x180027767  mov     rcx, [rax]
0x18002776a  mov     rax, [rcx+8]
0x18002776e  mov     rcx, rbx
0x180027771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027776  nop
0x180027777  mov     [rdi], rbx
0x18002777a  test    rbx, rbx
0x18002777d  jz      short loc_18002778F
0x18002777f  mov     rax, [rbx]
0x180027782  mov     rcx, rbx
0x180027785  mov     rax, [rax+10h]
0x180027789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002778e  nop
0x18002778f  xor     ebx, ebx
0x180027791  lea     rcx, [rsp+28h+arg_0]
0x180027796  call    ??1?$MakeAllocator@VCToastActivator_AppLaunch@Notifications@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::Notifications::CToastActivator_AppLaunch>::~MakeAllocator<Windows::Internal::Notifications::CToastActivator_AppLaunch>(void)
0x18002779b  mov     eax, ebx
0x18002779d  mov     rbx, [rsp+28h+arg_8]
0x1800277a2  add     rsp, 20h
0x1800277a6  pop     rdi
0x1800277a7  retn
```
