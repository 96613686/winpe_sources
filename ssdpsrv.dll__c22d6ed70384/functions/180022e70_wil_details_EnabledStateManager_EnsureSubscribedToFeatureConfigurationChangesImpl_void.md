# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x180022e70`
- end: `0x180022f04`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800291c8`

## callees

- `0x180022e70`
- `0x1800232a8`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022e8a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022e8a`

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
0x180022e70  mov     [rsp+arg_8], rbx
0x180022e75  push    rdi
0x180022e76  sub     rsp, 20h
0x180022e7a  mov     eax, [rcx]
0x180022e7c  mov     rdi, rcx
0x180022e7f  test    eax, eax
0x180022e81  jz      short loc_180022EF7
0x180022e83  lea     rbx, [rcx+8]
0x180022e87  mov     rcx, rbx; SRWLock
0x180022e8a  call    cs:__imp_AcquireSRWLockExclusive
0x180022e90  mov     [rsp+28h+arg_0], rbx
0x180022e95  lea     rbx, [rdi+60h]
0x180022e99  cmp     qword ptr [rbx], 0
0x180022e9d  jz      short loc_180022EA5
0x180022e9f  mov     ebx, [rdi+1Ch]
0x180022ea2  nop
0x180022ea3  jmp     short loc_180022EE9
0x180022ea5  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180022eac  mov     qword ptr [rbx], 0
0x180022eb3  test    rax, rax
0x180022eb6  jnz     short loc_180022EC4
0x180022eb8  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180022ebf  test    rax, rax
0x180022ec2  jz      short loc_180022ED6
0x180022ec4  mov     r8, rdi
0x180022ec7  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180022ece  mov     rcx, rbx
0x180022ed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ed6  cmp     qword ptr [rbx], 0
0x180022eda  jnz     short loc_180022EE0
0x180022edc  xor     ebx, ebx
0x180022ede  jmp     short loc_180022EE9
0x180022ee0  mov     ebx, 1
0x180022ee5  nop
0x180022ee6  mov     [rdi+1Ch], ebx
0x180022ee9  lea     rcx, [rsp+28h+arg_0]
0x180022eee  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180022ef3  mov     eax, ebx
0x180022ef5  jmp     short loc_180022EF9
0x180022ef7  xor     eax, eax
0x180022ef9  mov     rbx, [rsp+28h+arg_8]
0x180022efe  add     rsp, 20h
0x180022f02  pop     rdi
0x180022f03  retn
```
