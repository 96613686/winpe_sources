# SpLimiterDispatcherThreadRoutine(void *)

- ea: `0x140031bc0`
- end: `0x140031c3a`
- name: `?SpLimiterDispatcherThreadRoutine@@YAXPEAX@Z`
- size: `122`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x140031bc0`
- `0x140068000`

## import_xrefs

- `ntoskrnl!KeRemoveQueue` at `0x140031c17`
- `ntoskrnl!KeRemoveQueue` at `0x140031c17`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x140031bdb`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x140031bdb`
- `ntoskrnl!ExTryQueueWorkItem` at `0x140031bf1`
- `ntoskrnl!ExTryQueueWorkItem` at `0x140031bf1`

## pseudocode

```c
void __fastcall SpLimiterDispatcherThreadRoutine(char *StartContext)
{
  PLIST_ENTRY v2; // rax
  PLIST_ENTRY v3; // rbx

  KeSetActualBasePriorityThread(KeGetCurrentThread(), 12);
  while ( 1 )
  {
    v2 = KeRemoveQueue((PRKQUEUE)(StartContext + 8), 0, 0);
    v3 = v2;
    if ( v2 == (PLIST_ENTRY)128 )
      break;
    if ( !(unsigned __int8)ExTryQueueWorkItem(v2, 1) )
      ((void (__fastcall *)(struct _LIST_ENTRY *))v3[1].Flink)(v3[1].Blink);
  }
}

```

## disassembly

```asm
0x140031bc0  mov     [rsp+arg_0], rbx
0x140031bc5  push    rdi
0x140031bc6  sub     rsp, 20h
0x140031bca  mov     rdi, rcx
0x140031bcd  mov     edx, 0Ch
0x140031bd2  mov     rcx, gs:188h
0x140031bdb  call    cs:__imp_KeSetActualBasePriorityThread
0x140031be2  nop     dword ptr [rax+rax+00h]
0x140031be7  jmp     short loc_140031C0E
0x140031be9  mov     edx, 1
0x140031bee  mov     rcx, rbx
0x140031bf1  call    cs:__imp_ExTryQueueWorkItem
0x140031bf8  nop     dword ptr [rax+rax+00h]
0x140031bfd  test    al, al
0x140031bff  jnz     short loc_140031C0E
0x140031c01  mov     rax, [rbx+10h]
0x140031c05  mov     rcx, [rbx+18h]
0x140031c09  call    _guard_dispatch_icall
0x140031c0e  xor     r8d, r8d; Timeout
0x140031c11  lea     rcx, [rdi+8]; Queue
0x140031c15  xor     edx, edx; WaitMode
0x140031c17  call    cs:__imp_KeRemoveQueue
0x140031c1e  nop     dword ptr [rax+rax+00h]
0x140031c23  mov     rbx, rax
0x140031c26  cmp     rax, 80h
0x140031c2c  jnz     short loc_140031BE9
0x140031c2e  mov     rbx, [rsp+28h+arg_0]
0x140031c33  add     rsp, 20h
0x140031c37  pop     rdi
0x140031c38  retn
```
