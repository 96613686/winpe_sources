# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x18000724c`
- end: `0x18000737d`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `305`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001c600`

## callees

- `0x18000724c`
- `0x18000b5f4`
- `0x18000edd0`
- `0x18001d010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180007285`
- `KERNEL32!GetProcessHeap` at `0x1800072b3`
- `KERNEL32!GetProcessHeap` at `0x180007285`
- `KERNEL32!GetProcessHeap` at `0x1800072b3`
- `KERNEL32!HeapFree` at `0x180007299`
- `KERNEL32!HeapFree` at `0x1800072c7`
- `KERNEL32!HeapFree` at `0x180007299`
- `KERNEL32!HeapFree` at `0x1800072c7`
- `KERNEL32!SetThreadpoolTimer` at `0x18000733d`
- `KERNEL32!SetThreadpoolTimer` at `0x18000733d`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180007351`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180007351`
- `KERNEL32!CloseThreadpoolTimer` at `0x180007360`
- `KERNEL32!CloseThreadpoolTimer` at `0x180007360`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::~EnabledStateManager(struct _TP_TIMER **this)
{
  struct _TP_TIMER *v2; // rdi
  HANDLE ProcessHeap; // rax
  struct _TP_TIMER *v4; // rdi
  HANDLE v5; // rax
  struct _TP_TIMER *v6; // rcx
  __int64 v7; // rdx
  void (*v8)(void); // rax
  struct _TP_TIMER *v9; // rbx

  *(_BYTE *)this = 0;
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    this + 2,
    0);
  *(_BYTE *)this = 0;
  wil::details::EnabledStateManager::RecordCachedUsageUnderLock((wil::details::EnabledStateManager *)this);
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
  v6 = this[5];
  v7 = g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( v6 )
  {
    if ( g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
    {
      ((void (__fastcall *)(struct _TP_TIMER *, __int64))g_wil_details_internalUnsubscribeFeatureStateChangeNotification)(
        v6,
        g_wil_details_internalUnsubscribeFeatureStateChangeNotification);
    }
    else
    {
      v8 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
      if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
        goto LABEL_12;
      ((void (__fastcall *)(struct _TP_TIMER *, _QWORD))g_wil_details_apiUnsubscribeFeatureStateChangeNotification)(
        v6,
        0);
    }
    v7 = g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  }
  v8 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
LABEL_12:
  if ( !this[4] )
    goto LABEL_17;
  if ( v7 )
  {
    v8 = (void (*)(void))v7;
  }
  else if ( !v8 )
  {
    goto LABEL_17;
  }
  v8();
LABEL_17:
  v9 = this[2];
  if ( v9 )
  {
    SetThreadpoolTimer(v9, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v9, 1);
    CloseThreadpoolTimer(v9);
  }
}

```

## disassembly

```asm
0x18000724c  mov     [rsp+arg_0], rbx
0x180007251  mov     [rsp+arg_8], rsi
0x180007256  push    rdi
0x180007257  sub     rsp, 20h
0x18000725b  mov     rbx, rcx
0x18000725e  mov     byte ptr [rcx], 0
0x180007261  add     rcx, 10h
0x180007265  xor     edx, edx
0x180007267  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000726c  mov     rcx, rbx; this
0x18000726f  mov     byte ptr [rbx], 0
0x180007272  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXXZ; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(void)
0x180007277  mov     rdi, [rbx+68h]
0x18000727b  and     qword ptr [rbx+68h], 0
0x180007280  test    rdi, rdi
0x180007283  jz      short loc_1800072A5
0x180007285  call    cs:__imp_GetProcessHeap
0x18000728c  nop     dword ptr [rax+rax+00h]
0x180007291  mov     r8, rdi; lpMem
0x180007294  xor     edx, edx; dwFlags
0x180007296  mov     rcx, rax; hHeap
0x180007299  call    cs:__imp_HeapFree
0x1800072a0  nop     dword ptr [rax+rax+00h]
0x1800072a5  mov     rdi, [rbx+48h]
0x1800072a9  and     qword ptr [rbx+48h], 0
0x1800072ae  test    rdi, rdi
0x1800072b1  jz      short loc_1800072D3
0x1800072b3  call    cs:__imp_GetProcessHeap
0x1800072ba  nop     dword ptr [rax+rax+00h]
0x1800072bf  mov     r8, rdi; lpMem
0x1800072c2  xor     edx, edx; dwFlags
0x1800072c4  mov     rcx, rax; hHeap
0x1800072c7  call    cs:__imp_HeapFree
0x1800072ce  nop     dword ptr [rax+rax+00h]
0x1800072d3  mov     rcx, [rbx+28h]
0x1800072d7  mov     rdx, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800072de  test    rcx, rcx
0x1800072e1  jz      short loc_180007305
0x1800072e3  test    rdx, rdx
0x1800072e6  jz      short loc_1800072ED
0x1800072e8  mov     rax, rdx
0x1800072eb  jmp     short loc_1800072F9
0x1800072ed  mov     rax, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800072f4  test    rax, rax
0x1800072f7  jz      short loc_18000730C
0x1800072f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072fe  mov     rdx, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180007305  mov     rax, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000730c  mov     rcx, [rbx+20h]
0x180007310  test    rcx, rcx
0x180007313  jz      short loc_180007329
0x180007315  test    rdx, rdx
0x180007318  jz      short loc_18000731F
0x18000731a  mov     rax, rdx
0x18000731d  jmp     short loc_180007324
0x18000731f  test    rax, rax
0x180007322  jz      short loc_180007329
0x180007324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007329  mov     rbx, [rbx+10h]
0x18000732d  test    rbx, rbx
0x180007330  jz      short loc_18000736C
0x180007332  xor     r9d, r9d; msWindowLength
0x180007335  xor     r8d, r8d; msPeriod
0x180007338  xor     edx, edx; pftDueTime
0x18000733a  mov     rcx, rbx; pti
0x18000733d  call    cs:__imp_SetThreadpoolTimer
0x180007344  nop     dword ptr [rax+rax+00h]
0x180007349  mov     edx, 1; fCancelPendingCallbacks
0x18000734e  mov     rcx, rbx; pti
0x180007351  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007358  nop     dword ptr [rax+rax+00h]
0x18000735d  mov     rcx, rbx; pti
0x180007360  call    cs:__imp_CloseThreadpoolTimer
0x180007367  nop     dword ptr [rax+rax+00h]
0x18000736c  mov     rbx, [rsp+28h+arg_0]
0x180007371  mov     rsi, [rsp+28h+arg_8]
0x180007376  add     rsp, 20h
0x18000737a  pop     rdi
0x18000737b  retn
```
