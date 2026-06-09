# wil::details::FeatureLogging::Instance(void)

- ea: `0x14001784c`
- end: `0x140017931`
- name: `?Instance@FeatureLogging@details@wil@@KAPEAV123@XZ`
- size: `229`
- prototype: `struct wil::details::FeatureLogging *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140017360`

## callees

- `0x1400014f4`
- `0x140002878`
- `0x14001784c`
- `0x14001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x140017874`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x140017874`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140017920`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140017920`

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
    qword_14002DCB8 = 0;
    v2 = &qword_14002DCB0;
    qword_14002DCB0 = (__int64)&wil::details::FeatureLogging::`vftable';
    byte_14002DCC0 = 0;
    dword_14002DCC4 = 0;
    CallbackContext = &`wil::details::FeatureLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_::_lambda_invoker_cdecl_);
    qword_14002DCB8 = (__int64)CallbackContext;
    byte_14002DCC0 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_14002DCC4 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_14002DCB0 + 8))(&qword_14002DCB0);
    InitOnceComplete(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &qword_14002DCB0);
  }
  return (struct wil::details::FeatureLogging *)v2;
}

```

## disassembly

```asm
0x14001784c  mov     rax, rsp
0x14001784f  push    rbx
0x140017850  sub     rsp, 20h
0x140017854  lea     r9, [rax+10h]; lpContext
0x140017858  mov     qword ptr [rax+10h], 0
0x140017860  lea     r8, [rax+8]; fPending
0x140017864  mov     dword ptr [rax+8], 0
0x14001786b  xor     edx, edx; dwFlags
0x14001786d  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x140017874  call    cs:__imp_InitOnceBeginInitialize
0x14001787a  test    eax, eax
0x14001787c  jz      loc_140017926
0x140017882  cmp     [rsp+28h+arg_0], 0
0x140017887  jz      loc_140017926
0x14001788d  lea     rbx, qword_14002DCB0
0x140017894  mov     cs:qword_14002DCB8, 0
0x14001789f  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x1400178a6  mov     [rsp+28h+arg_8], rbx
0x1400178ab  mov     cs:qword_14002DCB0, rax
0x1400178b2  mov     cs:byte_14002DCC0, 0
0x1400178b9  mov     cs:dword_14002DCC4, 0
0x1400178c3  lea     rax, ?__hInner@?1???0StaticHandle@FeatureLogging@details@wil@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `wil::details::FeatureLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1400178ca  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_@@CA@XZ; void (__cdecl *)()
0x1400178d1  mov     cs:CallbackContext, rax
0x1400178d8  call    atexit
0x1400178dd  mov     rcx, cs:CallbackContext; CallbackContext
0x1400178e4  mov     cs:qword_14002DCB8, rcx
0x1400178eb  mov     cs:byte_14002DCC0, 1
0x1400178f2  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1400178f7  mov     rax, cs:qword_14002DCB0
0x1400178fe  mov     rcx, rbx
0x140017901  mov     cs:dword_14002DCC4, 1
0x14001790b  mov     rax, [rax+8]
0x14001790f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017914  mov     r8, rbx; lpContext
0x140017917  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x14001791e  xor     edx, edx; dwFlags
0x140017920  call    cs:__imp_InitOnceComplete
0x140017926  mov     rax, [rsp+28h+arg_8]
0x14001792b  add     rsp, 20h
0x14001792f  pop     rbx
0x140017930  retn
```
