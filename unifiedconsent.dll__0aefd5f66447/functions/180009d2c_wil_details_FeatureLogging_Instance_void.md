# wil::details::FeatureLogging::Instance(void)

- ea: `0x180009d2c`
- end: `0x180009de1`
- name: `?Instance@FeatureLogging@details@wil@@KAPEAV123@XZ`
- size: `181`
- prototype: `struct wil::details::FeatureLogging *(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800075a0`

## callees

- `0x180002ce0`
- `0x180009d2c`
- `0x18000b8b8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180009dd0`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180009dd0`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180009d54`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180009d54`

## pseudocode

```c
struct wil::details::FeatureLogging *wil::details::FeatureLogging::Instance(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  LPVOID v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &v2, &v3) && v2 )
  {
    qword_18009CCF8 = 0;
    v3 = &qword_18009CCF0;
    qword_18009CCF0 = &wil::details::FeatureLogging::`vftable';
    byte_18009CD00 = 0;
    dword_18009CD04 = 0;
    qword_18009CD08 = (struct _tlgProvider_t *)&`wil::details::FeatureLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_18009CCF0, qword_18009CD08, v0);
    InitOnceComplete(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &qword_18009CCF0);
  }
  return (struct wil::details::FeatureLogging *)v3;
}

```

## disassembly

```asm
0x180009d2c  mov     rax, rsp
0x180009d2f  push    rbx
0x180009d30  sub     rsp, 20h
0x180009d34  lea     r9, [rax+10h]; lpContext
0x180009d38  mov     qword ptr [rax+10h], 0
0x180009d40  lea     r8, [rax+8]; fPending
0x180009d44  mov     dword ptr [rax+8], 0
0x180009d4b  xor     edx, edx; dwFlags
0x180009d4d  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x180009d54  call    cs:__imp_InitOnceBeginInitialize
0x180009d5a  test    eax, eax
0x180009d5c  jz      short loc_180009DD6
0x180009d5e  cmp     [rsp+28h+arg_0], 0
0x180009d63  jz      short loc_180009DD6
0x180009d65  lea     rbx, qword_18009CCF0
0x180009d6c  mov     cs:qword_18009CCF8, 0
0x180009d77  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x180009d7e  mov     [rsp+28h+arg_8], rbx
0x180009d83  mov     cs:qword_18009CCF0, rax
0x180009d8a  mov     cs:byte_18009CD00, 0
0x180009d91  mov     cs:dword_18009CD04, 0
0x180009d9b  lea     rax, ?__hInner@?1???0StaticHandle@FeatureLogging@details@wil@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `wil::details::FeatureLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180009da2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_@@CA@XZ; void (__cdecl *)()
0x180009da9  mov     cs:qword_18009CD08, rax
0x180009db0  call    atexit
0x180009db5  mov     rdx, cs:qword_18009CD08; struct _tlgProvider_t *
0x180009dbc  mov     rcx, rbx; this
0x180009dbf  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180009dc4  mov     r8, rbx; lpContext
0x180009dc7  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x180009dce  xor     edx, edx; dwFlags
0x180009dd0  call    cs:__imp_InitOnceComplete
0x180009dd6  mov     rax, [rsp+28h+arg_8]
0x180009ddb  add     rsp, 20h
0x180009ddf  pop     rbx
0x180009de0  retn
```
