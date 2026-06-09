# InpMapPacketMdlComplete

- ea: `0x1400087a0`
- end: `0x140008870`
- name: `InpMapPacketMdlComplete`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140001170`
- `0x1400087a0`
- `0x140008964`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400087ff`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400087ff`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008846`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008846`

## pseudocode

```c
void __fastcall InpMapPacketMdlComplete(__int64 a1, int a2)
{
  __int64 v2; // rbx
  char v4; // di
  unsigned int v5; // ebp
  KIRQL v6; // dl

  v2 = *(_QWORD *)(a1 - 16);
  v4 = 1;
  if ( a2 < 0 )
  {
    *(_DWORD *)(v2 + 1400) = 5;
    v5 = 11;
    *(_DWORD *)(v2 + 1404) = 4;
  }
  else
  {
    InpPostProcessMappedMdl(
      *(_QWORD *)(a1 - 8),
      (__int64 *)(*(_QWORD *)(a1 - 8)
                + *(unsigned int *)(*(_QWORD *)(a1 - 8) + 56LL)
                + 8LL * *(unsigned int *)(*(_QWORD *)(a1 - 8) + 76LL)
                + 160),
      *(_DWORD *)(*(_QWORD *)(a1 - 8) + 76LL));
    v5 = 1;
  }
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v2 + 1088));
  if ( *(_DWORD *)(v2 + 1096) == 8 )
  {
    *(_DWORD *)(v2 + 1096) = 1;
    *(_QWORD *)(v2 + 1128) = KeGetCurrentThread();
  }
  else
  {
    *(_BYTE *)(v2 + 1120) |= 4u;
    if ( a2 < 0 )
      *(_BYTE *)(v2 + 1120) |= 8u;
    v4 = 0;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 1088), v6);
  if ( v4 )
    InpTransitionRunningQueue(v2, 0, v5);
}

```

## disassembly

```asm
0x1400087a0  push    rbx
0x1400087a2  push    rbp
0x1400087a3  push    rsi
0x1400087a4  push    rdi
0x1400087a5  push    r14
0x1400087a7  sub     rsp, 20h
0x1400087ab  mov     rbx, [rcx-10h]
0x1400087af  mov     esi, edx
0x1400087b1  mov     edi, 1
0x1400087b6  test    edx, edx
0x1400087b8  js      short loc_1400087DC
0x1400087ba  mov     rcx, [rcx-8]
0x1400087be  mov     edx, [rcx+38h]
0x1400087c1  mov     r8d, [rcx+4Ch]
0x1400087c5  add     rdx, rcx
0x1400087c8  lea     rdx, [rdx+r8*8]
0x1400087cc  add     rdx, 0A0h
0x1400087d3  call    InpPostProcessMappedMdl
0x1400087d8  mov     ebp, edi
0x1400087da  jmp     short loc_1400087F5
0x1400087dc  mov     dword ptr [rbx+578h], 5
0x1400087e6  mov     ebp, 0Bh
0x1400087eb  mov     dword ptr [rbx+57Ch], 4
0x1400087f5  lea     r14, [rbx+440h]
0x1400087fc  mov     rcx, r14; SpinLock
0x1400087ff  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140008806  nop     dword ptr [rax+rax+00h]
0x14000880b  cmp     dword ptr [rbx+448h], 8
0x140008812  mov     dl, al; NewIrql
0x140008814  jnz     short loc_14000882E
0x140008816  mov     [rbx+448h], edi
0x14000881c  mov     rcx, gs:188h
0x140008825  mov     [rbx+468h], rcx
0x14000882c  jmp     short loc_140008843
0x14000882e  or      byte ptr [rbx+460h], 4
0x140008835  test    esi, esi
0x140008837  jns     short loc_140008840
0x140008839  or      byte ptr [rbx+460h], 8
0x140008840  xor     dil, dil
0x140008843  mov     rcx, r14; SpinLock
0x140008846  call    cs:__imp_KeReleaseSpinLock
0x14000884d  nop     dword ptr [rax+rax+00h]
0x140008852  test    dil, dil
0x140008855  jz      short loc_140008864
0x140008857  mov     r8d, ebp
0x14000885a  xor     edx, edx
0x14000885c  mov     rcx, rbx
0x14000885f  call    InpTransitionRunningQueue
0x140008864  add     rsp, 20h
0x140008868  pop     r14
0x14000886a  pop     rdi
0x14000886b  pop     rsi
0x14000886c  pop     rbp
0x14000886d  pop     rbx
0x14000886e  retn
```
