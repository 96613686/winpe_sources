# StorPortUnitIdleState

- ea: `0x14002eea0`
- end: `0x14002fb14`
- name: `StorPortUnitIdleState`
- size: `3188`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14000f4bc`

## callees

- `0x1400016cc`
- `0x14000befc`
- `0x140012174`
- `0x14002eea0`
- `0x14004edf4`
- `0x14006672c`
- `0x14014b440`

## import_xrefs

- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14002f7a1`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14002f7a1`
- `ntoskrnl!PoFxIdleComponent` at `0x14002f3b0`
- `ntoskrnl!PoFxIdleComponent` at `0x14002f3b0`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002eecc`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002f28c`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002f33f`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002eecc`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002f28c`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002f33f`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002efcb`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002f406`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002f473`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002efcb`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002f406`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002f473`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002f76a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002f76a`
- `ntoskrnl!PoFxActivateComponent` at `0x14002f08e`
- `ntoskrnl!PoFxActivateComponent` at `0x14002f730`
- `ntoskrnl!PoFxActivateComponent` at `0x14002f08e`
- `ntoskrnl!PoFxActivateComponent` at `0x14002f730`
- `ntoskrnl!PoFxCompleteIdleState` at `0x14002efab`
- `ntoskrnl!PoFxCompleteIdleState` at `0x14002efab`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002f7b2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002f99b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002f7b2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002f99b`

## pseudocode

```c
void __fastcall StorPortUnitIdleState(__int64 a1, unsigned int a2, unsigned int a3)
{
  __int64 v4; // r15
  int v6; // r8d
  __int64 *v7; // rdi
  __int64 v8; // rdx
  union _SLIST_HEADER **v9; // r14
  int v10; // r8d
  __int64 v11; // r8
  int v12; // edx
  unsigned int v13; // edx
  union _SLIST_HEADER *v14; // rdi
  union _SLIST_HEADER *v15; // rcx
  __int64 *v16; // rdx
  _QWORD *v17; // r9
  union _SLIST_HEADER *v18; // rdi
  char v19; // r14
  unsigned __int64 Region; // rbp
  unsigned __int64 v21; // rcx
  int *v22; // rax
  int v23; // edx
  char v24; // r12
  union _SLIST_HEADER *v25; // rbp
  char v26; // r12
  unsigned __int64 v27; // r13
  unsigned __int64 v28; // rcx
  int *v29; // rax
  int v30; // edx
  char v31; // al
  _DWORD *v32; // rax
  __int64 v33; // rdx
  int *v34; // rax
  int v35; // ecx
  _DWORD *v36; // rax
  __int64 v37; // rdx
  int *v38; // rax
  int v39; // ecx
  _DWORD *v40; // rax
  _DWORD *v41; // rax
  unsigned __int64 v42; // rdx
  union _SLIST_HEADER *v43; // rax
  __int64 v44; // r10
  __int64 v45; // r11
  __int64 v46; // r13
  int Alignment; // ecx
  union _SLIST_HEADER *v48; // rbp
  __int64 p_Region; // rcx
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 v52; // r9
  unsigned int v53; // ebp
  int *v54; // rcx
  int v55; // eax
  __int64 v56; // rax
  _DWORD *v57; // rcx
  union _SLIST_HEADER *v58; // rax
  int v59; // ecx
  union _SLIST_HEADER *v60; // rdi
  __int64 v61; // rcx
  union _SLIST_HEADER *v62; // rcx
  void (__fastcall *v63)(unsigned __int64, __int64, struct _KLOCK_QUEUE_HANDLE *, __int64); // rax
  volatile signed __int64 *v64; // r13
  KSPIN_LOCK *p_Alignment; // rcx
  union _SLIST_HEADER *v66; // rcx
  __int64 v67; // rdx
  __int64 v68; // rcx
  __int64 v69; // r8
  __int64 v70; // r9
  int v71; // eax
  __int64 v72; // rcx
  _DWORD *v73; // r10
  __int64 v74; // rcx
  _DWORD *v75; // r9
  int v76; // eax
  __int64 v77; // rcx
  _DWORD *v78; // r10
  __int64 v79; // rcx
  _DWORD *v80; // r10
  __int64 v81; // rcx
  _DWORD *v82; // r10
  __int64 v83; // rcx
  _DWORD *v84; // r10
  __int64 v85; // rcx
  _DWORD *v86; // r9
  __int64 v87; // rcx
  _DWORD *v88; // r9
  __int64 v89; // rcx
  _DWORD *v90; // r9
  __int64 v91; // rcx
  _DWORD *v92; // r9
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+50h] [rbp-48h] BYREF

  v4 = a2;
  if ( (*(_DWORD *)(a1 + 504) & 0x8000) != 0
    && ExAcquireRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 1864)) )
  {
    if ( StorEtwLoggingEnabled && (byte_140177432 & 0x10) != 0 )
      McTemplateK0pquuuqq_EtwWriteTransfer(
        *(_QWORD *)(a1 + 24),
        (unsigned int)EventUnitIdleStateStart,
        v6,
        **(_QWORD **)(a1 + 1872),
        *(_DWORD *)(*(_QWORD *)(a1 + 24) + 56LL),
        *(_BYTE *)(a1 + 104),
        *(_BYTE *)(a1 + 105),
        *(_BYTE *)(a1 + 106),
        v4,
        a3);
    v7 = (__int64 *)(a1 + 1872);
    if ( a3 )
    {
      v9 = (union _SLIST_HEADER **)(a1 + 24);
      v11 = *v7;
      *(_QWORD *)(a1 + 2136) = MEMORY[0xFFFFF78000000008];
      v12 = *(_DWORD *)(v11 + 32);
      if ( (*(_BYTE *)(*(_QWORD *)(a1 + 24) + 108LL) & 1) != 0 )
        v13 = v12 | 0x40;
      else
        v13 = v12 & 0xFFFFFFBF;
      *(_DWORD *)(v11 + 32) = v13;
    }
    else
    {
      ++*(_DWORD *)(a1 + 2188);
      v8 = *(_QWORD *)(a1 + 2136);
      if ( v8 )
      {
        if ( (*(_DWORD *)(*v7 + 32) & 0x40) != 0 || (*(_BYTE *)(*(_QWORD *)(a1 + 24) + 108LL) & 1) != 0 )
        {
          v42 = (MEMORY[0xFFFFF78000000008] - v8) / 0x2710uLL;
          *(_QWORD *)(a1 + 2144) += v42;
          if ( v42 >= 0x2710 )
            ++*(_DWORD *)(a1 + 2196);
        }
        *(_QWORD *)(a1 + 2136) = 0;
      }
      v9 = (union _SLIST_HEADER **)(a1 + 24);
    }
    *(_DWORD *)(*v7 + 16) = a3;
    if ( !*(_DWORD *)(a1 + 1040) || !a3 )
    {
LABEL_11:
      if ( (*(_DWORD *)(*v7 + 32) & 4) != 0 )
      {
        v43 = *v9;
        v44 = 256;
        v45 = 264;
        v46 = 272;
        Alignment = (*v9)->Alignment;
        if ( Alignment == 1094997074 )
        {
          v48 = (union _SLIST_HEADER *)((char *)v43 + 360);
          p_Region = (__int64)&v43[38].Region;
          v50 = (__int64)&v43[39];
          v51 = (__int64)&v43[39].Region;
          v52 = (__int64)&v43[40];
        }
        else if ( Alignment == 1314275652 )
        {
          v48 = v43 + 11;
          p_Region = (__int64)&v43[27];
          v50 = (__int64)&v43[27].Region;
          v51 = (__int64)&v43[28];
          v52 = (__int64)&v43[28].Region;
        }
        else
        {
          v48 = 0;
          p_Region = 256;
          v50 = 264;
          v51 = 272;
          v52 = 280;
        }
        if ( *(_DWORD *)v48[14].Region == 208 )
        {
          if ( (*((_DWORD *)&v48[15].HeaderX64 + 2) & 0x10) == 0 )
          {
            *(_QWORD *)p_Region = 0;
            *(_QWORD *)v50 = 0;
            *(_QWORD *)v51 = 0;
            *(_QWORD *)v52 = 0;
            *((_DWORD *)&v48[15].HeaderX64 + 3) = 12;
            if ( (unsigned __int8)RaMiniportIsFeatureSupported(v48, 0) )
              *v73 = 13;
            if ( (unsigned __int8)RaMiniportIsFeatureSupported(v72, 1) )
              *v78 = 14;
            if ( (unsigned __int8)RaMiniportIsFeatureSupported(v77, 4) )
              *v80 = 15;
            if ( (unsigned __int8)RaMiniportIsFeatureSupported(v79, 11) )
              LODWORD(v48[18].Alignment) = 16;
            if ( (*(_DWORD *)(v48[14].Region + 184) & 0x20000) != 0 )
              *v82 = 17;
            if ( (unsigned __int8)RaMiniportIsFeatureSupported(v81, 14) )
              *v84 = 32;
            if ( (int)RaCallMiniportUnitControl(v83, 0, v84) < 0 )
              goto LABEL_12;
            *((_DWORD *)&v48[15].HeaderX64 + 2) |= 0x10u;
            v44 = 256;
            v45 = 264;
          }
          if ( *((_BYTE *)&v48[16].HeaderX64 + 7) )
          {
            v53 = 1;
            v54 = *(int **)(*v7 + 8);
            v55 = *v54;
            if ( *v54 == 1 )
            {
              if ( (unsigned int)v4 >= v54[2] )
                goto LABEL_124;
              v56 = (v4 << 6) + 16;
            }
            else
            {
              if ( v55 == 2 )
              {
                if ( (unsigned int)v4 >= v54[2] )
                  goto LABEL_124;
              }
              else if ( v55 != 3 || (unsigned int)v4 >= v54[2] )
              {
                goto LABEL_124;
              }
              v56 = (v4 << 6) + 24;
            }
            v57 = (int *)((char *)v54 + v56);
            if ( v57 && *v57 == 2 )
              v53 = v57[8];
LABEL_124:
            if ( ((*v9)[7].Alignment & 0x40) != 0 )
              v53 = 1;
            if ( a3 <= v53
              && (*v9)[314].Alignment
              && !_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 3616), 1, 0) )
            {
              v64 = (volatile signed __int64 *)*v9;
              if ( (*((_BYTE *)&(*v9)[6].HeaderX64 + 12) & 1) != 0 )
              {
                _InterlockedIncrement64(v64 + 668);
                if ( (*((_BYTE *)v64 + 108) & 2) != 0 )
                  _InterlockedIncrement64(v64 + 669);
              }
              PoFxActivateComponent(**((_QWORD **)v64 + 628), 0, 0);
              if ( (*(_DWORD *)(*((_QWORD *)v64 + 628) + 20LL) & 1) == 0 )
              {
                p_Alignment = &(*v9)[5].Alignment;
                memset(&LockHandle, 0, sizeof(LockHandle));
                KeAcquireInStackQueuedSpinLock(p_Alignment, &LockHandle);
                v66 = *v9;
                if ( *((int *)&(*v9)[20].HeaderX64 + 3) > 1 )
                {
                  *(_BYTE *)(a1 + 2040) = 1;
                  *(_DWORD *)(a1 + 2044) = a3;
                  ExpInterlockedPushEntrySList(v66 + 313, (PSLIST_ENTRY)(a1 + 2064));
                  KeReleaseInStackQueuedSpinLock(&LockHandle);
                  if ( !StorEtwLoggingEnabled || (byte_140177432 & 0x10) == 0 )
                    goto LABEL_15;
                  v15 = *v9;
                  v16 = EventUnitIdleStateQueued;
                  v17 = (_QWORD *)*v7;
                  goto LABEL_231;
                }
                KeReleaseInStackQueuedSpinLock(&LockHandle);
              }
              v46 = 272;
              v45 = 264;
              v44 = 256;
            }
            v58 = *v9;
            v59 = (*v9)->Alignment;
            if ( v59 == 1094997074 )
            {
              v60 = (union _SLIST_HEADER *)((char *)v58 + 360);
              v44 = (__int64)&v58[38].Region;
              v45 = (__int64)&v58[39];
              v46 = (__int64)&v58[39].Region;
              v61 = (__int64)&v58[40];
            }
            else if ( v59 == 1314275652 )
            {
              v60 = v58 + 11;
              v44 = (__int64)&v58[27];
              v45 = (__int64)&v58[27].Region;
              v46 = (__int64)&v58[28];
              v61 = (__int64)&v58[28].Region;
            }
            else
            {
              v60 = 0;
              v61 = 280;
            }
            if ( *(_DWORD *)v60[14].Region != 208 )
              goto LABEL_135;
            if ( (*((_DWORD *)&v60[15].HeaderX64 + 2) & 0x10) == 0 )
            {
              *(_QWORD *)v44 = 0;
              *(_QWORD *)v45 = 0;
              *(_QWORD *)v46 = 0;
              *(_QWORD *)v61 = 0;
              *((_DWORD *)&v60[15].HeaderX64 + 3) = 12;
              if ( (unsigned __int8)RaMiniportIsFeatureSupported(v60, 0) )
                *v75 = 13;
              if ( (unsigned __int8)RaMiniportIsFeatureSupported(v74, 1) )
                *v86 = 14;
              if ( (unsigned __int8)RaMiniportIsFeatureSupported(v85, 4) )
                *v88 = 15;
              if ( (unsigned __int8)RaMiniportIsFeatureSupported(v87, 11) )
                LODWORD(v60[18].Alignment) = 16;
              if ( (*(_DWORD *)(v60[14].Region + 184) & 0x20000) != 0 )
                *v90 = 17;
              if ( (unsigned __int8)RaMiniportIsFeatureSupported(v89, 14) )
                *v92 = 32;
              if ( (int)RaCallMiniportUnitControl(v91, 0, v92) < 0 )
                goto LABEL_135;
              *((_DWORD *)&v60[15].HeaderX64 + 2) |= 0x10u;
            }
            if ( *((_BYTE *)&v60[16].HeaderX64 + 7) )
            {
              v62 = *v9;
              LockHandle.LockQueue.Next = (_KSPIN_LOCK_QUEUE *volatile)0x1800000001LL;
              LockHandle.LockQueue.Lock = (unsigned __int64 *volatile)(a1 + 96);
              *(_DWORD *)&LockHandle.OldIrql = v4;
              *((_DWORD *)&LockHandle.OldIrql + 1) = a3;
              v63 = *(void (__fastcall **)(unsigned __int64, __int64, struct _KLOCK_QUEUE_HANDLE *, __int64))(v62[37].Alignment + 200);
              if ( v63 )
              {
                v63(v62[37].Region + 16, 7, &LockHandle, v52);
                Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v68, v67, v69, v70);
              }
            }
LABEL_135:
            if ( a3 > v53
              && (*v9)[314].Alignment
              && _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 3616), 0, 1) == 1 )
            {
              RaidAdapterPoFxIdleComponent(*v9, 0, 0, v52);
            }
            goto LABEL_13;
          }
        }
      }
LABEL_12:
      if ( (*((_BYTE *)&(*v9)[6].HeaderX64 + 14) & 0x40) != 0
        && (*(_DWORD *)(*v7 + 32) & 0x1000) != 0
        && (*v9)[314].Alignment )
      {
        if ( a3 )
        {
          if ( _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 3616), 0, 1) == 1 )
            PoFxIdleComponent(*(_QWORD *)(*v9)[314].Alignment, 0, 0);
        }
        else if ( !_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 3616), 1, 0) )
        {
          v14 = *v9;
          if ( (*((_BYTE *)&(*v9)[6].HeaderX64 + 12) & 1) != 0 )
          {
            _InterlockedIncrement64((volatile signed __int64 *)&v14[334]);
            if ( (*((_BYTE *)&v14[6].HeaderX64 + 12) & 2) != 0 )
              _InterlockedIncrement64((volatile signed __int64 *)&v14[334].Region);
          }
          PoFxActivateComponent(*(_QWORD *)v14[314].Alignment, 0, 0);
        }
      }
LABEL_13:
      if ( !*(_DWORD *)(a1 + 1040) || a3 )
        goto LABEL_14;
      v18 = *v9;
      v19 = 1;
      Region = v18[317].Region;
      if ( *((char *)&v18[6].HeaderX64 + 12) >= 0 )
      {
        if ( *((_DWORD *)&v18[20].HeaderX64 + 3) == 4 && !*((_DWORD *)&v18[6].HeaderX64 + 1) )
        {
          v76 = *((_DWORD *)&v18[23].HeaderX64 + 2);
          if ( v76 == 5 || v76 == 17 )
            goto LABEL_37;
          if ( (*((_BYTE *)&v18[6].HeaderX64 + 11) & 0x50) == 0x50 )
          {
            v24 = 0;
            goto LABEL_38;
          }
        }
        v21 = v18[314].Alignment;
        if ( !v21 )
          goto LABEL_55;
        v22 = *(int **)(v21 + 8);
        v23 = *v22;
        if ( *v22 == 1 )
        {
          if ( !v22[2] )
            goto LABEL_37;
          v32 = v22 + 4;
        }
        else
        {
          if ( v23 == 2 )
          {
            if ( !v22[2] )
              goto LABEL_37;
          }
          else if ( v23 != 3 || !v22[2] )
          {
            goto LABEL_37;
          }
          v32 = v22 + 6;
        }
        if ( v32 )
        {
          if ( *v32 < 2u )
          {
            if ( *v32 == 1 && (*((_BYTE *)&v18[6].HeaderX64 + 11) & 0x40) != 0 && *(_DWORD *)(v21 + 16) )
            {
              v24 = 0;
              goto LABEL_38;
            }
          }
          else if ( *(_DWORD *)(v21 + 16) > v32[9] )
          {
            v24 = 0;
            goto LABEL_38;
          }
LABEL_55:
          v24 = 1;
          if ( !Region
            || (*(_BYTE *)(Region + 506) & 4) != 0
            || *(_DWORD *)(Region + 548) == 4
            && !*(_DWORD *)(Region + 1044)
            && (*(_BYTE *)(Region + 505) & 0x44) == 0x44 )
          {
            v19 = 0;
LABEL_38:
            *((_BYTE *)&v18[309].HeaderX64 + 13) = v24;
            if ( Region )
            {
              *(_BYTE *)(Region + 1862) = v19;
              *(_BYTE *)(Region + 1863) = 0;
            }
            goto LABEL_14;
          }
          if ( (*(_DWORD *)(Region + 504) & 0x8000) == 0
            || !ExAcquireRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(Region + 1864)) )
          {
            goto LABEL_88;
          }
          v33 = *(_QWORD *)(Region + 1872);
          v34 = *(int **)(v33 + 8);
          v35 = *v34;
          if ( *v34 == 1 )
          {
            if ( !v34[2] )
              goto LABEL_63;
            v40 = v34 + 4;
          }
          else
          {
            if ( v35 == 2 )
            {
              if ( !v34[2] )
                goto LABEL_63;
            }
            else if ( v35 != 3 || !v34[2] )
            {
              goto LABEL_63;
            }
            v40 = v34 + 6;
          }
          if ( v40 )
          {
            if ( *v40 < 2u )
            {
              if ( *v40 == 1 && (*(_BYTE *)(Region + 505) & 0x40) != 0 && *(_DWORD *)(v33 + 16) )
                goto LABEL_63;
LABEL_87:
              ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(Region + 1864));
              if ( !v19 )
                goto LABEL_38;
LABEL_88:
              *((_BYTE *)&v18[309].HeaderX64 + 13) = 1;
              *(_BYTE *)(Region + 1862) = v19;
              *(_BYTE *)(Region + 1863) = 1;
LABEL_14:
              PoFxCompleteIdleState(**(_QWORD **)(a1 + 1872), (unsigned int)v4);
              if ( !StorEtwLoggingEnabled || (byte_140177432 & 0x10) == 0 )
                goto LABEL_15;
              v15 = *(union _SLIST_HEADER **)(a1 + 24);
              v16 = EventUnitIdleStateStop;
              v17 = *(_QWORD **)(a1 + 1872);
LABEL_231:
              McTemplateK0pquuuqq_EtwWriteTransfer(
                (_DWORD)v15,
                (_DWORD)v16,
                v10,
                *v17,
                *((_DWORD *)&v15[3].HeaderX64 + 2),
                *(_BYTE *)(a1 + 104),
                *(_BYTE *)(a1 + 105),
                *(_BYTE *)(a1 + 106),
                v4,
                a3);
LABEL_15:
              ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 1864));
              return;
            }
            if ( *(_DWORD *)(v33 + 16) <= v40[9] )
              goto LABEL_87;
          }
LABEL_63:
          v19 = 0;
          goto LABEL_87;
        }
      }
LABEL_37:
      v24 = 0;
      goto LABEL_38;
    }
    v25 = *v9;
    v26 = 1;
    v27 = (*v9)[317].Region;
    if ( *((char *)&(*v9)[6].HeaderX64 + 12) < 0 )
      goto LABEL_47;
    if ( *((_DWORD *)&v25[20].HeaderX64 + 3) == 4 && !*((_DWORD *)&v25[6].HeaderX64 + 1) )
    {
      v71 = *((_DWORD *)&v25[23].HeaderX64 + 2);
      if ( v71 == 5 || v71 == 17 )
        goto LABEL_47;
      if ( (*((_BYTE *)&v25[6].HeaderX64 + 11) & 0x50) == 0x50 )
      {
        v31 = 0;
        goto LABEL_48;
      }
    }
    v28 = v25[314].Alignment;
    if ( !v28 )
      goto LABEL_69;
    v29 = *(int **)(v28 + 8);
    v30 = *v29;
    if ( *v29 == 1 )
    {
      if ( !v29[2] )
        goto LABEL_47;
      v36 = v29 + 4;
    }
    else
    {
      if ( v30 == 2 )
      {
        if ( !v29[2] )
          goto LABEL_47;
      }
      else if ( v30 != 3 || !v29[2] )
      {
        goto LABEL_47;
      }
      v36 = v29 + 6;
    }
    if ( v36 )
    {
      if ( *v36 < 2u )
      {
        if ( *v36 == 1 && (*((_BYTE *)&v25[6].HeaderX64 + 11) & 0x40) != 0 && *(_DWORD *)(v28 + 16) )
        {
          v31 = 0;
          goto LABEL_48;
        }
      }
      else if ( *(_DWORD *)(v28 + 16) > v36[9] )
      {
        v31 = 0;
        goto LABEL_48;
      }
LABEL_69:
      v31 = 1;
      if ( !v27 || (*(_BYTE *)(v27 + 506) & 4) != 0 )
      {
        v26 = 0;
        goto LABEL_48;
      }
      if ( *(_DWORD *)(v27 + 548) == 4 && !*(_DWORD *)(v27 + 1044) && (*(_BYTE *)(v27 + 505) & 0x44) == 0x44 )
      {
        v26 = 0;
        goto LABEL_166;
      }
      if ( (*(_DWORD *)(v27 + 504) & 0x8000) == 0
        || !ExAcquireRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v27 + 1864)) )
      {
LABEL_96:
        *((_BYTE *)&v25[309].HeaderX64 + 13) = 1;
        *(_BYTE *)(v27 + 1862) = v26;
        *(_BYTE *)(v27 + 1863) = 1;
        goto LABEL_11;
      }
      v37 = *(_QWORD *)(v27 + 1872);
      v38 = *(int **)(v37 + 8);
      v39 = *v38;
      if ( *v38 == 1 )
      {
        if ( !v38[2] )
          goto LABEL_77;
        v41 = v38 + 4;
      }
      else
      {
        if ( v39 == 2 )
        {
          if ( !v38[2] )
            goto LABEL_77;
        }
        else if ( v39 != 3 || !v38[2] )
        {
          goto LABEL_77;
        }
        v41 = v38 + 6;
      }
      if ( v41 )
      {
        if ( *v41 < 2u )
        {
          if ( *v41 == 1 && (*(_BYTE *)(v27 + 505) & 0x40) != 0 && *(_DWORD *)(v37 + 16) )
            goto LABEL_77;
LABEL_95:
          ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v27 + 1864));
          if ( !v26 )
          {
LABEL_166:
            v31 = 1;
LABEL_48:
            *((_BYTE *)&v25[309].HeaderX64 + 13) = v31;
            if ( v27 )
            {
              *(_BYTE *)(v27 + 1862) = v26;
              *(_BYTE *)(v27 + 1863) = 0;
            }
            goto LABEL_11;
          }
          goto LABEL_96;
        }
        if ( *(_DWORD *)(v37 + 16) <= v41[9] )
          goto LABEL_95;
      }
LABEL_77:
      v26 = 0;
      goto LABEL_95;
    }
LABEL_47:
    v31 = 0;
    goto LABEL_48;
  }
}

```

## disassembly

```asm
0x14002eea0  push    rbx
0x14002eea2  push    rsi
0x14002eea3  push    r15
0x14002eea5  sub     rsp, 80h
0x14002eeac  mov     eax, [rcx+1F8h]
0x14002eeb2  mov     esi, r8d
0x14002eeb5  mov     r15d, edx
0x14002eeb8  mov     rbx, rcx
0x14002eebb  bt      eax, 0Fh
0x14002eebf  jnb     loc_14002EFF9
0x14002eec5  mov     rcx, [rcx+748h]; RunRefCacheAware
0x14002eecc  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x14002eed3  nop     dword ptr [rax+rax+00h]
0x14002eed8  test    al, al
0x14002eeda  jz      loc_14002EFF9
0x14002eee0  cmp     cs:StorEtwLoggingEnabled, 0
0x14002eee7  mov     [rsp+98h+arg_8], rdi
0x14002eeef  mov     [rsp+98h+arg_10], r12
0x14002eef7  jnz     loc_14002F0A9
0x14002eefd  mov     [rsp+98h+var_28], r14
0x14002ef02  lea     rdi, [rbx+750h]
0x14002ef09  test    esi, esi
0x14002ef0b  jnz     loc_14002F006
0x14002ef11  inc     dword ptr [rbx+88Ch]
0x14002ef17  mov     rdx, [rbx+858h]
0x14002ef1e  test    rdx, rdx
0x14002ef21  jz      short loc_14002EF4B
0x14002ef23  mov     rax, [rdi]
0x14002ef26  mov     ecx, [rax+20h]
0x14002ef29  test    cl, 40h
0x14002ef2c  jnz     loc_14002F4EF
0x14002ef32  mov     rax, [rbx+18h]
0x14002ef36  test    byte ptr [rax+6Ch], 1
0x14002ef3a  jnz     loc_14002F4EF
0x14002ef40  mov     qword ptr [rbx+858h], 0
0x14002ef4b  lea     r14, [rbx+18h]
0x14002ef4f  mov     rax, [rdi]
0x14002ef52  mov     [rsp+98h+arg_0], rbp
0x14002ef5a  mov     [rsp+98h+var_20], r13
0x14002ef5f  mov     [rax+10h], esi
0x14002ef62  cmp     dword ptr [rbx+410h], 0
0x14002ef69  ja      loc_14002F1A1
0x14002ef6f  mov     rax, [rdi]
0x14002ef72  mov     r12d, 1
0x14002ef78  mov     ecx, [rax+20h]
0x14002ef7b  test    cl, 4
0x14002ef7e  jnz     loc_14002F52F
0x14002ef84  mov     rdx, [r14]
0x14002ef87  test    byte ptr [rdx+6Eh], 40h
0x14002ef8b  jnz     loc_14002F03B
0x14002ef91  cmp     dword ptr [rbx+410h], 0
0x14002ef98  ja      loc_14002F121
0x14002ef9e  mov     rcx, [rbx+750h]
0x14002efa5  mov     edx, r15d
0x14002efa8  mov     rcx, [rcx]
0x14002efab  call    cs:__imp_PoFxCompleteIdleState
0x14002efb2  nop     dword ptr [rax+rax+00h]
0x14002efb7  cmp     cs:StorEtwLoggingEnabled, 0
0x14002efbe  jnz     loc_14002F0FD
0x14002efc4  mov     rcx, [rbx+748h]; RunRefCacheAware
0x14002efcb  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14002efd2  nop     dword ptr [rax+rax+00h]
0x14002efd7  mov     r13, [rsp+98h+var_20]
0x14002efdc  mov     rbp, [rsp+98h+arg_0]
0x14002efe4  mov     r14, [rsp+98h+var_28]
0x14002efe9  mov     rdi, [rsp+98h+arg_8]
0x14002eff1  mov     r12, [rsp+98h+arg_10]
0x14002eff9  add     rsp, 80h
0x14002f000  pop     r15
0x14002f002  pop     rsi
0x14002f003  pop     rbx
0x14002f004  retn
0x14002f006  mov     rax, ds:0FFFFF78000000008h
0x14002f010  lea     r14, [rbx+18h]
0x14002f014  mov     r8, [rdi]
0x14002f017  mov     [rbx+858h], rax
0x14002f01e  mov     rax, [r14]
0x14002f021  mov     edx, [r8+20h]
0x14002f025  test    byte ptr [rax+6Ch], 1
0x14002f029  jz      loc_14002F383
0x14002f02f  or      edx, 40h
0x14002f032  mov     [r8+20h], edx
0x14002f036  jmp     loc_14002EF4F
0x14002f03b  mov     rax, [rdi]
0x14002f03e  test    dword ptr [rax+20h], 1000h
0x14002f045  jz      loc_14002EF91
0x14002f04b  cmp     qword ptr [rdx+13A0h], 0
0x14002f053  jz      loc_14002EF91
0x14002f059  test    esi, esi
0x14002f05b  jnz     loc_14002F38B
0x14002f061  xor     eax, eax
0x14002f063  lock cmpxchg [rbx+0E20h], r12d
0x14002f06c  jnz     loc_14002EF91
0x14002f072  mov     rdi, [r14]
0x14002f075  test    byte ptr [rdi+6Ch], 1
0x14002f079  jnz     loc_14002F5D6
0x14002f07f  mov     rcx, [rdi+13A0h]
0x14002f086  xor     r8d, r8d
0x14002f089  xor     edx, edx
0x14002f08b  mov     rcx, [rcx]
0x14002f08e  call    cs:__imp_PoFxActivateComponent
0x14002f095  nop     dword ptr [rax+rax+00h]
0x14002f09a  mov     rax, [rdi+13A0h]
0x14002f0a1  mov     ecx, [rax+14h]
0x14002f0a4  jmp     loc_14002EF91
0x14002f0a9  test    cs:byte_140177432, 10h
0x14002f0b0  jz      loc_14002EEFD
0x14002f0b6  movzx   eax, byte ptr [rbx+6Ah]
0x14002f0ba  lea     rdx, EventUnitIdleStateStart
0x14002f0c1  mov     rcx, [rbx+18h]
0x14002f0c5  mov     r9, [rbx+750h]
0x14002f0cc  mov     [rsp+98h+var_50], esi
0x14002f0d0  mov     [rsp+98h+var_58], r15d
0x14002f0d5  mov     [rsp+98h+var_60], al
0x14002f0d9  movzx   eax, byte ptr [rbx+69h]
0x14002f0dd  mov     r9, [r9]
0x14002f0e0  mov     [rsp+98h+var_68], al
0x14002f0e4  movzx   eax, byte ptr [rbx+68h]
0x14002f0e8  mov     [rsp+98h+var_70], al
0x14002f0ec  mov     eax, [rcx+38h]
0x14002f0ef  mov     [rsp+98h+var_78], eax
0x14002f0f3  call    McTemplateK0pquuuqq_EtwWriteTransfer
0x14002f0f8  jmp     loc_14002EEFD
0x14002f0fd  test    cs:byte_140177432, 10h
0x14002f104  jz      loc_14002EFC4
0x14002f10a  mov     rcx, [rbx+18h]
0x14002f10e  lea     rdx, EventUnitIdleStateStop
0x14002f115  mov     r9, [rbx+750h]
0x14002f11c  jmp     loc_14014FAA3
0x14002f121  test    esi, esi
0x14002f123  jnz     loc_14002EF9E
0x14002f129  mov     rdi, [r14]
0x14002f12c  mov     r14b, 1
0x14002f12f  mov     rbp, [rdi+13D8h]
0x14002f136  cmp     [rdi+6Ch], sil
0x14002f13a  jl      short loc_14002F17A
0x14002f13c  cmp     dword ptr [rdi+14Ch], 4
0x14002f143  jz      loc_14002FA4B
0x14002f149  mov     rcx, [rdi+13A0h]
0x14002f150  test    rcx, rcx
0x14002f153  jz      loc_14002F24E
0x14002f159  mov     rax, [rcx+8]
0x14002f15d  mov     edx, [rax]
0x14002f15f  cmp     edx, 1
0x14002f162  jz      loc_14002F220
0x14002f168  cmp     edx, 2
0x14002f16b  jz      loc_14002F4A3
0x14002f171  cmp     edx, 3
0x14002f174  jz      loc_14002FA83
0x14002f17a  xor     r12b, r12b
0x14002f17d  mov     [rdi+135Dh], r12b
0x14002f184  test    rbp, rbp
0x14002f187  jz      loc_14002EF9E
0x14002f18d  xor     al, al
0x14002f18f  mov     [rbp+746h], r14b
0x14002f196  mov     [rbp+747h], al
0x14002f19c  jmp     loc_14002EF9E
0x14002f1a1  test    esi, esi
0x14002f1a3  jz      loc_14002EF6F
0x14002f1a9  mov     rbp, [r14]
0x14002f1ac  mov     r12b, 1
0x14002f1af  cmp     byte ptr [rbp+6Ch], 0
0x14002f1b3  mov     r13, [rbp+13D8h]
0x14002f1ba  jl      short loc_14002F1FA
0x14002f1bc  cmp     dword ptr [rbp+14Ch], 4
0x14002f1c3  jz      loc_14002F848
0x14002f1c9  mov     rcx, [rbp+13A0h]
0x14002f1d0  test    rcx, rcx
0x14002f1d3  jz      loc_14002F2FE
0x14002f1d9  mov     rax, [rcx+8]
0x14002f1dd  mov     edx, [rax]
0x14002f1df  cmp     edx, 1
0x14002f1e2  jz      loc_14002F2D0
0x14002f1e8  cmp     edx, 2
0x14002f1eb  jz      loc_14002F4B6
0x14002f1f1  cmp     edx, 3
0x14002f1f4  jz      loc_14002F87F
0x14002f1fa  xor     al, al
0x14002f1fc  mov     [rbp+135Dh], al
0x14002f202  test    r13, r13
0x14002f205  jz      loc_14002EF6F
0x14002f20b  xor     al, al
0x14002f20d  mov     [r13+746h], r12b
0x14002f214  mov     [r13+747h], al
0x14002f21b  jmp     loc_14002EF6F
0x14002f220  cmp     dword ptr [rax+8], 0
0x14002f224  jbe     loc_14002F17A
0x14002f22a  add     rax, 10h
0x14002f22e  test    rax, rax
0x14002f231  jz      loc_14002F17A
0x14002f237  mov     edx, [rax]
0x14002f239  cmp     edx, 2
0x14002f23c  jb      loc_14002FA9A
0x14002f242  mov     eax, [rax+24h]
0x14002f245  cmp     [rcx+10h], eax
0x14002f248  ja      loc_14002FA92
0x14002f24e  movzx   r12d, r14b
0x14002f252  test    rbp, rbp
0x14002f255  jz      loc_14002FADD
0x14002f25b  test    byte ptr [rbp+1FAh], 4
0x14002f262  jnz     loc_14002FADD
0x14002f268  cmp     dword ptr [rbp+224h], 4
0x14002f26f  jz      loc_14002FABF
0x14002f275  mov     eax, [rbp+1F8h]
0x14002f27b  bt      eax, 0Fh
0x14002f27f  jnb     loc_14002F41B
0x14002f285  mov     rcx, [rbp+748h]; RunRefCacheAware
0x14002f28c  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x14002f293  nop     dword ptr [rax+rax+00h]
0x14002f298  test    al, al
0x14002f29a  jz      loc_14002F41B
0x14002f2a0  mov     rdx, [rbp+750h]
0x14002f2a7  mov     rax, [rdx+8]
0x14002f2ab  mov     ecx, [rax]
0x14002f2ad  cmp     ecx, 1
0x14002f2b0  jz      loc_14002F3CB
0x14002f2b6  cmp     ecx, 2
0x14002f2b9  jz      loc_14002F4C9
0x14002f2bf  cmp     ecx, 3
0x14002f2c2  jz      loc_14002FAE5
0x14002f2c8  xor     r14b, r14b
0x14002f2cb  jmp     loc_14002F3FF
0x14002f2d0  cmp     dword ptr [rax+8], 0
0x14002f2d4  jbe     loc_14002F1FA
0x14002f2da  add     rax, 10h
0x14002f2de  test    rax, rax
0x14002f2e1  jz      loc_14002F1FA
0x14002f2e7  mov     edx, [rax]
0x14002f2e9  cmp     edx, 2
0x14002f2ec  jb      loc_14002F895
0x14002f2f2  mov     eax, [rax+24h]
0x14002f2f5  cmp     [rcx+10h], eax
0x14002f2f8  ja      loc_14002F88E
0x14002f2fe  movzx   eax, r12b
0x14002f302  test    r13, r13
0x14002f305  jz      loc_14002F8B9
0x14002f30b  test    byte ptr [r13+1FAh], 4
0x14002f313  jnz     loc_14002F8B9
0x14002f319  cmp     dword ptr [r13+224h], 4
0x14002f321  jz      loc_14002F8C1
0x14002f327  mov     eax, [r13+1F8h]
0x14002f32e  bt      eax, 0Fh
0x14002f332  jnb     loc_14002F488
0x14002f338  mov     rcx, [r13+748h]; RunRefCacheAware
0x14002f33f  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x14002f346  nop     dword ptr [rax+rax+00h]
0x14002f34b  test    al, al
0x14002f34d  jz      loc_14002F488
0x14002f353  mov     rdx, [r13+750h]
0x14002f35a  mov     rax, [rdx+8]
0x14002f35e  mov     ecx, [rax]
0x14002f360  cmp     ecx, 1
0x14002f363  jz      loc_14002F437
0x14002f369  cmp     ecx, 2
0x14002f36c  jz      loc_14002F4DC
0x14002f372  cmp     ecx, 3
0x14002f375  jz      loc_14002F8EB
0x14002f37b  xor     r12b, r12b
0x14002f37e  jmp     loc_14002F46C
0x14002f383  and     edx, 0FFFFFFBFh
0x14002f386  jmp     loc_14002F032
0x14002f38b  xor     ecx, ecx
0x14002f38d  mov     eax, r12d
0x14002f390  lock cmpxchg [rbx+0E20h], ecx
0x14002f398  jnz     loc_14002EF91
0x14002f39e  mov     rdi, [r14]
0x14002f3a1  xor     r8d, r8d
0x14002f3a4  xor     edx, edx
0x14002f3a6  mov     rcx, [rdi+13A0h]
0x14002f3ad  mov     rcx, [rcx]
0x14002f3b0  call    cs:__imp_PoFxIdleComponent
0x14002f3b7  nop     dword ptr [rax+rax+00h]
0x14002f3bc  mov     rax, [rdi+13A0h]
0x14002f3c3  mov     ecx, [rax+14h]
0x14002f3c6  jmp     loc_14002EF91
0x14002f3cb  cmp     dword ptr [rax+8], 0
0x14002f3cf  jbe     loc_14002F2C8
0x14002f3d5  add     rax, 10h
0x14002f3d9  test    rax, rax
0x14002f3dc  jz      loc_14002F2C8
0x14002f3e2  mov     ecx, [rax]
0x14002f3e4  cmp     ecx, 2
0x14002f3e7  jnb     loc_14002FAF4
0x14002f3ed  cmp     ecx, 1
0x14002f3f0  jnz     short loc_14002F3FF
0x14002f3f2  test    byte ptr [rbp+1F9h], 40h
0x14002f3f9  jnz     loc_14002FB05
0x14002f3ff  mov     rcx, [rbp+748h]; RunRefCacheAware
0x14002f406  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14002f40d  nop     dword ptr [rax+rax+00h]
0x14002f412  test    r14b, r14b
0x14002f415  jz      loc_14002F17D
0x14002f41b  movzx   eax, r12b
0x14002f41f  mov     [rdi+135Dh], al
0x14002f425  mov     [rbp+746h], r14b
0x14002f42c  mov     [rbp+747h], al
0x14002f432  jmp     loc_14002EF9E
0x14002f437  cmp     dword ptr [rax+8], 0
0x14002f43b  jbe     loc_14002F37B
0x14002f441  add     rax, 10h
  ... truncated ...
```
