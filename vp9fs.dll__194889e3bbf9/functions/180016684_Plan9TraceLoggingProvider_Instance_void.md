# Plan9TraceLoggingProvider::Instance(void)

- ea: `0x180016684`
- end: `0x180016757`
- name: `?Instance@Plan9TraceLoggingProvider@@KAPEAV1@XZ`
- size: `211`
- prototype: `struct Plan9TraceLoggingProvider *(void)`
- caller_count: `10`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000cd74`
- `0x18000cdf4`
- `0x180010d90`
- `0x180016760`
- `0x1800183c0`
- `0x180019414`
- `0x1800273f0`
- `0x180027950`
- `0x18002cc94`
- `0x18002cd54`

## callees

- `0x180004120`
- `0x180004514`
- `0x180016684`
- `0x180018028`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800166bd`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800166bd`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180016739`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180016739`

## pseudocode

```c
struct Plan9TraceLoggingProvider *Plan9TraceLoggingProvider::Instance(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  LPVOID Context; // [rsp+20h] [rbp-28h] BYREF
  WINBOOL fPending; // [rsp+28h] [rbp-20h] BYREF

  Context = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`Plan9TraceLoggingProvider::Instance'::`2'::wrapper, 0, &fPending, &Context) && fPending )
  {
    qword_180041768 = 0;
    Context = &qword_180041760;
    qword_180041760 = &Plan9TraceLoggingProvider::`vftable';
    byte_180041770 = 0;
    dword_180041774 = 0;
    qword_180041778 = (struct _tlgProvider_t *)&`Plan9TraceLoggingProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_95a3cf63ac82187ad0b2a516998b5285_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180041760, qword_180041778, v0);
    InitOnceComplete(&`Plan9TraceLoggingProvider::Instance'::`2'::wrapper, 0, &qword_180041760);
  }
  return (struct Plan9TraceLoggingProvider *)Context;
}

```

## disassembly

```asm
0x180016684  push    rbx
0x180016686  sub     rsp, 40h
0x18001668a  mov     rax, cs:__security_cookie
0x180016691  xor     rax, rsp
0x180016694  mov     [rsp+48h+var_18], rax
0x180016699  lea     r9, [rsp+48h+Context]; lpContext
0x18001669e  mov     [rsp+48h+Context], 0
0x1800166a7  lea     r8, [rsp+48h+fPending]; fPending
0x1800166ac  mov     [rsp+48h+fPending], 0
0x1800166b4  xor     edx, edx; dwFlags
0x1800166b6  lea     rcx, ?wrapper@?1??Instance@Plan9TraceLoggingProvider@@KAPEAV2@XZ@4V?$static_lazy@VPlan9TraceLoggingProvider@@@details@wil@@A; lpInitOnce
0x1800166bd  call    cs:__imp_InitOnceBeginInitialize
0x1800166c3  test    eax, eax
0x1800166c5  jz      short loc_18001673F
0x1800166c7  cmp     [rsp+48h+fPending], 0
0x1800166cc  jz      short loc_18001673F
0x1800166ce  lea     rbx, qword_180041760
0x1800166d5  mov     cs:qword_180041768, 0
0x1800166e0  lea     rax, ??_7Plan9TraceLoggingProvider@@6B@; const Plan9TraceLoggingProvider::`vftable'
0x1800166e7  mov     [rsp+48h+Context], rbx
0x1800166ec  mov     cs:qword_180041760, rax
0x1800166f3  mov     cs:byte_180041770, 0
0x1800166fa  mov     cs:dword_180041774, 0
0x180016704  lea     rax, ?__hInner@?1???0StaticHandle@Plan9TraceLoggingProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `Plan9TraceLoggingProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18001670b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_95a3cf63ac82187ad0b2a516998b5285_@@CA@XZ; void (__cdecl *)()
0x180016712  mov     cs:qword_180041778, rax
0x180016719  call    atexit
0x18001671e  mov     rdx, cs:qword_180041778; struct _tlgProvider_t *
0x180016725  mov     rcx, rbx; this
0x180016728  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18001672d  mov     r8, rbx; lpContext
0x180016730  lea     rcx, ?wrapper@?1??Instance@Plan9TraceLoggingProvider@@KAPEAV2@XZ@4V?$static_lazy@VPlan9TraceLoggingProvider@@@details@wil@@A; lpInitOnce
0x180016737  xor     edx, edx; dwFlags
0x180016739  call    cs:__imp_InitOnceComplete
0x18001673f  mov     rax, [rsp+48h+Context]
0x180016744  mov     rcx, [rsp+48h+var_18]
0x180016749  xor     rcx, rsp; StackCookie
0x18001674c  call    __security_check_cookie
0x180016751  add     rsp, 40h
0x180016755  pop     rbx
0x180016756  retn
```
