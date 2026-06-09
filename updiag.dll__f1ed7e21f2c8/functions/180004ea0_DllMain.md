# DllMain

- ea: `0x180004ea0`
- end: `0x180004f06`
- name: `DllMain`
- size: `102`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800906ac`

## callees

- `0x180004d9c`
- `0x180004ea0`
- `0x18000897c`
- `0x1800961f0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180004eb0`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180004eb0`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  const struct wil::FailureInfo *v4; // rdx
  _BYTE v5[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      if ( wil::details::g_pfnTelemetryCallback
        && (char *)wil::details::g_pfnTelemetryCallback != (char *)Diagnostics::Telemetry4Diag::FallbackTelemetryCallback )
      {
        memset(v5, 0, 0x98u);
        wil::details::WilFailFast((wil::details *)v5, v4);
      }
      wil::details::g_pfnTelemetryCallback = (__int64 (__fastcall *)(_QWORD, _QWORD))Diagnostics::Telemetry4Diag::FallbackTelemetryCallback;
    }
  }
  else
  {
    CalliopeTipTests::DiagHealth::Cleanup((CalliopeTipTests::DiagHealth *)hinstDLL);
  }
  return 1;
}

```

## disassembly

```asm
0x180004ea0  sub     rsp, 0C8h
0x180004ea7  test    edx, edx
0x180004ea9  jz      short loc_180004ED7
0x180004eab  cmp     edx, 1
0x180004eae  jnz     short loc_180004EDC
0x180004eb0  call    cs:__imp_DisableThreadLibraryCalls
0x180004eb6  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180004ebd  lea     rcx, ?FallbackTelemetryCallback@Telemetry4Diag@Diagnostics@@SAX_NAEBUFailureInfo@wil@@@Z; this
0x180004ec4  test    rax, rax
0x180004ec7  jz      short loc_180004ECE
0x180004ec9  cmp     rax, rcx
0x180004ecc  jnz     short loc_180004EE9
0x180004ece  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rcx
0x180004ed5  jmp     short loc_180004EDC
0x180004ed7  call    ?Cleanup@DiagHealth@CalliopeTipTests@@YAXXZ; CalliopeTipTests::DiagHealth::Cleanup(void)
0x180004edc  mov     eax, 1
0x180004ee1  add     rsp, 0C8h
0x180004ee8  retn
0x180004ee9  xor     edx, edx; Val
0x180004eeb  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180004ef0  mov     r8d, 98h; Size
0x180004ef6  call    memset
0x180004efb  lea     rcx, [rsp+0C8h+var_A8]; this
0x180004f00  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
