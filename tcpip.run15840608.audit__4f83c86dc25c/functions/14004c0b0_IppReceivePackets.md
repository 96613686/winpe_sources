# IppReceivePackets

- ea: `0x14004c0b0`
- end: `0x14004cb52`
- name: `IppReceivePackets`
- size: `2722`
- prototype: ``
- caller_count: `11`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14003e22c`
- `0x14004a420`
- `0x14004bb20`
- `0x14004c090`
- `0x14004c0b0`
- `0x14004d250`
- `0x14006579c`
- `0x140082a44`
- `0x140127214`
- `0x14018d7bc`
- `0x1401ad960`

## callees

- `0x14002a0c0`
- `0x14002b530`
- `0x14002d1a0`
- `0x14002eb90`
- `0x14004c0b0`
- `0x14004d750`
- `0x14004e070`
- `0x14009dfd0`
- `0x1400ff954`
- `0x1401c0fd0`
- `0x1401c1200`
- `0x1401c1580`
- `0x1401c1aa0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14004c7f3`
- `ntoskrnl!KfRaiseIrql` at `0x14004ca72`
- `ntoskrnl!KfRaiseIrql` at `0x14004c7f3`
- `ntoskrnl!KfRaiseIrql` at `0x14004ca72`
- `ntoskrnl!KeLowerIrql` at `0x14004c514`
- `ntoskrnl!KeLowerIrql` at `0x14004ca64`
- `ntoskrnl!KeLowerIrql` at `0x14004cb2e`
- `ntoskrnl!KeLowerIrql` at `0x14004c514`
- `ntoskrnl!KeLowerIrql` at `0x14004ca64`
- `ntoskrnl!KeLowerIrql` at `0x14004cb2e`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x14004c6f3`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x14004c6f3`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004c1a9`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004c4d4`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004c849`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004ca84`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004c1a9`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004c4d4`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004c849`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004ca84`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14004c1d4`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14004caab`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14004c1d4`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14004caab`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14004c47d`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14004c47d`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x14004c902`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x14004c902`

## pseudocode

```c
void __fastcall IppReceivePackets(__int64 a1, _QWORD *a2, bool a3, unsigned int a4)
{
  __int64 *v4; // r12
  char v5; // r13
  _QWORD *v6; // r14
  __int64 v8; // rdi
  unsigned int v9; // eax
  KIRQL v10; // dl
  unsigned int LockArray_high; // eax
  _QWORD *v12; // r15
  bool v13; // zf
  __int64 v14; // rbx
  __int64 v15; // rsi
  char v16; // r13
  int *v17; // rbx
  int v18; // eax
  __int64 v19; // rcx
  int v20; // ecx
  __int64 v21; // rdx
  __int64 v22; // rbx
  __int64 v23; // rax
  _QWORD *v24; // r12
  __int64 v25; // rdx
  __int64 v26; // r8
  char v27; // dl
  char v28; // al
  __int64 v29; // rdx
  _DWORD *v30; // rcx
  _OWORD *v31; // r11
  unsigned __int16 v32; // r10
  __int64 v33; // rax
  _QWORD *v34; // rcx
  unsigned __int16 v35; // dx
  _DWORD *v36; // r15
  _QWORD *v37; // rdi
  __int64 v38; // rsi
  _BYTE *v39; // r9
  _BYTE *v40; // r12
  __int64 v41; // rdx
  _QWORD *v42; // r12
  __int64 v43; // rcx
  char *v44; // r8
  _QWORD *v45; // rcx
  _DWORD *v46; // rcx
  _QWORD *v47; // rsi
  _QWORD *v48; // rdi
  int v49; // r15d
  unsigned int v50; // eax
  __int64 v51; // rcx
  __int64 v52; // rax
  __int64 v53; // rax
  int *v54; // rbx
  int v55; // eax
  _QWORD *v56; // rcx
  _QWORD *v57; // r13
  int v58; // r14d
  __int64 v59; // rdx
  bool v60; // [rsp+50h] [rbp-B0h]
  KIRQL v61; // [rsp+51h] [rbp-AFh]
  bool v62; // [rsp+52h] [rbp-AEh]
  int v63; // [rsp+54h] [rbp-ACh]
  int v64; // [rsp+58h] [rbp-A8h]
  unsigned int v65; // [rsp+5Ch] [rbp-A4h]
  __int128 v66; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v67; // [rsp+70h] [rbp-90h]
  __int128 v68; // [rsp+78h] [rbp-88h] BYREF
  _QWORD *v69; // [rsp+88h] [rbp-78h]
  unsigned int v70; // [rsp+90h] [rbp-70h]
  int v71; // [rsp+94h] [rbp-6Ch]
  _QWORD *v72; // [rsp+98h] [rbp-68h]
  __int64 v73; // [rsp+A0h] [rbp-60h]
  __int64 v74; // [rsp+A8h] [rbp-58h]
  __int64 *v75; // [rsp+B0h] [rbp-50h]
  _QWORD *v76; // [rsp+B8h] [rbp-48h]
  __int128 v77; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v78; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v79; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v80; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD *v81; // [rsp+F8h] [rbp-8h]
  _QWORD *v82; // [rsp+100h] [rbp+0h] BYREF
  __int64 v83; // [rsp+108h] [rbp+8h]
  __int64 v84; // [rsp+110h] [rbp+10h]
  _QWORD *v85; // [rsp+118h] [rbp+18h]
  int v86[2]; // [rsp+120h] [rbp+20h]
  _QWORD *v87; // [rsp+128h] [rbp+28h]
  __int64 v88; // [rsp+138h] [rbp+38h]
  _BYTE *v89; // [rsp+140h] [rbp+40h]
  _OWORD v90[61]; // [rsp+150h] [rbp+50h] BYREF

  v4 = *(__int64 **)(a1 + 8);
  v80 = 0;
  v66 = 0;
  v5 = a4;
  v60 = a3;
  v77 = 0;
  v6 = a2;
  v76 = a2;
  v78 = 0;
  v67 = a1;
  v79 = 0;
  v74 = *v4;
  v75 = v4;
  v8 = *(_QWORD *)(v74 + 40);
  v9 = a4 >> 1;
  LOBYTE(v9) = (a4 & 2) != 0;
  v73 = v8;
  v70 = v9;
  if ( a3 )
  {
    v10 = 2;
  }
  else
  {
    v10 = KfRaiseIrql(2u);
    a3 = v10 == 2;
    v60 = v10 == 2;
  }
  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  v65 = LockArray_high;
  v61 = v10;
  v12 = (_QWORD *)(*(_QWORD *)(v8 + 20264) + 192LL * LockArray_high);
  v13 = (v4[49] & 1) == 0;
  v14 = *(_QWORD *)(*(_QWORD *)(a1 + 104) + 8LL * LockArray_high);
  v84 = v14;
  v85 = v12;
  if ( !v13 || (v15 = *((_QWORD *)qword_1402288A0 + LockArray_high), v83 = v15, *(_DWORD *)(v15 + 21508) == 3) )
  {
    if ( !a3 )
    {
      KeLowerIrql(v10);
      a3 = v60;
    }
    v47 = v6;
    if ( v6 )
    {
      v57 = v6;
      v58 = v67;
      do
      {
        v59 = v57[1];
        ++*(_QWORD *)(v14 + 48);
        ++*v12;
        *(_QWORD *)(v14 + 56) += *(unsigned int *)(v59 + 24);
        v12[1] += *(unsigned int *)(v59 + 24);
        IppDiscardReceivedPackets(v8, 10, 0, v58, (__int64)v47, 3, -536854215);
        *((_DWORD *)v57 + 35) = -1073741285;
        v57 = (_QWORD *)*v47;
        v47 = v57;
      }
      while ( v57 );
      v6 = v76;
      a3 = v60;
    }
    NetioDereferenceNetBufferListChain(v6, a3);
    return;
  }
  v16 = v5 & 1;
  v17 = *(int **)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
  v18 = *v17;
  if ( *v17 )
  {
    if ( v18 == 1 )
    {
      ++v17[32];
    }
    else if ( v18 == 2 )
    {
      ++v17[28];
    }
  }
  else
  {
    if ( KeQueryDpcWatchdogInformation((PKDPC_WATCHDOG_INFORMATION)(v17 + 2)) )
    {
      *((_QWORD *)v17 + 1) = MEMORY[0xFFFFF78000000008];
      *v17 = 2;
      *((_OWORD *)v17 + 1) = 0;
      *((_OWORD *)v17 + 2) = 0;
      *((_OWORD *)v17 + 3) = 0;
      *((_OWORD *)v17 + 4) = 0;
      *((_OWORD *)v17 + 5) = 0;
      *((_OWORD *)v17 + 6) = 0;
    }
    else
    {
      *v17 = 1;
      *((_OWORD *)v17 + 2) = 0;
      *((_OWORD *)v17 + 3) = 0;
      *((_OWORD *)v17 + 4) = 0;
      *((_OWORD *)v17 + 5) = 0;
      *((_OWORD *)v17 + 6) = 0;
      *((_OWORD *)v17 + 7) = 0;
      v17[32] = 1;
    }
    v17[28] = 1;
  }
  ++*(_DWORD *)(v15 + 21508);
  while ( 2 )
  {
    while ( 2 )
    {
      *((_QWORD *)&v66 + 1) = &v66;
      *((_QWORD *)&v77 + 1) = &v77;
      *((_QWORD *)&v78 + 1) = &v78;
      *((_QWORD *)&v79 + 1) = &v79;
      v63 = 0;
      *(_QWORD *)&v66 = 0;
      *(_QWORD *)&v77 = 0;
      *(_QWORD *)&v78 = 0;
      *(_QWORD *)&v79 = 0;
      v19 = v4[12];
      v62 = v19
         && !*(_BYTE *)(v19 + 40)
         && ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v19 + 16), 1u);
      v64 = *(_DWORD *)(v15 + 21504);
      v20 = 64 - 32 / (1 << (*(_DWORD *)(v15 + 21508) - 1));
      v71 = v20;
      do
      {
        v21 = *(unsigned int *)(v15 + 21504);
        if ( (_DWORD)v21 == v20 )
          break;
        v22 = v15 + 336 * v21;
        *(_DWORD *)(v15 + 21504) = v21 + 1;
        memset((void *)v22, 0, 0x150u);
        v23 = v67;
        v24 = v6;
        v82 = v6;
        v6 = (_QWORD *)*v6;
        *v24 = 0;
        v25 = v24[1];
        *(_QWORD *)(v22 + 224) = v23;
        LOBYTE(v23) = *(_BYTE *)(v22 + 186) & 0x7F;
        *(_QWORD *)(v22 + 8) = v24;
        *(_QWORD *)(v22 + 200) = v74;
        *(_BYTE *)(v22 + 186) = v23 | (v16 << 7);
        v80 = v24[18];
        if ( !v16 )
        {
          v26 = v84;
          ++*(_QWORD *)(v84 + 48);
          ++*v12;
          *(_QWORD *)(v26 + 56) += *(unsigned int *)(v25 + 24);
          v12[1] += *(unsigned int *)(v25 + 24);
        }
        v8 = v73;
        if ( (*(int (__fastcall **)(__int64, __int64 *))(v73 + 88))(v22, &v80) < 0 )
        {
          **((_QWORD **)&v79 + 1) = v22;
          *((_QWORD *)&v79 + 1) = v22;
        }
        else
        {
          if ( !v62 || v16 )
          {
LABEL_19:
            if ( (_QWORD)v66
              && memcmp(
                   *(const void **)(v66 + 248),
                   *(const void **)(v22 + 248),
                   *(unsigned __int16 *)(*(_QWORD *)(v8 + 16) + 6LL)) )
            {
              IppDispatchReceivePacketHelper(v8, v74, v75, &v66, v63, &v77, &v78);
              v63 = 0;
              *(_QWORD *)&v66 = 0;
              *((_QWORD *)&v66 + 1) = &v66;
            }
            v27 = v70;
            v28 = *(_BYTE *)(v22 + 184);
            *(_BYTE *)(v22 + 16) ^= (*(_BYTE *)(v22 + 16) ^ v70) & 1;
            ++v63;
            *(_BYTE *)(v22 + 184) = v28 ^ (v28 ^ (16 * v27)) & 0x10;
            **((_QWORD **)&v66 + 1) = v22;
            *((_QWORD *)&v66 + 1) = v22;
            goto LABEL_23;
          }
          LOBYTE(v69) = 0;
          v68 = 0;
          memset(v90, 0, 0x3C4u);
          v31 = &v90[3];
          v32 = 0;
          v81 = *(_QWORD **)(v67 + 8);
          v33 = *v81;
          v76 = (_QWORD *)v81[12];
          v34 = (_QWORD *)*v76;
          *(_QWORD *)v86 = *(_QWORD *)(v33 + 40);
          *(_QWORD *)&v90[3] = 0;
          *((_QWORD *)&v90[0] + 1) = v67;
          v35 = -1;
          *(_QWORD *)&v90[2] = 0x1000000000FFFFLL;
          *(_QWORD *)&v90[6] = 0x800000000LL;
          v72 = v34;
          LODWORD(v90[0]) = 1918062665;
          *(_QWORD *)&v90[1] = 0;
          *((_QWORD *)&v90[1] + 1) = &v90[3];
          BYTE8(v90[2]) = 0;
          HIDWORD(v90[2]) = 0;
          *((_QWORD *)&v90[3] + 1) = v24;
          v90[4] = (unsigned __int64)v24;
          v90[5] = 0;
          if ( v34 != v76 )
          {
            v36 = v81;
            v37 = v34;
            do
            {
              v38 = v37[2];
              v88 = v38;
              v39 = (_BYTE *)(v38 + 62);
              v89 = (_BYTE *)(v38 + 62);
              v40 = (_BYTE *)(v38 + 62);
              while ( 1 )
              {
                LOWORD(v90[2]) = ++v35;
                if ( v35 > v32 )
                  break;
                v40 = v39;
                v44 = (char *)v31 + 56 * v35;
                v45 = v44 + 8;
                if ( *((_QWORD *)v44 + 1) && (v44[52] & 4) == 0 && !*((_DWORD *)v44 + 12) )
                {
                  v40 = (_BYTE *)(v38 + 62);
                  v68 = *(_OWORD *)v44;
                  v69 = (_QWORD *)*((_QWORD *)v44 + 2);
                  *v45 = 0;
                  *((_QWORD *)v44 + 2) = v45;
                  if ( *(_BYTE *)(v38 + 62) && (BYTE8(v90[2]) & 2) == 0 )
                  {
                    v48 = (_QWORD *)*((_QWORD *)&v68 + 1);
                    v49 = v86[0];
                    v69 = (_QWORD *)&v68 + 1;
                    *((_QWORD *)&v68 + 1) = 0;
                    do
                    {
                      v87 = v48;
                      v48 = (_QWORD *)*v48;
                      *v87 = 0;
                      if ( !(unsigned __int8)IppGroupFragmentsForIpsnpi(v49) )
                      {
                        v56 = v87;
                        *v69 = v87;
                        v69 = v56;
                      }
                    }
                    while ( v48 );
                    v37 = v72;
                    v38 = v88;
                    v36 = v81;
                  }
                  if ( *((_QWORD *)&v68 + 1) )
                    (*(void (__fastcall **)(_QWORD, _OWORD *, _QWORD, _QWORD, _DWORD, _QWORD, __int128 *, _DWORD))(*(_QWORD *)(v38 + 80) + 16LL))(
                      *(_QWORD *)(v38 + 88),
                      v90,
                      **(unsigned int **)v36,
                      *(unsigned int *)(*(_QWORD *)v36 + 20LL),
                      v36[2],
                      v37[3],
                      &v68,
                      0);
                  v32 = WORD1(v90[2]);
                  v35 = v90[2];
                  v31 = (_OWORD *)*((_QWORD *)&v90[1] + 1);
                  v39 = v89;
                }
              }
              v32 = WORD2(v90[2]);
              v35 = -1;
              LOWORD(v90[2]) = -1;
              WORD1(v90[2]) = WORD2(v90[2]);
              if ( *v40 )
                BYTE8(v90[2]) |= 2u;
              v37 = (_QWORD *)*v37;
              v72 = v37;
            }
            while ( v37 != v76 );
            v15 = v83;
            v12 = v85;
            v8 = v73;
          }
          IppCompleteIpsReceiveContext(v90, &v82);
          v42 = v82;
          if ( v82 )
          {
            if ( v82 == *(_QWORD **)(v22 + 8) && !*v82 )
              goto LABEL_19;
            LOBYTE(v41) = 1;
            *(_QWORD *)(v22 + 8) = 0;
            IppCompleteAndFreePacketList(v22, v41);
            v43 = v67;
            --*(_DWORD *)(v15 + 21504);
            IppReceivePackets(v43, v42, v60, 1);
          }
          else
          {
            LOBYTE(v41) = 1;
            *(_QWORD *)(v22 + 8) = 0;
            IppCompleteAndFreePacketList(v22, v41);
            --*(_DWORD *)(v15 + 21504);
          }
        }
LABEL_23:
        v20 = v71;
      }
      while ( v6 );
      v4 = v75;
      if ( (_QWORD)v66 )
      {
        IppDispatchReceivePacketHelper(v8, v74, v75, &v66, v63, &v77, &v78);
        *(_QWORD *)&v66 = 0;
        *((_QWORD *)&v66 + 1) = &v66;
      }
      if ( (_QWORD)v77 )
        IppReceiveHeaderBatch(v8, &v77);
      if ( v62 )
        ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v4[12] + 16), 1u);
      v29 = v78;
      if ( (_QWORD)v78 )
        IppFragmentPackets(v8);
      if ( (_QWORD)v79 )
      {
        LOBYTE(v29) = 1;
        IppCompleteAndFreePacketList(v79, v29);
      }
      *(_DWORD *)(v15 + 21504) = v64;
      if ( v60 )
      {
        if ( !v6 )
          goto LABEL_36;
        continue;
      }
      break;
    }
    if ( v6 )
    {
      IppDequeueForwardInjectedPacketsAtDpc(v65);
      --*(_DWORD *)(v15 + 21508);
      v46 = *(_DWORD **)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
      if ( *v46 == 1 )
      {
        v13 = v46[32]-- == 1;
        if ( v13 )
          goto LABEL_94;
      }
      else
      {
        if ( *v46 != 2 )
          goto LABEL_95;
        v13 = v46[28]-- == 1;
        if ( !v13 )
          goto LABEL_95;
LABEL_94:
        *v46 = 0;
      }
LABEL_95:
      KeLowerIrql(v61);
      v61 = KfRaiseIrql(2u);
      v54 = *(int **)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
      v55 = *v54;
      if ( *v54 )
      {
        if ( v55 == 1 )
        {
          ++v54[32];
        }
        else if ( v55 == 2 )
        {
          ++v54[28];
        }
      }
      else
      {
        if ( KeQueryDpcWatchdogInformation((PKDPC_WATCHDOG_INFORMATION)(v54 + 2)) )
        {
          *((_QWORD *)v54 + 1) = MEMORY[0xFFFFF78000000008];
          *v54 = 2;
          *((_OWORD *)v54 + 1) = 0;
          *((_OWORD *)v54 + 2) = 0;
          *((_OWORD *)v54 + 3) = 0;
          *((_OWORD *)v54 + 4) = 0;
          *((_OWORD *)v54 + 5) = 0;
          *((_OWORD *)v54 + 6) = 0;
        }
        else
        {
          *v54 = 1;
          *((_OWORD *)v54 + 2) = 0;
          *((_OWORD *)v54 + 3) = 0;
          *((_OWORD *)v54 + 4) = 0;
          *((_OWORD *)v54 + 5) = 0;
          *((_OWORD *)v54 + 6) = 0;
          *((_OWORD *)v54 + 7) = 0;
          v54[32] = 1;
        }
        v54[28] = 1;
      }
      v50 = HIDWORD(KeGetPcr()[1].LockArray);
      v51 = v50;
      v65 = v50;
      v15 = *((_QWORD *)qword_1402288A0 + v50);
      v52 = v67;
      v83 = v15;
      ++*(_DWORD *)(v15 + 21508);
      v53 = *(_QWORD *)(v52 + 104);
      v12 = (_QWORD *)(*(_QWORD *)(v8 + 20264) + 192 * v51);
      v85 = v12;
      v84 = *(_QWORD *)(v53 + 8 * v51);
      continue;
    }
    break;
  }
LABEL_36:
  IppDequeueForwardInjectedPacketsAtDpc(v65);
  --*(_DWORD *)(v15 + 21508);
  v30 = *(_DWORD **)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
  if ( *v30 == 1 )
  {
    v13 = v30[32]-- == 1;
    if ( v13 )
      goto LABEL_38;
  }
  else if ( *v30 == 2 )
  {
    v13 = v30[28]-- == 1;
    if ( v13 )
LABEL_38:
      *v30 = 0;
  }
  if ( !v60 )
    KeLowerIrql(v61);
}

```

## disassembly

```asm
0x14004c0b0  push    rbp
0x14004c0b2  push    rbx
0x14004c0b3  push    rdi
0x14004c0b4  push    r12
0x14004c0b6  push    r13
0x14004c0b8  push    r14
0x14004c0ba  push    r15
0x14004c0bc  lea     rbp, [rsp-430h]
0x14004c0c4  sub     rsp, 530h
0x14004c0cb  mov     rax, cs:__security_cookie
0x14004c0d2  xor     rax, rsp
0x14004c0d5  mov     [rbp+460h+var_40], rax
0x14004c0dc  mov     r12, [rcx+8]
0x14004c0e0  xorps   xmm0, xmm0
0x14004c0e3  xorps   xmm1, xmm1
0x14004c0e6  mov     [rbp+460h+var_470], 0
0x14004c0ee  movups  [rsp+560h+var_500], xmm0
0x14004c0f3  mov     r13d, r9d
0x14004c0f6  mov     [rsp+560h+var_510], r8b
0x14004c0fb  movups  [rbp+460h+var_4A0], xmm1
0x14004c0ff  mov     r14, rdx
0x14004c102  mov     [rbp+460h+var_4A8], rdx
0x14004c106  movups  [rbp+460h+var_490], xmm0
0x14004c10a  mov     rbx, rcx
0x14004c10d  mov     [rsp+560h+var_4F0], rcx
0x14004c112  movups  [rbp+460h+var_480], xmm1
0x14004c116  mov     rax, [r12]
0x14004c11a  mov     [rbp+460h+var_4B8], rax
0x14004c11e  mov     [rbp+460h+var_4B0], r12
0x14004c122  mov     rdi, [rax+28h]
0x14004c126  mov     eax, r9d
0x14004c129  shr     eax, 1
0x14004c12b  and     al, 1
0x14004c12d  mov     [rbp+460h+var_4C0], rdi
0x14004c131  mov     [rbp+460h+var_4D0], eax
0x14004c134  test    r8b, r8b
0x14004c137  jz      loc_14004C7F1
0x14004c13d  mov     dl, 2
0x14004c13f  mov     eax, gs:1A4h
0x14004c147  mov     ecx, eax
0x14004c149  mov     [rsp+560h+var_504], eax
0x14004c14d  mov     rax, [rbx+68h]
0x14004c151  mov     [rsp+560h+var_50F], dl
0x14004c155  lea     r15, [rcx+rcx*2]
0x14004c159  mov     [rsp+560h+arg_18], rsi
0x14004c161  shl     r15, 6
0x14004c165  add     r15, [rdi+4F28h]
0x14004c16c  test    byte ptr [r12+188h], 1
0x14004c175  mov     rbx, [rax+rcx*8]
0x14004c179  mov     [rbp+460h+var_450], rbx
0x14004c17d  mov     [rbp+460h+var_448], r15
0x14004c181  jnz     loc_14004C8E6
0x14004c187  mov     rax, cs:qword_1402288A0
0x14004c18e  mov     rsi, [rax+rcx*8]
0x14004c192  mov     [rbp+460h+var_458], rsi
0x14004c196  cmp     dword ptr [rsi+5404h], 3
0x14004c19d  jz      loc_14004C8E6
0x14004c1a3  xor     ecx, ecx; ProcNumber
0x14004c1a5  and     r13b, 1
0x14004c1a9  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14004c1b0  nop     dword ptr [rax+rax+00h]
0x14004c1b5  lea     ecx, [rax+rax*8]
0x14004c1b8  mov     rax, cs:gWfpPerProContext
0x14004c1bf  shl     ecx, 3
0x14004c1c2  mov     rbx, [rcx+rax]
0x14004c1c6  mov     eax, [rbx]
0x14004c1c8  test    eax, eax
0x14004c1ca  jnz     loc_14004C889
0x14004c1d0  lea     rcx, [rbx+8]; WatchdogInformation
0x14004c1d4  call    cs:__imp_KeQueryDpcWatchdogInformation
0x14004c1db  nop     dword ptr [rax+rax+00h]
0x14004c1e0  xorps   xmm0, xmm0
0x14004c1e3  xorps   xmm1, xmm1
0x14004c1e6  test    eax, eax
0x14004c1e8  jnz     loc_14004C924
0x14004c1ee  mov     dword ptr [rbx], 1
0x14004c1f4  movups  xmmword ptr [rbx+20h], xmm0
0x14004c1f8  movups  xmmword ptr [rbx+30h], xmm0
0x14004c1fc  movups  xmmword ptr [rbx+40h], xmm0
0x14004c200  movups  xmmword ptr [rbx+50h], xmm1
0x14004c204  movups  xmmword ptr [rbx+60h], xmm1
0x14004c208  movups  xmmword ptr [rbx+70h], xmm1
0x14004c20c  mov     dword ptr [rbx+80h], 1
0x14004c216  mov     dword ptr [rbx+70h], 1
0x14004c21d  inc     dword ptr [rsi+5404h]
0x14004c223  xor     ecx, ecx
0x14004c225  lea     rax, [rsp+560h+var_500]
0x14004c22a  mov     qword ptr [rsp+560h+var_500+8], rax
0x14004c22f  lea     rax, [rbp+460h+var_4A0]
0x14004c233  mov     qword ptr [rbp+460h+var_4A0+8], rax
0x14004c237  lea     rax, [rbp+460h+var_490]
0x14004c23b  mov     qword ptr [rbp+460h+var_490+8], rax
0x14004c23f  lea     rax, [rbp+460h+var_480]
0x14004c243  mov     qword ptr [rbp+460h+var_480+8], rax
0x14004c247  mov     [rsp+560h+var_50C], ecx
0x14004c24b  mov     qword ptr [rsp+560h+var_500], rcx
0x14004c250  mov     qword ptr [rbp+460h+var_4A0], rcx
0x14004c254  mov     qword ptr [rbp+460h+var_490], rcx
0x14004c258  mov     qword ptr [rbp+460h+var_480], rcx
0x14004c25c  mov     rcx, [r12+60h]
0x14004c261  test    rcx, rcx
0x14004c264  jz      short loc_14004C272
0x14004c266  movzx   eax, byte ptr [rcx+28h]
0x14004c26a  test    al, al
0x14004c26c  jz      loc_14004C6EA
0x14004c272  mov     [rsp+560h+var_50E], 0
0x14004c277  mov     ecx, [rsi+5404h]
0x14004c27d  mov     r8d, 1
0x14004c283  mov     ebx, [rsi+5400h]
0x14004c289  dec     ecx
0x14004c28b  shl     r8d, cl
0x14004c28e  mov     eax, 20h ; ' '
0x14004c293  cdq
0x14004c294  mov     [rsp+560h+var_508], ebx
0x14004c298  idiv    r8d
0x14004c29b  mov     ecx, 40h ; '@'
0x14004c2a0  sub     ecx, eax
0x14004c2a2  mov     [rbp+460h+var_4CC], ecx
0x14004c2a5  mov     edx, [rsi+5400h]
0x14004c2ab  cmp     edx, ecx
0x14004c2ad  jz      loc_14004C408
0x14004c2b3  imul    rbx, rdx, 150h
0x14004c2ba  lea     eax, [rdx+1]
0x14004c2bd  mov     r8d, 150h; Size
0x14004c2c3  add     rbx, rsi
0x14004c2c6  mov     [rsi+5400h], eax
0x14004c2cc  mov     rcx, rbx; void *
0x14004c2cf  xor     edx, edx; Val
0x14004c2d1  mov     rdi, r14
0x14004c2d4  call    memset
0x14004c2d9  mov     rax, [rsp+560h+var_4F0]
0x14004c2de  mov     r12, r14
0x14004c2e1  mov     [rbp+460h+var_460], r14
0x14004c2e5  movzx   ecx, r13b
0x14004c2e9  mov     r14, [r14]
0x14004c2ec  shl     cl, 7
0x14004c2ef  mov     qword ptr [r12], 0
0x14004c2f7  mov     rdx, [r12+8]
0x14004c2fc  mov     [rbx+0E0h], rax
0x14004c303  movzx   eax, byte ptr [rbx+0BAh]
0x14004c30a  and     al, 7Fh
0x14004c30c  mov     [rbx+8], r12
0x14004c310  or      cl, al
0x14004c312  mov     rax, [rbp+460h+var_4B8]
0x14004c316  mov     [rbx+0C8h], rax
0x14004c31d  mov     [rbx+0BAh], cl
0x14004c323  mov     rax, [r12+90h]
0x14004c32b  mov     [rbp+460h+var_470], rax
0x14004c32f  test    r13b, r13b
0x14004c332  jnz     short loc_14004C368
0x14004c334  mov     r8, [rbp+460h+var_450]
0x14004c338  mov     rax, [r8+30h]
0x14004c33c  inc     rax
0x14004c33f  mov     [r8+30h], rax
0x14004c343  mov     rax, [r15]
0x14004c346  inc     rax
0x14004c349  mov     [r15], rax
0x14004c34c  mov     rax, [r8+38h]
0x14004c350  mov     ecx, [rdx+18h]
0x14004c353  add     rcx, rax
0x14004c356  mov     [r8+38h], rcx
0x14004c35a  mov     ecx, [rdx+18h]
0x14004c35d  mov     rax, [r15+8]
0x14004c361  add     rcx, rax
0x14004c364  mov     [r15+8], rcx
0x14004c368  mov     rdi, [rbp+460h+var_4C0]
0x14004c36c  lea     rdx, [rbp+460h+var_470]
0x14004c370  mov     rcx, rbx
0x14004c373  mov     rax, [rdi+58h]
0x14004c377  call    _guard_dispatch_icall
0x14004c37c  test    eax, eax
0x14004c37e  js      loc_14004C54B
0x14004c384  cmp     [rsp+560h+var_50E], 0
0x14004c389  jnz     loc_14004C55B
0x14004c38f  mov     rcx, qword ptr [rsp+560h+var_500]
0x14004c394  test    rcx, rcx
0x14004c397  jz      short loc_14004C3BD
0x14004c399  mov     rax, [rdi+10h]
0x14004c39d  mov     rdx, [rbx+0F8h]; Buf2
0x14004c3a4  mov     rcx, [rcx+0F8h]; Buf1
0x14004c3ab  movzx   r8d, word ptr [rax+6]; Size
0x14004c3b0  call    memcmp
0x14004c3b5  test    eax, eax
0x14004c3b7  jnz     loc_14004C89D
0x14004c3bd  movzx   eax, byte ptr [rbx+10h]
0x14004c3c1  mov     edx, [rbp+460h+var_4D0]
0x14004c3c4  movzx   ecx, dl
0x14004c3c7  xor     cl, al
0x14004c3c9  and     cl, 1
0x14004c3cc  xor     cl, al
0x14004c3ce  movzx   eax, byte ptr [rbx+0B8h]
0x14004c3d5  mov     [rbx+10h], cl
0x14004c3d8  movzx   ecx, dl
0x14004c3db  shl     cl, 4
0x14004c3de  xor     cl, al
0x14004c3e0  and     cl, 10h
0x14004c3e3  xor     cl, al
0x14004c3e5  inc     [rsp+560h+var_50C]
0x14004c3e9  mov     [rbx+0B8h], cl
0x14004c3ef  mov     rax, qword ptr [rsp+560h+var_500+8]
0x14004c3f4  mov     [rax], rbx
0x14004c3f7  mov     qword ptr [rsp+560h+var_500+8], rbx
0x14004c3fc  mov     ecx, [rbp+460h+var_4CC]
0x14004c3ff  test    r14, r14
0x14004c402  jnz     loc_14004C2A5
0x14004c408  cmp     qword ptr [rsp+560h+var_500], 0
0x14004c40e  mov     r12, [rbp+460h+var_4B0]
0x14004c412  jz      short loc_14004C455
0x14004c414  mov     rdx, [rbp+460h+var_4B8]
0x14004c418  lea     rax, [rbp+460h+var_490]
0x14004c41c  mov     [rsp+560h+var_530], rax
0x14004c421  lea     r9, [rsp+560h+var_500]
0x14004c426  lea     rax, [rbp+460h+var_4A0]
0x14004c42a  mov     r8, r12
0x14004c42d  mov     [rsp+560h+var_538], rax
0x14004c432  mov     rcx, rdi
0x14004c435  mov     eax, [rsp+560h+var_50C]
0x14004c439  mov     dword ptr [rsp+560h+var_540], eax
0x14004c43d  call    IppDispatchReceivePacketHelper
0x14004c442  lea     rax, [rsp+560h+var_500]
0x14004c447  mov     qword ptr [rsp+560h+var_500], 0
0x14004c450  mov     qword ptr [rsp+560h+var_500+8], rax
0x14004c455  cmp     qword ptr [rbp+460h+var_4A0], 0
0x14004c45a  jz      short loc_14004C468
0x14004c45c  lea     rdx, [rbp+460h+var_4A0]
0x14004c460  mov     rcx, rdi
0x14004c463  call    IppReceiveHeaderBatch
0x14004c468  cmp     [rsp+560h+var_50E], 0
0x14004c46d  jz      short loc_14004C489
0x14004c46f  mov     rcx, [r12+60h]
0x14004c474  mov     edx, 1; Count
0x14004c479  mov     rcx, [rcx+10h]; RunRef
0x14004c47d  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x14004c484  nop     dword ptr [rax+rax+00h]
0x14004c489  mov     rdx, qword ptr [rbp+460h+var_490]
0x14004c48d  test    rdx, rdx
0x14004c490  jnz     loc_14004C7CC
0x14004c496  mov     rcx, qword ptr [rbp+460h+var_480]
0x14004c49a  test    rcx, rcx
0x14004c49d  jnz     loc_14004C955
0x14004c4a3  movzx   ebx, [rsp+560h+var_510]
0x14004c4a8  mov     eax, [rsp+560h+var_508]
0x14004c4ac  mov     [rsi+5400h], eax
0x14004c4b2  test    bl, bl
0x14004c4b4  jz      loc_14004C82F
0x14004c4ba  test    r14, r14
0x14004c4bd  jnz     loc_14004C223
0x14004c4c3  mov     ecx, [rsp+560h+var_504]
0x14004c4c7  call    IppDequeueForwardInjectedPacketsAtDpc
0x14004c4cc  dec     dword ptr [rsi+5404h]
0x14004c4d2  xor     ecx, ecx; ProcNumber
0x14004c4d4  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14004c4db  nop     dword ptr [rax+rax+00h]
0x14004c4e0  lea     ecx, [rax+rax*8]
0x14004c4e3  mov     rax, cs:gWfpPerProContext
0x14004c4ea  shl     ecx, 3
0x14004c4ed  mov     rcx, [rcx+rax]
0x14004c4f1  mov     eax, [rcx]
0x14004c4f3  cmp     eax, 1
0x14004c4f6  jnz     loc_14004C7D9
0x14004c4fc  add     dword ptr [rcx+80h], 0FFFFFFFFh
0x14004c503  jnz     short loc_14004C50B
0x14004c505  mov     dword ptr [rcx], 0
0x14004c50b  test    bl, bl
0x14004c50d  jnz     short loc_14004C520
0x14004c50f  movzx   ecx, [rsp+560h+var_50F]; NewIrql
0x14004c514  call    cs:__imp_KeLowerIrql
0x14004c51b  nop     dword ptr [rax+rax+00h]
0x14004c520  mov     rsi, [rsp+560h+arg_18]
0x14004c528  mov     rcx, [rbp+460h+var_40]
0x14004c52f  xor     rcx, rsp; StackCookie
0x14004c532  call    __security_check_cookie
0x14004c537  add     rsp, 530h
0x14004c53e  pop     r15
0x14004c540  pop     r14
0x14004c542  pop     r13
0x14004c544  pop     r12
0x14004c546  pop     rdi
0x14004c547  pop     rbx
0x14004c548  pop     rbp
0x14004c549  retn
0x14004c54b  mov     rax, qword ptr [rbp+460h+var_480+8]
0x14004c54f  mov     [rax], rbx
0x14004c552  mov     qword ptr [rbp+460h+var_480+8], rbx
0x14004c556  jmp     loc_14004C3FC
0x14004c55b  test    r13b, r13b
0x14004c55e  jnz     loc_14004C38F
0x14004c564  xor     eax, eax
0x14004c566  lea     rcx, [rbp+460h+var_410]; void *
0x14004c56a  xorps   xmm0, xmm0
0x14004c56d  mov     byte ptr [rbp+460h+var_4D8], al
0x14004c570  xor     edx, edx; Val
0x14004c572  mov     [rbp+460h+var_40C], eax
0x14004c575  mov     r8d, 3C4h; Size
0x14004c57b  movups  [rsp+560h+var_4E8], xmm0
0x14004c580  call    memset
0x14004c585  mov     rdx, [rsp+560h+var_4F0]
0x14004c58a  lea     r11, [rbp+460h+var_3E0]
0x14004c591  xor     r9d, r9d
0x14004c594  xorps   xmm0, xmm0
  ... truncated ...
```
