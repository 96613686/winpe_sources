# WUFallbackTelemetryProvider::FallbackTelemetryCallback(bool,wil::FailureInfo const &)

- ea: `0x1800063f0`
- end: `0x18000651a`
- name: `?FallbackTelemetryCallback@WUFallbackTelemetryProvider@@SAX_NAEBUFailureInfo@wil@@@Z`
- size: `298`
- prototype: `void __fastcall(bool, const struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800016fc`
- `0x1800063f0`
- `0x180042630`
- `0x180042a04`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800064e1`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800064e1`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180006435`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180006435`

## pseudocode

```c
void __fastcall WUFallbackTelemetryProvider::FallbackTelemetryCallback(char a1, const struct wil::FailureInfo *a2)
{
  __int64 v4; // rdx
  __int64 *v5; // [rsp+20h] [rbp-28h] BYREF
  BOOL v6; // [rsp+28h] [rbp-20h] BYREF

  v5 = 0;
  v6 = 0;
  if ( InitOnceBeginInitialize(&`WUFallbackTelemetryProvider::Instance'::`2'::wrapper, 0, &v6, (LPVOID *)&v5) && v6 )
  {
    qword_180076670 = 0;
    v5 = &qword_180076668;
    qword_180076668 = (__int64)&DeploymentHelperPrivate::UpdateDeploymentTelemetry::`vftable';
    byte_180076678 = 0;
    dword_18007667C = 0;
    CallbackContext = &`WUFallbackTelemetryProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_381b80c70d062aa1595caf08c84bdedd_::_lambda_invoker_cdecl_);
    qword_180076670 = (__int64)CallbackContext;
    byte_180076678 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_18007667C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180076668 + 8))(&qword_180076668);
    InitOnceComplete(&`WUFallbackTelemetryProvider::Instance'::`2'::wrapper, 0, &qword_180076668);
  }
  LOBYTE(v4) = a1;
  (*(void (__fastcall **)(__int64 *, __int64, const struct wil::FailureInfo *))(*v5 + 16))(v5, v4, a2);
}

```

## disassembly

```asm
0x1800063f0  mov     r11, rsp
0x1800063f3  mov     [r11+18h], rbx
0x1800063f7  mov     [r11+20h], rsi
0x1800063fb  push    rdi
0x1800063fc  sub     rsp, 40h
0x180006400  mov     rax, cs:__security_cookie
0x180006407  xor     rax, rsp
0x18000640a  mov     [rsp+48h+var_18], rax
0x18000640f  mov     rdi, rdx
0x180006412  mov     qword ptr [r11-28h], 0
0x18000641a  mov     bl, cl
0x18000641c  mov     [rsp+48h+var_20], 0
0x180006424  xor     edx, edx; dwFlags
0x180006426  lea     rcx, ?wrapper@?1??Instance@WUFallbackTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VWUFallbackTelemetryProvider@@@details@wil@@A; lpInitOnce
0x18000642d  lea     r9, [r11-28h]; lpContext
0x180006431  lea     r8, [r11-20h]; fPending
0x180006435  call    cs:__imp_InitOnceBeginInitialize
0x18000643b  test    eax, eax
0x18000643d  jz      loc_1800064E7
0x180006443  cmp     [rsp+48h+var_20], 0
0x180006448  jz      loc_1800064E7
0x18000644e  lea     rsi, qword_180076668
0x180006455  mov     cs:qword_180076670, 0
0x180006460  lea     rax, ??_7UpdateDeploymentTelemetry@DeploymentHelperPrivate@@6B@; const DeploymentHelperPrivate::UpdateDeploymentTelemetry::`vftable'
0x180006467  mov     [rsp+48h+var_28], rsi
0x18000646c  mov     cs:qword_180076668, rax
0x180006473  mov     cs:byte_180076678, 0
0x18000647a  mov     cs:dword_18007667C, 0
0x180006484  lea     rax, ?__hInner@?1???0StaticHandle@WUFallbackTelemetryProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `WUFallbackTelemetryProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000648b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_381b80c70d062aa1595caf08c84bdedd_@@CA@XZ; void (__cdecl *)()
0x180006492  mov     cs:CallbackContext, rax
0x180006499  call    atexit
0x18000649e  mov     rcx, cs:CallbackContext; CallbackContext
0x1800064a5  mov     cs:qword_180076670, rcx
0x1800064ac  mov     cs:byte_180076678, 1
0x1800064b3  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1800064b8  mov     rax, cs:qword_180076668
0x1800064bf  mov     rcx, rsi
0x1800064c2  mov     cs:dword_18007667C, 1
0x1800064cc  mov     rax, [rax+8]
0x1800064d0  call    _guard_dispatch_icall
0x1800064d5  mov     r8, rsi; lpContext
0x1800064d8  lea     rcx, ?wrapper@?1??Instance@WUFallbackTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VWUFallbackTelemetryProvider@@@details@wil@@A; lpInitOnce
0x1800064df  xor     edx, edx; dwFlags
0x1800064e1  call    cs:__imp_InitOnceComplete
0x1800064e7  mov     rcx, [rsp+48h+var_28]
0x1800064ec  mov     r8, rdi
0x1800064ef  mov     dl, bl
0x1800064f1  mov     rax, [rcx]
0x1800064f4  mov     rax, [rax+10h]
0x1800064f8  call    _guard_dispatch_icall
0x1800064fd  mov     rcx, [rsp+48h+var_18]
0x180006502  xor     rcx, rsp; StackCookie
0x180006505  call    __security_check_cookie
0x18000650a  mov     rbx, [rsp+48h+arg_10]
0x18000650f  mov     rsi, [rsp+48h+arg_18]
0x180006514  add     rsp, 40h
0x180006518  pop     rdi
0x180006519  retn
```
