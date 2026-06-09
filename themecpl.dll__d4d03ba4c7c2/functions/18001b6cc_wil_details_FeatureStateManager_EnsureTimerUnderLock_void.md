# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18001b6cc`
- end: `0x18001b774`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `168`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001cd0c`

## callees

- `0x18001b6cc`
- `0x18001f0ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b722`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b722`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b6ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b6ee`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001b709`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001b709`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001b753`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001b753`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::EnsureTimerUnderLock(struct _TP_TIMER **pv)
{
  struct _TP_TIMER **v2; // rsi
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v5; // rcx
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

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
0x18001b6cc  mov     [rsp+arg_8], rbx
0x18001b6d1  mov     [rsp+arg_10], rsi
0x18001b6d6  push    rdi
0x18001b6d7  sub     rsp, 20h
0x18001b6db  cmp     byte ptr [rcx+41h], 0
0x18001b6df  mov     rdi, rcx
0x18001b6e2  jnz     short loc_18001B763
0x18001b6e4  lea     rsi, [rcx+30h]
0x18001b6e8  cmp     qword ptr [rsi], 0
0x18001b6ec  jnz     short loc_18001B72E
0x18001b6ee  call    cs:__imp_GetLastError
0x18001b6f5  nop     dword ptr [rax+rax+00h]
0x18001b6fa  xor     r8d, r8d; pcbe
0x18001b6fd  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001b704  mov     rdx, rdi; pv
0x18001b707  mov     ebx, eax
0x18001b709  call    cs:__imp_CreateThreadpoolTimer
0x18001b710  nop     dword ptr [rax+rax+00h]
0x18001b715  mov     rdx, rax
0x18001b718  mov     rcx, rsi
0x18001b71b  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001b720  mov     ecx, ebx; dwErrCode
0x18001b722  call    cs:__imp_SetLastError
0x18001b729  nop     dword ptr [rax+rax+00h]
0x18001b72e  mov     rcx, [rsi]; pti
0x18001b731  test    rcx, rcx
0x18001b734  jz      short loc_18001B763
0x18001b736  mov     rax, 0FFFFFFFF4D2FA200h
0x18001b740  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18001b745  mov     r9d, 124F8h; msWindowLength
0x18001b74b  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x18001b750  xor     r8d, r8d; msPeriod
0x18001b753  call    cs:__imp_SetThreadpoolTimer
0x18001b75a  nop     dword ptr [rax+rax+00h]
0x18001b75f  mov     byte ptr [rdi+41h], 1
0x18001b763  mov     rbx, [rsp+28h+arg_8]
0x18001b768  mov     rsi, [rsp+28h+arg_10]
0x18001b76d  add     rsp, 20h
0x18001b771  pop     rdi
0x18001b772  retn
```
