# Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<std::function<long (void)> &>,std::function<long (void)> &>(std::function<long (void)> &)

- ea: `0x180012db8`
- end: `0x180012e79`
- name: `??$Make@V?$CTaskWrapper@AEAV?$function@$$A6AJXZ@std@@@ComTaskPool@Internal@Windows@@AEAV?$function@$$A6AJXZ@std@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@AEAV?$function@$$A6AJXZ@std@@@ComTaskPool@Internal@Windows@@@12@AEAV?$function@$$A6AJXZ@std@@@Z`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018f90`

## callees

- `0x18000872c`
- `0x180012db8`
- `0x180014308`
- `0x180014334`
- `0x180014b60`
- `0x180018730`
- `0x180029010`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<std::function<long (void)> &>,std::function<long (void)> &>(
        _QWORD *a1,
        __int64 a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  _QWORD *v7; // [rsp+60h] [rbp+18h] BYREF
  _QWORD *v8; // [rsp+68h] [rbp+20h]

  *a1 = 0;
  v4 = operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  v7 = v4;
  v8 = v4;
  if ( v4 )
  {
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>(v4);
    *v5 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    std::function<long (void)>::function<long (void)>(v5 + 3, a2);
    *v5 = &Windows::Internal::ComTaskPool::CTaskWrapper<std::function<long (void)> &>::`vftable';
    if ( *a1 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(*a1);
    *a1 = v5;
    v7 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>::~MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>(&v7);
  return a1;
}

```

## disassembly

```asm
0x180012db8  mov     [rsp+arg_0], rcx
0x180012dbd  push    rbx
0x180012dbe  push    rsi
0x180012dbf  push    rdi
0x180012dc0  sub     rsp, 30h
0x180012dc4  mov     rsi, rdx
0x180012dc7  mov     rdi, rcx
0x180012dca  mov     [rsp+48h+var_28], 0
0x180012dd2  mov     qword ptr [rcx], 0
0x180012dd9  mov     [rsp+48h+var_28], 1
0x180012de1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012de8  mov     ecx, 58h ; 'X'; unsigned __int64
0x180012ded  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180012df2  mov     rbx, rax
0x180012df5  mov     [rsp+48h+arg_10], rax
0x180012dfa  mov     [rsp+48h+arg_18], rax
0x180012dff  test    rax, rax
0x180012e02  jz      short loc_180012E63
0x180012e04  mov     [rsp+48h+var_20], rax
0x180012e09  mov     rcx, rax
0x180012e0c  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>(void)
0x180012e11  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::`vftable'
0x180012e18  mov     [rbx], rcx
0x180012e1b  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180012e22  test    rcx, rcx
0x180012e25  jz      short loc_180012E34
0x180012e27  mov     rax, [rcx]
0x180012e2a  mov     rax, [rax+8]
0x180012e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e33  nop
0x180012e34  lea     rcx, [rbx+18h]
0x180012e38  mov     rdx, rsi
0x180012e3b  call    ??0?$function@$$A6AJXZ@std@@QEAA@AEBV01@@Z; std::function<long (void)>::function<long (void)>(std::function<long (void)> const &)
0x180012e40  lea     rax, ??_7?$CTaskWrapper@AEAV?$function@$$A6AJXZ@std@@@ComTaskPool@Internal@Windows@@6B@; const Windows::Internal::ComTaskPool::CTaskWrapper<std::function<long (void)> &>::`vftable'
0x180012e47  mov     [rbx], rax
0x180012e4a  mov     rcx, [rdi]
0x180012e4d  test    rcx, rcx
0x180012e50  jz      short loc_180012E57
0x180012e52  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180012e57  mov     [rdi], rbx
0x180012e5a  mov     [rsp+48h+arg_10], 0
0x180012e63  lea     rcx, [rsp+48h+arg_10]
0x180012e68  call    ??1?$MakeAllocator@VWeakReferenceImpl@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>::~MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>(void)
0x180012e6d  mov     rax, rdi
0x180012e70  add     rsp, 30h
0x180012e74  pop     rdi
0x180012e75  pop     rsi
0x180012e76  pop     rbx
0x180012e77  retn
```
