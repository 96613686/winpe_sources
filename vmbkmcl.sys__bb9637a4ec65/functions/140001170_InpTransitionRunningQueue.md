# InpTransitionRunningQueue

- ea: `0x140001170`
- end: `0x140001363`
- name: `InpTransitionRunningQueue`
- size: `499`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140007800`
- `0x1400087a0`
- `0x140008ac0`

## callees

- `0x140001170`
- `0x140002170`
- `0x140002190`
- `0x140005cf0`
- `0x14000862c`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140001312`
- `ntoskrnl!KeSetEvent` at `0x14000134b`
- `ntoskrnl!KeSetEvent` at `0x140001312`
- `ntoskrnl!KeSetEvent` at `0x14000134b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001195`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001195`

## pseudocode

```c
void __fastcall InpTransitionRunningQueue(__int64 a1, char a2, int a3)
{
  int v6; // edi
  KIRQL v7; // bp
  __int64 v8; // rcx
  bool v9; // zf
  char v10; // al
  struct _KEVENT *v11; // rcx
  signed __int32 v12[22]; // [rsp+0h] [rbp-58h] BYREF

  v6 = 1;
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 1088));
  if ( a3 != 4 )
  {
    switch ( a3 )
    {
      case 1:
        *(_BYTE *)(a1 + 1120) = 0;
        goto LABEL_7;
      case 5:
      case 6:
        v9 = (*(_BYTE *)(a1 + 1120) & 2) == 0;
        goto LABEL_19;
      case 7:
        v9 = (*(_BYTE *)(a1 + 1120) & 1) == 0;
LABEL_19:
        if ( v9 )
          goto LABEL_9;
        break;
      case 8:
        v10 = *(_BYTE *)(a1 + 1120);
        if ( (v10 & 4) == 0 )
          goto LABEL_9;
        if ( (v10 & 8) != 0 )
        {
          v6 = 11;
          *(_DWORD *)(a1 + 1400) = 5;
          *(_DWORD *)(a1 + 1404) = 3;
        }
        break;
      case 11:
        goto LABEL_9;
      default:
        __fastfail(5u);
    }
LABEL_10:
    *(_BYTE *)(a1 + 1120) = 0;
    if ( v6 != 1 )
      goto LABEL_11;
    goto LABEL_7;
  }
  if ( *(_BYTE *)(a1 + 1204) || !PkIsIncomingRingEmpty(a1 + 64) )
    goto LABEL_10;
  if ( (unsigned int)(*(_DWORD *)(a1 + 1160) + *(_DWORD *)(a1 + 1320)) >= *(_DWORD *)(a1 + 1324)
    || (*(_DWORD *)(*(_QWORD *)(a1 + 88) + 8LL) = 0, _InterlockedOr(v12, 0), PkIsIncomingRingEmpty(v8)) )
  {
LABEL_9:
    v6 = a3;
    goto LABEL_10;
  }
  *(_DWORD *)(*(_QWORD *)(a1 + 88) + 8LL) = 1;
  *(_BYTE *)(a1 + 1120) = 0;
LABEL_7:
  if ( !*(_BYTE *)(a1 + 1204) )
  {
    InpPrepareToQueueWorkerLocked(a1, 0, a2);
    goto LABEL_15;
  }
LABEL_11:
  if ( *(_QWORD *)(a1 + 1216) && (v6 != 8 || (unsigned __int8)InpCancelMdlMapLocked(a1)) )
  {
    KeSetEvent(*(PRKEVENT *)(a1 + 1216), 0, 0);
    *(_QWORD *)(a1 + 1216) = 0;
  }
  else
  {
    if ( *(_BYTE *)(a1 + 1204) )
    {
      if ( v6 != 8 && v6 != 11 )
        v6 = 3;
      v11 = *(struct _KEVENT **)(a1 + 1208);
      if ( v11 )
      {
        KeSetEvent(v11, 0, 0);
        *(_QWORD *)(a1 + 1208) = 0;
      }
    }
    *(_DWORD *)(a1 + 1096) = v6;
  }
  *(_QWORD *)(a1 + 1128) = 0;
LABEL_15:
  InpReleaseLockAndPerformWork((KSPIN_LOCK *)a1, v7);
}

```

## disassembly

```asm
0x140001170  push    rbx
0x140001172  push    rbp
0x140001173  push    rsi
0x140001174  push    rdi
0x140001175  push    r12
0x140001177  push    r14
0x140001179  push    r15
0x14000117b  sub     rsp, 20h
0x14000117f  mov     rbx, rcx
0x140001182  mov     r15d, r8d
0x140001185  add     rcx, 440h; SpinLock
0x14000118c  movzx   r12d, dl
0x140001190  mov     edi, 1
0x140001195  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000119c  nop     dword ptr [rax+rax+00h]
0x1400011a1  xor     esi, esi
0x1400011a3  mov     r14d, 3
0x1400011a9  movzx   ebp, al
0x1400011ac  cmp     r15d, 4
0x1400011b0  jnz     loc_14000126E
0x1400011b6  cmp     [rbx+4B4h], sil
0x1400011bd  jnz     short loc_14000121E
0x1400011bf  lea     rcx, [rbx+40h]
0x1400011c3  call    PkIsIncomingRingEmpty
0x1400011c8  test    al, al
0x1400011ca  jz      short loc_14000121E
0x1400011cc  mov     eax, [rbx+528h]
0x1400011d2  add     eax, [rbx+488h]
0x1400011d8  cmp     eax, [rbx+52Ch]
0x1400011de  jnb     short loc_14000121B; jumptable 000000014000128B case 11
0x1400011e0  mov     rax, [rbx+58h]
0x1400011e4  mov     [rax+8], esi
0x1400011e7  lock or [rsp+58h+var_58], esi
0x1400011eb  call    PkIsIncomingRingEmpty
0x1400011f0  test    al, al
0x1400011f2  jnz     short loc_14000121B; jumptable 000000014000128B case 11
0x1400011f4  mov     rax, [rbx+58h]
0x1400011f8  mov     [rax+8], edi
0x1400011fb  mov     [rbx+460h], sil
0x140001202  cmp     byte ptr [rbx+4B4h], 0
0x140001209  jnz     short loc_14000122A
0x14000120b  movzx   r8d, r12b
0x14000120f  xor     edx, edx
0x140001211  mov     rcx, rbx
0x140001214  call    InpPrepareToQueueWorkerLocked
0x140001219  jmp     short loc_140001252
0x14000121b  mov     edi, r15d; jumptable 000000014000128B case 11
0x14000121e  mov     [rbx+460h], sil
0x140001225  cmp     edi, 1
0x140001228  jz      short loc_140001202
0x14000122a  cmp     qword ptr [rbx+4C0h], 0
0x140001232  jnz     loc_1400012F1
0x140001238  cmp     byte ptr [rbx+4B4h], 0
0x14000123f  jnz     loc_14000132A
0x140001245  mov     [rbx+448h], edi
0x14000124b  mov     [rbx+468h], rsi
0x140001252  movzx   edx, bpl
0x140001256  mov     rcx, rbx
0x140001259  call    InpReleaseLockAndPerformWork
0x14000125e  add     rsp, 20h
0x140001262  pop     r15
0x140001264  pop     r14
0x140001266  pop     r12
0x140001268  pop     rdi
0x140001269  pop     rsi
0x14000126a  pop     rbp
0x14000126b  pop     rbx
0x14000126c  retn
0x14000126e  lea     eax, [r15-1]; switch 11 cases
0x140001272  cmp     eax, 0Ah
0x140001275  ja      short def_14000128B; jumptable 000000014000128B default case, cases 2-4,9,10
0x140001277  movsxd  rcx, eax
0x14000127a  lea     rdx, cs:140000000h
0x140001281  mov     eax, ds:(jpt_14000128B - 140000000h)[rdx+rcx*4]
0x140001288  add     rax, rdx
0x14000128b  jmp     rax; switch jump
0x140001291  mov     [rbx+460h], sil; jumptable 000000014000128B case 1
0x140001298  jmp     loc_140001202
0x14000129d  test    byte ptr [rbx+460h], 2; jumptable 000000014000128B cases 5,6
0x1400012a4  jnz     loc_14000121E
0x1400012aa  jmp     loc_14000121B; jumptable 000000014000128B case 11
0x1400012af  test    [rbx+460h], dil; jumptable 000000014000128B case 7
0x1400012b6  jmp     short loc_1400012A4
0x1400012b8  movzx   eax, byte ptr [rbx+460h]; jumptable 000000014000128B case 8
0x1400012bf  test    al, 4
0x1400012c1  jz      loc_14000121B; jumptable 000000014000128B case 11
0x1400012c7  test    al, 8
0x1400012c9  jz      loc_14000121E
0x1400012cf  mov     edi, 0Bh
0x1400012d4  mov     dword ptr [rbx+578h], 5
0x1400012de  mov     [rbx+57Ch], r14d
0x1400012e5  jmp     loc_14000121E
0x1400012ea  mov     ecx, 5; jumptable 000000014000128B default case, cases 2-4,9,10
0x1400012ef  int     29h; Win8: RtlFailFast(ecx)
0x1400012f1  cmp     edi, 8
0x1400012f4  jnz     short loc_140001306
0x1400012f6  mov     rcx, rbx
0x1400012f9  call    InpCancelMdlMapLocked
0x1400012fe  test    al, al
0x140001300  jz      loc_140001238
0x140001306  mov     rcx, [rbx+4C0h]; Event
0x14000130d  xor     r8d, r8d; Wait
0x140001310  xor     edx, edx; Increment
0x140001312  call    cs:__imp_KeSetEvent
0x140001319  nop     dword ptr [rax+rax+00h]
0x14000131e  mov     [rbx+4C0h], rsi
0x140001325  jmp     loc_14000124B
0x14000132a  cmp     edi, 8
0x14000132d  jz      short loc_140001336
0x14000132f  cmp     edi, 0Bh
0x140001332  cmovnz  edi, r14d
0x140001336  mov     rcx, [rbx+4B8h]; Event
0x14000133d  test    rcx, rcx
0x140001340  jz      loc_140001245
0x140001346  xor     r8d, r8d; Wait
0x140001349  xor     edx, edx; Increment
0x14000134b  call    cs:__imp_KeSetEvent
0x140001352  nop     dword ptr [rax+rax+00h]
0x140001357  mov     [rbx+4B8h], rsi
0x14000135e  jmp     loc_140001245
```
