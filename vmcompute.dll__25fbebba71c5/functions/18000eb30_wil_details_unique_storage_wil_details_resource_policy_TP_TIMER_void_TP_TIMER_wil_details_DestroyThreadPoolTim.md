# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x18000eb30`
- end: `0x18000ebaa`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `122`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180006884`
- `0x180008b68`
- `0x18000aa4c`
- `0x180061a70`
- `0x180061bf8`

## callees

- `0x18000eb30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb47`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000eb91`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000eb91`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000eb83`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000eb83`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000eb60`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000eb60`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000eb74`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000eb74`

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
0x18000eb30  push    rbx
0x18000eb32  push    rbp
0x18000eb33  push    rsi
0x18000eb34  push    rdi
0x18000eb35  sub     rsp, 28h
0x18000eb39  mov     rsi, [rcx]
0x18000eb3c  mov     rbp, rdx
0x18000eb3f  mov     rdi, rcx
0x18000eb42  test    rsi, rsi
0x18000eb45  jz      short loc_18000EB9D
0x18000eb47  call    cs:__imp_GetLastError
0x18000eb4e  nop     dword ptr [rax+rax+00h]
0x18000eb53  xor     r9d, r9d; msWindowLength
0x18000eb56  xor     r8d, r8d; msPeriod
0x18000eb59  xor     edx, edx; pftDueTime
0x18000eb5b  mov     rcx, rsi; pti
0x18000eb5e  mov     ebx, eax
0x18000eb60  call    cs:__imp_SetThreadpoolTimer
0x18000eb67  nop     dword ptr [rax+rax+00h]
0x18000eb6c  mov     edx, 1; fCancelPendingCallbacks
0x18000eb71  mov     rcx, rsi; pti
0x18000eb74  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000eb7b  nop     dword ptr [rax+rax+00h]
0x18000eb80  mov     rcx, rsi; pti
0x18000eb83  call    cs:__imp_CloseThreadpoolTimer
0x18000eb8a  nop     dword ptr [rax+rax+00h]
0x18000eb8f  mov     ecx, ebx; dwErrCode
0x18000eb91  call    cs:__imp_SetLastError
0x18000eb98  nop     dword ptr [rax+rax+00h]
0x18000eb9d  mov     [rdi], rbp
0x18000eba0  add     rsp, 28h
0x18000eba4  pop     rdi
0x18000eba5  pop     rsi
0x18000eba6  pop     rbp
0x18000eba7  pop     rbx
0x18000eba8  retn
```
