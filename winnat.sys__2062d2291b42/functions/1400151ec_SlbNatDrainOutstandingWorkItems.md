# SlbNatDrainOutstandingWorkItems

- ea: `0x1400151ec`
- end: `0x140015263`
- name: `SlbNatDrainOutstandingWorkItems`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140033e5c`

## callees

- `0x1400151ec`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140015226`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015226`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015204`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015204`
- `ntoskrnl!KeDelayExecutionThread` at `0x140015249`
- `ntoskrnl!KeDelayExecutionThread` at `0x140015249`

## pseudocode

```c
void SlbNatDrainOutstandingWorkItems()
{
  char v0; // bl
  KIRQL v1; // al
  union _LARGE_INTEGER Interval; // [rsp+30h] [rbp+8h] BYREF

  v0 = 0;
  while ( 1 )
  {
    v1 = KeAcquireSpinLockRaiseToDpc(&qword_1400274D8);
    if ( !dword_1400274E4 )
      v0 = 1;
    KeReleaseSpinLock(&qword_1400274D8, v1);
    if ( v0 )
      break;
    Interval.QuadPart = -10000;
    KeDelayExecutionThread(1, 0, &Interval);
  }
}

```

## disassembly

```asm
0x1400151ec  mov     [rsp+arg_8], rbx
0x1400151f1  push    rdi
0x1400151f2  sub     rsp, 20h
0x1400151f6  xor     bl, bl
0x1400151f8  mov     edi, 1
0x1400151fd  lea     rcx, qword_1400274D8; SpinLock
0x140015204  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001520b  nop     dword ptr [rax+rax+00h]
0x140015210  cmp     cs:dword_1400274E4, 0
0x140015217  lea     rcx, qword_1400274D8; SpinLock
0x14001521e  movzx   ebx, bl
0x140015221  mov     dl, al; NewIrql
0x140015223  cmovz   ebx, edi
0x140015226  call    cs:__imp_KeReleaseSpinLock
0x14001522d  nop     dword ptr [rax+rax+00h]
0x140015232  test    bl, bl
0x140015234  jnz     short loc_140015257
0x140015236  lea     r8, [rsp+28h+Interval]; Interval
0x14001523b  mov     qword ptr [rsp+28h+Interval], 0FFFFFFFFFFFFD8F0h
0x140015244  xor     edx, edx; Alertable
0x140015246  mov     cl, dil; WaitMode
0x140015249  call    cs:__imp_KeDelayExecutionThread
0x140015250  nop     dword ptr [rax+rax+00h]
0x140015255  jmp     short loc_1400151FD
0x140015257  mov     rbx, [rsp+28h+arg_8]
0x14001525c  add     rsp, 20h
0x140015260  pop     rdi
0x140015261  retn
```
