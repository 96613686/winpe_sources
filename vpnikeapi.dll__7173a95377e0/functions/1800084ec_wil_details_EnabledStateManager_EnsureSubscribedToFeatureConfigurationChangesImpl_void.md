# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x1800084ec`
- end: `0x180008580`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800084c4`

## callees

- `0x180007b44`
- `0x1800084ec`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008506`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008506`

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
0x1800084ec  mov     [rsp+arg_8], rbx
0x1800084f1  push    rdi
0x1800084f2  sub     rsp, 20h
0x1800084f6  mov     eax, [rcx]
0x1800084f8  mov     rdi, rcx
0x1800084fb  test    eax, eax
0x1800084fd  jz      short loc_180008573
0x1800084ff  lea     rbx, [rcx+8]
0x180008503  mov     rcx, rbx; SRWLock
0x180008506  call    cs:__imp_AcquireSRWLockExclusive
0x18000850c  mov     [rsp+28h+arg_0], rbx
0x180008511  lea     rbx, [rdi+60h]
0x180008515  cmp     qword ptr [rbx], 0
0x180008519  jz      short loc_180008521
0x18000851b  mov     ebx, [rdi+1Ch]
0x18000851e  nop
0x18000851f  jmp     short loc_180008565
0x180008521  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180008528  mov     qword ptr [rbx], 0
0x18000852f  test    rax, rax
0x180008532  jnz     short loc_180008540
0x180008534  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000853b  test    rax, rax
0x18000853e  jz      short loc_180008552
0x180008540  mov     r8, rdi
0x180008543  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18000854a  mov     rcx, rbx
0x18000854d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008552  cmp     qword ptr [rbx], 0
0x180008556  jnz     short loc_18000855C
0x180008558  xor     ebx, ebx
0x18000855a  jmp     short loc_180008565
0x18000855c  mov     ebx, 1
0x180008561  nop
0x180008562  mov     [rdi+1Ch], ebx
0x180008565  lea     rcx, [rsp+28h+arg_0]
0x18000856a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000856f  mov     eax, ebx
0x180008571  jmp     short loc_180008575
0x180008573  xor     eax, eax
0x180008575  mov     rbx, [rsp+28h+arg_8]
0x18000857a  add     rsp, 20h
0x18000857e  pop     rdi
0x18000857f  retn
```
