# RndisDevHostDeviceIndicatePDBuffers

- ea: `0x140092168`
- end: `0x140092efd`
- name: `RndisDevHostDeviceIndicatePDBuffers`
- size: `3477`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1401acbc8`

## callees

- `0x140006620`
- `0x140027a64`
- `0x140027efc`
- `0x14003c378`
- `0x140047ad0`
- `0x140048f8c`
- `0x14004bfc0`
- `0x1400572dc`
- `0x1400573e4`
- `0x140062760`
- `0x14008497c`
- `0x140092168`
- `0x140092f04`
- `0x140115db8`
- `0x1401ac340`
- `0x1401bb110`
- `0x1401bb158`
- `0x1401bbbc2`
- `0x1401bbcb0`
- `0x1401bbe80`
- `0x1401bc040`
- `0x1401bc340`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14009275d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140092b0f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14009275d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140092b0f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14009228f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14009234a`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400923e3`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14009228f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14009234a`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400923e3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400925ca`
- `ntoskrnl!KeReleaseSpinLock` at `0x140092ec5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400925ca`
- `ntoskrnl!KeReleaseSpinLock` at `0x140092ec5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400924ac`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140092ea6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400924ac`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140092ea6`

## string_xrefs

- `0x140092d6e`: `numPacketsCombined > 0`

## pseudocode

```c
__int64 __fastcall RndisDevHostDeviceIndicatePDBuffers(_QWORD *a1, __int64 *a2, int a3, __int16 a4)
{
  __int64 v6; // rbx
  unsigned __int64 v7; // rax
  void *v8; // rsp
  __int64 v9; // r15
  _QWORD *v10; // r13
  int v11; // ebx
  __int64 v12; // rdi
  bool v13; // dl
  __int64 v14; // rsi
  unsigned __int64 v15; // rax
  void *v16; // rsp
  bool v17; // di
  ULONG CurrentProcessorNumber; // eax
  __int64 v19; // rdi
  KIRQL v20; // al
  __int64 v21; // rdx
  __int64 *v22; // rsi
  KIRQL v23; // r12
  unsigned int v24; // r15d
  _QWORD *v25; // rax
  int v26; // edx
  __int64 *v27; // rsi
  _QWORD *v28; // r12
  unsigned __int16 v29; // r15
  _QWORD *v30; // rdx
  int v31; // ecx
  __int64 v32; // r8
  int v33; // r15d
  unsigned int v34; // eax
  _QWORD *v35; // rsi
  int v36; // r13d
  int v37; // r12d
  unsigned int v38; // r15d
  int v39; // edx
  void *v40; // rdx
  int v41; // ecx
  unsigned int v42; // esi
  _QWORD *v43; // r8
  __int64 v44; // rdx
  int v45; // r10d
  unsigned int v46; // eax
  char *v47; // rsi
  __int64 v48; // r13
  unsigned int v49; // ecx
  int v50; // r9d
  void *v51; // r12
  __int64 v52; // rcx
  volatile signed __int16 *v53; // rax
  unsigned int v54; // eax
  __int64 v55; // rdx
  unsigned int v56; // esi
  _DWORD *v57; // rax
  int v58; // ecx
  __int64 v59; // rax
  __int64 v60; // r8
  volatile signed __int32 *v61; // rcx
  __int64 v62; // r8
  __int64 v63; // rax
  __int64 v64; // rcx
  __int64 v65; // rcx
  __int64 v66; // rax
  _QWORD *v67; // rcx
  _QWORD *v68; // rcx
  int v69; // edx
  __int64 v70; // rsi
  __int64 *v71; // rbx
  KIRQL v72; // bl
  bool v74; // [rsp+90h] [rbp+0h] BYREF
  char v75; // [rsp+91h] [rbp+1h]
  char v76; // [rsp+92h] [rbp+2h]
  char v77; // [rsp+93h] [rbp+3h]
  __int16 v78; // [rsp+94h] [rbp+4h]
  unsigned int v79; // [rsp+98h] [rbp+8h] BYREF
  unsigned int v80; // [rsp+9Ch] [rbp+Ch]
  int v81; // [rsp+A0h] [rbp+10h] BYREF
  int v82; // [rsp+A4h] [rbp+14h]
  int v83; // [rsp+A8h] [rbp+18h]
  unsigned int v84; // [rsp+ACh] [rbp+1Ch]
  void *v85; // [rsp+B0h] [rbp+20h]
  _QWORD *v86; // [rsp+B8h] [rbp+28h] BYREF
  _QWORD *v87; // [rsp+C0h] [rbp+30h] BYREF
  __int64 *v88; // [rsp+C8h] [rbp+38h]
  int v89; // [rsp+D0h] [rbp+40h]
  int v90; // [rsp+D4h] [rbp+44h] BYREF
  unsigned int v91; // [rsp+D8h] [rbp+48h] BYREF
  unsigned int v92; // [rsp+DCh] [rbp+4Ch]
  int v93; // [rsp+E0h] [rbp+50h]
  __int64 *v94; // [rsp+E8h] [rbp+58h]
  void *Src; // [rsp+F0h] [rbp+60h]
  __int64 v96; // [rsp+F8h] [rbp+68h] BYREF
  __int64 v97; // [rsp+100h] [rbp+70h] BYREF
  __int64 v98; // [rsp+108h] [rbp+78h] BYREF
  __int128 v99; // [rsp+110h] [rbp+80h] BYREF
  __int128 v100; // [rsp+120h] [rbp+90h]
  __int64 v101; // [rsp+130h] [rbp+A0h] BYREF
  __int64 v102; // [rsp+138h] [rbp+A8h] BYREF
  __int64 v103; // [rsp+140h] [rbp+B0h] BYREF
  __int64 v104; // [rsp+148h] [rbp+B8h]
  char *v105; // [rsp+150h] [rbp+C0h] BYREF
  int v106; // [rsp+158h] [rbp+C8h]
  int v107; // [rsp+15Ch] [rbp+CCh]
  _QWORD v108[12]; // [rsp+160h] [rbp+D0h] BYREF
  _QWORD v109[12]; // [rsp+1C0h] [rbp+130h] BYREF
  _OWORD v110[2]; // [rsp+220h] [rbp+190h] BYREF

  v88 = a2;
  v78 = a4;
  v93 = a3;
  v97 = 0;
  v87 = 0;
  v102 = 0;
  v103 = 0;
  v101 = 0;
  v90 = 0;
  v81 = 0;
  memset(v110, 0, sizeof(v110));
  v96 = 0;
  v91 = 0;
  memset(v109, 0, sizeof(v109));
  memset(v108, 0, sizeof(v108));
  v6 = 4;
  v79 = 0;
  if ( byte_1401F96F0 )
    v6 = HIDWORD(qword_1401F96CC);
  v99 = 0;
  v100 = 0;
  v7 = 24 * v6 + 15;
  if ( v7 <= 24 * v6 )
    v7 = 0xFFFFFFFFFFFFFF0LL;
  v8 = alloca(v7 & 0xFFFFFFFFFFFFFFF0uLL);
  if ( qword_1401F96E0 )
  {
    LODWORD(v109[0]) = -267522035;
    HIDWORD(v109[1]) = KeGetCurrentProcessorNumberEx(0);
    BYTE4(v109[0]) = 0;
    v109[3] = 0;
    v109[2] = 1;
    memset(&v109[6], 0, 20);
    HIDWORD(v109[5]) = 0;
    LODWORD(v109[1]) = qword_1401F96E0 != 0 ? 5 : 1;
    LOBYTE(v109[5]) = 0;
    v109[4] = &v109[7];
    if ( &v74 )
    {
      HIDWORD(v109[8]) = v6;
      v109[9] = &v74;
    }
    else
    {
      HIDWORD(v109[8]) = 0;
      v109[9] = 0;
    }
    v109[10] = &g_BatchLibContext;
  }
  v9 = *a1;
  v10 = &v86;
  Src = 0;
  v11 = a3;
  v86 = 0;
  v104 = *(_QWORD *)(v9 + 680);
  v12 = v104;
  KeGetCurrentProcessorNumberEx(0);
  v13 = v12 && *(_BYTE *)(v12 + 1877);
  v14 = 4;
  v74 = v13;
  if ( byte_1401F96F0 )
    v14 = HIDWORD(qword_1401F96CC);
  v15 = 24 * v14 + 15;
  if ( v15 <= 24 * v14 )
    v15 = 0xFFFFFFFFFFFFFF0LL;
  v16 = alloca(v15 & 0xFFFFFFFFFFFFFFF0uLL);
  v17 = !v13;
  if ( v13 || qword_1401F96E0 )
  {
    LODWORD(v108[0]) = -267522035;
    CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
    v108[2] = 1;
    HIDWORD(v108[1]) = CurrentProcessorNumber;
    v108[3] = v109;
    BYTE4(v108[0]) = 0;
    memset(&v108[6], 0, 20);
    HIDWORD(v108[5]) = 0;
    LOBYTE(v108[5]) = 0;
    v108[4] = &v108[7];
    LODWORD(v108[1]) = (2 * v17) | (qword_1401F96E0 != 0 ? 4 : 0);
    if ( &v74 )
    {
      HIDWORD(v108[8]) = v14;
      v108[9] = &v74;
    }
    else
    {
      HIDWORD(v108[8]) = 0;
      v108[9] = 0;
    }
    v108[10] = &g_BatchLibContext;
  }
  v19 = *(_QWORD *)(v9 + 564);
  v89 = *(_DWORD *)(v9 + 856);
  v20 = KeAcquireSpinLockRaiseToDpc(a1 + 13);
  v22 = v88;
  v23 = v20;
  while ( 1 )
  {
    v24 = 0;
    if ( !v22 )
      break;
    if ( (int)SegLibPDLsoInitialize(v22, v21, v110, &v79) < 0 )
    {
LABEL_34:
      ((void (__fastcall *)(_QWORD, __int64 *, __int64))a1[3])(*a1, v22, 2);
      break;
    }
    while ( v24 <= v79 )
    {
      SegLibPDLsoGetCurrentSegmentPacketSize(v22, v24, v110, &v81);
      if ( BYTE1(WPP_GLOBAL_Control->Timer) > 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
        WPP_RECORDER_SF_I(
          WPP_GLOBAL_Control->DeviceExtension,
          0,
          22,
          68,
          (__int64)WPP_da01b6527bcc3df100ab88c9816e11cf_Traceguids,
          (char)v22);
      if ( (int)RndisDevHostInternalAllocateSingleSubAllocation(a1, (unsigned int)(v89 + v81), &v87, &v98) < 0 )
        goto LABEL_34;
      v25 = v87;
      ++v24;
      *v10 = v87;
      v10 = v25;
    }
    v22 = (__int64 *)*v22;
  }
  KeReleaseSpinLock(a1 + 13, v23);
  if ( *v10 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v26,
      19,
      69,
      (__int64)WPP_da01b6527bcc3df100ab88c9816e11cf_Traceguids,
      (__int64)"*nextTransferPage == NULL");
    if ( *v10 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  v27 = v88;
  v28 = v86;
  v80 = 0;
  v79 = 0;
  v29 = v78;
  v94 = v88;
LABEL_39:
  if ( v28 )
  {
    v83 = RndisDevDeviceAcquireOperation(a1 + 32, &v97, v29);
    v33 = v83;
    if ( v83 >= 0 )
    {
      v87 = v28;
      v34 = 0;
      v82 = 0;
      v35 = v28;
      while ( 1 )
      {
        v84 = v34;
        if ( v34 >= *((_DWORD *)a1 + 10) || !v35 )
        {
          LOBYTE(v27) = (_BYTE)v88;
          v33 = v83;
LABEL_118:
          v68 = v108;
          LOBYTE(v32) = 1;
          if ( v74 )
            v68 = v109;
          BLFlushBatchOpContextEx(v68, 0, v32);
          VncFlushBatchRndisContext(&v99);
          if ( v33 >= 0 )
          {
            if ( !v84 )
            {
              WPP_RECORDER_SF_s(
                VmsIfrLog,
                v69,
                19,
                70,
                (__int64)WPP_da01b6527bcc3df100ab88c9816e11cf_Traceguids,
                (__int64)"numPacketsCombined > 0");
              MicrosoftTelemetryAssertTriggeredNoArgsKM();
            }
            v70 = v97;
            v29 = v78;
            *v10 = 0;
            *(_QWORD *)(v70 + 904) = v86;
            v86 = v28;
            if ( v29 == 0xFFFF )
            {
              WPP_RECORDER_SF_s(
                VmsIfrLog,
                v69,
                19,
                71,
                (__int64)WPP_da01b6527bcc3df100ab88c9816e11cf_Traceguids,
                (__int64)"ChannelIndex < 0xFFFF");
              MicrosoftTelemetryAssertTriggeredNoArgsKM();
            }
            ((void (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, unsigned int))a1[2])(
              *a1,
              *(_QWORD *)(v70 + 904),
              v70,
              0,
              v29 | 0xFFFF0000);
            v27 = v88;
            goto LABEL_39;
          }
          RndisDevDeviceReleaseOperation(a1 + 32, v97);
LABEL_129:
          v28 = v86;
          goto LABEL_130;
        }
        if ( !v80 )
        {
          v83 = SegLibPDLsoInitialize(v94, v30, v110, &v79);
          v33 = v83;
          if ( v83 < 0 )
          {
            LOBYTE(v27) = (_BYTE)v88;
            ((void (__fastcall *)(_QWORD, __int64 *, __int64))a1[3])(*a1, v88, 2);
            goto LABEL_118;
          }
        }
        v36 = v80;
        SegLibPDLsoGetCurrentSegmentPacketSize(v94, v80, v110, &v81);
        v37 = v81;
        v38 = v81 + v89;
        v92 = v81 + v89;
        LOBYTE(v39) = 1;
        VmsPDConvertPDMetaDataToNblOOB(
          (_DWORD)v94,
          v39,
          (unsigned int)&v102,
          0,
          0,
          (__int64)&v103,
          (__int64)&v101,
          (__int64)&v90);
        v40 = (void *)(a1[7] + *((unsigned int *)v35 + 4));
        v85 = v40;
        if ( !v74 )
        {
          v41 = dword_1401F9940;
          Src = 0;
          if ( v38 <= dword_1401F9940 )
            break;
        }
LABEL_61:
        v45 = (int)v40;
        if ( Src )
          v45 = (int)Src;
        if ( (v19 & 0x40) != 0 )
          v46 = v101 & 0xFFFFFF;
        else
          v46 = 0;
        v47 = (char *)RndisDevHostInternalPrepareRndisPacketMessage(
                        v45,
                        0,
                        (unsigned int)&v96,
                        (unsigned int)&v91,
                        v38,
                        v37,
                        1,
                        (unsigned int)v102 & v11,
                        0,
                        v103,
                        0,
                        v46,
                        v90,
                        0,
                        0,
                        0,
                        0,
                        0);
        SegLibPDDeferredLsoCopySegments((__int64)v109, v47, (__int64)v94, v36, (__int64)v110);
        v48 = v91;
        v107 = 0;
        v105 = v47;
        v106 = v37;
        v49 = *(_DWORD *)(v96 + v91);
        v98 = v49;
        v77 = (v49 & 0x24) != 0;
        v30 = (_QWORD *)(v49 & 9);
        v76 = (v49 & 9) != 0;
        v32 = v49 & 0x12;
        v75 = (v49 & 0x12) != 0;
        if ( (v49 & 0x24) == 0 || (v49 & 9) == 0 && (v49 & 0x12) == 0 )
        {
          if ( (v11 & 0x20) != 0 || (v11 & 8) != 0 || (v11 & 0x10) != 0 )
          {
            LOBYTE(v32) = 1;
            BLFlushBatchOpContextEx(v109, 0, v32);
            LOBYTE(v50) = (v11 & 0x20) != 0;
            VncChecksumVerifyHeaders(
              (unsigned int)v109,
              (unsigned int)&v105,
              0,
              v50,
              (v11 & 8) != 0,
              (v11 & 0x10) != 0,
              v77,
              v76,
              v75,
              (__int64)&v98,
              v104);
            v49 = v98;
          }
          v38 = v92;
        }
        v51 = Src;
        *(_DWORD *)(v96 + v48) = v11 & v49;
        if ( v51 )
        {
          v52 = v108[10];
          if ( *(_BYTE *)(v108[10] + 1LL) == 1 && !BYTE4(v108[0]) )
          {
            v53 = 0;
            BYTE4(v108[0]) = 1;
            if ( HIDWORD(v108[1]) != -1 )
            {
              v30 = *(_QWORD **)(v108[10] + 24LL);
              if ( v30 )
                v53 = (volatile signed __int16 *)v30 + 10 * HIDWORD(v108[1]);
            }
            _InterlockedAdd16(v53 + 8, 1u);
            v52 = v108[10];
          }
          v54 = *(_DWORD *)(v52 + 4);
          if ( v54 )
          {
            v30 = (_QWORD *)v108[4];
            v56 = *(_DWORD *)(v108[4] + 8LL);
            if ( v56 >= *(_DWORD *)(v108[4] + 12LL) )
            {
              v56 = 0;
              if ( LODWORD(v108[2]) < v54
                && (v57 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v52 + 64)), (v30 = v57) != 0) )
              {
                *(_QWORD *)v57 = 0;
                v57[2] = 0;
                v58 = *(_DWORD *)(v108[10] + 8LL);
                *((_QWORD *)v57 + 2) = v57 + 6;
                v57[3] = v58;
                *(_QWORD *)v108[4] = v57;
                ++LODWORD(v108[2]);
                v108[4] = v57;
                if ( *(_BYTE *)(v108[10] + 1LL) == 1 )
                {
                  v59 = 0;
                  if ( HIDWORD(v108[1]) != -1 )
                  {
                    v60 = *(_QWORD *)(v108[10] + 24LL);
                    if ( v60 )
                      v59 = v60 + 20LL * HIDWORD(v108[1]);
                  }
                  _InterlockedAdd16((volatile signed __int16 *)(v59 + 12), 1u);
                  v61 = 0;
                  if ( HIDWORD(v108[1]) != -1 )
                  {
                    v62 = *(_QWORD *)(v108[10] + 24LL);
                    if ( v62 )
                      v61 = (volatile signed __int32 *)(v62 + 20LL * HIDWORD(v108[1]));
                  }
                  _InterlockedAdd(v61, 1u);
                }
              }
              else
              {
                LOBYTE(v30) = 1;
                BLFlushBatchOpContextEx(v108, v30, 0);
                v30 = &v108[7];
              }
            }
            ++HIDWORD(v108[2]);
            ++*((_DWORD *)v30 + 2);
            v32 = v108[10];
            if ( *(_BYTE *)(v108[10] + 1LL) == 1 )
            {
              v63 = 0;
              if ( HIDWORD(v108[1]) != -1 )
              {
                v32 = *(_QWORD *)(v108[10] + 24LL);
                if ( v32 )
                  v63 = v32 + 20LL * HIDWORD(v108[1]);
              }
              _InterlockedAdd16((volatile signed __int16 *)(v63 + 14), 1u);
              v64 = 0;
              if ( HIDWORD(v108[1]) != -1 )
              {
                v32 = *(_QWORD *)(v108[10] + 24LL);
                if ( v32 )
                  v64 = v32 + 20LL * HIDWORD(v108[1]);
              }
              _InterlockedAdd((volatile signed __int32 *)(v64 + 4), 1u);
            }
            v65 = 3LL * v56;
            v66 = v30[2];
            *(_QWORD *)(v66 + 8 * v65) = v85;
            *(_DWORD *)(v66 + 8 * v65 + 16) = (16 * v38) | 1;
            *(_QWORD *)(v66 + 8 * v65 + 8) = v51;
          }
          else
          {
            if ( HIDWORD(v108[2]) )
            {
              LOBYTE(v30) = 1;
              BLFlushBatchOpContextEx(v108, v30, 0);
              v52 = v108[10];
            }
            v55 = LODWORD(v108[1]);
            if ( (v108[1] & 5) == 5 || (v55 = v108[1] & 6, (v108[1] & 6) == 6) )
            {
              (*(void (__fastcall **)(__int64, __int64, __int64))(v52 + 32))(v52, v55, v32);
              memmove(v85, v51, v38);
              (*(void (**)(void))(v108[10] + 40LL))();
            }
            else
            {
              memmove(v85, v51, v38);
            }
          }
        }
        v10 = v87;
        ++v80;
        v35 = (_QWORD *)*v87;
        v28 = (_QWORD *)*v87;
        v87 = (_QWORD *)*v87;
        if ( v80 > v79 )
        {
          if ( ++v82 >= (unsigned int)VmsVmMaxNBLsPerFlush )
          {
            v67 = v108;
            LOBYTE(v32) = 1;
            if ( v74 )
              v67 = v109;
            BLFlushBatchOpContextEx(v67, 0, v32);
            VncFlushBatchRndisContext(&v99);
            v82 = 0;
          }
          v80 = 0;
          v79 = 0;
          v94 = (__int64 *)*v94;
        }
        v34 = v84 + 1;
      }
      v42 = DWORD1(v99) % VmsVmBatchCopyRndisBatchSize;
      if ( DWORD1(v99) % VmsVmBatchCopyRndisBatchSize )
      {
        v43 = (_QWORD *)*((_QWORD *)&v100 + 1);
      }
      else
      {
        v43 = ExAllocateFromNPagedLookasideList(&stru_1401F9980);
        if ( !v43 )
        {
LABEL_60:
          LODWORD(v40) = (_DWORD)v85;
          goto LABEL_61;
        }
        if ( (VmsDiagnosticFlags & 2) != 0 )
        {
          v44 = 5440LL * (unsigned int)v99;
          _InterlockedAdd16((volatile signed __int16 *)((char *)VmsPlanCpuTable + v44 + 504), 1u);
          _InterlockedAdd((volatile signed __int32 *)((char *)VmsPlanCpuTable + v44 + 488), 1u);
        }
        *v43 = 0;
        if ( DWORD1(v99) )
          **((_QWORD **)&v100 + 1) = v43;
        else
          *(_QWORD *)&v100 = v43;
        v41 = dword_1401F9940;
        *((_QWORD *)&v100 + 1) = v43;
      }
      ++DWORD1(v99);
      Src = (char *)v43 + v41 * v42 + 8;
      memset(Src, 0, v38);
      if ( (VmsDiagnosticFlags & 2) != 0 && !BYTE8(v99) )
      {
        BYTE8(v99) = 1;
        _InterlockedAdd16((volatile signed __int16 *)VmsPlanCpuTable + 2720 * (unsigned int)v99 + 251, 1u);
      }
      goto LABEL_60;
    }
    v71 = v27;
    if ( v27 )
    {
      do
      {
        ((void (__fastcall *)(_QWORD, __int64 *, __int64))a1[3])(*a1, v71, 2);
        v71 = (__int64 *)*v71;
      }
      while ( v71 );
      goto LABEL_129;
    }
LABEL_130:
    WPP_RECORDER_SF_qqDLd(
      v31,
      (_DWORD)v30,
      v32,
      72,
      (__int64)WPP_da01b6527bcc3df100ab88c9816e11cf_Traceguids,
      (char)a1,
      (char)v27,
      v93,
      v78,
      v33);
    if ( v28 )
    {
      v72 = KeAcquireSpinLockRaiseToDpc(a1 + 13);
      RndisDevHostInternalFreeSubAllocation(a1, v28);
      KeReleaseSpinLock(a1 + 13, v72);
    }
  }
  else
  {
    return 0;
  }
  return (unsigned int)v33;
}

```

## disassembly

```asm
0x140092168  push    rbp
0x14009216a  push    rbx
0x14009216b  push    rsi
0x14009216c  push    rdi
0x14009216d  push    r12
0x14009216f  push    r13
0x140092171  push    r14
0x140092173  push    r15
0x140092175  sub     rsp, 258h
0x14009217c  lea     rbp, [rsp+90h]
0x140092184  mov     rax, cs:__security_cookie
0x14009218b  xor     rax, rbp
0x14009218e  mov     [rbp+200h+var_50], rax
0x140092195  xor     r12d, r12d
0x140092198  mov     esi, r8d
0x14009219b  xorps   xmm0, xmm0
0x14009219e  mov     [rbp+200h+var_1C8], rdx
0x1400921a2  mov     r14, rcx
0x1400921a5  mov     [rbp+200h+var_1FC], r9w
0x1400921aa  xor     edx, edx; Val
0x1400921ac  mov     [rbp+200h+var_1B0], esi
0x1400921af  lea     ebx, [r12+60h]
0x1400921b4  mov     [rbp+200h+var_190], r12
0x1400921b8  mov     r8d, ebx; Size
0x1400921bb  mov     [rbp+200h+var_1D0], r12
0x1400921bf  lea     rcx, [rbp+200h+var_D0]; void *
0x1400921c6  mov     [rbp+200h+var_158], r12
0x1400921cd  mov     [rbp+200h+var_150], r12
0x1400921d4  mov     [rbp+200h+var_160], r12
0x1400921db  mov     [rbp+200h+var_1BC], r12d
0x1400921df  mov     [rbp+200h+var_1F0], r12d
0x1400921e3  movups  [rbp+200h+var_70], xmm0
0x1400921ea  mov     [rbp+200h+var_198], r12
0x1400921ee  movups  [rbp+200h+var_60], xmm0
0x1400921f5  mov     [rbp+200h+var_1B8], r12d
0x1400921f9  call    memset
0x1400921fe  mov     r8d, ebx; Size
0x140092201  lea     rcx, [rbp+200h+var_130]; void *
0x140092208  xor     edx, edx; Val
0x14009220a  call    memset
0x14009220f  cmp     cs:byte_1401F96F0, r12b
0x140092216  lea     ebx, [r12+4]
0x14009221b  xorps   xmm0, xmm0
0x14009221e  mov     [rbp+200h+var_1F8], r12d
0x140092222  cmovnz  ebx, dword ptr cs:qword_1401F96CC+4
0x140092229  mov     rdx, 0FFFFFFFFFFFFFF0h
0x140092233  movups  [rbp+200h+var_180], xmm0
0x14009223a  movups  [rbp+200h+var_170], xmm0
0x140092241  lea     rcx, [rbx+rbx*2]
0x140092245  shl     rcx, 3
0x140092249  lea     rax, [rcx+0Fh]
0x14009224d  cmp     rax, rcx
0x140092250  ja      short loc_140092255
0x140092252  mov     rax, rdx
0x140092255  and     rax, 0FFFFFFFFFFFFFFF0h
0x140092259  call    __chkstk_0
0x14009225e  sub     rsp, rax
0x140092261  lea     r13, g_BatchLibContext
0x140092268  cmp     cs:qword_1401F96E0, r12
0x14009226f  mov     r15d, 1
0x140092275  lea     rdi, [rsp+290h+var_200]
0x14009227d  jz      loc_140092328
0x140092283  xor     ecx, ecx; ProcNumber
0x140092285  mov     [rbp+200h+var_D0], 0F00DF00Dh
0x14009228f  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140092296  nop     dword ptr [rax+rax+00h]
0x14009229b  mov     [rbp+200h+var_C4], eax
0x1400922a1  mov     rax, cs:qword_1401F96E0
0x1400922a8  neg     rax
0x1400922ab  mov     [rbp+200h+var_CC], r12b
0x1400922b2  lea     rax, [rbp+200h+var_98]
0x1400922b9  mov     [rbp+200h+var_B8], r12
0x1400922c0  sbb     ecx, ecx
0x1400922c2  mov     [rbp+200h+var_C0], r15
0x1400922c9  and     ecx, 4
0x1400922cc  mov     [rbp+200h+var_A0], r12
0x1400922d3  add     ecx, r15d
0x1400922d6  mov     [rbp+200h+var_A4], r12d
0x1400922dd  mov     [rbp+200h+var_C8], ecx
0x1400922e3  mov     [rbp+200h+var_A8], r12b
0x1400922ea  mov     [rbp+200h+var_98], r12
0x1400922f1  mov     [rbp+200h+var_90], r12d
0x1400922f8  mov     [rbp+200h+var_B0], rax
0x1400922ff  test    rdi, rdi
0x140092302  jz      short loc_140092313
0x140092304  mov     [rbp+200h+var_8C], ebx
0x14009230a  mov     [rbp+200h+var_88], rdi
0x140092311  jmp     short loc_140092321
0x140092313  mov     [rbp+200h+var_8C], r12d
0x14009231a  mov     [rbp+200h+var_88], r12
0x140092321  mov     [rbp+200h+var_80], r13
0x140092328  mov     r15, [r14]
0x14009232b  lea     r13, [rbp+200h+var_1D8]
0x14009232f  xor     ecx, ecx; ProcNumber
0x140092331  mov     [rbp+200h+Src], r12
0x140092335  mov     rbx, rsi
0x140092338  mov     [rbp+200h+var_1D8], r12
0x14009233c  mov     rdi, [r15+2A8h]
0x140092343  mov     [rbp+200h+var_148], rdi
0x14009234a  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140092351  nop     dword ptr [rax+rax+00h]
0x140092356  test    rdi, rdi
0x140092359  jz      short loc_14009236F
0x14009235b  cmp     [rdi+755h], r12b
0x140092362  jz      short loc_14009236F
0x140092364  mov     r8d, 1
0x14009236a  mov     dl, r8b
0x14009236d  jmp     short loc_140092378
0x14009236f  mov     dl, r12b
0x140092372  mov     r8d, 1
0x140092378  cmp     cs:byte_1401F96F0, r12b
0x14009237f  mov     esi, 4
0x140092384  mov     [rbp+200h+var_200], dl
0x140092387  cmovnz  esi, dword ptr cs:qword_1401F96CC+4
0x14009238e  lea     rcx, [rsi+rsi*2]
0x140092392  shl     rcx, 3
0x140092396  lea     rax, [rcx+0Fh]
0x14009239a  cmp     rax, rcx
0x14009239d  ja      short loc_1400923A9
0x14009239f  mov     rax, 0FFFFFFFFFFFFFF0h
0x1400923a9  and     rax, 0FFFFFFFFFFFFFFF0h
0x1400923ad  call    __chkstk_0
0x1400923b2  sub     rsp, rax
0x1400923b5  mov     dil, dl
0x1400923b8  xor     dil, r8b
0x1400923bb  lea     r12, [rsp+290h+var_200]
0x1400923c3  cmp     dil, r8b
0x1400923c6  jnz     short loc_1400923D7
0x1400923c8  xor     eax, eax
0x1400923ca  cmp     cs:qword_1401F96E0, rax
0x1400923d1  jz      loc_140092497
0x1400923d7  xor     ecx, ecx; ProcNumber
0x1400923d9  mov     [rbp+200h+var_130], 0F00DF00Dh
0x1400923e3  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400923ea  nop     dword ptr [rax+rax+00h]
0x1400923ef  xor     r8d, r8d
0x1400923f2  mov     [rbp+200h+var_120], 1
0x1400923fd  mov     [rbp+200h+var_124], eax
0x140092403  lea     rax, [rbp+200h+var_D0]
0x14009240a  mov     [rbp+200h+var_118], rax
0x140092411  movzx   eax, dil
0x140092415  mov     [rbp+200h+var_12C], r8b
0x14009241c  mov     [rbp+200h+var_100], r8
0x140092423  mov     [rbp+200h+var_104], r8d
0x14009242a  lea     edx, [rax+rax]
0x14009242d  mov     [rbp+200h+var_108], r8b
0x140092434  mov     rax, cs:qword_1401F96E0
0x14009243b  neg     rax
0x14009243e  mov     [rbp+200h+var_F8], r8
0x140092445  lea     rax, [rbp+200h+var_F8]
0x14009244c  mov     [rbp+200h+var_F0], r8d
0x140092453  sbb     ecx, ecx
0x140092455  mov     [rbp+200h+var_110], rax
0x14009245c  and     ecx, 4
0x14009245f  or      ecx, edx
0x140092461  mov     [rbp+200h+var_128], ecx
0x140092467  test    r12, r12
0x14009246a  jz      short loc_14009247B
0x14009246c  mov     [rbp+200h+var_EC], esi
0x140092472  mov     [rbp+200h+var_E8], r12
0x140092479  jmp     short loc_140092489
0x14009247b  mov     [rbp+200h+var_EC], r8d
0x140092482  mov     [rbp+200h+var_E8], r8
0x140092489  lea     rax, g_BatchLibContext
0x140092490  mov     [rbp+200h+var_E0], rax
0x140092497  mov     eax, [r15+358h]
0x14009249e  lea     rcx, [r14+68h]; SpinLock
0x1400924a2  mov     rdi, [r15+234h]
0x1400924a9  mov     [rbp+200h+var_1C0], eax
0x1400924ac  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400924b3  nop     dword ptr [rax+rax+00h]
0x1400924b8  mov     rsi, [rbp+200h+var_1C8]
0x1400924bc  mov     r12b, al
0x1400924bf  xor     r15d, r15d
0x1400924c2  test    rsi, rsi
0x1400924c5  jz      loc_1400925C3
0x1400924cb  lea     r9, [rbp+200h+var_1F8]
0x1400924cf  mov     rcx, rsi
0x1400924d2  lea     r8, [rbp+200h+var_70]
0x1400924d9  call    SegLibPDLsoInitialize
0x1400924de  mov     ecx, eax
0x1400924e0  test    eax, eax
0x1400924e2  js      loc_1400925A1
0x1400924e8  cmp     r15d, [rbp+200h+var_1F8]
0x1400924ec  ja      loc_140092572
0x1400924f2  lea     r9, [rbp+200h+var_1F0]
0x1400924f6  mov     edx, r15d
0x1400924f9  lea     r8, [rbp+200h+var_70]
0x140092500  mov     rcx, rsi
0x140092503  call    SegLibPDLsoGetCurrentSegmentPacketSize
0x140092508  mov     rcx, cs:WPP_GLOBAL_Control
0x14009250f  cmp     byte ptr [rcx+29h], 5
0x140092513  ja      short loc_14009251D
0x140092515  xor     eax, eax
0x140092517  cmp     [rcx+48h], ax
0x14009251b  jz      short loc_140092543
0x14009251d  mov     rcx, [rcx+40h]
0x140092521  lea     rax, WPP_da01b6527bcc3df100ab88c9816e11cf_Traceguids
0x140092528  mov     r9d, 44h ; 'D'
0x14009252e  mov     [rsp+290h+var_268], rsi
0x140092533  xor     edx, edx
0x140092535  mov     [rsp+290h+var_270], rax
0x14009253a  lea     r8d, [r9-2Eh]
0x14009253e  call    WPP_RECORDER_SF_I
0x140092543  mov     edx, [rbp+200h+var_1F0]
0x140092546  lea     r9, [rbp+200h+var_188]
0x14009254a  add     edx, [rbp+200h+var_1C0]
0x14009254d  lea     r8, [rbp+200h+var_1D0]
0x140092551  mov     rcx, r14
0x140092554  call    RndisDevHostInternalAllocateSingleSubAllocation
0x140092559  mov     ecx, eax
0x14009255b  test    eax, eax
0x14009255d  js      short loc_14009257A
0x14009255f  mov     rax, [rbp+200h+var_1D0]
0x140092563  inc     r15d
0x140092566  mov     [r13+0], rax
0x14009256a  mov     r13, rax
0x14009256d  jmp     loc_1400924E8
0x140092572  mov     rsi, [rsi]
0x140092575  jmp     loc_1400924BF
0x14009257a  mov     rax, [r14+18h]
0x14009257e  xor     r9d, r9d
0x140092581  mov     dword ptr [rsp+290h+var_268], 0E0002061h
0x140092589  mov     rdx, rsi
0x14009258c  mov     dword ptr [rsp+290h+var_270], ecx
0x140092590  mov     rcx, [r14]
0x140092593  lea     r8d, [r9+2]
0x140092597  call    _guard_dispatch_icall
0x14009259c  xor     r15d, r15d
0x14009259f  jmp     short loc_1400925C3
0x1400925a1  mov     rax, [r14+18h]
0x1400925a5  xor     r9d, r9d
0x1400925a8  mov     dword ptr [rsp+290h+var_268], 0E0002060h
0x1400925b0  mov     rdx, rsi
0x1400925b3  mov     dword ptr [rsp+290h+var_270], ecx
0x1400925b7  mov     rcx, [r14]
0x1400925ba  lea     r8d, [r9+2]
0x1400925be  call    _guard_dispatch_icall
0x1400925c3  mov     dl, r12b; NewIrql
0x1400925c6  lea     rcx, [r14+68h]; SpinLock
0x1400925ca  call    cs:__imp_KeReleaseSpinLock
0x1400925d1  nop     dword ptr [rax+rax+00h]
0x1400925d6  cmp     [r13+0], r15
0x1400925da  jz      short loc_140092615
0x1400925dc  mov     rcx, cs:VmsIfrLog
0x1400925e3  lea     rax, aNexttransferpa; "*nextTransferPage == NULL"
0x1400925ea  mov     [rsp+290h+var_268], rax
0x1400925ef  mov     r9d, 45h ; 'E'
0x1400925f5  lea     rax, WPP_da01b6527bcc3df100ab88c9816e11cf_Traceguids
0x1400925fc  mov     [rsp+290h+var_270], rax
0x140092601  lea     r8d, [r9-32h]
0x140092605  call    WPP_RECORDER_SF_s
0x14009260a  cmp     [r13+0], r15
0x14009260e  jz      short loc_140092615
0x140092610  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "*nextTransferPage == ((void *)0)")
0x140092615  mov     rsi, [rbp+200h+var_1C8]
0x140092619  mov     r12, [rbp+200h+var_1D8]
0x14009261d  mov     [rbp+200h+var_1F4], r15d
0x140092621  mov     [rbp+200h+var_1F8], r15d
0x140092625  movzx   r15d, [rbp+200h+var_1FC]
0x14009262a  mov     [rbp+200h+var_1A8], rsi
0x14009262e  xor     eax, eax
0x140092630  test    r12, r12
0x140092633  jz      loc_140092ED3
0x140092639  lea     rcx, [r14+100h]
0x140092640  movzx   r8d, r15w
0x140092644  lea     rdx, [rbp+200h+var_190]
0x140092648  call    RndisDevDeviceAcquireOperation
0x14009264d  xor     r9d, r9d
0x140092650  mov     [rbp+200h+var_1E8], eax
0x140092653  mov     r15d, eax
0x140092656  test    eax, eax
0x140092658  js      loc_140092E31
0x14009265e  mov     [rbp+200h+var_1D0], r12
0x140092662  mov     eax, r9d
0x140092665  mov     [rbp+200h+var_1EC], r9d
0x140092669  mov     rsi, r12
0x14009266c  mov     [rbp+200h+var_1E4], eax
0x14009266f  cmp     eax, [r14+28h]
0x140092673  jnb     loc_140092D1F
0x140092679  test    rsi, rsi
0x14009267c  jz      loc_140092D1F
0x140092682  cmp     [rbp+200h+var_1F4], r9d
0x140092686  jnz     short loc_1400926AA
0x140092688  mov     rcx, [rbp+200h+var_1A8]
0x14009268c  lea     r9, [rbp+200h+var_1F8]
0x140092690  lea     r8, [rbp+200h+var_70]
0x140092697  call    SegLibPDLsoInitialize
0x14009269c  mov     [rbp+200h+var_1E8], eax
0x14009269f  mov     r15d, eax
0x1400926a2  test    eax, eax
0x1400926a4  js      loc_140092CF3
0x1400926aa  mov     r13d, [rbp+200h+var_1F4]
0x1400926ae  lea     r9, [rbp+200h+var_1F0]
0x1400926b2  mov     rcx, [rbp+200h+var_1A8]
0x1400926b6  lea     r8, [rbp+200h+var_70]
0x1400926bd  mov     edx, r13d
0x1400926c0  call    SegLibPDLsoGetCurrentSegmentPacketSize
0x1400926c5  mov     r15d, [rbp+200h+var_1C0]
0x1400926c9  lea     rax, [rbp+200h+var_1BC]
  ... truncated ...
```
