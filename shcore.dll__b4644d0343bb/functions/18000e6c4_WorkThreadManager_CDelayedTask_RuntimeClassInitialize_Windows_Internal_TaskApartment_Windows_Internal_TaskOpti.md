# WorkThreadManager::CDelayedTask::RuntimeClassInitialize(Windows::Internal::TaskApartment,Windows::Internal::TaskOptions,ulong,ulong,Windows::Internal::IComPoolTask *)

- ea: `0x18000e6c4`
- end: `0x18000e7ea`
- name: `?RuntimeClassInitialize@CDelayedTask@WorkThreadManager@@QEAAJW4TaskApartment@Internal@Windows@@W4TaskOptions@45@KKPEAUIComPoolTask@45@@Z`
- size: `294`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000e49c`

## callees

- `0x18000e6c4`
- `0x18000e7f0`
- `0x18000edf0`
- `0x18000f808`
- `0x18000f900`
- `0x180053bd8`
- `0x180054410`
- `0x180068d9c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000e73d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000e73d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e795`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e795`

## string_xrefs

- `0x18000e7a4`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`
- `0x18000e7cd`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`

## pseudocode

```c
__int64 __fastcall WorkThreadManager::CDelayedTask::RuntimeClassInitialize(
        PTP_TIMER *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5)
{
  struct _TP_TIMER *v9; // rax
  unsigned int v10; // edx
  WorkThreadManager::TaskData *v11; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  const char *v13; // r9
  int v15; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  _FILETIME pftDueTime; // [rsp+60h] [rbp+8h] BYREF

  v9 = (struct _TP_TIMER *)operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v9 )
  {
    v15 = 0;
    v9 = (struct _TP_TIMER *)WorkThreadManager::TaskData::TaskData(v9, a2, a3, a4);
  }
  v11 = a1[4];
  a1[4] = v9;
  if ( v11 )
    WorkThreadManager::TaskData::`scalar deleting destructor'(v11, v10);
  if ( a1[4] )
  {
    ThreadpoolTimer = CreateThreadpoolTimer(_lambda_c517a792861221b2815f232f7f0c7973_::_lambda_invoker_cdecl_, a1, 0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      a1 + 3,
      ThreadpoolTimer);
    if ( a1[3] )
    {
      pftDueTime = (_FILETIME)(-10000LL * a5);
      Microsoft::WRL::ComPtr<IRWLock>::operator=(a1 + 5, a1);
      SetThreadpoolTimer(a1[3], &pftDueTime, 0, 0);
      return 0;
    }
    else
    {
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x19C,
               (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
               v13);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x191,
      (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
      (const char *)0x8007000ELL,
      v15);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18000e6c4  push    rbx
0x18000e6c6  push    rbp
0x18000e6c7  push    rsi
0x18000e6c8  push    rdi
0x18000e6c9  sub     rsp, 38h
0x18000e6cd  mov     ebp, edx
0x18000e6cf  mov     rbx, rcx
0x18000e6d2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e6d9  mov     ecx, 48h ; 'H'; unsigned __int64
0x18000e6de  mov     edi, r9d
0x18000e6e1  mov     esi, r8d
0x18000e6e4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000e6e9  test    rax, rax
0x18000e6ec  jz      short loc_18000E714
0x18000e6ee  mov     r10, [rsp+58h+arg_28]
0x18000e6f6  mov     r9d, edi
0x18000e6f9  mov     [rsp+58h+var_30], r10
0x18000e6fe  mov     r8d, esi
0x18000e701  mov     edx, ebp
0x18000e703  mov     qword ptr [rsp+58h+var_38], 0; int
0x18000e70c  mov     rcx, rax
0x18000e70f  call    ??0TaskData@WorkThreadManager@@QEAA@W4TaskApartment@Internal@Windows@@W4TaskOptions@34@KPEAXPEAUIComPoolTask@34@@Z; WorkThreadManager::TaskData::TaskData(Windows::Internal::TaskApartment,Windows::Internal::TaskOptions,ulong,void *,Windows::Internal::IComPoolTask *)
0x18000e714  mov     rcx, [rbx+20h]; this
0x18000e718  mov     [rbx+20h], rax
0x18000e71c  test    rcx, rcx
0x18000e71f  jnz     loc_18000E7E0
0x18000e725  cmp     qword ptr [rbx+20h], 0
0x18000e72a  jz      short loc_18000E79F
0x18000e72c  xor     r8d, r8d; pcbe
0x18000e72f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_c517a792861221b2815f232f7f0c7973_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000e736  mov     rdx, rbx; pv
0x18000e739  lea     rdi, [rbx+18h]
0x18000e73d  call    cs:__imp_CreateThreadpoolTimer
0x18000e743  mov     rdx, rax
0x18000e746  mov     rcx, rdi
0x18000e749  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000e74e  cmp     qword ptr [rdi], 0
0x18000e752  jz      short loc_18000E7C8
0x18000e754  mov     eax, [rsp+58h+arg_20]
0x18000e75b  lea     rcx, [rbx+28h]
0x18000e75f  imul    rax, 0FFFFFFFFFFFFD8F0h
0x18000e766  mov     rdx, rax
0x18000e769  mov     [rsp+58h+pftDueTime.dwLowDateTime], eax
0x18000e76d  shr     rdx, 20h
0x18000e771  mov     [rsp+58h+pftDueTime.dwHighDateTime], edx
0x18000e775  mov     rdx, rbx
0x18000e778  mov     rax, qword ptr [rsp+58h+pftDueTime.dwLowDateTime]
0x18000e77d  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x18000e782  call    ??4?$ComPtr@UIRWLock@@@WRL@Microsoft@@QEAAAEAV012@PEAUIRWLock@@@Z; Microsoft::WRL::ComPtr<IRWLock>::operator=(IRWLock *)
0x18000e787  mov     rcx, [rdi]; pti
0x18000e78a  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x18000e78f  xor     r9d, r9d; msWindowLength
0x18000e792  xor     r8d, r8d; msPeriod
0x18000e795  call    cs:__imp_SetThreadpoolTimer
0x18000e79b  xor     eax, eax
0x18000e79d  jmp     short loc_18000E7BF
0x18000e79f  mov     rcx, [rsp+58h]; this
0x18000e7a4  lea     r8, aOnecoreShellSh_7; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x18000e7ab  mov     ebx, 8007000Eh
0x18000e7b0  mov     edx, 191h; void *
0x18000e7b5  mov     r9d, ebx; char *
0x18000e7b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e7bd  mov     eax, ebx
0x18000e7bf  add     rsp, 38h
0x18000e7c3  pop     rdi
0x18000e7c4  pop     rsi
0x18000e7c5  pop     rbp
0x18000e7c6  pop     rbx
0x18000e7c7  retn
0x18000e7c8  mov     rcx, [rsp+58h]; this
0x18000e7cd  lea     r8, aOnecoreShellSh_7; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x18000e7d4  mov     edx, 19Ch; void *
0x18000e7d9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e7de  jmp     short loc_18000E7BF
0x18000e7e0  call    ??_GTaskData@WorkThreadManager@@QEAAPEAXI@Z; WorkThreadManager::TaskData::`scalar deleting destructor'(uint)
0x18000e7e5  jmp     loc_18000E725
```
