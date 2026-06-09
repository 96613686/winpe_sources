# Windows::Telemetry::ServiceErrors::FallbackTelemetryCallback(bool,wil::FailureInfo const &)

- ea: `0x180030620`
- end: `0x18003071a`
- name: `?FallbackTelemetryCallback@ServiceErrors@Telemetry@Windows@@SAX_NAEBUFailureInfo@wil@@@Z`
- size: `250`
- prototype: `void __fastcall(bool, const struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180030620`
- `0x180039534`
- `0x1800dd930`
- `0x1800dddd4`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180030665`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180030665`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800306e1`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800306e1`

## pseudocode

```c
void __fastcall Windows::Telemetry::ServiceErrors::FallbackTelemetryCallback(
        char a1,
        const struct wil::FailureInfo *a2)
{
  __int64 v4; // rdx
  void (*v5)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  LPVOID v6; // [rsp+20h] [rbp-28h] BYREF
  WINBOOL v7; // [rsp+28h] [rbp-20h] BYREF

  v6 = 0;
  v7 = 0;
  if ( __std_init_once_begin_initialize(&`Windows::Telemetry::ServiceErrors::Instance'::`2'::wrapper, 0, &v7, &v6) && v7 )
  {
    qword_180150B70 = 0;
    v6 = &qword_180150B68;
    qword_180150B68 = &Windows::Telemetry::ServiceBase::`vftable';
    byte_180150B78 = 0;
    dword_180150B7C = 0;
    qword_180150B80 = (struct _tlgProvider_t *)&`Windows::Telemetry::ServiceErrors::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(`Windows::Telemetry::ServiceErrors::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180150B68, qword_180150B80, v5);
    InitOnceComplete(&`Windows::Telemetry::ServiceErrors::Instance'::`2'::wrapper, 0, &qword_180150B68);
  }
  LOBYTE(v4) = a1;
  (*(void (__fastcall **)(LPVOID, __int64, const struct wil::FailureInfo *))(*(_QWORD *)v6 + 16LL))(v6, v4, a2);
}

```

## disassembly

```asm
0x180030620  mov     r11, rsp
0x180030623  mov     [r11+18h], rbx
0x180030627  mov     [r11+20h], rsi
0x18003062b  push    rdi
0x18003062c  sub     rsp, 40h
0x180030630  mov     rax, cs:__security_cookie
0x180030637  xor     rax, rsp
0x18003063a  mov     [rsp+48h+var_18], rax
0x18003063f  mov     rdi, rdx
0x180030642  mov     qword ptr [r11-28h], 0
0x18003064a  mov     bl, cl
0x18003064c  mov     [rsp+48h+var_20], 0
0x180030654  xor     edx, edx; dwFlags
0x180030656  lea     rcx, ?wrapper@?1??Instance@ServiceErrors@Telemetry@Windows@@KAPEAV234@XZ@4V?$static_lazy@VServiceErrors@Telemetry@Windows@@@details@wil@@A; lpInitOnce
0x18003065d  lea     r9, [r11-28h]; lpContext
0x180030661  lea     r8, [r11-20h]; fPending
0x180030665  call    cs:__imp___std_init_once_begin_initialize
0x18003066b  test    eax, eax
0x18003066d  jz      short loc_1800306E7
0x18003066f  cmp     [rsp+48h+var_20], 0
0x180030674  jz      short loc_1800306E7
0x180030676  lea     rsi, qword_180150B68
0x18003067d  mov     cs:qword_180150B70, 0
0x180030688  lea     rax, ??_7ServiceBase@Telemetry@Windows@@6B@; const Windows::Telemetry::ServiceBase::`vftable'
0x18003068f  mov     [rsp+48h+var_28], rsi
0x180030694  mov     cs:qword_180150B68, rax
0x18003069b  mov     cs:byte_180150B78, 0
0x1800306a2  mov     cs:dword_180150B7C, 0
0x1800306ac  lea     rax, ?__hInner@?1???0StaticHandle@ServiceErrors@Telemetry@Windows@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `Windows::Telemetry::ServiceErrors::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800306b3  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@ServiceErrors@Telemetry@Windows@@KAPEAV345@XZ@SA@XZ; void (__cdecl *)()
0x1800306ba  mov     cs:qword_180150B80, rax
0x1800306c1  call    atexit
0x1800306c6  mov     rdx, cs:qword_180150B80; struct _tlgProvider_t *
0x1800306cd  mov     rcx, rsi; this
0x1800306d0  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x1800306d5  mov     r8, rsi; lpContext
0x1800306d8  lea     rcx, ?wrapper@?1??Instance@ServiceErrors@Telemetry@Windows@@KAPEAV234@XZ@4V?$static_lazy@VServiceErrors@Telemetry@Windows@@@details@wil@@A; lpInitOnce
0x1800306df  xor     edx, edx; dwFlags
0x1800306e1  call    cs:__imp_InitOnceComplete
0x1800306e7  mov     rcx, [rsp+48h+var_28]
0x1800306ec  mov     r8, rdi
0x1800306ef  mov     dl, bl
0x1800306f1  mov     rax, [rcx]
0x1800306f4  mov     rax, [rax+10h]
0x1800306f8  call    _guard_dispatch_icall
0x1800306fd  mov     rcx, [rsp+48h+var_18]
0x180030702  xor     rcx, rsp; StackCookie
0x180030705  call    __security_check_cookie
0x18003070a  mov     rbx, [rsp+48h+arg_10]
0x18003070f  mov     rsi, [rsp+48h+arg_18]
0x180030714  add     rsp, 40h
0x180030718  pop     rdi
0x180030719  retn
```
