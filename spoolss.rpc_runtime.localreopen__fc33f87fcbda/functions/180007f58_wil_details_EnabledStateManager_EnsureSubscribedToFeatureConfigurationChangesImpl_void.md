# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x180007f58`
- end: `0x180007ff3`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `155`
- prototype: `unsigned int __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180007f30`

## callees

- `0x1800047ac`
- `0x180007f58`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007f72`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007f72`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(
        RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // rbx
  RTL_SRWLOCK *v3; // rbx
  unsigned int Ptr_high; // ebx
  void (__fastcall *v5)(RTL_SRWLOCK *, __int64 (__fastcall *)(void *), RTL_SRWLOCK *); // rax
  RTL_SRWLOCK *v7; // [rsp+30h] [rbp+8h] BYREF

  if ( !LODWORD(this->Ptr) )
    return 0;
  v2 = this + 1;
  AcquireSRWLockExclusive(this + 1);
  v7 = v2;
  v3 = this + 4;
  if ( this[4].Ptr )
  {
    Ptr_high = HIDWORD(this[3].Ptr);
  }
  else
  {
    v3->Ptr = 0;
    v5 = (void (__fastcall *)(RTL_SRWLOCK *, __int64 (__fastcall *)(void *), RTL_SRWLOCK *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
    if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
      || (v5 = (void (__fastcall *)(RTL_SRWLOCK *, __int64 (__fastcall *)(void *), RTL_SRWLOCK *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
    {
      v5(this + 4, _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_, this);
    }
    if ( v3->Ptr )
    {
      Ptr_high = 1;
      HIDWORD(this[3].Ptr) = 1;
    }
    else
    {
      Ptr_high = 0;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v7);
  return Ptr_high;
}

```

## disassembly

```asm
0x180007f58  mov     [rsp+arg_8], rbx
0x180007f5d  push    rdi
0x180007f5e  sub     rsp, 20h
0x180007f62  mov     rdi, rcx
0x180007f65  mov     eax, [rcx]
0x180007f67  test    eax, eax
0x180007f69  jz      short loc_180007FE5
0x180007f6b  lea     rbx, [rcx+8]
0x180007f6f  mov     rcx, rbx; SRWLock
0x180007f72  call    cs:__imp_AcquireSRWLockExclusive
0x180007f79  nop     dword ptr [rax+rax+00h]
0x180007f7e  mov     [rsp+28h+arg_0], rbx
0x180007f83  lea     rbx, [rdi+20h]
0x180007f87  cmp     qword ptr [rbx], 0
0x180007f8b  jz      short loc_180007F93
0x180007f8d  mov     ebx, [rdi+1Ch]
0x180007f90  nop
0x180007f91  jmp     short loc_180007FD7
0x180007f93  mov     qword ptr [rbx], 0
0x180007f9a  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180007fa1  test    rax, rax
0x180007fa4  jnz     short loc_180007FB2
0x180007fa6  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180007fad  test    rax, rax
0x180007fb0  jz      short loc_180007FC4
0x180007fb2  mov     r8, rdi
0x180007fb5  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180007fbc  mov     rcx, rbx
0x180007fbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fc4  cmp     qword ptr [rbx], 0
0x180007fc8  jnz     short loc_180007FCE
0x180007fca  xor     ebx, ebx
0x180007fcc  jmp     short loc_180007FD7
0x180007fce  nop
0x180007fcf  mov     ebx, 1
0x180007fd4  mov     [rdi+1Ch], ebx
0x180007fd7  lea     rcx, [rsp+28h+arg_0]
0x180007fdc  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180007fe1  mov     eax, ebx
0x180007fe3  jmp     short loc_180007FE7
0x180007fe5  xor     eax, eax
0x180007fe7  mov     rbx, [rsp+28h+arg_8]
0x180007fec  add     rsp, 20h
0x180007ff0  pop     rdi
0x180007ff1  retn
```
