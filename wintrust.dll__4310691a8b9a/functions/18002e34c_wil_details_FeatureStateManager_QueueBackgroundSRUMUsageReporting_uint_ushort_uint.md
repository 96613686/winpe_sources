# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18002e34c`
- end: `0x18002e436`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `234`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180035120`

## callees

- `0x180021ba8`
- `0x180021c8c`
- `0x18002222c`
- `0x180022460`
- `0x180025950`
- `0x18002e34c`
- `0x18002e504`
- `0x18002e524`
- `0x18002e568`
- `0x18004deb0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002e3e6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002e3e6`

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
  _BYTE v9[8]; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v10[8]; // [rsp+28h] [rbp-50h] BYREF
  int v11; // [rsp+30h] [rbp-48h] BYREF
  __int16 v12; // [rsp+34h] [rbp-44h]
  __int16 v13; // [rsp+36h] [rbp-42h]
  int v14; // [rsp+38h] [rbp-40h]

  if ( *(_BYTE *)pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    wil::srwlock::lock_exclusive(pv + 5, v10);
    v13 = 0;
    v11 = a2;
    v12 = a3;
    v14 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 29), &v11, 0xCu);
    if ( !*((_BYTE *)pv + 64) )
    {
      if ( !pv[7] )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v9);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          pv + 7,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v9);
      }
      wil::details::EnsureCoalescedTimer_SetTimer(pv + 7, (_BYTE *)pv + 64, 5000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v10);
  }
}

```

## disassembly

```asm
0x18002e34c  push    rbx
0x18002e34e  push    rbp
0x18002e34f  push    rsi
0x18002e350  push    rdi
0x18002e351  sub     rsp, 58h
0x18002e355  mov     rax, cs:__security_cookie
0x18002e35c  xor     rax, rsp
0x18002e35f  mov     [rsp+78h+var_38], rax
0x18002e364  mov     ebp, r9d
0x18002e367  movzx   esi, r8w
0x18002e36b  mov     ebx, edx
0x18002e36d  mov     rdi, rcx
0x18002e370  cmp     byte ptr [rcx], 0
0x18002e373  jz      loc_18002E420
0x18002e379  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18002e37e  test    al, al
0x18002e380  jnz     loc_18002E420
0x18002e386  lea     rcx, [rdi+28h]
0x18002e38a  lea     rdx, [rsp+78h+var_50]
0x18002e38f  call    ?lock_exclusive@srwlock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::srwlock::lock_exclusive(void)
0x18002e394  nop
0x18002e395  xor     eax, eax
0x18002e397  mov     [rsp+78h+var_42], ax
0x18002e39c  mov     [rsp+78h+var_48], ebx
0x18002e3a0  mov     [rsp+78h+var_44], si
0x18002e3a5  mov     [rsp+78h+var_40], ebp
0x18002e3a9  lea     rcx, [rdi+0E8h]; this
0x18002e3b0  lea     r8d, [rax+0Ch]; unsigned __int64
0x18002e3b4  lea     rdx, [rsp+78h+var_48]; void *
0x18002e3b9  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18002e3be  cmp     byte ptr [rdi+40h], 0
0x18002e3c2  jnz     short loc_18002E415
0x18002e3c4  lea     rbx, [rdi+38h]
0x18002e3c8  cmp     qword ptr [rbx], 0
0x18002e3cc  jnz     short loc_18002E402
0x18002e3ce  lea     rcx, [rsp+78h+var_58]; this
0x18002e3d3  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002e3d8  nop
0x18002e3d9  xor     r8d, r8d; pcbe
0x18002e3dc  mov     rdx, rdi; pv
0x18002e3df  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002e3e6  call    cs:__imp_CreateThreadpoolTimer
0x18002e3ec  mov     rdx, rax
0x18002e3ef  mov     rcx, rbx
0x18002e3f2  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18002e3f7  nop
0x18002e3f8  lea     rcx, [rsp+78h+var_58]; this
0x18002e3fd  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002e402  mov     r8d, 1388h
0x18002e408  lea     rdx, [rdi+40h]
0x18002e40c  mov     rcx, rbx
0x18002e40f  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18002e414  nop
0x18002e415  lea     rcx, [rsp+78h+var_50]
0x18002e41a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002e41f  nop
0x18002e420  mov     rcx, [rsp+78h+var_38]
0x18002e425  xor     rcx, rsp; StackCookie
0x18002e428  call    __security_check_cookie
0x18002e42d  add     rsp, 58h
0x18002e431  pop     rdi
0x18002e432  pop     rsi
0x18002e433  pop     rbp
0x18002e434  pop     rbx
0x18002e435  retn
```
