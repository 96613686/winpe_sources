# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x180012a98`
- end: `0x180012b33`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `155`
- prototype: `unsigned int __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180012a70`

## callees

- `0x180010d08`
- `0x180012a98`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012ab2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012ab2`

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
0x180012a98  mov     [rsp+arg_8], rbx
0x180012a9d  push    rdi
0x180012a9e  sub     rsp, 20h
0x180012aa2  mov     eax, [rcx]
0x180012aa4  mov     rdi, rcx
0x180012aa7  test    eax, eax
0x180012aa9  jz      short loc_180012B25
0x180012aab  lea     rbx, [rcx+8]
0x180012aaf  mov     rcx, rbx; SRWLock
0x180012ab2  call    cs:__imp_AcquireSRWLockExclusive
0x180012ab9  nop     dword ptr [rax+rax+00h]
0x180012abe  mov     [rsp+28h+arg_0], rbx
0x180012ac3  lea     rbx, [rdi+20h]
0x180012ac7  cmp     qword ptr [rbx], 0
0x180012acb  jz      short loc_180012AD3
0x180012acd  mov     ebx, [rdi+1Ch]
0x180012ad0  nop
0x180012ad1  jmp     short loc_180012B17
0x180012ad3  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180012ada  mov     qword ptr [rbx], 0
0x180012ae1  test    rax, rax
0x180012ae4  jnz     short loc_180012AF2
0x180012ae6  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180012aed  test    rax, rax
0x180012af0  jz      short loc_180012B04
0x180012af2  mov     r8, rdi
0x180012af5  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180012afc  mov     rcx, rbx
0x180012aff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b04  cmp     qword ptr [rbx], 0
0x180012b08  jnz     short loc_180012B0E
0x180012b0a  xor     ebx, ebx
0x180012b0c  jmp     short loc_180012B17
0x180012b0e  mov     ebx, 1
0x180012b13  nop
0x180012b14  mov     [rdi+1Ch], ebx
0x180012b17  lea     rcx, [rsp+28h+arg_0]
0x180012b1c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180012b21  mov     eax, ebx
0x180012b23  jmp     short loc_180012B27
0x180012b25  xor     eax, eax
0x180012b27  mov     rbx, [rsp+28h+arg_8]
0x180012b2c  add     rsp, 20h
0x180012b30  pop     rdi
0x180012b31  retn
```
