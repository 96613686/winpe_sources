# VhdmpiThreadPoolThreadRoutine(void *)

- ea: `0x1400e81a0`
- end: `0x1400e821f`
- name: `?VhdmpiThreadPoolThreadRoutine@@YAXPEAX@Z`
- size: `127`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14005d840`
- `0x1400e81a0`

## import_xrefs

- `ntoskrnl!ExTryQueueWorkItem` at `0x1400e81d8`
- `ntoskrnl!ExTryQueueWorkItem` at `0x1400e81d8`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x1400e81bb`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x1400e81bb`
- `ntoskrnl!KeRemoveQueue` at `0x1400e81fc`
- `ntoskrnl!KeRemoveQueue` at `0x1400e81fc`

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
0x1400e81a0  mov     [rsp+arg_0], rbx
0x1400e81a5  push    rdi
0x1400e81a6  sub     rsp, 20h
0x1400e81aa  mov     rdi, rcx
0x1400e81ad  mov     edx, 0Ch
0x1400e81b2  mov     rcx, gs:188h
0x1400e81bb  call    cs:__imp_KeSetActualBasePriorityThread
0x1400e81c2  nop     dword ptr [rax+rax+00h]
0x1400e81c7  jmp     short loc_1400E81F4
0x1400e81c9  mov     edx, 1
0x1400e81ce  mov     qword ptr [rbx], 0
0x1400e81d5  mov     rcx, rbx
0x1400e81d8  call    cs:__imp_ExTryQueueWorkItem
0x1400e81df  nop     dword ptr [rax+rax+00h]
0x1400e81e4  test    al, al
0x1400e81e6  jnz     short loc_1400E81F4
0x1400e81e8  mov     rax, [rbx+10h]
0x1400e81ec  mov     rcx, rbx
0x1400e81ef  call    _guard_dispatch_icall
0x1400e81f4  xor     r8d, r8d; Timeout
0x1400e81f7  xor     edx, edx; WaitMode
0x1400e81f9  mov     rcx, rdi; Queue
0x1400e81fc  call    cs:__imp_KeRemoveQueue
0x1400e8203  nop     dword ptr [rax+rax+00h]
0x1400e8208  mov     rbx, rax
0x1400e820b  cmp     rax, 80h
0x1400e8211  jnz     short loc_1400E81C9
0x1400e8213  mov     rbx, [rsp+28h+arg_0]
0x1400e8218  add     rsp, 20h
0x1400e821c  pop     rdi
0x1400e821d  retn
```
