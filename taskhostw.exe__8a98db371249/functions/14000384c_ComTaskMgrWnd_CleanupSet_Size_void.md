# ComTaskMgrWnd::CleanupSet::Size(void)

- ea: `0x14000384c`
- end: `0x14000387a`
- name: `?Size@CleanupSet@ComTaskMgrWnd@@QEAA_KXZ`
- size: `46`
- prototype: `PVOID __fastcall(PSRWLOCK SRWLock)`
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x140003270`
- `0x140003880`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140003866`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140003866`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140003859`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140003859`

## pseudocode

```c
PVOID __fastcall ComTaskMgrWnd::CleanupSet::Size(PSRWLOCK SRWLock)
{
  PVOID Ptr; // rbx

  AcquireSRWLockExclusive(SRWLock);
  Ptr = SRWLock[2].Ptr;
  ReleaseSRWLockExclusive(SRWLock);
  return Ptr;
}

```

## disassembly

```asm
0x14000384c  mov     [rsp+arg_0], rbx
0x140003851  push    rdi
0x140003852  sub     rsp, 20h
0x140003856  mov     rdi, rcx
0x140003859  call    cs:__imp_AcquireSRWLockExclusive
0x14000385f  mov     rbx, [rdi+10h]
0x140003863  mov     rcx, rdi; SRWLock
0x140003866  call    cs:__imp_ReleaseSRWLockExclusive
0x14000386c  mov     rax, rbx
0x14000386f  mov     rbx, [rsp+28h+arg_0]
0x140003874  add     rsp, 20h
0x140003878  pop     rdi
0x140003879  retn
```
