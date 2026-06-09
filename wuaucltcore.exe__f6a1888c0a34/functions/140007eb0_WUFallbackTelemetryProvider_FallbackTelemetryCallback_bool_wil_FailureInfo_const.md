# WUFallbackTelemetryProvider::FallbackTelemetryCallback(bool,wil::FailureInfo const &)

- ea: `0x140007eb0`
- end: `0x140007fda`
- name: `?FallbackTelemetryCallback@WUFallbackTelemetryProvider@@SAX_NAEBUFailureInfo@wil@@@Z`
- size: `298`
- prototype: `void __fastcall(bool, const struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1400016fc`
- `0x140007eb0`
- `0x14001aa60`
- `0x14001acd4`
- `0x1400206e0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x140007ef5`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x140007ef5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140007fa1`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140007fa1`

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
    qword_14002F198 = 0;
    v5 = &qword_14002F190;
    qword_14002F190 = (__int64)&WUFallbackTelemetryProvider::`vftable';
    byte_14002F1A0 = 0;
    dword_14002F1A4 = 0;
    CallbackContext = &`WUFallbackTelemetryProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_381b80c70d062aa1595caf08c84bdedd_::_lambda_invoker_cdecl_);
    qword_14002F198 = (__int64)CallbackContext;
    byte_14002F1A0 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_14002F1A4 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_14002F190 + 8))(&qword_14002F190);
    InitOnceComplete(&`WUFallbackTelemetryProvider::Instance'::`2'::wrapper, 0, &qword_14002F190);
  }
  LOBYTE(v4) = a1;
  (*(void (__fastcall **)(__int64 *, __int64, const struct wil::FailureInfo *))(*v5 + 16))(v5, v4, a2);
}

```

## disassembly

```asm
0x140007eb0  mov     r11, rsp
0x140007eb3  mov     [r11+18h], rbx
0x140007eb7  mov     [r11+20h], rsi
0x140007ebb  push    rdi
0x140007ebc  sub     rsp, 40h
0x140007ec0  mov     rax, cs:__security_cookie
0x140007ec7  xor     rax, rsp
0x140007eca  mov     [rsp+48h+var_18], rax
0x140007ecf  mov     rdi, rdx
0x140007ed2  mov     qword ptr [r11-28h], 0
0x140007eda  mov     bl, cl
0x140007edc  mov     [rsp+48h+var_20], 0
0x140007ee4  xor     edx, edx; dwFlags
0x140007ee6  lea     rcx, ?wrapper@?1??Instance@WUFallbackTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VWUFallbackTelemetryProvider@@@details@wil@@A; lpInitOnce
0x140007eed  lea     r9, [r11-28h]; lpContext
0x140007ef1  lea     r8, [r11-20h]; fPending
0x140007ef5  call    cs:__imp_InitOnceBeginInitialize
0x140007efb  test    eax, eax
0x140007efd  jz      loc_140007FA7
0x140007f03  cmp     [rsp+48h+var_20], 0
0x140007f08  jz      loc_140007FA7
0x140007f0e  lea     rsi, qword_14002F190
0x140007f15  mov     cs:qword_14002F198, 0
0x140007f20  lea     rax, ??_7WUFallbackTelemetryProvider@@6B@; const WUFallbackTelemetryProvider::`vftable'
0x140007f27  mov     [rsp+48h+var_28], rsi
0x140007f2c  mov     cs:qword_14002F190, rax
0x140007f33  mov     cs:byte_14002F1A0, 0
0x140007f3a  mov     cs:dword_14002F1A4, 0
0x140007f44  lea     rax, ?__hInner@?1???0StaticHandle@WUFallbackTelemetryProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `WUFallbackTelemetryProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x140007f4b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_381b80c70d062aa1595caf08c84bdedd_@@CA@XZ; void (__cdecl *)()
0x140007f52  mov     cs:CallbackContext, rax
0x140007f59  call    atexit
0x140007f5e  mov     rcx, cs:CallbackContext; CallbackContext
0x140007f65  mov     cs:qword_14002F198, rcx
0x140007f6c  mov     cs:byte_14002F1A0, 1
0x140007f73  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x140007f78  mov     rax, cs:qword_14002F190
0x140007f7f  mov     rcx, rsi
0x140007f82  mov     cs:dword_14002F1A4, 1
0x140007f8c  mov     rax, [rax+8]
0x140007f90  call    _guard_dispatch_icall
0x140007f95  mov     r8, rsi; lpContext
0x140007f98  lea     rcx, ?wrapper@?1??Instance@WUFallbackTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VWUFallbackTelemetryProvider@@@details@wil@@A; lpInitOnce
0x140007f9f  xor     edx, edx; dwFlags
0x140007fa1  call    cs:__imp_InitOnceComplete
0x140007fa7  mov     rcx, [rsp+48h+var_28]
0x140007fac  mov     r8, rdi
0x140007faf  mov     dl, bl
0x140007fb1  mov     rax, [rcx]
0x140007fb4  mov     rax, [rax+10h]
0x140007fb8  call    _guard_dispatch_icall
0x140007fbd  mov     rcx, [rsp+48h+var_18]
0x140007fc2  xor     rcx, rsp; StackCookie
0x140007fc5  call    __security_check_cookie
0x140007fca  mov     rbx, [rsp+48h+arg_10]
0x140007fcf  mov     rsi, [rsp+48h+arg_18]
0x140007fd4  add     rsp, 40h
0x140007fd8  pop     rdi
0x140007fd9  retn
```
