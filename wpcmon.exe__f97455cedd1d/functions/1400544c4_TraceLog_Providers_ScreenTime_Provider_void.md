# TraceLog::Providers::ScreenTime::Provider(void)

- ea: `0x1400544c4`
- end: `0x1400545ad`
- name: `?Provider@ScreenTime@Providers@TraceLog@@SAPEBU_tlgProvider_t@@XZ`
- size: `233`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `20`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14004f65c`
- `0x14004f718`
- `0x1400514d0`
- `0x1400533a8`
- `0x140053438`
- `0x1400534c8`
- `0x140053558`
- `0x1400535e8`
- `0x140053ec8`
- `0x140054030`
- `0x1400543a4`
- `0x140054434`
- `0x1400555ac`
- `0x1400556d8`
- `0x140055804`
- `0x140055930`
- `0x140055a90`
- `0x140055d30`
- `0x140055fd0`
- `0x1400576e0`

## callees

- `0x140001cf8`
- `0x140005a84`
- `0x1400544c4`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x140054598`
- `KERNEL32!InitOnceComplete` at `0x140054598`
- `KERNEL32!InitOnceBeginInitialize` at `0x1400544ec`
- `KERNEL32!InitOnceBeginInitialize` at `0x1400544ec`

## pseudocode

```c
const struct _tlgProvider_t *TraceLog::Providers::ScreenTime::Provider(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( __std_init_once_begin_initialize(
         &`TraceLog::Providers::ScreenTime::Instance'::`2'::wrapper,
         0,
         &v1,
         (LPVOID *)&v2)
    && v1 )
  {
    qword_140111168 = 0;
    v2 = &qword_140111160;
    qword_140111160 = (__int64)&TraceLog::Providers::ScreenTime::`vftable';
    byte_140111170 = 0;
    dword_140111174 = 0;
    qword_140111178 = &`TraceLog::Providers::ScreenTime::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_65efeca8168c3558c084acd0087e3a44_::_lambda_invoker_cdecl_);
    qword_140111168 = (__int64)qword_140111178;
    byte_140111170 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(qword_140111178);
    dword_140111174 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_140111160 + 8))(&qword_140111160);
    InitOnceComplete(&`TraceLog::Providers::ScreenTime::Instance'::`2'::wrapper, 0, &qword_140111160);
  }
  return (const struct _tlgProvider_t *)v2[1];
}

```

## disassembly

```asm
0x1400544c4  mov     rax, rsp
0x1400544c7  push    rbx
0x1400544c8  sub     rsp, 20h
0x1400544cc  lea     r9, [rax+10h]; lpContext
0x1400544d0  mov     qword ptr [rax+10h], 0
0x1400544d8  lea     r8, [rax+8]; fPending
0x1400544dc  mov     dword ptr [rax+8], 0
0x1400544e3  xor     edx, edx; dwFlags
0x1400544e5  lea     rcx, ?wrapper@?1??Instance@ScreenTime@Providers@TraceLog@@KAPEAV234@XZ@4V?$static_lazy@VScreenTime@Providers@TraceLog@@@details@wil@@A; lpInitOnce
0x1400544ec  call    cs:__imp___std_init_once_begin_initialize
0x1400544f2  test    eax, eax
0x1400544f4  jz      loc_14005459E
0x1400544fa  cmp     [rsp+28h+arg_0], 0
0x1400544ff  jz      loc_14005459E
0x140054505  lea     rbx, qword_140111160
0x14005450c  mov     cs:qword_140111168, 0
0x140054517  lea     rax, ??_7ScreenTime@Providers@TraceLog@@6B@; const TraceLog::Providers::ScreenTime::`vftable'
0x14005451e  mov     [rsp+28h+arg_8], rbx
0x140054523  mov     cs:qword_140111160, rax
0x14005452a  mov     cs:byte_140111170, 0
0x140054531  mov     cs:dword_140111174, 0
0x14005453b  lea     rax, ?__hInner@?1???0StaticHandle@ScreenTime@Providers@TraceLog@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `TraceLog::Providers::ScreenTime::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x140054542  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_65efeca8168c3558c084acd0087e3a44_@@CA@XZ; void (__cdecl *)()
0x140054549  mov     cs:qword_140111178, rax
0x140054550  call    atexit
0x140054555  mov     rcx, cs:qword_140111178; CallbackContext
0x14005455c  mov     cs:qword_140111168, rcx
0x140054563  mov     cs:byte_140111170, 1
0x14005456a  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x14005456f  mov     rax, cs:qword_140111160
0x140054576  mov     rcx, rbx
0x140054579  mov     cs:dword_140111174, 1
0x140054583  mov     rax, [rax+8]
0x140054587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005458c  mov     r8, rbx; lpContext
0x14005458f  lea     rcx, ?wrapper@?1??Instance@ScreenTime@Providers@TraceLog@@KAPEAV234@XZ@4V?$static_lazy@VScreenTime@Providers@TraceLog@@@details@wil@@A; lpInitOnce
0x140054596  xor     edx, edx; dwFlags
0x140054598  call    cs:__imp_InitOnceComplete
0x14005459e  mov     rax, [rsp+28h+arg_8]
0x1400545a3  mov     rax, [rax+8]
0x1400545a7  add     rsp, 20h
0x1400545ab  pop     rbx
0x1400545ac  retn
```
