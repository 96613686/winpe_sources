# Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_7b4fabe6bb32ef3f000e12ab001b652f_____lambda_7b4fabe6bb32ef3f000e12ab001b652f___

- ea: `0x180025bfc`
- end: `0x180025cb2`
- name: `Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_7b4fabe6bb32ef3f000e12ab001b652f_____lambda_7b4fabe6bb32ef3f000e12ab001b652f___`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800186f0`

## callees

- `0x1800132a4`
- `0x180015150`
- `0x180020350`
- `0x180025bfc`
- `0x180025e50`
- `0x180032010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_7b4fabe6bb32ef3f000e12ab001b652f_____lambda_7b4fabe6bb32ef3f000e12ab001b652f___(
        _QWORD *a1,
        __int64 a2)
{
  _OWORD *v4; // rax
  _OWORD *v5; // rbx
  void *v7; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v4 = operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
  v5 = v4;
  v7 = v4;
  if ( v4 )
  {
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IActivationBrokerPlugin>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IActivationBrokerPlugin>(v4);
    *(_QWORD *)v5 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v5[1] = *(_OWORD *)a2;
    *((_QWORD *)v5 + 4) = *(_QWORD *)(a2 + 16);
    *(_QWORD *)v5 = &off_180034728;
    if ( *a1 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
    *a1 = v5;
    v7 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_7b4fabe6bb32ef3f000e12ab001b652f_____::_MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_7b4fabe6bb32ef3f000e12ab001b652f_____(&v7);
  return a1;
}

```

## disassembly

```asm
0x180025bfc  mov     [rsp+arg_8], rbx
0x180025c01  mov     [rsp+arg_10], rsi
0x180025c06  push    rdi
0x180025c07  sub     rsp, 20h
0x180025c0b  mov     rsi, rdx
0x180025c0e  mov     rdi, rcx
0x180025c11  mov     qword ptr [rcx], 0
0x180025c18  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180025c1f  mov     ecx, 28h ; '('; unsigned __int64
0x180025c24  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180025c29  mov     rbx, rax
0x180025c2c  mov     [rsp+28h+arg_0], rax
0x180025c31  test    rax, rax
0x180025c34  jz      short loc_180025C95
0x180025c36  mov     rcx, rax
0x180025c39  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIActivationBrokerPlugin@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IActivationBrokerPlugin>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IActivationBrokerPlugin>(void)
0x180025c3e  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::`vftable'
0x180025c45  mov     [rbx], rcx
0x180025c48  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180025c4f  test    rcx, rcx
0x180025c52  jz      short loc_180025C61
0x180025c54  mov     rax, [rcx]
0x180025c57  mov     rax, [rax+8]
0x180025c5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c60  nop
0x180025c61  movups  xmm0, xmmword ptr [rsi]
0x180025c64  movups  xmmword ptr [rbx+10h], xmm0
0x180025c68  movsd   xmm1, qword ptr [rsi+10h]
0x180025c6d  movsd   qword ptr [rbx+20h], xmm1
0x180025c72  lea     rax, off_180034728
0x180025c79  mov     [rbx], rax
0x180025c7c  mov     rcx, [rdi]
0x180025c7f  test    rcx, rcx
0x180025c82  jz      short loc_180025C89
0x180025c84  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180025c89  mov     [rdi], rbx
0x180025c8c  mov     [rsp+28h+arg_0], 0
0x180025c95  lea     rcx, [rsp+28h+arg_0]
0x180025c9a  call    Microsoft__WRL__Details__MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_7b4fabe6bb32ef3f000e12ab001b652f________MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_7b4fabe6bb32ef3f000e12ab001b652f_____
0x180025c9f  mov     rax, rdi
0x180025ca2  mov     rbx, [rsp+28h+arg_8]
0x180025ca7  mov     rsi, [rsp+28h+arg_10]
0x180025cac  add     rsp, 20h
0x180025cb0  pop     rdi
0x180025cb1  retn
```
