# WinHvpRemoveVpFromPartition

- ea: `0x140002454`
- end: `0x1400024bf`
- name: `WinHvpRemoveVpFromPartition`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14002648c`

## callees

- `0x1400024d0`
- `0x140002bf0`

## import_xrefs

- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140002475`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140002475`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14000249a`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14000249a`

## pseudocode

```c
__int64 __fastcall WinHvpRemoveVpFromPartition(__int64 a1)
{
  __int64 v2; // rsi
  KIRQL v3; // al

  v2 = WinHvpReferencePartition(*(_QWORD *)a1);
  v3 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v2 + 80));
  *(_QWORD *)(*(_QWORD *)(v2 + 64) + 8LL * *(unsigned int *)(a1 + 8)) = 0;
  --*(_DWORD *)(v2 + 76);
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v2 + 80), v3);
  return WinHvpDereferencePartition(v2);
}

```

## disassembly

```asm
0x140002454  mov     [rsp+arg_0], rbx
0x140002459  mov     [rsp+arg_8], rsi
0x14000245e  push    rdi
0x14000245f  sub     rsp, 20h
0x140002463  mov     rbx, rcx
0x140002466  mov     rcx, [rcx]
0x140002469  call    WinHvpReferencePartition
0x14000246e  mov     rsi, rax
0x140002471  lea     rcx, [rax+50h]; SpinLock
0x140002475  call    cs:__imp_ExAcquireSpinLockExclusive
0x14000247c  nop     dword ptr [rax+rax+00h]
0x140002481  mov     r8d, [rbx+8]
0x140002485  lea     rcx, [rsi+50h]; SpinLock
0x140002489  mov     rdx, [rsi+40h]
0x14000248d  mov     qword ptr [rdx+r8*8], 0
0x140002495  mov     dl, al; OldIrql
0x140002497  dec     dword ptr [rsi+4Ch]
0x14000249a  call    cs:__imp_ExReleaseSpinLockExclusive
0x1400024a1  nop     dword ptr [rax+rax+00h]
0x1400024a6  mov     rcx, rsi
0x1400024a9  call    WinHvpDereferencePartition
0x1400024ae  mov     rbx, [rsp+28h+arg_0]
0x1400024b3  mov     rsi, [rsp+28h+arg_8]
0x1400024b8  add     rsp, 20h
0x1400024bc  pop     rdi
0x1400024bd  retn
```
