# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x1800248ac`
- end: `0x180024947`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `155`
- prototype: `unsigned int __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18002b074`

## callees

- `0x1800248ac`
- `0x180024d20`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800248c6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800248c6`

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
  v3 = this + 4;
  if ( this[4].Ptr )
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
0x1800248ac  mov     [rsp+arg_8], rbx
0x1800248b1  push    rdi
0x1800248b2  sub     rsp, 20h
0x1800248b6  mov     eax, [rcx]
0x1800248b8  mov     rdi, rcx
0x1800248bb  test    eax, eax
0x1800248bd  jz      short loc_180024939
0x1800248bf  lea     rbx, [rcx+8]
0x1800248c3  mov     rcx, rbx; SRWLock
0x1800248c6  call    cs:__imp_AcquireSRWLockExclusive
0x1800248cd  nop     dword ptr [rax+rax+00h]
0x1800248d2  mov     [rsp+28h+arg_0], rbx
0x1800248d7  lea     rbx, [rdi+20h]
0x1800248db  cmp     qword ptr [rbx], 0
0x1800248df  jz      short loc_1800248E7
0x1800248e1  mov     ebx, [rdi+1Ch]
0x1800248e4  nop
0x1800248e5  jmp     short loc_18002492B
0x1800248e7  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1800248ee  mov     qword ptr [rbx], 0
0x1800248f5  test    rax, rax
0x1800248f8  jnz     short loc_180024906
0x1800248fa  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180024901  test    rax, rax
0x180024904  jz      short loc_180024918
0x180024906  mov     r8, rdi
0x180024909  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180024910  mov     rcx, rbx
0x180024913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024918  cmp     qword ptr [rbx], 0
0x18002491c  jnz     short loc_180024922
0x18002491e  xor     ebx, ebx
0x180024920  jmp     short loc_18002492B
0x180024922  mov     ebx, 1
0x180024927  nop
0x180024928  mov     [rdi+1Ch], ebx
0x18002492b  lea     rcx, [rsp+28h+arg_0]
0x180024930  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180024935  mov     eax, ebx
0x180024937  jmp     short loc_18002493B
0x180024939  xor     eax, eax
0x18002493b  mov     rbx, [rsp+28h+arg_8]
0x180024940  add     rsp, 20h
0x180024944  pop     rdi
0x180024945  retn
```
