# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18003fc18`
- end: `0x18003fd08`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `240`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18004f900`

## callees

- `0x18003fc18`
- `0x18003fdec`
- `0x18003fe10`
- `0x18003fe58`
- `0x18003fe7c`
- `0x18003fea8`
- `0x18003ffdc`
- `0x18004fe2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003fc54`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003fc54`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003fcb6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003fcb6`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  char *v9; // [rsp+20h] [rbp-38h] BYREF
  int v10; // [rsp+28h] [rbp-30h] BYREF
  __int16 v11; // [rsp+2Ch] [rbp-2Ch]
  __int16 v12; // [rsp+2Eh] [rbp-2Ah]
  int v13; // [rsp+30h] [rbp-28h]
  char v14; // [rsp+60h] [rbp+8h] BYREF

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v9 = pv + 40;
    v12 = 0;
    v10 = a2;
    v11 = a3;
    v13 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 232), &v10, 0xCu);
    if ( !pv[64] )
    {
      if ( !*((_QWORD *)pv + 7) )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v14);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            `wil::details::EnsureCoalescedTimerSRUM<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          pv + 56,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v14);
      }
      wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 7, pv + 64, 5000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  }
}

```

## disassembly

```asm
0x18003fc18  mov     [rsp+arg_8], rbx
0x18003fc1d  mov     [rsp+arg_10], rbp
0x18003fc22  push    rsi
0x18003fc23  push    rdi
0x18003fc24  push    r14
0x18003fc26  sub     rsp, 40h
0x18003fc2a  mov     esi, r9d
0x18003fc2d  movzx   ebp, r8w
0x18003fc31  mov     r14d, edx
0x18003fc34  mov     rdi, rcx
0x18003fc37  cmp     byte ptr [rcx], 0
0x18003fc3a  jz      loc_18003FCF4
0x18003fc40  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18003fc45  test    al, al
0x18003fc47  jnz     loc_18003FCF4
0x18003fc4d  lea     rbx, [rdi+28h]
0x18003fc51  mov     rcx, rbx; SRWLock
0x18003fc54  call    cs:__imp_AcquireSRWLockExclusive
0x18003fc5b  nop     dword ptr [rax+rax+00h]
0x18003fc60  mov     [rsp+58h+var_38], rbx
0x18003fc65  xor     eax, eax
0x18003fc67  mov     [rsp+58h+var_2A], ax
0x18003fc6c  mov     [rsp+58h+var_30], r14d
0x18003fc71  mov     [rsp+58h+var_2C], bp
0x18003fc76  mov     [rsp+58h+var_28], esi
0x18003fc7a  lea     rcx, [rdi+0E8h]; this
0x18003fc81  lea     r8d, [rax+0Ch]; unsigned __int64
0x18003fc85  lea     rdx, [rsp+58h+var_30]; void *
0x18003fc8a  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18003fc8f  cmp     byte ptr [rdi+40h], 0
0x18003fc93  jnz     short loc_18003FCE9
0x18003fc95  lea     rbx, [rdi+38h]
0x18003fc99  cmp     qword ptr [rbx], 0
0x18003fc9d  jnz     short loc_18003FCD7
0x18003fc9f  lea     rcx, [rsp+58h+arg_0]; this
0x18003fca4  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003fca9  xor     r8d, r8d; pcbe
0x18003fcac  mov     rdx, rdi; pv
0x18003fcaf  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimerSRUM@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18003fcb6  call    cs:__imp_CreateThreadpoolTimer
0x18003fcbd  nop     dword ptr [rax+rax+00h]
0x18003fcc2  mov     rdx, rax
0x18003fcc5  mov     rcx, rbx
0x18003fcc8  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18003fccd  lea     rcx, [rsp+58h+arg_0]; this
0x18003fcd2  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003fcd7  mov     r8d, 1388h
0x18003fcdd  lea     rdx, [rdi+40h]
0x18003fce1  mov     rcx, rbx
0x18003fce4  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18003fce9  lea     rcx, [rsp+58h+var_38]
0x18003fcee  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003fcf3  nop
0x18003fcf4  mov     rbx, [rsp+58h+arg_8]
0x18003fcf9  mov     rbp, [rsp+58h+arg_10]
0x18003fcfe  add     rsp, 40h
0x18003fd02  pop     r14
0x18003fd04  pop     rdi
0x18003fd05  pop     rsi
0x18003fd06  retn
```
