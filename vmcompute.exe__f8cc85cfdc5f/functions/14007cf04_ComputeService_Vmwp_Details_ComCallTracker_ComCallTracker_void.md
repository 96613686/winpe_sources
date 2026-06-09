# ComputeService::Vmwp::Details::ComCallTracker::ComCallTracker(void)

- ea: `0x14007cf04`
- end: `0x14007cfe4`
- name: `??0ComCallTracker@Details@Vmwp@ComputeService@@QEAA@XZ`
- size: `224`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `40`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14002d4b4`
- `0x14002d680`
- `0x14007c980`
- `0x14007ca70`
- `0x14007cb48`
- `0x14007ccc8`
- `0x14007cdd0`
- `0x1400c67f8`
- `0x1400c723c`
- `0x1400c7690`
- `0x1400c7754`
- `0x1400c7830`
- `0x1400c7978`
- `0x1400c7a40`
- `0x1400c7af0`
- `0x1400c7bb4`
- `0x1400c7cb8`
- `0x1400c7d80`
- `0x1400c7ee0`
- `0x1400c7fe4`
- `0x1400c8278`
- `0x1400c8340`
- `0x1400c8ee0`
- `0x1400c9060`
- `0x1400c9288`
- `0x1400c9514`
- `0x1400c95e0`
- `0x1400c9728`
- `0x1400c9bd8`
- `0x1400c9f5c`
- `0x1400ca10c`
- `0x1400ccf8c`
- `0x1400f76ac`
- `0x1400f78d4`
- `0x1400f79a0`
- `0x1400f7a64`
- `0x1400f7e8c`
- `0x1400f7f58`
- `0x14011edd4`
- `0x14011f728`

## callees

- `0x140064c08`
- `0x14007cf04`
- `0x140080180`
- `0x140106b04`
- `0x1401332f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14007cfbe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14007cfbe`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x14007cf31`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x14007cf31`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14007cf57`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14007cf57`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14007cfb2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14007cfb2`

## string_xrefs

- `0x14007cf7e`: `onecore\vm\compute\shared\vmwp\lib\workerprocess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_DWORD *__fastcall ComputeService::Vmwp::Details::ComCallTracker::ComCallTracker(_DWORD *pv)
{
  PTP_TIMER ThreadpoolTimer; // rax
  unsigned __int64 v3; // rdx
  const char *v4; // r9
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
        v4);
    pftDueTime = wil::FileTime::FromInt64((wil::FileTime *)0xFFFFFFFFB8797400LL, v3);
    SetThreadpoolTimer(*(PTP_TIMER *)pv, &pftDueTime, 0, 0x1388u);
    pv[2] = GetCurrentThreadId();
  }
  return pv;
}

```

## disassembly

```asm
0x14007cf04  push    rbx
0x14007cf06  sub     rsp, 40h
0x14007cf0a  mov     rax, cs:__security_cookie
0x14007cf11  xor     rax, rsp
0x14007cf14  mov     [rsp+48h+var_10], rax
0x14007cf19  mov     rbx, rcx
0x14007cf1c  mov     [rsp+48h+var_20], rcx
0x14007cf21  mov     qword ptr [rcx], 0
0x14007cf28  mov     dword ptr [rcx+8], 0
0x14007cf2f  xor     ecx, ecx; pReserved
0x14007cf31  call    cs:__imp_CoEnableCallCancellation
0x14007cf38  nop     dword ptr [rax+rax+00h]
0x14007cf3d  test    eax, eax
0x14007cf3f  js      loc_14007CFCD
0x14007cf45  mov     [rsp+48h+var_27], 1
0x14007cf4a  xor     r8d, r8d; pcbe
0x14007cf4d  mov     rdx, rbx; pv
0x14007cf50  lea     rcx, ?TimerCallback@ComCallTracker@Details@Vmwp@ComputeService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14007cf57  call    cs:__imp_CreateThreadpoolTimer
0x14007cf5e  nop     dword ptr [rax+rax+00h]
0x14007cf63  mov     rdx, rax
0x14007cf66  mov     rcx, rbx
0x14007cf69  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x14007cf6e  cmp     qword ptr [rbx], 0
0x14007cf72  setz    al
0x14007cf75  mov     rcx, [rsp+48h]; this
0x14007cf7a  test    al, al
0x14007cf7c  jz      short loc_14007CF90
0x14007cf7e  lea     r8, aOnecoreVmCompu_62; "onecore\\vm\\compute\\shared\\vmwp\\lib"...
0x14007cf85  mov     edx, 6Ch ; 'l'; void *
0x14007cf8a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14007cf90  mov     rcx, 0FFFFFFFFB8797400h; this
0x14007cf97  call    ?FromInt64@FileTime@wil@@YA?AU_FILETIME@@_K@Z; wil::FileTime::FromInt64(unsigned __int64)
0x14007cf9c  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x14007cfa1  mov     r9d, 1388h; msWindowLength
0x14007cfa7  xor     r8d, r8d; msPeriod
0x14007cfaa  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x14007cfaf  mov     rcx, [rbx]; pti
0x14007cfb2  call    cs:__imp_SetThreadpoolTimer
0x14007cfb9  nop     dword ptr [rax+rax+00h]
0x14007cfbe  call    cs:__imp_GetCurrentThreadId
0x14007cfc5  nop     dword ptr [rax+rax+00h]
0x14007cfca  mov     [rbx+8], eax
0x14007cfcd  mov     rax, rbx
0x14007cfd0  mov     rcx, [rsp+48h+var_10]
0x14007cfd5  xor     rcx, rsp; StackCookie
0x14007cfd8  call    __security_check_cookie
0x14007cfdd  add     rsp, 40h
0x14007cfe1  pop     rbx
0x14007cfe2  retn
```
