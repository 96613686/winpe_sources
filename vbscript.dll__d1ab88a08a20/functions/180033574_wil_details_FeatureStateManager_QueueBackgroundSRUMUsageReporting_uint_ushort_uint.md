# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180033574`
- end: `0x18003366f`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `251`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180032800`

## callees

- `0x180032698`
- `0x180032a30`
- `0x180032b0c`
- `0x180032bb4`
- `0x180033574`
- `0x180033f08`
- `0x180033f2c`
- `0x180033f50`
- `0x180079490`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x180033619`
- `KERNEL32!CreateThreadpoolTimer` at `0x180033619`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800335b7`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800335b7`

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
0x180033574  push    rbx
0x180033576  push    rbp
0x180033577  push    rsi
0x180033578  push    rdi
0x180033579  push    r14
0x18003357b  sub     rsp, 50h
0x18003357f  mov     rax, cs:__security_cookie
0x180033586  xor     rax, rsp
0x180033589  mov     [rsp+78h+var_38], rax
0x18003358e  cmp     byte ptr [rcx], 0
0x180033591  mov     r14d, r9d
0x180033594  movzx   ebp, r8w
0x180033598  mov     esi, edx
0x18003359a  mov     rdi, rcx
0x18003359d  jz      loc_180033656
0x1800335a3  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800335a8  test    al, al
0x1800335aa  jnz     loc_180033656
0x1800335b0  lea     rbx, [rdi+28h]
0x1800335b4  mov     rcx, rbx; SRWLock
0x1800335b7  call    cs:__imp_AcquireSRWLockExclusive
0x1800335be  nop     dword ptr [rax+rax+00h]
0x1800335c3  xor     eax, eax
0x1800335c5  mov     [rsp+78h+var_50], rbx
0x1800335ca  lea     rcx, [rdi+0E8h]; this
0x1800335d1  mov     [rsp+78h+var_42], ax
0x1800335d6  lea     rdx, [rsp+78h+Source]; Source
0x1800335db  mov     [rsp+78h+Source], esi
0x1800335df  mov     [rsp+78h+var_44], bp
0x1800335e4  lea     r8d, [rax+0Ch]; SourceSize
0x1800335e8  mov     [rsp+78h+var_40], r14d
0x1800335ed  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800335f2  cmp     byte ptr [rdi+40h], 0
0x1800335f6  jnz     short loc_18003364C
0x1800335f8  lea     rbx, [rdi+38h]
0x1800335fc  cmp     qword ptr [rbx], 0
0x180033600  jnz     short loc_18003363A
0x180033602  lea     rcx, [rsp+78h+var_58]; this
0x180033607  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003360c  xor     r8d, r8d; pcbe
0x18003360f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180033616  mov     rdx, rdi; pv
0x180033619  call    cs:__imp_CreateThreadpoolTimer
0x180033620  nop     dword ptr [rax+rax+00h]
0x180033625  mov     rdx, rax
0x180033628  mov     rcx, rbx
0x18003362b  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180033630  lea     rcx, [rsp+78h+var_58]; this
0x180033635  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003363a  mov     r8d, 1388h
0x180033640  lea     rdx, [rdi+40h]
0x180033644  mov     rcx, rbx
0x180033647  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18003364c  lea     rcx, [rsp+78h+var_50]
0x180033651  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180033656  mov     rcx, [rsp+78h+var_38]
0x18003365b  xor     rcx, rsp; StackCookie
0x18003365e  call    __security_check_cookie
0x180033663  add     rsp, 50h
0x180033667  pop     r14
0x180033669  pop     rdi
0x18003366a  pop     rsi
0x18003366b  pop     rbp
0x18003366c  pop     rbx
0x18003366d  retn
```
