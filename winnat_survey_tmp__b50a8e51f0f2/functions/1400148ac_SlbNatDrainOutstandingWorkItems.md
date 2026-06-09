# SlbNatDrainOutstandingWorkItems

- ea: `0x1400148ac`
- end: `0x140014923`
- name: `SlbNatDrainOutstandingWorkItems`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140032d2c`

## callees

- `0x1400148ac`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400148e6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400148e6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400148c4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400148c4`
- `ntoskrnl!KeDelayExecutionThread` at `0x140014909`
- `ntoskrnl!KeDelayExecutionThread` at `0x140014909`

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
    v1 = KeAcquireSpinLockRaiseToDpc(&qword_1400264D8);
    if ( !dword_1400264E4 )
      v0 = 1;
    KeReleaseSpinLock(&qword_1400264D8, v1);
    if ( v0 )
      break;
    Interval.QuadPart = -10000;
    KeDelayExecutionThread(1, 0, &Interval);
  }
}

```

## disassembly

```asm
0x1400148ac  mov     [rsp+arg_8], rbx
0x1400148b1  push    rdi
0x1400148b2  sub     rsp, 20h
0x1400148b6  xor     bl, bl
0x1400148b8  mov     edi, 1
0x1400148bd  lea     rcx, qword_1400264D8; SpinLock
0x1400148c4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400148cb  nop     dword ptr [rax+rax+00h]
0x1400148d0  cmp     cs:dword_1400264E4, 0
0x1400148d7  lea     rcx, qword_1400264D8; SpinLock
0x1400148de  movzx   ebx, bl
0x1400148e1  mov     dl, al; NewIrql
0x1400148e3  cmovz   ebx, edi
0x1400148e6  call    cs:__imp_KeReleaseSpinLock
0x1400148ed  nop     dword ptr [rax+rax+00h]
0x1400148f2  test    bl, bl
0x1400148f4  jnz     short loc_140014917
0x1400148f6  lea     r8, [rsp+28h+Interval]; Interval
0x1400148fb  mov     qword ptr [rsp+28h+Interval], 0FFFFFFFFFFFFD8F0h
0x140014904  xor     edx, edx; Alertable
0x140014906  mov     cl, dil; WaitMode
0x140014909  call    cs:__imp_KeDelayExecutionThread
0x140014910  nop     dword ptr [rax+rax+00h]
0x140014915  jmp     short loc_1400148BD
0x140014917  mov     rbx, [rsp+28h+arg_8]
0x14001491c  add     rsp, 20h
0x140014920  pop     rdi
0x140014921  retn
```
