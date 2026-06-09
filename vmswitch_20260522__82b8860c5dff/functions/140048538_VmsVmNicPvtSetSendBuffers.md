# VmsVmNicPvtSetSendBuffers

- ea: `0x140048538`
- end: `0x140048c03`
- name: `VmsVmNicPvtSetSendBuffers`
- size: `1739`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14019c458`
- `0x14019ebc0`

## callees

- `0x140027a64`
- `0x14003a450`
- `0x14003e804`
- `0x140048538`
- `0x14004a1b4`
- `0x140051528`
- `0x14006a330`
- `0x14006b084`
- `0x14008497c`
- `0x1400a0ef8`
- `0x140198764`
- `0x1401a28b8`
- `0x1401bc2c0`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140048900`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140048910`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140048900`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140048910`
- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x14004870e`
- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x14004870e`
- `ntoskrnl!MmFreePagesFromMdl` at `0x140048bbc`
- `ntoskrnl!MmFreePagesFromMdl` at `0x140048bbc`
- `ntoskrnl!IoFreeMdl` at `0x140048b26`
- `ntoskrnl!IoFreeMdl` at `0x140048b43`
- `ntoskrnl!IoFreeMdl` at `0x140048b26`
- `ntoskrnl!IoFreeMdl` at `0x140048b43`
- `ntoskrnl!IoAllocateMdl` at `0x1400488b3`
- `ntoskrnl!IoAllocateMdl` at `0x1400488e7`
- `ntoskrnl!IoAllocateMdl` at `0x1400488b3`
- `ntoskrnl!IoAllocateMdl` at `0x1400488e7`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140048679`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004878a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140048679`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004878a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048b6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048b8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048bcd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048b6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048b8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048bcd`
- `ntoskrnl!ExAllocatePool2` at `0x1400487f8`
- `ntoskrnl!ExAllocatePool2` at `0x140048865`
- `ntoskrnl!ExAllocatePool2` at `0x1400487f8`
- `ntoskrnl!ExAllocatePool2` at `0x140048865`
- `NDIS!NdisReleaseRWLock` at `0x140048a2b`
- `NDIS!NdisReleaseRWLock` at `0x140048a2b`
- `vmbkmclr!VmbChannelUnmapGpadl` at `0x140048ba8`
- `vmbkmclr!VmbChannelUnmapGpadl` at `0x140048ba8`
- `vmbkmclr!VmbChannelMapGpadl` at `0x1400485d2`
- `vmbkmclr!VmbChannelMapGpadl` at `0x1400485d2`

## pseudocode

```c
__int64 __fastcall VmsVmNicPvtSetSendBuffers(__int64 a1, unsigned int a2, ULONG a3)
{
  __int64 *v5; // rdx
  struct _MDL *v7; // r15
  _QWORD *v8; // rdi
  char *v9; // r12
  _QWORD *v10; // r14
  __int64 v11; // rbp
  unsigned int v12; // ebx
  int v13; // edx
  int v14; // r8d
  int v15; // eax
  int v16; // edx
  int v17; // r8d
  int v18; // r9d
  char v19; // cl
  SIZE_T ByteCount; // rbp
  char *MappedSystemVa; // rax
  unsigned int v22; // eax
  unsigned int v23; // eax
  __int64 v24; // rbx
  PMDL PagesForMdl; // rax
  int v26; // edx
  int v27; // r8d
  char *v28; // rax
  size_t v29; // rbx
  _QWORD *Pool2; // rax
  int v31; // edx
  int v32; // r8d
  __int64 i; // rbp
  PMDL Mdl; // rax
  int v35; // edx
  int v36; // r8d
  PMDL v37; // rax
  int v38; // edx
  int v39; // r8d
  __int64 v40; // rcx
  PVOID v41; // rax
  int WorkItem; // eax
  int v43; // edx
  unsigned int v44; // esi
  int v45; // edx
  __int64 v46; // rsi
  struct _MDL *v47; // rcx
  struct _MDL *v48; // rcx
  char v50; // [rsp+38h] [rbp-80h]
  PMDL MemoryDescriptorList; // [rsp+50h] [rbp-68h] BYREF
  PVOID P; // [rsp+58h] [rbp-60h]
  char *v53; // [rsp+60h] [rbp-58h]
  char *v54; // [rsp+68h] [rbp-50h]
  __int64 v55; // [rsp+70h] [rbp-48h]
  struct _LOCK_STATE_EX LockState; // [rsp+C0h] [rbp+8h] BYREF
  unsigned int v57; // [rsp+C8h] [rbp+10h]
  unsigned int v58; // [rsp+D8h] [rbp+20h]

  v57 = a2;
  v5 = WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v7 = 0;
  v8 = (_QWORD *)(a1 + 16);
  v9 = 0;
  v10 = 0;
  MemoryDescriptorList = 0;
  LODWORD(v11) = 0;
  v58 = 0;
  P = 0;
  if ( *(_QWORD *)(a1 + 296) )
  {
    v12 = -1073741808;
    LOBYTE(v5) = 2;
    WPP_RECORDER_SF_d(VmsIfrNicLog, (_DWORD)v5, 20, 240, (__int64)WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids, 16);
    goto LABEL_36;
  }
  v15 = VmbChannelMapGpadl(*v8, 1, a2, &MemoryDescriptorList);
  v12 = v15;
  if ( v15 < 0 )
  {
    WPP_RECORDER_SF_qLd(
      VmsIfrNicLog,
      v16,
      v17,
      241,
      (__int64)WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids,
      *v8,
      v57,
      v15);
    goto LABEL_36;
  }
  v19 = (char)MemoryDescriptorList;
  ByteCount = MemoryDescriptorList->ByteCount;
  if ( (unsigned int)ByteCount > VmsVmNicMaxSendBufferSizeInBytes )
  {
    v12 = -1073741306;
    WPP_RECORDER_SF_qLLLd((_DWORD)MemoryDescriptorList, v16, v17, v18);
LABEL_7:
    LODWORD(v11) = 0;
    goto LABEL_36;
  }
  if ( (MemoryDescriptorList->MdlFlags & 5) != 0 )
  {
    MappedSystemVa = (char *)MemoryDescriptorList->MappedSystemVa;
  }
  else
  {
    MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(MemoryDescriptorList, 0, MmCached, 0, 0, 0x40000000u);
    v19 = (char)MemoryDescriptorList;
  }
  v54 = MappedSystemVa;
  if ( !MappedSystemVa )
  {
    v12 = -1073741670;
    LOBYTE(v16) = 2;
    WPP_RECORDER_SF_qDd(
      VmsIfrNicLog,
      v16,
      20,
      243,
      (__int64)WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids,
      v19,
      0,
      154);
    goto LABEL_7;
  }
  v22 = 6144;
  if ( a3 )
    v22 = a3;
  a3 = v22;
  v23 = (unsigned int)ByteCount / v22;
  v24 = v23;
  v58 = v23;
  PagesForMdl = MmAllocatePagesForMdlEx(0, (PHYSICAL_ADDRESS)-1LL, 0, ByteCount, MmCached, 5u);
  v7 = PagesForMdl;
  if ( !PagesForMdl )
  {
    v12 = -1073741670;
    WPP_RECORDER_SF_qLd(
      VmsIfrNicLog,
      v26,
      v27,
      244,
      (__int64)WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids,
      (char)MemoryDescriptorList,
      ByteCount,
      154);
LABEL_17:
    LODWORD(v11) = v58;
    goto LABEL_36;
  }
  if ( (PagesForMdl->MdlFlags & 5) != 0 )
    v28 = (char *)PagesForMdl->MappedSystemVa;
  else
    v28 = (char *)MmMapLockedPagesSpecifyCache(PagesForMdl, 0, MmCached, 0, 0, 0x40000000u);
  v53 = v28;
  if ( !v28 )
  {
    v12 = -1073741670;
    LOBYTE(v26) = 2;
    WPP_RECORDER_SF_qDd(
      VmsIfrNicLog,
      v26,
      20,
      245,
      (__int64)WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids,
      (char)v7,
      0,
      154);
    goto LABEL_17;
  }
  v11 = v24;
  v29 = 16 * v24;
  Pool2 = (_QWORD *)ExAllocatePool2(64, v29, 1314288470);
  v10 = Pool2;
  if ( Pool2 )
  {
    memset(Pool2, 0, v29);
    v9 = (char *)&v10[v11];
    P = (PVOID)ExAllocatePool2(64, 8 * v11, 1314288470);
    if ( P )
    {
      for ( i = 0; (unsigned int)i < v58; i = (unsigned int)(i + 1) )
      {
        v55 = (unsigned int)i * a3;
        Mdl = IoAllocateMdl(&v54[v55], a3, 0, 0, 0);
        v10[i] = Mdl;
        if ( !Mdl )
        {
          v12 = -1073741670;
          WPP_RECORDER_SF_qLd(
            VmsIfrNicLog,
            v35,
            v36,
            247,
            (__int64)WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids,
            (char)v10,
            i,
            154);
          goto LABEL_17;
        }
        v37 = IoAllocateMdl(&v53[v55], a3, 0, 0, 0);
        *(_QWORD *)&v9[8 * i] = v37;
        if ( !v37 )
        {
          v12 = -1073741670;
          WPP_RECORDER_SF_qLd(
            VmsIfrNicLog,
            v38,
            v39,
            248,
            (__int64)WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids,
            (char)v9,
            i,
            154);
          goto LABEL_17;
        }
        MmBuildMdlForNonPagedPool((PMDL)v10[i]);
        MmBuildMdlForNonPagedPool(*(PMDL *)&v9[8 * i]);
        *(_QWORD *)v10[i] = 0;
        **(_QWORD **)&v9[8 * i] = 0;
        *((_QWORD *)P + i) = 0;
      }
      VmsOmObjectLockExclusive(*(_QWORD *)(a1 + 680), &LockState, 0);
      v40 = *(_QWORD *)(a1 + 680);
      LODWORD(v11) = v58;
      *(_DWORD *)(a1 + 548) = v57;
      v41 = P;
      *(_DWORD *)(a1 + 576) = a3;
      *(_QWORD *)(a1 + 296) = v10;
      *(_DWORD *)(a1 + 304) = v11;
      *(_QWORD *)(a1 + 1448) = v41;
      *(_QWORD *)(a1 + 320) = v53;
      *(_QWORD *)(a1 + 312) = v7;
      *(_QWORD *)(a1 + 328) = v9;
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v40 + 56), &LockState);
      WorkItem = NvIoAllocateWorkItem(
                   *(PNPAGED_LOOKASIDE_LIST *)(*(_QWORD *)(a1 + 680) + 2096LL),
                   0,
                   (__int64)VmsVmNicPvtRevokeSendBufferWorkItem,
                   (void *(__fastcall *)(_POOL_TYPE, unsigned __int64, unsigned int, _LOOKASIDE_LIST_EX *))a1,
                   10,
                   (volatile __int64 *)(a1 + 1520));
      v12 = WorkItem;
      if ( WorkItem >= 0 )
        return 0;
      LOBYTE(v43) = 2;
      WPP_RECORDER_SF_d(VmsIfrLog, v43, 20, 249, (__int64)WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids, WorkItem);
    }
    else
    {
      v12 = -1073741801;
    }
  }
  else
  {
    v12 = -1073741801;
    WPP_RECORDER_SF_Ld(
      VmsIfrNicLog,
      v31,
      v32,
      246,
      (__int64)WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids,
      16 * v11,
      23);
  }
LABEL_36:
  v50 = a3;
  v44 = v57;
  WPP_RECORDER_SF_qLdd(
    VmsIfrNicLog,
    v13,
    v14,
    250,
    (__int64)WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids,
    a1,
    v57,
    v50,
    v12);
  if ( v10 )
  {
    if ( !v9 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v45,
        19,
        251,
        (__int64)WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids,
        (__int64)"shadowSendBufferSectionMdlArray != NULL");
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    v46 = 0;
    if ( (_DWORD)v11 )
    {
      do
      {
        v47 = (struct _MDL *)v10[v46];
        if ( v47 )
        {
          IoFreeMdl(v47);
          v10[v46] = 0;
        }
        v48 = *(struct _MDL **)&v9[8 * v46];
        if ( v48 )
        {
          IoFreeMdl(v48);
          *(_QWORD *)&v9[8 * v46] = 0;
        }
        v46 = (unsigned int)(v46 + 1);
      }
      while ( (unsigned int)v46 < v58 );
    }
    ExFreePoolWithTag(v10, 0x4E567356u);
    v44 = v57;
  }
  if ( P )
    ExFreePoolWithTag(P, 0x4E567356u);
  if ( MemoryDescriptorList )
    VmbChannelUnmapGpadl(*v8, v44);
  if ( v7 )
  {
    MmFreePagesFromMdl(v7);
    ExFreePoolWithTag(v7, 0);
  }
  VmsVmNicExtObjCleanup(a1);
  return v12;
}

```

## disassembly

```asm
0x140048538  mov     r11, rsp
0x14004853b  mov     [r11+18h], rbx
0x14004853f  mov     [rsp+arg_8], edx
0x140048543  push    rbp
0x140048544  push    rsi
0x140048545  push    rdi
0x140048546  push    r12
0x140048548  push    r13
0x14004854a  push    r14
0x14004854c  push    r15
0x14004854e  sub     rsp, 80h
0x140048555  mov     r13, rcx
0x140048558  mov     eax, edx
0x14004855a  xor     ecx, ecx
0x14004855c  lea     rdx, WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids
0x140048563  mov     esi, r8d
0x140048566  mov     [r11+8], cx
0x14004856b  mov     [r11+0Ah], cl
0x14004856f  mov     r15d, ecx
0x140048572  lea     rdi, [r13+10h]
0x140048576  mov     r12d, ecx
0x140048579  mov     r14d, ecx
0x14004857c  mov     [r11-68h], rcx
0x140048580  mov     ebp, ecx
0x140048582  mov     [rsp+0B8h+arg_18], ecx
0x140048589  mov     [rsp+0B8h+P], rcx
0x14004858e  cmp     [r13+128h], rcx
0x140048595  jz      short loc_1400485C2
0x140048597  mov     ebx, 0C0000010h
0x14004859c  lea     r8d, [rcx+14h]
0x1400485a0  mov     [rsp+0B8h+Priority], ebx
0x1400485a4  mov     rcx, cs:VmsIfrNicLog
0x1400485ab  mov     r9d, 0F0h
0x1400485b1  mov     qword ptr [rsp+0B8h+BugCheckOnFailure], rdx
0x1400485b6  mov     dl, 2
0x1400485b8  call    WPP_RECORDER_SF_d
0x1400485bd  jmp     loc_140048A9F
0x1400485c2  mov     rcx, [rdi]
0x1400485c5  lea     r9, [rsp+0B8h+MemoryDescriptorList]
0x1400485ca  mov     r8d, eax
0x1400485cd  mov     edx, 1
0x1400485d2  call    cs:__imp_VmbChannelMapGpadl
0x1400485d9  nop     dword ptr [rax+rax+00h]
0x1400485de  mov     ebx, eax
0x1400485e0  test    eax, eax
0x1400485e2  jns     short loc_14004861E
0x1400485e4  mov     rcx, cs:VmsIfrNicLog
0x1400485eb  mov     r9d, 0F1h
0x1400485f1  mov     dword ptr [rsp+0B8h+var_80], eax
0x1400485f5  mov     eax, [rsp+0B8h+arg_8]
0x1400485fc  mov     [rsp+0B8h+var_88], eax
0x140048600  mov     rax, [rdi]
0x140048603  mov     qword ptr [rsp+0B8h+Priority], rax
0x140048608  lea     rax, WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids
0x14004860f  mov     qword ptr [rsp+0B8h+BugCheckOnFailure], rax
0x140048614  call    WPP_RECORDER_SF_qLd
0x140048619  jmp     loc_140048A9F
0x14004861e  mov     rcx, [rsp+0B8h+MemoryDescriptorList]; MemoryDescriptorList
0x140048623  mov     ebp, [rcx+28h]
0x140048626  cmp     ebp, cs:VmsVmNicMaxSendBufferSizeInBytes
0x14004862c  jbe     short loc_140048657
0x14004862e  mov     ebx, 0C0000206h
0x140048633  mov     eax, [rsp+0B8h+arg_8]
0x14004863a  mov     dword ptr [rsp+0B8h+var_80], ebp
0x14004863e  mov     [rsp+0B8h+var_88], eax
0x140048642  mov     rax, [rdi]
0x140048645  mov     qword ptr [rsp+0B8h+Priority], rax
0x14004864a  call    WPP_RECORDER_SF_qLLLd
0x14004864f  mov     ebp, r12d
0x140048652  jmp     loc_140048A9F
0x140048657  test    byte ptr [rcx+0Ah], 5
0x14004865b  jz      short loc_140048663
0x14004865d  mov     rax, [rcx+18h]
0x140048661  jmp     short loc_14004868A
0x140048663  xor     r9d, r9d; RequestedAddress
0x140048666  mov     [rsp+0B8h+Priority], 40000000h; Priority
0x14004866e  xor     edx, edx; AccessMode
0x140048670  mov     [rsp+0B8h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x140048675  lea     r8d, [r9+1]; CacheType
0x140048679  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140048680  nop     dword ptr [rax+rax+00h]
0x140048685  mov     rcx, [rsp+0B8h+MemoryDescriptorList]
0x14004868a  mov     [rsp+0B8h+var_50], rax
0x14004868f  test    rax, rax
0x140048692  jnz     short loc_1400486D7
0x140048694  mov     eax, 0C000009Ah
0x140048699  mov     ebx, eax
0x14004869b  mov     dword ptr [rsp+0B8h+var_80], eax
0x14004869f  mov     r9d, 0F3h
0x1400486a5  mov     [rsp+0B8h+var_88], 40000000h
0x1400486ad  lea     rax, WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids
0x1400486b4  mov     qword ptr [rsp+0B8h+Priority], rcx
0x1400486b9  mov     r8d, 14h
0x1400486bf  mov     rcx, cs:VmsIfrNicLog
0x1400486c6  mov     dl, 2
0x1400486c8  mov     qword ptr [rsp+0B8h+BugCheckOnFailure], rax
0x1400486cd  call    WPP_RECORDER_SF_qDd
0x1400486d2  jmp     loc_14004864F
0x1400486d7  test    esi, esi
0x1400486d9  mov     [rsp+0B8h+Priority], 5; Flags
0x1400486e1  mov     eax, 1800h
0x1400486e6  mov     [rsp+0B8h+BugCheckOnFailure], 1; CacheType
0x1400486ee  cmovnz  eax, esi
0x1400486f1  mov     r9, rbp; TotalBytes
0x1400486f4  mov     esi, eax
0x1400486f6  xor     edx, edx
0x1400486f8  mov     eax, ebp
0x1400486fa  xor     ecx, ecx; LowAddress
0x1400486fc  div     esi
0x1400486fe  xor     r8d, r8d; SkipBytes
0x140048701  or      rdx, 0FFFFFFFFFFFFFFFFh; HighAddress
0x140048705  mov     ebx, eax
0x140048707  mov     [rsp+0B8h+arg_18], ebx
0x14004870e  call    cs:__imp_MmAllocatePagesForMdlEx
0x140048715  nop     dword ptr [rax+rax+00h]
0x14004871a  mov     r15, rax
0x14004871d  test    rax, rax
0x140048720  jnz     short loc_140048765
0x140048722  mov     eax, 0C000009Ah
0x140048727  mov     ebx, eax
0x140048729  mov     rcx, [rsp+0B8h+MemoryDescriptorList]
0x14004872e  mov     r9d, 0F4h
0x140048734  mov     dword ptr [rsp+0B8h+var_80], eax
0x140048738  lea     rax, WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids
0x14004873f  mov     [rsp+0B8h+var_88], ebp
0x140048743  mov     qword ptr [rsp+0B8h+Priority], rcx
0x140048748  mov     rcx, cs:VmsIfrNicLog
0x14004874f  mov     qword ptr [rsp+0B8h+BugCheckOnFailure], rax
0x140048754  call    WPP_RECORDER_SF_qLd
0x140048759  mov     ebp, [rsp+0B8h+arg_18]
0x140048760  jmp     loc_140048A9F
0x140048765  test    byte ptr [rax+0Ah], 5
0x140048769  jz      short loc_140048771
0x14004876b  mov     rax, [rax+18h]
0x14004876f  jmp     short loc_140048796
0x140048771  xor     r9d, r9d; RequestedAddress
0x140048774  mov     [rsp+0B8h+Priority], 40000000h; Priority
0x14004877c  xor     edx, edx; AccessMode
0x14004877e  mov     [rsp+0B8h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x140048783  mov     rcx, r15; MemoryDescriptorList
0x140048786  lea     r8d, [r9+1]; CacheType
0x14004878a  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140048791  nop     dword ptr [rax+rax+00h]
0x140048796  mov     [rsp+0B8h+var_58], rax
0x14004879b  test    rax, rax
0x14004879e  jnz     short loc_1400487E3
0x1400487a0  mov     eax, 0C000009Ah
0x1400487a5  mov     ebx, eax
0x1400487a7  mov     rcx, cs:VmsIfrNicLog
0x1400487ae  mov     r9d, 0F5h
0x1400487b4  mov     dword ptr [rsp+0B8h+var_80], eax
0x1400487b8  mov     r8d, 14h
0x1400487be  mov     [rsp+0B8h+var_88], 40000000h
0x1400487c6  lea     rax, WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids
0x1400487cd  mov     qword ptr [rsp+0B8h+Priority], r15
0x1400487d2  mov     dl, 2
0x1400487d4  mov     qword ptr [rsp+0B8h+BugCheckOnFailure], rax
0x1400487d9  call    WPP_RECORDER_SF_qDd
0x1400487de  jmp     loc_140048759
0x1400487e3  mov     rbp, rbx
0x1400487e6  mov     r8d, 4E567356h
0x1400487ec  shl     rbx, 4
0x1400487f0  mov     ecx, 40h ; '@'
0x1400487f5  mov     rdx, rbx
0x1400487f8  call    cs:__imp_ExAllocatePool2
0x1400487ff  nop     dword ptr [rax+rax+00h]
0x140048804  mov     r14, rax
0x140048807  test    rax, rax
0x14004880a  jnz     short loc_140048841
0x14004880c  mov     ebx, 0C0000017h
0x140048811  mov     [rsp+0B8h+var_88], ebx
0x140048815  lea     rax, WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids
0x14004881c  mov     r9d, 0F6h
0x140048822  mov     ecx, ebp
0x140048824  shl     ecx, 4
0x140048827  mov     [rsp+0B8h+Priority], ecx
0x14004882b  mov     rcx, cs:VmsIfrNicLog
0x140048832  mov     qword ptr [rsp+0B8h+BugCheckOnFailure], rax
0x140048837  call    WPP_RECORDER_SF_Ld
0x14004883c  jmp     loc_140048A9F
0x140048841  mov     r8, rbx; Size
0x140048844  xor     edx, edx; Val
0x140048846  mov     rcx, r14; void *
0x140048849  call    memset
0x14004884e  lea     rdx, ds:0[rbp*8]
0x140048856  mov     ecx, 40h ; '@'
0x14004885b  mov     r8d, 4E567356h
0x140048861  lea     r12, [rdx+r14]
0x140048865  call    cs:__imp_ExAllocatePool2
0x14004886c  nop     dword ptr [rax+rax+00h]
0x140048871  mov     [rsp+0B8h+P], rax
0x140048876  test    rax, rax
0x140048879  jnz     short loc_140048885
0x14004887b  mov     ebx, 0C0000017h
0x140048880  jmp     loc_140048A9F
0x140048885  xor     ebp, ebp
0x140048887  xor     r8d, r8d; SecondaryBuffer
0x14004888a  cmp     ebp, [rsp+0B8h+arg_18]
0x140048891  jnb     loc_1400489B4
0x140048897  mov     rcx, [rsp+0B8h+var_50]
0x14004889c  mov     eax, esi
0x14004889e  imul    eax, ebp
0x1400488a1  xor     r9d, r9d; ChargeQuota
0x1400488a4  mov     edx, esi; Length
0x1400488a6  mov     qword ptr [rsp+0B8h+BugCheckOnFailure], r8; Irp
0x1400488ab  add     rcx, rax; VirtualAddress
0x1400488ae  mov     [rsp+0B8h+var_48], rax
0x1400488b3  call    cs:__imp_IoAllocateMdl
0x1400488ba  nop     dword ptr [rax+rax+00h]
0x1400488bf  mov     [r14+rbp*8], rax
0x1400488c3  test    rax, rax
0x1400488c6  jz      loc_14004897D
0x1400488cc  mov     rcx, [rsp+0B8h+var_48]
0x1400488d1  xor     r9d, r9d; ChargeQuota
0x1400488d4  add     rcx, [rsp+0B8h+var_58]; VirtualAddress
0x1400488d9  xor     r8d, r8d; SecondaryBuffer
0x1400488dc  mov     edx, esi; Length
0x1400488de  mov     qword ptr [rsp+0B8h+BugCheckOnFailure], 0; Irp
0x1400488e7  call    cs:__imp_IoAllocateMdl
0x1400488ee  nop     dword ptr [rax+rax+00h]
0x1400488f3  mov     [r12+rbp*8], rax
0x1400488f7  test    rax, rax
0x1400488fa  jz      short loc_140048946
0x1400488fc  mov     rcx, [r14+rbp*8]; MemoryDescriptorList
0x140048900  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140048907  nop     dword ptr [rax+rax+00h]
0x14004890c  mov     rcx, [r12+rbp*8]; MemoryDescriptorList
0x140048910  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140048917  nop     dword ptr [rax+rax+00h]
0x14004891c  mov     rax, [r14+rbp*8]
0x140048920  mov     qword ptr [rax], 0
0x140048927  mov     rax, [r12+rbp*8]
0x14004892b  mov     qword ptr [rax], 0
0x140048932  mov     rax, [rsp+0B8h+P]
0x140048937  mov     qword ptr [rax+rbp*8], 0
0x14004893f  inc     ebp
0x140048941  jmp     loc_140048887
0x140048946  mov     eax, 0C000009Ah
0x14004894b  mov     ebx, eax
0x14004894d  mov     rcx, cs:VmsIfrNicLog
0x140048954  mov     r9d, 0F8h
0x14004895a  mov     dword ptr [rsp+0B8h+var_80], eax
0x14004895e  lea     rax, WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids
0x140048965  mov     [rsp+0B8h+var_88], ebp
0x140048969  mov     qword ptr [rsp+0B8h+Priority], r12
0x14004896e  mov     qword ptr [rsp+0B8h+BugCheckOnFailure], rax
0x140048973  call    WPP_RECORDER_SF_qLd
0x140048978  jmp     loc_140048759
0x14004897d  mov     eax, 0C000009Ah
0x140048982  mov     ebx, eax
0x140048984  mov     rcx, cs:VmsIfrNicLog
0x14004898b  mov     r9d, 0F7h
0x140048991  mov     dword ptr [rsp+0B8h+var_80], eax
0x140048995  lea     rax, WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids
0x14004899c  mov     [rsp+0B8h+var_88], ebp
0x1400489a0  mov     qword ptr [rsp+0B8h+Priority], r14
0x1400489a5  mov     qword ptr [rsp+0B8h+BugCheckOnFailure], rax
0x1400489aa  call    WPP_RECORDER_SF_qLd
0x1400489af  jmp     loc_140048759
0x1400489b4  mov     rcx, [r13+2A8h]
0x1400489bb  lea     rdx, [rsp+0B8h+LockState]
0x1400489c3  call    VmsOmObjectLockExclusive
0x1400489c8  mov     eax, [rsp+0B8h+arg_8]
0x1400489cf  lea     rdx, [rsp+0B8h+LockState]; LockState
0x1400489d7  mov     rcx, [r13+2A8h]
0x1400489de  mov     ebp, [rsp+0B8h+arg_18]
0x1400489e5  mov     [r13+224h], eax
0x1400489ec  mov     rax, [rsp+0B8h+P]
0x1400489f1  mov     [r13+240h], esi
0x1400489f8  mov     [r13+128h], r14
0x1400489ff  mov     [r13+130h], ebp
0x140048a06  mov     [r13+5A8h], rax
0x140048a0d  mov     rax, [rsp+0B8h+var_58]
0x140048a12  mov     [r13+140h], rax
0x140048a19  mov     [r13+138h], r15
0x140048a20  mov     [r13+148h], r12
0x140048a27  mov     rcx, [rcx+38h]; Lock
0x140048a2b  call    cs:__imp_NdisReleaseRWLock
0x140048a32  nop     dword ptr [rax+rax+00h]
0x140048a37  mov     rcx, [r13+2A8h]
0x140048a3e  lea     rax, [r13+5F0h]
0x140048a45  mov     qword ptr [rsp+0B8h+Priority], rax; __int64
0x140048a4a  lea     r8, VmsVmNicPvtRevokeSendBufferWorkItem
0x140048a51  mov     r9, r13
0x140048a54  mov     qword ptr [rsp+0B8h+BugCheckOnFailure], 0Ah; __int64
0x140048a5d  xor     edx, edx
0x140048a5f  mov     rcx, [rcx+830h]; Lookaside
0x140048a66  call    NvIoAllocateWorkItem
0x140048a6b  mov     ebx, eax
0x140048a6d  test    eax, eax
0x140048a6f  jns     loc_140048BE3
0x140048a75  mov     rcx, cs:VmsIfrLog
0x140048a7c  mov     r9d, 0F9h
0x140048a82  mov     [rsp+0B8h+Priority], eax
0x140048a86  mov     r8d, 14h
0x140048a8c  lea     rax, WPP_c82ab66e9bd63990c2f25111644f9dca_Traceguids
0x140048a93  mov     dl, 2
0x140048a95  mov     qword ptr [rsp+0B8h+BugCheckOnFailure], rax
0x140048a9a  call    WPP_RECORDER_SF_d
0x140048a9f  mov     rcx, cs:VmsIfrNicLog
  ... truncated ...
```
