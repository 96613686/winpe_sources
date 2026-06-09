# UnifiedConsentLogging::Instance(void)

- ea: `0x180009de8`
- end: `0x180009e9d`
- name: `?Instance@UnifiedConsentLogging@@KAPEAV1@XZ`
- size: `181`
- prototype: `struct UnifiedConsentLogging *(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007540`
- `0x180018290`

## callees

- `0x180002ce0`
- `0x180009de8`
- `0x18000b8b8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180009e8c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180009e8c`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180009e10`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180009e10`

## pseudocode

```c
struct UnifiedConsentLogging *UnifiedConsentLogging::Instance(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  LPVOID v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(&`UnifiedConsentLogging::Instance'::`2'::wrapper, 0, &v2, &v3) && v2 )
  {
    qword_18009CAD0 = 0;
    v3 = &qword_18009CAC8;
    qword_18009CAC8 = &wil::details::FeatureLogging::`vftable';
    byte_18009CAD8 = 0;
    dword_18009CADC = 0;
    qword_18009CAE0 = (struct _tlgProvider_t *)&`UnifiedConsentLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_dc7ae61080861b5490b181e8e22affe5_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_18009CAC8, qword_18009CAE0, v0);
    InitOnceComplete(&`UnifiedConsentLogging::Instance'::`2'::wrapper, 0, &qword_18009CAC8);
  }
  return (struct UnifiedConsentLogging *)v3;
}

```

## disassembly

```asm
0x180009de8  mov     rax, rsp
0x180009deb  push    rbx
0x180009dec  sub     rsp, 20h
0x180009df0  lea     r9, [rax+10h]; lpContext
0x180009df4  mov     qword ptr [rax+10h], 0
0x180009dfc  lea     r8, [rax+8]; fPending
0x180009e00  mov     dword ptr [rax+8], 0
0x180009e07  xor     edx, edx; dwFlags
0x180009e09  lea     rcx, ?wrapper@?1??Instance@UnifiedConsentLogging@@KAPEAV2@XZ@4V?$static_lazy@VUnifiedConsentLogging@@@details@wil@@A; lpInitOnce
0x180009e10  call    cs:__imp_InitOnceBeginInitialize
0x180009e16  test    eax, eax
0x180009e18  jz      short loc_180009E92
0x180009e1a  cmp     [rsp+28h+arg_0], 0
0x180009e1f  jz      short loc_180009E92
0x180009e21  lea     rbx, qword_18009CAC8
0x180009e28  mov     cs:qword_18009CAD0, 0
0x180009e33  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x180009e3a  mov     [rsp+28h+arg_8], rbx
0x180009e3f  mov     cs:qword_18009CAC8, rax
0x180009e46  mov     cs:byte_18009CAD8, 0
0x180009e4d  mov     cs:dword_18009CADC, 0
0x180009e57  lea     rax, ?__hInner@?1???0StaticHandle@UnifiedConsentLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `UnifiedConsentLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180009e5e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_dc7ae61080861b5490b181e8e22affe5_@@CA@XZ; void (__cdecl *)()
0x180009e65  mov     cs:qword_18009CAE0, rax
0x180009e6c  call    atexit
0x180009e71  mov     rdx, cs:qword_18009CAE0; struct _tlgProvider_t *
0x180009e78  mov     rcx, rbx; this
0x180009e7b  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180009e80  mov     r8, rbx; lpContext
0x180009e83  lea     rcx, ?wrapper@?1??Instance@UnifiedConsentLogging@@KAPEAV2@XZ@4V?$static_lazy@VUnifiedConsentLogging@@@details@wil@@A; lpInitOnce
0x180009e8a  xor     edx, edx; dwFlags
0x180009e8c  call    cs:__imp_InitOnceComplete
0x180009e92  mov     rax, [rsp+28h+arg_8]
0x180009e97  add     rsp, 20h
0x180009e9b  pop     rbx
0x180009e9c  retn
```
