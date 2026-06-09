# SplWow64Logging::Instance(void)

- ea: `0x140004d0c`
- end: `0x140004dc1`
- name: `?Instance@SplWow64Logging@@KAPEAV1@XZ`
- size: `181`
- prototype: `struct SplWow64Logging *(void)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140004020`
- `0x1400072d0`
- `0x1400085d8`
- `0x1400086e0`

## callees

- `0x140002154`
- `0x140004d0c`
- `0x14000557c`

## import_xrefs

- `KERNEL32!InitOnceBeginInitialize` at `0x140004d34`
- `KERNEL32!InitOnceBeginInitialize` at `0x140004d34`
- `KERNEL32!InitOnceComplete` at `0x140004db0`
- `KERNEL32!InitOnceComplete` at `0x140004db0`

## pseudocode

```c
struct SplWow64Logging *SplWow64Logging::Instance(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  LPVOID v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(&`SplWow64Logging::Instance'::`2'::wrapper, 0, &v2, &v3) && v2 )
  {
    qword_140021700 = 0;
    v3 = &qword_1400216F8;
    qword_1400216F8 = &SplWow64Logging::`vftable';
    byte_140021708 = 0;
    dword_14002170C = 0;
    qword_140021710 = (struct _tlgProvider_t *)&`SplWow64Logging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_eeb5f34cb7207931b988a71301131333_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_1400216F8, qword_140021710, v0);
    InitOnceComplete(&`SplWow64Logging::Instance'::`2'::wrapper, 0, &qword_1400216F8);
  }
  return (struct SplWow64Logging *)v3;
}

```

## disassembly

```asm
0x140004d0c  mov     rax, rsp
0x140004d0f  push    rbx
0x140004d10  sub     rsp, 20h
0x140004d14  lea     r9, [rax+10h]; lpContext
0x140004d18  mov     qword ptr [rax+10h], 0
0x140004d20  lea     r8, [rax+8]; fPending
0x140004d24  mov     dword ptr [rax+8], 0
0x140004d2b  xor     edx, edx; dwFlags
0x140004d2d  lea     rcx, ?wrapper@?1??Instance@SplWow64Logging@@KAPEAV2@XZ@4V?$static_lazy@VSplWow64Logging@@@details@wil@@A; lpInitOnce
0x140004d34  call    cs:__imp_InitOnceBeginInitialize
0x140004d3a  test    eax, eax
0x140004d3c  jz      short loc_140004DB6
0x140004d3e  cmp     [rsp+28h+arg_0], 0
0x140004d43  jz      short loc_140004DB6
0x140004d45  lea     rbx, qword_1400216F8
0x140004d4c  mov     cs:qword_140021700, 0
0x140004d57  lea     rax, ??_7SplWow64Logging@@6B@; const SplWow64Logging::`vftable'
0x140004d5e  mov     [rsp+28h+arg_8], rbx
0x140004d63  mov     cs:qword_1400216F8, rax
0x140004d6a  mov     cs:byte_140021708, 0
0x140004d71  mov     cs:dword_14002170C, 0
0x140004d7b  lea     rax, ?__hInner@?1???0StaticHandle@SplWow64Logging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `SplWow64Logging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x140004d82  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_eeb5f34cb7207931b988a71301131333_@@CA@XZ; void (__cdecl *)()
0x140004d89  mov     cs:qword_140021710, rax
0x140004d90  call    atexit
0x140004d95  mov     rdx, cs:qword_140021710; struct _tlgProvider_t *
0x140004d9c  mov     rcx, rbx; this
0x140004d9f  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x140004da4  mov     r8, rbx; lpContext
0x140004da7  lea     rcx, ?wrapper@?1??Instance@SplWow64Logging@@KAPEAV2@XZ@4V?$static_lazy@VSplWow64Logging@@@details@wil@@A; lpInitOnce
0x140004dae  xor     edx, edx; dwFlags
0x140004db0  call    cs:__imp_InitOnceComplete
0x140004db6  mov     rax, [rsp+28h+arg_8]
0x140004dbb  add     rsp, 20h
0x140004dbf  pop     rbx
0x140004dc0  retn
```
