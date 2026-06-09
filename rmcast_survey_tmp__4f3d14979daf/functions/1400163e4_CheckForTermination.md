# CheckForTermination

- ea: `0x1400163e4`
- end: `0x140016a6b`
- name: `CheckForTermination`
- size: `1671`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001a334`

## callees

- `0x140005038`
- `0x140005068`
- `0x1400050ac`
- `0x1400052e4`
- `0x1400067f4`
- `0x140007f1c`
- `0x140008868`
- `0x140008fb0`
- `0x1400163e4`
- `0x140017c80`
- `0x14001b740`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400167ef`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140016965`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400167ef`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140016965`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016654`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400167a9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016654`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400167a9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400166a6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400167d6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400166a6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400167d6`

## pseudocode

```c
char __fastcall CheckForTermination(__int64 a1, KIRQL *a2, __int64 a3)
{
  KIRQL *v3; // r14
  __int64 v5; // rcx
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rcx
  IRP *v10; // rsi
  _QWORD *v11; // rcx
  unsigned __int64 v12; // rax
  __int64 v13; // rcx
  KIRQL v14; // dl
  __int64 v15; // rax
  unsigned __int64 v16; // r8
  _QWORD *v17; // rdi
  __int64 v18; // rax
  KIRQL v19; // dl
  IRP *v20; // rcx
  KIRQL v21; // al
  struct _NPAGED_LOOKASIDE_LIST *v22; // rcx
  __int64 v23; // rcx
  int v24; // edx
  int v25; // eax
  _DWORD *v26; // r8
  void ***v27; // rdx
  int v28; // r9d
  __int64 v29; // rcx
  unsigned __int64 v30; // r8
  unsigned __int64 v31; // rax
  void **v32; // rcx
  void **v33; // rax
  _QWORD *v34; // r9
  _QWORD *v35; // rax
  PVOID Entry[7]; // [rsp+30h] [rbp-38h] BYREF

  v3 = a2;
  *(_OWORD *)Entry = 0;
  if ( !a1 || *(_DWORD *)(a1 + 16) != 844318035 )
  {
    v5 = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 32LL);
    if ( (!v5 || *(_DWORD *)(v5 + 16) != 843334721) && (*(_DWORD *)(a1 + 32) & 0x2000) == 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
        return 0;
      v7 = 74;
      goto LABEL_71;
    }
  }
  if ( (*(_DWORD *)(a1 + 32) & 0x1000) == 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_d(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x4Bu,
        (__int64)WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids,
        *(_DWORD *)(*(_QWORD *)(a1 + 40) + 188LL));
    v8 = *(_QWORD *)(a1 + 40);
    *(_DWORD *)(a1 + 32) |= 0x1000u;
    if ( *(_QWORD *)(v8 + 248) == v8 + 248 )
    {
      if ( !*(_DWORD *)(v8 + 144) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        {
          WPP_SF_(
            (__int64)WPP_GLOBAL_Control->AttachedDevice,
            0x4Eu,
            (__int64)WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids);
          v8 = *(_QWORD *)(a1 + 40);
        }
        if ( (*(_DWORD *)(a1 + 32) & 0x4000) != 0 || !*(_QWORD *)(a1 + 96) )
        {
          *(_DWORD *)(v8 + 196) &= ~0x40u;
          *(_DWORD *)(*(_QWORD *)(a1 + 40) + 196LL) |= 0x80u;
        }
        else
        {
          *(_DWORD *)(v8 + 196) &= ~0x80u;
          *(_DWORD *)(*(_QWORD *)(a1 + 40) + 196LL) |= 0x40u;
        }
        *(_QWORD *)(*(_QWORD *)(a1 + 40) + 368LL) = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 376LL);
        *(_DWORD *)(a1 + 32) |= 4u;
        return 0;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0x4Du,
          (__int64)WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids);
      v9 = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 240LL);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0x4Cu,
          (__int64)WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids);
      v9 = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 256LL);
    }
    *(_BYTE *)(v9 + 152) = 1;
    return 0;
  }
  v10 = *(IRP **)(a1 + 96);
  if ( v10 )
  {
    if ( (v11 = *(_QWORD **)(a1 + 40), (v12 = v11[39]) != 0) && v11[37] > v12
      || (_QWORD *)v11[31] == v11 + 31
      && (_QWORD *)v11[29] == v11 + 29
      && (LOBYTE(a3) = 1, !FindFirstEntry(a1, 0, a3))
      && (v13 = *(_QWORD *)(a1 + 40), *(_QWORD *)(v13 + 216) == v13 + 216)
      && (*(_DWORD *)(v13 + 196) & 0x1C0) != 0
      && (*(_BYTE *)(a1 + 32) & 4) == 0 )
    {
      v14 = *v3;
      *(_QWORD *)(a1 + 96) = 0;
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 360), v14);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 79, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids, v10);
      PgmIoComplete(v10, 0, 0);
      *v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 360));
      return 0;
    }
  }
  if ( *(_DWORD *)(a1 + 16) != 844318035 )
  {
    a2 = *(KIRQL **)(a1 + 40);
    v15 = *((_QWORD *)a2 + 4);
    if ( !v15 || *(_DWORD *)(v15 + 16) != 843334721 )
    {
      v16 = *((_QWORD *)a2 + 39);
      if ( !v16 || *((_QWORD *)a2 + 37) < v16 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        {
          WPP_SF_qii(
            WPP_GLOBAL_Control->AttachedDevice,
            a2,
            v16,
            a1,
            *((_QWORD *)a2 + 37),
            *((_QWORD *)a2 + 39),
            Entry[0],
            Entry[1]);
        }
        return 0;
      }
    }
  }
  LOBYTE(a2) = 1;
  RemoveAllEntries(a1, a2);
  Entry[1] = Entry;
  Entry[0] = Entry;
  PgmCancelAllSends(a1, (__int64)Entry, 0);
  while ( 1 )
  {
    v17 = Entry[0];
    if ( Entry[0] == Entry )
      break;
    if ( *((PVOID **)Entry[0] + 1) != Entry
      || (v18 = *(_QWORD *)Entry[0], *(PVOID *)(*(_QWORD *)Entry[0] + 8LL) != Entry[0]) )
    {
LABEL_79:
      __fastfail(3u);
    }
    v19 = *v3;
    Entry[0] = *(PVOID *)Entry[0];
    *(_QWORD *)(v18 + 8) = Entry;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 360), v19);
    v20 = (IRP *)v17[4];
    if ( v20 )
      PgmIoComplete(v20, -1073741536, 0);
    PgmDereferenceSessionCommon(a1);
    v21 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 360));
    v22 = (struct _NPAGED_LOOKASIDE_LIST *)(*(_QWORD *)(a1 + 40) + 576LL);
    *v3 = v21;
    ExFreeToNPagedLookasideList(v22, v17);
  }
  v23 = *(_QWORD *)(a1 + 40);
  v24 = *(_DWORD *)(a1 + 32);
  v25 = *(_DWORD *)(v23 + 196);
  if ( (v25 & 0x1C0) == 0 )
  {
    if ( (v24 & 0x4000) != 0 || !*(_QWORD *)(a1 + 96) )
    {
      *(_DWORD *)(v23 + 196) = v25 & 0xFFFFFFBF;
      *(_DWORD *)(*(_QWORD *)(a1 + 40) + 196LL) |= 0x80u;
    }
    else
    {
      *(_DWORD *)(v23 + 196) = v25 & 0xFFFFFF7F;
      *(_DWORD *)(*(_QWORD *)(a1 + 40) + 196LL) |= 0x40u;
    }
    *(_DWORD *)(a1 + 32) |= 4u;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
      return 0;
    v7 = 81;
LABEL_71:
    WPP_SF_q(v6->AttachedDevice, v7, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids, a1);
    return 0;
  }
  if ( (v24 & 4) != 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
      return 0;
    v7 = 82;
    goto LABEL_71;
  }
  while ( 1 )
  {
    v26 = *(_DWORD **)(a1 + 40);
    v27 = (void ***)*((_QWORD *)v26 + 27);
    if ( v27 == (void ***)(v26 + 54) )
      break;
    if ( *((_DWORD *)v27 + 34) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        WPP_SF_(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0x53u,
          (__int64)WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids);
      break;
    }
    v28 = *((_DWORD *)v27 + 23) - v26[40] + 1;
    v26[29] += v28;
    *(_QWORD *)(*(_QWORD *)(a1 + 40) + 120LL) += (unsigned int)(*(_DWORD *)(*(_QWORD *)(a1 + 40) + 108LL) * v28);
    *(_QWORD *)(*(_QWORD *)(a1 + 40) + 136LL) += (unsigned int)(*(_DWORD *)(*(_QWORD *)(a1 + 40) + 108LL) * v28);
    v29 = *(_QWORD *)(a1 + 40);
    v30 = *(_QWORD *)(v29 + 88);
    v31 = *(_QWORD *)(v29 + 136);
    if ( v31 >= v30 )
      *(_QWORD *)(v29 + 136) = v31 - v30;
    *(_DWORD *)(*(_QWORD *)(a1 + 40) + 160LL) += v28;
    v32 = *v27;
    if ( (*v27)[1] != v27 )
      goto LABEL_79;
    v33 = v27[1];
    if ( *v33 != v27 )
      goto LABEL_79;
    *v33 = v32;
    v32[1] = v33;
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(a1 + 40) + 576LL), v27);
  }
  if ( *(_QWORD *)(a1 + 96)
    || (v34 = *(_QWORD **)(a1 + 40), (_QWORD *)v34[27] != v34 + 27)
    || (_QWORD *)v34[31] != v34 + 31
    || (_QWORD *)v34[29] != v34 + 29
    || (v35 = (_QWORD *)v34[33], (_QWORD *)*v35 != v35) && *v35 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_Dd(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x54u,
        (__int64)WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids,
        *(_DWORD *)(*(_QWORD *)(a1 + 40) + 160LL),
        *(_DWORD *)(*(_QWORD *)(a1 + 40) + 152LL) - 1);
    return 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 85, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids, v34[37]);
  return 1;
}

```

## disassembly

```asm
0x1400163e4  push    rbx
0x1400163e6  push    rsi
0x1400163e7  push    rdi
0x1400163e8  push    r14
0x1400163ea  push    r15
0x1400163ec  sub     rsp, 40h
0x1400163f0  xorps   xmm0, xmm0
0x1400163f3  mov     r14, rdx
0x1400163f6  mov     rbx, rcx
0x1400163f9  mov     edi, 32534553h
0x1400163fe  mov     r15d, 32444441h
0x140016404  movups  xmmword ptr [rsp+68h+Entry], xmm0
0x140016409  test    rcx, rcx
0x14001640c  jz      short loc_140016413
0x14001640e  cmp     [rcx+10h], edi
0x140016411  jz      short loc_14001645B
0x140016413  mov     rax, [rcx+28h]
0x140016417  mov     rcx, [rax+20h]
0x14001641b  test    rcx, rcx
0x14001641e  jz      short loc_140016426
0x140016420  cmp     [rcx+10h], r15d
0x140016424  jz      short loc_14001645B
0x140016426  test    dword ptr [rbx+20h], 2000h
0x14001642d  jnz     short loc_14001645B
0x14001642f  mov     rcx, cs:WPP_GLOBAL_Control
0x140016436  lea     rdi, WPP_GLOBAL_Control
0x14001643d  cmp     rcx, rdi
0x140016440  jz      loc_140016A5C
0x140016446  mov     eax, [rcx+2Ch]
0x140016449  test    al, 10h
0x14001644b  jz      loc_140016A5C
0x140016451  mov     edx, 4Ah ; 'J'
0x140016456  jmp     loc_1400168A6
0x14001645b  mov     esi, 1000h
0x140016460  test    [rbx+20h], esi
0x140016463  jnz     loc_1400165BA
0x140016469  mov     rcx, cs:WPP_GLOBAL_Control
0x140016470  lea     rdi, WPP_GLOBAL_Control
0x140016477  cmp     rcx, rdi
0x14001647a  jz      short loc_1400164A3
0x14001647c  mov     eax, [rcx+2Ch]
0x14001647f  test    al, 4
0x140016481  jz      short loc_1400164A3
0x140016483  mov     r9, [rbx+28h]
0x140016487  lea     r8, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids
0x14001648e  mov     rcx, [rcx+18h]
0x140016492  mov     edx, 4Bh ; 'K'
0x140016497  mov     r9d, [r9+0BCh]
0x14001649e  call    WPP_SF_d
0x1400164a3  mov     rcx, [rbx+28h]
0x1400164a7  or      [rbx+20h], esi
0x1400164aa  lea     rax, [rcx+0F8h]
0x1400164b1  cmp     [rax], rax
0x1400164b4  jnz     loc_140016582
0x1400164ba  cmp     dword ptr [rcx+90h], 0
0x1400164c1  jz      short loc_140016502
0x1400164c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400164ca  cmp     rcx, rdi
0x1400164cd  jz      short loc_1400164EB
0x1400164cf  mov     eax, [rcx+2Ch]
0x1400164d2  test    al, 4
0x1400164d4  jz      short loc_1400164EB
0x1400164d6  mov     rcx, [rcx+18h]
0x1400164da  lea     r8, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids
0x1400164e1  mov     edx, 4Dh ; 'M'
0x1400164e6  call    WPP_SF_
0x1400164eb  mov     rax, [rbx+28h]
0x1400164ef  mov     rcx, [rax+0F0h]
0x1400164f6  mov     byte ptr [rcx+98h], 1
0x1400164fd  jmp     loc_140016A5C
0x140016502  mov     r9, cs:WPP_GLOBAL_Control
0x140016509  cmp     r9, rdi
0x14001650c  jz      short loc_14001652F
0x14001650e  mov     eax, [r9+2Ch]
0x140016512  test    al, 4
0x140016514  jz      short loc_14001652F
0x140016516  mov     rcx, [r9+18h]
0x14001651a  lea     r8, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids
0x140016521  mov     edx, 4Eh ; 'N'
0x140016526  call    WPP_SF_
0x14001652b  mov     rcx, [rbx+28h]
0x14001652f  test    dword ptr [rbx+20h], 4000h
0x140016536  jnz     short loc_140016554
0x140016538  cmp     qword ptr [rbx+60h], 0
0x14001653d  jz      short loc_140016554
0x14001653f  btr     dword ptr [rcx+0C4h], 7
0x140016547  mov     rax, [rbx+28h]
0x14001654b  or      dword ptr [rax+0C4h], 40h
0x140016552  jmp     short loc_140016567
0x140016554  and     dword ptr [rcx+0C4h], 0FFFFFFBFh
0x14001655b  mov     rax, [rbx+28h]
0x14001655f  bts     dword ptr [rax+0C4h], 7
0x140016567  mov     rcx, [rbx+28h]
0x14001656b  mov     rax, [rcx+178h]
0x140016572  mov     [rcx+170h], rax
0x140016579  or      dword ptr [rbx+20h], 4
0x14001657d  jmp     loc_140016A5C
0x140016582  mov     rcx, cs:WPP_GLOBAL_Control
0x140016589  cmp     rcx, rdi
0x14001658c  jz      short loc_1400165AA
0x14001658e  mov     eax, [rcx+2Ch]
0x140016591  test    al, 4
0x140016593  jz      short loc_1400165AA
0x140016595  mov     rcx, [rcx+18h]
0x140016599  lea     r8, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids
0x1400165a0  mov     edx, 4Ch ; 'L'
0x1400165a5  call    WPP_SF_
0x1400165aa  mov     rax, [rbx+28h]
0x1400165ae  mov     rcx, [rax+100h]
0x1400165b5  jmp     loc_1400164F6
0x1400165ba  mov     rsi, [rbx+60h]
0x1400165be  test    rsi, rsi
0x1400165c1  jz      loc_1400166BA
0x1400165c7  mov     rcx, [rbx+28h]
0x1400165cb  mov     rax, [rcx+138h]
0x1400165d2  test    rax, rax
0x1400165d5  jz      short loc_1400165E0
0x1400165d7  cmp     [rcx+128h], rax
0x1400165de  ja      short loc_140016642
0x1400165e0  lea     rax, [rcx+0F8h]
0x1400165e7  cmp     [rax], rax
0x1400165ea  jnz     loc_1400166BA
0x1400165f0  lea     rax, [rcx+0E8h]
0x1400165f7  cmp     [rax], rax
0x1400165fa  jnz     loc_1400166BA
0x140016600  mov     r8b, 1
0x140016603  xor     edx, edx
0x140016605  mov     rcx, rbx
0x140016608  call    FindFirstEntry
0x14001660d  test    rax, rax
0x140016610  jnz     loc_1400166BA
0x140016616  mov     rcx, [rbx+28h]
0x14001661a  lea     rax, [rcx+0D8h]
0x140016621  cmp     [rax], rax
0x140016624  jnz     loc_1400166BA
0x14001662a  test    dword ptr [rcx+0C4h], 1C0h
0x140016634  setnz   cl
0x140016637  test    byte ptr [rbx+20h], 4
0x14001663b  setz    al
0x14001663e  test    al, cl
0x140016640  jz      short loc_1400166BA
0x140016642  mov     dl, [r14]; NewIrql
0x140016645  lea     rcx, [rbx+168h]; SpinLock
0x14001664c  mov     qword ptr [rbx+60h], 0
0x140016654  call    cs:__imp_KeReleaseSpinLock
0x14001665b  nop     dword ptr [rax+rax+00h]
0x140016660  mov     rcx, cs:WPP_GLOBAL_Control
0x140016667  lea     rdi, WPP_GLOBAL_Control
0x14001666e  cmp     rcx, rdi
0x140016671  jz      short loc_140016692
0x140016673  mov     eax, [rcx+2Ch]
0x140016676  test    al, 4
0x140016678  jz      short loc_140016692
0x14001667a  mov     rcx, [rcx+18h]
0x14001667e  lea     r8, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids
0x140016685  mov     edx, 4Fh ; 'O'
0x14001668a  mov     r9, rsi
0x14001668d  call    WPP_SF_q
0x140016692  xor     r8d, r8d
0x140016695  xor     edx, edx
0x140016697  mov     rcx, rsi; Irp
0x14001669a  call    PgmIoComplete
0x14001669f  lea     rcx, [rbx+168h]; SpinLock
0x1400166a6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400166ad  nop     dword ptr [rax+rax+00h]
0x1400166b2  mov     [r14], al
0x1400166b5  jmp     loc_140016A5C
0x1400166ba  cmp     [rbx+10h], edi
0x1400166bd  jz      short loc_14001672B
0x1400166bf  mov     rdx, [rbx+28h]
0x1400166c3  mov     rax, [rdx+20h]
0x1400166c7  test    rax, rax
0x1400166ca  jz      short loc_1400166D2
0x1400166cc  cmp     [rax+10h], r15d
0x1400166d0  jz      short loc_14001672B
0x1400166d2  mov     r8, [rdx+138h]
0x1400166d9  test    r8, r8
0x1400166dc  jz      short loc_1400166E7
0x1400166de  cmp     [rdx+128h], r8
0x1400166e5  jnb     short loc_14001672B
0x1400166e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400166ee  lea     rdi, WPP_GLOBAL_Control
0x1400166f5  cmp     rcx, rdi
0x1400166f8  jz      loc_140016A5C
0x1400166fe  mov     eax, [rcx+2Ch]
0x140016701  test    al, 10h
0x140016703  jz      loc_140016A5C
0x140016709  mov     rax, [rdx+128h]
0x140016710  mov     r9, rbx
0x140016713  mov     rcx, [rcx+18h]
0x140016717  mov     [rsp+68h+var_40], r8
0x14001671c  mov     [rsp+68h+var_48], rax
0x140016721  call    WPP_SF_qii
0x140016726  jmp     loc_140016A5C
0x14001672b  mov     dl, 1
0x14001672d  mov     rcx, rbx
0x140016730  call    RemoveAllEntries
0x140016735  lea     rax, [rsp+68h+Entry]
0x14001673a  xor     r8d, r8d
0x14001673d  mov     [rsp+68h+Entry+8], rax
0x140016742  lea     rdx, [rsp+68h+Entry]
0x140016747  lea     rax, [rsp+68h+Entry]
0x14001674c  mov     rcx, rbx
0x14001674f  mov     [rsp+68h+Entry], rax
0x140016754  call    PgmCancelAllSends
0x140016759  mov     r15d, 240h
0x14001675f  mov     rdi, [rsp+68h+Entry]
0x140016764  lea     rax, [rsp+68h+Entry]
0x140016769  cmp     rdi, rax
0x14001676c  jz      loc_140016800
0x140016772  lea     rax, [rsp+68h+Entry]
0x140016777  cmp     [rdi+8], rax
0x14001677b  jnz     loc_140016976
0x140016781  mov     rax, [rdi]
0x140016784  cmp     [rax+8], rdi
0x140016788  jnz     loc_140016976
0x14001678e  mov     dl, [r14]; NewIrql
0x140016791  lea     rcx, [rsp+68h+Entry]
0x140016796  mov     [rsp+68h+Entry], rax
0x14001679b  lea     rsi, [rbx+168h]
0x1400167a2  mov     [rax+8], rcx
0x1400167a6  mov     rcx, rsi; SpinLock
0x1400167a9  call    cs:__imp_KeReleaseSpinLock
0x1400167b0  nop     dword ptr [rax+rax+00h]
0x1400167b5  mov     rcx, [rdi+20h]; Irp
0x1400167b9  test    rcx, rcx
0x1400167bc  jz      short loc_1400167CB
0x1400167be  xor     r8d, r8d
0x1400167c1  mov     edx, 0C0000120h
0x1400167c6  call    PgmIoComplete
0x1400167cb  mov     rcx, rbx
0x1400167ce  call    PgmDereferenceSessionCommon
0x1400167d3  mov     rcx, rsi; SpinLock
0x1400167d6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400167dd  nop     dword ptr [rax+rax+00h]
0x1400167e2  mov     rcx, [rbx+28h]
0x1400167e6  mov     rdx, rdi; Entry
0x1400167e9  add     rcx, r15; Lookaside
0x1400167ec  mov     [r14], al
0x1400167ef  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400167f6  nop     dword ptr [rax+rax+00h]
0x1400167fb  jmp     loc_14001675F
0x140016800  mov     rcx, [rbx+28h]
0x140016804  mov     edx, [rbx+20h]
0x140016807  mov     eax, [rcx+0C4h]
0x14001680d  test    eax, 1C0h
0x140016812  jnz     short loc_14001687A
0x140016814  bt      edx, 0Eh
0x140016818  jb      short loc_140016838
0x14001681a  cmp     qword ptr [rbx+60h], 0
0x14001681f  jz      short loc_140016838
0x140016821  btr     eax, 7
0x140016825  mov     [rcx+0C4h], eax
0x14001682b  mov     rax, [rbx+28h]
0x14001682f  or      dword ptr [rax+0C4h], 40h
0x140016836  jmp     short loc_14001684D
0x140016838  and     eax, 0FFFFFFBFh
0x14001683b  mov     [rcx+0C4h], eax
0x140016841  mov     rax, [rbx+28h]
0x140016845  bts     dword ptr [rax+0C4h], 7
0x14001684d  or      dword ptr [rbx+20h], 4
0x140016851  mov     rcx, cs:WPP_GLOBAL_Control
0x140016858  lea     rdi, WPP_GLOBAL_Control
0x14001685f  cmp     rcx, rdi
0x140016862  jz      loc_140016A5C
0x140016868  mov     eax, [rcx+2Ch]
0x14001686b  test    al, 10h
0x14001686d  jz      loc_140016A5C
0x140016873  mov     edx, 51h ; 'Q'
0x140016878  jmp     short loc_1400168A6
0x14001687a  test    dl, 4
0x14001687d  jz      short loc_1400168BE
0x14001687f  mov     rcx, cs:WPP_GLOBAL_Control
0x140016886  lea     rdi, WPP_GLOBAL_Control
0x14001688d  cmp     rcx, rdi
0x140016890  jz      loc_140016A5C
0x140016896  mov     eax, [rcx+2Ch]
0x140016899  test    al, 10h
0x14001689b  jz      loc_140016A5C
0x1400168a1  mov     edx, 52h ; 'R'
0x1400168a6  mov     rcx, [rcx+18h]
0x1400168aa  lea     r8, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids
0x1400168b1  mov     r9, rbx
0x1400168b4  call    WPP_SF_q
0x1400168b9  jmp     loc_140016A5C
0x1400168be  mov     r8, [rbx+28h]
0x1400168c2  lea     rdi, WPP_GLOBAL_Control
0x1400168c9  lea     rax, [r8+0D8h]
0x1400168d0  mov     rdx, [rax]; Entry
0x1400168d3  cmp     rdx, rax
0x1400168d6  jz      loc_1400169A5
0x1400168dc  cmp     dword ptr [rdx+88h], 0
0x1400168e3  jnz     loc_14001697D
0x1400168e9  mov     r9d, [rdx+5Ch]
0x1400168ed  sub     r9d, [r8+0A0h]
0x1400168f4  inc     r9d
0x1400168f7  add     [r8+74h], r9d
0x1400168fb  mov     eax, r9d
0x1400168fe  mov     rcx, [rbx+28h]
0x140016902  imul    eax, [rcx+6Ch]
  ... truncated ...
```
