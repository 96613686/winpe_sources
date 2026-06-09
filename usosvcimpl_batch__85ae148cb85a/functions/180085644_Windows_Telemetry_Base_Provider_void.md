# Windows::Telemetry::Base::Provider(void)

- ea: `0x180085644`
- end: `0x18008571b`
- name: `?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ`
- size: `215`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `28`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180086a10`
- `0x180086b90`
- `0x180086d0c`
- `0x180086ef0`
- `0x1800870f0`
- `0x18008735c`
- `0x18008888c`
- `0x1800b2864`
- `0x1800b28f0`
- `0x1800b2bb8`
- `0x1800b2d50`
- `0x1800b30ec`
- `0x1800b7414`
- `0x1800b74a0`
- `0x1800bc160`
- `0x1800bc428`
- `0x1800bc610`
- `0x1800bcdf8`
- `0x1800bd500`
- `0x1800bd7c8`
- `0x1800bd8ec`
- `0x1800c18b0`
- `0x1800c1b78`
- `0x1800c1cf0`
- `0x1800c6000`
- `0x1800c62c8`
- `0x1800c6440`
- `0x1800d5d54`

## callees

- `0x180039534`
- `0x180085644`
- `0x1800dd930`
- `0x1800dddd4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18008567d`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18008567d`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800856f9`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800856f9`

## pseudocode

```c
const struct _tlgProvider_t *Windows::Telemetry::Base::Provider(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  LPVOID Context; // [rsp+20h] [rbp-28h] BYREF
  WINBOOL fPending; // [rsp+28h] [rbp-20h] BYREF

  Context = 0;
  fPending = 0;
  if ( __std_init_once_begin_initialize(&`Windows::Telemetry::Base::Instance'::`2'::wrapper, 0, &fPending, &Context)
    && fPending )
  {
    qword_180150410 = 0;
    Context = &qword_180150408;
    qword_180150408 = &Windows::Telemetry::ServiceBase::`vftable';
    byte_180150418 = 0;
    dword_18015041C = 0;
    qword_180150420 = (struct _tlgProvider_t *)&`Windows::Telemetry::Base::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(`Windows::Telemetry::Base::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180150408, qword_180150420, v0);
    InitOnceComplete(&`Windows::Telemetry::Base::Instance'::`2'::wrapper, 0, &qword_180150408);
  }
  return (const struct _tlgProvider_t *)*((_QWORD *)Context + 1);
}

```

## disassembly

```asm
0x180085644  push    rbx
0x180085646  sub     rsp, 40h
0x18008564a  mov     rax, cs:__security_cookie
0x180085651  xor     rax, rsp
0x180085654  mov     [rsp+48h+var_18], rax
0x180085659  lea     r9, [rsp+48h+Context]; lpContext
0x18008565e  mov     [rsp+48h+Context], 0
0x180085667  lea     r8, [rsp+48h+fPending]; fPending
0x18008566c  mov     [rsp+48h+fPending], 0
0x180085674  xor     edx, edx; dwFlags
0x180085676  lea     rcx, ?wrapper@?1??Instance@Base@Telemetry@Windows@@KAPEAV234@XZ@4V?$static_lazy@VBase@Telemetry@Windows@@@details@wil@@A; lpInitOnce
0x18008567d  call    cs:__imp___std_init_once_begin_initialize
0x180085683  test    eax, eax
0x180085685  jz      short loc_1800856FF
0x180085687  cmp     [rsp+48h+fPending], 0
0x18008568c  jz      short loc_1800856FF
0x18008568e  lea     rbx, qword_180150408
0x180085695  mov     cs:qword_180150410, 0
0x1800856a0  lea     rax, ??_7ServiceBase@Telemetry@Windows@@6B@; const Windows::Telemetry::ServiceBase::`vftable'
0x1800856a7  mov     [rsp+48h+Context], rbx
0x1800856ac  mov     cs:qword_180150408, rax
0x1800856b3  mov     cs:byte_180150418, 0
0x1800856ba  mov     cs:dword_18015041C, 0
0x1800856c4  lea     rax, ?__hInner@?1???0StaticHandle@Base@Telemetry@Windows@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `Windows::Telemetry::Base::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800856cb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@Base@Telemetry@Windows@@KAPEAV345@XZ@SA@XZ; void (__cdecl *)()
0x1800856d2  mov     cs:qword_180150420, rax
0x1800856d9  call    atexit
0x1800856de  mov     rdx, cs:qword_180150420; struct _tlgProvider_t *
0x1800856e5  mov     rcx, rbx; this
0x1800856e8  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x1800856ed  mov     r8, rbx; lpContext
0x1800856f0  lea     rcx, ?wrapper@?1??Instance@Base@Telemetry@Windows@@KAPEAV234@XZ@4V?$static_lazy@VBase@Telemetry@Windows@@@details@wil@@A; lpInitOnce
0x1800856f7  xor     edx, edx; dwFlags
0x1800856f9  call    cs:__imp_InitOnceComplete
0x1800856ff  mov     rax, [rsp+48h+Context]
0x180085704  mov     rax, [rax+8]
0x180085708  mov     rcx, [rsp+48h+var_18]
0x18008570d  xor     rcx, rsp; StackCookie
0x180085710  call    __security_check_cookie
0x180085715  add     rsp, 40h
0x180085719  pop     rbx
0x18008571a  retn
```
