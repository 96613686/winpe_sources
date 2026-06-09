# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180011200`
- end: `0x180011345`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `325`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800564f0`

## callees

- `0x180011200`
- `0x18001c584`
- `0x18001f0ec`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011250`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011281`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011250`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011281`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001123c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001126d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001123c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001126d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011318`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011318`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011304`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011304`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011327`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011327`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::EnabledStateManager::~EnabledStateManager(struct _TP_TIMER **this)
{
  struct _TP_TIMER *v2; // rdi
  HANDLE ProcessHeap; // rax
  struct _TP_TIMER *v4; // rdi
  HANDLE v5; // rax
  void (*v6)(void); // rax
  __int64 v7; // rdx
  struct _TP_TIMER *v8; // rbx

  *(_DWORD *)this = 0;
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    this + 2,
    0);
  wil::details::EnabledStateManager::ProcessShutdown((wil::details::EnabledStateManager *)this);
  v2 = this[13];
  this[13] = 0;
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
  v4 = this[9];
  this[9] = 0;
  if ( v4 )
  {
    v5 = GetProcessHeap();
    HeapFree(v5, 0, v4);
  }
  if ( !this[5] )
  {
    v6 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
    v7 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    goto LABEL_12;
  }
  v6 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( !g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
  {
    v7 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
      goto LABEL_12;
    v6 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  }
  v6();
  v7 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  v6 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
LABEL_12:
  if ( !this[4] )
    goto LABEL_17;
  if ( !v6 )
  {
    if ( !v7 )
      goto LABEL_17;
    v6 = (void (*)(void))v7;
  }
  v6();
LABEL_17:
  v8 = this[2];
  if ( v8 )
  {
    SetThreadpoolTimer(v8, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v8, 1);
    CloseThreadpoolTimer(v8);
  }
}

```

## disassembly

```asm
0x180011200  mov     [rsp+arg_0], rbx
0x180011205  mov     [rsp+arg_8], rsi
0x18001120a  push    rdi
0x18001120b  sub     rsp, 20h
0x18001120f  mov     rbx, rcx
0x180011212  mov     dword ptr [rcx], 0
0x180011218  xor     edx, edx
0x18001121a  add     rcx, 10h
0x18001121e  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180011223  mov     rcx, rbx; this
0x180011226  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18001122b  mov     rdi, [rbx+68h]
0x18001122f  mov     qword ptr [rbx+68h], 0
0x180011237  test    rdi, rdi
0x18001123a  jz      short loc_18001125C
0x18001123c  call    cs:__imp_GetProcessHeap
0x180011243  nop     dword ptr [rax+rax+00h]
0x180011248  mov     rcx, rax; hHeap
0x18001124b  mov     r8, rdi; lpMem
0x18001124e  xor     edx, edx; dwFlags
0x180011250  call    cs:__imp_HeapFree
0x180011257  nop     dword ptr [rax+rax+00h]
0x18001125c  mov     rdi, [rbx+48h]
0x180011260  mov     qword ptr [rbx+48h], 0
0x180011268  test    rdi, rdi
0x18001126b  jz      short loc_18001128D
0x18001126d  call    cs:__imp_GetProcessHeap
0x180011274  nop     dword ptr [rax+rax+00h]
0x180011279  mov     rcx, rax; hHeap
0x18001127c  mov     r8, rdi; lpMem
0x18001127f  xor     edx, edx; dwFlags
0x180011281  call    cs:__imp_HeapFree
0x180011288  nop     dword ptr [rax+rax+00h]
0x18001128d  mov     rcx, [rbx+28h]
0x180011291  test    rcx, rcx
0x180011294  jz      short loc_1800112C6
0x180011296  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18001129d  test    rax, rax
0x1800112a0  jnz     short loc_1800112B1
0x1800112a2  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800112a9  test    rdx, rdx
0x1800112ac  jz      short loc_1800112C4
0x1800112ae  mov     rax, rdx
0x1800112b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112b6  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800112bd  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800112c4  jmp     short loc_1800112D4
0x1800112c6  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800112cd  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800112d4  mov     rcx, [rbx+20h]
0x1800112d8  test    rcx, rcx
0x1800112db  jz      short loc_1800112F0
0x1800112dd  test    rax, rax
0x1800112e0  jnz     short loc_1800112EA
0x1800112e2  test    rdx, rdx
0x1800112e5  jz      short loc_1800112F0
0x1800112e7  mov     rax, rdx
0x1800112ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112ef  nop
0x1800112f0  mov     rbx, [rbx+10h]
0x1800112f4  test    rbx, rbx
0x1800112f7  jz      short loc_180011334
0x1800112f9  xor     r9d, r9d; msWindowLength
0x1800112fc  xor     r8d, r8d; msPeriod
0x1800112ff  xor     edx, edx; pftDueTime
0x180011301  mov     rcx, rbx; pti
0x180011304  call    cs:__imp_SetThreadpoolTimer
0x18001130b  nop     dword ptr [rax+rax+00h]
0x180011310  mov     edx, 1; fCancelPendingCallbacks
0x180011315  mov     rcx, rbx; pti
0x180011318  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001131f  nop     dword ptr [rax+rax+00h]
0x180011324  mov     rcx, rbx; pti
0x180011327  call    cs:__imp_CloseThreadpoolTimer
0x18001132e  nop     dword ptr [rax+rax+00h]
0x180011333  nop
0x180011334  mov     rbx, [rsp+28h+arg_0]
0x180011339  mov     rsi, [rsp+28h+arg_8]
0x18001133e  add     rsp, 20h
0x180011342  pop     rdi
0x180011343  retn
```
