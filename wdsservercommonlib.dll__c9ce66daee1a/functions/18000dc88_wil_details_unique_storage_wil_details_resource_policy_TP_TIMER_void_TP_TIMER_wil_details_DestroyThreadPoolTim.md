# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18000dc88`
- end: `0x18000dd19`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `145`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180008cb8`
- `0x180009d44`
- `0x18000b4b0`

## callees

- `0x18000dc88`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000dcf4`
- `KERNEL32!SetLastError` at `0x18000dcf4`
- `KERNEL32!GetLastError` at `0x18000dcaa`
- `KERNEL32!GetLastError` at `0x18000dcaa`
- `KERNEL32!SetThreadpoolTimer` at `0x18000dcc3`
- `KERNEL32!SetThreadpoolTimer` at `0x18000dcc3`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000dcd7`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000dcd7`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000dce6`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000dce6`

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
0x18000dc88  mov     [rsp+arg_0], rbx
0x18000dc8d  mov     [rsp+arg_8], rbp
0x18000dc92  mov     [rsp+arg_10], rsi
0x18000dc97  push    rdi
0x18000dc98  sub     rsp, 20h
0x18000dc9c  mov     rsi, [rcx]
0x18000dc9f  mov     rbp, rdx
0x18000dca2  mov     rdi, rcx
0x18000dca5  test    rsi, rsi
0x18000dca8  jz      short loc_18000DD00
0x18000dcaa  call    cs:__imp_GetLastError
0x18000dcb1  nop     dword ptr [rax+rax+00h]
0x18000dcb6  xor     r9d, r9d; msWindowLength
0x18000dcb9  xor     r8d, r8d; msPeriod
0x18000dcbc  xor     edx, edx; pftDueTime
0x18000dcbe  mov     rcx, rsi; pti
0x18000dcc1  mov     ebx, eax
0x18000dcc3  call    cs:__imp_SetThreadpoolTimer
0x18000dcca  nop     dword ptr [rax+rax+00h]
0x18000dccf  mov     edx, 1; fCancelPendingCallbacks
0x18000dcd4  mov     rcx, rsi; pti
0x18000dcd7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000dcde  nop     dword ptr [rax+rax+00h]
0x18000dce3  mov     rcx, rsi; pti
0x18000dce6  call    cs:__imp_CloseThreadpoolTimer
0x18000dced  nop     dword ptr [rax+rax+00h]
0x18000dcf2  mov     ecx, ebx; dwErrCode
0x18000dcf4  call    cs:__imp_SetLastError
0x18000dcfb  nop     dword ptr [rax+rax+00h]
0x18000dd00  mov     rbx, [rsp+28h+arg_0]
0x18000dd05  mov     rsi, [rsp+28h+arg_10]
0x18000dd0a  mov     [rdi], rbp
0x18000dd0d  mov     rbp, [rsp+28h+arg_8]
0x18000dd12  add     rsp, 20h
0x18000dd16  pop     rdi
0x18000dd17  retn
```
