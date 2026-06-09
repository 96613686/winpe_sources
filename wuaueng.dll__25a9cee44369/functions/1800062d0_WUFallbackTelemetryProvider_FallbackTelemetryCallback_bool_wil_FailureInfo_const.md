# WUFallbackTelemetryProvider::FallbackTelemetryCallback(bool,wil::FailureInfo const &)

- ea: `0x1800062d0`
- end: `0x1800063fa`
- name: `?FallbackTelemetryCallback@WUFallbackTelemetryProvider@@SAX_NAEBUFailureInfo@wil@@@Z`
- size: `298`
- prototype: `void __fastcall(char, const struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000109c`
- `0x1800062d0`
- `0x18000fc90`
- `0x180010064`
- `0x1800159b0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800063c1`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800063c1`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180006315`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180006315`

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
    qword_180022070 = 0;
    v5 = &qword_180022068;
    qword_180022068 = (__int64)&WUFallbackTelemetryProvider::`vftable';
    byte_180022078 = 0;
    dword_18002207C = 0;
    CallbackContext = &`WUFallbackTelemetryProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_381b80c70d062aa1595caf08c84bdedd_::_lambda_invoker_cdecl_);
    qword_180022070 = (__int64)CallbackContext;
    byte_180022078 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_18002207C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180022068 + 8))(&qword_180022068);
    InitOnceComplete(&`WUFallbackTelemetryProvider::Instance'::`2'::wrapper, 0, &qword_180022068);
  }
  LOBYTE(v4) = a1;
  (*(void (__fastcall **)(__int64 *, __int64, const struct wil::FailureInfo *))(*v5 + 16))(v5, v4, a2);
}

```

## disassembly

```asm
0x1800062d0  mov     r11, rsp
0x1800062d3  mov     [r11+18h], rbx
0x1800062d7  mov     [r11+20h], rsi
0x1800062db  push    rdi
0x1800062dc  sub     rsp, 40h
0x1800062e0  mov     rax, cs:__security_cookie
0x1800062e7  xor     rax, rsp
0x1800062ea  mov     [rsp+48h+var_18], rax
0x1800062ef  mov     rdi, rdx
0x1800062f2  mov     qword ptr [r11-28h], 0
0x1800062fa  mov     bl, cl
0x1800062fc  mov     [rsp+48h+var_20], 0
0x180006304  xor     edx, edx; dwFlags
0x180006306  lea     rcx, ?wrapper@?1??Instance@WUFallbackTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VWUFallbackTelemetryProvider@@@details@wil@@A; lpInitOnce
0x18000630d  lea     r9, [r11-28h]; lpContext
0x180006311  lea     r8, [r11-20h]; fPending
0x180006315  call    cs:__imp_InitOnceBeginInitialize
0x18000631b  test    eax, eax
0x18000631d  jz      loc_1800063C7
0x180006323  cmp     [rsp+48h+var_20], 0
0x180006328  jz      loc_1800063C7
0x18000632e  lea     rsi, qword_180022068
0x180006335  mov     cs:qword_180022070, 0
0x180006340  lea     rax, ??_7WUFallbackTelemetryProvider@@6B@; const WUFallbackTelemetryProvider::`vftable'
0x180006347  mov     [rsp+48h+var_28], rsi
0x18000634c  mov     cs:qword_180022068, rax
0x180006353  mov     cs:byte_180022078, 0
0x18000635a  mov     cs:dword_18002207C, 0
0x180006364  lea     rax, ?__hInner@?1???0StaticHandle@WUFallbackTelemetryProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `WUFallbackTelemetryProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000636b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_381b80c70d062aa1595caf08c84bdedd_@@CA@XZ; void (__cdecl *)()
0x180006372  mov     cs:CallbackContext, rax
0x180006379  call    atexit
0x18000637e  mov     rcx, cs:CallbackContext; CallbackContext
0x180006385  mov     cs:qword_180022070, rcx
0x18000638c  mov     cs:byte_180022078, 1
0x180006393  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180006398  mov     rax, cs:qword_180022068
0x18000639f  mov     rcx, rsi
0x1800063a2  mov     cs:dword_18002207C, 1
0x1800063ac  mov     rax, [rax+8]
0x1800063b0  call    _guard_dispatch_icall
0x1800063b5  mov     r8, rsi; lpContext
0x1800063b8  lea     rcx, ?wrapper@?1??Instance@WUFallbackTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VWUFallbackTelemetryProvider@@@details@wil@@A; lpInitOnce
0x1800063bf  xor     edx, edx; dwFlags
0x1800063c1  call    cs:__imp_InitOnceComplete
0x1800063c7  mov     rcx, [rsp+48h+var_28]
0x1800063cc  mov     r8, rdi
0x1800063cf  mov     dl, bl
0x1800063d1  mov     rax, [rcx]
0x1800063d4  mov     rax, [rax+10h]
0x1800063d8  call    _guard_dispatch_icall
0x1800063dd  mov     rcx, [rsp+48h+var_18]
0x1800063e2  xor     rcx, rsp; StackCookie
0x1800063e5  call    __security_check_cookie
0x1800063ea  mov     rbx, [rsp+48h+arg_10]
0x1800063ef  mov     rsi, [rsp+48h+arg_18]
0x1800063f4  add     rsp, 40h
0x1800063f8  pop     rdi
0x1800063f9  retn
```
