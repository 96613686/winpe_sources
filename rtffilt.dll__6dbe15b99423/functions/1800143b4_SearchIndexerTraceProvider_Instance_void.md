# SearchIndexerTraceProvider::Instance(void)

- ea: `0x1800143b4`
- end: `0x180014469`
- name: `?Instance@SearchIndexerTraceProvider@@KAPEAU1@XZ`
- size: `181`
- prototype: `struct SearchIndexerTraceProvider *(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011384`
- `0x180011420`

## callees

- `0x180002284`
- `0x1800143b4`
- `0x180014948`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800143dc`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800143dc`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180014458`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180014458`

## pseudocode

```c
struct SearchIndexerTraceProvider *SearchIndexerTraceProvider::Instance(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  BOOL v2; // [rsp+30h] [rbp+8h] BYREF
  LPVOID v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(&`SearchIndexerTraceProvider::Instance'::`2'::wrapper, 0, &v2, &v3) && v2 )
  {
    qword_1800239B0 = 0;
    v3 = &qword_1800239A8;
    qword_1800239A8 = &SearchIndexerTraceProvider::`vftable';
    byte_1800239B8 = 0;
    dword_1800239BC = 0;
    qword_1800239C0 = (struct _tlgProvider_t *)&`SearchIndexerTraceProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_8d28b2098336314bba74a672c814e573_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_1800239A8, qword_1800239C0, v0);
    InitOnceComplete(&`SearchIndexerTraceProvider::Instance'::`2'::wrapper, 0, &qword_1800239A8);
  }
  return (struct SearchIndexerTraceProvider *)v3;
}

```

## disassembly

```asm
0x1800143b4  mov     rax, rsp
0x1800143b7  push    rbx
0x1800143b8  sub     rsp, 20h
0x1800143bc  lea     r9, [rax+10h]; lpContext
0x1800143c0  mov     qword ptr [rax+10h], 0
0x1800143c8  lea     r8, [rax+8]; fPending
0x1800143cc  mov     dword ptr [rax+8], 0
0x1800143d3  xor     edx, edx; dwFlags
0x1800143d5  lea     rcx, ?wrapper@?1??Instance@SearchIndexerTraceProvider@@KAPEAU2@XZ@4V?$static_lazy@USearchIndexerTraceProvider@@@details@wil@@A; lpInitOnce
0x1800143dc  call    cs:__imp_InitOnceBeginInitialize
0x1800143e2  test    eax, eax
0x1800143e4  jz      short loc_18001445E
0x1800143e6  cmp     [rsp+28h+arg_0], 0
0x1800143eb  jz      short loc_18001445E
0x1800143ed  lea     rbx, qword_1800239A8
0x1800143f4  mov     cs:qword_1800239B0, 0
0x1800143ff  lea     rax, ??_7SearchIndexerTraceProvider@@6B@; const SearchIndexerTraceProvider::`vftable'
0x180014406  mov     [rsp+28h+arg_8], rbx
0x18001440b  mov     cs:qword_1800239A8, rax
0x180014412  mov     cs:byte_1800239B8, 0
0x180014419  mov     cs:dword_1800239BC, 0
0x180014423  lea     rax, ?__hInner@?1???0StaticHandle@SearchIndexerTraceProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `SearchIndexerTraceProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18001442a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_8d28b2098336314bba74a672c814e573_@@CA@XZ; void (__cdecl *)()
0x180014431  mov     cs:qword_1800239C0, rax
0x180014438  call    atexit
0x18001443d  mov     rdx, cs:qword_1800239C0; struct _tlgProvider_t *
0x180014444  mov     rcx, rbx; this
0x180014447  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18001444c  mov     r8, rbx; lpContext
0x18001444f  lea     rcx, ?wrapper@?1??Instance@SearchIndexerTraceProvider@@KAPEAU2@XZ@4V?$static_lazy@USearchIndexerTraceProvider@@@details@wil@@A; lpInitOnce
0x180014456  xor     edx, edx; dwFlags
0x180014458  call    cs:__imp_InitOnceComplete
0x18001445e  mov     rax, [rsp+28h+arg_8]
0x180014463  add     rsp, 20h
0x180014467  pop     rbx
0x180014468  retn
```
