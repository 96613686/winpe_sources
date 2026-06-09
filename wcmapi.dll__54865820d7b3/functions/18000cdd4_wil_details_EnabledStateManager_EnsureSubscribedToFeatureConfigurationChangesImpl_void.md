# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x18000cdd4`
- end: `0x18000ce6f`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `155`
- prototype: `unsigned int __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000cdac`

## callees

- `0x18000bf04`
- `0x18000cdd4`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cdee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cdee`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(
        RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // rbx
  RTL_SRWLOCK *v3; // rbx
  unsigned int Ptr_high; // ebx
  void (__fastcall *v5)(RTL_SRWLOCK *, __int64 (__fastcall *)(), RTL_SRWLOCK *); // rax
  RTL_SRWLOCK *v7; // [rsp+20h] [rbp-18h] BYREF

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
    v5 = (void (__fastcall *)(RTL_SRWLOCK *, __int64 (__fastcall *)(), RTL_SRWLOCK *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
    if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
      || (v5 = (void (__fastcall *)(RTL_SRWLOCK *, __int64 (__fastcall *)(), RTL_SRWLOCK *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
    {
      v5(
        this + 4,
        `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl'::`5'::_lambda_1_::_lambda_invoker_cdecl_,
        this);
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
0x18000cdd4  mov     [rsp+arg_8], rbx
0x18000cdd9  push    rdi
0x18000cdda  sub     rsp, 30h
0x18000cdde  mov     rdi, rcx
0x18000cde1  mov     eax, [rcx]
0x18000cde3  test    eax, eax
0x18000cde5  jz      short loc_18000CE61
0x18000cde7  lea     rbx, [rcx+8]
0x18000cdeb  mov     rcx, rbx; SRWLock
0x18000cdee  call    cs:__imp_AcquireSRWLockExclusive
0x18000cdf5  nop     dword ptr [rax+rax+00h]
0x18000cdfa  mov     [rsp+38h+var_18], rbx
0x18000cdff  lea     rbx, [rdi+20h]
0x18000ce03  cmp     qword ptr [rbx], 0
0x18000ce07  jz      short loc_18000CE0F
0x18000ce09  mov     ebx, [rdi+1Ch]
0x18000ce0c  nop
0x18000ce0d  jmp     short loc_18000CE53
0x18000ce0f  mov     qword ptr [rbx], 0
0x18000ce16  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000ce1d  test    rax, rax
0x18000ce20  jnz     short loc_18000CE2E
0x18000ce22  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000ce29  test    rax, rax
0x18000ce2c  jz      short loc_18000CE40
0x18000ce2e  mov     r8, rdi
0x18000ce31  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ@SA@PEAX@Z; `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x18000ce38  mov     rcx, rbx
0x18000ce3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce40  cmp     qword ptr [rbx], 0
0x18000ce44  jnz     short loc_18000CE4A
0x18000ce46  xor     ebx, ebx
0x18000ce48  jmp     short loc_18000CE53
0x18000ce4a  nop
0x18000ce4b  mov     ebx, 1
0x18000ce50  mov     [rdi+1Ch], ebx
0x18000ce53  lea     rcx, [rsp+38h+var_18]
0x18000ce58  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000ce5d  mov     eax, ebx
0x18000ce5f  jmp     short loc_18000CE63
0x18000ce61  xor     eax, eax
0x18000ce63  mov     rbx, [rsp+38h+arg_8]
0x18000ce68  add     rsp, 30h
0x18000ce6c  pop     rdi
0x18000ce6d  retn
```
