# PgmDereferenceAddress

- ea: `0x1400023b8`
- end: `0x14000253b`
- name: `PgmDereferenceAddress`
- size: `387`
- prototype: `void __fastcall(KSPIN_LOCK *P)`
- caller_count: `16`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140001178`
- `0x140001954`
- `0x140001a50`
- `0x140002048`
- `0x1400025d0`
- `0x1400035e0`
- `0x140003f10`
- `0x140005e3c`
- `0x14000ab60`
- `0x14000ae04`
- `0x14000b0b0`
- `0x14000b670`
- `0x140011904`
- `0x140013930`
- `0x140014540`
- `0x14001a6d0`

## callees

- `0x1400023b8`
- `0x140002550`
- `0x1400052e4`
- `0x140007f1c`
- `0x14001c9f4`

## import_xrefs

- `ntoskrnl!ExInterlockedInsertTailList` at `0x1400024ee`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x1400024ee`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400024b2`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400024b2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400023e5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400023fb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000245e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002474`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400023e5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400023fb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000245e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002474`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400023ce`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000240e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002420`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400023ce`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000240e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002420`

## pseudocode

```c
void __fastcall PgmDereferenceAddress(KSPIN_LOCK *P)
{
  KSPIN_LOCK *v1; // rdi
  KIRQL v3; // al
  KIRQL v5; // bp
  KIRQL v6; // al
  IRP *v7; // rsi
  KSPIN_LOCK v8; // rdx
  PVOID *v9; // rcx
  int v10; // r9d

  v1 = P + 53;
  v3 = KeAcquireSpinLockRaiseToDpc(P + 53);
  if ( (*((_DWORD *)P + 5))-- == 1 )
  {
    KeReleaseSpinLock(v1, v3);
    v5 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
    v6 = KeAcquireSpinLockRaiseToDpc(v1);
    v7 = (IRP *)P[6];
    P[6] = 0;
    v8 = *P;
    if ( *(KSPIN_LOCK **)(*P + 8) != P || (v9 = (PVOID *)P[1], *v9 != P) )
      __fastfail(3u);
    *v9 = (PVOID)v8;
    *(_QWORD *)(v8 + 8) = v9;
    KeReleaseSpinLock(v1, v6);
    KeReleaseSpinLock(&SpinLock, v5);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_a5f71cc0ffa4380b60416a2f8449984a_Traceguids, P);
    if ( KeGetCurrentIrql() )
    {
      if ( (int)PgmQueueForDelayedExecution((unsigned int)PgmDestroyAddress, (_DWORD)P, 0, v10, 0) < 0 )
        ExInterlockedInsertTailList((PLIST_ENTRY)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels, (PLIST_ENTRY)P, &SpinLock);
    }
    else
    {
      PgmDestroyAddress(P);
    }
    if ( v7 )
    {
      v7->Tail.Overlay.CurrentStackLocation->FileObject->FsContext = 0;
      PgmIoComplete(v7);
    }
  }
  else
  {
    KeReleaseSpinLock(v1, v3);
  }
}

```

## disassembly

```asm
0x1400023b8  push    rbx
0x1400023ba  push    rbp
0x1400023bb  push    rsi
0x1400023bc  push    rdi
0x1400023bd  sub     rsp, 38h
0x1400023c1  lea     rdi, [rcx+1A8h]
0x1400023c8  mov     rbx, rcx
0x1400023cb  mov     rcx, rdi; SpinLock
0x1400023ce  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400023d5  nop     dword ptr [rax+rax+00h]
0x1400023da  sub     dword ptr [rbx+14h], 1
0x1400023de  mov     rcx, rdi; SpinLock
0x1400023e1  mov     dl, al; NewIrql
0x1400023e3  jz      short loc_1400023FB
0x1400023e5  call    cs:__imp_KeReleaseSpinLock
0x1400023ec  nop     dword ptr [rax+rax+00h]
0x1400023f1  add     rsp, 38h
0x1400023f5  pop     rdi
0x1400023f6  pop     rsi
0x1400023f7  pop     rbp
0x1400023f8  pop     rbx
0x1400023f9  retn
0x1400023fb  call    cs:__imp_KeReleaseSpinLock
0x140002402  nop     dword ptr [rax+rax+00h]
0x140002407  lea     rcx, SpinLock; SpinLock
0x14000240e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002415  nop     dword ptr [rax+rax+00h]
0x14000241a  mov     rcx, rdi; SpinLock
0x14000241d  mov     bpl, al
0x140002420  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002427  nop     dword ptr [rax+rax+00h]
0x14000242c  mov     rsi, [rbx+30h]
0x140002430  mov     qword ptr [rbx+30h], 0
0x140002438  mov     rdx, [rbx]
0x14000243b  cmp     [rdx+8], rbx
0x14000243f  jnz     loc_140002534
0x140002445  mov     rcx, [rbx+8]
0x140002449  cmp     [rcx], rbx
0x14000244c  jnz     loc_140002534
0x140002452  mov     [rcx], rdx
0x140002455  mov     [rdx+8], rcx
0x140002459  mov     dl, al; NewIrql
0x14000245b  mov     rcx, rdi; SpinLock
0x14000245e  call    cs:__imp_KeReleaseSpinLock
0x140002465  nop     dword ptr [rax+rax+00h]
0x14000246a  mov     dl, bpl; NewIrql
0x14000246d  lea     rcx, SpinLock; SpinLock
0x140002474  call    cs:__imp_KeReleaseSpinLock
0x14000247b  nop     dword ptr [rax+rax+00h]
0x140002480  mov     rcx, cs:WPP_GLOBAL_Control
0x140002487  lea     rax, WPP_GLOBAL_Control
0x14000248e  cmp     rcx, rax
0x140002491  jz      short loc_1400024B2
0x140002493  mov     eax, [rcx+2Ch]
0x140002496  test    al, 4
0x140002498  jz      short loc_1400024B2
0x14000249a  mov     rcx, [rcx+18h]
0x14000249e  lea     r8, WPP_a5f71cc0ffa4380b60416a2f8449984a_Traceguids
0x1400024a5  mov     edx, 1Bh
0x1400024aa  mov     r9, rbx
0x1400024ad  call    WPP_SF_q
0x1400024b2  call    cs:__imp_KeGetCurrentIrql
0x1400024b9  nop     dword ptr [rax+rax+00h]
0x1400024be  xor     r8d, r8d
0x1400024c1  test    al, al
0x1400024c3  jz      short loc_1400024FC
0x1400024c5  mov     rdx, rbx
0x1400024c8  mov     [rsp+58h+var_38], r8b
0x1400024cd  lea     rcx, PgmDestroyAddress
0x1400024d4  call    PgmQueueForDelayedExecution
0x1400024d9  test    eax, eax
0x1400024db  jns     short loc_140002506
0x1400024dd  lea     r8, SpinLock; Lock
0x1400024e4  mov     rdx, rbx; ListEntry
0x1400024e7  lea     rcx, WPP_MAIN_CB.Queue+10h; ListHead
0x1400024ee  call    cs:__imp_ExInterlockedInsertTailList
0x1400024f5  nop     dword ptr [rax+rax+00h]
0x1400024fa  jmp     short loc_140002506
0x1400024fc  xor     edx, edx
0x1400024fe  mov     rcx, rbx; P
0x140002501  call    PgmDestroyAddress
0x140002506  test    rsi, rsi
0x140002509  jz      loc_1400023F1
0x14000250f  mov     rax, [rsi+0B8h]
0x140002516  xor     r8d, r8d
0x140002519  mov     rcx, rsi; Irp
0x14000251c  mov     rdx, [rax+30h]
0x140002520  mov     qword ptr [rdx+18h], 0
0x140002528  xor     edx, edx
0x14000252a  call    PgmIoComplete
0x14000252f  jmp     loc_1400023F1
0x140002534  mov     ecx, 3
0x140002539  int     29h; Win8: RtlFailFast(ecx)
```
