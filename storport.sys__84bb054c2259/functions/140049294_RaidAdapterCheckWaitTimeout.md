# RaidAdapterCheckWaitTimeout

- ea: `0x140049294`
- end: `0x140049d1e`
- name: `RaidAdapterCheckWaitTimeout`
- size: `2698`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14004cb80`

## callees

- `0x14000e2dc`
- `0x1400172d0`
- `0x1400290b0`
- `0x140049294`
- `0x140049d24`
- `0x14006d1c0`
- `0x14006d298`
- `0x1400848c4`
- `0x1400991b8`
- `0x14014b400`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x140049480`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140049a26`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140049480`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140049a26`
- `ntoskrnl!KeSetEvent` at `0x1400493b7`
- `ntoskrnl!KeSetEvent` at `0x14004989b`
- `ntoskrnl!KeSetEvent` at `0x140049965`
- `ntoskrnl!KeSetEvent` at `0x1400493b7`
- `ntoskrnl!KeSetEvent` at `0x14004989b`
- `ntoskrnl!KeSetEvent` at `0x140049965`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400493fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400498ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049998`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400493fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400498ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049998`
- `ntoskrnl!IofCompleteRequest` at `0x140049719`
- `ntoskrnl!IofCompleteRequest` at `0x140049cd5`
- `ntoskrnl!IofCompleteRequest` at `0x140049719`
- `ntoskrnl!IofCompleteRequest` at `0x140049cd5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140049756`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140049756`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400497ec`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140049cf1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400497ec`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140049cf1`

## pseudocode

```c
void __fastcall RaidAdapterCheckWaitTimeout(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rax
  __int64 v4; // rcx
  _QWORD *v5; // rdi
  __int64 v6; // rbx
  __int64 v7; // r15
  char v8; // si
  unsigned __int64 v9; // r8
  signed __int32 v10; // eax
  signed __int32 v11; // ett
  __int64 v12; // rbx
  __int64 v13; // rax
  char v14; // al
  char v15; // cl
  char v16; // cl
  char v17; // al
  int v18; // eax
  char v19; // al
  bool v20; // zf
  unsigned __int64 v21; // rcx
  __int64 v22; // rdx
  int *v23; // rax
  int v24; // ecx
  __int64 *v25; // rdx
  _BYTE *v26; // rdx
  unsigned int v27; // esi
  unsigned __int8 v28; // r11
  char *v29; // rbx
  char v30; // r12
  _BYTE *v31; // r9
  __int64 v32; // rdi
  char v33; // r14
  unsigned __int64 v34; // r10
  __int64 v35; // r8
  int v36; // ecx
  char v37; // cl
  char v38; // bl
  char v39; // r8
  char v40; // r10
  _BYTE *v41; // rax
  unsigned int v42; // eax
  char v43; // al
  unsigned int v44; // r12d
  _QWORD *Pool; // r14
  __int64 v46; // rsi
  _QWORD *i; // rdi
  _QWORD *v48; // rbx
  unsigned int v49; // edi
  unsigned int v50; // esi
  __int64 v51; // rcx
  unsigned int v52; // eax
  __int64 v53; // r8
  unsigned __int64 v54; // r9
  signed __int32 v55; // eax
  signed __int32 v56; // ett
  __int64 v57; // rax
  __int64 v58; // rcx
  _QWORD *v59; // rdi
  __int64 v60; // r8
  __int64 v61; // rsi
  char v62; // r14
  __int64 v63; // rbx
  unsigned __int64 v64; // r9
  signed __int32 v65; // eax
  signed __int32 v66; // ett
  __int64 v67; // rax
  char v68; // al
  char v69; // cl
  char v70; // cl
  char v71; // al
  int v72; // eax
  char v73; // al
  unsigned __int64 v74; // rcx
  __int64 v75; // rdx
  int *v76; // rax
  int v77; // ecx
  __int64 *v78; // rdx
  __int64 v79; // rdx
  unsigned int v80; // r14d
  unsigned __int8 v81; // r10
  char *v82; // rbx
  char v83; // r12
  _BYTE *v84; // r9
  unsigned int v85; // edi
  char v86; // r15
  unsigned __int64 v87; // r11
  __int64 v88; // r8
  int v89; // ecx
  char v90; // cl
  char v91; // bl
  char v92; // r11
  _BYTE *v93; // rax
  char v94; // r8
  char *v95; // r8
  unsigned int v96; // eax
  char v97; // al
  _QWORD v98[2]; // [rsp+60h] [rbp-39h] BYREF
  unsigned int v99; // [rsp+70h] [rbp-29h]
  unsigned int v100; // [rsp+74h] [rbp-25h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+80h] [rbp-19h] BYREF
  __int128 v102; // [rsp+98h] [rbp-1h] BYREF

  v100 = DpcCompletionLimit;
  v2 = *(_QWORD *)(a1 + 1024);
  v98[1] = v98;
  v98[0] = v98;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v99 = GatewayCheckWaitTimeout(v2, (unsigned int)DpcCompletionLimit, v98);
  while ( 1 )
  {
    v3 = v98[0];
    if ( (_QWORD *)v98[0] == v98 )
      break;
    if ( *(_QWORD **)(v98[0] + 8LL) != v98 || (v4 = *(_QWORD *)v98[0], *(_QWORD *)(*(_QWORD *)v98[0] + 8LL) != v98[0]) )
LABEL_210:
      __fastfail(3u);
    v98[0] = *(_QWORD *)v98[0];
    *(_QWORD *)(v4 + 8) = v98;
    v5 = (_QWORD *)(v3 - 24);
    v6 = *(_QWORD *)(v3 - 24 + 48);
    v7 = *(_QWORD *)(v3 - 24 + 40);
    v8 = *(_BYTE *)(v6 + 506);
    RaidDeleteDeviceQueueEntry(v6 + 720, *(_BYTE *)(v7 + 142) & 1);
    _InterlockedIncrement64((volatile signed __int64 *)(v6 + 2248));
    v9 = (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 6;
    v10 = *(_DWORD *)(v9 + *(_QWORD *)(v6 + 40));
    while ( (v10 & 1) == 0 )
    {
      v11 = v10;
      v10 = _InterlockedCompareExchange((volatile signed __int32 *)(v9 + *(_QWORD *)(v6 + 40)), v10 - 2, v10);
      if ( v11 == v10 )
        goto LABEL_11;
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v6 + 1032), 0xFFFFFFFF) == 1 )
      KeSetEvent((PRKEVENT)(v6 + 520), 0, 0);
LABEL_11:
    v12 = *(_QWORD *)(*(_QWORD *)(v7 + 184) + 8LL);
    v13 = v5[2];
    if ( *(_BYTE *)(v12 + 2) == 40 )
    {
      *(_QWORD *)(v12 + 96) = v13;
    }
    else
    {
      *(_QWORD *)(v12 + 48) = v13;
      *(_QWORD *)(v12 + 56) = 0;
      *(_QWORD *)(v12 + 40) = 0;
    }
    ExFreePoolWithTag(v5, 0x54436152u);
    v14 = *(_BYTE *)(v12 + 2);
    v15 = *(_BYTE *)(v12 + 3);
    if ( (v8 & 2) != 0 )
    {
      if ( v14 == 40 )
      {
        v16 = ((v15 >> 7) & 0x80) + 56;
      }
      else
      {
        v17 = 56;
        if ( v15 < 0 )
          v17 = -72;
        v16 = v17;
      }
      v18 = -1073740534;
    }
    else
    {
      if ( v14 == 40 )
      {
        v16 = ((v15 >> 7) & 0x80) + 9;
      }
      else
      {
        v19 = 9;
        if ( v15 < 0 )
          v19 = -119;
        v16 = v19;
      }
      v18 = 258;
    }
    *(_BYTE *)(v12 + 3) = v16;
    v20 = StorEtwLoggingEnabled == 0;
    *(_BYTE *)(v7 + 141) = -84;
    *(_DWORD *)(v7 + 48) = v18;
    if ( v20 )
      goto LABEL_90;
    v102 = 0;
    IoGetActivityIdIrp(v7, &v102);
    v22 = *(_QWORD *)(v7 + 184);
    if ( *(_BYTE *)v22 == 14 )
    {
      if ( (byte_140177432 & 8) == 0 )
        goto LABEL_90;
      v25 = EventNonReadWriteRequestComplete;
      goto LABEL_40;
    }
    if ( *(_BYTE *)v22 != 15 )
    {
      if ( *(_BYTE *)v22 != 27 )
        goto LABEL_90;
      if ( *(_BYTE *)(v22 + 1) == 7 && !*(_DWORD *)(v22 + 8) )
      {
        if ( (byte_140177432 & 0x40) != 0 )
        {
          v23 = *(int **)(v7 + 56);
          if ( v23 )
            v24 = *v23;
          else
            v24 = 0;
          McTemplateK0pqd_EtwWriteTransfer(v24, v22, (unsigned int)&v102, v7, v24, *(_DWORD *)(v7 + 48));
        }
        goto LABEL_90;
      }
      if ( (byte_140177432 & 0x20) == 0 )
        goto LABEL_90;
      v25 = EventPnpRequestComplete;
LABEL_40:
      McTemplateK0pd_EtwWriteTransfer(v21, v25, &v102, v7, *(_DWORD *)(v7 + 48));
      goto LABEL_90;
    }
    if ( byte_140177431 >= 0 )
      goto LABEL_90;
    v26 = *(_BYTE **)(v22 + 8);
    if ( v26[2] == 40 )
    {
      if ( *((_DWORD *)v26 + 5) )
        goto LABEL_90;
      v27 = *((_DWORD *)v26 + 14);
      if ( !v27 )
        goto LABEL_90;
      v28 = 0;
      v29 = 0;
      v30 = 0;
      v31 = 0;
      v32 = 0;
      v33 = 0;
      while ( 1 )
      {
        v21 = *(unsigned int *)&v26[4 * v32 + 120];
        if ( (unsigned int)v21 >= 0x80 )
        {
          v34 = *((unsigned int *)v26 + 4);
          if ( (unsigned int)v21 < (unsigned int)v34 )
          {
            v35 = (unsigned int)v21;
            v36 = *(_DWORD *)&v26[v21] - 64;
            if ( v36 )
            {
              LODWORD(v21) = v36 - 1;
              if ( (_DWORD)v21 )
              {
                if ( (_DWORD)v21 == 1 )
                {
                  LODWORD(v21) = v35 + 40;
                  if ( v35 + 40 <= v34 )
                  {
                    if ( *(_DWORD *)&v26[v35 + 12] )
                      v29 = &v26[v35 + 32];
                    v31 = *(_BYTE **)&v26[v35 + 24];
                    goto LABEL_66;
                  }
                }
              }
              else
              {
                LODWORD(v21) = v35 + 56;
                if ( v35 + 56 <= v34 )
                {
                  v33 = 1;
                  if ( v26[v35 + 10] )
                    v29 = &v26[v35 + 24];
                  v30 = v26[v35 + 8];
                  v31 = *(_BYTE **)&v26[v35 + 16];
                  v28 = v26[v35 + 9];
                }
              }
            }
            else
            {
              LODWORD(v21) = v35 + 40;
              if ( v35 + 40 <= v34 )
              {
                if ( v26[v35 + 10] )
                  v29 = &v26[v35 + 24];
                v31 = *(_BYTE **)&v26[v35 + 16];
LABEL_66:
                v28 = v26[v35 + 9];
                v30 = v26[v35 + 8];
LABEL_67:
                if ( v29 )
                {
                  v37 = *v29;
                  goto LABEL_70;
                }
                goto LABEL_90;
              }
            }
            if ( v33 )
              goto LABEL_67;
          }
        }
        v32 = (unsigned int)(v32 + 1);
        if ( (unsigned int)v32 >= v27 )
          goto LABEL_67;
      }
    }
    v37 = v26[72];
    v31 = (_BYTE *)*((_QWORD *)v26 + 4);
    v28 = v26[11];
    v30 = v26[4];
    if ( v26[2] )
      goto LABEL_90;
LABEL_70:
    LOBYTE(v21) = v37 - 8;
    if ( (v21 & 0x5D) == 0 )
    {
      v38 = v26[3];
      if ( v38 == 1 || !v31 || !v28 )
        goto LABEL_88;
      v39 = 0;
      v40 = 0;
      LOBYTE(v26) = 0;
      v21 = (unsigned __int64)&v31[v28];
      v41 = v31 + 8;
      if ( (unsigned __int8)((*v31 & 0x7F) - 114) <= 1u )
      {
        if ( (unsigned __int64)v41 <= v21 )
        {
          v40 = v31[2];
          v39 = v31[1] & 0xF;
          LOBYTE(v26) = v31[3];
          goto LABEL_85;
        }
      }
      else if ( (unsigned __int64)v41 <= v21 )
      {
        v26 = v31 + 13;
        v39 = v31[2] & 0xF;
        v42 = v28;
        if ( (unsigned int)(unsigned __int8)v31[7] + 8 <= v28 )
          v42 = (unsigned __int8)v31[7] + 8;
        v21 = (unsigned __int64)&v31[v42];
        if ( (unsigned __int64)v26 <= v21 )
          v40 = v31[12];
        if ( (unsigned __int64)(v31 + 14) > v21 )
          LOBYTE(v26) = 0;
        else
          LOBYTE(v26) = *v26;
LABEL_85:
        v43 = 1;
LABEL_87:
        if ( !v43 )
        {
LABEL_88:
          v39 = 0;
          v40 = 0;
          LOBYTE(v26) = 0;
        }
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v21,
          (_DWORD)v26,
          (unsigned int)&v102,
          v7,
          *(_DWORD *)(v7 + 48),
          v38,
          v30,
          v39,
          v40,
          (char)v26,
          v7);
        goto LABEL_90;
      }
      v43 = 0;
      goto LABEL_87;
    }
LABEL_90:
    IofCompleteRequest((PIRP)v7, 0);
  }
  if ( v100 != v99 )
  {
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 136), &LockHandle);
    v44 = *(_DWORD *)(a1 + 160);
    if ( v44 )
    {
      Pool = (_QWORD *)RaidAllocatePool(64, 8LL * v44, 1280663890, *(_QWORD *)(a1 + 8));
      if ( Pool )
      {
        v46 = 0;
        for ( i = *(_QWORD **)(a1 + 144); i != (_QWORD *)(a1 + 144); i = (_QWORD *)*i )
        {
          v48 = i - 8;
          if ( *((_BYTE *)i + 3304)
            && (*((_DWORD *)v48 + 848) != -1 || (*((_BYTE *)v48 + 506) & 2) != 0)
            && (int)RaUnitAcquireRemoveLock(i - 8, 0, 0) >= 0 )
          {
            Pool[v46] = v48;
            v46 = (unsigned int)(v46 + 1);
          }
        }
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        if ( (unsigned int)v46 < v44 )
          Pool[v46] = 0;
        v49 = 0;
        v50 = v99;
        do
        {
          v51 = Pool[v49];
          if ( !v51 )
            break;
          if ( v100 > v50 )
          {
            v52 = RaidLunQueueCheckWaitTimeout(v51 + 720, v100 - v50, v98);
            v50 += v52;
            if ( v52 )
              _InterlockedAdd64((volatile signed __int64 *)(Pool[v49] + 2256LL), v52);
          }
          v53 = Pool[v49];
          v54 = (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 6;
          v55 = *(_DWORD *)(v54 + *(_QWORD *)(v53 + 40));
          while ( (v55 & 1) == 0 )
          {
            v56 = v55;
            v55 = _InterlockedCompareExchange((volatile signed __int32 *)(v54 + *(_QWORD *)(v53 + 40)), v55 - 2, v55);
            if ( v56 == v55 )
              goto LABEL_117;
          }
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v53 + 1032), 0xFFFFFFFF) == 1 )
            KeSetEvent((PRKEVENT)(v53 + 520), 0, 0);
LABEL_117:
          ++v49;
        }
        while ( v49 < v44 );
        ExFreePoolWithTag(Pool, 0x4C556152u);
        while ( 1 )
        {
          v57 = v98[0];
          if ( (_QWORD *)v98[0] == v98 )
            return;
          if ( *(_QWORD **)(v98[0] + 8LL) != v98 )
            goto LABEL_210;
          v58 = *(_QWORD *)v98[0];
          if ( *(_QWORD *)(*(_QWORD *)v98[0] + 8LL) != v98[0] )
            goto LABEL_210;
          v98[0] = *(_QWORD *)v98[0];
          v59 = (_QWORD *)(v57 - 24);
          *(_QWORD *)(v58 + 8) = v98;
          v60 = *(_QWORD *)(v57 - 24 + 48);
          v61 = *(_QWORD *)(v57 - 24 + 40);
          v62 = *(_BYTE *)(v60 + 506);
          v63 = *(_QWORD *)(*(_QWORD *)(v61 + 184) + 8LL);
          v64 = (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 6;
          v65 = *(_DWORD *)(v64 + *(_QWORD *)(v60 + 40));
          while ( (v65 & 1) == 0 )
          {
            v66 = v65;
            v65 = _InterlockedCompareExchange((volatile signed __int32 *)(v64 + *(_QWORD *)(v60 + 40)), v65 - 2, v65);
            if ( v66 == v65 )
              goto LABEL_128;
          }
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v60 + 1032), 0xFFFFFFFF) == 1 )
            KeSetEvent((PRKEVENT)(v60 + 520), 0, 0);
LABEL_128:
          v67 = v59[2];
          if ( *(_BYTE *)(v63 + 2) == 40 )
          {
            *(_QWORD *)(v63 + 96) = v67;
          }
          else
          {
            *(_QWORD *)(v63 + 48) = v67;
            *(_QWORD *)(v63 + 56) = 0;
            *(_QWORD *)(v63 + 40) = 0;
          }
          ExFreePoolWithTag(v59, 0x54436152u);
          v68 = *(_BYTE *)(v63 + 2);
          v69 = *(_BYTE *)(v63 + 3);
          if ( (v62 & 2) != 0 )
          {
            if ( v68 == 40 )
            {
              v70 = ((v69 >> 7) & 0x80) + 56;
            }
            else
            {
              v71 = 56;
              if ( v69 < 0 )
                v71 = -72;
              v70 = v71;
            }
            v72 = -1073740534;
          }
          else
          {
            if ( v68 == 40 )
            {
              v70 = ((v69 >> 7) & 0x80) + 9;
            }
            else
            {
              v73 = 9;
              if ( v69 < 0 )
                v73 = -119;
              v70 = v73;
            }
            v72 = 258;
          }
          *(_BYTE *)(v63 + 3) = v70;
          v20 = StorEtwLoggingEnabled == 0;
          *(_BYTE *)(v61 + 141) = -84;
          *(_DWORD *)(v61 + 48) = v72;
          if ( v20 )
            goto LABEL_209;
          v102 = 0;
          IoGetActivityIdIrp(v61, &v102);
          v75 = *(_QWORD *)(v61 + 184);
          if ( *(_BYTE *)v75 == 14 )
            break;
          if ( *(_BYTE *)v75 != 15 )
          {
            if ( *(_BYTE *)v75 != 27 )
              goto LABEL_209;
            if ( *(_BYTE *)(v75 + 1) == 7 && !*(_DWORD *)(v75 + 8) )
            {
              if ( (byte_140177432 & 0x40) != 0 )
              {
                v76 = *(int **)(v61 + 56);
                if ( v76 )
                  v77 = *v76;
                else
                  v77 = 0;
                McTemplateK0pqd_EtwWriteTransfer(v77, v75, (unsigned int)&v102, v61, v77, *(_DWORD *)(v61 + 48));
              }
              goto LABEL_209;
            }
            if ( (byte_140177432 & 0x20) == 0 )
              goto LABEL_209;
            v78 = EventPnpRequestComplete;
LABEL_208:
            McTemplateK0pd_EtwWriteTransfer(v74, v78, &v102, v61, *(_DWORD *)(v61 + 48));
            goto LABEL_209;
          }
          if ( byte_140177431 >= 0 )
            goto LABEL_209;
          v79 = *(_QWORD *)(v75 + 8);
          if ( *(_BYTE *)(v79 + 2) == 40 )
          {
            if ( *(_DWORD *)(v79 + 20) )
              goto LABEL_209;
            v80 = *(_DWORD *)(v79 + 56);
            if ( !v80 )
              goto LABEL_209;
            v81 = 0;
            v82 = 0;
            v83 = 0;
            v84 = 0;
            v85 = 0;
            v86 = 0;
            while ( 1 )
            {
              v74 = *(unsigned int *)(v79 + 4LL * v85 + 120);
              if ( (unsigned int)v74 >= 0x80 )
              {
                v87 = *(unsigned int *)(v79 + 16);
                if ( (unsigned int)v74 < (unsigned int)v87 )
                {
                  v88 = (unsigned int)v74;
                  v89 = *(_DWORD *)(v79 + v74) - 64;
                  if ( v89 )
                  {
                    LODWORD(v74) = v89 - 1;
                    if ( (_DWORD)v74 )
                    {
                      if ( (_DWORD)v74 == 1 )
                      {
                        LODWORD(v74) = v88 + 40;
                        if ( v88 + 40 <= v87 )
                        {
                          if ( *(_DWORD *)(v79 + v88 + 12) )
                            v82 = (char *)(v88 + v79 + 32);
                          v84 = *(_BYTE **)(v79 + v88 + 24);
                          goto LABEL_182;
                        }
                      }
                    }
                    else
                    {
                      LODWORD(v74) = v88 + 56;
                      if ( v88 + 56 <= v87 )
                      {
                        v86 = 1;
                        if ( *(_BYTE *)(v79 + v88 + 10) )
                          v82 = (char *)(v88 + v79 + 24);
                        v83 = *(_BYTE *)(v79 + v88 + 8);
                        v84 = *(_BYTE **)(v79 + v88 + 16);
                        v81 = *(_BYTE *)(v79 + v88 + 9);
                      }
                    }
                  }
                  else
                  {
                    LODWORD(v74) = v88 + 40;
                    if ( v88 + 40 <= v87 )
                    {
                      if ( *(_BYTE *)(v79 + v88 + 10) )
                        v82 = (char *)(v88 + v79 + 24);
                      v84 = *(_BYTE **)(v79 + v88 + 16);
LABEL_182:
                      v81 = *(_BYTE *)(v79 + v88 + 9);
                      v83 = *(_BYTE *)(v79 + v88 + 8);
LABEL_183:
                      if ( v82 )
                      {
                        v90 = *v82;
                        goto LABEL_186;
                      }
                      goto LABEL_209;
                    }
                  }
                  if ( v86 )
                    goto LABEL_183;
                }
              }
              if ( ++v85 >= v80 )
                goto LABEL_183;
            }
          }
          v90 = *(_BYTE *)(v79 + 72);
          v84 = *(_BYTE **)(v79 + 32);
          v81 = *(_BYTE *)(v79 + 11);
          v83 = *(_BYTE *)(v79 + 4);
          if ( *(_BYTE *)(v79 + 2) )
            goto LABEL_209;
LABEL_186:
          LOBYTE(v74) = v90 - 8;
          if ( (v74 & 0x5D) == 0 )
          {
            v91 = *(_BYTE *)(v79 + 3);
            if ( v91 == 1 || !v84 || !v81 )
              goto LABEL_204;
            LOBYTE(v79) = 0;
            v74 = (unsigned __int64)&v84[v81];
            v92 = 0;
            v93 = v84 + 8;
            v94 = 0;
            if ( (unsigned __int8)((*v84 & 0x7F) - 114) <= 1u )
            {
              if ( (unsigned __int64)v93 <= v74 )
              {
                v92 = v84[2];
                LOBYTE(v79) = v84[1] & 0xF;
                v94 = v84[3];
                goto LABEL_201;
              }
            }
            else if ( (unsigned __int64)v93 <= v74 )
            {
              v95 = v84 + 13;
              LOBYTE(v79) = v84[2] & 0xF;
              v96 = v81;
              if ( (unsigned int)(unsigned __int8)v84[7] + 8 <= v81 )
                v96 = (unsigned __int8)v84[7] + 8;
              v74 = (unsigned __int64)&v84[v96];
              if ( (unsigned __int64)v95 <= v74 )
                v92 = v84[12];
              if ( (unsigned __int64)(v84 + 14) > v74 )
                v94 = 0;
              else
                v94 = *v95;
LABEL_201:
              v97 = 1;
LABEL_203:
              if ( !v97 )
              {
LABEL_204:
                LOBYTE(v79) = 0;
                v92 = 0;
                v94 = 0;
              }
              McTemplateK0pduuuuup_EtwWriteTransfer(
                v74,
                v79,
                (unsigned int)&v102,
                v61,
                *(_DWORD *)(v61 + 48),
                v91,
                v83,
                v79,
                v92,
                v94,
                v61);
              goto LABEL_209;
            }
            v97 = 0;
            goto LABEL_203;
          }
LABEL_209:
          IofCompleteRequest((PIRP)v61, 0);
        }
        if ( (byte_140177432 & 8) == 0 )
          goto LABEL_209;
        v78 = EventNonReadWriteRequestComplete;
        goto LABEL_208;
      }
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
}

```

## disassembly

```asm
0x140049294  push    rbp
0x140049296  push    rbx
0x140049297  push    rsi
0x140049298  push    rdi
0x140049299  push    r12
0x14004929b  push    r13
0x14004929d  push    r14
0x14004929f  push    r15
0x1400492a1  lea     rbp, [rsp-1Fh]
0x1400492a6  sub     rsp, 0B8h
0x1400492ad  mov     rax, cs:__security_cookie
0x1400492b4  xor     rax, rsp
0x1400492b7  mov     [rbp+57h+var_48], rax
0x1400492bb  mov     ebx, cs:DpcCompletionLimit
0x1400492c1  lea     r8, [rbp+57h+var_90]
0x1400492c5  xor     eax, eax
0x1400492c7  mov     [rbp+57h+var_7C], ebx
0x1400492ca  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x1400492ce  mov     r13, rcx
0x1400492d1  mov     rcx, [rcx+400h]
0x1400492d8  lea     rax, [rbp+57h+var_90]
0x1400492dc  mov     [rbp+57h+var_88], rax
0x1400492e0  xorps   xmm0, xmm0
0x1400492e3  lea     rax, [rbp+57h+var_90]
0x1400492e7  mov     edx, ebx
0x1400492e9  mov     [rbp+57h+var_90], rax
0x1400492ed  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x1400492f1  call    GatewayCheckWaitTimeout
0x1400492f6  mov     [rbp+57h+var_80], eax
0x1400492f9  mov     r12d, 89h
0x1400492ff  mov     rax, [rbp+57h+var_90]
0x140049303  lea     rcx, [rbp+57h+var_90]
0x140049307  mov     r14d, 0B8h
0x14004930d  cmp     rax, rcx
0x140049310  jz      loc_14004973F
0x140049316  lea     rcx, [rbp+57h+var_90]
0x14004931a  cmp     [rax+8], rcx
0x14004931e  jnz     loc_140049CE6
0x140049324  mov     rcx, [rax]
0x140049327  cmp     [rcx+8], rax
0x14004932b  jnz     loc_140049CE6
0x140049331  mov     [rbp+57h+var_90], rcx
0x140049335  lea     rdx, [rbp+57h+var_90]
0x140049339  mov     [rcx+8], rdx
0x14004933d  lea     rdi, [rax-18h]
0x140049341  mov     rbx, [rdi+30h]
0x140049345  mov     r15, [rdi+28h]
0x140049349  mov     sil, [rbx+1FAh]
0x140049350  lea     rcx, [rbx+2D0h]
0x140049357  movzx   edx, byte ptr [r15+8Eh]
0x14004935f  and     edx, 1
0x140049362  call    RaidDeleteDeviceQueueEntry
0x140049367  lock inc qword ptr [rbx+8C8h]
0x14004936f  mov     eax, gs:1A4h
0x140049377  mov     r8d, eax
0x14004937a  mov     rax, [rbx+28h]
0x14004937e  shl     r8, 6
0x140049382  mov     eax, [r8+rax]
0x140049386  test    al, 1
0x140049388  jnz     short loc_14004939B
0x14004938a  mov     rcx, [rbx+28h]
0x14004938e  lea     edx, [rax-2]
0x140049391  lock cmpxchg [r8+rcx], edx
0x140049397  jnz     short loc_140049386
0x140049399  jmp     short loc_1400493C3
0x14004939b  or      eax, 0FFFFFFFFh
0x14004939e  lock xadd [rbx+408h], eax
0x1400493a6  cmp     eax, 1
0x1400493a9  jnz     short loc_1400493C3
0x1400493ab  lea     rcx, [rbx+208h]; Event
0x1400493b2  xor     r8d, r8d; Wait
0x1400493b5  xor     edx, edx; Increment
0x1400493b7  call    cs:__imp_KeSetEvent
0x1400493be  nop     dword ptr [rax+rax+00h]
0x1400493c3  mov     rax, [r15+0B8h]
0x1400493ca  mov     rbx, [rax+8]
0x1400493ce  mov     rax, [rdi+10h]
0x1400493d2  cmp     byte ptr [rbx+2], 28h ; '('
0x1400493d6  jnz     short loc_1400493DE
0x1400493d8  mov     [rbx+60h], rax
0x1400493dc  jmp     short loc_1400493F2
0x1400493de  mov     [rbx+30h], rax
0x1400493e2  mov     qword ptr [rbx+38h], 0
0x1400493ea  mov     qword ptr [rbx+28h], 0
0x1400493f2  mov     edx, 54436152h; Tag
0x1400493f7  mov     rcx, rdi; P
0x1400493fa  call    cs:__imp_ExFreePoolWithTag
0x140049401  nop     dword ptr [rax+rax+00h]
0x140049406  mov     al, [rbx+2]
0x140049409  mov     cl, [rbx+3]
0x14004940c  test    sil, 2
0x140049410  jz      short loc_140049435
0x140049412  cmp     al, 28h ; '('
0x140049414  jnz     short loc_140049421
0x140049416  sar     cl, 7
0x140049419  and     cl, 80h
0x14004941c  add     cl, 38h ; '8'
0x14004941f  jmp     short loc_14004942E
0x140049421  test    cl, cl
0x140049423  mov     eax, 38h ; '8'
0x140049428  cmovs   eax, r14d
0x14004942c  mov     cl, al
0x14004942e  mov     eax, 0C000050Ah
0x140049433  jmp     short loc_140049456
0x140049435  cmp     al, 28h ; '('
0x140049437  jnz     short loc_140049444
0x140049439  sar     cl, 7
0x14004943c  and     cl, 80h
0x14004943f  add     cl, 9
0x140049442  jmp     short loc_140049451
0x140049444  test    cl, cl
0x140049446  mov     eax, 9
0x14004944b  cmovs   eax, r12d
0x14004944f  mov     cl, al
0x140049451  mov     eax, 102h
0x140049456  mov     [rbx+3], cl
0x140049459  cmp     cs:StorEtwLoggingEnabled, 0
0x140049460  mov     byte ptr [r15+8Dh], 0ACh
0x140049468  mov     [r15+30h], eax
0x14004946c  jz      loc_140049714
0x140049472  xorps   xmm0, xmm0
0x140049475  lea     rdx, [rbp+57h+var_58]
0x140049479  mov     rcx, r15
0x14004947c  movups  [rbp+57h+var_58], xmm0
0x140049480  call    cs:__imp_IoGetActivityIdIrp
0x140049487  nop     dword ptr [rax+rax+00h]
0x14004948c  mov     rdx, [r15+0B8h]
0x140049493  movzx   eax, byte ptr [rdx]
0x140049496  sub     eax, 0Eh
0x140049499  jz      loc_14004972A
0x14004949f  sub     eax, 1
0x1400494a2  jz      short loc_14004951F
0x1400494a4  cmp     eax, 0Ch
0x1400494a7  jnz     loc_140049714
0x1400494ad  cmp     byte ptr [rdx+1], 7
0x1400494b1  jnz     short loc_1400494F2
0x1400494b3  cmp     dword ptr [rdx+8], 0
0x1400494b7  jnz     short loc_1400494F2
0x1400494b9  test    cs:byte_140177432, 40h
0x1400494c0  jz      loc_140049714
0x1400494c6  mov     rax, [r15+38h]
0x1400494ca  test    rax, rax
0x1400494cd  jz      short loc_1400494D3
0x1400494cf  mov     ecx, [rax]
0x1400494d1  jmp     short loc_1400494D5
0x1400494d3  xor     ecx, ecx
0x1400494d5  mov     eax, [r15+30h]
0x1400494d9  lea     r8, [rbp+57h+var_58]
0x1400494dd  mov     [rsp+0F0h+var_C8], eax
0x1400494e1  mov     r9, r15
0x1400494e4  mov     [rsp+0F0h+var_D0], ecx
0x1400494e8  call    McTemplateK0pqd_EtwWriteTransfer
0x1400494ed  jmp     loc_140049714
0x1400494f2  test    cs:byte_140177432, 20h
0x1400494f9  jz      loc_140049714
0x1400494ff  lea     rdx, EventPnpRequestComplete
0x140049506  mov     eax, [r15+30h]
0x14004950a  lea     r8, [rbp+57h+var_58]
0x14004950e  mov     r9, r15
0x140049511  mov     [rsp+0F0h+var_D0], eax
0x140049515  call    McTemplateK0pd_EtwWriteTransfer
0x14004951a  jmp     loc_140049714
0x14004951f  cmp     cs:byte_140177431, 0
0x140049526  jge     loc_140049714
0x14004952c  mov     rdx, [rdx+8]
0x140049530  movzx   eax, byte ptr [rdx+2]
0x140049534  cmp     al, 28h ; '('
0x140049536  jnz     loc_14004961B
0x14004953c  cmp     dword ptr [rdx+14h], 0
0x140049540  jnz     loc_140049714
0x140049546  mov     esi, [rdx+38h]
0x140049549  test    esi, esi
0x14004954b  jz      loc_140049714
0x140049551  xor     r11b, r11b
0x140049554  xor     ebx, ebx
0x140049556  xor     r12b, r12b
0x140049559  xor     r9d, r9d
0x14004955c  xor     edi, edi
0x14004955e  xor     r14b, r14b
0x140049561  mov     ecx, [rdx+rdi*4+78h]
0x140049565  cmp     ecx, 80h
0x14004956b  jb      short loc_1400495E4
0x14004956d  mov     r10d, [rdx+10h]
0x140049571  cmp     ecx, r10d
0x140049574  jnb     short loc_1400495E4
0x140049576  mov     r8d, ecx
0x140049579  mov     ecx, [rcx+rdx]
0x14004957c  sub     ecx, 40h ; '@'
0x14004957f  jz      short loc_1400495D6
0x140049581  sub     ecx, 1
0x140049584  jz      short loc_1400495AA
0x140049586  cmp     ecx, 1
0x140049589  jnz     short loc_1400495DF
0x14004958b  lea     rcx, [r8+28h]
0x14004958f  cmp     rcx, r10
0x140049592  ja      short loc_1400495DF
0x140049594  cmp     dword ptr [r8+rdx+0Ch], 0
0x14004959a  jbe     short loc_1400495A3
0x14004959c  lea     rbx, [rdx+20h]
0x1400495a0  add     rbx, r8
0x1400495a3  mov     r9, [r8+rdx+18h]
0x1400495a8  jmp     short loc_140049604
0x1400495aa  lea     rcx, [r8+38h]
0x1400495ae  cmp     rcx, r10
0x1400495b1  ja      short loc_1400495DF
0x1400495b3  cmp     byte ptr [r8+rdx+0Ah], 0
0x1400495b9  mov     r14b, 1
0x1400495bc  jbe     short loc_1400495C5
0x1400495be  lea     rbx, [rdx+18h]
0x1400495c2  add     rbx, r8
0x1400495c5  mov     r12b, [r8+rdx+8]
0x1400495ca  mov     r9, [r8+rdx+10h]
0x1400495cf  mov     r11b, [r8+rdx+9]
0x1400495d4  jmp     short loc_1400495DF
0x1400495d6  lea     rcx, [r8+28h]
0x1400495da  cmp     rcx, r10
0x1400495dd  jbe     short loc_1400495F0
0x1400495df  test    r14b, r14b
0x1400495e2  jnz     short loc_14004960E
0x1400495e4  inc     edi
0x1400495e6  cmp     edi, esi
0x1400495e8  jb      loc_140049561
0x1400495ee  jmp     short loc_14004960E
0x1400495f0  cmp     byte ptr [r8+rdx+0Ah], 0
0x1400495f6  jbe     short loc_1400495FF
0x1400495f8  lea     rbx, [rdx+18h]
0x1400495fc  add     rbx, r8
0x1400495ff  mov     r9, [r8+rdx+10h]
0x140049604  mov     r11b, [r8+rdx+9]
0x140049609  mov     r12b, [r8+rdx+8]
0x14004960e  test    rbx, rbx
0x140049611  jz      loc_14004970E
0x140049617  mov     cl, [rbx]
0x140049619  jmp     short loc_140049632
0x14004961b  mov     cl, [rdx+48h]
0x14004961e  mov     r9, [rdx+20h]
0x140049622  mov     r11b, [rdx+0Bh]
0x140049626  mov     r12b, [rdx+4]
0x14004962a  test    eax, eax
0x14004962c  jnz     loc_14004970E
0x140049632  sub     cl, 8
0x140049635  test    cl, 5Dh
0x140049638  jnz     loc_14004970E
0x14004963e  mov     bl, [rdx+3]
0x140049641  cmp     bl, 1
0x140049644  jz      loc_1400496D6
0x14004964a  test    r9, r9
0x14004964d  jz      loc_1400496D6
0x140049653  test    r11b, r11b
0x140049656  jz      short loc_1400496D6
0x140049658  mov     al, [r9]
0x14004965b  xor     r8b, r8b
0x14004965e  and     al, 7Fh
0x140049660  movzx   ecx, r11b
0x140049664  sub     al, 72h ; 'r'
0x140049666  xor     r10b, r10b
0x140049669  xor     dl, dl
0x14004966b  add     rcx, r9
0x14004966e  cmp     al, 1
0x140049670  lea     rax, [r9+8]
0x140049674  jbe     short loc_1400496B7
0x140049676  cmp     rax, rcx
0x140049679  ja      short loc_1400496D0
0x14004967b  movzx   ecx, byte ptr [r9+7]
0x140049680  lea     rdx, [r9+0Dh]
0x140049684  mov     r8b, [r9+2]
0x140049688  add     ecx, 8
0x14004968b  and     r8b, 0Fh
0x14004968f  movzx   eax, r11b
0x140049693  cmp     ecx, eax
0x140049695  cmovbe  eax, ecx
0x140049698  mov     ecx, eax
0x14004969a  add     rcx, r9
0x14004969d  cmp     rdx, rcx
0x1400496a0  ja      short loc_1400496A6
0x1400496a2  mov     r10b, [r9+0Ch]
0x1400496a6  lea     rax, [r9+0Eh]
0x1400496aa  cmp     rax, rcx
0x1400496ad  ja      short loc_1400496B3
0x1400496af  mov     dl, [rdx]
0x1400496b1  jmp     short loc_1400496CC
0x1400496b3  xor     dl, dl
0x1400496b5  jmp     short loc_1400496CC
0x1400496b7  cmp     rax, rcx
0x1400496ba  ja      short loc_1400496D0
0x1400496bc  mov     r8b, [r9+1]
0x1400496c0  mov     r10b, [r9+2]
0x1400496c4  and     r8b, 0Fh
0x1400496c8  mov     dl, [r9+3]
0x1400496cc  mov     al, 1
0x1400496ce  jmp     short loc_1400496D2
0x1400496d0  xor     al, al
0x1400496d2  test    al, al
0x1400496d4  jnz     short loc_1400496DE
0x1400496d6  xor     r8b, r8b
0x1400496d9  xor     r10b, r10b
0x1400496dc  xor     dl, dl
0x1400496de  mov     eax, [r15+30h]
0x1400496e2  mov     r9, r15
0x1400496e5  mov     [rsp+0F0h+var_A0], r15
  ... truncated ...
```
