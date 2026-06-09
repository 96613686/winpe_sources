# VmWorkerTraceLoggingProvider::Instance(void)

- ea: `0x180025ebc`
- end: `0x180025f8f`
- name: `?Instance@VmWorkerTraceLoggingProvider@@KAPEAV1@XZ`
- size: `211`
- prototype: `struct VmWorkerTraceLoggingProvider *(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800258a0`
- `0x180028af8`

## callees

- `0x180004120`
- `0x180004514`
- `0x180018028`
- `0x180025ebc`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180025ef5`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180025ef5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180025f71`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180025f71`

## pseudocode

```c
struct VmWorkerTraceLoggingProvider *VmWorkerTraceLoggingProvider::Instance(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  LPVOID Context; // [rsp+20h] [rbp-28h] BYREF
  WINBOOL fPending; // [rsp+28h] [rbp-20h] BYREF

  Context = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`VmWorkerTraceLoggingProvider::Instance'::`2'::wrapper, 0, &fPending, &Context)
    && fPending )
  {
    qword_1800417A0 = 0;
    Context = &qword_180041798;
    qword_180041798 = &Plan9TraceLoggingProvider::`vftable';
    byte_1800417A8 = 0;
    dword_1800417AC = 0;
    qword_1800417B0 = (struct _tlgProvider_t *)&`VmWorkerTraceLoggingProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_77a473238827774f0a0863e69ac9237f_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180041798, qword_1800417B0, v0);
    InitOnceComplete(&`VmWorkerTraceLoggingProvider::Instance'::`2'::wrapper, 0, &qword_180041798);
  }
  return (struct VmWorkerTraceLoggingProvider *)Context;
}

```

## disassembly

```asm
0x180025ebc  push    rbx
0x180025ebe  sub     rsp, 40h
0x180025ec2  mov     rax, cs:__security_cookie
0x180025ec9  xor     rax, rsp
0x180025ecc  mov     [rsp+48h+var_18], rax
0x180025ed1  lea     r9, [rsp+48h+Context]; lpContext
0x180025ed6  mov     [rsp+48h+Context], 0
0x180025edf  lea     r8, [rsp+48h+fPending]; fPending
0x180025ee4  mov     [rsp+48h+fPending], 0
0x180025eec  xor     edx, edx; dwFlags
0x180025eee  lea     rcx, ?wrapper@?1??Instance@VmWorkerTraceLoggingProvider@@KAPEAV2@XZ@4V?$static_lazy@VVmWorkerTraceLoggingProvider@@@details@wil@@A; lpInitOnce
0x180025ef5  call    cs:__imp_InitOnceBeginInitialize
0x180025efb  test    eax, eax
0x180025efd  jz      short loc_180025F77
0x180025eff  cmp     [rsp+48h+fPending], 0
0x180025f04  jz      short loc_180025F77
0x180025f06  lea     rbx, qword_180041798
0x180025f0d  mov     cs:qword_1800417A0, 0
0x180025f18  lea     rax, ??_7Plan9TraceLoggingProvider@@6B@; const Plan9TraceLoggingProvider::`vftable'
0x180025f1f  mov     [rsp+48h+Context], rbx
0x180025f24  mov     cs:qword_180041798, rax
0x180025f2b  mov     cs:byte_1800417A8, 0
0x180025f32  mov     cs:dword_1800417AC, 0
0x180025f3c  lea     rax, ?__hInner@?1???0StaticHandle@VmWorkerTraceLoggingProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `VmWorkerTraceLoggingProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180025f43  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_77a473238827774f0a0863e69ac9237f_@@CA@XZ; void (__cdecl *)()
0x180025f4a  mov     cs:qword_1800417B0, rax
0x180025f51  call    atexit
0x180025f56  mov     rdx, cs:qword_1800417B0; struct _tlgProvider_t *
0x180025f5d  mov     rcx, rbx; this
0x180025f60  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180025f65  mov     r8, rbx; lpContext
0x180025f68  lea     rcx, ?wrapper@?1??Instance@VmWorkerTraceLoggingProvider@@KAPEAV2@XZ@4V?$static_lazy@VVmWorkerTraceLoggingProvider@@@details@wil@@A; lpInitOnce
0x180025f6f  xor     edx, edx; dwFlags
0x180025f71  call    cs:__imp_InitOnceComplete
0x180025f77  mov     rax, [rsp+48h+Context]
0x180025f7c  mov     rcx, [rsp+48h+var_18]
0x180025f81  xor     rcx, rsp; StackCookie
0x180025f84  call    __security_check_cookie
0x180025f89  add     rsp, 40h
0x180025f8d  pop     rbx
0x180025f8e  retn
```
