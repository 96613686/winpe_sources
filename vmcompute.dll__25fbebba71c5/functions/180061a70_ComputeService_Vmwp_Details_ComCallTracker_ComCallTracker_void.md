# ComputeService::Vmwp::Details::ComCallTracker::ComCallTracker(void)

- ea: `0x180061a70`
- end: `0x180061b44`
- name: `??0ComCallTracker@Details@Vmwp@ComputeService@@QEAA@XZ`
- size: `212`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800619b0`

## callees

- `0x180002f50`
- `0x18000d0ec`
- `0x18000eb30`
- `0x180061a70`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180061b0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180061b0c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180061b00`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180061b00`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180061abf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180061abf`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x180061a9d`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x180061a9d`

## string_xrefs

- `0x180061b32`: `onecore\vm\compute\shared\vmwp\lib\workerprocess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_DWORD *__fastcall ComputeService::Vmwp::Details::ComCallTracker::ComCallTracker(_DWORD *pv)
{
  PTP_TIMER ThreadpoolTimer; // rax
  const char *v3; // r9
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *(_QWORD *)pv = 0;
  pv[2] = 0;
  if ( CoEnableCallCancellation(0) >= 0 )
  {
    ThreadpoolTimer = CreateThreadpoolTimer(ComputeService::Vmwp::Details::ComCallTracker::TimerCallback, pv, 0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      pv,
      ThreadpoolTimer);
    if ( !*(_QWORD *)pv )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x6C,
        (unsigned int)"onecore\\vm\\compute\\shared\\vmwp\\lib\\workerprocess.cpp",
        v3);
    pftDueTime = (struct _FILETIME)-1200000000LL;
    SetThreadpoolTimer(*(PTP_TIMER *)pv, &pftDueTime, 0, 0x1388u);
    pv[2] = GetCurrentThreadId();
  }
  return pv;
}

```

## disassembly

```asm
0x180061a70  push    rbx
0x180061a72  sub     rsp, 40h
0x180061a76  mov     rax, cs:__security_cookie
0x180061a7d  xor     rax, rsp
0x180061a80  mov     [rsp+48h+var_10], rax
0x180061a85  mov     rbx, rcx
0x180061a88  mov     [rsp+48h+var_20], rcx
0x180061a8d  mov     qword ptr [rcx], 0
0x180061a94  mov     dword ptr [rcx+8], 0
0x180061a9b  xor     ecx, ecx; pReserved
0x180061a9d  call    cs:__imp_CoEnableCallCancellation
0x180061aa4  nop     dword ptr [rax+rax+00h]
0x180061aa9  test    eax, eax
0x180061aab  js      short loc_180061B1B
0x180061aad  mov     [rsp+48h+var_27], 1
0x180061ab2  xor     r8d, r8d; pcbe
0x180061ab5  mov     rdx, rbx; pv
0x180061ab8  lea     rcx, ?TimerCallback@ComCallTracker@Details@Vmwp@ComputeService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180061abf  call    cs:__imp_CreateThreadpoolTimer
0x180061ac6  nop     dword ptr [rax+rax+00h]
0x180061acb  mov     rdx, rax
0x180061ace  mov     rcx, rbx
0x180061ad1  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180061ad6  cmp     qword ptr [rbx], 0
0x180061ada  setz    al
0x180061add  mov     rcx, [rsp+48h]; this
0x180061ae2  test    al, al
0x180061ae4  jnz     short loc_180061B32
0x180061ae6  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFB8797400h
0x180061aef  mov     r9d, 1388h; msWindowLength
0x180061af5  xor     r8d, r8d; msPeriod
0x180061af8  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180061afd  mov     rcx, [rbx]; pti
0x180061b00  call    cs:__imp_SetThreadpoolTimer
0x180061b07  nop     dword ptr [rax+rax+00h]
0x180061b0c  call    cs:__imp_GetCurrentThreadId
0x180061b13  nop     dword ptr [rax+rax+00h]
0x180061b18  mov     [rbx+8], eax
0x180061b1b  mov     rax, rbx
0x180061b1e  mov     rcx, [rsp+48h+var_10]
0x180061b23  xor     rcx, rsp; StackCookie
0x180061b26  call    __security_check_cookie
0x180061b2b  add     rsp, 40h
0x180061b2f  pop     rbx
0x180061b30  retn
0x180061b32  lea     r8, aOnecoreVmCompu_7; "onecore\\vm\\compute\\shared\\vmwp\\lib"...
0x180061b39  mov     edx, 6Ch ; 'l'; void *
0x180061b3e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
