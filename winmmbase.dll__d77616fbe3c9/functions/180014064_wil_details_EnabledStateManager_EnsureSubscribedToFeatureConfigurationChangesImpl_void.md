# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x180014064`
- end: `0x1800140f8`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `148`
- prototype: `unsigned int __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001403c`

## callees

- `0x180013b04`
- `0x180014064`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001407e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001407e`

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
0x180014064  mov     [rsp+arg_8], rbx
0x180014069  push    rdi
0x18001406a  sub     rsp, 20h
0x18001406e  mov     rdi, rcx
0x180014071  mov     eax, [rcx]
0x180014073  test    eax, eax
0x180014075  jz      short loc_1800140EB
0x180014077  lea     rbx, [rcx+8]
0x18001407b  mov     rcx, rbx; SRWLock
0x18001407e  call    cs:__imp_AcquireSRWLockExclusive
0x180014084  mov     [rsp+28h+arg_0], rbx
0x180014089  lea     rbx, [rdi+60h]
0x18001408d  cmp     qword ptr [rbx], 0
0x180014091  jz      short loc_180014099
0x180014093  mov     ebx, [rdi+1Ch]
0x180014096  nop
0x180014097  jmp     short loc_1800140DD
0x180014099  mov     qword ptr [rbx], 0
0x1800140a0  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1800140a7  test    rax, rax
0x1800140aa  jnz     short loc_1800140B8
0x1800140ac  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x1800140b3  test    rax, rax
0x1800140b6  jz      short loc_1800140CA
0x1800140b8  mov     r8, rdi
0x1800140bb  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x1800140c2  mov     rcx, rbx
0x1800140c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140ca  cmp     qword ptr [rbx], 0
0x1800140ce  jnz     short loc_1800140D4
0x1800140d0  xor     ebx, ebx
0x1800140d2  jmp     short loc_1800140DD
0x1800140d4  nop
0x1800140d5  mov     ebx, 1
0x1800140da  mov     [rdi+1Ch], ebx
0x1800140dd  lea     rcx, [rsp+28h+arg_0]
0x1800140e2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800140e7  mov     eax, ebx
0x1800140e9  jmp     short loc_1800140ED
0x1800140eb  xor     eax, eax
0x1800140ed  mov     rbx, [rsp+28h+arg_8]
0x1800140f2  add     rsp, 20h
0x1800140f6  pop     rdi
0x1800140f7  retn
```
