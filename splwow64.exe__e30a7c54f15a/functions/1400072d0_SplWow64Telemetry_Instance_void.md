# SplWow64Telemetry::Instance(void)

- ea: `0x1400072d0`
- end: `0x1400073a4`
- name: `?Instance@SplWow64Telemetry@@KAPEAV1@XZ`
- size: `212`
- prototype: `struct SplWow64Telemetry *(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400085d8`
- `0x1400086e0`

## callees

- `0x140002154`
- `0x140004d0c`
- `0x1400072d0`
- `0x140016010`

## import_xrefs

- `KERNEL32!InitOnceBeginInitialize` at `0x1400072f8`
- `KERNEL32!InitOnceBeginInitialize` at `0x1400072f8`
- `KERNEL32!InitOnceComplete` at `0x140007393`
- `KERNEL32!InitOnceComplete` at `0x140007393`

## pseudocode

```c
struct SplWow64Telemetry *SplWow64Telemetry::Instance(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(&`SplWow64Telemetry::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2) && v1 )
  {
    qword_140021760 = 0;
    qword_140021758 = (__int64)&wil::TraceLoggingProvider::`vftable';
    v2 = &qword_140021758;
    byte_140021768 = 0;
    dword_14002176C = 0;
    atexit(_lambda_ed480c77b145ef751110012d0d6d46cf_::_lambda_invoker_cdecl_);
    qword_140021760 = *((_QWORD *)SplWow64Logging::Instance() + 1);
    byte_140021768 = 0;
    dword_14002176C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_140021758 + 8))(&qword_140021758);
    InitOnceComplete(&`SplWow64Telemetry::Instance'::`2'::wrapper, 0, &qword_140021758);
  }
  return (struct SplWow64Telemetry *)v2;
}

```

## disassembly

```asm
0x1400072d0  mov     rax, rsp
0x1400072d3  push    rbx
0x1400072d4  sub     rsp, 20h
0x1400072d8  lea     r9, [rax+10h]; lpContext
0x1400072dc  mov     qword ptr [rax+10h], 0
0x1400072e4  lea     r8, [rax+8]; fPending
0x1400072e8  mov     dword ptr [rax+8], 0
0x1400072ef  xor     edx, edx; dwFlags
0x1400072f1  lea     rcx, ?wrapper@?1??Instance@SplWow64Telemetry@@KAPEAV2@XZ@4V?$static_lazy@VSplWow64Telemetry@@@details@wil@@A; lpInitOnce
0x1400072f8  call    cs:__imp_InitOnceBeginInitialize
0x1400072fe  test    eax, eax
0x140007300  jz      loc_140007399
0x140007306  cmp     [rsp+28h+arg_0], 0
0x14000730b  jz      loc_140007399
0x140007311  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x140007318  mov     cs:qword_140021760, 0
0x140007323  lea     rbx, qword_140021758
0x14000732a  mov     cs:qword_140021758, rax
0x140007331  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_ed480c77b145ef751110012d0d6d46cf_@@CA@XZ; void (__cdecl *)()
0x140007338  mov     [rsp+28h+arg_8], rbx
0x14000733d  mov     cs:byte_140021768, 0
0x140007344  mov     cs:dword_14002176C, 0
0x14000734e  call    atexit
0x140007353  call    ?Instance@SplWow64Logging@@KAPEAV1@XZ; SplWow64Logging::Instance(void)
0x140007358  mov     rcx, rbx
0x14000735b  mov     rdx, [rax+8]
0x14000735f  mov     rax, cs:qword_140021758
0x140007366  mov     cs:qword_140021760, rdx
0x14000736d  mov     cs:byte_140021768, 0
0x140007374  mov     cs:dword_14002176C, 1
0x14000737e  mov     rax, [rax+8]
0x140007382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007387  mov     r8, rbx; lpContext
0x14000738a  lea     rcx, ?wrapper@?1??Instance@SplWow64Telemetry@@KAPEAV2@XZ@4V?$static_lazy@VSplWow64Telemetry@@@details@wil@@A; lpInitOnce
0x140007391  xor     edx, edx; dwFlags
0x140007393  call    cs:__imp_InitOnceComplete
0x140007399  mov     rax, [rsp+28h+arg_8]
0x14000739e  add     rsp, 20h
0x1400073a2  pop     rbx
0x1400073a3  retn
```
