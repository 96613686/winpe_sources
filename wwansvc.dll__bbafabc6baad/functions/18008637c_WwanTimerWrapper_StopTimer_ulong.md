# WwanTimerWrapper::StopTimer(ulong)

- ea: `0x18008637c`
- end: `0x1800863f2`
- name: `?StopTimer@WwanTimerWrapper@@QEAAXK@Z`
- size: `118`
- prototype: `void __fastcall(WwanTimerWrapper *__hidden this, unsigned int)`
- caller_count: `15`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001ca48`
- `0x18001cc60`
- `0x18001cd10`
- `0x18006658c`
- `0x18006d8bc`
- `0x18006d9e4`
- `0x18006dcac`
- `0x18006de20`
- `0x180074d1c`
- `0x180091b84`
- `0x180091ea4`
- `0x180097180`
- `0x18009a1c0`
- `0x18009aed8`
- `0x18009af90`

## callees

- `0x180016c50`

## import_xrefs

- `MobileNetworking!StopTimer` at `0x1800863b0`
- `MobileNetworking!StopTimer` at `0x1800863b0`
- `MobileNetworking!AcquireWriteLock` at `0x18008639f`
- `MobileNetworking!AcquireWriteLock` at `0x18008639f`
- `MobileNetworking!ReleaseWriteLock` at `0x1800863ca`
- `MobileNetworking!ReleaseWriteLock` at `0x1800863ca`

## string_xrefs

- `0x1800863d3`: ` Timer (%d) Stop Completed`

## pseudocode

```c
void __fastcall WwanTimerWrapper::StopTimer(
        WwanTimerWrapper *this,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  AcquireWriteLock(*((_QWORD *)this + 13), this, "WwanTimerWrapper::StopTimer", 509);
  StopTimer(*((_QWORD *)this + 13), "WwanTimerWrapper::StopTimer");
  ReleaseWriteLock(*((_QWORD *)this + 13), this, "WwanTimerWrapper::StopTimer", 511);
  WwanLog::Verbose("WwanTimerWrapper::StopTimer", 0, L" Timer (%d) Stop Completed", a2, a5);
}

```

## disassembly

```asm
0x18008637c  mov     [rsp+arg_0], rbx
0x180086381  push    rdi
0x180086382  sub     rsp, 20h
0x180086386  mov     edi, edx
0x180086388  lea     r8, aWwantimerwrapp_1; "WwanTimerWrapper::StopTimer"
0x18008638f  mov     rdx, rcx
0x180086392  mov     rbx, rcx
0x180086395  mov     rcx, [rcx+68h]
0x180086399  mov     r9d, 1FDh
0x18008639f  call    cs:__imp_AcquireWriteLock
0x1800863a5  mov     rcx, [rbx+68h]
0x1800863a9  lea     rdx, aWwantimerwrapp_1; "WwanTimerWrapper::StopTimer"
0x1800863b0  call    cs:__imp_StopTimer
0x1800863b6  mov     rcx, [rbx+68h]
0x1800863ba  lea     r8, aWwantimerwrapp_1; "WwanTimerWrapper::StopTimer"
0x1800863c1  mov     r9d, 1FFh
0x1800863c7  mov     rdx, rbx
0x1800863ca  call    cs:__imp_ReleaseWriteLock
0x1800863d0  mov     r9d, edi
0x1800863d3  lea     r8, aTimerDStopComp; " Timer (%d) Stop Completed"
0x1800863da  xor     edx, edx; struct _GUID *
0x1800863dc  lea     rcx, aWwantimerwrapp_1; "WwanTimerWrapper::StopTimer"
0x1800863e3  mov     rbx, [rsp+28h+arg_0]
0x1800863e8  add     rsp, 20h
0x1800863ec  pop     rdi
0x1800863ed  jmp     ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
```
