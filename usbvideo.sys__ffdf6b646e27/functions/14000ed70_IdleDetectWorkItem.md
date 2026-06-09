# IdleDetectWorkItem

- ea: `0x14000ed70`
- end: `0x14000ee4f`
- name: `IdleDetectWorkItem`
- size: `223`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000ed70`
- `0x14000ee58`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000ee39`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000ee39`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ed86`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000edf6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ed86`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000edf6`
- `ntoskrnl!IoFreeWorkItem` at `0x14000ed9c`
- `ntoskrnl!IoFreeWorkItem` at `0x14000ed9c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000edd8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ee19`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000edd8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ee19`

## pseudocode

```c
void __fastcall IdleDetectWorkItem(PDEVICE_OBJECT DeviceObject, char *Context)
{
  KSPIN_LOCK *v2; // rsi
  KIRQL v4; // bp
  bool v5; // zf
  int v6; // ebx

  v2 = (KSPIN_LOCK *)(Context + 216);
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Context + 27);
  IoFreeWorkItem(*((PIO_WORKITEM *)Context + 30));
  v5 = *((_DWORD *)Context + 210) == 0;
  *((_QWORD *)Context + 30) = 0;
  if ( v5 && Context[2]
    || Context[1]
    || (*((_DWORD *)Context + 56) = 2,
        KeReleaseSpinLock(v2, v4),
        v6 = RequestDxPowerIrp((struct _IO_REMOVE_LOCK *)Context, (POWER_STATE)4),
        v4 = KeAcquireSpinLockRaiseToDpc(v2),
        v6 < 0) )
  {
    *((_DWORD *)Context + 56) = 0;
  }
  KeReleaseSpinLock(v2, v4);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)Context + 24, IdleDetectWorkItem, 0x20u);
}

```

## disassembly

```asm
0x14000ed70  push    rbx
0x14000ed72  push    rbp
0x14000ed73  push    rsi
0x14000ed74  push    rdi
0x14000ed75  sub     rsp, 28h
0x14000ed79  lea     rsi, [rdx+0D8h]
0x14000ed80  mov     rdi, rdx
0x14000ed83  mov     rcx, rsi; SpinLock
0x14000ed86  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000ed8d  nop     dword ptr [rax+rax+00h]
0x14000ed92  mov     rcx, [rdi+0F0h]; IoWorkItem
0x14000ed99  mov     bpl, al
0x14000ed9c  call    cs:__imp_IoFreeWorkItem
0x14000eda3  nop     dword ptr [rax+rax+00h]
0x14000eda8  cmp     dword ptr [rdi+348h], 0
0x14000edaf  mov     qword ptr [rdi+0F0h], 0
0x14000edba  jnz     short loc_14000EDC2
0x14000edbc  cmp     byte ptr [rdi+2], 0
0x14000edc0  jnz     short loc_14000EE09
0x14000edc2  cmp     byte ptr [rdi+1], 0
0x14000edc6  jnz     short loc_14000EE09
0x14000edc8  mov     dl, bpl; NewIrql
0x14000edcb  mov     dword ptr [rdi+0E0h], 2
0x14000edd5  mov     rcx, rsi; SpinLock
0x14000edd8  call    cs:__imp_KeReleaseSpinLock
0x14000eddf  nop     dword ptr [rax+rax+00h]
0x14000ede4  mov     edx, 4; PowerState
0x14000ede9  mov     rcx, rdi; Context
0x14000edec  call    RequestDxPowerIrp
0x14000edf1  mov     rcx, rsi; SpinLock
0x14000edf4  mov     ebx, eax
0x14000edf6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000edfd  nop     dword ptr [rax+rax+00h]
0x14000ee02  mov     bpl, al
0x14000ee05  test    ebx, ebx
0x14000ee07  jns     short loc_14000EE13
0x14000ee09  mov     dword ptr [rdi+0E0h], 0
0x14000ee13  mov     dl, bpl; NewIrql
0x14000ee16  mov     rcx, rsi; SpinLock
0x14000ee19  call    cs:__imp_KeReleaseSpinLock
0x14000ee20  nop     dword ptr [rax+rax+00h]
0x14000ee25  lea     rcx, [rdi+300h]; RemoveLock
0x14000ee2c  mov     r8d, 20h ; ' '; RemlockSize
0x14000ee32  lea     rdx, IdleDetectWorkItem; Tag
0x14000ee39  call    cs:__imp_IoReleaseRemoveLockEx
0x14000ee40  nop     dword ptr [rax+rax+00h]
0x14000ee45  add     rsp, 28h
0x14000ee49  pop     rdi
0x14000ee4a  pop     rsi
0x14000ee4b  pop     rbp
0x14000ee4c  pop     rbx
0x14000ee4d  retn
```
