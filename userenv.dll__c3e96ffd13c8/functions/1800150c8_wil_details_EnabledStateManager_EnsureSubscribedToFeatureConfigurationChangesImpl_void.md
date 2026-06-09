# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x1800150c8`
- end: `0x18001515c`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800150a0`

## callees

- `0x18000d158`
- `0x1800150c8`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800150e2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800150e2`

## pseudocode

```c
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
0x1800150c8  mov     [rsp+arg_8], rbx
0x1800150cd  push    rdi
0x1800150ce  sub     rsp, 20h
0x1800150d2  mov     rdi, rcx
0x1800150d5  mov     eax, [rcx]
0x1800150d7  test    eax, eax
0x1800150d9  jz      short loc_18001514F
0x1800150db  lea     rbx, [rcx+8]
0x1800150df  mov     rcx, rbx; SRWLock
0x1800150e2  call    cs:__imp_AcquireSRWLockExclusive
0x1800150e8  mov     [rsp+28h+arg_0], rbx
0x1800150ed  lea     rbx, [rdi+60h]
0x1800150f1  cmp     qword ptr [rbx], 0
0x1800150f5  jz      short loc_1800150FD
0x1800150f7  mov     ebx, [rdi+1Ch]
0x1800150fa  nop
0x1800150fb  jmp     short loc_180015141
0x1800150fd  mov     qword ptr [rbx], 0
0x180015104  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18001510b  test    rax, rax
0x18001510e  jnz     short loc_18001511C
0x180015110  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180015117  test    rax, rax
0x18001511a  jz      short loc_18001512E
0x18001511c  mov     r8, rdi
0x18001511f  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180015126  mov     rcx, rbx
0x180015129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001512e  cmp     qword ptr [rbx], 0
0x180015132  jnz     short loc_180015138
0x180015134  xor     ebx, ebx
0x180015136  jmp     short loc_180015141
0x180015138  nop
0x180015139  mov     ebx, 1
0x18001513e  mov     [rdi+1Ch], ebx
0x180015141  lea     rcx, [rsp+28h+arg_0]
0x180015146  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001514b  mov     eax, ebx
0x18001514d  jmp     short loc_180015151
0x18001514f  xor     eax, eax
0x180015151  mov     rbx, [rsp+28h+arg_8]
0x180015156  add     rsp, 20h
0x18001515a  pop     rdi
0x18001515b  retn
```
