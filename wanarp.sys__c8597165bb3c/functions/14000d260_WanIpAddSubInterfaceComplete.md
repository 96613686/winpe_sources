# WanIpAddSubInterfaceComplete

- ea: `0x14000d260`
- end: `0x14000d2d2`
- name: `WanIpAddSubInterfaceComplete`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000d260`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d279`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d279`
- `ntoskrnl!KeSetEvent` at `0x14000d2a2`
- `ntoskrnl!KeSetEvent` at `0x14000d2a2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d2b5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d2b5`

## pseudocode

```c
void __fastcall WanIpAddSubInterfaceComplete(_DWORD *a1)
{
  __int64 v1; // rdi
  KIRQL v3; // si
  struct _KEVENT *v4; // rcx

  v1 = *(_QWORD *)a1;
  v3 = KeAcquireSpinLockRaiseToDpc(*(PKSPIN_LOCK *)(*(_QWORD *)a1 + 80LL));
  *(_DWORD *)(v1 + 144) = a1[4];
  v4 = *(struct _KEVENT **)(v1 + 136);
  if ( v4 )
    KeSetEvent(v4, 0, 0);
  KeReleaseSpinLock(*(PKSPIN_LOCK *)(v1 + 80), v3);
}

```

## disassembly

```asm
0x14000d260  mov     [rsp+arg_0], rbx
0x14000d265  mov     [rsp+arg_8], rsi
0x14000d26a  push    rdi
0x14000d26b  sub     rsp, 20h
0x14000d26f  mov     rdi, [rcx]
0x14000d272  mov     rbx, rcx
0x14000d275  mov     rcx, [rdi+50h]; SpinLock
0x14000d279  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000d280  nop     dword ptr [rax+rax+00h]
0x14000d285  mov     ecx, [rbx+10h]
0x14000d288  mov     sil, al
0x14000d28b  mov     [rdi+90h], ecx
0x14000d291  mov     rcx, [rdi+88h]; Event
0x14000d298  test    rcx, rcx
0x14000d29b  jz      short loc_14000D2AE
0x14000d29d  xor     r8d, r8d; Wait
0x14000d2a0  xor     edx, edx; Increment
0x14000d2a2  call    cs:__imp_KeSetEvent
0x14000d2a9  nop     dword ptr [rax+rax+00h]
0x14000d2ae  mov     rcx, [rdi+50h]; SpinLock
0x14000d2b2  mov     dl, sil; NewIrql
0x14000d2b5  call    cs:__imp_KeReleaseSpinLock
0x14000d2bc  nop     dword ptr [rax+rax+00h]
0x14000d2c1  mov     rbx, [rsp+28h+arg_0]
0x14000d2c6  mov     rsi, [rsp+28h+arg_8]
0x14000d2cb  add     rsp, 20h
0x14000d2cf  pop     rdi
0x14000d2d0  retn
```
