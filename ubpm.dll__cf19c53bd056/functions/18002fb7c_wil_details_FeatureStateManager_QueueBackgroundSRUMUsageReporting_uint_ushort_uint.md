# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18002fb7c`
- end: `0x18002fc6a`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `238`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18003b400`

## callees

- `0x18002fb7c`
- `0x18002fd38`
- `0x18002fd58`
- `0x18002fd9c`
- `0x18002fdbc`
- `0x18002fde0`
- `0x18002ff08`
- `0x18003b94c`
- `0x18003d810`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002fc1b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002fc1b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002fbbf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002fbbf`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  _BYTE v9[8]; // [rsp+20h] [rbp-58h] BYREF
  char *v10; // [rsp+28h] [rbp-50h] BYREF
  int v11; // [rsp+30h] [rbp-48h] BYREF
  __int16 v12; // [rsp+34h] [rbp-44h]
  __int16 v13; // [rsp+36h] [rbp-42h]
  int v14; // [rsp+38h] [rbp-40h]

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v10 = pv + 40;
    v13 = 0;
    v11 = a2;
    v12 = a3;
    v14 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 232), &v11, 0xCu);
    if ( !pv[64] )
    {
      if ( !*((_QWORD *)pv + 7) )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v9);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          pv + 56,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v9);
      }
      wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 7, pv + 64, 5000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  }
}

```

## disassembly

```asm
0x18002fb7c  push    rbx
0x18002fb7e  push    rbp
0x18002fb7f  push    rsi
0x18002fb80  push    rdi
0x18002fb81  push    r14
0x18002fb83  sub     rsp, 50h
0x18002fb87  mov     rax, cs:__security_cookie
0x18002fb8e  xor     rax, rsp
0x18002fb91  mov     [rsp+78h+var_38], rax
0x18002fb96  cmp     byte ptr [rcx], 0
0x18002fb99  mov     r14d, r9d
0x18002fb9c  movzx   ebp, r8w
0x18002fba0  mov     esi, edx
0x18002fba2  mov     rdi, rcx
0x18002fba5  jz      loc_18002FC52
0x18002fbab  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18002fbb0  test    al, al
0x18002fbb2  jnz     loc_18002FC52
0x18002fbb8  lea     rbx, [rdi+28h]
0x18002fbbc  mov     rcx, rbx; SRWLock
0x18002fbbf  call    cs:__imp_AcquireSRWLockExclusive
0x18002fbc5  xor     eax, eax
0x18002fbc7  mov     [rsp+78h+var_50], rbx
0x18002fbcc  lea     rcx, [rdi+0E8h]; this
0x18002fbd3  mov     [rsp+78h+var_42], ax
0x18002fbd8  lea     rdx, [rsp+78h+var_48]; void *
0x18002fbdd  mov     [rsp+78h+var_48], esi
0x18002fbe1  mov     [rsp+78h+var_44], bp
0x18002fbe6  lea     r8d, [rax+0Ch]; unsigned __int64
0x18002fbea  mov     [rsp+78h+var_40], r14d
0x18002fbef  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18002fbf4  cmp     byte ptr [rdi+40h], 0
0x18002fbf8  jnz     short loc_18002FC48
0x18002fbfa  lea     rbx, [rdi+38h]
0x18002fbfe  cmp     qword ptr [rbx], 0
0x18002fc02  jnz     short loc_18002FC36
0x18002fc04  lea     rcx, [rsp+78h+var_58]; this
0x18002fc09  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002fc0e  xor     r8d, r8d; pcbe
0x18002fc11  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002fc18  mov     rdx, rdi; pv
0x18002fc1b  call    cs:__imp_CreateThreadpoolTimer
0x18002fc21  mov     rdx, rax
0x18002fc24  mov     rcx, rbx
0x18002fc27  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18002fc2c  lea     rcx, [rsp+78h+var_58]; this
0x18002fc31  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002fc36  mov     r8d, 1388h
0x18002fc3c  lea     rdx, [rdi+40h]
0x18002fc40  mov     rcx, rbx
0x18002fc43  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18002fc48  lea     rcx, [rsp+78h+var_50]
0x18002fc4d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002fc52  mov     rcx, [rsp+78h+var_38]
0x18002fc57  xor     rcx, rsp; StackCookie
0x18002fc5a  call    __security_check_cookie
0x18002fc5f  add     rsp, 50h
0x18002fc63  pop     r14
0x18002fc65  pop     rdi
0x18002fc66  pop     rsi
0x18002fc67  pop     rbp
0x18002fc68  pop     rbx
0x18002fc69  retn
```
