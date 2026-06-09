# uus::UndockedUpdateTelemetry::Provider(void)

- ea: `0x18000868c`
- end: `0x180008763`
- name: `?Provider@UndockedUpdateTelemetry@uus@@SAPEBU_tlgProvider_t@@XZ`
- size: `215`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `27`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800087f0`
- `0x180008c48`
- `0x180008da8`
- `0x180008e30`
- `0x180008f3c`
- `0x180008fc4`
- `0x180009180`
- `0x180009300`
- `0x1800094bc`
- `0x1800096d4`
- `0x18003b804`
- `0x18003babc`
- `0x18003bc5c`
- `0x18003beac`
- `0x18003c2c0`
- `0x18003c348`
- `0x18003c4e4`
- `0x18003c7f8`
- `0x18003c978`
- `0x18003cb54`
- `0x18003d5e0`
- `0x18003d720`
- `0x18003d7a8`
- `0x18003d8e4`
- `0x18003da28`
- `0x18003e548`
- `0x18003e64c`

## callees

- `0x180008520`
- `0x18000868c`
- `0x1800427d0`
- `0x180042ba4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180008741`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180008741`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800086c5`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800086c5`

## pseudocode

```c
const struct _tlgProvider_t *uus::UndockedUpdateTelemetry::Provider(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  LPVOID Context; // [rsp+20h] [rbp-28h] BYREF
  WINBOOL fPending; // [rsp+28h] [rbp-20h] BYREF

  Context = 0;
  fPending = 0;
  if ( __std_init_once_begin_initialize(&`uus::UndockedUpdateTelemetry::Instance'::`2'::wrapper, 0, &fPending, &Context)
    && fPending )
  {
    qword_180063510 = 0;
    Context = &qword_180063508;
    qword_180063508 = &uus::UUSTracing::`vftable';
    byte_180063518 = 0;
    dword_18006351C = 0;
    qword_180063520 = (struct _tlgProvider_t *)&`uus::UndockedUpdateTelemetry::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_6cf933dfbea90a966b650da22a1901f4_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180063508, qword_180063520, v0);
    InitOnceComplete(&`uus::UndockedUpdateTelemetry::Instance'::`2'::wrapper, 0, &qword_180063508);
  }
  return (const struct _tlgProvider_t *)*((_QWORD *)Context + 1);
}

```

## disassembly

```asm
0x18000868c  push    rbx
0x18000868e  sub     rsp, 40h
0x180008692  mov     rax, cs:__security_cookie
0x180008699  xor     rax, rsp
0x18000869c  mov     [rsp+48h+var_18], rax
0x1800086a1  lea     r9, [rsp+48h+Context]; lpContext
0x1800086a6  mov     [rsp+48h+Context], 0
0x1800086af  lea     r8, [rsp+48h+fPending]; fPending
0x1800086b4  mov     [rsp+48h+fPending], 0
0x1800086bc  xor     edx, edx; dwFlags
0x1800086be  lea     rcx, ?wrapper@?1??Instance@UndockedUpdateTelemetry@uus@@KAPEAV23@XZ@4V?$static_lazy@VUndockedUpdateTelemetry@uus@@@details@wil@@A; lpInitOnce
0x1800086c5  call    cs:__imp___std_init_once_begin_initialize
0x1800086cb  test    eax, eax
0x1800086cd  jz      short loc_180008747
0x1800086cf  cmp     [rsp+48h+fPending], 0
0x1800086d4  jz      short loc_180008747
0x1800086d6  lea     rbx, qword_180063508
0x1800086dd  mov     cs:qword_180063510, 0
0x1800086e8  lea     rax, ??_7UUSTracing@uus@@6B@; const uus::UUSTracing::`vftable'
0x1800086ef  mov     [rsp+48h+Context], rbx
0x1800086f4  mov     cs:qword_180063508, rax
0x1800086fb  mov     cs:byte_180063518, 0
0x180008702  mov     cs:dword_18006351C, 0
0x18000870c  lea     rax, ?__hInner@?1???0StaticHandle@UndockedUpdateTelemetry@uus@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `uus::UndockedUpdateTelemetry::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180008713  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_6cf933dfbea90a966b650da22a1901f4_@@CA@XZ; void (__cdecl *)()
0x18000871a  mov     cs:qword_180063520, rax
0x180008721  call    atexit
0x180008726  mov     rdx, cs:qword_180063520; struct _tlgProvider_t *
0x18000872d  mov     rcx, rbx; this
0x180008730  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180008735  mov     r8, rbx; lpContext
0x180008738  lea     rcx, ?wrapper@?1??Instance@UndockedUpdateTelemetry@uus@@KAPEAV23@XZ@4V?$static_lazy@VUndockedUpdateTelemetry@uus@@@details@wil@@A; lpInitOnce
0x18000873f  xor     edx, edx; dwFlags
0x180008741  call    cs:__imp_InitOnceComplete
0x180008747  mov     rax, [rsp+48h+Context]
0x18000874c  mov     rax, [rax+8]
0x180008750  mov     rcx, [rsp+48h+var_18]
0x180008755  xor     rcx, rsp; StackCookie
0x180008758  call    __security_check_cookie
0x18000875d  add     rsp, 40h
0x180008761  pop     rbx
0x180008762  retn
```
