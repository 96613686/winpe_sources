# PerfLibLogging::Provider(void)

- ea: `0x1400149d0`
- end: `0x140014a89`
- name: `?Provider@PerfLibLogging@@SAPEBU_tlgProvider_t@@XZ`
- size: `185`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400148f8`
- `0x140014c34`

## callees

- `0x140002154`
- `0x14000557c`
- `0x1400149d0`

## import_xrefs

- `KERNEL32!InitOnceBeginInitialize` at `0x1400149f8`
- `KERNEL32!InitOnceBeginInitialize` at `0x1400149f8`
- `KERNEL32!InitOnceComplete` at `0x140014a74`
- `KERNEL32!InitOnceComplete` at `0x140014a74`

## pseudocode

```c
const struct _tlgProvider_t *PerfLibLogging::Provider(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  _QWORD *v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(&`PerfLibLogging::Instance'::`2'::wrapper, 0, &v2, (LPVOID *)&v3) && v2 )
  {
    qword_140021940 = 0;
    v3 = &qword_140021938;
    qword_140021938 = &PerfLibLogging::`vftable';
    byte_140021948 = 0;
    dword_14002194C = 0;
    qword_140021950 = (struct _tlgProvider_t *)&`PerfLibLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_413cbca4d6bb2bbe5e98eab3b821cc31_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_140021938, qword_140021950, v0);
    InitOnceComplete(&`PerfLibLogging::Instance'::`2'::wrapper, 0, &qword_140021938);
  }
  return (const struct _tlgProvider_t *)v3[1];
}

```

## disassembly

```asm
0x1400149d0  mov     rax, rsp
0x1400149d3  push    rbx
0x1400149d4  sub     rsp, 20h
0x1400149d8  lea     r9, [rax+10h]; lpContext
0x1400149dc  mov     qword ptr [rax+10h], 0
0x1400149e4  lea     r8, [rax+8]; fPending
0x1400149e8  mov     dword ptr [rax+8], 0
0x1400149ef  xor     edx, edx; dwFlags
0x1400149f1  lea     rcx, ?wrapper@?1??Instance@PerfLibLogging@@KAPEAV2@XZ@4V?$static_lazy@VPerfLibLogging@@@details@wil@@A; lpInitOnce
0x1400149f8  call    cs:__imp_InitOnceBeginInitialize
0x1400149fe  test    eax, eax
0x140014a00  jz      short loc_140014A7A
0x140014a02  cmp     [rsp+28h+arg_0], 0
0x140014a07  jz      short loc_140014A7A
0x140014a09  lea     rbx, qword_140021938
0x140014a10  mov     cs:qword_140021940, 0
0x140014a1b  lea     rax, ??_7PerfLibLogging@@6B@; const PerfLibLogging::`vftable'
0x140014a22  mov     [rsp+28h+arg_8], rbx
0x140014a27  mov     cs:qword_140021938, rax
0x140014a2e  mov     cs:byte_140021948, 0
0x140014a35  mov     cs:dword_14002194C, 0
0x140014a3f  lea     rax, ?__hInner@?1???0StaticHandle@PerfLibLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `PerfLibLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x140014a46  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_413cbca4d6bb2bbe5e98eab3b821cc31_@@CA@XZ; void (__cdecl *)()
0x140014a4d  mov     cs:qword_140021950, rax
0x140014a54  call    atexit
0x140014a59  mov     rdx, cs:qword_140021950; struct _tlgProvider_t *
0x140014a60  mov     rcx, rbx; this
0x140014a63  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x140014a68  mov     r8, rbx; lpContext
0x140014a6b  lea     rcx, ?wrapper@?1??Instance@PerfLibLogging@@KAPEAV2@XZ@4V?$static_lazy@VPerfLibLogging@@@details@wil@@A; lpInitOnce
0x140014a72  xor     edx, edx; dwFlags
0x140014a74  call    cs:__imp_InitOnceComplete
0x140014a7a  mov     rax, [rsp+28h+arg_8]
0x140014a7f  mov     rax, [rax+8]
0x140014a83  add     rsp, 20h
0x140014a87  pop     rbx
0x140014a88  retn
```
