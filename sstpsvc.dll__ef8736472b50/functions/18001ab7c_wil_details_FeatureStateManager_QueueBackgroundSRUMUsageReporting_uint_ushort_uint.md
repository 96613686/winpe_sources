# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18001ab7c`
- end: `0x18001ac77`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `251`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18001c3c0`

## callees

- `0x180018570`
- `0x180018778`
- `0x180018a00`
- `0x180019098`
- `0x18001ab48`
- `0x18001ab7c`
- `0x18001c89c`
- `0x18001c9b8`
- `0x18001d210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001abbf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001abbf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001ac21`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001ac21`

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
0x18001ab7c  push    rbx
0x18001ab7e  push    rbp
0x18001ab7f  push    rsi
0x18001ab80  push    rdi
0x18001ab81  push    r14
0x18001ab83  sub     rsp, 50h
0x18001ab87  mov     rax, cs:__security_cookie
0x18001ab8e  xor     rax, rsp
0x18001ab91  mov     [rsp+78h+var_38], rax
0x18001ab96  cmp     byte ptr [rcx], 0
0x18001ab99  mov     r14d, r9d
0x18001ab9c  movzx   ebp, r8w
0x18001aba0  mov     esi, edx
0x18001aba2  mov     rdi, rcx
0x18001aba5  jz      loc_18001AC5E
0x18001abab  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001abb0  test    al, al
0x18001abb2  jnz     loc_18001AC5E
0x18001abb8  lea     rbx, [rdi+28h]
0x18001abbc  mov     rcx, rbx; SRWLock
0x18001abbf  call    cs:__imp_AcquireSRWLockExclusive
0x18001abc6  nop     dword ptr [rax+rax+00h]
0x18001abcb  xor     eax, eax
0x18001abcd  mov     [rsp+78h+var_50], rbx
0x18001abd2  lea     rcx, [rdi+0E8h]; this
0x18001abd9  mov     [rsp+78h+var_42], ax
0x18001abde  lea     rdx, [rsp+78h+var_48]; void *
0x18001abe3  mov     [rsp+78h+var_48], esi
0x18001abe7  mov     [rsp+78h+var_44], bp
0x18001abec  lea     r8d, [rax+0Ch]; unsigned __int64
0x18001abf0  mov     [rsp+78h+var_40], r14d
0x18001abf5  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001abfa  cmp     byte ptr [rdi+40h], 0
0x18001abfe  jnz     short loc_18001AC54
0x18001ac00  lea     rbx, [rdi+38h]
0x18001ac04  cmp     qword ptr [rbx], 0
0x18001ac08  jnz     short loc_18001AC42
0x18001ac0a  lea     rcx, [rsp+78h+var_58]; this
0x18001ac0f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001ac14  xor     r8d, r8d; pcbe
0x18001ac17  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001ac1e  mov     rdx, rdi; pv
0x18001ac21  call    cs:__imp_CreateThreadpoolTimer
0x18001ac28  nop     dword ptr [rax+rax+00h]
0x18001ac2d  mov     rdx, rax
0x18001ac30  mov     rcx, rbx
0x18001ac33  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001ac38  lea     rcx, [rsp+78h+var_58]; this
0x18001ac3d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001ac42  mov     r8d, 1388h
0x18001ac48  lea     rdx, [rdi+40h]
0x18001ac4c  mov     rcx, rbx
0x18001ac4f  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18001ac54  lea     rcx, [rsp+78h+var_50]
0x18001ac59  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001ac5e  mov     rcx, [rsp+78h+var_38]
0x18001ac63  xor     rcx, rsp; StackCookie
0x18001ac66  call    __security_check_cookie
0x18001ac6b  add     rsp, 50h
0x18001ac6f  pop     r14
0x18001ac71  pop     rdi
0x18001ac72  pop     rsi
0x18001ac73  pop     rbp
0x18001ac74  pop     rbx
0x18001ac75  retn
```
