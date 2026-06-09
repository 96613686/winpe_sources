# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x180010c80`
- end: `0x180010d11`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `145`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180009da0`
- `0x18000b1b8`
- `0x18000cef0`

## callees

- `0x180010c80`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180010cec`
- `KERNEL32!SetLastError` at `0x180010cec`
- `KERNEL32!GetLastError` at `0x180010ca2`
- `KERNEL32!GetLastError` at `0x180010ca2`
- `KERNEL32!SetThreadpoolTimer` at `0x180010cbb`
- `KERNEL32!SetThreadpoolTimer` at `0x180010cbb`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180010ccf`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180010ccf`
- `KERNEL32!CloseThreadpoolTimer` at `0x180010cde`
- `KERNEL32!CloseThreadpoolTimer` at `0x180010cde`

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
0x180010c80  mov     [rsp+arg_0], rbx
0x180010c85  mov     [rsp+arg_8], rbp
0x180010c8a  mov     [rsp+arg_10], rsi
0x180010c8f  push    rdi
0x180010c90  sub     rsp, 20h
0x180010c94  mov     rsi, [rcx]
0x180010c97  mov     rbp, rdx
0x180010c9a  mov     rdi, rcx
0x180010c9d  test    rsi, rsi
0x180010ca0  jz      short loc_180010CF8
0x180010ca2  call    cs:__imp_GetLastError
0x180010ca9  nop     dword ptr [rax+rax+00h]
0x180010cae  xor     r9d, r9d; msWindowLength
0x180010cb1  xor     r8d, r8d; msPeriod
0x180010cb4  xor     edx, edx; pftDueTime
0x180010cb6  mov     rcx, rsi; pti
0x180010cb9  mov     ebx, eax
0x180010cbb  call    cs:__imp_SetThreadpoolTimer
0x180010cc2  nop     dword ptr [rax+rax+00h]
0x180010cc7  mov     edx, 1; fCancelPendingCallbacks
0x180010ccc  mov     rcx, rsi; pti
0x180010ccf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180010cd6  nop     dword ptr [rax+rax+00h]
0x180010cdb  mov     rcx, rsi; pti
0x180010cde  call    cs:__imp_CloseThreadpoolTimer
0x180010ce5  nop     dword ptr [rax+rax+00h]
0x180010cea  mov     ecx, ebx; dwErrCode
0x180010cec  call    cs:__imp_SetLastError
0x180010cf3  nop     dword ptr [rax+rax+00h]
0x180010cf8  mov     rbx, [rsp+28h+arg_0]
0x180010cfd  mov     rsi, [rsp+28h+arg_10]
0x180010d02  mov     [rdi], rbp
0x180010d05  mov     rbp, [rsp+28h+arg_8]
0x180010d0a  add     rsp, 20h
0x180010d0e  pop     rdi
0x180010d0f  retn
```
