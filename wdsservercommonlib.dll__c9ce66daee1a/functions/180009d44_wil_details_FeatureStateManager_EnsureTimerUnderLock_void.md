# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180009d44`
- end: `0x180009dec`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `168`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000b844`

## callees

- `0x180009d44`
- `0x18000dc88`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180009d9a`
- `KERNEL32!SetLastError` at `0x180009d9a`
- `KERNEL32!GetLastError` at `0x180009d66`
- `KERNEL32!GetLastError` at `0x180009d66`
- `KERNEL32!SetThreadpoolTimer` at `0x180009dcb`
- `KERNEL32!SetThreadpoolTimer` at `0x180009dcb`
- `KERNEL32!CreateThreadpoolTimer` at `0x180009d81`
- `KERNEL32!CreateThreadpoolTimer` at `0x180009d81`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::EnsureTimerUnderLock(struct _TP_TIMER **pv)
{
  struct _TP_TIMER **v1; // rsi
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v5; // rcx
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  v1 = pv + 6;
  if ( !*((_BYTE *)pv + 65) )
  {
    if ( !*v1 )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_, pv, 0);
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        v1,
        ThreadpoolTimer);
      SetLastError(LastError);
    }
    v5 = *v1;
    if ( *v1 )
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
0x180009d44  mov     [rsp+arg_8], rbx
0x180009d49  mov     [rsp+arg_10], rsi
0x180009d4e  push    rdi
0x180009d4f  sub     rsp, 20h
0x180009d53  cmp     byte ptr [rcx+41h], 0
0x180009d57  lea     rsi, [rcx+30h]
0x180009d5b  mov     rdi, rcx
0x180009d5e  jnz     short loc_180009DDB
0x180009d60  cmp     qword ptr [rsi], 0
0x180009d64  jnz     short loc_180009DA6
0x180009d66  call    cs:__imp_GetLastError
0x180009d6d  nop     dword ptr [rax+rax+00h]
0x180009d72  xor     r8d, r8d; pcbe
0x180009d75  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180009d7c  mov     rdx, rdi; pv
0x180009d7f  mov     ebx, eax
0x180009d81  call    cs:__imp_CreateThreadpoolTimer
0x180009d88  nop     dword ptr [rax+rax+00h]
0x180009d8d  mov     rdx, rax
0x180009d90  mov     rcx, rsi
0x180009d93  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180009d98  mov     ecx, ebx; dwErrCode
0x180009d9a  call    cs:__imp_SetLastError
0x180009da1  nop     dword ptr [rax+rax+00h]
0x180009da6  mov     rcx, [rsi]; pti
0x180009da9  test    rcx, rcx
0x180009dac  jz      short loc_180009DDB
0x180009dae  mov     rax, 0FFFFFFFF4D2FA200h
0x180009db8  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180009dbd  mov     r9d, 124F8h; msWindowLength
0x180009dc3  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x180009dc8  xor     r8d, r8d; msPeriod
0x180009dcb  call    cs:__imp_SetThreadpoolTimer
0x180009dd2  nop     dword ptr [rax+rax+00h]
0x180009dd7  mov     byte ptr [rdi+41h], 1
0x180009ddb  mov     rbx, [rsp+28h+arg_8]
0x180009de0  mov     rsi, [rsp+28h+arg_10]
0x180009de5  add     rsp, 20h
0x180009de9  pop     rdi
0x180009dea  retn
```
