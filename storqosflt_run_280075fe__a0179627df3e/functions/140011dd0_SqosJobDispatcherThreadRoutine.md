# SqosJobDispatcherThreadRoutine

- ea: `0x140011dd0`
- end: `0x140011e49`
- name: `SqosJobDispatcherThreadRoutine`
- size: `121`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x140008d60`
- `0x140011dd0`

## import_xrefs

- `ntoskrnl!ExTryQueueWorkItem` at `0x140011e01`
- `ntoskrnl!ExTryQueueWorkItem` at `0x140011e01`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x140011deb`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x140011deb`
- `ntoskrnl!KeRemoveQueue` at `0x140011e26`
- `ntoskrnl!KeRemoveQueue` at `0x140011e26`

## pseudocode

```c
void __fastcall SqosJobDispatcherThreadRoutine(char *StartContext)
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
      ((void (__fastcall *)(PLIST_ENTRY))v3[1].Flink)(v3);
  }
}

```

## disassembly

```asm
0x140011dd0  mov     [rsp+arg_0], rbx
0x140011dd5  push    rdi
0x140011dd6  sub     rsp, 20h
0x140011dda  mov     rdi, rcx
0x140011ddd  mov     edx, 0Ch
0x140011de2  mov     rcx, gs:188h
0x140011deb  call    cs:__imp_KeSetActualBasePriorityThread
0x140011df2  nop     dword ptr [rax+rax+00h]
0x140011df7  jmp     short loc_140011E1D
0x140011df9  mov     edx, 1
0x140011dfe  mov     rcx, rbx
0x140011e01  call    cs:__imp_ExTryQueueWorkItem
0x140011e08  nop     dword ptr [rax+rax+00h]
0x140011e0d  test    al, al
0x140011e0f  jnz     short loc_140011E1D
0x140011e11  mov     rax, [rbx+10h]
0x140011e15  mov     rcx, rbx
0x140011e18  call    _guard_dispatch_icall
0x140011e1d  xor     r8d, r8d; Timeout
0x140011e20  lea     rcx, [rdi+8]; Queue
0x140011e24  xor     edx, edx; WaitMode
0x140011e26  call    cs:__imp_KeRemoveQueue
0x140011e2d  nop     dword ptr [rax+rax+00h]
0x140011e32  mov     rbx, rax
0x140011e35  cmp     rax, 80h
0x140011e3b  jnz     short loc_140011DF9
0x140011e3d  mov     rbx, [rsp+28h+arg_0]
0x140011e42  add     rsp, 20h
0x140011e46  pop     rdi
0x140011e47  retn
```
