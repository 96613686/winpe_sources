# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800247a8`
- end: `0x1800248a3`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `251`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18002de70`

## callees

- `0x1800247a8`
- `0x180024a28`
- `0x180024a4c`
- `0x180024a94`
- `0x180024ac0`
- `0x180024c60`
- `0x180024d20`
- `0x1800287d0`
- `0x18002e454`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800247eb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800247eb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002484d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002484d`

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
0x1800247a8  push    rbx
0x1800247aa  push    rbp
0x1800247ab  push    rsi
0x1800247ac  push    rdi
0x1800247ad  push    r14
0x1800247af  sub     rsp, 50h
0x1800247b3  mov     rax, cs:__security_cookie
0x1800247ba  xor     rax, rsp
0x1800247bd  mov     [rsp+78h+var_38], rax
0x1800247c2  cmp     byte ptr [rcx], 0
0x1800247c5  mov     r14d, r9d
0x1800247c8  movzx   ebp, r8w
0x1800247cc  mov     esi, edx
0x1800247ce  mov     rdi, rcx
0x1800247d1  jz      loc_18002488A
0x1800247d7  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800247dc  test    al, al
0x1800247de  jnz     loc_18002488A
0x1800247e4  lea     rbx, [rdi+28h]
0x1800247e8  mov     rcx, rbx; SRWLock
0x1800247eb  call    cs:__imp_AcquireSRWLockExclusive
0x1800247f2  nop     dword ptr [rax+rax+00h]
0x1800247f7  xor     eax, eax
0x1800247f9  mov     [rsp+78h+var_50], rbx
0x1800247fe  lea     rcx, [rdi+0E8h]; this
0x180024805  mov     [rsp+78h+var_42], ax
0x18002480a  lea     rdx, [rsp+78h+var_48]; void *
0x18002480f  mov     [rsp+78h+var_48], esi
0x180024813  mov     [rsp+78h+var_44], bp
0x180024818  lea     r8d, [rax+0Ch]; unsigned __int64
0x18002481c  mov     [rsp+78h+var_40], r14d
0x180024821  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180024826  cmp     byte ptr [rdi+40h], 0
0x18002482a  jnz     short loc_180024880
0x18002482c  lea     rbx, [rdi+38h]
0x180024830  cmp     qword ptr [rbx], 0
0x180024834  jnz     short loc_18002486E
0x180024836  lea     rcx, [rsp+78h+var_58]; this
0x18002483b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180024840  xor     r8d, r8d; pcbe
0x180024843  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002484a  mov     rdx, rdi; pv
0x18002484d  call    cs:__imp_CreateThreadpoolTimer
0x180024854  nop     dword ptr [rax+rax+00h]
0x180024859  mov     rdx, rax
0x18002485c  mov     rcx, rbx
0x18002485f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180024864  lea     rcx, [rsp+78h+var_58]; this
0x180024869  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002486e  mov     r8d, 1388h
0x180024874  lea     rdx, [rdi+40h]
0x180024878  mov     rcx, rbx
0x18002487b  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180024880  lea     rcx, [rsp+78h+var_50]
0x180024885  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002488a  mov     rcx, [rsp+78h+var_38]
0x18002488f  xor     rcx, rsp; StackCookie
0x180024892  call    __security_check_cookie
0x180024897  add     rsp, 50h
0x18002489b  pop     r14
0x18002489d  pop     rdi
0x18002489e  pop     rsi
0x18002489f  pop     rbp
0x1800248a0  pop     rbx
0x1800248a1  retn
```
