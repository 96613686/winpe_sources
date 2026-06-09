# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18000edd0`
- end: `0x18000ee61`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `145`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000724c`
- `0x18000746c`
- `0x180008804`
- `0x18000ae68`
- `0x18000afb4`

## callees

- `0x18000edd0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000ee3c`
- `KERNEL32!SetLastError` at `0x18000ee3c`
- `KERNEL32!GetLastError` at `0x18000edf2`
- `KERNEL32!GetLastError` at `0x18000edf2`
- `KERNEL32!SetThreadpoolTimer` at `0x18000ee0b`
- `KERNEL32!SetThreadpoolTimer` at `0x18000ee0b`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000ee1f`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000ee1f`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000ee2e`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000ee2e`

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
0x18000edd0  mov     [rsp+arg_0], rbx
0x18000edd5  mov     [rsp+arg_8], rbp
0x18000edda  mov     [rsp+arg_10], rsi
0x18000eddf  push    rdi
0x18000ede0  sub     rsp, 20h
0x18000ede4  mov     rsi, [rcx]
0x18000ede7  mov     rbp, rdx
0x18000edea  mov     rdi, rcx
0x18000eded  test    rsi, rsi
0x18000edf0  jz      short loc_18000EE48
0x18000edf2  call    cs:__imp_GetLastError
0x18000edf9  nop     dword ptr [rax+rax+00h]
0x18000edfe  xor     r9d, r9d; msWindowLength
0x18000ee01  xor     r8d, r8d; msPeriod
0x18000ee04  xor     edx, edx; pftDueTime
0x18000ee06  mov     rcx, rsi; pti
0x18000ee09  mov     ebx, eax
0x18000ee0b  call    cs:__imp_SetThreadpoolTimer
0x18000ee12  nop     dword ptr [rax+rax+00h]
0x18000ee17  mov     edx, 1; fCancelPendingCallbacks
0x18000ee1c  mov     rcx, rsi; pti
0x18000ee1f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000ee26  nop     dword ptr [rax+rax+00h]
0x18000ee2b  mov     rcx, rsi; pti
0x18000ee2e  call    cs:__imp_CloseThreadpoolTimer
0x18000ee35  nop     dword ptr [rax+rax+00h]
0x18000ee3a  mov     ecx, ebx; dwErrCode
0x18000ee3c  call    cs:__imp_SetLastError
0x18000ee43  nop     dword ptr [rax+rax+00h]
0x18000ee48  mov     rbx, [rsp+28h+arg_0]
0x18000ee4d  mov     rsi, [rsp+28h+arg_10]
0x18000ee52  mov     [rdi], rbp
0x18000ee55  mov     rbp, [rsp+28h+arg_8]
0x18000ee5a  add     rsp, 20h
0x18000ee5e  pop     rdi
0x18000ee5f  retn
```
