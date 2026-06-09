# WanIpAddInterfaceComplete

- ea: `0x14000d1f0`
- end: `0x14000d24f`
- name: `WanIpAddInterfaceComplete`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000d1f0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d203`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d203`
- `ntoskrnl!KeSetEvent` at `0x14000d226`
- `ntoskrnl!KeSetEvent` at `0x14000d226`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d239`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d239`

## pseudocode

```c
void __fastcall WanIpAddInterfaceComplete(_DWORD *a1)
{
  __int64 v1; // rdi
  KIRQL v3; // al
  struct _KEVENT *v4; // rcx
  KIRQL v5; // bp

  v1 = *(_QWORD *)a1;
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(*(_QWORD *)a1 + 56LL));
  v4 = *(struct _KEVENT **)(v1 + 96);
  v5 = v3;
  *(_DWORD *)(v1 + 104) = a1[4];
  if ( v4 )
    KeSetEvent(v4, 0, 0);
  KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 56), v5);
}

```

## disassembly

```asm
0x14000d1f0  push    rbx
0x14000d1f2  push    rbp
0x14000d1f3  push    rsi
0x14000d1f4  push    rdi
0x14000d1f5  sub     rsp, 28h
0x14000d1f9  mov     rdi, [rcx]
0x14000d1fc  mov     rbx, rcx
0x14000d1ff  lea     rcx, [rdi+38h]; SpinLock
0x14000d203  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000d20a  nop     dword ptr [rax+rax+00h]
0x14000d20f  mov     rcx, [rdi+60h]; Event
0x14000d213  mov     bpl, al
0x14000d216  mov     edx, [rbx+10h]
0x14000d219  mov     [rdi+68h], edx
0x14000d21c  test    rcx, rcx
0x14000d21f  jz      short loc_14000D232
0x14000d221  xor     r8d, r8d; Wait
0x14000d224  xor     edx, edx; Increment
0x14000d226  call    cs:__imp_KeSetEvent
0x14000d22d  nop     dword ptr [rax+rax+00h]
0x14000d232  mov     dl, bpl; NewIrql
0x14000d235  lea     rcx, [rdi+38h]; SpinLock
0x14000d239  call    cs:__imp_KeReleaseSpinLock
0x14000d240  nop     dword ptr [rax+rax+00h]
0x14000d245  add     rsp, 28h
0x14000d249  pop     rdi
0x14000d24a  pop     rsi
0x14000d24b  pop     rbp
0x14000d24c  pop     rbx
0x14000d24d  retn
```
