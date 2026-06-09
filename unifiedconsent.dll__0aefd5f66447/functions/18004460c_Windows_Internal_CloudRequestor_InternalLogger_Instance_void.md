# Windows::Internal::CloudRequestor::InternalLogger::Instance(void)

- ea: `0x18004460c`
- end: `0x1800446e6`
- name: `?Instance@InternalLogger@CloudRequestor@Internal@Windows@@KAPEAV1234@XZ`
- size: `218`
- prototype: `struct Windows::Internal::CloudRequestor::InternalLogger *(void)`
- caller_count: `23`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180040598`
- `0x180045e40`
- `0x180046cd8`
- `0x180046e48`
- `0x180046fb8`
- `0x180047128`
- `0x180047260`
- `0x180047510`
- `0x1800477c0`
- `0x180048950`
- `0x18004bcd4`
- `0x18004be44`
- `0x18004c010`
- `0x18004c2c0`
- `0x18004fabc`
- `0x18004fc30`
- `0x180054d44`
- `0x180054ec0`
- `0x180056498`
- `0x18005de88`
- `0x18005e000`
- `0x180066f14`
- `0x180067090`

## callees

- `0x180002ce0`
- `0x18000b8b8`
- `0x18004460c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800446d5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800446d5`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180044634`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180044634`

## pseudocode

```c
struct Windows::Internal::CloudRequestor::InternalLogger *Windows::Internal::CloudRequestor::InternalLogger::Instance(
        void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(
         &`Windows::Internal::CloudRequestor::InternalLogger::Instance'::`2'::wrapper,
         0,
         &v2,
         (LPVOID *)&v3)
    && v2 )
  {
    qword_18009D088 = 0;
    qword_18009D078 = (__int64)&Windows::Internal::CloudRequestor::InternalLogger::`vftable'{for `Windows::Internal::CloudRequestor::ILogger'};
    v3 = &qword_18009D078;
    qword_18009D080 = &Windows::Internal::CloudRequestor::InternalLogger::`vftable'{for `wil::TraceLoggingProvider'};
    byte_18009D090 = 0;
    dword_18009D094 = 0;
    qword_18009D098 = (struct _tlgProvider_t *)&`Windows::Internal::CloudRequestor::InternalLogger::StaticHandle::StaticHandle'::`2'::__hInner;
    xmmword_18009D0A0 = 0;
    atexit(_lambda_83f0f1e994c35091134744388b002e3d_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_18009D080, qword_18009D098, v0);
    InitOnceComplete(&`Windows::Internal::CloudRequestor::InternalLogger::Instance'::`2'::wrapper, 0, &qword_18009D078);
  }
  return (struct Windows::Internal::CloudRequestor::InternalLogger *)v3;
}

```

## disassembly

```asm
0x18004460c  mov     rax, rsp
0x18004460f  push    rbx
0x180044610  sub     rsp, 20h
0x180044614  lea     r9, [rax+10h]; lpContext
0x180044618  mov     qword ptr [rax+10h], 0
0x180044620  lea     r8, [rax+8]; fPending
0x180044624  mov     dword ptr [rax+8], 0
0x18004462b  xor     edx, edx; dwFlags
0x18004462d  lea     rcx, ?wrapper@?1??Instance@InternalLogger@CloudRequestor@Internal@Windows@@KAPEAV2345@XZ@4V?$static_lazy@VInternalLogger@CloudRequestor@Internal@Windows@@@details@wil@@A; lpInitOnce
0x180044634  call    cs:__imp_InitOnceBeginInitialize
0x18004463a  test    eax, eax
0x18004463c  jz      loc_1800446DB
0x180044642  cmp     [rsp+28h+arg_0], 0
0x180044647  jz      loc_1800446DB
0x18004464d  lea     rax, ??_7InternalLogger@CloudRequestor@Internal@Windows@@6BILogger@123@@; const Windows::Internal::CloudRequestor::InternalLogger::`vftable'{for `Windows::Internal::CloudRequestor::ILogger'}
0x180044654  mov     cs:qword_18009D088, 0
0x18004465f  mov     cs:qword_18009D078, rax
0x180044666  lea     rbx, qword_18009D078
0x18004466d  lea     rax, ??_7InternalLogger@CloudRequestor@Internal@Windows@@6BTraceLoggingProvider@wil@@@; const Windows::Internal::CloudRequestor::InternalLogger::`vftable'{for `wil::TraceLoggingProvider'}
0x180044674  mov     [rsp+28h+arg_8], rbx
0x180044679  mov     cs:qword_18009D080, rax
0x180044680  mov     cs:byte_18009D090, 0
0x180044687  mov     cs:dword_18009D094, 0
0x180044691  lea     rax, ?__hInner@?1???0StaticHandle@InternalLogger@CloudRequestor@Internal@Windows@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `Windows::Internal::CloudRequestor::InternalLogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180044698  xorps   xmm0, xmm0
0x18004469b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_83f0f1e994c35091134744388b002e3d_@@CA@XZ; void (__cdecl *)()
0x1800446a2  mov     cs:qword_18009D098, rax
0x1800446a9  movdqu  cs:xmmword_18009D0A0, xmm0
0x1800446b1  call    atexit
0x1800446b6  mov     rdx, cs:qword_18009D098; struct _tlgProvider_t *
0x1800446bd  lea     rcx, qword_18009D080; this
0x1800446c4  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x1800446c9  mov     r8, rbx; lpContext
0x1800446cc  lea     rcx, ?wrapper@?1??Instance@InternalLogger@CloudRequestor@Internal@Windows@@KAPEAV2345@XZ@4V?$static_lazy@VInternalLogger@CloudRequestor@Internal@Windows@@@details@wil@@A; lpInitOnce
0x1800446d3  xor     edx, edx; dwFlags
0x1800446d5  call    cs:__imp_InitOnceComplete
0x1800446db  mov     rax, [rsp+28h+arg_8]
0x1800446e0  add     rsp, 20h
0x1800446e4  pop     rbx
0x1800446e5  retn
```
