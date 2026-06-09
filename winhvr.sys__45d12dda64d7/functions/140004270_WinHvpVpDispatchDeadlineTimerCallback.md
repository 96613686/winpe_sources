# WinHvpVpDispatchDeadlineTimerCallback

- ea: `0x140004270`
- end: `0x1400042d4`
- name: `WinHvpVpDispatchDeadlineTimerCallback`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x140004270`
- `0x1400042dc`

## import_xrefs

- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14000429b`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14000429b`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140004281`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140004281`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400042b3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400042b3`

## pseudocode

```c
__int64 __fastcall WinHvpVpDispatchDeadlineTimerCallback(__int64 a1, _QWORD *a2)
{
  __int64 v3; // rcx

  KeAcquireSpinLockAtDpcLevel(a2 + 11);
  v3 = a2[5];
  if ( v3 )
    KeSetActualBasePriorityThread(v3, 15);
  a2[10] = -1;
  KeReleaseSpinLockFromDpcLevel(a2 + 11);
  return WinHvpDereferenceVp(a2 - 3);
}

```

## disassembly

```asm
0x140004270  mov     [rsp+arg_0], rbx
0x140004275  push    rdi
0x140004276  sub     rsp, 20h
0x14000427a  lea     rcx, [rdx+58h]; SpinLock
0x14000427e  mov     rbx, rdx
0x140004281  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140004288  nop     dword ptr [rax+rax+00h]
0x14000428d  mov     rcx, [rbx+28h]
0x140004291  test    rcx, rcx
0x140004294  jz      short loc_1400042A7
0x140004296  mov     edx, 0Fh
0x14000429b  call    cs:__imp_KeSetActualBasePriorityThread
0x1400042a2  nop     dword ptr [rax+rax+00h]
0x1400042a7  lea     rcx, [rbx+58h]; SpinLock
0x1400042ab  mov     qword ptr [rbx+50h], 0FFFFFFFFFFFFFFFFh
0x1400042b3  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400042ba  nop     dword ptr [rax+rax+00h]
0x1400042bf  lea     rcx, [rbx-18h]
0x1400042c3  call    WinHvpDereferenceVp
0x1400042c8  mov     rbx, [rsp+28h+arg_0]
0x1400042cd  add     rsp, 20h
0x1400042d1  pop     rdi
0x1400042d2  retn
```
