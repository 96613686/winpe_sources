# Tpm20Scheduler::SchedulerThreadWrapper(void *)

- ea: `0x14001c080`
- end: `0x14001c0e0`
- name: `?SchedulerThreadWrapper@Tpm20Scheduler@@CAXPEAX@Z`
- size: `96`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400179c4`
- `0x14001c080`

## import_xrefs

- `ntoskrnl!PsTerminateSystemThread` at `0x14001c0cd`
- `ntoskrnl!PsTerminateSystemThread` at `0x14001c0cd`
- `ntoskrnl!KeSetPriorityThread` at `0x14001c0af`
- `ntoskrnl!KeSetPriorityThread` at `0x14001c0af`
- `ntoskrnl!KeQueryPriorityThread` at `0x14001c096`
- `ntoskrnl!KeQueryPriorityThread` at `0x14001c096`

## pseudocode

```c
void __fastcall Tpm20Scheduler::SchedulerThreadWrapper(PVOID StartContext)
{
  struct _KTHREAD *CurrentThread; // rcx

  CurrentThread = KeGetCurrentThread();
  *((_QWORD *)StartContext + 13) = CurrentThread;
  if ( KeQueryPriorityThread(CurrentThread) < 16 )
    KeSetPriorityThread(*((PKTHREAD *)StartContext + 13), 16);
  Tpm20Scheduler::SchedulerThreadFunction((Tpm20Scheduler *)StartContext);
  *((_QWORD *)StartContext + 13) = 0;
  PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x14001c080  push    rbx
0x14001c082  sub     rsp, 20h
0x14001c086  mov     rbx, rcx
0x14001c089  mov     rcx, gs:188h; Thread
0x14001c092  mov     [rbx+68h], rcx
0x14001c096  call    cs:__imp_KeQueryPriorityThread
0x14001c09d  nop     dword ptr [rax+rax+00h]
0x14001c0a2  mov     edx, 10h; Priority
0x14001c0a7  cmp     eax, edx
0x14001c0a9  jge     short loc_14001C0BB
0x14001c0ab  mov     rcx, [rbx+68h]; Thread
0x14001c0af  call    cs:__imp_KeSetPriorityThread
0x14001c0b6  nop     dword ptr [rax+rax+00h]
0x14001c0bb  mov     rcx, rbx; this
0x14001c0be  call    ?SchedulerThreadFunction@Tpm20Scheduler@@AEAAXXZ; Tpm20Scheduler::SchedulerThreadFunction(void)
0x14001c0c3  xor     ecx, ecx; ExitStatus
0x14001c0c5  mov     qword ptr [rbx+68h], 0
0x14001c0cd  call    cs:__imp_PsTerminateSystemThread
0x14001c0d4  nop     dword ptr [rax+rax+00h]
0x14001c0d9  add     rsp, 20h
0x14001c0dd  pop     rbx
0x14001c0de  retn
```
