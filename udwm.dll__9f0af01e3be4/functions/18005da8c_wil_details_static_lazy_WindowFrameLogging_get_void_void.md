# wil::details::static_lazy<WindowFrameLogging>::get(void (*)(void))

- ea: `0x18005da8c`
- end: `0x18005db4b`
- name: `?get@?$static_lazy@VWindowFrameLogging@@@details@wil@@QEAAPEAVWindowFrameLogging@@P6AXXZ@Z`
- size: `191`
- prototype: ``
- caller_count: `26`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180024edc`
- `0x18002526c`
- `0x180026f3c`
- `0x18007ba28`
- `0x18007bc80`
- `0x1800854c4`
- `0x1800855a4`
- `0x180085d7c`
- `0x180085e58`
- `0x180087fac`
- `0x1800a3504`
- `0x1800a35d4`
- `0x1800a3634`
- `0x1800a63b0`
- `0x1800a71f4`
- `0x1800a72f4`
- `0x1800a78d0`
- `0x1800a7b00`
- `0x1800a7d30`
- `0x1800a7f60`
- `0x1800bdbc4`
- `0x1800c0584`
- `0x1800c05cc`
- `0x1800c0614`
- `0x1800c065c`
- `0x1800cbc70`

## callees

- `0x18005da8c`
- `0x18005dc68`
- `0x1800954e0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18005db43`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18005db43`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18005dabc`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18005dabc`

## pseudocode

```c
LPVOID __fastcall wil::details::static_lazy<WindowFrameLogging>::get(__int64 a1, __int64 a2)
{
  void (*v3)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  LPVOID v4; // [rsp+30h] [rbp+8h] BYREF
  WINBOOL v5; // [rsp+38h] [rbp+10h] BYREF
  int v6; // [rsp+3Ch] [rbp+14h]

  v6 = HIDWORD(a2);
  v4 = 0;
  v5 = 0;
  if ( InitOnceBeginInitialize(&`WindowFrameLogging::Instance'::`2'::wrapper, 0, &v5, &v4) && v5 )
  {
    qword_180116328 = 0;
    v4 = &qword_180116320;
    qword_180116320 = &WindowFrameLogging::`vftable';
    byte_180116330 = 0;
    dword_180116334 = 0;
    qword_180116338 = (struct _tlgProvider_t *)&`WindowFrameLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(`WindowFrameLogging::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180116320, qword_180116338, v3);
    InitOnceComplete(&`WindowFrameLogging::Instance'::`2'::wrapper, 0, &qword_180116320);
  }
  return v4;
}

```

## disassembly

```asm
0x18005da8c  mov     rax, rsp
0x18005da8f  mov     [rax+10h], rdx
0x18005da93  mov     [rax+8], rcx
0x18005da97  push    rbx
0x18005da98  sub     rsp, 20h
0x18005da9c  lea     r9, [rax+8]; lpContext
0x18005daa0  mov     qword ptr [rax+8], 0
0x18005daa8  lea     r8, [rax+10h]; fPending
0x18005daac  mov     dword ptr [rax+10h], 0
0x18005dab3  xor     edx, edx; dwFlags
0x18005dab5  lea     rcx, ?wrapper@?1??Instance@WindowFrameLogging@@KAPEAV2@XZ@4V?$static_lazy@VWindowFrameLogging@@@details@wil@@A; lpInitOnce
0x18005dabc  call    cs:__imp_InitOnceBeginInitialize
0x18005dac2  test    eax, eax
0x18005dac4  jz      short loc_18005DACD
0x18005dac6  cmp     [rsp+28h+arg_8], 0
0x18005dacb  jnz     short loc_18005DAD8
0x18005dacd  mov     rax, [rsp+28h+arg_0]
0x18005dad2  add     rsp, 20h
0x18005dad6  pop     rbx
0x18005dad7  retn
0x18005dad8  lea     rbx, qword_180116320
0x18005dadf  mov     cs:qword_180116328, 0
0x18005daea  lea     rax, ??_7WindowFrameLogging@@6B@; const WindowFrameLogging::`vftable'
0x18005daf1  mov     [rsp+28h+arg_0], rbx
0x18005daf6  mov     cs:qword_180116320, rax
0x18005dafd  mov     cs:byte_180116330, 0
0x18005db04  mov     cs:dword_180116334, 0
0x18005db0e  lea     rax, ?__hInner@?1???0StaticHandle@WindowFrameLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `WindowFrameLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18005db15  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@WindowFrameLogging@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x18005db1c  mov     cs:qword_180116338, rax
0x18005db23  call    atexit
0x18005db28  mov     rdx, cs:qword_180116338; struct _tlgProvider_t *
0x18005db2f  mov     rcx, rbx; this
0x18005db32  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18005db37  mov     r8, rbx; lpContext
0x18005db3a  lea     rcx, ?wrapper@?1??Instance@WindowFrameLogging@@KAPEAV2@XZ@4V?$static_lazy@VWindowFrameLogging@@@details@wil@@A; lpInitOnce
0x18005db41  xor     edx, edx; dwFlags
0x18005db43  call    cs:__imp_InitOnceComplete
0x18005db49  jmp     short loc_18005DACD
```
