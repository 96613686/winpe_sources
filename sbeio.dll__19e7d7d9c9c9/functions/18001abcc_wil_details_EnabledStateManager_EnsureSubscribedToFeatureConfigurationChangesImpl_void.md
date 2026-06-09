# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x18001abcc`
- end: `0x18001ac60`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `unsigned int __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001aba4`

## callees

- `0x180015800`
- `0x18001abcc`
- `0x18002b010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18001abe6`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001abe6`

## pseudocode

```c
__int64 __fastcall wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(
        RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // rbx
  RTL_SRWLOCK *v3; // rbx
  unsigned int Ptr_high; // ebx
  void (__fastcall *v5)(RTL_SRWLOCK *, __int64 (__fastcall *)(void *), RTL_SRWLOCK *); // rax
  RTL_SRWLOCK *v7; // [rsp+20h] [rbp-18h] BYREF

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
    v5 = (void (__fastcall *)(RTL_SRWLOCK *, __int64 (__fastcall *)(void *), RTL_SRWLOCK *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
    v3->Ptr = 0;
    if ( v5
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
0x18001abcc  mov     [rsp+arg_8], rbx
0x18001abd1  push    rdi
0x18001abd2  sub     rsp, 30h
0x18001abd6  mov     eax, [rcx]
0x18001abd8  mov     rdi, rcx
0x18001abdb  test    eax, eax
0x18001abdd  jz      short loc_18001AC53
0x18001abdf  lea     rbx, [rcx+8]
0x18001abe3  mov     rcx, rbx; SRWLock
0x18001abe6  call    cs:__imp_AcquireSRWLockExclusive
0x18001abec  mov     [rsp+38h+var_18], rbx
0x18001abf1  lea     rbx, [rdi+60h]
0x18001abf5  cmp     qword ptr [rbx], 0
0x18001abf9  jz      short loc_18001AC01
0x18001abfb  mov     ebx, [rdi+1Ch]
0x18001abfe  nop
0x18001abff  jmp     short loc_18001AC45
0x18001ac01  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18001ac08  mov     qword ptr [rbx], 0
0x18001ac0f  test    rax, rax
0x18001ac12  jnz     short loc_18001AC20
0x18001ac14  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18001ac1b  test    rax, rax
0x18001ac1e  jz      short loc_18001AC32
0x18001ac20  mov     r8, rdi
0x18001ac23  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18001ac2a  mov     rcx, rbx
0x18001ac2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac32  cmp     qword ptr [rbx], 0
0x18001ac36  jnz     short loc_18001AC3C
0x18001ac38  xor     ebx, ebx
0x18001ac3a  jmp     short loc_18001AC45
0x18001ac3c  mov     ebx, 1
0x18001ac41  nop
0x18001ac42  mov     [rdi+1Ch], ebx
0x18001ac45  lea     rcx, [rsp+38h+var_18]
0x18001ac4a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001ac4f  mov     eax, ebx
0x18001ac51  jmp     short loc_18001AC55
0x18001ac53  xor     eax, eax
0x18001ac55  mov     rbx, [rsp+38h+arg_8]
0x18001ac5a  add     rsp, 30h
0x18001ac5e  pop     rdi
0x18001ac5f  retn
```
