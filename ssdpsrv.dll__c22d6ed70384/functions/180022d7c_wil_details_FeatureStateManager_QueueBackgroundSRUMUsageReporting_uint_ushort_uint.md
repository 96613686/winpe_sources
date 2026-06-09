# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180022d7c`
- end: `0x180022e6a`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `238`
- prototype: `void __fastcall(char *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18002bf40`

## callees

- `0x180022d7c`
- `0x180022fd4`
- `0x180022ff4`
- `0x180023038`
- `0x18002305c`
- `0x1800231e8`
- `0x1800232a8`
- `0x180026a30`
- `0x18002c4a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022dbf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022dbf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180022e1b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180022e1b`

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
  RTL_SRWLOCK *v10; // [rsp+28h] [rbp-50h] BYREF
  int v11; // [rsp+30h] [rbp-48h] BYREF
  __int16 v12; // [rsp+34h] [rbp-44h]
  __int16 v13; // [rsp+36h] [rbp-42h]
  int v14; // [rsp+38h] [rbp-40h]

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v10 = (RTL_SRWLOCK *)(pv + 40);
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
0x180022d7c  push    rbx
0x180022d7e  push    rbp
0x180022d7f  push    rsi
0x180022d80  push    rdi
0x180022d81  push    r14
0x180022d83  sub     rsp, 50h
0x180022d87  mov     rax, cs:__security_cookie
0x180022d8e  xor     rax, rsp
0x180022d91  mov     [rsp+78h+var_38], rax
0x180022d96  cmp     byte ptr [rcx], 0
0x180022d99  mov     r14d, r9d
0x180022d9c  movzx   ebp, r8w
0x180022da0  mov     esi, edx
0x180022da2  mov     rdi, rcx
0x180022da5  jz      loc_180022E52
0x180022dab  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180022db0  test    al, al
0x180022db2  jnz     loc_180022E52
0x180022db8  lea     rbx, [rdi+28h]
0x180022dbc  mov     rcx, rbx; SRWLock
0x180022dbf  call    cs:__imp_AcquireSRWLockExclusive
0x180022dc5  xor     eax, eax
0x180022dc7  mov     [rsp+78h+var_50], rbx
0x180022dcc  lea     rcx, [rdi+0E8h]; this
0x180022dd3  mov     [rsp+78h+var_42], ax
0x180022dd8  lea     rdx, [rsp+78h+var_48]; void *
0x180022ddd  mov     [rsp+78h+var_48], esi
0x180022de1  mov     [rsp+78h+var_44], bp
0x180022de6  lea     r8d, [rax+0Ch]; unsigned __int64
0x180022dea  mov     [rsp+78h+var_40], r14d
0x180022def  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180022df4  cmp     byte ptr [rdi+40h], 0
0x180022df8  jnz     short loc_180022E48
0x180022dfa  lea     rbx, [rdi+38h]
0x180022dfe  cmp     qword ptr [rbx], 0
0x180022e02  jnz     short loc_180022E36
0x180022e04  lea     rcx, [rsp+78h+var_58]; this
0x180022e09  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180022e0e  xor     r8d, r8d; pcbe
0x180022e11  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180022e18  mov     rdx, rdi; pv
0x180022e1b  call    cs:__imp_CreateThreadpoolTimer
0x180022e21  mov     rdx, rax
0x180022e24  mov     rcx, rbx
0x180022e27  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180022e2c  lea     rcx, [rsp+78h+var_58]; this
0x180022e31  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180022e36  mov     r8d, 1388h
0x180022e3c  lea     rdx, [rdi+40h]
0x180022e40  mov     rcx, rbx
0x180022e43  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180022e48  lea     rcx, [rsp+78h+var_50]
0x180022e4d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180022e52  mov     rcx, [rsp+78h+var_38]
0x180022e57  xor     rcx, rsp; StackCookie
0x180022e5a  call    __security_check_cookie
0x180022e5f  add     rsp, 50h
0x180022e63  pop     r14
0x180022e65  pop     rdi
0x180022e66  pop     rsi
0x180022e67  pop     rbp
0x180022e68  pop     rbx
0x180022e69  retn
```
