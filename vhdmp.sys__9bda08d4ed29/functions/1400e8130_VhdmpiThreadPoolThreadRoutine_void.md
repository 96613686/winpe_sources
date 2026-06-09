# VhdmpiThreadPoolThreadRoutine(void *)

- ea: `0x1400e8130`
- end: `0x1400e81af`
- name: `?VhdmpiThreadPoolThreadRoutine@@YAXPEAX@Z`
- size: `127`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14005dc30`
- `0x1400e8130`

## import_xrefs

- `ntoskrnl!ExTryQueueWorkItem` at `0x1400e8168`
- `ntoskrnl!ExTryQueueWorkItem` at `0x1400e8168`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x1400e814b`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x1400e814b`
- `ntoskrnl!KeRemoveQueue` at `0x1400e818c`
- `ntoskrnl!KeRemoveQueue` at `0x1400e818c`

## pseudocode

```c
void __fastcall VhdmpiThreadPoolThreadRoutine(struct _KQUEUE *StartContext)
{
  PLIST_ENTRY v2; // rax
  PLIST_ENTRY v3; // rbx

  KeSetActualBasePriorityThread(KeGetCurrentThread(), 12);
  while ( 1 )
  {
    v2 = KeRemoveQueue(StartContext, 0, 0);
    v3 = v2;
    if ( v2 == (PLIST_ENTRY)128 )
      break;
    v2->Flink = 0;
    if ( !(unsigned __int8)ExTryQueueWorkItem(v2, 1) )
      ((void (__fastcall *)(PLIST_ENTRY))v3[1].Flink)(v3);
  }
}

```

## disassembly

```asm
0x1400e8130  mov     [rsp+arg_0], rbx
0x1400e8135  push    rdi
0x1400e8136  sub     rsp, 20h
0x1400e813a  mov     rdi, rcx
0x1400e813d  mov     edx, 0Ch
0x1400e8142  mov     rcx, gs:188h
0x1400e814b  call    cs:__imp_KeSetActualBasePriorityThread
0x1400e8152  nop     dword ptr [rax+rax+00h]
0x1400e8157  jmp     short loc_1400E8184
0x1400e8159  mov     edx, 1
0x1400e815e  mov     qword ptr [rbx], 0
0x1400e8165  mov     rcx, rbx
0x1400e8168  call    cs:__imp_ExTryQueueWorkItem
0x1400e816f  nop     dword ptr [rax+rax+00h]
0x1400e8174  test    al, al
0x1400e8176  jnz     short loc_1400E8184
0x1400e8178  mov     rax, [rbx+10h]
0x1400e817c  mov     rcx, rbx
0x1400e817f  call    _guard_dispatch_icall
0x1400e8184  xor     r8d, r8d; Timeout
0x1400e8187  xor     edx, edx; WaitMode
0x1400e8189  mov     rcx, rdi; Queue
0x1400e818c  call    cs:__imp_KeRemoveQueue
0x1400e8193  nop     dword ptr [rax+rax+00h]
0x1400e8198  mov     rbx, rax
0x1400e819b  cmp     rax, 80h
0x1400e81a1  jnz     short loc_1400E8159
0x1400e81a3  mov     rbx, [rsp+28h+arg_0]
0x1400e81a8  add     rsp, 20h
0x1400e81ac  pop     rdi
0x1400e81ad  retn
```
