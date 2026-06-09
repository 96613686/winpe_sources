# Windows::Telemetry::ServiceBaseCore::Provider(void)

- ea: `0x180086670`
- end: `0x180086747`
- name: `?Provider@ServiceBaseCore@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ`
- size: `215`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800867c8`
- `0x180086908`

## callees

- `0x180039534`
- `0x180086670`
- `0x1800dd930`
- `0x1800dddd4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800866a9`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800866a9`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180086725`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180086725`

## pseudocode

```c
const struct _tlgProvider_t *Windows::Telemetry::ServiceBaseCore::Provider(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  LPVOID Context; // [rsp+20h] [rbp-28h] BYREF
  WINBOOL fPending; // [rsp+28h] [rbp-20h] BYREF

  Context = 0;
  fPending = 0;
  if ( __std_init_once_begin_initialize(
         &`Windows::Telemetry::ServiceBaseCore::Instance'::`2'::wrapper,
         0,
         &fPending,
         &Context)
    && fPending )
  {
    qword_1801503C0 = 0;
    Context = &qword_1801503B8;
    qword_1801503B8 = &Windows::Telemetry::ServiceBase::`vftable';
    byte_1801503C8 = 0;
    dword_1801503CC = 0;
    qword_1801503D0 = (struct _tlgProvider_t *)&`Windows::Telemetry::ServiceBaseCore::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(`Windows::Telemetry::ServiceBaseCore::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_1801503B8, qword_1801503D0, v0);
    InitOnceComplete(&`Windows::Telemetry::ServiceBaseCore::Instance'::`2'::wrapper, 0, &qword_1801503B8);
  }
  return (const struct _tlgProvider_t *)*((_QWORD *)Context + 1);
}

```

## disassembly

```asm
0x180086670  push    rbx
0x180086672  sub     rsp, 40h
0x180086676  mov     rax, cs:__security_cookie
0x18008667d  xor     rax, rsp
0x180086680  mov     [rsp+48h+var_18], rax
0x180086685  lea     r9, [rsp+48h+Context]; lpContext
0x18008668a  mov     [rsp+48h+Context], 0
0x180086693  lea     r8, [rsp+48h+fPending]; fPending
0x180086698  mov     [rsp+48h+fPending], 0
0x1800866a0  xor     edx, edx; dwFlags
0x1800866a2  lea     rcx, ?wrapper@?1??Instance@ServiceBaseCore@Telemetry@Windows@@KAPEAV234@XZ@4V?$static_lazy@VServiceBaseCore@Telemetry@Windows@@@details@wil@@A; lpInitOnce
0x1800866a9  call    cs:__imp___std_init_once_begin_initialize
0x1800866af  test    eax, eax
0x1800866b1  jz      short loc_18008672B
0x1800866b3  cmp     [rsp+48h+fPending], 0
0x1800866b8  jz      short loc_18008672B
0x1800866ba  lea     rbx, qword_1801503B8
0x1800866c1  mov     cs:qword_1801503C0, 0
0x1800866cc  lea     rax, ??_7ServiceBase@Telemetry@Windows@@6B@; const Windows::Telemetry::ServiceBase::`vftable'
0x1800866d3  mov     [rsp+48h+Context], rbx
0x1800866d8  mov     cs:qword_1801503B8, rax
0x1800866df  mov     cs:byte_1801503C8, 0
0x1800866e6  mov     cs:dword_1801503CC, 0
0x1800866f0  lea     rax, ?__hInner@?1???0StaticHandle@ServiceBaseCore@Telemetry@Windows@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `Windows::Telemetry::ServiceBaseCore::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800866f7  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@ServiceBaseCore@Telemetry@Windows@@KAPEAV345@XZ@SA@XZ; void (__cdecl *)()
0x1800866fe  mov     cs:qword_1801503D0, rax
0x180086705  call    atexit
0x18008670a  mov     rdx, cs:qword_1801503D0; struct _tlgProvider_t *
0x180086711  mov     rcx, rbx; this
0x180086714  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180086719  mov     r8, rbx; lpContext
0x18008671c  lea     rcx, ?wrapper@?1??Instance@ServiceBaseCore@Telemetry@Windows@@KAPEAV234@XZ@4V?$static_lazy@VServiceBaseCore@Telemetry@Windows@@@details@wil@@A; lpInitOnce
0x180086723  xor     edx, edx; dwFlags
0x180086725  call    cs:__imp_InitOnceComplete
0x18008672b  mov     rax, [rsp+48h+Context]
0x180086730  mov     rax, [rax+8]
0x180086734  mov     rcx, [rsp+48h+var_18]
0x180086739  xor     rcx, rsp; StackCookie
0x18008673c  call    __security_check_cookie
0x180086741  add     rsp, 40h
0x180086745  pop     rbx
0x180086746  retn
```
