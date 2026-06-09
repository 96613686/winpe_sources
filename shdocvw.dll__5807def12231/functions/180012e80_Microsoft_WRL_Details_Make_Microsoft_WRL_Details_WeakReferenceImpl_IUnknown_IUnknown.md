# Microsoft::WRL::Details::Make<Microsoft::WRL::Details::WeakReferenceImpl,IUnknown * &>(IUnknown * &)

- ea: `0x180012e80`
- end: `0x180012f3a`
- name: `??$Make@VWeakReferenceImpl@Details@WRL@Microsoft@@AEAPEAUIUnknown@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VWeakReferenceImpl@Details@WRL@Microsoft@@@12@AEAPEAUIUnknown@@@Z`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016e90`

## callees

- `0x18000872c`
- `0x180012e80`
- `0x180014308`
- `0x180014b60`
- `0x180018730`
- `0x180029010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall Microsoft::WRL::Details::Make<Microsoft::WRL::Details::WeakReferenceImpl,IUnknown * &>(
        __int64 *a1,
        __int64 *a2)
{
  _DWORD *v4; // rax
  _DWORD *v5; // rbx
  __int64 v6; // rsi
  volatile int *v7; // rdx
  void *v9; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v4 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  v9 = v4;
  if ( v4 )
  {
    v6 = *a2;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>(v4);
    *(_QWORD *)v5 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWeakReference>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v5[4] = 0x3FFFFFFF;
    *(_QWORD *)v5 = &Microsoft::WRL::Details::WeakReferenceImpl::`vftable';
    *((_QWORD *)v5 + 3) = v6;
    v5[3] = 2;
    if ( *a1 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(
        *a1,
        v7);
    *a1 = (__int64)v5;
    v9 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>::~MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>(&v9);
  return a1;
}

```

## disassembly

```asm
0x180012e80  mov     [rsp+arg_8], rbx
0x180012e85  mov     [rsp+arg_10], rsi
0x180012e8a  push    rdi
0x180012e8b  sub     rsp, 20h
0x180012e8f  mov     rsi, rdx
0x180012e92  mov     rdi, rcx
0x180012e95  mov     qword ptr [rcx], 0
0x180012e9c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012ea3  mov     ecx, 20h ; ' '; unsigned __int64
0x180012ea8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180012ead  mov     rbx, rax
0x180012eb0  mov     [rsp+28h+arg_0], rax
0x180012eb5  test    rax, rax
0x180012eb8  jz      short loc_180012F1D
0x180012eba  mov     rsi, [rsi]
0x180012ebd  mov     rcx, rax
0x180012ec0  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>(void)
0x180012ec5  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIWeakReference@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWeakReference>::`vftable'
0x180012ecc  mov     [rbx], rcx
0x180012ecf  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180012ed6  test    rcx, rcx
0x180012ed9  jz      short loc_180012EE8
0x180012edb  mov     rax, [rcx]
0x180012ede  mov     rax, [rax+8]
0x180012ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ee7  nop
0x180012ee8  mov     dword ptr [rbx+10h], 3FFFFFFFh
0x180012eef  lea     rax, ??_7WeakReferenceImpl@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::WeakReferenceImpl::`vftable'
0x180012ef6  mov     [rbx], rax
0x180012ef9  mov     [rbx+18h], rsi
0x180012efd  mov     dword ptr [rbx+0Ch], 2
0x180012f04  mov     rcx, [rdi]
0x180012f07  test    rcx, rcx
0x180012f0a  jz      short loc_180012F11
0x180012f0c  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180012f11  mov     [rdi], rbx
0x180012f14  mov     [rsp+28h+arg_0], 0
0x180012f1d  lea     rcx, [rsp+28h+arg_0]
0x180012f22  call    ??1?$MakeAllocator@VWeakReferenceImpl@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>::~MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>(void)
0x180012f27  mov     rax, rdi
0x180012f2a  mov     rbx, [rsp+28h+arg_8]
0x180012f2f  mov     rsi, [rsp+28h+arg_10]
0x180012f34  add     rsp, 20h
0x180012f38  pop     rdi
0x180012f39  retn
```
