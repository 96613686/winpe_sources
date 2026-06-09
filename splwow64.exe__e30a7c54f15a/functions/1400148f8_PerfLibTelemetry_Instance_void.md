# PerfLibTelemetry::Instance(void)

- ea: `0x1400148f8`
- end: `0x1400149c8`
- name: `?Instance@PerfLibTelemetry@@KAPEAV1@XZ`
- size: `208`
- prototype: `struct PerfLibTelemetry *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140014c34`

## callees

- `0x140002154`
- `0x1400148f8`
- `0x1400149d0`
- `0x140016010`

## import_xrefs

- `KERNEL32!InitOnceBeginInitialize` at `0x140014920`
- `KERNEL32!InitOnceBeginInitialize` at `0x140014920`
- `KERNEL32!InitOnceComplete` at `0x1400149b7`
- `KERNEL32!InitOnceComplete` at `0x1400149b7`

## pseudocode

```c
struct PerfLibTelemetry *PerfLibTelemetry::Instance(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(&`PerfLibTelemetry::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2) && v1 )
  {
    qword_140021968 = 0;
    qword_140021960 = (__int64)&PerfLibLogging::`vftable';
    v2 = &qword_140021960;
    byte_140021970 = 0;
    dword_140021974 = 0;
    atexit(_lambda_afb3aedd42a937a6b0239593c828df1f_::_lambda_invoker_cdecl_);
    qword_140021968 = (__int64)PerfLibLogging::Provider();
    byte_140021970 = 0;
    dword_140021974 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_140021960 + 8))(&qword_140021960);
    InitOnceComplete(&`PerfLibTelemetry::Instance'::`2'::wrapper, 0, &qword_140021960);
  }
  return (struct PerfLibTelemetry *)v2;
}

```

## disassembly

```asm
0x1400148f8  mov     rax, rsp
0x1400148fb  push    rbx
0x1400148fc  sub     rsp, 20h
0x140014900  lea     r9, [rax+10h]; lpContext
0x140014904  mov     qword ptr [rax+10h], 0
0x14001490c  lea     r8, [rax+8]; fPending
0x140014910  mov     dword ptr [rax+8], 0
0x140014917  xor     edx, edx; dwFlags
0x140014919  lea     rcx, ?wrapper@?1??Instance@PerfLibTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VPerfLibTelemetry@@@details@wil@@A; lpInitOnce
0x140014920  call    cs:__imp_InitOnceBeginInitialize
0x140014926  test    eax, eax
0x140014928  jz      loc_1400149BD
0x14001492e  cmp     [rsp+28h+arg_0], 0
0x140014933  jz      loc_1400149BD
0x140014939  lea     rax, ??_7PerfLibLogging@@6B@; const PerfLibLogging::`vftable'
0x140014940  mov     cs:qword_140021968, 0
0x14001494b  lea     rbx, qword_140021960
0x140014952  mov     cs:qword_140021960, rax
0x140014959  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_afb3aedd42a937a6b0239593c828df1f_@@CA@XZ; void (__cdecl *)()
0x140014960  mov     [rsp+28h+arg_8], rbx
0x140014965  mov     cs:byte_140021970, 0
0x14001496c  mov     cs:dword_140021974, 0
0x140014976  call    atexit
0x14001497b  call    ?Provider@PerfLibLogging@@SAPEBU_tlgProvider_t@@XZ; PerfLibLogging::Provider(void)
0x140014980  mov     cs:qword_140021968, rax
0x140014987  mov     rcx, rbx
0x14001498a  mov     rax, cs:qword_140021960
0x140014991  mov     cs:byte_140021970, 0
0x140014998  mov     cs:dword_140021974, 1
0x1400149a2  mov     rax, [rax+8]
0x1400149a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400149ab  mov     r8, rbx; lpContext
0x1400149ae  lea     rcx, ?wrapper@?1??Instance@PerfLibTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VPerfLibTelemetry@@@details@wil@@A; lpInitOnce
0x1400149b5  xor     edx, edx; dwFlags
0x1400149b7  call    cs:__imp_InitOnceComplete
0x1400149bd  mov     rax, [rsp+28h+arg_8]
0x1400149c2  add     rsp, 20h
0x1400149c6  pop     rbx
0x1400149c7  retn
```
