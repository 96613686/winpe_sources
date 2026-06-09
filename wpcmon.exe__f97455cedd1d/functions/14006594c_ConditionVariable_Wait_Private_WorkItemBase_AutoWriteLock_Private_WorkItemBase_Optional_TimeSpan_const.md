# ConditionVariable::Wait<Private::WorkItemBase *>(AutoWriteLock<Private::WorkItemBase *> &,Optional<TimeSpan> const &)

- ea: `0x14006594c`
- end: `0x140065b36`
- name: `??$Wait@PEAVWorkItemBase@Private@@@ConditionVariable@@QEBA_NAEAV?$AutoWriteLock@PEAVWorkItemBase@Private@@@@AEBV?$Optional@VTimeSpan@@@@@Z`
- size: `490`
- prototype: `char __fastcall(PCONDITION_VARIABLE ConditionVariable, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140065df4`

## callees

- `0x140006338`
- `0x14000e200`
- `0x1400237ac`
- `0x140060f58`
- `0x140063324`
- `0x140063c78`
- `0x140063d18`
- `0x14006594c`
- `0x140065d68`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!SleepConditionVariableSRW` at `0x140065aad`
- `KERNEL32!SleepConditionVariableSRW` at `0x140065aad`
- `KERNEL32!GetLastError` at `0x140065ab7`
- `KERNEL32!GetLastError` at `0x140065ae8`
- `KERNEL32!GetLastError` at `0x140065ab7`
- `KERNEL32!GetLastError` at `0x140065ae8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1400659b3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1400659c3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x140065a05`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1400659b3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1400659c3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x140065a05`

## pseudocode

```c

```
