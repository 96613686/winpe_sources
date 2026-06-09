# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x1800054a8`
- end: `0x180005550`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `168`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180008a34`

## callees

- `0x1800054a8`
- `0x18000ba50`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800054fe`
- `KERNEL32!SetLastError` at `0x1800054fe`
- `KERNEL32!GetLastError` at `0x1800054ca`
- `KERNEL32!GetLastError` at `0x1800054ca`
- `KERNEL32!SetThreadpoolTimer` at `0x18000552f`
- `KERNEL32!SetThreadpoolTimer` at `0x18000552f`
- `KERNEL32!CreateThreadpoolTimer` at `0x1800054e5`
- `KERNEL32!CreateThreadpoolTimer` at `0x1800054e5`

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
0x1800054a8  mov     [rsp+arg_8], rbx
0x1800054ad  mov     [rsp+arg_10], rsi
0x1800054b2  push    rdi
0x1800054b3  sub     rsp, 20h
0x1800054b7  cmp     byte ptr [rcx+41h], 0
0x1800054bb  lea     rsi, [rcx+30h]
0x1800054bf  mov     rdi, rcx
0x1800054c2  jnz     short loc_18000553F
0x1800054c4  cmp     qword ptr [rsi], 0
0x1800054c8  jnz     short loc_18000550A
0x1800054ca  call    cs:__imp_GetLastError
0x1800054d1  nop     dword ptr [rax+rax+00h]
0x1800054d6  xor     r8d, r8d; pcbe
0x1800054d9  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800054e0  mov     rdx, rdi; pv
0x1800054e3  mov     ebx, eax
0x1800054e5  call    cs:__imp_CreateThreadpoolTimer
0x1800054ec  nop     dword ptr [rax+rax+00h]
0x1800054f1  mov     rdx, rax
0x1800054f4  mov     rcx, rsi
0x1800054f7  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800054fc  mov     ecx, ebx; dwErrCode
0x1800054fe  call    cs:__imp_SetLastError
0x180005505  nop     dword ptr [rax+rax+00h]
0x18000550a  mov     rcx, [rsi]; pti
0x18000550d  test    rcx, rcx
0x180005510  jz      short loc_18000553F
0x180005512  mov     rax, 0FFFFFFFF4D2FA200h
0x18000551c  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180005521  mov     r9d, 124F8h; msWindowLength
0x180005527  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x18000552c  xor     r8d, r8d; msPeriod
0x18000552f  call    cs:__imp_SetThreadpoolTimer
0x180005536  nop     dword ptr [rax+rax+00h]
0x18000553b  mov     byte ptr [rdi+41h], 1
0x18000553f  mov     rbx, [rsp+28h+arg_8]
0x180005544  mov     rsi, [rsp+28h+arg_10]
0x180005549  add     rsp, 20h
0x18000554d  pop     rdi
0x18000554e  retn
```
