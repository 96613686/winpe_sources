# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180015564`
- end: `0x1800155e6`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `130`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800158f8`

## callees

- `0x180012f5c`
- `0x180013b04`
- `0x180015530`
- `0x180015564`
- `0x18001666c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001558b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001558b`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        wil::details::EnabledStateManager *this,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  unsigned __int64 v7; // r8
  _DWORD Source[2]; // [rsp+20h] [rbp-38h] BYREF
  struct wil_details_FeatureReportingCache *v9; // [rsp+28h] [rbp-30h]
  char *v10; // [rsp+60h] [rbp+8h] BYREF

  if ( *(_DWORD *)this && !wil::ProcessShutdownInProgress(this) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)this + 1);
    v10 = (char *)this + 8;
    if ( *(_DWORD *)this )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        Source[0] = a2;
        Source[1] = 0;
        v9 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details::EnabledStateManager *)((char *)this + 32), Source, v7);
        wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>(
          (struct _TP_TIMER **)this + 2,
          (_BYTE *)this + 24,
          this);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  }
}

```

## disassembly

```asm
0x180015564  push    rbx
0x180015566  push    rbp
0x180015567  push    rsi
0x180015568  push    rdi
0x180015569  sub     rsp, 38h
0x18001556d  mov     rsi, r8
0x180015570  mov     ebp, edx
0x180015572  mov     rdi, rcx
0x180015575  mov     eax, [rcx]
0x180015577  test    eax, eax
0x180015579  jz      short loc_1800155DD
0x18001557b  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180015580  test    al, al
0x180015582  jnz     short loc_1800155DD
0x180015584  lea     rbx, [rdi+8]
0x180015588  mov     rcx, rbx; SRWLock
0x18001558b  call    cs:__imp_AcquireSRWLockExclusive
0x180015591  mov     [rsp+58h+arg_0], rbx
0x180015596  mov     eax, [rdi]
0x180015598  test    eax, eax
0x18001559a  jz      short loc_1800155D2
0x18001559c  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800155a1  test    al, al
0x1800155a3  jnz     short loc_1800155D2
0x1800155a5  mov     [rsp+58h+Source], ebp
0x1800155a9  xor     eax, eax
0x1800155ab  mov     [rsp+58h+var_34], eax
0x1800155af  mov     [rsp+58h+var_30], rsi
0x1800155b4  lea     rcx, [rdi+20h]; this
0x1800155b8  lea     rdx, [rsp+58h+Source]; Source
0x1800155bd  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800155c2  lea     rdx, [rdi+18h]
0x1800155c6  lea     rcx, [rdi+10h]
0x1800155ca  mov     r8, rdi
0x1800155cd  call    ??$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVEnabledStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::EnabledStateManager *)
0x1800155d2  lea     rcx, [rsp+58h+arg_0]
0x1800155d7  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800155dc  nop
0x1800155dd  add     rsp, 38h
0x1800155e1  pop     rdi
0x1800155e2  pop     rsi
0x1800155e3  pop     rbp
0x1800155e4  pop     rbx
0x1800155e5  retn
```
