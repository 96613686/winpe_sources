# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000ed2c`
- end: `0x18000ee0c`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `224`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800108f0`

## callees

- `0x18000bd50`
- `0x18000bf04`
- `0x18000c264`
- `0x18000ccb8`
- `0x18000ecf8`
- `0x18000ed2c`
- `0x180010dd4`
- `0x180010ef4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ed60`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ed60`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000edc2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000edc2`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  int v9; // [rsp+20h] [rbp-48h] BYREF
  __int16 v10; // [rsp+24h] [rbp-44h]
  __int16 v11; // [rsp+26h] [rbp-42h]
  int v12; // [rsp+28h] [rbp-40h]
  char *v13; // [rsp+30h] [rbp-38h] BYREF

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v13 = pv + 40;
    v11 = 0;
    v9 = a2;
    v10 = a3;
    v12 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 232), &v9, 0xCu);
    if ( !pv[64] )
    {
      if ( !*((_QWORD *)pv + 7) )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v9);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            `wil::details::EnsureCoalescedTimerSRUM<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          pv + 56,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v9);
      }
      wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 7, pv + 64, 5000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
  }
}

```

## disassembly

```asm
0x18000ed2c  push    rbx
0x18000ed2e  push    rbp
0x18000ed2f  push    rsi
0x18000ed30  push    rdi
0x18000ed31  push    r14
0x18000ed33  sub     rsp, 40h
0x18000ed37  mov     r14d, r9d
0x18000ed3a  movzx   ebp, r8w
0x18000ed3e  mov     esi, edx
0x18000ed40  mov     rdi, rcx
0x18000ed43  cmp     byte ptr [rcx], 0
0x18000ed46  jz      loc_18000EE00
0x18000ed4c  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000ed51  test    al, al
0x18000ed53  jnz     loc_18000EE00
0x18000ed59  lea     rbx, [rdi+28h]
0x18000ed5d  mov     rcx, rbx; SRWLock
0x18000ed60  call    cs:__imp_AcquireSRWLockExclusive
0x18000ed67  nop     dword ptr [rax+rax+00h]
0x18000ed6c  mov     [rsp+68h+var_38], rbx
0x18000ed71  xor     eax, eax
0x18000ed73  mov     [rsp+68h+var_42], ax
0x18000ed78  mov     [rsp+68h+var_48], esi
0x18000ed7c  mov     [rsp+68h+var_44], bp
0x18000ed81  mov     [rsp+68h+var_40], r14d
0x18000ed86  lea     rcx, [rdi+0E8h]; this
0x18000ed8d  lea     r8d, [rax+0Ch]; unsigned __int64
0x18000ed91  lea     rdx, [rsp+68h+var_48]; void *
0x18000ed96  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000ed9b  cmp     byte ptr [rdi+40h], 0
0x18000ed9f  jnz     short loc_18000EDF5
0x18000eda1  lea     rbx, [rdi+38h]
0x18000eda5  cmp     qword ptr [rbx], 0
0x18000eda9  jnz     short loc_18000EDE3
0x18000edab  lea     rcx, [rsp+68h+var_48]; this
0x18000edb0  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000edb5  xor     r8d, r8d; pcbe
0x18000edb8  mov     rdx, rdi; pv
0x18000edbb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimerSRUM@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000edc2  call    cs:__imp_CreateThreadpoolTimer
0x18000edc9  nop     dword ptr [rax+rax+00h]
0x18000edce  mov     rdx, rax
0x18000edd1  mov     rcx, rbx
0x18000edd4  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000edd9  lea     rcx, [rsp+68h+var_48]; this
0x18000edde  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000ede3  mov     r8d, 1388h
0x18000ede9  lea     rdx, [rdi+40h]
0x18000eded  mov     rcx, rbx
0x18000edf0  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18000edf5  lea     rcx, [rsp+68h+var_38]
0x18000edfa  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000edff  nop
0x18000ee00  add     rsp, 40h
0x18000ee04  pop     r14
0x18000ee06  pop     rdi
0x18000ee07  pop     rsi
0x18000ee08  pop     rbp
0x18000ee09  pop     rbx
0x18000ee0a  retn
```
