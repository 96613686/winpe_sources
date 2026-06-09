# ThumbnailTelemetryAggregator::Init(void)

- ea: `0x18001f138`
- end: `0x18001f1b8`
- name: `?Init@ThumbnailTelemetryAggregator@@QEAAXXZ`
- size: `128`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001eee0`

## callees

- `0x18001f138`
- `0x18001f670`
- `0x180035830`
- `0x18004411c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001f15d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001f15d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001f19c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001f19c`

## pseudocode

```c
void __fastcall ThumbnailTelemetryAggregator::Init(PTP_TIMER *pv)
{
  PTP_TIMER ThreadpoolTimer; // rax
  void *v3; // rdx
  unsigned int v4; // r8d
  const char *v5; // r9
  const char *v6; // r9
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  ThreadpoolTimer = CreateThreadpoolTimer(OuterTimerCallback, pv, 0);
  try
  {
    if ( !ThreadpoolTimer )
      wil::details::in1diag3::Throw_GetLastError(retaddr, v3, v4, v5);
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      pv + 11,
      ThreadpoolTimer);
    pftDueTime = (struct _FILETIME)-6000000000LL;
    SetThreadpoolTimer(pv[11], &pftDueTime, 0, 0);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbnailcachetelemetry.cpp",
      v6);
  }
}

```

## disassembly

```asm
0x18001f138  push    rbx
0x18001f13a  sub     rsp, 30h
0x18001f13e  mov     rax, cs:__security_cookie
0x18001f145  xor     rax, rsp
0x18001f148  mov     [rsp+38h+var_10], rax
0x18001f14d  mov     rbx, rcx
0x18001f150  xor     r8d, r8d; pcbe
0x18001f153  mov     rdx, rcx; pv
0x18001f156  lea     rcx, ?OuterTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001f15d  call    cs:__imp_CreateThreadpoolTimer
0x18001f163  test    rax, rax
0x18001f166  jnz     short loc_18001F172
0x18001f168  mov     rcx, [rsp+38h]; this
0x18001f16d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18001f172  mov     rdx, rax
0x18001f175  lea     rcx, [rbx+58h]
0x18001f179  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001f17e  mov     rax, 0FFFFFFFE9A5F4400h
0x18001f188  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18001f18d  xor     r9d, r9d; msWindowLength
0x18001f190  xor     r8d, r8d; msPeriod
0x18001f193  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x18001f198  mov     rcx, [rbx+58h]; pti
0x18001f19c  call    cs:__imp_SetThreadpoolTimer
0x18001f1a2  nop
0x18001f1a3  jmp     short $+2
0x18001f1a5  mov     rcx, [rsp+38h+var_10]
0x18001f1aa  xor     rcx, rsp; StackCookie
0x18001f1ad  call    __security_check_cookie
0x18001f1b2  add     rsp, 30h
0x18001f1b6  pop     rbx
0x18001f1b7  retn
```
