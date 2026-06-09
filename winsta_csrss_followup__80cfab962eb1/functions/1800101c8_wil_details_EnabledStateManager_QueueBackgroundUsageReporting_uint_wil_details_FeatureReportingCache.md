# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x1800101c8`
- end: `0x180010250`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `136`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001001c`

## callees

- `0x1800101c8`
- `0x18001028c`
- `0x1800103cc`
- `0x180010d08`
- `0x180020e98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800101ef`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800101ef`

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
        wil::details_abi::heap_buffer::push_back((wil::details::EnabledStateManager *)((char *)this + 48), Source, v8);
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
0x1800101c8  push    rbx
0x1800101ca  push    rbp
0x1800101cb  push    rsi
0x1800101cc  push    rdi
0x1800101cd  sub     rsp, 38h
0x1800101d1  mov     eax, [rcx]
0x1800101d3  mov     rsi, r8
0x1800101d6  mov     ebp, edx
0x1800101d8  mov     rdi, rcx
0x1800101db  test    eax, eax
0x1800101dd  jz      short loc_180010246
0x1800101df  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800101e4  test    al, al
0x1800101e6  jnz     short loc_180010246
0x1800101e8  lea     rbx, [rdi+8]
0x1800101ec  mov     rcx, rbx; SRWLock
0x1800101ef  call    cs:__imp_AcquireSRWLockExclusive
0x1800101f6  nop     dword ptr [rax+rax+00h]
0x1800101fb  mov     eax, [rdi]
0x1800101fd  mov     [rsp+58h+arg_0], rbx
0x180010202  test    eax, eax
0x180010204  jz      short loc_18001023C
0x180010206  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001020b  test    al, al
0x18001020d  jnz     short loc_18001023C
0x18001020f  xor     eax, eax
0x180010211  mov     [rsp+58h+Source], ebp
0x180010215  lea     rcx, [rdi+30h]; this
0x180010219  mov     [rsp+58h+var_34], eax
0x18001021d  lea     rdx, [rsp+58h+Source]; Source
0x180010222  mov     [rsp+58h+var_30], rsi
0x180010227  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001022c  lea     rdx, [rdi+18h]
0x180010230  mov     r8, rdi
0x180010233  lea     rcx, [rdi+10h]
0x180010237  call    ??$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVEnabledStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::EnabledStateManager *)
0x18001023c  lea     rcx, [rsp+58h+arg_0]
0x180010241  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180010246  add     rsp, 38h
0x18001024a  pop     rdi
0x18001024b  pop     rsi
0x18001024c  pop     rbp
0x18001024d  pop     rbx
0x18001024e  retn
```
