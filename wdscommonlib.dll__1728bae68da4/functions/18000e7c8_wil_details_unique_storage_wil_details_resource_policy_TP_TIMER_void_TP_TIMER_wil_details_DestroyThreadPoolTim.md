# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18000e7c8`
- end: `0x18000e859`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `145`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800097fc`
- `0x18000a884`
- `0x18000bff0`

## callees

- `0x18000e7c8`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000e834`
- `KERNEL32!SetLastError` at `0x18000e834`
- `KERNEL32!GetLastError` at `0x18000e7ea`
- `KERNEL32!GetLastError` at `0x18000e7ea`
- `KERNEL32!SetThreadpoolTimer` at `0x18000e803`
- `KERNEL32!SetThreadpoolTimer` at `0x18000e803`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000e817`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000e817`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000e826`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000e826`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        struct _TP_TIMER **a1,
        struct _TP_TIMER *a2)
{
  struct _TP_TIMER *v2; // rsi
  DWORD LastError; // ebx

  v2 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v2, 1);
    CloseThreadpoolTimer(v2);
    SetLastError(LastError);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x18000e7c8  mov     [rsp+arg_0], rbx
0x18000e7cd  mov     [rsp+arg_8], rbp
0x18000e7d2  mov     [rsp+arg_10], rsi
0x18000e7d7  push    rdi
0x18000e7d8  sub     rsp, 20h
0x18000e7dc  mov     rsi, [rcx]
0x18000e7df  mov     rbp, rdx
0x18000e7e2  mov     rdi, rcx
0x18000e7e5  test    rsi, rsi
0x18000e7e8  jz      short loc_18000E840
0x18000e7ea  call    cs:__imp_GetLastError
0x18000e7f1  nop     dword ptr [rax+rax+00h]
0x18000e7f6  xor     r9d, r9d; msWindowLength
0x18000e7f9  xor     r8d, r8d; msPeriod
0x18000e7fc  xor     edx, edx; pftDueTime
0x18000e7fe  mov     rcx, rsi; pti
0x18000e801  mov     ebx, eax
0x18000e803  call    cs:__imp_SetThreadpoolTimer
0x18000e80a  nop     dword ptr [rax+rax+00h]
0x18000e80f  mov     edx, 1; fCancelPendingCallbacks
0x18000e814  mov     rcx, rsi; pti
0x18000e817  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000e81e  nop     dword ptr [rax+rax+00h]
0x18000e823  mov     rcx, rsi; pti
0x18000e826  call    cs:__imp_CloseThreadpoolTimer
0x18000e82d  nop     dword ptr [rax+rax+00h]
0x18000e832  mov     ecx, ebx; dwErrCode
0x18000e834  call    cs:__imp_SetLastError
0x18000e83b  nop     dword ptr [rax+rax+00h]
0x18000e840  mov     rbx, [rsp+28h+arg_0]
0x18000e845  mov     rsi, [rsp+28h+arg_10]
0x18000e84a  mov     [rdi], rbp
0x18000e84d  mov     rbp, [rsp+28h+arg_8]
0x18000e852  add     rsp, 20h
0x18000e856  pop     rdi
0x18000e857  retn
```
