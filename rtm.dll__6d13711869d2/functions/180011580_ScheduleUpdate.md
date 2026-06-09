# ScheduleUpdate

- ea: `0x180011580`
- end: `0x1800115f1`
- name: `ScheduleUpdate`
- size: `113`
- prototype: `__int64 __fastcall(PVOID TimerContext)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x180011600`

## callees

- `0x180011580`

## import_xrefs

- `ntdll!NtSetTimer` at `0x1800115e0`
- `ntdll!NtSetTimer` at `0x1800115e0`
- `ntdll!RtlQueueWorkItem` at `0x1800115a8`
- `ntdll!RtlQueueWorkItem` at `0x1800115a8`

## pseudocode

```c
NTSTATUS __fastcall ScheduleUpdate(PVOID TimerContext)
{
  NTSTATUS result; // eax

  if ( _InterlockedDecrement((volatile signed __int32 *)TimerContext + 12) >= 0 )
  {
    result = RtlQueueWorkItem(ConsolidateNetNumberListsWI, TimerContext, 0);
    if ( !result )
      return result;
    _InterlockedExchange((volatile __int32 *)TimerContext + 12, -1);
  }
  return NtSetTimer(*((HANDLE *)TimerContext + 3), &DueTime, UpdateAPC, TimerContext, 0, 0, 0);
}

```

## disassembly

```asm
0x180011580  mov     [rsp+arg_0], rbx
0x180011585  push    rdi
0x180011586  sub     rsp, 40h
0x18001158a  or      edi, 0FFFFFFFFh
0x18001158d  mov     rbx, rcx
0x180011590  mov     eax, edi
0x180011592  lock xadd [rcx+30h], eax
0x180011597  add     eax, edi
0x180011599  js      short loc_1800115B5
0x18001159b  mov     rdx, rcx; Context
0x18001159e  xor     r8d, r8d; Flags
0x1800115a1  lea     rcx, ConsolidateNetNumberListsWI; Function
0x1800115a8  call    cs:__imp_RtlQueueWorkItem
0x1800115ae  test    eax, eax
0x1800115b0  jz      short loc_1800115E6
0x1800115b2  xchg    edi, [rbx+30h]
0x1800115b5  mov     rcx, [rbx+18h]; TimerHandle
0x1800115b9  lea     r8, UpdateAPC; TimerApcRoutine
0x1800115c0  mov     [rsp+48h+PreviousState], 0; PreviousState
0x1800115c9  lea     rdx, DueTime; DueTime
0x1800115d0  mov     [rsp+48h+Period], 0; Period
0x1800115d8  mov     r9, rbx; TimerContext
0x1800115db  mov     [rsp+48h+WakeTimer], 0; WakeTimer
0x1800115e0  call    cs:__imp_NtSetTimer
0x1800115e6  mov     rbx, [rsp+48h+arg_0]
0x1800115eb  add     rsp, 40h
0x1800115ef  pop     rdi
0x1800115f0  retn
```
