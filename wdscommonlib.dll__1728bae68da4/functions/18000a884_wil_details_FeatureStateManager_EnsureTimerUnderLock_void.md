# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18000a884`
- end: `0x18000a92c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `168`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000c384`

## callees

- `0x18000a884`
- `0x18000e7c8`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000a8da`
- `KERNEL32!SetLastError` at `0x18000a8da`
- `KERNEL32!GetLastError` at `0x18000a8a6`
- `KERNEL32!GetLastError` at `0x18000a8a6`
- `KERNEL32!SetThreadpoolTimer` at `0x18000a90b`
- `KERNEL32!SetThreadpoolTimer` at `0x18000a90b`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000a8c1`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000a8c1`

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
0x18000a884  mov     [rsp+arg_8], rbx
0x18000a889  mov     [rsp+arg_10], rsi
0x18000a88e  push    rdi
0x18000a88f  sub     rsp, 20h
0x18000a893  cmp     byte ptr [rcx+41h], 0
0x18000a897  lea     rsi, [rcx+30h]
0x18000a89b  mov     rdi, rcx
0x18000a89e  jnz     short loc_18000A91B
0x18000a8a0  cmp     qword ptr [rsi], 0
0x18000a8a4  jnz     short loc_18000A8E6
0x18000a8a6  call    cs:__imp_GetLastError
0x18000a8ad  nop     dword ptr [rax+rax+00h]
0x18000a8b2  xor     r8d, r8d; pcbe
0x18000a8b5  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000a8bc  mov     rdx, rdi; pv
0x18000a8bf  mov     ebx, eax
0x18000a8c1  call    cs:__imp_CreateThreadpoolTimer
0x18000a8c8  nop     dword ptr [rax+rax+00h]
0x18000a8cd  mov     rdx, rax
0x18000a8d0  mov     rcx, rsi
0x18000a8d3  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000a8d8  mov     ecx, ebx; dwErrCode
0x18000a8da  call    cs:__imp_SetLastError
0x18000a8e1  nop     dword ptr [rax+rax+00h]
0x18000a8e6  mov     rcx, [rsi]; pti
0x18000a8e9  test    rcx, rcx
0x18000a8ec  jz      short loc_18000A91B
0x18000a8ee  mov     rax, 0FFFFFFFF4D2FA200h
0x18000a8f8  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18000a8fd  mov     r9d, 124F8h; msWindowLength
0x18000a903  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x18000a908  xor     r8d, r8d; msPeriod
0x18000a90b  call    cs:__imp_SetThreadpoolTimer
0x18000a912  nop     dword ptr [rax+rax+00h]
0x18000a917  mov     byte ptr [rdi+41h], 1
0x18000a91b  mov     rbx, [rsp+28h+arg_8]
0x18000a920  mov     rsi, [rsp+28h+arg_10]
0x18000a925  add     rsp, 20h
0x18000a929  pop     rdi
0x18000a92a  retn
```
