# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x18001221c`
- end: `0x1800122b0`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `unsigned int __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800121f4`

## callees

- `0x180010104`
- `0x18001221c`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012236`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012236`

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
0x18001221c  mov     [rsp+arg_8], rbx
0x180012221  push    rdi
0x180012222  sub     rsp, 20h
0x180012226  mov     eax, [rcx]
0x180012228  mov     rdi, rcx
0x18001222b  test    eax, eax
0x18001222d  jz      short loc_1800122A3
0x18001222f  lea     rbx, [rcx+8]
0x180012233  mov     rcx, rbx; SRWLock
0x180012236  call    cs:__imp_AcquireSRWLockExclusive
0x18001223c  mov     [rsp+28h+arg_0], rbx
0x180012241  lea     rbx, [rdi+60h]
0x180012245  cmp     qword ptr [rbx], 0
0x180012249  jz      short loc_180012251
0x18001224b  mov     ebx, [rdi+1Ch]
0x18001224e  nop
0x18001224f  jmp     short loc_180012295
0x180012251  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180012258  mov     qword ptr [rbx], 0
0x18001225f  test    rax, rax
0x180012262  jnz     short loc_180012270
0x180012264  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18001226b  test    rax, rax
0x18001226e  jz      short loc_180012282
0x180012270  mov     r8, rdi
0x180012273  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18001227a  mov     rcx, rbx
0x18001227d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012282  cmp     qword ptr [rbx], 0
0x180012286  jnz     short loc_18001228C
0x180012288  xor     ebx, ebx
0x18001228a  jmp     short loc_180012295
0x18001228c  mov     ebx, 1
0x180012291  nop
0x180012292  mov     [rdi+1Ch], ebx
0x180012295  lea     rcx, [rsp+28h+arg_0]
0x18001229a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001229f  mov     eax, ebx
0x1800122a1  jmp     short loc_1800122A5
0x1800122a3  xor     eax, eax
0x1800122a5  mov     rbx, [rsp+28h+arg_8]
0x1800122aa  add     rsp, 20h
0x1800122ae  pop     rdi
0x1800122af  retn
```
