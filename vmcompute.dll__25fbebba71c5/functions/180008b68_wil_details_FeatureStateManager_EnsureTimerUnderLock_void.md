# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180008b68`
- end: `0x180008c2c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `196`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000af04`

## callees

- `0x180002f50`
- `0x180008b68`
- `0x18000eb30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b99`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008bcd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008bcd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008bfe`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008bfe`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008bb4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008bb4`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::EnsureTimerUnderLock(struct _TP_TIMER **pv)
{
  struct _TP_TIMER **v2; // rsi
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v5; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-18h] BYREF

  if ( !*((_BYTE *)pv + 65) )
  {
    v2 = pv + 6;
    if ( !pv[6] )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_, pv, 0);
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        v2,
        ThreadpoolTimer);
      SetLastError(LastError);
    }
    v5 = *v2;
    if ( *v2 )
    {
      pftDueTime = (struct _FILETIME)-3000000000LL;
      SetThreadpoolTimer(v5, &pftDueTime, 0, 0x124F8u);
      *((_BYTE *)pv + 65) = 1;
    }
  }
}

```

## disassembly

```asm
0x180008b68  mov     [rsp+arg_8], rbx
0x180008b6d  mov     [rsp+arg_10], rsi
0x180008b72  push    rdi
0x180008b73  sub     rsp, 30h
0x180008b77  mov     rax, cs:__security_cookie
0x180008b7e  xor     rax, rsp
0x180008b81  mov     [rsp+38h+var_10], rax
0x180008b86  cmp     byte ptr [rcx+41h], 0
0x180008b8a  mov     rdi, rcx
0x180008b8d  jnz     short loc_180008C0E
0x180008b8f  lea     rsi, [rcx+30h]
0x180008b93  cmp     qword ptr [rsi], 0
0x180008b97  jnz     short loc_180008BD9
0x180008b99  call    cs:__imp_GetLastError
0x180008ba0  nop     dword ptr [rax+rax+00h]
0x180008ba5  xor     r8d, r8d; pcbe
0x180008ba8  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180008baf  mov     rdx, rdi; pv
0x180008bb2  mov     ebx, eax
0x180008bb4  call    cs:__imp_CreateThreadpoolTimer
0x180008bbb  nop     dword ptr [rax+rax+00h]
0x180008bc0  mov     rdx, rax
0x180008bc3  mov     rcx, rsi
0x180008bc6  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180008bcb  mov     ecx, ebx; dwErrCode
0x180008bcd  call    cs:__imp_SetLastError
0x180008bd4  nop     dword ptr [rax+rax+00h]
0x180008bd9  mov     rcx, [rsi]; pti
0x180008bdc  test    rcx, rcx
0x180008bdf  jz      short loc_180008C0E
0x180008be1  mov     rax, 0FFFFFFFF4D2FA200h
0x180008beb  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180008bf0  mov     r9d, 124F8h; msWindowLength
0x180008bf6  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180008bfb  xor     r8d, r8d; msPeriod
0x180008bfe  call    cs:__imp_SetThreadpoolTimer
0x180008c05  nop     dword ptr [rax+rax+00h]
0x180008c0a  mov     byte ptr [rdi+41h], 1
0x180008c0e  mov     rcx, [rsp+38h+var_10]
0x180008c13  xor     rcx, rsp; StackCookie
0x180008c16  call    __security_check_cookie
0x180008c1b  mov     rbx, [rsp+38h+arg_8]
0x180008c20  mov     rsi, [rsp+38h+arg_10]
0x180008c25  add     rsp, 30h
0x180008c29  pop     rdi
0x180008c2a  retn
```
