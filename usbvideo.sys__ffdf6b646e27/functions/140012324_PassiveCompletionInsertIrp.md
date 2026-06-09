# PassiveCompletionInsertIrp

- ea: `0x140012324`
- end: `0x1400123f5`
- name: `PassiveCompletionInsertIrp`
- size: `209`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001b60`
- `0x140002930`

## callees

- `0x140012324`
- `0x14001b15c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012348`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012348`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400123a2`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400123a2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012385`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012385`

## pseudocode

```c
LONG __fastcall PassiveCompletionInsertIrp(__int64 a1, __int64 a2)
{
  KSPIN_LOCK *v4; // rdi
  KIRQL v5; // dl
  _QWORD *v6; // r8

  v4 = (KSPIN_LOCK *)(a1 + 456);
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 456));
  v6 = *(_QWORD **)(a1 + 536);
  if ( *v6 != a1 + 528 )
    __fastfail(3u);
  *(_QWORD *)(a2 + 168) = a1 + 528;
  *(_QWORD *)(a2 + 176) = v6;
  *v6 = a2 + 168;
  *(_QWORD *)(a1 + 536) = a2 + 168;
  KeReleaseSpinLock(v4, v5);
  return KeReleaseSemaphore((PRKSEMAPHORE)(a1 + 496), 0, 1, 0);
}

```

## disassembly

```asm
0x140012324  mov     [rsp+arg_8], rbx
0x140012329  mov     [rsp+arg_10], rsi
0x14001232e  mov     [rsp+arg_0], rcx
0x140012333  push    rdi
0x140012334  sub     rsp, 20h
0x140012338  mov     rsi, rdx
0x14001233b  mov     rbx, rcx
0x14001233e  lea     rdi, [rcx+1C8h]
0x140012345  mov     rcx, rdi; SpinLock
0x140012348  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001234f  nop     dword ptr [rax+rax+00h]
0x140012354  mov     dl, al; NewIrql
0x140012356  lea     rcx, [rbx+210h]
0x14001235d  mov     r8, [rcx+8]
0x140012361  cmp     [r8], rcx
0x140012364  jz      short loc_14001236D
0x140012366  mov     ecx, 3
0x14001236b  int     29h; Win8: RtlFailFast(ecx)
0x14001236d  lea     rax, [rsi+0A8h]
0x140012374  mov     [rax], rcx
0x140012377  mov     [rax+8], r8
0x14001237b  mov     [r8], rax
0x14001237e  mov     [rcx+8], rax
0x140012382  mov     rcx, rdi; SpinLock
0x140012385  call    cs:__imp_KeReleaseSpinLock
0x14001238c  nop     dword ptr [rax+rax+00h]
0x140012391  nop
0x140012392  lea     rcx, [rbx+1F0h]; Semaphore
0x140012399  xor     r9d, r9d; Wait
0x14001239c  xor     edx, edx; Increment
0x14001239e  lea     r8d, [r9+1]; Adjustment
0x1400123a2  call    cs:__imp_KeReleaseSemaphore
0x1400123a9  nop     dword ptr [rax+rax+00h]
0x1400123ae  jmp     short loc_1400123E4
0x1400123b0  lea     rax, WPP_GLOBAL_Control
0x1400123b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400123be  cmp     rcx, rax
0x1400123c1  jz      short loc_1400123E4
0x1400123c3  cmp     byte ptr [rcx+29h], 2
0x1400123c7  jb      short loc_1400123E4
0x1400123c9  mov     edx, 8Bh
0x1400123ce  mov     r9, [rsp+28h+arg_0]
0x1400123d3  lea     r8, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
0x1400123da  mov     rcx, [rcx+18h]
0x1400123de  call    WPP_SF_q
0x1400123e3  nop
0x1400123e4  mov     rbx, [rsp+28h+arg_8]
0x1400123e9  mov     rsi, [rsp+28h+arg_10]
0x1400123ee  add     rsp, 20h
0x1400123f2  pop     rdi
0x1400123f3  retn
0x14004133d  push    rbp
0x14004133f  sub     rsp, 20h
0x140041343  mov     rbp, rdx
0x140041346  mov     rax, [rcx]
0x140041349  mov     ecx, [rax]
0x14004134b  xor     eax, eax
0x14004134d  cmp     ecx, 0C0000047h
0x140041353  setz    al
0x140041356  add     rsp, 20h
0x14004135a  pop     rbp
0x14004135b  retn
```
