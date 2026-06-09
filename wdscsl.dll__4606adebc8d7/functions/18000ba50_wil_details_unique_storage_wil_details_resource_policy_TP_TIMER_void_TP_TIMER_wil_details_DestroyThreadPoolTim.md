# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18000ba50`
- end: `0x18000bae1`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `145`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180003694`
- `0x1800054a8`
- `0x180008698`

## callees

- `0x18000ba50`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000babc`
- `KERNEL32!SetLastError` at `0x18000babc`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000ba9f`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000ba9f`
- `KERNEL32!GetLastError` at `0x18000ba72`
- `KERNEL32!GetLastError` at `0x18000ba72`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000baae`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000baae`
- `KERNEL32!SetThreadpoolTimer` at `0x18000ba8b`
- `KERNEL32!SetThreadpoolTimer` at `0x18000ba8b`

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
0x18000ba50  mov     [rsp+arg_0], rbx
0x18000ba55  mov     [rsp+arg_8], rbp
0x18000ba5a  mov     [rsp+arg_10], rsi
0x18000ba5f  push    rdi
0x18000ba60  sub     rsp, 20h
0x18000ba64  mov     rsi, [rcx]
0x18000ba67  mov     rbp, rdx
0x18000ba6a  mov     rdi, rcx
0x18000ba6d  test    rsi, rsi
0x18000ba70  jz      short loc_18000BAC8
0x18000ba72  call    cs:__imp_GetLastError
0x18000ba79  nop     dword ptr [rax+rax+00h]
0x18000ba7e  xor     r9d, r9d; msWindowLength
0x18000ba81  xor     r8d, r8d; msPeriod
0x18000ba84  xor     edx, edx; pftDueTime
0x18000ba86  mov     rcx, rsi; pti
0x18000ba89  mov     ebx, eax
0x18000ba8b  call    cs:__imp_SetThreadpoolTimer
0x18000ba92  nop     dword ptr [rax+rax+00h]
0x18000ba97  mov     edx, 1; fCancelPendingCallbacks
0x18000ba9c  mov     rcx, rsi; pti
0x18000ba9f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000baa6  nop     dword ptr [rax+rax+00h]
0x18000baab  mov     rcx, rsi; pti
0x18000baae  call    cs:__imp_CloseThreadpoolTimer
0x18000bab5  nop     dword ptr [rax+rax+00h]
0x18000baba  mov     ecx, ebx; dwErrCode
0x18000babc  call    cs:__imp_SetLastError
0x18000bac3  nop     dword ptr [rax+rax+00h]
0x18000bac8  mov     rbx, [rsp+28h+arg_0]
0x18000bacd  mov     rsi, [rsp+28h+arg_10]
0x18000bad2  mov     [rdi], rbp
0x18000bad5  mov     rbp, [rsp+28h+arg_8]
0x18000bada  add     rsp, 20h
0x18000bade  pop     rdi
0x18000badf  retn
```
