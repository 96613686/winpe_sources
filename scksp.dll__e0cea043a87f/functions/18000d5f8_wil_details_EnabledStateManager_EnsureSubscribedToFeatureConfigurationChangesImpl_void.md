# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x18000d5f8`
- end: `0x18000d68c`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `unsigned int __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000d5d0`

## callees

- `0x18000cb5c`
- `0x18000d5f8`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d612`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d612`

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
  v3 = this + 12;
  if ( this[12].Ptr )
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
      v5(this + 12, _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_, this);
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
0x18000d5f8  mov     [rsp+arg_8], rbx
0x18000d5fd  push    rdi
0x18000d5fe  sub     rsp, 20h
0x18000d602  mov     rdi, rcx
0x18000d605  mov     eax, [rcx]
0x18000d607  test    eax, eax
0x18000d609  jz      short loc_18000D67F
0x18000d60b  lea     rbx, [rcx+8]
0x18000d60f  mov     rcx, rbx; SRWLock
0x18000d612  call    cs:__imp_AcquireSRWLockExclusive
0x18000d618  mov     [rsp+28h+arg_0], rbx
0x18000d61d  lea     rbx, [rdi+60h]
0x18000d621  cmp     qword ptr [rbx], 0
0x18000d625  jz      short loc_18000D62D
0x18000d627  mov     ebx, [rdi+1Ch]
0x18000d62a  nop
0x18000d62b  jmp     short loc_18000D671
0x18000d62d  mov     qword ptr [rbx], 0
0x18000d634  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000d63b  test    rax, rax
0x18000d63e  jnz     short loc_18000D64C
0x18000d640  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000d647  test    rax, rax
0x18000d64a  jz      short loc_18000D65E
0x18000d64c  mov     r8, rdi
0x18000d64f  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18000d656  mov     rcx, rbx
0x18000d659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d65e  cmp     qword ptr [rbx], 0
0x18000d662  jnz     short loc_18000D668
0x18000d664  xor     ebx, ebx
0x18000d666  jmp     short loc_18000D671
0x18000d668  nop
0x18000d669  mov     ebx, 1
0x18000d66e  mov     [rdi+1Ch], ebx
0x18000d671  lea     rcx, [rsp+28h+arg_0]
0x18000d676  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000d67b  mov     eax, ebx
0x18000d67d  jmp     short loc_18000D681
0x18000d67f  xor     eax, eax
0x18000d681  mov     rbx, [rsp+28h+arg_8]
0x18000d686  add     rsp, 20h
0x18000d68a  pop     rdi
0x18000d68b  retn
```
