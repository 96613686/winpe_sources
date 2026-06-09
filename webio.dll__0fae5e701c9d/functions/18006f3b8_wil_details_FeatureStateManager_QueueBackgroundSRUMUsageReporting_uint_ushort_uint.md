# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18006f3b8`
- end: `0x18006f4b3`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `251`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180089560`

## callees

- `0x18006f3b8`
- `0x18006f59c`
- `0x18006f5c0`
- `0x18006f624`
- `0x18006f648`
- `0x18006f730`
- `0x18006f864`
- `0x18006fcec`
- `0x1800722f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006f3fb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006f3fb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18006f45d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18006f45d`

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
0x18006f3b8  push    rbx
0x18006f3ba  push    rbp
0x18006f3bb  push    rsi
0x18006f3bc  push    rdi
0x18006f3bd  push    r14
0x18006f3bf  sub     rsp, 50h
0x18006f3c3  mov     rax, cs:__security_cookie
0x18006f3ca  xor     rax, rsp
0x18006f3cd  mov     [rsp+78h+var_38], rax
0x18006f3d2  cmp     byte ptr [rcx], 0
0x18006f3d5  mov     r14d, r9d
0x18006f3d8  movzx   ebp, r8w
0x18006f3dc  mov     esi, edx
0x18006f3de  mov     rdi, rcx
0x18006f3e1  jz      loc_18006F49A
0x18006f3e7  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18006f3ec  test    al, al
0x18006f3ee  jnz     loc_18006F49A
0x18006f3f4  lea     rbx, [rdi+28h]
0x18006f3f8  mov     rcx, rbx; SRWLock
0x18006f3fb  call    cs:__imp_AcquireSRWLockExclusive
0x18006f402  nop     dword ptr [rax+rax+00h]
0x18006f407  xor     eax, eax
0x18006f409  mov     [rsp+78h+var_50], rbx
0x18006f40e  lea     rcx, [rdi+0E8h]; this
0x18006f415  mov     [rsp+78h+var_42], ax
0x18006f41a  lea     rdx, [rsp+78h+var_48]; void *
0x18006f41f  mov     [rsp+78h+var_48], esi
0x18006f423  mov     [rsp+78h+var_44], bp
0x18006f428  lea     r8d, [rax+0Ch]; unsigned __int64
0x18006f42c  mov     [rsp+78h+var_40], r14d
0x18006f431  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18006f436  cmp     byte ptr [rdi+40h], 0
0x18006f43a  jnz     short loc_18006F490
0x18006f43c  lea     rbx, [rdi+38h]
0x18006f440  cmp     qword ptr [rbx], 0
0x18006f444  jnz     short loc_18006F47E
0x18006f446  lea     rcx, [rsp+78h+var_58]; this
0x18006f44b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18006f450  xor     r8d, r8d; pcbe
0x18006f453  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18006f45a  mov     rdx, rdi; pv
0x18006f45d  call    cs:__imp_CreateThreadpoolTimer
0x18006f464  nop     dword ptr [rax+rax+00h]
0x18006f469  mov     rdx, rax
0x18006f46c  mov     rcx, rbx
0x18006f46f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18006f474  lea     rcx, [rsp+78h+var_58]; this
0x18006f479  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18006f47e  mov     r8d, 1388h
0x18006f484  lea     rdx, [rdi+40h]
0x18006f488  mov     rcx, rbx
0x18006f48b  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18006f490  lea     rcx, [rsp+78h+var_50]
0x18006f495  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18006f49a  mov     rcx, [rsp+78h+var_38]
0x18006f49f  xor     rcx, rsp; StackCookie
0x18006f4a2  call    __security_check_cookie
0x18006f4a7  add     rsp, 50h
0x18006f4ab  pop     r14
0x18006f4ad  pop     rdi
0x18006f4ae  pop     rsi
0x18006f4af  pop     rbp
0x18006f4b0  pop     rbx
0x18006f4b1  retn
```
