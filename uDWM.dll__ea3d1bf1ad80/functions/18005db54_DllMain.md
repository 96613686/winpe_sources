# DllMain

- ea: `0x18005db54`
- end: `0x18005dc23`
- name: `DllMain`
- size: `207`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180096874`

## callees

- `0x180001b1c`
- `0x18005db54`
- `0x18005dca4`
- `0x18005dd5c`
- `0x180067514`
- `0x180095b4c`
- `0x1800bdd64`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18005db7c`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18005db7c`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  const struct wil::FailureInfo *v4; // rdx
  const struct wil::FailureInfo *v5; // rdx
  _BYTE v6[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      g_hInstance = hinstDLL;
      DisableThreadLibraryCalls(hinstDLL);
      if ( wil::details::g_pfnTelemetryCallback
        && (void (*)(bool, const struct wil::FailureInfo *))wil::details::g_pfnTelemetryCallback != WindowFrameLoggingTelemetry::FallbackTelemetryCallback )
      {
        memset_0(v6, 0, 0x98u);
        wil::details::WilFailFast((wil::details *)v6, v4);
      }
      wil::details::g_pfnTelemetryCallback = (__int64)WindowFrameLoggingTelemetry::FallbackTelemetryCallback;
      McGenEventRegister_EtwEventRegister();
      if ( wil::details::g_pfnLoggingCallback
        && (void (__fastcall *)(const struct wil::FailureInfo *))wil::details::g_pfnLoggingCallback != WilResultLoggingCallback_MaybeFailFast )
      {
        memset_0(v6, 0, 0x98u);
        wil::details::WilFailFast((wil::details *)v6, v5);
      }
      wil::details::g_pfnLoggingCallback = (__int64)WilResultLoggingCallback_MaybeFailFast;
      TraceLoggingRegisterEx_EtwEventRegister_EtwEventSetInformation(&dword_1801150F8);
    }
  }
  else
  {
    TraceLoggingUnregister_EtwEventUnregister(&dword_1801150F8, fdwReason, lpvReserved);
    McGenEventUnregister_EtwEventUnregister();
  }
  return 1;
}

```

## disassembly

```asm
0x18005db54  sub     rsp, 0C8h
0x18005db5b  test    edx, edx
0x18005db5d  jz      loc_18005DC0D
0x18005db63  cmp     edx, 1
0x18005db66  jz      short loc_18005DB75
0x18005db68  mov     eax, 1
0x18005db6d  add     rsp, 0C8h
0x18005db74  retn
0x18005db75  mov     cs:?g_hInstance@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_hInstance
0x18005db7c  call    cs:__imp_DisableThreadLibraryCalls
0x18005db82  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18005db89  lea     rcx, ?FallbackTelemetryCallback@WindowFrameLoggingTelemetry@@SAX_NAEBUFailureInfo@wil@@@Z; WindowFrameLoggingTelemetry::FallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x18005db90  test    rax, rax
0x18005db93  jnz     short loc_18005DBC9
0x18005db95  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rcx
0x18005db9c  call    McGenEventRegister_EtwEventRegister
0x18005dba1  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18005dba8  lea     rcx, ?WilResultLoggingCallback_MaybeFailFast@@YAXAEBUFailureInfo@wil@@@Z; WilResultLoggingCallback_MaybeFailFast(wil::FailureInfo const &)
0x18005dbaf  test    rax, rax
0x18005dbb2  jnz     short loc_18005DBEB
0x18005dbb4  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, rcx
0x18005dbbb  lea     rcx, dword_1801150F8
0x18005dbc2  call    TraceLoggingRegisterEx_EtwEventRegister_EtwEventSetInformation
0x18005dbc7  jmp     short loc_18005DB68
0x18005dbc9  cmp     rax, rcx
0x18005dbcc  jz      short loc_18005DB95
0x18005dbce  xor     edx, edx; Val
0x18005dbd0  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18005dbd5  mov     r8d, 98h; Size
0x18005dbdb  call    memset_0
0x18005dbe0  lea     rcx, [rsp+0C8h+var_A8]; this
0x18005dbe5  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18005dbeb  cmp     rax, rcx
0x18005dbee  jz      short loc_18005DBB4
0x18005dbf0  xor     edx, edx; Val
0x18005dbf2  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18005dbf7  mov     r8d, 98h; Size
0x18005dbfd  call    memset_0
0x18005dc02  lea     rcx, [rsp+0C8h+var_A8]; this
0x18005dc07  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18005dc0d  lea     rcx, dword_1801150F8
0x18005dc14  call    TraceLoggingUnregister_EtwEventUnregister
0x18005dc19  call    McGenEventUnregister_EtwEventUnregister
0x18005dc1e  jmp     loc_18005DB68
```
