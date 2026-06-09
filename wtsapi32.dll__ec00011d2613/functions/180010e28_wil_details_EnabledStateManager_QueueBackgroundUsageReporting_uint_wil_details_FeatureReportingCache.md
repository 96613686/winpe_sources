# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180010e28`
- end: `0x180010ea9`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `129`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800110f0`

## callees

- `0x180005bd0`
- `0x1800063f4`
- `0x18000bf4c`
- `0x180010e28`
- `0x180011fc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010e4f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010e4f`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        wil::details::EnabledStateManager *this,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  int v7; // eax
  unsigned __int64 v8; // r8
  _DWORD Source[2]; // [rsp+20h] [rbp-38h] BYREF
  struct wil_details_FeatureReportingCache *v10; // [rsp+28h] [rbp-30h]
  char *v11; // [rsp+60h] [rbp+8h] BYREF

  if ( *(_DWORD *)this && !wil::ProcessShutdownInProgress(this) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)this + 1);
    v7 = *(_DWORD *)this;
    v11 = (char *)this + 8;
    if ( v7 )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        Source[0] = a2;
        Source[1] = 0;
        v10 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details::EnabledStateManager *)((char *)this + 32), Source, v8);
        wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>(
          (struct _TP_TIMER **)this + 2,
          (_BYTE *)this + 24,
          this);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  }
}

```

## disassembly

```asm
0x180010e28  push    rbx
0x180010e2a  push    rbp
0x180010e2b  push    rsi
0x180010e2c  push    rdi
0x180010e2d  sub     rsp, 38h
0x180010e31  mov     eax, [rcx]
0x180010e33  mov     rsi, r8
0x180010e36  mov     ebp, edx
0x180010e38  mov     rdi, rcx
0x180010e3b  test    eax, eax
0x180010e3d  jz      short loc_180010EA0
0x180010e3f  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180010e44  test    al, al
0x180010e46  jnz     short loc_180010EA0
0x180010e48  lea     rbx, [rdi+8]
0x180010e4c  mov     rcx, rbx; SRWLock
0x180010e4f  call    cs:__imp_AcquireSRWLockExclusive
0x180010e55  mov     eax, [rdi]
0x180010e57  mov     [rsp+58h+arg_0], rbx
0x180010e5c  test    eax, eax
0x180010e5e  jz      short loc_180010E96
0x180010e60  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180010e65  test    al, al
0x180010e67  jnz     short loc_180010E96
0x180010e69  xor     eax, eax
0x180010e6b  mov     [rsp+58h+Source], ebp
0x180010e6f  lea     rcx, [rdi+20h]; this
0x180010e73  mov     [rsp+58h+var_34], eax
0x180010e77  lea     rdx, [rsp+58h+Source]; Source
0x180010e7c  mov     [rsp+58h+var_30], rsi
0x180010e81  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180010e86  lea     rdx, [rdi+18h]
0x180010e8a  mov     r8, rdi
0x180010e8d  lea     rcx, [rdi+10h]
0x180010e91  call    ??$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVEnabledStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::EnabledStateManager *)
0x180010e96  lea     rcx, [rsp+58h+arg_0]
0x180010e9b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180010ea0  add     rsp, 38h
0x180010ea4  pop     rdi
0x180010ea5  pop     rsi
0x180010ea6  pop     rbp
0x180010ea7  pop     rbx
0x180010ea8  retn
```
