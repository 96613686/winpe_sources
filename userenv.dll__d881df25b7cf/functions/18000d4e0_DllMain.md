# DllMain

- ea: `0x18000d4e0`
- end: `0x18000d574`
- name: `DllMain`
- size: `148`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18000e4b4`

## callees

- `0x180008890`
- `0x180008af4`
- `0x180008b78`
- `0x18000d4e0`
- `0x18000efe0`
- `0x1800126a4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000d4fe`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000d4fe`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  const struct wil::FailureInfo *v4; // rdx
  _BYTE v6[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      g_hDllInstance = hinstDLL;
      McGenEventRegister_EtwEventRegister();
      if ( wil::details::g_pfnTelemetryCallback
        && (void (__fastcall *)(bool, const struct wil::FailureInfo *))wil::details::g_pfnTelemetryCallback != UserenvTelemetry::FallbackTelemetryCallback )
      {
        memset_0(v6, 0, 0x98u);
        wil::details::WilFailFast((wil::details *)v6, v4);
      }
      wil::details::g_pfnTelemetryCallback = (__int64)UserenvTelemetry::FallbackTelemetryCallback;
      hProxyDll = (__int64)hinstDLL;
    }
  }
  else
  {
    ClosePingCritSec();
    McGenEventUnregister_EtwEventUnregister();
  }
  return 1;
}

```

## disassembly

```asm
0x18000d4e0  push    rbx
0x18000d4e2  sub     rsp, 0C0h
0x18000d4e9  mov     rbx, rcx
0x18000d4ec  mov     eax, edx
0x18000d4ee  test    edx, edx
0x18000d4f0  jz      short loc_18000D55B
0x18000d4f2  cmp     eax, 1
0x18000d4f5  jz      short loc_18000D4FE
0x18000d4f7  cmp     edx, 1
0x18000d4fa  jz      short loc_18000D552
0x18000d4fc  jmp     short loc_18000D565
0x18000d4fe  call    cs:__imp_DisableThreadLibraryCalls
0x18000d505  nop     dword ptr [rax+rax+00h]
0x18000d50a  mov     cs:g_hDllInstance, rbx
0x18000d511  call    McGenEventRegister_EtwEventRegister
0x18000d516  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000d51d  lea     rcx, ?FallbackTelemetryCallback@UserenvTelemetry@@SAX_NAEBUFailureInfo@wil@@@Z; UserenvTelemetry::FallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x18000d524  test    rax, rax
0x18000d527  jz      short loc_18000D54B
0x18000d529  cmp     rax, rcx
0x18000d52c  jz      short loc_18000D54B
0x18000d52e  xor     edx, edx; Val
0x18000d530  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000d535  mov     r8d, 98h; Size
0x18000d53b  call    memset_0
0x18000d540  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000d545  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000d54b  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rcx
0x18000d552  mov     cs:hProxyDll, rbx
0x18000d559  jmp     short loc_18000D565
0x18000d55b  call    ?ClosePingCritSec@@YAXXZ; ClosePingCritSec(void)
0x18000d560  call    McGenEventUnregister_EtwEventUnregister
0x18000d565  mov     eax, 1
0x18000d56a  add     rsp, 0C0h
0x18000d571  pop     rbx
0x18000d572  retn
```
