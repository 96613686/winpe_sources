# wil::details::FeatureLogging::Instance(void)

- ea: `0x18000aacc`
- end: `0x18000abb1`
- name: `?Instance@FeatureLogging@details@wil@@KAPEAV123@XZ`
- size: `229`
- prototype: `struct wil::details::FeatureLogging *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180009d30`

## callees

- `0x180001008`
- `0x180002f10`
- `0x18000aacc`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000aba0`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000aba0`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000aaf4`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000aaf4`

## pseudocode

```c
struct wil::details::FeatureLogging *wil::details::FeatureLogging::Instance(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2) && v1 )
  {
    qword_180047998 = 0;
    v2 = &qword_180047990;
    qword_180047990 = (__int64)&wil::details::FeatureLogging::`vftable';
    byte_1800479A0 = 0;
    dword_1800479A4 = 0;
    CallbackContext = &`wil::details::FeatureLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_::_lambda_invoker_cdecl_);
    qword_180047998 = (__int64)CallbackContext;
    byte_1800479A0 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_1800479A4 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180047990 + 8))(&qword_180047990);
    InitOnceComplete(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &qword_180047990);
  }
  return (struct wil::details::FeatureLogging *)v2;
}

```

## disassembly

```asm
0x18000aacc  mov     rax, rsp
0x18000aacf  push    rbx
0x18000aad0  sub     rsp, 20h
0x18000aad4  lea     r9, [rax+10h]; lpContext
0x18000aad8  mov     qword ptr [rax+10h], 0
0x18000aae0  lea     r8, [rax+8]; fPending
0x18000aae4  mov     dword ptr [rax+8], 0
0x18000aaeb  xor     edx, edx; dwFlags
0x18000aaed  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x18000aaf4  call    cs:__imp_InitOnceBeginInitialize
0x18000aafa  test    eax, eax
0x18000aafc  jz      loc_18000ABA6
0x18000ab02  cmp     [rsp+28h+arg_0], 0
0x18000ab07  jz      loc_18000ABA6
0x18000ab0d  lea     rbx, qword_180047990
0x18000ab14  mov     cs:qword_180047998, 0
0x18000ab1f  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x18000ab26  mov     [rsp+28h+arg_8], rbx
0x18000ab2b  mov     cs:qword_180047990, rax
0x18000ab32  mov     cs:byte_1800479A0, 0
0x18000ab39  mov     cs:dword_1800479A4, 0
0x18000ab43  lea     rax, ?__hInner@?1???0StaticHandle@FeatureLogging@details@wil@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `wil::details::FeatureLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000ab4a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_@@CA@XZ; void (__cdecl *)()
0x18000ab51  mov     cs:CallbackContext, rax
0x18000ab58  call    atexit
0x18000ab5d  mov     rcx, cs:CallbackContext; CallbackContext
0x18000ab64  mov     cs:qword_180047998, rcx
0x18000ab6b  mov     cs:byte_1800479A0, 1
0x18000ab72  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000ab77  mov     rax, cs:qword_180047990
0x18000ab7e  mov     rcx, rbx
0x18000ab81  mov     cs:dword_1800479A4, 1
0x18000ab8b  mov     rax, [rax+8]
0x18000ab8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab94  mov     r8, rbx; lpContext
0x18000ab97  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x18000ab9e  xor     edx, edx; dwFlags
0x18000aba0  call    cs:__imp_InitOnceComplete
0x18000aba6  mov     rax, [rsp+28h+arg_8]
0x18000abab  add     rsp, 20h
0x18000abaf  pop     rbx
0x18000abb0  retn
```
