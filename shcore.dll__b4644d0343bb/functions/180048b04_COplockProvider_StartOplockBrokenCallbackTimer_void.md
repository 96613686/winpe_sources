# COplockProvider::StartOplockBrokenCallbackTimer(void)

- ea: `0x180048b04`
- end: `0x180048ba5`
- name: `?StartOplockBrokenCallbackTimer@COplockProvider@@AEAAXXZ`
- size: `161`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800482b0`

## callees

- `0x18000ca10`
- `0x1800259a4`
- `0x180048b04`
- `0x180083090`
- `0x180083154`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180048b2f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180048b2f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180048b58`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180048b58`

## pseudocode

```c
void __fastcall COplockProvider::StartOplockBrokenCallbackTimer(struct _TP_CALLBACK_ENVIRON_V3 *pv)
{
  PTP_TIMER ThreadpoolTimer; // rax
  struct _FILETIME v3; // rax
  struct _TP_TIMER *v4; // rcx
  struct _TP_CALLBACK_ENVIRON_V3 *v5; // [rsp+20h] [rbp-18h] BYREF
  struct _FILETIME pftDueTime; // [rsp+48h] [rbp+10h] BYREF
  TP_VERSION Version; // [rsp+50h] [rbp+18h] BYREF
  int RaceDll; // [rsp+58h] [rbp+20h] BYREF

  if ( wil::ProcessShutdownInProgress((wil *)pv) )
  {
    Version = pv[4].Version;
    RaceDll = (int)pv[3].RaceDll;
    pftDueTime.dwLowDateTime = 0;
    v5 = pv;
    ((void (__fastcall *)(struct _TP_CALLBACK_ENVIRON_V3 **, int *, TP_VERSION *, struct _FILETIME *))SHCoreOplockTelemetry::SkipTimerDuringProcessShutdown<COplockProvider *,int,int,int>)(
      &v5,
      &RaceDll,
      &Version,
      &pftDueTime);
  }
  else
  {
    ThreadpoolTimer = CreateThreadpoolTimer(COplockProvider::oplockNotRelinquishedInTime, pv, pv + 1);
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      &pv[3].u,
      ThreadpoolTimer);
    v3 = (struct _FILETIME)wil::filetime::from_int64<unsigned __int64,0>();
    v4 = *(struct _TP_TIMER **)&pv[3].u.Flags;
    pftDueTime = v3;
    SetThreadpoolTimer(v4, &pftDueTime, 0, 0);
  }
}

```

## disassembly

```asm
0x180048b04  mov     [rsp+arg_0], rbx
0x180048b09  push    rdi
0x180048b0a  sub     rsp, 30h
0x180048b0e  mov     rdi, rcx
0x180048b11  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180048b16  test    al, al
0x180048b18  jnz     short loc_180048B60
0x180048b1a  lea     r8, [rdi+48h]; pcbe
0x180048b1e  mov     rdx, rdi; pv
0x180048b21  lea     rcx, ?oplockNotRelinquishedInTime@COplockProvider@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180048b28  lea     rbx, [rdi+110h]
0x180048b2f  call    cs:__imp_CreateThreadpoolTimer
0x180048b35  mov     rdx, rax
0x180048b38  mov     rcx, rbx
0x180048b3b  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180048b40  call    ??$from_int64@_K$0A@@filetime@wil@@YA?AU_FILETIME@@_K@Z; wil::filetime::from_int64<unsigned __int64,0>(unsigned __int64)
0x180048b45  mov     rcx, [rbx]; pti
0x180048b48  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180048b4d  xor     r9d, r9d; msWindowLength
0x180048b50  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180048b55  xor     r8d, r8d; msPeriod
0x180048b58  call    cs:__imp_SetThreadpoolTimer
0x180048b5e  jmp     short loc_180048B9A
0x180048b60  mov     eax, [rdi+120h]
0x180048b66  lea     r9, [rsp+38h+pftDueTime]
0x180048b6b  mov     [rsp+38h+arg_10], eax
0x180048b6f  lea     r8, [rsp+38h+arg_10]
0x180048b74  mov     eax, [rdi+0F8h]
0x180048b7a  lea     rdx, [rsp+38h+arg_18]
0x180048b7f  lea     rcx, [rsp+38h+var_18]
0x180048b84  mov     [rsp+38h+arg_18], eax
0x180048b88  mov     [rsp+38h+pftDueTime.dwLowDateTime], 0
0x180048b90  mov     [rsp+38h+var_18], rdi
0x180048b95  call    ??$SkipTimerDuringProcessShutdown@PEAVCOplockProvider@@HHH@SHCoreOplockTelemetry@@SAX$$QEAPEAVCOplockProvider@@$$QEAH11@Z; SHCoreOplockTelemetry::SkipTimerDuringProcessShutdown<COplockProvider *,int,int,int>(COplockProvider * &&,int &&,int &&,int &&)
0x180048b9a  mov     rbx, [rsp+38h+arg_0]
0x180048b9f  add     rsp, 30h
0x180048ba3  pop     rdi
0x180048ba4  retn
```
