# WUFallbackTelemetryProvider::FallbackTelemetryCallback(bool,wil::FailureInfo const &)

- ea: `0x180009ff0`
- end: `0x18000a11a`
- name: `?FallbackTelemetryCallback@WUFallbackTelemetryProvider@@SAX_NAEBUFailureInfo@wil@@@Z`
- size: `298`
- prototype: `void __fastcall(bool, const struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000109c`
- `0x180009ff0`
- `0x18000fce0`
- `0x1800100b4`
- `0x180015a00`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000a0e1`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000a0e1`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000a035`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000a035`

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
    qword_1800224E0 = 0;
    v5 = &qword_1800224D8;
    qword_1800224D8 = (__int64)&WUFallbackTelemetryProvider::`vftable';
    byte_1800224E8 = 0;
    dword_1800224EC = 0;
    CallbackContext = &`WUFallbackTelemetryProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_381b80c70d062aa1595caf08c84bdedd_::_lambda_invoker_cdecl_);
    qword_1800224E0 = (__int64)CallbackContext;
    byte_1800224E8 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_1800224EC = 1;
    (*(void (__fastcall **)(__int64 *))(qword_1800224D8 + 8))(&qword_1800224D8);
    InitOnceComplete(&`WUFallbackTelemetryProvider::Instance'::`2'::wrapper, 0, &qword_1800224D8);
  }
  LOBYTE(v4) = a1;
  (*(void (__fastcall **)(__int64 *, __int64, const struct wil::FailureInfo *))(*v5 + 16))(v5, v4, a2);
}

```

## disassembly

```asm
0x180009ff0  mov     r11, rsp
0x180009ff3  mov     [r11+18h], rbx
0x180009ff7  mov     [r11+20h], rsi
0x180009ffb  push    rdi
0x180009ffc  sub     rsp, 40h
0x18000a000  mov     rax, cs:__security_cookie
0x18000a007  xor     rax, rsp
0x18000a00a  mov     [rsp+48h+var_18], rax
0x18000a00f  mov     rdi, rdx
0x18000a012  mov     qword ptr [r11-28h], 0
0x18000a01a  mov     bl, cl
0x18000a01c  mov     [rsp+48h+var_20], 0
0x18000a024  xor     edx, edx; dwFlags
0x18000a026  lea     rcx, ?wrapper@?1??Instance@WUFallbackTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VWUFallbackTelemetryProvider@@@details@wil@@A; lpInitOnce
0x18000a02d  lea     r9, [r11-28h]; lpContext
0x18000a031  lea     r8, [r11-20h]; fPending
0x18000a035  call    cs:__imp_InitOnceBeginInitialize
0x18000a03b  test    eax, eax
0x18000a03d  jz      loc_18000A0E7
0x18000a043  cmp     [rsp+48h+var_20], 0
0x18000a048  jz      loc_18000A0E7
0x18000a04e  lea     rsi, qword_1800224D8
0x18000a055  mov     cs:qword_1800224E0, 0
0x18000a060  lea     rax, ??_7WUFallbackTelemetryProvider@@6B@; const WUFallbackTelemetryProvider::`vftable'
0x18000a067  mov     [rsp+48h+var_28], rsi
0x18000a06c  mov     cs:qword_1800224D8, rax
0x18000a073  mov     cs:byte_1800224E8, 0
0x18000a07a  mov     cs:dword_1800224EC, 0
0x18000a084  lea     rax, ?__hInner@?1???0StaticHandle@WUFallbackTelemetryProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `WUFallbackTelemetryProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000a08b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_381b80c70d062aa1595caf08c84bdedd_@@CA@XZ; void (__cdecl *)()
0x18000a092  mov     cs:CallbackContext, rax
0x18000a099  call    atexit
0x18000a09e  mov     rcx, cs:CallbackContext; CallbackContext
0x18000a0a5  mov     cs:qword_1800224E0, rcx
0x18000a0ac  mov     cs:byte_1800224E8, 1
0x18000a0b3  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000a0b8  mov     rax, cs:qword_1800224D8
0x18000a0bf  mov     rcx, rsi
0x18000a0c2  mov     cs:dword_1800224EC, 1
0x18000a0cc  mov     rax, [rax+8]
0x18000a0d0  call    _guard_dispatch_icall
0x18000a0d5  mov     r8, rsi; lpContext
0x18000a0d8  lea     rcx, ?wrapper@?1??Instance@WUFallbackTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VWUFallbackTelemetryProvider@@@details@wil@@A; lpInitOnce
0x18000a0df  xor     edx, edx; dwFlags
0x18000a0e1  call    cs:__imp_InitOnceComplete
0x18000a0e7  mov     rcx, [rsp+48h+var_28]
0x18000a0ec  mov     r8, rdi
0x18000a0ef  mov     dl, bl
0x18000a0f1  mov     rax, [rcx]
0x18000a0f4  mov     rax, [rax+10h]
0x18000a0f8  call    _guard_dispatch_icall
0x18000a0fd  mov     rcx, [rsp+48h+var_18]
0x18000a102  xor     rcx, rsp; StackCookie
0x18000a105  call    __security_check_cookie
0x18000a10a  mov     rbx, [rsp+48h+arg_10]
0x18000a10f  mov     rsi, [rsp+48h+arg_18]
0x18000a114  add     rsp, 40h
0x18000a118  pop     rdi
0x18000a119  retn
```
