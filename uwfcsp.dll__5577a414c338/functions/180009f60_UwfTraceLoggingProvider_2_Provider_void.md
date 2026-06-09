# UwfTraceLoggingProvider<2>::Provider(void)

- ea: `0x180009f60`
- end: `0x18000a012`
- name: `?Provider@?$UwfTraceLoggingProvider@$01@@SAPEBU_tlgProvider_t@@XZ`
- size: `178`
- prototype: `__int64()`
- caller_count: `10`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000745c`
- `0x180007788`
- `0x180007ccc`
- `0x180009890`
- `0x18000b61c`
- `0x18000b820`
- `0x18000c1ec`
- `0x18000c5b4`
- `0x18000c8d8`
- `0x18000cbfc`

## callees

- `0x180003b34`
- `0x180007ee8`
- `0x180009f60`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180009f8b`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180009f8b`

## pseudocode

```c
__int64 UwfTraceLoggingProvider<2>::Provider()
{
  union _RTL_RUN_ONCE *v1; // [rsp+20h] [rbp-18h] BYREF
  int v2; // [rsp+28h] [rbp-10h]
  WINBOOL v3; // [rsp+40h] [rbp+8h] BYREF
  __int64 *v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  v3 = 0;
  if ( InitOnceBeginInitialize(&`UwfTraceLoggingProvider<2>::Instance'::`2'::wrapper, 0, &v3, (LPVOID *)&v4) && v3 )
  {
    v1 = &`UwfTraceLoggingProvider<2>::Instance'::`2'::wrapper;
    v4 = &qword_180028570;
    qword_180028570 = (__int64)&UwfTraceLoggingProvider<2>::`vftable';
    qword_180028578 = 0;
    byte_180028580 = 0;
    dword_180028584 = 0;
    qword_180028588 = (__int64)&`UwfTraceLoggingProvider<2>::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_af9993d746f634a9cddf8dd6e326c847_::_lambda_invoker_cdecl_);
    v2 = 0;
    wil::details::static_lazy<UwfTraceLoggingProvider<2>>::Completer::~Completer(&v1);
  }
  return v4[1];
}

```

## disassembly

```asm
0x180009f60  mov     rax, rsp
0x180009f63  push    rdi
0x180009f64  sub     rsp, 30h
0x180009f68  lea     rdi, ?wrapper@?1??Instance@?$UwfTraceLoggingProvider@$01@@KAPEAV2@XZ@4V?$static_lazy@V?$UwfTraceLoggingProvider@$01@@@details@wil@@A; wil::details::static_lazy<UwfTraceLoggingProvider<2>> `UwfTraceLoggingProvider<2>::Instance(void)'::`2'::wrapper
0x180009f6f  mov     qword ptr [rax+10h], 0
0x180009f77  mov     rcx, rdi; lpInitOnce
0x180009f7a  mov     dword ptr [rax+8], 0
0x180009f81  lea     r9, [rax+10h]; lpContext
0x180009f85  xor     edx, edx; dwFlags
0x180009f87  lea     r8, [rax+8]; fPending
0x180009f8b  call    cs:__imp_InitOnceBeginInitialize
0x180009f91  test    eax, eax
0x180009f93  jz      short loc_18000A003
0x180009f95  cmp     [rsp+38h+arg_0], 0
0x180009f9a  jz      short loc_18000A003
0x180009f9c  lea     rax, qword_180028570
0x180009fa3  mov     [rsp+38h+var_18], rdi
0x180009fa8  mov     [rsp+38h+arg_8], rax
0x180009fad  lea     rax, ??_7?$UwfTraceLoggingProvider@$01@@6B@; const UwfTraceLoggingProvider<2>::`vftable'
0x180009fb4  mov     cs:qword_180028570, rax
0x180009fbb  mov     cs:qword_180028578, 0
0x180009fc6  mov     cs:byte_180028580, 0
0x180009fcd  mov     cs:dword_180028584, 0
0x180009fd7  lea     rax, ?__hInner@?1???0StaticHandle@?$UwfTraceLoggingProvider@$01@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `UwfTraceLoggingProvider<2>::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180009fde  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_af9993d746f634a9cddf8dd6e326c847_@@CA@XZ; void (__cdecl *)()
0x180009fe5  mov     cs:qword_180028588, rax
0x180009fec  call    atexit
0x180009ff1  lea     rcx, [rsp+38h+var_18]
0x180009ff6  mov     [rsp+38h+var_10], 0
0x180009ffe  call    ??1Completer@?$static_lazy@V?$UwfTraceLoggingProvider@$01@@@details@wil@@QEAA@XZ; wil::details::static_lazy<UwfTraceLoggingProvider<2>>::Completer::~Completer(void)
0x18000a003  mov     rax, [rsp+38h+arg_8]
0x18000a008  mov     rax, [rax+8]
0x18000a00c  add     rsp, 30h
0x18000a010  pop     rdi
0x18000a011  retn
```
