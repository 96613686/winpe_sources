# ResetPdoExtension

- ea: `0x14000e608`
- end: `0x14000e659`
- name: `ResetPdoExtension`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140010650`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e61f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e61f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e63a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e63a`

## pseudocode

```c
void __fastcall ResetPdoExtension(__int64 a1, __int64 a2)
{
  KSPIN_LOCK *v2; // rbx
  KIRQL v4; // al

  v2 = (KSPIN_LOCK *)(a1 + 696);
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 696));
  *(_DWORD *)(a2 + 296) = 0;
  KeReleaseSpinLock(v2, v4);
  *(_DWORD *)(a2 + 16) = 1;
}

```

## disassembly

```asm
0x14000e608  mov     [rsp+arg_0], rbx
0x14000e60d  push    rdi
0x14000e60e  sub     rsp, 20h
0x14000e612  lea     rbx, [rcx+2B8h]
0x14000e619  mov     rdi, rdx
0x14000e61c  mov     rcx, rbx; SpinLock
0x14000e61f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000e626  nop     dword ptr [rax+rax+00h]
0x14000e62b  mov     rcx, rbx; SpinLock
0x14000e62e  mov     dword ptr [rdi+128h], 0
0x14000e638  mov     dl, al; NewIrql
0x14000e63a  call    cs:__imp_KeReleaseSpinLock
0x14000e641  nop     dword ptr [rax+rax+00h]
0x14000e646  mov     rbx, [rsp+28h+arg_0]
0x14000e64b  mov     dword ptr [rdi+10h], 1
0x14000e652  add     rsp, 20h
0x14000e656  pop     rdi
0x14000e657  retn
```
