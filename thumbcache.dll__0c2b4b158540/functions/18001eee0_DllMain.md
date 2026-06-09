# DllMain

- ea: `0x18001eee0`
- end: `0x18001efe0`
- name: `DllMain`
- size: `256`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callers

- `0x1800356a4`

## callees

- `0x18001eee0`
- `0x18001efe8`
- `0x18001f090`
- `0x18001f100`
- `0x18001f138`
- `0x18001f1c0`
- `0x18001f59c`
- `0x18001f670`
- `0x18001f760`
- `0x18002ec08`
- `0x1800364ac`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001ef0b`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001ef0b`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int i; // ebx
  __int64 v5; // rcx
  PTP_TIMER *GlobalTelemetryAggregator; // rax
  struct ThumbnailTelemetryAggregator *v7; // rax
  unsigned int v8; // edx
  const struct wil::FailureInfo *v9; // rdx
  _BYTE v10[168]; // [rsp+20h] [rbp-A8h] BYREF
  __int64 v11; // [rsp+E8h] [rbp+20h] BYREF

  if ( fdwReason == 1 )
  {
    g_hmodThisDll = hinstDLL;
    DisableThreadLibraryCalls(hinstDLL);
    for ( i = 0; i < 5; ++i )
    {
      v11 = 0;
      GetIconSize(i, &v11);
      v5 = (int)i;
      *((_DWORD *)&g_IconSize + v5) = v11;
    }
    if ( wil::details::g_pfnTelemetryCallback
      && (void (*)(bool, const struct wil::FailureInfo *))wil::details::g_pfnTelemetryCallback != ThumbnailCacheTelemetry::FallbackTelemetryCallback )
    {
      memset_0(v10, 0, 0x98u);
      wil::details::WilFailFast((wil::details *)v10, v9);
    }
    wil::details::g_pfnTelemetryCallback = (__int64)ThumbnailCacheTelemetry::FallbackTelemetryCallback;
    GlobalTelemetryAggregator = (PTP_TIMER *)ThumbnailTelemetryAggregator::GetGlobalTelemetryAggregator();
    ThumbnailTelemetryAggregator::Init(GlobalTelemetryAggregator);
    McGenEventRegister_EventRegister();
    *((_DWORD *)ThumbnailCacheLogging::Instance() + 5) = 2;
  }
  else if ( !fdwReason )
  {
    v7 = ThumbnailTelemetryAggregator::GetGlobalTelemetryAggregator();
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      (char *)v7 + 88,
      0);
    if ( g_pThumbsDBStore )
    {
      CGlobalThumbsDBStore::`scalar deleting destructor'(g_pThumbsDBStore, v8);
      g_pThumbsDBStore = 0;
    }
    McGenEventUnregister_EventUnregister();
  }
  return 1;
}

```

## disassembly

```asm
0x18001eee0  push    rbx
0x18001eee2  sub     rsp, 0C0h
0x18001eee9  cmp     edx, 1
0x18001eeec  jz      short loc_18001EF04
0x18001eeee  test    edx, edx
0x18001eef0  jz      loc_18001EF86
0x18001eef6  mov     eax, 1
0x18001eefb  add     rsp, 0C0h
0x18001ef02  pop     rbx
0x18001ef03  retn
0x18001ef04  mov     cs:?g_hmodThisDll@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_hmodThisDll
0x18001ef0b  call    cs:__imp_DisableThreadLibraryCalls
0x18001ef11  xor     ebx, ebx
0x18001ef13  lea     rdx, [rsp+0C8h+arg_18]
0x18001ef1b  mov     [rsp+0C8h+arg_18], 0
0x18001ef27  mov     ecx, ebx
0x18001ef29  call    ?GetIconSize@@YAXW4ICONSIZE@@PEAUtagSIZE@@@Z; GetIconSize(ICONSIZE,tagSIZE *)
0x18001ef2e  mov     eax, dword ptr [rsp+0C8h+arg_18]
0x18001ef35  lea     rdx, ?g_IconSize@@3PAIA; uint near * g_IconSize
0x18001ef3c  movsxd  rcx, ebx
0x18001ef3f  inc     ebx
0x18001ef41  mov     [rdx+rcx*4], eax
0x18001ef44  cmp     ebx, 5
0x18001ef47  jb      short loc_18001EF13
0x18001ef49  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18001ef50  lea     rcx, ?FallbackTelemetryCallback@ThumbnailCacheTelemetry@@SAX_NAEBUFailureInfo@wil@@@Z; ThumbnailCacheTelemetry::FallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x18001ef57  test    rax, rax
0x18001ef5a  jnz     short loc_18001EFBE
0x18001ef5c  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rcx
0x18001ef63  call    ?GetGlobalTelemetryAggregator@ThumbnailTelemetryAggregator@@SAAEAV1@XZ; ThumbnailTelemetryAggregator::GetGlobalTelemetryAggregator(void)
0x18001ef68  mov     rcx, rax; pv
0x18001ef6b  call    ?Init@ThumbnailTelemetryAggregator@@QEAAXXZ; ThumbnailTelemetryAggregator::Init(void)
0x18001ef70  call    McGenEventRegister_EventRegister
0x18001ef75  call    ?Instance@ThumbnailCacheLogging@@KAPEAV1@XZ; ThumbnailCacheLogging::Instance(void)
0x18001ef7a  mov     dword ptr [rax+14h], 2
0x18001ef81  jmp     loc_18001EEF6
0x18001ef86  call    ?GetGlobalTelemetryAggregator@ThumbnailTelemetryAggregator@@SAAEAV1@XZ; ThumbnailTelemetryAggregator::GetGlobalTelemetryAggregator(void)
0x18001ef8b  xor     edx, edx
0x18001ef8d  lea     rcx, [rax+58h]
0x18001ef91  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001ef96  mov     rcx, cs:?g_pThumbsDBStore@@3PEAVCGlobalThumbsDBStore@@EA; this
0x18001ef9d  test    rcx, rcx
0x18001efa0  jnz     short loc_18001EFAC
0x18001efa2  call    McGenEventUnregister_EventUnregister
0x18001efa7  jmp     loc_18001EEF6
0x18001efac  call    ??_GCGlobalThumbsDBStore@@QEAAPEAXI@Z; CGlobalThumbsDBStore::`scalar deleting destructor'(uint)
0x18001efb1  mov     cs:?g_pThumbsDBStore@@3PEAVCGlobalThumbsDBStore@@EA, 0; CGlobalThumbsDBStore * g_pThumbsDBStore
0x18001efbc  jmp     short loc_18001EFA2
0x18001efbe  cmp     rax, rcx
0x18001efc1  jz      short loc_18001EF5C
0x18001efc3  xor     edx, edx; Val
0x18001efc5  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18001efca  mov     r8d, 98h; Size
0x18001efd0  call    memset_0
0x18001efd5  lea     rcx, [rsp+0C8h+var_A8]; this
0x18001efda  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
