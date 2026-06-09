# DllMain

- ea: `0x180003aa8`
- end: `0x180003b9f`
- name: `DllMain`
- size: `247`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180066784`

## callees

- `0x180003aa8`
- `0x180003ba8`
- `0x180003cd8`
- `0x180003ec8`
- `0x180003ef8`
- `0x18005aee8`
- `0x1800672e8`
- `0x18006bad0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180003ae4`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180003ae4`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180003aea`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180003afb`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180003aea`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180003afb`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  _BOOL8 v4; // rbx
  DWORD v6; // eax
  const struct wil::FailureInfo *v7; // rdx
  _BYTE v8[168]; // [rsp+20h] [rbp-A8h] BYREF

  LODWORD(v4) = 1;
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      McGenEventRegister_EventRegister(hinstDLL, fdwReason, lpvReserved);
      DisableThreadLibraryCalls(hinstDLL);
      dwTlsIndex = TlsAlloc();
      if ( dwTlsIndex == -1 )
      {
        v6 = *(&dwTlsIndex + 1);
      }
      else
      {
        v6 = TlsAlloc();
        *(&dwTlsIndex + 1) = v6;
      }
      g_hinst = hinstDLL;
      v4 = v6 != -1;
      if ( wil::details::g_pfnTelemetryCallback
        && (void (*)(bool, const struct wil::FailureInfo *))wil::details::g_pfnTelemetryCallback != SHCoreTelemetry::FallbackTelemetryCallback )
      {
        memset_0(v8, 0, 0x98u);
        wil::details::WilFailFast((wil::details *)v8, v7);
      }
      wil::details::g_pfnTelemetryCallback = (__int64)SHCoreTelemetry::FallbackTelemetryCallback;
      *(_DWORD *)(wil::details::static_lazy<SHCoreTelemetry>::get(
                    SHCoreTelemetry::FallbackTelemetryCallback,
                    _lambda_974da4771b5d0d3605f7e6cfbdf701fc_::_lambda_invoker_cdecl_)
                + 20) = 2;
    }
  }
  else
  {
    dword_1800DEEBC = 1;
    if ( dword_1800DEEB8 )
      WindowsPolicies_ProcessAttachDetach(0, fdwReason, lpvReserved);
    if ( g_oplockUsed )
      OplockTipTests::OplockTipTests_Cleanup((OplockTipTests *)hinstDLL);
    McGenEventUnregister_EventUnregister(hinstDLL, *(_QWORD *)&fdwReason, lpvReserved);
  }
  return v4;
}

```

## disassembly

```asm
0x180003aa8  mov     [rsp+arg_0], rbx
0x180003aad  push    rdi
0x180003aae  sub     rsp, 0C0h
0x180003ab5  mov     rdi, rcx
0x180003ab8  mov     ebx, 1
0x180003abd  test    edx, edx
0x180003abf  jz      loc_180003B45
0x180003ac5  cmp     edx, ebx
0x180003ac7  jz      short loc_180003ADC
0x180003ac9  mov     eax, ebx
0x180003acb  mov     rbx, [rsp+0C8h+arg_0]
0x180003ad3  add     rsp, 0C0h
0x180003ada  pop     rdi
0x180003adb  retn
0x180003adc  call    McGenEventRegister_EventRegister
0x180003ae1  mov     rcx, rdi; hLibModule
0x180003ae4  call    cs:__imp_DisableThreadLibraryCalls
0x180003aea  call    cs:__imp_TlsAlloc
0x180003af0  mov     dword ptr cs:dwTlsIndex, eax
0x180003af6  cmp     eax, 0FFFFFFFFh
0x180003af9  jz      short loc_180003B6E
0x180003afb  call    cs:__imp_TlsAlloc
0x180003b01  mov     dword ptr cs:dwTlsIndex+4, eax
0x180003b07  xor     ebx, ebx
0x180003b09  mov     cs:g_hinst, rdi
0x180003b10  cmp     eax, 0FFFFFFFFh
0x180003b13  lea     rcx, ?FallbackTelemetryCallback@SHCoreTelemetry@@SAX_NAEBUFailureInfo@wil@@@Z; SHCoreTelemetry::FallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x180003b1a  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180003b21  setnz   bl
0x180003b24  test    rax, rax
0x180003b27  jnz     short loc_180003B76
0x180003b29  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_974da4771b5d0d3605f7e6cfbdf701fc_@@CA@XZ; _lambda_974da4771b5d0d3605f7e6cfbdf701fc_::_lambda_invoker_cdecl_(void)
0x180003b30  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rcx
0x180003b37  call    ?get@?$static_lazy@VSHCoreTelemetry@@@details@wil@@QEAAPEAVSHCoreTelemetry@@P6AXXZ@Z; wil::details::static_lazy<SHCoreTelemetry>::get(void (*)(void))
0x180003b3c  mov     dword ptr [rax+14h], 2
0x180003b43  jmp     short loc_180003AC9
0x180003b45  cmp     cs:dword_1800DEEB8, 0
0x180003b4c  mov     cs:dword_1800DEEBC, ebx
0x180003b52  jz      short loc_180003B5B
0x180003b54  xor     ecx, ecx
0x180003b56  call    WindowsPolicies_ProcessAttachDetach
0x180003b5b  cmp     cs:?g_oplockUsed@@3_NA, 0; bool g_oplockUsed
0x180003b62  jnz     short loc_180003B98
0x180003b64  call    McGenEventUnregister_EventUnregister
0x180003b69  jmp     loc_180003AC9
0x180003b6e  mov     eax, dword ptr cs:dwTlsIndex+4
0x180003b74  jmp     short loc_180003B07
0x180003b76  cmp     rax, rcx
0x180003b79  jz      short loc_180003B29
0x180003b7b  xor     edx, edx; Val
0x180003b7d  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180003b82  mov     r8d, 98h; Size
0x180003b88  call    memset_0
0x180003b8d  lea     rcx, [rsp+0C8h+var_A8]; this
0x180003b92  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003b98  call    ?OplockTipTests_Cleanup@OplockTipTests@@YAXXZ; OplockTipTests::OplockTipTests_Cleanup(void)
0x180003b9d  jmp     short loc_180003B64
```
