# wpc::UI::Logging::MonitorUILogger::Provider(void)

- ea: `0x14002af88`
- end: `0x14002b071`
- name: `?Provider@MonitorUILogger@Logging@UI@wpc@@SAPEBU_tlgProvider_t@@XZ`
- size: `233`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `33`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14002a6ac`
- `0x14002a754`
- `0x14002a854`
- `0x14002a948`
- `0x14002aa68`
- `0x14002ab10`
- `0x14002adc4`
- `0x14002ae6c`
- `0x14002d3bc`
- `0x14002e660`
- `0x14002e9a8`
- `0x14002ec60`
- `0x14002eda8`
- `0x14002eee0`
- `0x140032044`
- `0x14003218c`
- `0x1400322e0`
- `0x140032560`
- `0x1400460f4`
- `0x140046ab4`
- `0x140046b98`
- `0x140047c40`
- `0x140048ce0`
- `0x14004a8c0`
- `0x14004a9ec`
- `0x14004ab34`
- `0x14004ac60`
- `0x14004adb0`
- `0x14004b050`
- `0x14004b2d0`
- `0x14004cc6c`
- `0x14009516c`
- `0x1400952c0`

## callees

- `0x140001cf8`
- `0x140005a84`
- `0x14002af88`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x14002b05c`
- `KERNEL32!InitOnceComplete` at `0x14002b05c`
- `KERNEL32!InitOnceBeginInitialize` at `0x14002afb0`
- `KERNEL32!InitOnceBeginInitialize` at `0x14002afb0`

## pseudocode

```c
const struct _tlgProvider_t *wpc::UI::Logging::MonitorUILogger::Provider(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( __std_init_once_begin_initialize(
         &`wpc::UI::Logging::MonitorUILogger::Instance'::`2'::wrapper,
         0,
         &v1,
         (LPVOID *)&v2)
    && v1 )
  {
    qword_140111038 = 0;
    v2 = &qword_140111030;
    qword_140111030 = (__int64)&wpc::UI::Logging::MonitorUILogger::`vftable';
    byte_140111040 = 0;
    dword_140111044 = 0;
    qword_140111048 = &`wpc::UI::Logging::MonitorUILogger::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_63b04113eaa3ff14b173f279f469d64c_::_lambda_invoker_cdecl_);
    qword_140111038 = (__int64)qword_140111048;
    byte_140111040 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(qword_140111048);
    dword_140111044 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_140111030 + 8))(&qword_140111030);
    InitOnceComplete(&`wpc::UI::Logging::MonitorUILogger::Instance'::`2'::wrapper, 0, &qword_140111030);
  }
  return (const struct _tlgProvider_t *)v2[1];
}

```

## disassembly

```asm
0x14002af88  mov     rax, rsp
0x14002af8b  push    rbx
0x14002af8c  sub     rsp, 20h
0x14002af90  lea     r9, [rax+10h]; lpContext
0x14002af94  mov     qword ptr [rax+10h], 0
0x14002af9c  lea     r8, [rax+8]; fPending
0x14002afa0  mov     dword ptr [rax+8], 0
0x14002afa7  xor     edx, edx; dwFlags
0x14002afa9  lea     rcx, ?wrapper@?1??Instance@MonitorUILogger@Logging@UI@wpc@@KAPEAV2345@XZ@4V?$static_lazy@VMonitorUILogger@Logging@UI@wpc@@@details@wil@@A; lpInitOnce
0x14002afb0  call    cs:__imp___std_init_once_begin_initialize
0x14002afb6  test    eax, eax
0x14002afb8  jz      loc_14002B062
0x14002afbe  cmp     [rsp+28h+arg_0], 0
0x14002afc3  jz      loc_14002B062
0x14002afc9  lea     rbx, qword_140111030
0x14002afd0  mov     cs:qword_140111038, 0
0x14002afdb  lea     rax, ??_7MonitorUILogger@Logging@UI@wpc@@6B@; const wpc::UI::Logging::MonitorUILogger::`vftable'
0x14002afe2  mov     [rsp+28h+arg_8], rbx
0x14002afe7  mov     cs:qword_140111030, rax
0x14002afee  mov     cs:byte_140111040, 0
0x14002aff5  mov     cs:dword_140111044, 0
0x14002afff  lea     rax, ?__hInner@?1???0StaticHandle@MonitorUILogger@Logging@UI@wpc@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `wpc::UI::Logging::MonitorUILogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x14002b006  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_63b04113eaa3ff14b173f279f469d64c_@@CA@XZ; void (__cdecl *)()
0x14002b00d  mov     cs:qword_140111048, rax
0x14002b014  call    atexit
0x14002b019  mov     rcx, cs:qword_140111048; CallbackContext
0x14002b020  mov     cs:qword_140111038, rcx
0x14002b027  mov     cs:byte_140111040, 1
0x14002b02e  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x14002b033  mov     rax, cs:qword_140111030
0x14002b03a  mov     rcx, rbx
0x14002b03d  mov     cs:dword_140111044, 1
0x14002b047  mov     rax, [rax+8]
0x14002b04b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b050  mov     r8, rbx; lpContext
0x14002b053  lea     rcx, ?wrapper@?1??Instance@MonitorUILogger@Logging@UI@wpc@@KAPEAV2345@XZ@4V?$static_lazy@VMonitorUILogger@Logging@UI@wpc@@@details@wil@@A; lpInitOnce
0x14002b05a  xor     edx, edx; dwFlags
0x14002b05c  call    cs:__imp_InitOnceComplete
0x14002b062  mov     rax, [rsp+28h+arg_8]
0x14002b067  mov     rax, [rax+8]
0x14002b06b  add     rsp, 20h
0x14002b06f  pop     rbx
0x14002b070  retn
```
