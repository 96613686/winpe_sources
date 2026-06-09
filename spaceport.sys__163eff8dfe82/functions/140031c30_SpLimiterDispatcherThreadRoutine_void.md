# SpLimiterDispatcherThreadRoutine(void *)

- ea: `0x140031c30`
- end: `0x140031caa`
- name: `?SpLimiterDispatcherThreadRoutine@@YAXPEAX@Z`
- size: `122`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x140031c30`
- `0x140068150`

## import_xrefs

- `ntoskrnl!KeRemoveQueue` at `0x140031c87`
- `ntoskrnl!KeRemoveQueue` at `0x140031c87`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x140031c4b`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x140031c4b`
- `ntoskrnl!ExTryQueueWorkItem` at `0x140031c61`
- `ntoskrnl!ExTryQueueWorkItem` at `0x140031c61`

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
0x140031c30  mov     [rsp+arg_0], rbx
0x140031c35  push    rdi
0x140031c36  sub     rsp, 20h
0x140031c3a  mov     rdi, rcx
0x140031c3d  mov     edx, 0Ch
0x140031c42  mov     rcx, gs:188h
0x140031c4b  call    cs:__imp_KeSetActualBasePriorityThread
0x140031c52  nop     dword ptr [rax+rax+00h]
0x140031c57  jmp     short loc_140031C7E
0x140031c59  mov     edx, 1
0x140031c5e  mov     rcx, rbx
0x140031c61  call    cs:__imp_ExTryQueueWorkItem
0x140031c68  nop     dword ptr [rax+rax+00h]
0x140031c6d  test    al, al
0x140031c6f  jnz     short loc_140031C7E
0x140031c71  mov     rax, [rbx+10h]
0x140031c75  mov     rcx, [rbx+18h]
0x140031c79  call    _guard_dispatch_icall
0x140031c7e  xor     r8d, r8d; Timeout
0x140031c81  lea     rcx, [rdi+8]; Queue
0x140031c85  xor     edx, edx; WaitMode
0x140031c87  call    cs:__imp_KeRemoveQueue
0x140031c8e  nop     dword ptr [rax+rax+00h]
0x140031c93  mov     rbx, rax
0x140031c96  cmp     rax, 80h
0x140031c9c  jnz     short loc_140031C59
0x140031c9e  mov     rbx, [rsp+28h+arg_0]
0x140031ca3  add     rsp, 20h
0x140031ca7  pop     rdi
0x140031ca8  retn
```
