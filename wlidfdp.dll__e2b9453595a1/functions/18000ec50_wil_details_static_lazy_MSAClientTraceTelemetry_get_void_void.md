# wil::details::static_lazy<MSAClientTraceTelemetry>::get(void (*)(void))

- ea: `0x18000ec50`
- end: `0x18000ed0a`
- name: `?get@?$static_lazy@VMSAClientTraceTelemetry@@@details@wil@@QEAAPEAVMSAClientTraceTelemetry@@P6AXXZ@Z`
- size: `186`
- prototype: `__int64 *__fastcall(__int64, void (__cdecl *)())`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000cea8`

## callees

- `0x180002bd8`
- `0x18000c868`
- `0x18000ec50`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000ec86`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000ec86`

## pseudocode

```c
__int64 *__fastcall wil::details::static_lazy<MSAClientTraceTelemetry>::get(__int64 a1, void (__cdecl *a2)())
{
  union _RTL_RUN_ONCE *v4; // [rsp+20h] [rbp-18h] BYREF
  int v5; // [rsp+28h] [rbp-10h]
  BOOL v6; // [rsp+40h] [rbp+8h] BYREF
  int v7; // [rsp+44h] [rbp+Ch]
  __int64 *v8; // [rsp+50h] [rbp+18h] BYREF

  v7 = HIDWORD(a1);
  v8 = 0;
  v6 = 0;
  if ( InitOnceBeginInitialize(&`MSAClientTraceTelemetry::Instance'::`2'::wrapper, 0, &v6, (LPVOID *)&v8) && v6 )
  {
    v4 = &`MSAClientTraceTelemetry::Instance'::`2'::wrapper;
    v8 = &qword_180020A20;
    qword_180020A20 = (__int64)&MSAClientTraceTelemetry::`vftable';
    qword_180020A28 = 0;
    byte_180020A30 = 0;
    dword_180020A34 = 0;
    qword_180020A38 = (__int64)&`MSAClientTraceTelemetry::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(a2);
    v5 = 0;
    wil::details::static_lazy<MSAClientTraceTelemetry>::Completer::~Completer(&v4);
  }
  return v8;
}

```

## disassembly

```asm
0x18000ec50  mov     rax, rsp
0x18000ec53  mov     [rax+10h], rbx
0x18000ec57  mov     [rax+8], rcx
0x18000ec5b  push    rsi
0x18000ec5c  sub     rsp, 30h
0x18000ec60  mov     rbx, rdx
0x18000ec63  mov     qword ptr [rax+18h], 0
0x18000ec6b  lea     rsi, ?wrapper@?1??Instance@MSAClientTraceTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VMSAClientTraceTelemetry@@@details@wil@@A; wil::details::static_lazy<MSAClientTraceTelemetry> `MSAClientTraceTelemetry::Instance(void)'::`2'::wrapper
0x18000ec72  mov     dword ptr [rax+8], 0
0x18000ec79  mov     rcx, rsi; lpInitOnce
0x18000ec7c  lea     r9, [rax+18h]; lpContext
0x18000ec80  lea     r8, [rax+8]; fPending
0x18000ec84  xor     edx, edx; dwFlags
0x18000ec86  call    cs:__imp_InitOnceBeginInitialize
0x18000ec8c  test    eax, eax
0x18000ec8e  jz      short loc_18000ECFA
0x18000ec90  cmp     [rsp+38h+arg_0], 0
0x18000ec95  jz      short loc_18000ECFA
0x18000ec97  lea     rax, qword_180020A20
0x18000ec9e  mov     [rsp+38h+var_18], rsi
0x18000eca3  mov     [rsp+38h+arg_10], rax
0x18000eca8  lea     rax, ??_7MSAClientTraceTelemetry@@6B@; const MSAClientTraceTelemetry::`vftable'
0x18000ecaf  mov     cs:qword_180020A20, rax
0x18000ecb6  mov     cs:qword_180020A28, 0
0x18000ecc1  mov     cs:byte_180020A30, 0
0x18000ecc8  mov     cs:dword_180020A34, 0
0x18000ecd2  lea     rax, ?__hInner@?1???0StaticHandle@MSAClientTraceTelemetry@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `MSAClientTraceTelemetry::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000ecd9  mov     rcx, rbx; void (__cdecl *)()
0x18000ecdc  mov     cs:qword_180020A38, rax
0x18000ece3  call    atexit
0x18000ece8  lea     rcx, [rsp+38h+var_18]
0x18000eced  mov     [rsp+38h+var_10], 0
0x18000ecf5  call    ??1Completer@?$static_lazy@VMSAClientTraceTelemetry@@@details@wil@@QEAA@XZ; wil::details::static_lazy<MSAClientTraceTelemetry>::Completer::~Completer(void)
0x18000ecfa  mov     rax, [rsp+38h+arg_10]
0x18000ecff  mov     rbx, [rsp+38h+arg_8]
0x18000ed04  add     rsp, 30h
0x18000ed08  pop     rsi
0x18000ed09  retn
```
