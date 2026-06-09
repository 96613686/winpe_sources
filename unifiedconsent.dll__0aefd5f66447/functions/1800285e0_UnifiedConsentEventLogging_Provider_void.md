# UnifiedConsentEventLogging::Provider(void)

- ea: `0x1800285e0`
- end: `0x180028699`
- name: `?Provider@UnifiedConsentEventLogging@@SAPEBU_tlgProvider_t@@XZ`
- size: `185`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001e2f0`
- `0x18001e490`

## callees

- `0x180002ce0`
- `0x18000b8b8`
- `0x1800285e0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180028684`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180028684`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180028608`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180028608`

## pseudocode

```c
const struct _tlgProvider_t *UnifiedConsentEventLogging::Provider(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  _QWORD *v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(&`UnifiedConsentEventLogging::Instance'::`2'::wrapper, 0, &v2, (LPVOID *)&v3) && v2 )
  {
    qword_18009CF50 = 0;
    v3 = &qword_18009CF48;
    qword_18009CF48 = &wil::details::FeatureLogging::`vftable';
    byte_18009CF58 = 0;
    dword_18009CF5C = 0;
    qword_18009CF60 = (struct _tlgProvider_t *)&`UnifiedConsentEventLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_196105bdc346e0048d23212faa6f0582_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_18009CF48, qword_18009CF60, v0);
    InitOnceComplete(&`UnifiedConsentEventLogging::Instance'::`2'::wrapper, 0, &qword_18009CF48);
  }
  return (const struct _tlgProvider_t *)v3[1];
}

```

## disassembly

```asm
0x1800285e0  mov     rax, rsp
0x1800285e3  push    rbx
0x1800285e4  sub     rsp, 20h
0x1800285e8  lea     r9, [rax+10h]; lpContext
0x1800285ec  mov     qword ptr [rax+10h], 0
0x1800285f4  lea     r8, [rax+8]; fPending
0x1800285f8  mov     dword ptr [rax+8], 0
0x1800285ff  xor     edx, edx; dwFlags
0x180028601  lea     rcx, ?wrapper@?1??Instance@UnifiedConsentEventLogging@@KAPEAV2@XZ@4V?$static_lazy@VUnifiedConsentEventLogging@@@details@wil@@A; lpInitOnce
0x180028608  call    cs:__imp_InitOnceBeginInitialize
0x18002860e  test    eax, eax
0x180028610  jz      short loc_18002868A
0x180028612  cmp     [rsp+28h+arg_0], 0
0x180028617  jz      short loc_18002868A
0x180028619  lea     rbx, qword_18009CF48
0x180028620  mov     cs:qword_18009CF50, 0
0x18002862b  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x180028632  mov     [rsp+28h+arg_8], rbx
0x180028637  mov     cs:qword_18009CF48, rax
0x18002863e  mov     cs:byte_18009CF58, 0
0x180028645  mov     cs:dword_18009CF5C, 0
0x18002864f  lea     rax, ?__hInner@?1???0StaticHandle@UnifiedConsentEventLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `UnifiedConsentEventLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180028656  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_196105bdc346e0048d23212faa6f0582_@@CA@XZ; void (__cdecl *)()
0x18002865d  mov     cs:qword_18009CF60, rax
0x180028664  call    atexit
0x180028669  mov     rdx, cs:qword_18009CF60; struct _tlgProvider_t *
0x180028670  mov     rcx, rbx; this
0x180028673  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180028678  mov     r8, rbx; lpContext
0x18002867b  lea     rcx, ?wrapper@?1??Instance@UnifiedConsentEventLogging@@KAPEAV2@XZ@4V?$static_lazy@VUnifiedConsentEventLogging@@@details@wil@@A; lpInitOnce
0x180028682  xor     edx, edx; dwFlags
0x180028684  call    cs:__imp_InitOnceComplete
0x18002868a  mov     rax, [rsp+28h+arg_8]
0x18002868f  mov     rax, [rax+8]
0x180028693  add     rsp, 20h
0x180028697  pop     rbx
0x180028698  retn
```
