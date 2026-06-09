# COplockProvider::StartCreateFileCallbackTimer(void)

- ea: `0x18002440c`
- end: `0x1800244ad`
- name: `?StartCreateFileCallbackTimer@COplockProvider@@AEAAXXZ`
- size: `161`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180023d40`

## callees

- `0x18000ca10`
- `0x18002440c`
- `0x1800259a4`
- `0x180083090`
- `0x180083154`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180024437`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180024437`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180024460`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180024460`

## pseudocode

```c
void __fastcall COplockProvider::StartCreateFileCallbackTimer(struct _TP_CALLBACK_ENVIRON_V3 *pv)
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
    pftDueTime.dwLowDateTime = 1;
    v5 = pv;
    ((void (__fastcall *)(struct _TP_CALLBACK_ENVIRON_V3 **, int *, TP_VERSION *, struct _FILETIME *))SHCoreOplockTelemetry::SkipTimerDuringProcessShutdown<COplockProvider *,int,int,int>)(
      &v5,
      &RaceDll,
      &Version,
      &pftDueTime);
  }
  else
  {
    ThreadpoolTimer = CreateThreadpoolTimer(COplockProvider::createFileNotFinishedInTime, pv, pv + 1);
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      &pv[3].Size,
      ThreadpoolTimer);
    v3 = (struct _FILETIME)wil::filetime::from_int64<unsigned __int64,0>();
    v4 = *(struct _TP_TIMER **)&pv[3].Size;
    pftDueTime = v3;
    SetThreadpoolTimer(v4, &pftDueTime, 0, 0);
  }
}

```

## disassembly

```asm
0x18002440c  mov     [rsp+arg_0], rbx
0x180024411  push    rdi
0x180024412  sub     rsp, 30h
0x180024416  mov     rdi, rcx
0x180024419  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18002441e  test    al, al
0x180024420  jnz     short loc_180024471
0x180024422  lea     r8, [rdi+48h]; pcbe
0x180024426  mov     rdx, rdi; pv
0x180024429  lea     rcx, ?createFileNotFinishedInTime@COplockProvider@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180024430  lea     rbx, [rdi+118h]
0x180024437  call    cs:__imp_CreateThreadpoolTimer
0x18002443d  mov     rdx, rax
0x180024440  mov     rcx, rbx
0x180024443  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180024448  call    ??$from_int64@_K$0A@@filetime@wil@@YA?AU_FILETIME@@_K@Z; wil::filetime::from_int64<unsigned __int64,0>(unsigned __int64)
0x18002444d  mov     rcx, [rbx]; pti
0x180024450  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180024455  xor     r9d, r9d; msWindowLength
0x180024458  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18002445d  xor     r8d, r8d; msPeriod
0x180024460  call    cs:__imp_SetThreadpoolTimer
0x180024466  mov     rbx, [rsp+38h+arg_0]
0x18002446b  add     rsp, 30h
0x18002446f  pop     rdi
0x180024470  retn
0x180024471  mov     eax, [rdi+120h]
0x180024477  lea     r9, [rsp+38h+pftDueTime]
0x18002447c  mov     [rsp+38h+arg_10], eax
0x180024480  lea     r8, [rsp+38h+arg_10]
0x180024485  mov     eax, [rdi+0F8h]
0x18002448b  lea     rdx, [rsp+38h+arg_18]
0x180024490  lea     rcx, [rsp+38h+var_18]
0x180024495  mov     [rsp+38h+arg_18], eax
0x180024499  mov     [rsp+38h+pftDueTime.dwLowDateTime], 1
0x1800244a1  mov     [rsp+38h+var_18], rdi
0x1800244a6  call    ??$SkipTimerDuringProcessShutdown@PEAVCOplockProvider@@HHH@SHCoreOplockTelemetry@@SAX$$QEAPEAVCOplockProvider@@$$QEAH11@Z; SHCoreOplockTelemetry::SkipTimerDuringProcessShutdown<COplockProvider *,int,int,int>(COplockProvider * &&,int &&,int &&,int &&)
0x1800244ab  jmp     short loc_180024466
```
