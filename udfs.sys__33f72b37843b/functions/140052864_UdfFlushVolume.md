# UdfFlushVolume

- ea: `0x140052864`
- end: `0x14005324f`
- name: `UdfFlushVolume`
- size: `2539`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, char, char)`
- caller_count: `15`
- callee_count: `19`
- tags: `installer_update`

## callers

- `0x140003148`
- `0x140006680`
- `0x14000cce0`
- `0x140012e94`
- `0x140013128`
- `0x140013e10`
- `0x140016fa8`
- `0x140018740`
- `0x140035794`
- `0x140035ca4`
- `0x14003787c`
- `0x14003a7a4`
- `0x14003aa44`
- `0x140050ee0`
- `0x140055060`

## callees

- `0x1400050d8`
- `0x140008790`
- `0x140009014`
- `0x14000925c`
- `0x14000ba88`
- `0x14000c870`
- `0x14000ca10`
- `0x14000cad4`
- `0x140012cc8`
- `0x140012e2c`
- `0x140016fa8`
- `0x14003b730`
- `0x14003ca78`
- `0x14004ce50`
- `0x140052864`
- `0x1400537b0`
- `0x140058898`
- `0x140058aac`
- `0x140059004`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140052bec`
- `ntoskrnl!ExReleaseResourceLite` at `0x140052c2a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140052e0c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ab11`
- `ntoskrnl!ExReleaseResourceLite` at `0x140052bec`
- `ntoskrnl!ExReleaseResourceLite` at `0x140052c2a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140052e0c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ab11`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140052dda`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140052dda`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140052975`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140052998`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140052975`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140052998`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140052a05`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140052a23`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140052a5c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140052a7a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140052a05`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140052a23`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140052a5c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140052a7a`
- `ntoskrnl!CcFlushCache` at `0x140052ace`
- `ntoskrnl!CcFlushCache` at `0x140052b18`
- `ntoskrnl!CcFlushCache` at `0x140052c69`
- `ntoskrnl!CcFlushCache` at `0x140052caf`
- `ntoskrnl!CcFlushCache` at `0x140052d04`
- `ntoskrnl!CcFlushCache` at `0x140052d4a`
- `ntoskrnl!CcFlushCache` at `0x140052da2`
- `ntoskrnl!CcFlushCache` at `0x14005314e`
- `ntoskrnl!CcFlushCache` at `0x140052ace`
- `ntoskrnl!CcFlushCache` at `0x140052b18`
- `ntoskrnl!CcFlushCache` at `0x140052c69`
- `ntoskrnl!CcFlushCache` at `0x140052caf`
- `ntoskrnl!CcFlushCache` at `0x140052d04`
- `ntoskrnl!CcFlushCache` at `0x140052d4a`
- `ntoskrnl!CcFlushCache` at `0x140052da2`
- `ntoskrnl!CcFlushCache` at `0x14005314e`
- `ntoskrnl!CcPurgeCacheSection` at `0x140052eb4`
- `ntoskrnl!CcPurgeCacheSection` at `0x140052edf`
- `ntoskrnl!CcPurgeCacheSection` at `0x140052f0a`
- `ntoskrnl!CcPurgeCacheSection` at `0x140052f35`
- `ntoskrnl!CcPurgeCacheSection` at `0x140052f60`
- `ntoskrnl!CcPurgeCacheSection` at `0x140052f8b`
- `ntoskrnl!CcPurgeCacheSection` at `0x140052fb6`
- `ntoskrnl!CcPurgeCacheSection` at `0x1400531f1`
- `ntoskrnl!CcPurgeCacheSection` at `0x140052eb4`
- `ntoskrnl!CcPurgeCacheSection` at `0x140052edf`
- `ntoskrnl!CcPurgeCacheSection` at `0x140052f0a`
- `ntoskrnl!CcPurgeCacheSection` at `0x140052f35`
- `ntoskrnl!CcPurgeCacheSection` at `0x140052f60`
- `ntoskrnl!CcPurgeCacheSection` at `0x140052f8b`
- `ntoskrnl!CcPurgeCacheSection` at `0x140052fb6`
- `ntoskrnl!CcPurgeCacheSection` at `0x1400531f1`
- `ntoskrnl!MmFlushImageSection` at `0x14005311a`
- `ntoskrnl!MmFlushImageSection` at `0x14005311a`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1400529c0`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1400529c0`

## pseudocode

```c
__int64 __fastcall UdfFlushVolume(__int64 a1, __int64 a2, __int64 a3, char a4, char a5, char a6)
{
  char v6; // r12
  __int64 v7; // rdi
  NTSTATUS v9; // ebx
  char v11; // r14
  _QWORD *v12; // rax
  _QWORD *v13; // rsi
  struct _FAST_MUTEX *v14; // rcx
  int v15; // r9d
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rcx
  int v26; // esi
  __int64 v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  SECTION_OBJECT_POINTERS *v35; // rcx
  NTSTATUS Status; // r13d
  NTSTATUS v37; // [rsp+34h] [rbp-64h] BYREF
  NTSTATUS v38; // [rsp+38h] [rbp-60h]
  _QWORD *v39; // [rsp+40h] [rbp-58h]
  PVOID RestartKey; // [rsp+48h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+50h] [rbp-48h] BYREF
  char v42; // [rsp+B0h] [rbp+18h]
  char v43; // [rsp+B8h] [rbp+20h] BYREF

  v42 = a3;
  v6 = a4;
  v7 = a2;
  v9 = 0;
  v37 = 0;
  RestartKey = 0;
  v43 = 0;
  IoStatus = 0;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x8000000) != 0 )
  {
    LOBYTE(a3) = a5 != 0 ? 89 : 78;
    LOBYTE(a2) = a4 != 0 ? 89 : 78;
    WPP_SF_qcc(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), a2, a3, v7, (_BYTE)a2, (_BYTE)a3);
  }
  UdfFspClose(v7);
  if ( v6 && (*(_DWORD *)(v7 + 52) != 2 || (*(_DWORD *)(v7 + 48) & 0x10) != 0) )
  {
    v6 = 0;
    if ( !a5 )
    {
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x8000000) != 0 )
      {
        WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 13, WPP_dfdd884fd2a539582ed6ef57b513599a_Traceguids);
      }
      return 0;
    }
  }
  v39 = 0;
  v11 = 0;
  UdfAcquireAllFiles(a1, v7);
  while ( 1 )
  {
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v7 + 1648));
    *(_QWORD *)(v7 + 1704) = KeGetCurrentThread();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v7 + 1584));
    *(_QWORD *)(v7 + 1640) = KeGetCurrentThread();
    v12 = RtlEnumerateGenericTableWithoutSplayingAvl((PRTL_AVL_TABLE)(v7 + 1736), &RestartKey);
    v13 = v12;
    if ( v12 )
      v13 = (_QWORD *)v12[1];
    if ( v13 )
      ++*((_DWORD *)v13 + 51);
    v14 = (struct _FAST_MUTEX *)(v7 + 1584);
    if ( v39 )
    {
      --*((_DWORD *)v39 + 51);
      *(_QWORD *)(v7 + 1640) = 0;
      ExReleaseFastMutexUnsafe(v14);
      *(_QWORD *)(v7 + 1704) = 0;
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v7 + 1648));
      LOBYTE(v15) = 1;
      UdfTeardownStructures(a1, (_DWORD)v39, 0, v15, (__int64)&v43);
    }
    else
    {
      *(_QWORD *)(v7 + 1640) = 0;
      ExReleaseFastMutexUnsafe(v14);
      *(_QWORD *)(v7 + 1704) = 0;
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v7 + 1648));
    }
    if ( !v13 )
      break;
    v39 = v13;
    v34 = v13[53];
    if ( *(_QWORD *)(v34 + 24) )
      MmFlushImageSection((PSECTION_OBJECT_POINTERS)(v34 + 8), MmFlushForWrite);
    v35 = (SECTION_OBJECT_POINTERS *)(v13[53] + 8LL);
    if ( v35->DataSectionObject )
    {
      if ( !v6 )
        goto LABEL_119;
      CcFlushCache(v35, 0, 0, &IoStatus);
      Status = IoStatus.Status;
      v38 = IoStatus.Status;
      if ( IoStatus.Status == -2147483626 && *(_BYTE *)(a1 + 57) != 2 )
        UdfRaiseStatusEx(a1, 2147483670LL, 0);
      if ( IoStatus.Status < 0 )
      {
        v35 = *(SECTION_OBJECT_POINTERS **)&WPP_GLOBAL_Control;
        if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x8000000) != 0 )
        {
          WPP_SF_qD(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
            14,
            WPP_dfdd884fd2a539582ed6ef57b513599a_Traceguids,
            v13,
            IoStatus.Status);
        }
        if ( !v9 )
          v9 = Status;
        v37 = v9;
      }
      if ( Status >= 0 )
      {
LABEL_119:
        if ( !a5 )
          goto LABEL_128;
        if ( !CcPurgeCacheSection((PSECTION_OBJECT_POINTERS)(v13[53] + 8LL), 0, 0, 0) )
        {
          if ( !v9 )
            v9 = -1073741797;
          v37 = v9;
        }
      }
    }
    if ( a5 && *(_WORD *)v13 != 2356 && v13[63] )
      UdfDeleteInternalStream(v35, v13);
LABEL_128:
    if ( a6 )
      *((_DWORD *)v13 + 54) = 2;
  }
  if ( v6 )
  {
    if ( _bittest((const signed __int32 *)(v7 + 48), 0x15u) )
      UdfSeqCacheFlush(a1, v7);
    v17 = *(_QWORD *)(v7 + 320);
    if ( v17 )
    {
      CcFlushCache((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v17 + 424) + 8LL), 0, 0, &IoStatus);
      if ( IoStatus.Status < 0 )
      {
        if ( v9 >= 0 )
          v9 = IoStatus.Status;
        v37 = v9;
        v11 = 1;
      }
    }
    v18 = *(_DWORD *)(v7 + 48);
    if ( (v18 & 0x8000000) != 0 )
    {
      CcFlushCache((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(*(_QWORD *)(v7 + 328) + 424LL) + 8LL), 0, 0, &IoStatus);
      if ( IoStatus.Status < 0 )
      {
        if ( v9 >= 0 )
          v9 = IoStatus.Status;
        v37 = v9;
        v11 = 1;
      }
    }
    else if ( (v18 & 0x20000000) != 0 )
    {
      if ( (v18 & 0x200000) != 0 )
        UdfSeqCacheFlush(a1, v7);
      UdfAcquireResource(a1, *(_QWORD *)(*(_QWORD *)(v7 + 320) + 16LL), 0, 0);
      v19 = *(_QWORD *)(v7 + 328);
      if ( _bittest((const signed __int32 *)(v19 + 212), 0x1Du) )
      {
        v20 = *(_QWORD *)(v7 + 320);
        *(_OWORD *)(v19 + 232) = *(_OWORD *)(v20 + 232);
        *(_OWORD *)(v19 + 248) = *(_OWORD *)(v20 + 248);
        UdfAcquireResource(a1, *(_QWORD *)(*(_QWORD *)(v7 + 328) + 16LL), 0, 0);
        UdfUpdateAdsFromScb(a1, *(_QWORD *)(v7 + 328), 0, 0xFFFFFFFFLL);
        ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(v7 + 328) + 16LL));
        v21 = *(_QWORD *)(v7 + 328);
        *(_OWORD *)(v21 + 232) = 0;
        *(_OWORD *)(v21 + 248) = 0;
        *(_DWORD *)(*(_QWORD *)(v7 + 328) + 212LL) &= ~0x20000000u;
      }
      ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(v7 + 320) + 16LL));
    }
    if ( _bittest((const signed __int32 *)(v7 + 48), 0x15u) )
      UdfSeqCacheFlush(a1, v7);
    v22 = *(_QWORD *)(v7 + 336);
    if ( v22 )
    {
      CcFlushCache((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v22 + 424) + 8LL), 0, 0, &IoStatus);
      if ( IoStatus.Status < 0 )
      {
        if ( v9 >= 0 )
          v9 = IoStatus.Status;
        v37 = v9;
        v11 = 1;
      }
    }
    v23 = *(_QWORD *)(v7 + 272);
    if ( v23 )
    {
      CcFlushCache((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v23 + 424) + 8LL), 0, 0, &IoStatus);
      if ( IoStatus.Status < 0 )
      {
        if ( v9 >= 0 )
          v9 = IoStatus.Status;
        v37 = v9;
        v11 = 1;
      }
    }
    v24 = *(_QWORD *)(v7 + 296);
    if ( v24 )
    {
      *(_DWORD *)(v24 + 212) |= 0x40000000u;
      CcFlushCache((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(*(_QWORD *)(v7 + 296) + 424LL) + 8LL), 0, 0, &IoStatus);
      if ( IoStatus.Status < 0 )
      {
        if ( v9 >= 0 )
          v9 = IoStatus.Status;
        v37 = v9;
        v11 = 1;
      }
    }
    v25 = *(_QWORD *)(v7 + 352);
    if ( v25 )
    {
      CcFlushCache((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v25 + 424) + 8LL), 0, 0, &IoStatus);
      if ( IoStatus.Status < 0 )
      {
        if ( v9 >= 0 )
          v9 = IoStatus.Status;
        v37 = v9;
        v11 = 1;
      }
    }
    if ( _bittest((const signed __int32 *)(v7 + 48), 0x15u) )
      UdfSeqCacheFlush(a1, v7);
    v16 = *(_QWORD *)(v7 + 344);
    if ( v16 )
    {
      CcFlushCache((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v16 + 424) + 8LL), 0, 0, &IoStatus);
      if ( IoStatus.Status < 0 )
      {
        if ( v9 >= 0 )
          v9 = IoStatus.Status;
        v37 = v9;
        v11 = 1;
      }
    }
    if ( (*(_DWORD *)(v7 + 48) & 0x2000) != 0 )
    {
      ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)(v7 + 104) + 128LL), 1u);
      v26 = UdfRmwFlushCache(a1);
      v38 = v26;
      ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(v7 + 104) + 128LL));
      if ( v26 < 0 )
      {
        if ( v9 >= 0 )
          v9 = v26;
        v37 = v9;
        v11 = 1;
      }
    }
    if ( !_bittest((const signed __int32 *)(v7 + 48), 0xEu)
      && !_bittest((const signed __int32 *)(a1 + 28), 0xEu)
      && *(_DWORD *)(v7 + 52) == 2 )
    {
      UdfMarkVolumeClean(a1);
    }
    v27 = *(_QWORD *)(v7 + 296);
    if ( v27 )
      *(_DWORD *)(v27 + 212) &= ~0x40000000u;
  }
  if ( a5 )
  {
    if ( (*(_DWORD *)(v7 + 2128) & 0x40) != 0 )
      UdfRmwStopQuickGrowFormat(v16, v7);
    if ( !v11 )
    {
      v28 = *(_QWORD *)(v7 + 320);
      if ( v28 )
        CcPurgeCacheSection((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v28 + 424) + 8LL), 0, 0, 0);
      v29 = *(_QWORD *)(v7 + 328);
      if ( v29 )
        CcPurgeCacheSection((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v29 + 424) + 8LL), 0, 0, 0);
      v30 = *(_QWORD *)(v7 + 336);
      if ( v30 )
        CcPurgeCacheSection((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v30 + 424) + 8LL), 0, 0, 0);
      v31 = *(_QWORD *)(v7 + 352);
      if ( v31 )
        CcPurgeCacheSection((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v31 + 424) + 8LL), 0, 0, 0);
      v32 = *(_QWORD *)(v7 + 344);
      if ( v32 )
        CcPurgeCacheSection((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v32 + 424) + 8LL), 0, 0, 0);
      v33 = *(_QWORD *)(v7 + 272);
      if ( v33 )
        CcPurgeCacheSection((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v33 + 424) + 8LL), 0, 0, 0);
      v16 = *(_QWORD *)(v7 + 296);
      if ( v16 )
        CcPurgeCacheSection((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v16 + 424) + 8LL), 0, 0, 0);
    }
  }
  if ( v42 )
  {
    UdfTearDownAllocationSupport(a1, v7);
    UdfTearDownSpecialScb(a1, *(_QWORD *)(v7 + 288), &v37);
    UdfTearDownSpecialScb(a1, *(_QWORD *)(v7 + 272), &v37);
    UdfTearDownSpecialScb(a1, *(_QWORD *)(v7 + 352), &v37);
    UdfTearDownSpecialScb(a1, *(_QWORD *)(v7 + 344), &v37);
    UdfTearDownSpecialScb(a1, *(_QWORD *)(v7 + 280), &v37);
    UdfTearDownSpecialScb(a1, *(_QWORD *)(v7 + 296), &v37);
    UdfTearDownSpecialScb(a1, *(_QWORD *)(v7 + 304), &v37);
    UdfTearDownSpecialScb(a1, *(_QWORD *)(v7 + 312), &v37);
    UdfTearDownSpecialScb(a1, *(_QWORD *)(v7 + 320), &v37);
    UdfTearDownSpecialScb(a1, *(_QWORD *)(v7 + 328), &v37);
    UdfTearDownSpecialScb(a1, *(_QWORD *)(v7 + 336), &v37);
    v9 = v37;
  }
  UdfReleaseAllFiles(v16, v7);
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x8000000) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 15, WPP_dfdd884fd2a539582ed6ef57b513599a_Traceguids);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140052864  mov     rax, rsp
0x140052867  mov     [rax+18h], r8b
0x14005286b  mov     [rax+10h], rdx
0x14005286f  push    rbx
0x140052870  push    rsi
0x140052871  push    rdi
0x140052872  push    r12
0x140052874  push    r13
0x140052876  push    r14
0x140052878  push    r15
0x14005287a  sub     rsp, 60h
0x14005287e  mov     r12b, r9b
0x140052881  mov     rdi, rdx
0x140052884  mov     r15, rcx
0x140052887  xor     esi, esi
0x140052889  mov     ebx, esi
0x14005288b  mov     [rax-64h], ebx
0x14005288e  mov     [rax-50h], rsi
0x140052892  mov     [rax+20h], sil
0x140052896  xorps   xmm0, xmm0
0x140052899  movups  xmmword ptr [rax-48h], xmm0
0x14005289d  lea     r14, WPP_GLOBAL_Control
0x1400528a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400528ab  cmp     rcx, r14
0x1400528ae  jz      short loc_1400528EF
0x1400528b0  mov     eax, [rcx+2Ch]
0x1400528b3  bt      eax, 1Bh
0x1400528b7  jnb     short loc_1400528EF
0x1400528b9  mov     al, [rsp+98h+arg_20]
0x1400528c0  neg     al
0x1400528c2  sbb     r8b, r8b
0x1400528c5  and     r8b, 0Bh
0x1400528c9  add     r8b, 4Eh ; 'N'
0x1400528cd  mov     al, r9b
0x1400528d0  neg     al
0x1400528d2  sbb     dl, dl
0x1400528d4  and     dl, 0Bh
0x1400528d7  add     dl, 4Eh ; 'N'
0x1400528da  mov     [rsp+98h+var_70], r8b
0x1400528df  mov     byte ptr [rsp+98h+var_78], dl
0x1400528e3  mov     r9, rdi
0x1400528e6  mov     rcx, [rcx+18h]
0x1400528ea  call    WPP_SF_qcc
0x1400528ef  mov     rcx, rdi
0x1400528f2  call    UdfFspClose
0x1400528f7  test    r12b, r12b
0x1400528fa  jz      short loc_140052953
0x1400528fc  cmp     dword ptr [rdi+34h], 2
0x140052900  jnz     short loc_140052909
0x140052902  mov     eax, [rdi+30h]
0x140052905  test    al, 10h
0x140052907  jz      short loc_140052953
0x140052909  mov     r12b, sil
0x14005290c  cmp     [rsp+98h+arg_20], sil
0x140052914  jnz     short loc_140052953
0x140052916  mov     rcx, cs:WPP_GLOBAL_Control
0x14005291d  cmp     rcx, r14
0x140052920  jz      short loc_140052940
0x140052922  test    dword ptr [rcx+2Ch], 8000000h
0x140052929  jz      short loc_140052940
0x14005292b  mov     edx, 0Dh
0x140052930  lea     r8, WPP_dfdd884fd2a539582ed6ef57b513599a_Traceguids
0x140052937  mov     rcx, [rcx+18h]
0x14005293b  call    WPP_SF_
0x140052940  xor     eax, eax
0x140052942  add     rsp, 60h
0x140052946  pop     r15
0x140052948  pop     r14
0x14005294a  pop     r13
0x14005294c  pop     r12
0x14005294e  pop     rdi
0x14005294f  pop     rsi
0x140052950  pop     rbx
0x140052951  retn
0x140052953  mov     r13d, esi
0x140052956  mov     [rsp+98h+var_58], rsi
0x14005295b  mov     r14b, sil
0x14005295e  mov     [rsp+98h+var_67], bl
0x140052962  mov     rdx, rdi
0x140052965  mov     rcx, r15
0x140052968  call    UdfAcquireAllFiles
0x14005296d  nop
0x14005296e  lea     rcx, [rdi+670h]; FastMutex
0x140052975  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14005297c  nop     dword ptr [rax+rax+00h]
0x140052981  mov     rax, gs:188h
0x14005298a  mov     [rdi+6A8h], rax
0x140052991  lea     rcx, [rdi+630h]; FastMutex
0x140052998  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14005299f  nop     dword ptr [rax+rax+00h]
0x1400529a4  mov     rax, gs:188h
0x1400529ad  mov     [rdi+668h], rax
0x1400529b4  lea     rcx, [rdi+6C8h]; Table
0x1400529bb  lea     rdx, [rsp+98h+RestartKey]; RestartKey
0x1400529c0  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x1400529c7  nop     dword ptr [rax+rax+00h]
0x1400529cc  mov     rsi, rax
0x1400529cf  test    rax, rax
0x1400529d2  jz      short loc_1400529D8
0x1400529d4  mov     rsi, [rax+8]
0x1400529d8  test    rsi, rsi
0x1400529db  jz      short loc_1400529E3
0x1400529dd  inc     dword ptr [rsi+0CCh]
0x1400529e3  mov     rax, [rsp+98h+var_58]
0x1400529e8  lea     rcx, [rdi+630h]; FastMutex
0x1400529ef  test    rax, rax
0x1400529f2  jz      short loc_140052A51
0x1400529f4  dec     dword ptr [rax+0CCh]
0x1400529fa  mov     qword ptr [rdi+668h], 0
0x140052a05  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140052a0c  nop     dword ptr [rax+rax+00h]
0x140052a11  mov     qword ptr [rdi+6A8h], 0
0x140052a1c  lea     rcx, [rdi+670h]; FastMutex
0x140052a23  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140052a2a  nop     dword ptr [rax+rax+00h]
0x140052a2f  lea     rax, [rsp+98h+arg_18]
0x140052a37  mov     [rsp+98h+var_78], rax
0x140052a3c  mov     r9b, 1
0x140052a3f  xor     r8d, r8d
0x140052a42  mov     rdx, [rsp+98h+var_58]
0x140052a47  mov     rcx, r15
0x140052a4a  call    UdfTeardownStructures
0x140052a4f  jmp     short loc_140052A86
0x140052a51  mov     qword ptr [rdi+668h], 0
0x140052a5c  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140052a63  nop     dword ptr [rax+rax+00h]
0x140052a68  mov     qword ptr [rdi+6A8h], 0
0x140052a73  lea     rcx, [rdi+670h]; FastMutex
0x140052a7a  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140052a81  nop     dword ptr [rax+rax+00h]
0x140052a86  test    rsi, rsi
0x140052a89  jnz     loc_1400530FE
0x140052a8f  xor     r13d, r13d
0x140052a92  test    r12b, r12b
0x140052a95  jz      loc_140052E6C
0x140052a9b  bt      dword ptr [rdi+30h], 15h
0x140052aa0  jnb     short loc_140052AAD
0x140052aa2  mov     rdx, rdi
0x140052aa5  mov     rcx, r15
0x140052aa8  call    UdfSeqCacheFlush
0x140052aad  mov     rcx, [rdi+140h]
0x140052ab4  test    rcx, rcx
0x140052ab7  jz      short loc_140052AF3
0x140052ab9  mov     rcx, [rcx+1A8h]
0x140052ac0  add     rcx, 8; SectionObjectPointer
0x140052ac4  lea     r9, [rsp+98h+IoStatus]; IoStatus
0x140052ac9  xor     r8d, r8d; Length
0x140052acc  xor     edx, edx; FileOffset
0x140052ace  call    cs:__imp_CcFlushCache
0x140052ad5  nop     dword ptr [rax+rax+00h]
0x140052ada  mov     eax, dword ptr [rsp+98h+IoStatus]
0x140052ade  test    eax, eax
0x140052ae0  jns     short loc_140052AF3
0x140052ae2  test    ebx, ebx
0x140052ae4  cmovns  ebx, eax
0x140052ae7  mov     [rsp+98h+var_64], ebx
0x140052aeb  mov     r14b, 1
0x140052aee  mov     [rsp+98h+var_68], r14b
0x140052af3  mov     eax, [rdi+30h]
0x140052af6  bt      eax, 1Bh
0x140052afa  jnb     short loc_140052B46
0x140052afc  mov     rax, [rdi+148h]
0x140052b03  mov     rcx, [rax+1A8h]
0x140052b0a  add     rcx, 8; SectionObjectPointer
0x140052b0e  lea     r9, [rsp+98h+IoStatus]; IoStatus
0x140052b13  xor     r8d, r8d; Length
0x140052b16  xor     edx, edx; FileOffset
0x140052b18  call    cs:__imp_CcFlushCache
0x140052b1f  nop     dword ptr [rax+rax+00h]
0x140052b24  mov     eax, dword ptr [rsp+98h+IoStatus]
0x140052b28  test    eax, eax
0x140052b2a  jns     loc_140052C36
0x140052b30  test    ebx, ebx
0x140052b32  cmovns  ebx, eax
0x140052b35  mov     [rsp+98h+var_64], ebx
0x140052b39  mov     r14b, 1
0x140052b3c  mov     [rsp+98h+var_68], r14b
0x140052b41  jmp     loc_140052C36
0x140052b46  bt      eax, 1Dh
0x140052b4a  jnb     loc_140052C36
0x140052b50  bt      eax, 15h
0x140052b54  jnb     short loc_140052B61
0x140052b56  mov     rdx, rdi
0x140052b59  mov     rcx, r15
0x140052b5c  call    UdfSeqCacheFlush
0x140052b61  mov     rdx, [rdi+140h]
0x140052b68  xor     r9d, r9d
0x140052b6b  xor     r8d, r8d
0x140052b6e  mov     rdx, [rdx+10h]
0x140052b72  mov     rcx, r15
0x140052b75  call    UdfAcquireResource
0x140052b7a  mov     rcx, [rdi+148h]
0x140052b81  bt      dword ptr [rcx+0D4h], 1Dh
0x140052b89  jnb     loc_140052C1F
0x140052b8f  mov     rax, [rdi+140h]
0x140052b96  movups  xmm0, xmmword ptr [rax+0E8h]
0x140052b9d  movups  xmmword ptr [rcx+0E8h], xmm0
0x140052ba4  movups  xmm1, xmmword ptr [rax+0F8h]
0x140052bab  movups  xmmword ptr [rcx+0F8h], xmm1
0x140052bb2  mov     rdx, [rdi+148h]
0x140052bb9  xor     r9d, r9d
0x140052bbc  xor     r8d, r8d
0x140052bbf  mov     rdx, [rdx+10h]
0x140052bc3  mov     rcx, r15
0x140052bc6  call    UdfAcquireResource
0x140052bcb  or      r9d, 0FFFFFFFFh
0x140052bcf  xor     r8d, r8d
0x140052bd2  mov     rdx, [rdi+148h]
0x140052bd9  mov     rcx, r15
0x140052bdc  call    UdfUpdateAdsFromScb
0x140052be1  mov     rcx, [rdi+148h]
0x140052be8  mov     rcx, [rcx+10h]; Resource
0x140052bec  call    cs:__imp_ExReleaseResourceLite
0x140052bf3  nop     dword ptr [rax+rax+00h]
0x140052bf8  mov     rax, [rdi+148h]
0x140052bff  xorps   xmm0, xmm0
0x140052c02  movups  xmmword ptr [rax+0E8h], xmm0
0x140052c09  movups  xmmword ptr [rax+0F8h], xmm0
0x140052c10  mov     rax, [rdi+148h]
0x140052c17  btr     dword ptr [rax+0D4h], 1Dh
0x140052c1f  mov     rcx, [rdi+140h]
0x140052c26  mov     rcx, [rcx+10h]; Resource
0x140052c2a  call    cs:__imp_ExReleaseResourceLite
0x140052c31  nop     dword ptr [rax+rax+00h]
0x140052c36  bt      dword ptr [rdi+30h], 15h
0x140052c3b  jnb     short loc_140052C48
0x140052c3d  mov     rdx, rdi
0x140052c40  mov     rcx, r15
0x140052c43  call    UdfSeqCacheFlush
0x140052c48  mov     rcx, [rdi+150h]
0x140052c4f  test    rcx, rcx
0x140052c52  jz      short loc_140052C8E
0x140052c54  mov     rcx, [rcx+1A8h]
0x140052c5b  add     rcx, 8; SectionObjectPointer
0x140052c5f  lea     r9, [rsp+98h+IoStatus]; IoStatus
0x140052c64  xor     r8d, r8d; Length
0x140052c67  xor     edx, edx; FileOffset
0x140052c69  call    cs:__imp_CcFlushCache
0x140052c70  nop     dword ptr [rax+rax+00h]
0x140052c75  mov     eax, dword ptr [rsp+98h+IoStatus]
0x140052c79  test    eax, eax
0x140052c7b  jns     short loc_140052C8E
0x140052c7d  test    ebx, ebx
0x140052c7f  cmovns  ebx, eax
0x140052c82  mov     [rsp+98h+var_64], ebx
0x140052c86  mov     r14b, 1
0x140052c89  mov     [rsp+98h+var_68], r14b
0x140052c8e  mov     rcx, [rdi+110h]
0x140052c95  test    rcx, rcx
0x140052c98  jz      short loc_140052CD4
0x140052c9a  mov     rcx, [rcx+1A8h]
0x140052ca1  add     rcx, 8; SectionObjectPointer
0x140052ca5  lea     r9, [rsp+98h+IoStatus]; IoStatus
0x140052caa  xor     r8d, r8d; Length
0x140052cad  xor     edx, edx; FileOffset
0x140052caf  call    cs:__imp_CcFlushCache
0x140052cb6  nop     dword ptr [rax+rax+00h]
0x140052cbb  mov     eax, dword ptr [rsp+98h+IoStatus]
0x140052cbf  test    eax, eax
0x140052cc1  jns     short loc_140052CD4
0x140052cc3  test    ebx, ebx
0x140052cc5  cmovns  ebx, eax
0x140052cc8  mov     [rsp+98h+var_64], ebx
0x140052ccc  mov     r14b, 1
0x140052ccf  mov     [rsp+98h+var_68], r14b
0x140052cd4  mov     rax, [rdi+128h]
0x140052cdb  test    rax, rax
0x140052cde  jz      short loc_140052D29
0x140052ce0  bts     dword ptr [rax+0D4h], 1Eh
0x140052ce8  mov     rax, [rdi+128h]
0x140052cef  mov     rcx, [rax+1A8h]
0x140052cf6  add     rcx, 8; SectionObjectPointer
0x140052cfa  lea     r9, [rsp+98h+IoStatus]; IoStatus
0x140052cff  xor     r8d, r8d; Length
0x140052d02  xor     edx, edx; FileOffset
0x140052d04  call    cs:__imp_CcFlushCache
0x140052d0b  nop     dword ptr [rax+rax+00h]
0x140052d10  mov     eax, dword ptr [rsp+98h+IoStatus]
0x140052d14  test    eax, eax
0x140052d16  jns     short loc_140052D29
0x140052d18  test    ebx, ebx
0x140052d1a  cmovns  ebx, eax
0x140052d1d  mov     [rsp+98h+var_64], ebx
0x140052d21  mov     r14b, 1
0x140052d24  mov     [rsp+98h+var_68], r14b
0x140052d29  mov     rcx, [rdi+160h]
0x140052d30  test    rcx, rcx
0x140052d33  jz      short loc_140052D6F
0x140052d35  mov     rcx, [rcx+1A8h]
0x140052d3c  add     rcx, 8; SectionObjectPointer
0x140052d40  lea     r9, [rsp+98h+IoStatus]; IoStatus
0x140052d45  xor     r8d, r8d; Length
0x140052d48  xor     edx, edx; FileOffset
0x140052d4a  call    cs:__imp_CcFlushCache
0x140052d51  nop     dword ptr [rax+rax+00h]
0x140052d56  mov     eax, dword ptr [rsp+98h+IoStatus]
0x140052d5a  test    eax, eax
0x140052d5c  jns     short loc_140052D6F
0x140052d5e  test    ebx, ebx
0x140052d60  cmovns  ebx, eax
  ... truncated ...
```
