# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800172d0`
- end: `0x1800173be`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `238`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180015960`

## callees

- `0x1800109cc`
- `0x180010a10`
- `0x180010a30`
- `0x180010cc0`
- `0x180010d6c`
- `0x180010e64`
- `0x1800172d0`
- `0x1800173c4`
- `0x180022190`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017313`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017313`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001736f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001736f`

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
0x1800172d0  push    rbx
0x1800172d2  push    rbp
0x1800172d3  push    rsi
0x1800172d4  push    rdi
0x1800172d5  push    r14
0x1800172d7  sub     rsp, 50h
0x1800172db  mov     rax, cs:__security_cookie
0x1800172e2  xor     rax, rsp
0x1800172e5  mov     [rsp+78h+var_38], rax
0x1800172ea  cmp     byte ptr [rcx], 0
0x1800172ed  mov     r14d, r9d
0x1800172f0  movzx   ebp, r8w
0x1800172f4  mov     esi, edx
0x1800172f6  mov     rdi, rcx
0x1800172f9  jz      loc_1800173A6
0x1800172ff  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180017304  test    al, al
0x180017306  jnz     loc_1800173A6
0x18001730c  lea     rbx, [rdi+28h]
0x180017310  mov     rcx, rbx; SRWLock
0x180017313  call    cs:__imp_AcquireSRWLockExclusive
0x180017319  xor     eax, eax
0x18001731b  mov     [rsp+78h+var_50], rbx
0x180017320  lea     rcx, [rdi+0E8h]; this
0x180017327  mov     [rsp+78h+var_42], ax
0x18001732c  lea     rdx, [rsp+78h+var_48]; void *
0x180017331  mov     [rsp+78h+var_48], esi
0x180017335  mov     [rsp+78h+var_44], bp
0x18001733a  lea     r8d, [rax+0Ch]; unsigned __int64
0x18001733e  mov     [rsp+78h+var_40], r14d
0x180017343  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180017348  cmp     byte ptr [rdi+40h], 0
0x18001734c  jnz     short loc_18001739C
0x18001734e  lea     rbx, [rdi+38h]
0x180017352  cmp     qword ptr [rbx], 0
0x180017356  jnz     short loc_18001738A
0x180017358  lea     rcx, [rsp+78h+var_58]; this
0x18001735d  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180017362  xor     r8d, r8d; pcbe
0x180017365  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001736c  mov     rdx, rdi; pv
0x18001736f  call    cs:__imp_CreateThreadpoolTimer
0x180017375  mov     rdx, rax
0x180017378  mov     rcx, rbx
0x18001737b  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180017380  lea     rcx, [rsp+78h+var_58]; this
0x180017385  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001738a  mov     r8d, 1388h
0x180017390  lea     rdx, [rdi+40h]
0x180017394  mov     rcx, rbx
0x180017397  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18001739c  lea     rcx, [rsp+78h+var_50]
0x1800173a1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800173a6  mov     rcx, [rsp+78h+var_38]
0x1800173ab  xor     rcx, rsp; StackCookie
0x1800173ae  call    __security_check_cookie
0x1800173b3  add     rsp, 50h
0x1800173b7  pop     r14
0x1800173b9  pop     rdi
0x1800173ba  pop     rsi
0x1800173bb  pop     rbp
0x1800173bc  pop     rbx
0x1800173bd  retn
```
