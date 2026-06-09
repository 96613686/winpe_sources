# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18003ee28`
- end: `0x18003ef16`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `238`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180040650`

## callees

- `0x18001deb0`
- `0x18003c8c4`
- `0x18003cb20`
- `0x18003cd8c`
- `0x18003d364`
- `0x18003edf4`
- `0x18003ee28`
- `0x180040b8c`
- `0x180040c94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003ee6b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003ee6b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003eec7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003eec7`

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
0x18003ee28  push    rbx
0x18003ee2a  push    rbp
0x18003ee2b  push    rsi
0x18003ee2c  push    rdi
0x18003ee2d  push    r14
0x18003ee2f  sub     rsp, 50h
0x18003ee33  mov     rax, cs:__security_cookie
0x18003ee3a  xor     rax, rsp
0x18003ee3d  mov     [rsp+78h+var_38], rax
0x18003ee42  cmp     byte ptr [rcx], 0
0x18003ee45  mov     r14d, r9d
0x18003ee48  movzx   ebp, r8w
0x18003ee4c  mov     esi, edx
0x18003ee4e  mov     rdi, rcx
0x18003ee51  jz      loc_18003EEFE
0x18003ee57  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18003ee5c  test    al, al
0x18003ee5e  jnz     loc_18003EEFE
0x18003ee64  lea     rbx, [rdi+28h]
0x18003ee68  mov     rcx, rbx; SRWLock
0x18003ee6b  call    cs:__imp_AcquireSRWLockExclusive
0x18003ee71  xor     eax, eax
0x18003ee73  mov     [rsp+78h+var_50], rbx
0x18003ee78  lea     rcx, [rdi+0E8h]; this
0x18003ee7f  mov     [rsp+78h+var_42], ax
0x18003ee84  lea     rdx, [rsp+78h+var_48]; void *
0x18003ee89  mov     [rsp+78h+var_48], esi
0x18003ee8d  mov     [rsp+78h+var_44], bp
0x18003ee92  lea     r8d, [rax+0Ch]; unsigned __int64
0x18003ee96  mov     [rsp+78h+var_40], r14d
0x18003ee9b  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18003eea0  cmp     byte ptr [rdi+40h], 0
0x18003eea4  jnz     short loc_18003EEF4
0x18003eea6  lea     rbx, [rdi+38h]
0x18003eeaa  cmp     qword ptr [rbx], 0
0x18003eeae  jnz     short loc_18003EEE2
0x18003eeb0  lea     rcx, [rsp+78h+var_58]; this
0x18003eeb5  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003eeba  xor     r8d, r8d; pcbe
0x18003eebd  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18003eec4  mov     rdx, rdi; pv
0x18003eec7  call    cs:__imp_CreateThreadpoolTimer
0x18003eecd  mov     rdx, rax
0x18003eed0  mov     rcx, rbx
0x18003eed3  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18003eed8  lea     rcx, [rsp+78h+var_58]; this
0x18003eedd  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003eee2  mov     r8d, 1388h
0x18003eee8  lea     rdx, [rdi+40h]
0x18003eeec  mov     rcx, rbx
0x18003eeef  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18003eef4  lea     rcx, [rsp+78h+var_50]
0x18003eef9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003eefe  mov     rcx, [rsp+78h+var_38]
0x18003ef03  xor     rcx, rsp; StackCookie
0x18003ef06  call    __security_check_cookie
0x18003ef0b  add     rsp, 50h
0x18003ef0f  pop     r14
0x18003ef11  pop     rdi
0x18003ef12  pop     rsi
0x18003ef13  pop     rbp
0x18003ef14  pop     rbx
0x18003ef15  retn
```
