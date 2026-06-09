# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800179c8`
- end: `0x180017ab8`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `240`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180018f40`

## callees

- `0x18000ddcc`
- `0x18001136c`
- `0x1800114c4`
- `0x18001205c`
- `0x180016280`
- `0x1800179c8`
- `0x1800194ac`
- `0x1800195b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017a04`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017a04`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180017a66`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180017a66`

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
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
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
0x1800179c8  mov     [rsp+arg_8], rbx
0x1800179cd  mov     [rsp+arg_10], rbp
0x1800179d2  push    rsi
0x1800179d3  push    rdi
0x1800179d4  push    r14
0x1800179d6  sub     rsp, 40h
0x1800179da  mov     esi, r9d
0x1800179dd  movzx   ebp, r8w
0x1800179e1  mov     r14d, edx
0x1800179e4  mov     rdi, rcx
0x1800179e7  cmp     byte ptr [rcx], 0
0x1800179ea  jz      loc_180017AA4
0x1800179f0  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800179f5  test    al, al
0x1800179f7  jnz     loc_180017AA4
0x1800179fd  lea     rbx, [rdi+28h]
0x180017a01  mov     rcx, rbx; SRWLock
0x180017a04  call    cs:__imp_AcquireSRWLockExclusive
0x180017a0b  nop     dword ptr [rax+rax+00h]
0x180017a10  mov     [rsp+58h+var_38], rbx
0x180017a15  xor     eax, eax
0x180017a17  mov     [rsp+58h+var_2A], ax
0x180017a1c  mov     [rsp+58h+var_30], r14d
0x180017a21  mov     [rsp+58h+var_2C], bp
0x180017a26  mov     [rsp+58h+var_28], esi
0x180017a2a  lea     rcx, [rdi+0E8h]; this
0x180017a31  lea     r8d, [rax+0Ch]; unsigned __int64
0x180017a35  lea     rdx, [rsp+58h+var_30]; void *
0x180017a3a  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180017a3f  cmp     byte ptr [rdi+40h], 0
0x180017a43  jnz     short loc_180017A99
0x180017a45  lea     rbx, [rdi+38h]
0x180017a49  cmp     qword ptr [rbx], 0
0x180017a4d  jnz     short loc_180017A87
0x180017a4f  lea     rcx, [rsp+58h+arg_0]; this
0x180017a54  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180017a59  xor     r8d, r8d; pcbe
0x180017a5c  mov     rdx, rdi; pv
0x180017a5f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180017a66  call    cs:__imp_CreateThreadpoolTimer
0x180017a6d  nop     dword ptr [rax+rax+00h]
0x180017a72  mov     rdx, rax
0x180017a75  mov     rcx, rbx
0x180017a78  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180017a7d  lea     rcx, [rsp+58h+arg_0]; this
0x180017a82  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180017a87  mov     r8d, 1388h
0x180017a8d  lea     rdx, [rdi+40h]
0x180017a91  mov     rcx, rbx
0x180017a94  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180017a99  lea     rcx, [rsp+58h+var_38]
0x180017a9e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180017aa3  nop
0x180017aa4  mov     rbx, [rsp+58h+arg_8]
0x180017aa9  mov     rbp, [rsp+58h+arg_10]
0x180017aae  add     rsp, 40h
0x180017ab2  pop     r14
0x180017ab4  pop     rdi
0x180017ab5  pop     rsi
0x180017ab6  retn
```
