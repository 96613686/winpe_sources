# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18002d724`
- end: `0x18002d812`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `238`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800400a0`

## callees

- `0x18002d6e0`
- `0x18002d704`
- `0x18002d724`
- `0x18002d818`
- `0x18002dbe4`
- `0x18002debc`
- `0x18002e038`
- `0x18002f0d8`
- `0x1800767a0`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x18002d7c3`
- `KERNEL32!CreateThreadpoolTimer` at `0x18002d7c3`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002d767`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002d767`

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
  int Source; // [rsp+30h] [rbp-48h] BYREF
  __int16 v12; // [rsp+34h] [rbp-44h]
  __int16 v13; // [rsp+36h] [rbp-42h]
  int v14; // [rsp+38h] [rbp-40h]

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v10 = pv + 40;
    v13 = 0;
    Source = a2;
    v12 = a3;
    v14 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 232), &Source, 0xCu);
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
0x18002d724  push    rbx
0x18002d726  push    rbp
0x18002d727  push    rsi
0x18002d728  push    rdi
0x18002d729  push    r14
0x18002d72b  sub     rsp, 50h
0x18002d72f  mov     rax, cs:__security_cookie
0x18002d736  xor     rax, rsp
0x18002d739  mov     [rsp+78h+var_38], rax
0x18002d73e  cmp     byte ptr [rcx], 0
0x18002d741  mov     r14d, r9d
0x18002d744  movzx   ebp, r8w
0x18002d748  mov     esi, edx
0x18002d74a  mov     rdi, rcx
0x18002d74d  jz      loc_18002D7FA
0x18002d753  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18002d758  test    al, al
0x18002d75a  jnz     loc_18002D7FA
0x18002d760  lea     rbx, [rdi+28h]
0x18002d764  mov     rcx, rbx; SRWLock
0x18002d767  call    cs:__imp_AcquireSRWLockExclusive
0x18002d76d  xor     eax, eax
0x18002d76f  mov     [rsp+78h+var_50], rbx
0x18002d774  lea     rcx, [rdi+0E8h]; this
0x18002d77b  mov     [rsp+78h+var_42], ax
0x18002d780  lea     rdx, [rsp+78h+Source]; Source
0x18002d785  mov     [rsp+78h+Source], esi
0x18002d789  mov     [rsp+78h+var_44], bp
0x18002d78e  lea     r8d, [rax+0Ch]; SourceSize
0x18002d792  mov     [rsp+78h+var_40], r14d
0x18002d797  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18002d79c  cmp     byte ptr [rdi+40h], 0
0x18002d7a0  jnz     short loc_18002D7F0
0x18002d7a2  lea     rbx, [rdi+38h]
0x18002d7a6  cmp     qword ptr [rbx], 0
0x18002d7aa  jnz     short loc_18002D7DE
0x18002d7ac  lea     rcx, [rsp+78h+var_58]; this
0x18002d7b1  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002d7b6  xor     r8d, r8d; pcbe
0x18002d7b9  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002d7c0  mov     rdx, rdi; pv
0x18002d7c3  call    cs:__imp_CreateThreadpoolTimer
0x18002d7c9  mov     rdx, rax
0x18002d7cc  mov     rcx, rbx
0x18002d7cf  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18002d7d4  lea     rcx, [rsp+78h+var_58]; this
0x18002d7d9  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002d7de  mov     r8d, 1388h
0x18002d7e4  lea     rdx, [rdi+40h]
0x18002d7e8  mov     rcx, rbx
0x18002d7eb  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18002d7f0  lea     rcx, [rsp+78h+var_50]
0x18002d7f5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002d7fa  mov     rcx, [rsp+78h+var_38]
0x18002d7ff  xor     rcx, rsp; StackCookie
0x18002d802  call    __security_check_cookie
0x18002d807  add     rsp, 50h
0x18002d80b  pop     r14
0x18002d80d  pop     rdi
0x18002d80e  pop     rsi
0x18002d80f  pop     rbp
0x18002d810  pop     rbx
0x18002d811  retn
```
