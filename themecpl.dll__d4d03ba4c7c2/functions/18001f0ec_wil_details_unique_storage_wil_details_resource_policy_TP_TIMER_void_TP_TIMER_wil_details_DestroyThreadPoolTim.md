# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18001f0ec`
- end: `0x18001f166`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `122`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180011200`
- `0x180011434`
- `0x18001b6cc`
- `0x18001c584`
- `0x18001c63c`
- `0x18001c7a0`

## callees

- `0x18001f0ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f14d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f14d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f103`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f103`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001f130`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001f130`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001f11c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001f11c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001f13f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001f13f`

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
0x18001f0ec  push    rbx
0x18001f0ee  push    rbp
0x18001f0ef  push    rsi
0x18001f0f0  push    rdi
0x18001f0f1  sub     rsp, 28h
0x18001f0f5  mov     rsi, [rcx]
0x18001f0f8  mov     rbp, rdx
0x18001f0fb  mov     rdi, rcx
0x18001f0fe  test    rsi, rsi
0x18001f101  jz      short loc_18001F159
0x18001f103  call    cs:__imp_GetLastError
0x18001f10a  nop     dword ptr [rax+rax+00h]
0x18001f10f  xor     r9d, r9d; msWindowLength
0x18001f112  xor     r8d, r8d; msPeriod
0x18001f115  xor     edx, edx; pftDueTime
0x18001f117  mov     rcx, rsi; pti
0x18001f11a  mov     ebx, eax
0x18001f11c  call    cs:__imp_SetThreadpoolTimer
0x18001f123  nop     dword ptr [rax+rax+00h]
0x18001f128  mov     edx, 1; fCancelPendingCallbacks
0x18001f12d  mov     rcx, rsi; pti
0x18001f130  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001f137  nop     dword ptr [rax+rax+00h]
0x18001f13c  mov     rcx, rsi; pti
0x18001f13f  call    cs:__imp_CloseThreadpoolTimer
0x18001f146  nop     dword ptr [rax+rax+00h]
0x18001f14b  mov     ecx, ebx; dwErrCode
0x18001f14d  call    cs:__imp_SetLastError
0x18001f154  nop     dword ptr [rax+rax+00h]
0x18001f159  mov     [rdi], rbp
0x18001f15c  add     rsp, 28h
0x18001f160  pop     rdi
0x18001f161  pop     rsi
0x18001f162  pop     rbp
0x18001f163  pop     rbx
0x18001f164  retn
```
