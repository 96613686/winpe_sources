# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180018304`
- end: `0x1800183d2`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `206`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800221f0`

## callees

- `0x180018304`
- `0x1800184a0`
- `0x1800184c0`
- `0x180018504`
- `0x180018524`
- `0x18001854c`
- `0x1800186b0`
- `0x18001b964`
- `0x1800227b0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001838f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001838f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        struct _TP_TIMER **pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  _BYTE v9[8]; // [rsp+20h] [rbp-48h] BYREF
  int v10; // [rsp+28h] [rbp-40h] BYREF
  __int16 v11; // [rsp+2Ch] [rbp-3Ch]
  __int16 v12; // [rsp+2Eh] [rbp-3Ah]
  int v13; // [rsp+30h] [rbp-38h]
  char v14; // [rsp+70h] [rbp+8h] BYREF

  if ( *(_BYTE *)pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    wil::srwlock::lock_exclusive(pv + 5, v9);
    v12 = 0;
    v10 = a2;
    v11 = a3;
    v13 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 29), &v10, 0xCu);
    if ( !*((_BYTE *)pv + 64) )
    {
      if ( !pv[7] )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v14);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          pv + 7,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v14);
      }
      wil::details::EnsureCoalescedTimer_SetTimer(pv + 7, (_BYTE *)pv + 64, 5000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v9);
  }
}

```

## disassembly

```asm
0x180018304  push    rbx
0x180018306  push    rbp
0x180018307  push    rsi
0x180018308  push    rdi
0x180018309  sub     rsp, 48h
0x18001830d  mov     edi, r9d
0x180018310  movzx   esi, r8w
0x180018314  mov     ebp, edx
0x180018316  mov     rbx, rcx
0x180018319  cmp     byte ptr [rcx], 0
0x18001831c  jz      loc_1800183C9
0x180018322  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180018327  test    al, al
0x180018329  jnz     loc_1800183C9
0x18001832f  lea     rcx, [rbx+28h]
0x180018333  lea     rdx, [rsp+68h+var_48]
0x180018338  call    ?lock_exclusive@srwlock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::srwlock::lock_exclusive(void)
0x18001833d  nop
0x18001833e  xor     eax, eax
0x180018340  mov     [rsp+68h+var_3A], ax
0x180018345  mov     [rsp+68h+var_40], ebp
0x180018349  mov     [rsp+68h+var_3C], si
0x18001834e  mov     [rsp+68h+var_38], edi
0x180018352  lea     rcx, [rbx+0E8h]; this
0x180018359  lea     r8d, [rax+0Ch]; unsigned __int64
0x18001835d  lea     rdx, [rsp+68h+var_40]; void *
0x180018362  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180018367  cmp     byte ptr [rbx+40h], 0
0x18001836b  jnz     short loc_1800183BE
0x18001836d  lea     rdi, [rbx+38h]
0x180018371  cmp     qword ptr [rdi], 0
0x180018375  jnz     short loc_1800183AB
0x180018377  lea     rcx, [rsp+68h+arg_0]; this
0x18001837c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180018381  nop
0x180018382  xor     r8d, r8d; pcbe
0x180018385  mov     rdx, rbx; pv
0x180018388  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001838f  call    cs:__imp_CreateThreadpoolTimer
0x180018395  mov     rdx, rax
0x180018398  mov     rcx, rdi
0x18001839b  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800183a0  nop
0x1800183a1  lea     rcx, [rsp+68h+arg_0]; this
0x1800183a6  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800183ab  mov     r8d, 1388h
0x1800183b1  lea     rdx, [rbx+40h]
0x1800183b5  mov     rcx, rdi
0x1800183b8  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800183bd  nop
0x1800183be  lea     rcx, [rsp+68h+var_48]
0x1800183c3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800183c8  nop
0x1800183c9  add     rsp, 48h
0x1800183cd  pop     rdi
0x1800183ce  pop     rsi
0x1800183cf  pop     rbp
0x1800183d0  pop     rbx
0x1800183d1  retn
```
