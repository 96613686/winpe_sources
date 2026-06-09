# TraceLog::Providers::Reliability::Provider(void)

- ea: `0x1400146cc`
- end: `0x1400147b5`
- name: `?Provider@Reliability@Providers@TraceLog@@SAPEBU_tlgProvider_t@@XZ`
- size: `233`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000c614`
- `0x140013f70`
- `0x140015e18`
- `0x1400177f4`
- `0x1400181ac`
- `0x1400182e0`

## callees

- `0x140001cf8`
- `0x140005a84`
- `0x1400146cc`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x1400147a0`
- `KERNEL32!InitOnceComplete` at `0x1400147a0`
- `KERNEL32!InitOnceBeginInitialize` at `0x1400146f4`
- `KERNEL32!InitOnceBeginInitialize` at `0x1400146f4`

## pseudocode

```c
const struct _tlgProvider_t *TraceLog::Providers::Reliability::Provider(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( __std_init_once_begin_initialize(
         &`TraceLog::Providers::Reliability::Instance'::`2'::wrapper,
         0,
         &v1,
         (LPVOID *)&v2)
    && v1 )
  {
    qword_140110E70 = 0;
    v2 = &qword_140110E68;
    qword_140110E68 = (__int64)&TraceLog::Providers::Reliability::`vftable';
    byte_140110E78 = 0;
    dword_140110E7C = 0;
    CallbackContext = &`TraceLog::Providers::Reliability::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_b3ba549a0478ed578a07f87a224ac94f_::_lambda_invoker_cdecl_);
    qword_140110E70 = (__int64)CallbackContext;
    byte_140110E78 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_140110E7C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_140110E68 + 8))(&qword_140110E68);
    InitOnceComplete(&`TraceLog::Providers::Reliability::Instance'::`2'::wrapper, 0, &qword_140110E68);
  }
  return (const struct _tlgProvider_t *)v2[1];
}

```

## disassembly

```asm
0x1400146cc  mov     rax, rsp
0x1400146cf  push    rbx
0x1400146d0  sub     rsp, 20h
0x1400146d4  lea     r9, [rax+10h]; lpContext
0x1400146d8  mov     qword ptr [rax+10h], 0
0x1400146e0  lea     r8, [rax+8]; fPending
0x1400146e4  mov     dword ptr [rax+8], 0
0x1400146eb  xor     edx, edx; dwFlags
0x1400146ed  lea     rcx, ?wrapper@?1??Instance@Reliability@Providers@TraceLog@@KAPEAV234@XZ@4V?$static_lazy@VReliability@Providers@TraceLog@@@details@wil@@A; lpInitOnce
0x1400146f4  call    cs:__imp___std_init_once_begin_initialize
0x1400146fa  test    eax, eax
0x1400146fc  jz      loc_1400147A6
0x140014702  cmp     [rsp+28h+arg_0], 0
0x140014707  jz      loc_1400147A6
0x14001470d  lea     rbx, qword_140110E68
0x140014714  mov     cs:qword_140110E70, 0
0x14001471f  lea     rax, ??_7Reliability@Providers@TraceLog@@6B@; const TraceLog::Providers::Reliability::`vftable'
0x140014726  mov     [rsp+28h+arg_8], rbx
0x14001472b  mov     cs:qword_140110E68, rax
0x140014732  mov     cs:byte_140110E78, 0
0x140014739  mov     cs:dword_140110E7C, 0
0x140014743  lea     rax, ?__hInner@?1???0StaticHandle@Reliability@Providers@TraceLog@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `TraceLog::Providers::Reliability::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x14001474a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_b3ba549a0478ed578a07f87a224ac94f_@@CA@XZ; void (__cdecl *)()
0x140014751  mov     cs:CallbackContext, rax
0x140014758  call    atexit
0x14001475d  mov     rcx, cs:CallbackContext; CallbackContext
0x140014764  mov     cs:qword_140110E70, rcx
0x14001476b  mov     cs:byte_140110E78, 1
0x140014772  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x140014777  mov     rax, cs:qword_140110E68
0x14001477e  mov     rcx, rbx
0x140014781  mov     cs:dword_140110E7C, 1
0x14001478b  mov     rax, [rax+8]
0x14001478f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014794  mov     r8, rbx; lpContext
0x140014797  lea     rcx, ?wrapper@?1??Instance@Reliability@Providers@TraceLog@@KAPEAV234@XZ@4V?$static_lazy@VReliability@Providers@TraceLog@@@details@wil@@A; lpInitOnce
0x14001479e  xor     edx, edx; dwFlags
0x1400147a0  call    cs:__imp_InitOnceComplete
0x1400147a6  mov     rax, [rsp+28h+arg_8]
0x1400147ab  mov     rax, [rax+8]
0x1400147af  add     rsp, 20h
0x1400147b3  pop     rbx
0x1400147b4  retn
```
