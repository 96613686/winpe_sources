# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000a0a4`
- end: `0x18000a192`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `238`
- prototype: `void __fastcall(char *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000b8c0`

## callees

- `0x1800078cc`
- `0x180007b44`
- `0x180007e30`
- `0x1800083f4`
- `0x18000a070`
- `0x18000a0a4`
- `0x18000be9c`
- `0x18000bfa8`
- `0x18000cff0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a0e7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a0e7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a143`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a143`

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
    wil::details_abi::heap_buffer::push_back((void **)pv + 29, &v11, 0xCu);
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
0x18000a0a4  push    rbx
0x18000a0a6  push    rbp
0x18000a0a7  push    rsi
0x18000a0a8  push    rdi
0x18000a0a9  push    r14
0x18000a0ab  sub     rsp, 50h
0x18000a0af  mov     rax, cs:__security_cookie
0x18000a0b6  xor     rax, rsp
0x18000a0b9  mov     [rsp+78h+var_38], rax
0x18000a0be  cmp     byte ptr [rcx], 0
0x18000a0c1  mov     r14d, r9d
0x18000a0c4  movzx   ebp, r8w
0x18000a0c8  mov     esi, edx
0x18000a0ca  mov     rdi, rcx
0x18000a0cd  jz      loc_18000A17A
0x18000a0d3  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000a0d8  test    al, al
0x18000a0da  jnz     loc_18000A17A
0x18000a0e0  lea     rbx, [rdi+28h]
0x18000a0e4  mov     rcx, rbx; SRWLock
0x18000a0e7  call    cs:__imp_AcquireSRWLockExclusive
0x18000a0ed  xor     eax, eax
0x18000a0ef  mov     [rsp+78h+var_50], rbx
0x18000a0f4  lea     rcx, [rdi+0E8h]; this
0x18000a0fb  mov     [rsp+78h+var_42], ax
0x18000a100  lea     rdx, [rsp+78h+var_48]; void *
0x18000a105  mov     [rsp+78h+var_48], esi
0x18000a109  mov     [rsp+78h+var_44], bp
0x18000a10e  lea     r8d, [rax+0Ch]; unsigned __int64
0x18000a112  mov     [rsp+78h+var_40], r14d
0x18000a117  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000a11c  cmp     byte ptr [rdi+40h], 0
0x18000a120  jnz     short loc_18000A170
0x18000a122  lea     rbx, [rdi+38h]
0x18000a126  cmp     qword ptr [rbx], 0
0x18000a12a  jnz     short loc_18000A15E
0x18000a12c  lea     rcx, [rsp+78h+var_58]; this
0x18000a131  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000a136  xor     r8d, r8d; pcbe
0x18000a139  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000a140  mov     rdx, rdi; pv
0x18000a143  call    cs:__imp_CreateThreadpoolTimer
0x18000a149  mov     rdx, rax
0x18000a14c  mov     rcx, rbx
0x18000a14f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000a154  lea     rcx, [rsp+78h+var_58]; this
0x18000a159  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000a15e  mov     r8d, 1388h
0x18000a164  lea     rdx, [rdi+40h]
0x18000a168  mov     rcx, rbx
0x18000a16b  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18000a170  lea     rcx, [rsp+78h+var_50]
0x18000a175  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000a17a  mov     rcx, [rsp+78h+var_38]
0x18000a17f  xor     rcx, rsp; StackCookie
0x18000a182  call    __security_check_cookie
0x18000a187  add     rsp, 50h
0x18000a18b  pop     r14
0x18000a18d  pop     rdi
0x18000a18e  pop     rsi
0x18000a18f  pop     rbp
0x18000a190  pop     rbx
0x18000a191  retn
```
