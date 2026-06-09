# wil::details::FeatureLogging::Instance(void)

- ea: `0x18001b3a4`
- end: `0x18001b477`
- name: `?Instance@FeatureLogging@details@wil@@KAPEAV123@XZ`
- size: `211`
- prototype: `struct wil::details::FeatureLogging *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001ab70`

## callees

- `0x180007660`
- `0x180007da0`
- `0x18001b3a4`
- `0x18001b4fc`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001b3dd`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001b3dd`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001b459`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001b459`

## pseudocode

```c
struct wil::details::FeatureLogging *wil::details::FeatureLogging::Instance(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  LPVOID Context; // [rsp+20h] [rbp-28h] BYREF
  WINBOOL fPending; // [rsp+28h] [rbp-20h] BYREF

  Context = 0;
  fPending = 0;
  if ( __std_init_once_begin_initialize(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &fPending, &Context)
    && fPending )
  {
    qword_180095B60 = 0;
    Context = &qword_180095B58;
    qword_180095B58 = &Windows::Telemetry::Base::`vftable';
    byte_180095B68 = 0;
    dword_180095B6C = 0;
    qword_180095B70 = (struct _tlgProvider_t *)&`wil::details::FeatureLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180095B58, qword_180095B70, v0);
    InitOnceComplete(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &qword_180095B58);
  }
  return (struct wil::details::FeatureLogging *)Context;
}

```

## disassembly

```asm
0x18001b3a4  push    rbx
0x18001b3a6  sub     rsp, 40h
0x18001b3aa  mov     rax, cs:__security_cookie
0x18001b3b1  xor     rax, rsp
0x18001b3b4  mov     [rsp+48h+var_18], rax
0x18001b3b9  lea     r9, [rsp+48h+Context]; lpContext
0x18001b3be  mov     [rsp+48h+Context], 0
0x18001b3c7  lea     r8, [rsp+48h+fPending]; fPending
0x18001b3cc  mov     [rsp+48h+fPending], 0
0x18001b3d4  xor     edx, edx; dwFlags
0x18001b3d6  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x18001b3dd  call    cs:__imp___std_init_once_begin_initialize
0x18001b3e3  test    eax, eax
0x18001b3e5  jz      short loc_18001B45F
0x18001b3e7  cmp     [rsp+48h+fPending], 0
0x18001b3ec  jz      short loc_18001B45F
0x18001b3ee  lea     rbx, qword_180095B58
0x18001b3f5  mov     cs:qword_180095B60, 0
0x18001b400  lea     rax, ??_7Base@Telemetry@Windows@@6B@; const Windows::Telemetry::Base::`vftable'
0x18001b407  mov     [rsp+48h+Context], rbx
0x18001b40c  mov     cs:qword_180095B58, rax
0x18001b413  mov     cs:byte_180095B68, 0
0x18001b41a  mov     cs:dword_180095B6C, 0
0x18001b424  lea     rax, ?__hInner@?1???0StaticHandle@FeatureLogging@details@wil@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `wil::details::FeatureLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18001b42b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_@@CA@XZ; void (__cdecl *)()
0x18001b432  mov     cs:qword_180095B70, rax
0x18001b439  call    atexit
0x18001b43e  mov     rdx, cs:qword_180095B70; struct _tlgProvider_t *
0x18001b445  mov     rcx, rbx; this
0x18001b448  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18001b44d  mov     r8, rbx; lpContext
0x18001b450  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x18001b457  xor     edx, edx; dwFlags
0x18001b459  call    cs:__imp_InitOnceComplete
0x18001b45f  mov     rax, [rsp+48h+Context]
0x18001b464  mov     rcx, [rsp+48h+var_18]
0x18001b469  xor     rcx, rsp; StackCookie
0x18001b46c  call    __security_check_cookie
0x18001b471  add     rsp, 40h
0x18001b475  pop     rbx
0x18001b476  retn
```
