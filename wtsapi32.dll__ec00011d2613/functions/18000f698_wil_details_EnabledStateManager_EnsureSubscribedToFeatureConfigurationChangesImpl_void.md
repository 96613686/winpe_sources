# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x18000f698`
- end: `0x18000f72c`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `unsigned int __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000f670`

## callees

- `0x18000bf4c`
- `0x18000f698`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f6b2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f6b2`

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
0x18000f698  mov     [rsp+arg_8], rbx
0x18000f69d  push    rdi
0x18000f69e  sub     rsp, 20h
0x18000f6a2  mov     eax, [rcx]
0x18000f6a4  mov     rdi, rcx
0x18000f6a7  test    eax, eax
0x18000f6a9  jz      short loc_18000F71F
0x18000f6ab  lea     rbx, [rcx+8]
0x18000f6af  mov     rcx, rbx; SRWLock
0x18000f6b2  call    cs:__imp_AcquireSRWLockExclusive
0x18000f6b8  mov     [rsp+28h+arg_0], rbx
0x18000f6bd  lea     rbx, [rdi+60h]
0x18000f6c1  cmp     qword ptr [rbx], 0
0x18000f6c5  jz      short loc_18000F6CD
0x18000f6c7  mov     ebx, [rdi+1Ch]
0x18000f6ca  nop
0x18000f6cb  jmp     short loc_18000F711
0x18000f6cd  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18000f6d4  mov     qword ptr [rbx], 0
0x18000f6db  test    rax, rax
0x18000f6de  jnz     short loc_18000F6EC
0x18000f6e0  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18000f6e7  test    rax, rax
0x18000f6ea  jz      short loc_18000F6FE
0x18000f6ec  mov     r8, rdi
0x18000f6ef  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18000f6f6  mov     rcx, rbx
0x18000f6f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6fe  cmp     qword ptr [rbx], 0
0x18000f702  jnz     short loc_18000F708
0x18000f704  xor     ebx, ebx
0x18000f706  jmp     short loc_18000F711
0x18000f708  mov     ebx, 1
0x18000f70d  nop
0x18000f70e  mov     [rdi+1Ch], ebx
0x18000f711  lea     rcx, [rsp+28h+arg_0]
0x18000f716  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000f71b  mov     eax, ebx
0x18000f71d  jmp     short loc_18000F721
0x18000f71f  xor     eax, eax
0x18000f721  mov     rbx, [rsp+28h+arg_8]
0x18000f726  add     rsp, 20h
0x18000f72a  pop     rdi
0x18000f72b  retn
```
