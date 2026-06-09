# WinHvpInitializePersistenceSupport

- ea: `0x140022394`
- end: `0x1400223d7`
- name: `WinHvpInitializePersistenceSupport`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14002a804`

## import_xrefs

- `ntoskrnl!ExInitializeRundownProtection` at `0x14002239f`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14002239f`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400223b2`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400223b2`
- `ntoskrnl!ExRundownCompleted` at `0x1400223c5`
- `ntoskrnl!ExRundownCompleted` at `0x1400223c5`

## pseudocode

```c
void WinHvpInitializePersistenceSupport()
{
  ExInitializeRundownProtection(&RunRef);
  ExWaitForRundownProtectionRelease(&RunRef);
  ExRundownCompleted(&RunRef);
}

```

## disassembly

```asm
0x140022394  sub     rsp, 28h
0x140022398  lea     rcx, RunRef; RunRef
0x14002239f  call    cs:__imp_ExInitializeRundownProtection
0x1400223a6  nop     dword ptr [rax+rax+00h]
0x1400223ab  lea     rcx, RunRef; RunRef
0x1400223b2  call    cs:__imp_ExWaitForRundownProtectionRelease
0x1400223b9  nop     dword ptr [rax+rax+00h]
0x1400223be  lea     rcx, RunRef; RunRef
0x1400223c5  call    cs:__imp_ExRundownCompleted
0x1400223cc  nop     dword ptr [rax+rax+00h]
0x1400223d1  add     rsp, 28h
0x1400223d5  retn
```
