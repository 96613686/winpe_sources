# DllMain

- ea: `0x18000c8c0`
- end: `0x18000c975`
- name: `DllMain`
- size: `181`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000d824`

## callees

- `0x180007860`
- `0x180007a4c`
- `0x18000c8c0`
- `0x18000e330`
- `0x180011750`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000c8e1`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000c8e1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c944`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c944`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c951`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c951`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  const struct wil::FailureInfo *v4; // rdx
  LPCRITICAL_SECTION v5; // rcx
  _BYTE v7[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      g_hDllInstance = hinstDLL;
      McGenEventRegister_EtwEventRegister();
      if ( wil::details::g_pfnTelemetryCallback
        && (char *)wil::details::g_pfnTelemetryCallback != (char *)UserenvTelemetry::FallbackTelemetryCallback )
      {
        memset_0(v7, 0, 0x98u);
        wil::details::WilFailFast((wil::details *)v7, v4);
      }
      wil::details::g_pfnTelemetryCallback = (__int64 (__fastcall *)(_QWORD, _QWORD))UserenvTelemetry::FallbackTelemetryCallback;
      hProxyDll = (__int64)hinstDLL;
    }
  }
  else
  {
    v5 = g_PingCritSec;
    if ( g_PingCritSec )
    {
      DeleteCriticalSection(g_PingCritSec);
      LocalFree(g_PingCritSec);
      g_PingCritSec = 0;
    }
    McGenEventUnregister_EtwEventUnregister(v5, *(_QWORD *)&fdwReason, lpvReserved);
  }
  return 1;
}

```

## disassembly

```asm
0x18000c8c0  push    rbx
0x18000c8c2  sub     rsp, 0C0h
0x18000c8c9  mov     rbx, rcx
0x18000c8cc  mov     eax, edx
0x18000c8ce  test    edx, edx
0x18000c8d0  jz      short loc_18000C938
0x18000c8d2  cmp     eax, 1
0x18000c8d5  jz      short loc_18000C8E1
0x18000c8d7  cmp     edx, 1
0x18000c8da  jz      short loc_18000C92F
0x18000c8dc  jmp     loc_18000C967
0x18000c8e1  call    cs:__imp_DisableThreadLibraryCalls
0x18000c8e7  mov     cs:g_hDllInstance, rbx
0x18000c8ee  call    McGenEventRegister_EtwEventRegister
0x18000c8f3  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000c8fa  lea     rcx, ?FallbackTelemetryCallback@UserenvTelemetry@@SAX_NAEBUFailureInfo@wil@@@Z; UserenvTelemetry::FallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x18000c901  test    rax, rax
0x18000c904  jz      short loc_18000C928
0x18000c906  cmp     rax, rcx
0x18000c909  jz      short loc_18000C928
0x18000c90b  xor     edx, edx; Val
0x18000c90d  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000c912  mov     r8d, 98h; Size
0x18000c918  call    memset_0
0x18000c91d  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000c922  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000c928  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rcx
0x18000c92f  mov     cs:hProxyDll, rbx
0x18000c936  jmp     short loc_18000C967
0x18000c938  mov     rcx, cs:?g_PingCritSec@@3PEAU_RTL_CRITICAL_SECTION@@EA; lpCriticalSection
0x18000c93f  test    rcx, rcx
0x18000c942  jz      short loc_18000C962
0x18000c944  call    cs:__imp_DeleteCriticalSection
0x18000c94a  mov     rcx, cs:?g_PingCritSec@@3PEAU_RTL_CRITICAL_SECTION@@EA; hMem
0x18000c951  call    cs:__imp_LocalFree
0x18000c957  mov     cs:?g_PingCritSec@@3PEAU_RTL_CRITICAL_SECTION@@EA, 0; _RTL_CRITICAL_SECTION * g_PingCritSec
0x18000c962  call    McGenEventUnregister_EtwEventUnregister
0x18000c967  mov     eax, 1
0x18000c96c  add     rsp, 0C0h
0x18000c973  pop     rbx
0x18000c974  retn
```
