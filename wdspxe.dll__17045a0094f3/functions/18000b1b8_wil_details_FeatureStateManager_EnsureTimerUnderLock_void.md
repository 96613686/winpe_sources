# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18000b1b8`
- end: `0x18000b260`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `168`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000d514`

## callees

- `0x18000b1b8`
- `0x180010c80`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000b20e`
- `KERNEL32!SetLastError` at `0x18000b20e`
- `KERNEL32!GetLastError` at `0x18000b1da`
- `KERNEL32!GetLastError` at `0x18000b1da`
- `KERNEL32!SetThreadpoolTimer` at `0x18000b23f`
- `KERNEL32!SetThreadpoolTimer` at `0x18000b23f`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000b1f5`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000b1f5`

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
0x18000b1b8  mov     [rsp+arg_8], rbx
0x18000b1bd  mov     [rsp+arg_10], rsi
0x18000b1c2  push    rdi
0x18000b1c3  sub     rsp, 20h
0x18000b1c7  cmp     byte ptr [rcx+41h], 0
0x18000b1cb  lea     rsi, [rcx+30h]
0x18000b1cf  mov     rdi, rcx
0x18000b1d2  jnz     short loc_18000B24F
0x18000b1d4  cmp     qword ptr [rsi], 0
0x18000b1d8  jnz     short loc_18000B21A
0x18000b1da  call    cs:__imp_GetLastError
0x18000b1e1  nop     dword ptr [rax+rax+00h]
0x18000b1e6  xor     r8d, r8d; pcbe
0x18000b1e9  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000b1f0  mov     rdx, rdi; pv
0x18000b1f3  mov     ebx, eax
0x18000b1f5  call    cs:__imp_CreateThreadpoolTimer
0x18000b1fc  nop     dword ptr [rax+rax+00h]
0x18000b201  mov     rdx, rax
0x18000b204  mov     rcx, rsi
0x18000b207  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000b20c  mov     ecx, ebx; dwErrCode
0x18000b20e  call    cs:__imp_SetLastError
0x18000b215  nop     dword ptr [rax+rax+00h]
0x18000b21a  mov     rcx, [rsi]; pti
0x18000b21d  test    rcx, rcx
0x18000b220  jz      short loc_18000B24F
0x18000b222  mov     rax, 0FFFFFFFF4D2FA200h
0x18000b22c  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18000b231  mov     r9d, 124F8h; msWindowLength
0x18000b237  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x18000b23c  xor     r8d, r8d; msPeriod
0x18000b23f  call    cs:__imp_SetThreadpoolTimer
0x18000b246  nop     dword ptr [rax+rax+00h]
0x18000b24b  mov     byte ptr [rdi+41h], 1
0x18000b24f  mov     rbx, [rsp+28h+arg_8]
0x18000b254  mov     rsi, [rsp+28h+arg_10]
0x18000b259  add     rsp, 20h
0x18000b25d  pop     rdi
0x18000b25e  retn
```
