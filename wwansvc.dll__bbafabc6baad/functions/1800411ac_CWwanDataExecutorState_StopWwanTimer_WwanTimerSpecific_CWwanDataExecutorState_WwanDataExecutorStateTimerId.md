# CWwanDataExecutorState::StopWwanTimer(_WwanTimerSpecific *,CWwanDataExecutorState::WwanDataExecutorStateTimerId)

- ea: `0x1800411ac`
- end: `0x180041223`
- name: `?StopWwanTimer@CWwanDataExecutorState@@AEAAKPEAU_WwanTimerSpecific@@W4WwanDataExecutorStateTimerId@1@@Z`
- size: `119`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18003cfd8`
- `0x180042be8`
- `0x180043474`
- `0x180043a54`
- `0x180043d1c`
- `0x180043eec`
- `0x1800446b0`
- `0x180044920`

## callees

- `0x180014f1c`

## import_xrefs

- `MobileNetworking!StopTimer` at `0x1800411de`
- `MobileNetworking!StopTimer` at `0x1800411de`
- `MobileNetworking!AcquireWriteLock` at `0x1800411cd`
- `MobileNetworking!AcquireWriteLock` at `0x1800411cd`
- `MobileNetworking!ReleaseWriteLock` at `0x1800411f8`
- `MobileNetworking!ReleaseWriteLock` at `0x1800411f8`

## string_xrefs

- `0x180041201`: `Timer (ID = %d) Stop Completed`

## pseudocode

```c
__int64 __fastcall CWwanDataExecutorState::StopWwanTimer(__int64 a1, __int64 a2, unsigned int a3)
{
  AcquireWriteLock(*(_QWORD *)(a2 + 104), a2, "CWwanDataExecutorState::StopWwanTimer", 4277);
  StopTimer(*(_QWORD *)(a2 + 104), "CWwanDataExecutorState::StopWwanTimer");
  ReleaseWriteLock(*(_QWORD *)(a2 + 104), a2, "CWwanDataExecutorState::StopWwanTimer", 4279);
  WwanLog::Info("CWwanDataExecutorState::StopWwanTimer", 0, L"Timer (ID = %d) Stop Completed", a3);
  return 0;
}

```

## disassembly

```asm
0x1800411ac  mov     [rsp+arg_0], rbx
0x1800411b1  push    rdi
0x1800411b2  sub     rsp, 20h
0x1800411b6  mov     rcx, [rdx+68h]
0x1800411ba  mov     edi, r8d
0x1800411bd  lea     r8, aCwwandataexecu_5; "CWwanDataExecutorState::StopWwanTimer"
0x1800411c4  mov     r9d, 10B5h
0x1800411ca  mov     rbx, rdx
0x1800411cd  call    cs:__imp_AcquireWriteLock
0x1800411d3  mov     rcx, [rbx+68h]
0x1800411d7  lea     rdx, aCwwandataexecu_5; "CWwanDataExecutorState::StopWwanTimer"
0x1800411de  call    cs:__imp_StopTimer
0x1800411e4  mov     rcx, [rbx+68h]
0x1800411e8  lea     r8, aCwwandataexecu_5; "CWwanDataExecutorState::StopWwanTimer"
0x1800411ef  mov     r9d, 10B7h
0x1800411f5  mov     rdx, rbx
0x1800411f8  call    cs:__imp_ReleaseWriteLock
0x1800411fe  mov     r9d, edi
0x180041201  lea     r8, aTimerIdDStopCo; "Timer (ID = %d) Stop Completed"
0x180041208  xor     edx, edx; struct _GUID *
0x18004120a  lea     rcx, aCwwandataexecu_5; "CWwanDataExecutorState::StopWwanTimer"
0x180041211  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180041216  mov     rbx, [rsp+28h+arg_0]
0x18004121b  xor     eax, eax
0x18004121d  add     rsp, 20h
0x180041221  pop     rdi
0x180041222  retn
```
