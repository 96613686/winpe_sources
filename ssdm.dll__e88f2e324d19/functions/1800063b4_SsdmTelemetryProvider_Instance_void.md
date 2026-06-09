# SsdmTelemetryProvider::Instance(void)

- ea: `0x1800063b4`
- end: `0x180006462`
- name: `?Instance@SsdmTelemetryProvider@@KAPEAV1@XZ`
- size: `174`
- prototype: `struct SsdmTelemetryProvider *(void)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005710`
- `0x18000a5fc`
- `0x18000a970`
- `0x18000b328`
- `0x18000b4d4`
- `0x18000b840`

## callees

- `0x18000274c`
- `0x180004b10`
- `0x1800063b4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800063df`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800063df`

## pseudocode

```c
struct SsdmTelemetryProvider *SsdmTelemetryProvider::Instance(void)
{
  union _RTL_RUN_ONCE *v1; // [rsp+20h] [rbp-18h] BYREF
  int v2; // [rsp+28h] [rbp-10h]
  BOOL v3; // [rsp+40h] [rbp+8h] BYREF
  __int64 *v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  v3 = 0;
  if ( InitOnceBeginInitialize(&`SsdmTelemetryProvider::Instance'::`2'::wrapper, 0, &v3, (LPVOID *)&v4) && v3 )
  {
    v1 = &`SsdmTelemetryProvider::Instance'::`2'::wrapper;
    v4 = &qword_18001F948;
    qword_18001F948 = (__int64)&SsdmTelemetryProvider::`vftable';
    qword_18001F950 = 0;
    byte_18001F958 = 0;
    dword_18001F95C = 0;
    qword_18001F960 = (__int64)&`SsdmTelemetryProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_eaa800c76b8bce0cd434ec66bb7526f7_::_lambda_invoker_cdecl_);
    v2 = 0;
    wil::details::static_lazy<SsdmTelemetryProvider>::Completer::~Completer(&v1);
  }
  return (struct SsdmTelemetryProvider *)v4;
}

```

## disassembly

```asm
0x1800063b4  mov     rax, rsp
0x1800063b7  push    rdi
0x1800063b8  sub     rsp, 30h
0x1800063bc  lea     rdi, ?wrapper@?1??Instance@SsdmTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VSsdmTelemetryProvider@@@details@wil@@A; wil::details::static_lazy<SsdmTelemetryProvider> `SsdmTelemetryProvider::Instance(void)'::`2'::wrapper
0x1800063c3  mov     qword ptr [rax+10h], 0
0x1800063cb  mov     rcx, rdi; lpInitOnce
0x1800063ce  mov     dword ptr [rax+8], 0
0x1800063d5  lea     r9, [rax+10h]; lpContext
0x1800063d9  xor     edx, edx; dwFlags
0x1800063db  lea     r8, [rax+8]; fPending
0x1800063df  call    cs:__imp_InitOnceBeginInitialize
0x1800063e5  test    eax, eax
0x1800063e7  jz      short loc_180006457
0x1800063e9  cmp     [rsp+38h+arg_0], 0
0x1800063ee  jz      short loc_180006457
0x1800063f0  lea     rax, qword_18001F948
0x1800063f7  mov     [rsp+38h+var_18], rdi
0x1800063fc  mov     [rsp+38h+arg_8], rax
0x180006401  lea     rax, ??_7SsdmTelemetryProvider@@6B@; const SsdmTelemetryProvider::`vftable'
0x180006408  mov     cs:qword_18001F948, rax
0x18000640f  mov     cs:qword_18001F950, 0
0x18000641a  mov     cs:byte_18001F958, 0
0x180006421  mov     cs:dword_18001F95C, 0
0x18000642b  lea     rax, ?__hInner@?1???0StaticHandle@SsdmTelemetryProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `SsdmTelemetryProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180006432  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_eaa800c76b8bce0cd434ec66bb7526f7_@@CA@XZ; void (__cdecl *)()
0x180006439  mov     cs:qword_18001F960, rax
0x180006440  call    atexit
0x180006445  lea     rcx, [rsp+38h+var_18]
0x18000644a  mov     [rsp+38h+var_10], 0
0x180006452  call    ??1Completer@?$static_lazy@VSsdmTelemetryProvider@@@details@wil@@QEAA@XZ; wil::details::static_lazy<SsdmTelemetryProvider>::Completer::~Completer(void)
0x180006457  mov     rax, [rsp+38h+arg_8]
0x18000645c  add     rsp, 30h
0x180006460  pop     rdi
0x180006461  retn
```
