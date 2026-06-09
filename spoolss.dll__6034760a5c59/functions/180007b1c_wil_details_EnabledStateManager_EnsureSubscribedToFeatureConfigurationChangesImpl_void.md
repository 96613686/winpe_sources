# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x180007b1c`
- end: `0x180007bb0`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `unsigned int __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180007af4`

## callees

- `0x180004490`
- `0x180007b1c`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007b36`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007b36`

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
0x180007b1c  mov     [rsp+arg_8], rbx
0x180007b21  push    rdi
0x180007b22  sub     rsp, 20h
0x180007b26  mov     rdi, rcx
0x180007b29  mov     eax, [rcx]
0x180007b2b  test    eax, eax
0x180007b2d  jz      short loc_180007BA3
0x180007b2f  lea     rbx, [rcx+8]
0x180007b33  mov     rcx, rbx; SRWLock
0x180007b36  call    cs:__imp_AcquireSRWLockExclusive
0x180007b3c  mov     [rsp+28h+arg_0], rbx
0x180007b41  lea     rbx, [rdi+60h]
0x180007b45  cmp     qword ptr [rbx], 0
0x180007b49  jz      short loc_180007B51
0x180007b4b  mov     ebx, [rdi+1Ch]
0x180007b4e  nop
0x180007b4f  jmp     short loc_180007B95
0x180007b51  mov     qword ptr [rbx], 0
0x180007b58  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180007b5f  test    rax, rax
0x180007b62  jnz     short loc_180007B70
0x180007b64  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180007b6b  test    rax, rax
0x180007b6e  jz      short loc_180007B82
0x180007b70  mov     r8, rdi
0x180007b73  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180007b7a  mov     rcx, rbx
0x180007b7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b82  cmp     qword ptr [rbx], 0
0x180007b86  jnz     short loc_180007B8C
0x180007b88  xor     ebx, ebx
0x180007b8a  jmp     short loc_180007B95
0x180007b8c  nop
0x180007b8d  mov     ebx, 1
0x180007b92  mov     [rdi+1Ch], ebx
0x180007b95  lea     rcx, [rsp+28h+arg_0]
0x180007b9a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180007b9f  mov     eax, ebx
0x180007ba1  jmp     short loc_180007BA5
0x180007ba3  xor     eax, eax
0x180007ba5  mov     rbx, [rsp+28h+arg_8]
0x180007baa  add     rsp, 20h
0x180007bae  pop     rdi
0x180007baf  retn
```
