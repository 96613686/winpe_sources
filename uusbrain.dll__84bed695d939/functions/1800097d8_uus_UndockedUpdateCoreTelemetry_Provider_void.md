# uus::UndockedUpdateCoreTelemetry::Provider(void)

- ea: `0x1800097d8`
- end: `0x1800098af`
- name: `?Provider@UndockedUpdateCoreTelemetry@uus@@SAPEBU_tlgProvider_t@@XZ`
- size: `215`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180009938`
- `0x18003e358`

## callees

- `0x180008520`
- `0x1800097d8`
- `0x1800427d0`
- `0x180042ba4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000988d`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000988d`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180009811`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180009811`

## pseudocode

```c
const struct _tlgProvider_t *uus::UndockedUpdateCoreTelemetry::Provider(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  LPVOID Context; // [rsp+20h] [rbp-28h] BYREF
  WINBOOL fPending; // [rsp+28h] [rbp-20h] BYREF

  Context = 0;
  fPending = 0;
  if ( __std_init_once_begin_initialize(
         &`uus::UndockedUpdateCoreTelemetry::Instance'::`2'::wrapper,
         0,
         &fPending,
         &Context)
    && fPending )
  {
    qword_180063598 = 0;
    Context = &qword_180063590;
    qword_180063590 = &uus::UUSTracing::`vftable';
    byte_1800635A0 = 0;
    dword_1800635A4 = 0;
    qword_1800635A8 = (struct _tlgProvider_t *)&`uus::UndockedUpdateCoreTelemetry::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_53493457c1dde45e42dc25341f324570_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180063590, qword_1800635A8, v0);
    InitOnceComplete(&`uus::UndockedUpdateCoreTelemetry::Instance'::`2'::wrapper, 0, &qword_180063590);
  }
  return (const struct _tlgProvider_t *)*((_QWORD *)Context + 1);
}

```

## disassembly

```asm
0x1800097d8  push    rbx
0x1800097da  sub     rsp, 40h
0x1800097de  mov     rax, cs:__security_cookie
0x1800097e5  xor     rax, rsp
0x1800097e8  mov     [rsp+48h+var_18], rax
0x1800097ed  lea     r9, [rsp+48h+Context]; lpContext
0x1800097f2  mov     [rsp+48h+Context], 0
0x1800097fb  lea     r8, [rsp+48h+fPending]; fPending
0x180009800  mov     [rsp+48h+fPending], 0
0x180009808  xor     edx, edx; dwFlags
0x18000980a  lea     rcx, ?wrapper@?1??Instance@UndockedUpdateCoreTelemetry@uus@@KAPEAV23@XZ@4V?$static_lazy@VUndockedUpdateCoreTelemetry@uus@@@details@wil@@A; lpInitOnce
0x180009811  call    cs:__imp___std_init_once_begin_initialize
0x180009817  test    eax, eax
0x180009819  jz      short loc_180009893
0x18000981b  cmp     [rsp+48h+fPending], 0
0x180009820  jz      short loc_180009893
0x180009822  lea     rbx, qword_180063590
0x180009829  mov     cs:qword_180063598, 0
0x180009834  lea     rax, ??_7UUSTracing@uus@@6B@; const uus::UUSTracing::`vftable'
0x18000983b  mov     [rsp+48h+Context], rbx
0x180009840  mov     cs:qword_180063590, rax
0x180009847  mov     cs:byte_1800635A0, 0
0x18000984e  mov     cs:dword_1800635A4, 0
0x180009858  lea     rax, ?__hInner@?1???0StaticHandle@UndockedUpdateCoreTelemetry@uus@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `uus::UndockedUpdateCoreTelemetry::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000985f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_53493457c1dde45e42dc25341f324570_@@CA@XZ; void (__cdecl *)()
0x180009866  mov     cs:qword_1800635A8, rax
0x18000986d  call    atexit
0x180009872  mov     rdx, cs:qword_1800635A8; struct _tlgProvider_t *
0x180009879  mov     rcx, rbx; this
0x18000987c  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180009881  mov     r8, rbx; lpContext
0x180009884  lea     rcx, ?wrapper@?1??Instance@UndockedUpdateCoreTelemetry@uus@@KAPEAV23@XZ@4V?$static_lazy@VUndockedUpdateCoreTelemetry@uus@@@details@wil@@A; lpInitOnce
0x18000988b  xor     edx, edx; dwFlags
0x18000988d  call    cs:__imp_InitOnceComplete
0x180009893  mov     rax, [rsp+48h+Context]
0x180009898  mov     rax, [rax+8]
0x18000989c  mov     rcx, [rsp+48h+var_18]
0x1800098a1  xor     rcx, rsp; StackCookie
0x1800098a4  call    __security_check_cookie
0x1800098a9  add     rsp, 40h
0x1800098ad  pop     rbx
0x1800098ae  retn
```
