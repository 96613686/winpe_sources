# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800325c0`
- end: `0x1800326ae`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `238`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180033cc0`

## callees

- `0x180027364`
- `0x180027388`
- `0x18002756c`
- `0x18002786c`
- `0x180027ca8`
- `0x18002b2a4`
- `0x18002b3b0`
- `0x1800325c0`
- `0x180035bd0`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180032603`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180032603`
- `KERNEL32!CreateThreadpoolTimer` at `0x18003265f`
- `KERNEL32!CreateThreadpoolTimer` at `0x18003265f`

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
0x1800325c0  push    rbx
0x1800325c2  push    rbp
0x1800325c3  push    rsi
0x1800325c4  push    rdi
0x1800325c5  push    r14
0x1800325c7  sub     rsp, 50h
0x1800325cb  mov     rax, cs:__security_cookie
0x1800325d2  xor     rax, rsp
0x1800325d5  mov     [rsp+78h+var_38], rax
0x1800325da  cmp     byte ptr [rcx], 0
0x1800325dd  mov     r14d, r9d
0x1800325e0  movzx   ebp, r8w
0x1800325e4  mov     esi, edx
0x1800325e6  mov     rdi, rcx
0x1800325e9  jz      loc_180032696
0x1800325ef  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800325f4  test    al, al
0x1800325f6  jnz     loc_180032696
0x1800325fc  lea     rbx, [rdi+28h]
0x180032600  mov     rcx, rbx; SRWLock
0x180032603  call    cs:__imp_AcquireSRWLockExclusive
0x180032609  xor     eax, eax
0x18003260b  mov     [rsp+78h+var_50], rbx
0x180032610  lea     rcx, [rdi+0E8h]; this
0x180032617  mov     [rsp+78h+var_42], ax
0x18003261c  lea     rdx, [rsp+78h+var_48]; void *
0x180032621  mov     [rsp+78h+var_48], esi
0x180032625  mov     [rsp+78h+var_44], bp
0x18003262a  lea     r8d, [rax+0Ch]; unsigned __int64
0x18003262e  mov     [rsp+78h+var_40], r14d
0x180032633  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180032638  cmp     byte ptr [rdi+40h], 0
0x18003263c  jnz     short loc_18003268C
0x18003263e  lea     rbx, [rdi+38h]
0x180032642  cmp     qword ptr [rbx], 0
0x180032646  jnz     short loc_18003267A
0x180032648  lea     rcx, [rsp+78h+var_58]; this
0x18003264d  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180032652  xor     r8d, r8d; pcbe
0x180032655  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18003265c  mov     rdx, rdi; pv
0x18003265f  call    cs:__imp_CreateThreadpoolTimer
0x180032665  mov     rdx, rax
0x180032668  mov     rcx, rbx
0x18003266b  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180032670  lea     rcx, [rsp+78h+var_58]; this
0x180032675  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003267a  mov     r8d, 1388h
0x180032680  lea     rdx, [rdi+40h]
0x180032684  mov     rcx, rbx
0x180032687  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18003268c  lea     rcx, [rsp+78h+var_50]
0x180032691  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180032696  mov     rcx, [rsp+78h+var_38]
0x18003269b  xor     rcx, rsp; StackCookie
0x18003269e  call    __security_check_cookie
0x1800326a3  add     rsp, 50h
0x1800326a7  pop     r14
0x1800326a9  pop     rdi
0x1800326aa  pop     rsi
0x1800326ab  pop     rbp
0x1800326ac  pop     rbx
0x1800326ad  retn
```
