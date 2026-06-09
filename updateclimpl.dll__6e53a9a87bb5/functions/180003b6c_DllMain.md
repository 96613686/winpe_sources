# DllMain

- ea: `0x180003b6c`
- end: `0x180003bc7`
- name: `DllMain`
- size: `91`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18001093c`

## callees

- `0x180003b6c`
- `0x180004298`
- `0x180014960`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180003b78`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180003b78`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  const struct wil::FailureInfo *v4; // rdx
  _BYTE v5[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( fdwReason == 1 )
  {
    DisableThreadLibraryCalls(hinstDLL);
    if ( wil::details::g_pfnTelemetryCallback
      && (char *)wil::details::g_pfnTelemetryCallback != (char *)Telemetry4UpdateCli::FallbackTelemetryCallback )
    {
      memset(v5, 0, 0x98u);
      wil::details::WilFailFast((wil::details *)v5, v4);
    }
    wil::details::g_pfnTelemetryCallback = (__int64 (__fastcall *)(_QWORD, _QWORD))Telemetry4UpdateCli::FallbackTelemetryCallback;
  }
  return 1;
}

```

## disassembly

```asm
0x180003b6c  sub     rsp, 0C8h
0x180003b73  cmp     edx, 1
0x180003b76  jnz     short loc_180003B9D
0x180003b78  call    cs:__imp_DisableThreadLibraryCalls
0x180003b7e  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180003b85  lea     rcx, ?FallbackTelemetryCallback@Telemetry4UpdateCli@@SAX_NAEBUFailureInfo@wil@@@Z; Telemetry4UpdateCli::FallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x180003b8c  test    rax, rax
0x180003b8f  jz      short loc_180003B96
0x180003b91  cmp     rax, rcx
0x180003b94  jnz     short loc_180003BAA
0x180003b96  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rcx
0x180003b9d  mov     eax, 1
0x180003ba2  add     rsp, 0C8h
0x180003ba9  retn
0x180003baa  xor     edx, edx; Val
0x180003bac  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180003bb1  mov     r8d, 98h; Size
0x180003bb7  call    memset
0x180003bbc  lea     rcx, [rsp+0C8h+var_A8]; this
0x180003bc1  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
