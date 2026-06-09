# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000f65c`
- end: `0x18000f6dd`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `129`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000f4b8`

## callees

- `0x18000f65c`
- `0x18000f71c`
- `0x18000f89c`
- `0x180010104`
- `0x18001f7dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f683`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f683`

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
0x18000f65c  push    rbx
0x18000f65e  push    rbp
0x18000f65f  push    rsi
0x18000f660  push    rdi
0x18000f661  sub     rsp, 38h
0x18000f665  mov     eax, [rcx]
0x18000f667  mov     rsi, r8
0x18000f66a  mov     ebp, edx
0x18000f66c  mov     rdi, rcx
0x18000f66f  test    eax, eax
0x18000f671  jz      short loc_18000F6D4
0x18000f673  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000f678  test    al, al
0x18000f67a  jnz     short loc_18000F6D4
0x18000f67c  lea     rbx, [rdi+8]
0x18000f680  mov     rcx, rbx; SRWLock
0x18000f683  call    cs:__imp_AcquireSRWLockExclusive
0x18000f689  mov     eax, [rdi]
0x18000f68b  mov     [rsp+58h+arg_0], rbx
0x18000f690  test    eax, eax
0x18000f692  jz      short loc_18000F6CA
0x18000f694  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000f699  test    al, al
0x18000f69b  jnz     short loc_18000F6CA
0x18000f69d  xor     eax, eax
0x18000f69f  mov     [rsp+58h+Source], ebp
0x18000f6a3  lea     rcx, [rdi+20h]; this
0x18000f6a7  mov     [rsp+58h+var_34], eax
0x18000f6ab  lea     rdx, [rsp+58h+Source]; Source
0x18000f6b0  mov     [rsp+58h+var_30], rsi
0x18000f6b5  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000f6ba  lea     rdx, [rdi+18h]
0x18000f6be  mov     r8, rdi
0x18000f6c1  lea     rcx, [rdi+10h]
0x18000f6c5  call    ??$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVEnabledStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::EnabledStateManager *)
0x18000f6ca  lea     rcx, [rsp+58h+arg_0]
0x18000f6cf  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000f6d4  add     rsp, 38h
0x18000f6d8  pop     rdi
0x18000f6d9  pop     rsi
0x18000f6da  pop     rbp
0x18000f6db  pop     rbx
0x18000f6dc  retn
```
