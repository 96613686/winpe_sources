# Windows::Telemetry::Base::Instance(void)

- ea: `0x180041c1c`
- end: `0x180041cd1`
- name: `?Instance@Base@Telemetry@Windows@@KAPEAV123@XZ`
- size: `181`
- prototype: `struct Windows::Telemetry::Base *(void)`
- caller_count: `26`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800413a8`
- `0x180041dc0`
- `0x1800437bc`
- `0x180043964`
- `0x180043d84`
- `0x1800440d0`
- `0x1800445d4`
- `0x18004f37c`
- `0x18004f46c`
- `0x180050970`
- `0x180050b70`
- `0x180051be8`
- `0x180051dac`
- `0x180052080`
- `0x180052310`
- `0x180052590`
- `0x1800526b0`
- `0x1800527f8`
- `0x1800529c0`
- `0x180052b8c`
- `0x180052d84`
- `0x180052ed0`
- `0x180053160`
- `0x180053530`
- `0x1800535c0`
- `0x180053b10`

## callees

- `0x180007da0`
- `0x18001b4fc`
- `0x180041c1c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180041c44`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180041c44`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180041cc0`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180041cc0`

## pseudocode

```c
struct Windows::Telemetry::Base *Windows::Telemetry::Base::Instance(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  LPVOID v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( __std_init_once_begin_initialize(&`Windows::Telemetry::Base::Instance'::`2'::wrapper, 0, &v2, &v3) && v2 )
  {
    qword_180095D48 = 0;
    v3 = &qword_180095D40;
    qword_180095D40 = &Windows::Telemetry::Base::`vftable';
    byte_180095D50 = 0;
    dword_180095D54 = 0;
    qword_180095D58 = (struct _tlgProvider_t *)&`Windows::Telemetry::Base::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_b9af1bd91d689b17158227b7540bc621_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180095D40, qword_180095D58, v0);
    InitOnceComplete(&`Windows::Telemetry::Base::Instance'::`2'::wrapper, 0, &qword_180095D40);
  }
  return (struct Windows::Telemetry::Base *)v3;
}

```

## disassembly

```asm
0x180041c1c  mov     rax, rsp
0x180041c1f  push    rbx
0x180041c20  sub     rsp, 20h
0x180041c24  lea     r9, [rax+10h]; lpContext
0x180041c28  mov     qword ptr [rax+10h], 0
0x180041c30  lea     r8, [rax+8]; fPending
0x180041c34  mov     dword ptr [rax+8], 0
0x180041c3b  xor     edx, edx; dwFlags
0x180041c3d  lea     rcx, ?wrapper@?1??Instance@Base@Telemetry@Windows@@KAPEAV234@XZ@4V?$static_lazy@VBase@Telemetry@Windows@@@details@wil@@A; lpInitOnce
0x180041c44  call    cs:__imp___std_init_once_begin_initialize
0x180041c4a  test    eax, eax
0x180041c4c  jz      short loc_180041CC6
0x180041c4e  cmp     [rsp+28h+arg_0], 0
0x180041c53  jz      short loc_180041CC6
0x180041c55  lea     rbx, qword_180095D40
0x180041c5c  mov     cs:qword_180095D48, 0
0x180041c67  lea     rax, ??_7Base@Telemetry@Windows@@6B@; const Windows::Telemetry::Base::`vftable'
0x180041c6e  mov     [rsp+28h+arg_8], rbx
0x180041c73  mov     cs:qword_180095D40, rax
0x180041c7a  mov     cs:byte_180095D50, 0
0x180041c81  mov     cs:dword_180095D54, 0
0x180041c8b  lea     rax, ?__hInner@?1???0StaticHandle@Base@Telemetry@Windows@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `Windows::Telemetry::Base::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180041c92  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_b9af1bd91d689b17158227b7540bc621_@@CA@XZ; void (__cdecl *)()
0x180041c99  mov     cs:qword_180095D58, rax
0x180041ca0  call    atexit
0x180041ca5  mov     rdx, cs:qword_180095D58; struct _tlgProvider_t *
0x180041cac  mov     rcx, rbx; this
0x180041caf  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180041cb4  mov     r8, rbx; lpContext
0x180041cb7  lea     rcx, ?wrapper@?1??Instance@Base@Telemetry@Windows@@KAPEAV234@XZ@4V?$static_lazy@VBase@Telemetry@Windows@@@details@wil@@A; lpInitOnce
0x180041cbe  xor     edx, edx; dwFlags
0x180041cc0  call    cs:__imp_InitOnceComplete
0x180041cc6  mov     rax, [rsp+28h+arg_8]
0x180041ccb  add     rsp, 20h
0x180041ccf  pop     rbx
0x180041cd0  retn
```
