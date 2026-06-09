# TdxTcpQueryInformationEx

- ea: `0x14001606c`
- end: `0x140016fe5`
- name: `TdxTcpQueryInformationEx`
- size: `3961`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140010f10`

## callees

- `0x14000ccfc`
- `0x140010608`
- `0x140010af0`
- `0x1400121d8`
- `0x1400148b0`
- `0x14001606c`
- `0x1400184b0`
- `0x1400184e0`
- `0x140018600`
- `0x140018900`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x140016c10`
- `ntoskrnl!KeReleaseMutex` at `0x140016e46`
- `ntoskrnl!KeReleaseMutex` at `0x140016c10`
- `ntoskrnl!KeReleaseMutex` at `0x140016e46`
- `ntoskrnl!IoAllocateMdl` at `0x140016139`
- `ntoskrnl!IoAllocateMdl` at `0x140016139`
- `ntoskrnl!MmProbeAndLockPages` at `0x14001616d`
- `ntoskrnl!MmProbeAndLockPages` at `0x14001616d`
- `ntoskrnl!MmUnlockPages` at `0x140016f76`
- `ntoskrnl!MmUnlockPages` at `0x140016f76`
- `ntoskrnl!IoFreeMdl` at `0x140016f4b`
- `ntoskrnl!IoFreeMdl` at `0x140016f85`
- `ntoskrnl!IoFreeMdl` at `0x140016f4b`
- `ntoskrnl!IoFreeMdl` at `0x140016f85`
- `ntoskrnl!ExAllocatePool3` at `0x140016105`
- `ntoskrnl!ExAllocatePool3` at `0x140016105`
- `ntoskrnl!KeReleaseSemaphore` at `0x140016ed6`
- `ntoskrnl!KeReleaseSemaphore` at `0x140016f20`
- `ntoskrnl!KeReleaseSemaphore` at `0x140016ed6`
- `ntoskrnl!KeReleaseSemaphore` at `0x140016f20`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016f99`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016f99`
- `ntoskrnl!KeWaitForSingleObject` at `0x140016bd5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140016e93`
- `ntoskrnl!KeWaitForSingleObject` at `0x140016bd5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140016e93`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x140016758`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x140016758`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x14001624d`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x140016782`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x1400167b4`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x140016af2`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x140016b21`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x140016e1c`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x140016f06`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x14001624d`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x140016782`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x1400167b4`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x140016af2`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x140016b21`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x140016e1c`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x140016f06`
- `NETIO!NsiGetAllParameters` at `0x1400163a5`
- `NETIO!NsiGetAllParameters` at `0x14001640c`
- `NETIO!NsiGetAllParameters` at `0x140016c77`
- `NETIO!NsiGetAllParameters` at `0x1400163a5`
- `NETIO!NsiGetAllParameters` at `0x14001640c`
- `NETIO!NsiGetAllParameters` at `0x140016c77`
- `NDIS!NdisIfGetInterfaceIndexFromNetLuid` at `0x14001668e`
- `NDIS!NdisIfGetInterfaceIndexFromNetLuid` at `0x14001668e`

## pseudocode

```c
__int64 __fastcall TdxTcpQueryInformationEx(__int64 a1, __int64 a2)
{
  __int64 v3; // rdx
  unsigned __int64 v4; // r13
  void *v5; // r12
  void *v6; // r15
  size_t v7; // rbx
  __int64 Pool3; // rax
  _DWORD *v9; // rsi
  struct _MDL *v11; // rax
  struct _MDL *v12; // r15
  int AllParameters; // ebx
  __int64 v14; // r9
  int *v15; // rcx
  __int64 v16; // r8
  unsigned int v17; // ecx
  int v18; // edx
  const NPI_MODULEID *v19; // r13
  int Value; // eax
  unsigned int v21; // r14d
  unsigned __int64 v22; // r12
  int v23; // eax
  __int128 *v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rbx
  __int64 v27; // r14
  __int64 v28; // rax
  struct _MDL *v29; // rbx
  size_t v30; // r12
  int v31; // r8d
  int j; // edx
  int v33; // ebx
  struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C i; // rax
  unsigned int v35; // r12d
  int v36; // eax
  __int64 v37; // rcx
  unsigned __int64 v38; // rbx
  unsigned __int64 v40; // [rsp+68h] [rbp-A70h] BYREF
  PMDL Mdl; // [rsp+70h] [rbp-A68h] BYREF
  ULONG pIfIndex[2]; // [rsp+78h] [rbp-A60h] BYREF
  unsigned int v43; // [rsp+80h] [rbp-A58h] BYREF
  __int64 v44; // [rsp+88h] [rbp-A50h] BYREF
  int v45; // [rsp+90h] [rbp-A48h] BYREF
  _QWORD v46[2]; // [rsp+98h] [rbp-A40h] BYREF
  NET_LUID NetLuid[2]; // [rsp+A8h] [rbp-A30h] BYREF
  int v48; // [rsp+B8h] [rbp-A20h]
  __int128 v49; // [rsp+C0h] [rbp-A18h] BYREF
  __int64 v50; // [rsp+D0h] [rbp-A08h]
  _DWORD v51[24]; // [rsp+E0h] [rbp-9F8h] BYREF
  _OWORD v52[2]; // [rsp+140h] [rbp-998h] BYREF
  __int128 v53; // [rsp+160h] [rbp-978h] BYREF
  __int64 v54; // [rsp+170h] [rbp-968h]
  _QWORD v55[72]; // [rsp+180h] [rbp-958h] BYREF
  _QWORD v56[82]; // [rsp+3C0h] [rbp-718h] BYREF
  _DWORD v57[276]; // [rsp+650h] [rbp-488h] BYREF

  v44 = a1;
  v40 = 0;
  v3 = *(unsigned int *)(a2 + 16);
  if ( (unsigned int)(v3 - 40) > 0x7FFFFFD7 )
    return 3221225485LL;
  v4 = *(unsigned int *)(a2 + 8);
  v43 = v4;
  if ( !(_DWORD)v4 )
    return 3221225485LL;
  v5 = *(void **)(a2 + 32);
  v6 = *(void **)(a1 + 112);
  v46[1] = 0;
  v46[0] = 1;
  v7 = (unsigned int)v3;
  Pool3 = ExAllocatePool3(64, v3, 544760916, v46, 1);
  v9 = (_DWORD *)Pool3;
  if ( !Pool3 )
    return 3221225626LL;
  *(_QWORD *)pIfIndex = Pool3;
  v11 = IoAllocateMdl(v6, v4, 0, 1u, 0);
  v12 = v11;
  Mdl = v11;
  if ( !v11 )
  {
    AllParameters = -1073741670;
    goto LABEL_111;
  }
  MmProbeAndLockPages(v11, *(_BYTE *)(a1 + 64), IoWriteAccess);
  if ( *(_BYTE *)(a1 + 64) )
    RtlCopyFromUser(v9, v5, v7);
  else
    RtlCopyVolatileMemory(v9, v5, v7);
  switch ( *v9 )
  {
    case 0:
      if ( v9[2] == 256 && v9[3] == 256 && !v9[4] )
      {
        KeWaitForSingleObject(&TdxEntityArraySemaphore, Executive, 0, 0, 0);
        v43 = TdxEntityCount;
        TdxAddDevicesToEntityList(v37, &v43);
        v38 = 8 * v43;
        if ( (unsigned int)v4 >= 8 * v43 )
        {
          RtlCopyKernelBufferToMdl(TdxEntityArray, v12, 0, v38, &v40);
          AllParameters = 0;
          KeReleaseSemaphore(&TdxEntityArraySemaphore, 0, 1, 0);
          goto LABEL_111;
        }
        KeReleaseSemaphore(&TdxEntityArraySemaphore, 0, 1, 0);
        v40 = v38;
        goto LABEL_23;
      }
      goto LABEL_29;
    case 0x200:
      Mdl = 0;
      memset(v57, 0, 0x444u);
      memset(v55, 0, 0xD8u);
      memset(v56, 0, 0x258u);
      memset(v51, 0, sizeof(v51));
      if ( v9[3] == 256 && v9[2] == 512 && v9[4] == 1 )
      {
        v33 = v9[1];
        KeWaitForSingleObject(&WPP_MAIN_CB.Dpc.DpcListEntry, Executive, 0, 0, 0);
        for ( i = WPP_MAIN_CB.DeviceQueue.1;
              ;
              i = **(struct _KDEVICE_QUEUE::$9FAF936D47973D5FBAA72DAF24011AE0::$18E3EACC1E717291AA7C720ECCD5C45C **)&i )
        {
          if ( *(struct _DEVICE_OBJECT **)&i == (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.DeviceQueue.Busy )
          {
            KeReleaseMutex((PRKMUTEX)&WPP_MAIN_CB.Dpc.DpcListEntry, 0);
            AllParameters = -1073741275;
            goto LABEL_111;
          }
          if ( *(_DWORD *)(*(_QWORD *)&i + 32LL) == v33 )
            break;
        }
        Mdl = *(PMDL *)(*(_QWORD *)&i + 24LL);
        KeReleaseMutex((PRKMUTEX)&WPP_MAIN_CB.Dpc.DpcListEntry, 0);
        v35 = 8;
        AllParameters = NsiGetAllParameters(3, &NPI_MS_NDIS_MODULEID, 0, &Mdl, 8, v57, 1092, v55, 216, v56, 600);
        if ( AllParameters )
          goto LABEL_111;
        v51[0] = v56[0];
        v51[1] = LOWORD(v56[65]);
        v51[2] = v55[2];
        v36 = v55[3];
        if ( v55[3] > 0xFFFFFFFF )
          v36 = -1;
        v51[3] = v36;
        if ( LOWORD(v57[134]) <= 8u )
          v35 = LOWORD(v57[134]);
        v51[4] = v35;
        memmove(&v51[5], (char *)&v57[134] + 2, v35);
        v51[7] = v57[4];
        v51[8] = v55[0];
        v51[9] = v55[5];
        v51[10] = v55[10];
        v51[11] = v55[11];
        v51[12] = LODWORD(v55[13]) + LODWORD(v55[12]);
        v51[13] = v55[8];
        v51[14] = v55[9];
        v51[15] = v55[7];
        v51[16] = v55[14];
        v51[17] = v55[15];
        v51[18] = LODWORD(v55[17]) + LODWORD(v55[16]);
        v51[20] = v55[18];
        v51[22] = WORD2(v56[0]);
        v40 = (unsigned int)WORD2(v56[0]) + 92;
        if ( v4 >= v40 )
        {
          RtlCopyKernelBufferToMdl(v51, v12, 0, 92, &v40);
          v14 = WORD2(v56[0]);
          v16 = 92;
          v15 = (int *)((char *)v56 + 6);
          goto LABEL_27;
        }
        goto LABEL_23;
      }
LABEL_89:
      AllParameters = -1073741822;
      goto LABEL_111;
    case 0x280:
      goto LABEL_89;
  }
  if ( *v9 != 769 )
  {
    if ( *v9 == 896 )
    {
      if ( v9[1] < 2u )
      {
        if ( v9[2] == 256 && v9[3] == 256 && v9[4] == 1 )
        {
          if ( (unsigned int)v4 < 4 )
            goto LABEL_22;
          v45 = 896;
LABEL_25:
          v14 = 4;
          v15 = &v45;
LABEL_26:
          v16 = 0;
LABEL_27:
          RtlCopyKernelBufferToMdl(v15, v12, v16, v14, &v40);
          goto LABEL_28;
        }
LABEL_29:
        AllParameters = -1073741811;
        goto LABEL_111;
      }
    }
    else if ( (unsigned int)(*v9 - 1024) < 2 && !v9[1] )
    {
      if ( v9[2] == 256 && v9[3] == 256 && v9[4] == 1 )
      {
        if ( (unsigned int)v4 < 4 )
        {
LABEL_22:
          v40 = 4;
LABEL_23:
          AllParameters = -1073741789;
          goto LABEL_111;
        }
        v45 = 1028 - (*v9 != 1024);
        goto LABEL_25;
      }
      goto LABEL_29;
    }
LABEL_16:
    AllParameters = -1073741808;
    goto LABEL_111;
  }
  v17 = v9[1];
  LODWORD(Mdl) = v17;
  if ( v17 >= 2 )
    goto LABEL_16;
  v18 = v9[3];
  if ( v18 != 256 )
    goto LABEL_68;
  if ( v9[4] == 1 )
  {
    memset(v51, 0, 0x5Cu);
    memset(v56, 0, 0x9Cu);
    memset(v55, 0, 0xD0u);
    pIfIndex[0] = 0;
    LODWORD(v44) = 0;
    *(_OWORD *)&NetLuid[0].Value = 0;
    v49 = 0;
    if ( (unsigned int)v4 < 0x5C )
    {
      v40 = 92;
      goto LABEL_23;
    }
    v19 = &NPI_MS_IPV4_MODULEID;
    if ( (_DWORD)Mdl )
      v19 = &NPI_MS_IPV6_MODULEID;
    AllParameters = NsiGetAllParameters(1, v19, 6, 0, 0, v56, 156, v55, 208, pIfIndex, 4);
    if ( AllParameters )
      goto LABEL_111;
    LODWORD(v44) = 0;
    AllParameters = NsiGetAllParameters(1, v19, 2, &v44, 4, NetLuid, 16, &v49, 16, 0, 0);
    if ( AllParameters )
      goto LABEL_111;
    v51[2] = v55[2];
    v51[3] = v55[16];
    v51[4] = v55[17];
    v51[5] = v55[4];
    v51[6] = HIDWORD(v55[17]);
    v51[7] = v55[20];
    v51[8] = v55[5];
    v51[9] = v55[6];
    v51[10] = HIDWORD(v55[23]);
    v51[11] = v55[21];
    v51[12] = HIDWORD(v55[20]);
    v51[13] = pIfIndex[0];
    v51[14] = HIDWORD(v55[18]);
    *(_QWORD *)&v51[15] = v55[19];
    *(_QWORD *)&v51[17] = v55[22];
    v51[19] = v55[23];
    v51[0] = (LODWORD(NetLuid[0].Value) == 1) + 1;
    v51[20] = v49;
    v51[21] = HIDWORD(v49);
    v51[22] = DWORD1(v49);
    Value = v56[3];
    if ( LODWORD(NetLuid[1].Value) != -1 )
      Value = NetLuid[1].Value;
    v51[1] = Value;
    v14 = 92;
    v15 = v51;
    goto LABEL_26;
  }
  if ( v9[4] != 258 || v17 )
  {
LABEL_68:
    AllParameters = -1073741822;
    if ( v18 != 256 || v9[4] != 259 || v17 )
      goto LABEL_111;
    *(_OWORD *)&NetLuid[0].Value = 0;
    v48 = 0;
    memset(v56, 0, sizeof(v56));
    memset(v55, 0, 0x238u);
    v49 = 0;
    v50 = 0;
    v28 = TdxLocateAndReferenceTransport(*(_QWORD *)(a2 + 40));
    if ( !v28 || *(_QWORD *)(v28 + 88) == *(_QWORD *)(a2 + 40) )
    {
      pIfIndex[0] = 16;
      v29 = (struct _MDL *)&NPI_MS_IPV4_MODULEID;
      v30 = 4;
      LODWORD(v4) = v43;
    }
    else
    {
      *(_QWORD *)pIfIndex = 24;
      v29 = (struct _MDL *)&NPI_MS_IPV6_MODULEID;
      v30 = 16;
    }
    Mdl = v29;
    DbgTdxDereferenceTransport(v28, "minio\\netio\\session\\tdi\\tdiprovider.c", 1193);
    memmove((char *)&v49 + 8, v9 + 6, v30);
    v31 = (int)v29;
    for ( j = 1; ; j = 2 )
    {
      AllParameters = TdxGetAllParameters(3, j, v31, 7, (__int64)&v49, 8, 0, 0, 0, 0, 0, 0);
      if ( AllParameters < 0 )
        break;
      AllParameters = TdxGetAllParameters(3, 0, (_DWORD)Mdl, 10, (__int64)&v49, pIfIndex[0], 0, 0, 0, 0, 0, 0);
      if ( !AllParameters )
        break;
      v31 = (int)Mdl;
    }
    if ( AllParameters )
      goto LABEL_111;
    AllParameters = TdxGetAllParameters(
                      1,
                      0,
                      (unsigned int)&NPI_MS_NDIS_MODULEID,
                      1,
                      (__int64)&v49,
                      8,
                      0,
                      0,
                      (__int64)v56,
                      656,
                      (__int64)v55,
                      568);
    if ( AllParameters )
      goto LABEL_111;
    if ( (unsigned int)v4 < (unsigned int)WORD2(v56[68]) + 16 )
      goto LABEL_23;
    if ( LOWORD(v55[65]) == (_WORD)AllParameters + 3 )
      LODWORD(NetLuid[0].Value) |= 1u;
    if ( LOWORD(v55[65]) == 4 )
      LODWORD(NetLuid[0].Value) |= 2u;
    if ( LODWORD(v55[66]) )
      LODWORD(NetLuid[0].Value) |= 4u;
    *((_DWORD *)&NetLuid[0].Info + 1) = v56[68];
    LODWORD(NetLuid[1].Value) = v56[78];
    *((_DWORD *)&NetLuid[1].Info + 1) = WORD2(v56[68]);
    RtlCopyKernelBufferToMdl(NetLuid, v12, 0, 16, &v40);
    RtlCopyKernelBufferToMdl((char *)&v56[68] + 6, v12, v40, WORD2(v56[68]), &v40);
    v40 = (unsigned int)WORD2(v56[68]) + 16;
LABEL_28:
    AllParameters = 0;
    goto LABEL_111;
  }
  *(_QWORD *)&v49 = 0;
  *((_QWORD *)&v49 + 1) = 0x100000000LL;
  v53 = 0;
  v54 = 0;
  *(_OWORD *)&NetLuid[0].Value = 0;
  memset(v52, 0, 28);
  LODWORD(v44) = 0;
  v21 = 0;
  pIfIndex[0] = 0;
  v50 = 0xFFFF;
  AllParameters = TdxGetAllParameters(
                    3,
                    1,
                    (unsigned int)&NPI_MS_IPV4_MODULEID,
                    10,
                    (__int64)NetLuid,
                    16,
                    (__int64)v52,
                    28,
                    0,
                    0,
                    0,
                    0);
  if ( AllParameters >= 0 )
  {
    v22 = v43;
    while ( AllParameters >= 0 )
    {
      if ( !NdisIfGetInterfaceIndexFromNetLuid(NetLuid[0], pIfIndex) )
      {
        LODWORD(Mdl) = v21 + 1;
        if ( v22 < 24 * (unsigned __int64)(v21 + 1) )
        {
          AllParameters = -2147483643;
          break;
        }
        *(_QWORD *)&v49 = __PAIR64__(pIfIndex[0], NetLuid[1].Value);
        if ( LOBYTE(v52[1]) >= 0x21u )
          v23 = -1;
        else
          v23 = *((_DWORD *)Ipv4Mask + LOBYTE(v52[1]));
        DWORD2(v49) = v23;
        v24 = &v49;
        if ( v21 )
        {
          if ( ((HIDWORD(v52[0]) - 3) & 0xFFFFFFFD) == 0 )
          {
            v25 = (unsigned int)v44;
            LODWORD(v44) = v44 + 1;
            if ( (_DWORD)v44 != v21 )
            {
              v26 = 24 * v25;
              RtlCopyMdlToKernelBuffer(v12, 24 * v25, &v53, 24, &v40);
              RtlCopyKernelBufferToMdl(&v49, v12, v26, 24, &v40);
              v24 = &v53;
            }
          }
        }
        RtlCopyKernelBufferToMdl(v24, v12, 24LL * v21, 24, &v40);
        v21 = (unsigned int)Mdl;
      }
      AllParameters = TdxGetAllParameters(
                        3,
                        2,
                        (unsigned int)&NPI_MS_IPV4_MODULEID,
                        10,
                        (__int64)NetLuid,
                        16,
                        (__int64)v52,
                        28,
                        0,
                        0,
                        0,
                        0);
    }
    v40 = 24LL * v21;
    if ( v21 )
    {
      v27 = a1;
      if ( AllParameters != -2147483643 )
        AllParameters = 0;
      goto LABEL_112;
    }
  }
LABEL_111:
  v27 = a1;
LABEL_112:
  if ( v12 )
  {
    MmUnlockPages(v12);
    IoFreeMdl(v12);
  }
  ExFreePoolWithTag(v9, 0x20786454u);
  *(_QWORD *)(v27 + 56) = v40;
  return (unsigned int)AllParameters;
}

```

## disassembly

```asm
0x14001606c  mov     r11, rsp
0x14001606f  mov     [r11+18h], rbx
0x140016073  mov     [r11+20h], rsi
0x140016077  push    rdi
0x140016078  push    r12
0x14001607a  push    r13
0x14001607c  push    r14
0x14001607e  push    r15
0x140016080  sub     rsp, 0AB0h
0x140016087  mov     rax, cs:__security_cookie
0x14001608e  xor     rax, rsp
0x140016091  mov     [rsp+0AD8h+var_38], rax
0x140016099  mov     r14, rdx
0x14001609c  mov     [rsp+0AD8h+var_A78], rcx
0x1400160a1  mov     [rsp+0AD8h+var_A50], rcx
0x1400160a9  xor     edi, edi
0x1400160ab  mov     [rsp+0AD8h+var_A70], rdi
0x1400160b0  mov     edx, [rdx+10h]
0x1400160b3  lea     eax, [rdx-28h]
0x1400160b6  cmp     eax, 7FFFFFD7h
0x1400160bb  ja      loc_140016FB2
0x1400160c1  mov     r13d, [r14+8]
0x1400160c5  mov     [rsp+0AD8h+var_A58], r13d
0x1400160cd  test    r13d, r13d
0x1400160d0  jz      loc_140016FB2
0x1400160d6  mov     r12, [r14+20h]
0x1400160da  mov     r15, [rcx+70h]
0x1400160de  mov     [r11-0A38h], rdi
0x1400160e5  lea     eax, [rdi+1]
0x1400160e8  mov     [r11-0A40h], rax
0x1400160ef  mov     ebx, edx
0x1400160f1  mov     dword ptr [rsp+0AD8h+Irp], eax
0x1400160f5  lea     r9, [r11-0A40h]
0x1400160fc  lea     ecx, [rdi+40h]
0x1400160ff  mov     r8d, 20786454h
0x140016105  call    cs:__imp_ExAllocatePool3
0x14001610c  nop     dword ptr [rax+rax+00h]
0x140016111  mov     rsi, rax
0x140016114  test    rax, rax
0x140016117  jnz     short loc_140016123
0x140016119  mov     eax, 0C000009Ah
0x14001611e  jmp     loc_140016FB7
0x140016123  mov     qword ptr [rsp+0AD8h+pIfIndex], rsi
0x140016128  mov     [rsp+0AD8h+Irp], rdi; Irp
0x14001612d  mov     r9b, 1; ChargeQuota
0x140016130  xor     r8d, r8d; SecondaryBuffer
0x140016133  mov     edx, r13d; Length
0x140016136  mov     rcx, r15; VirtualAddress
0x140016139  call    cs:__imp_IoAllocateMdl
0x140016140  nop     dword ptr [rax+rax+00h]
0x140016145  mov     r15, rax
0x140016148  mov     [rsp+0AD8h+Mdl], rax
0x14001614d  test    rax, rax
0x140016150  jnz     short loc_14001615C
0x140016152  mov     ebx, 0C000009Ah
0x140016157  jmp     loc_140016F69
0x14001615c  mov     r8d, 1; Operation
0x140016162  mov     rdx, [rsp+0AD8h+var_A78]
0x140016167  mov     dl, [rdx+40h]; AccessMode
0x14001616a  mov     rcx, r15; MemoryDescriptorList
0x14001616d  call    cs:__imp_MmProbeAndLockPages
0x140016174  nop     dword ptr [rax+rax+00h]
0x140016179  nop
0x14001617a  mov     rax, [rsp+0AD8h+var_A78]
0x14001617f  mov     r8, rbx; Size
0x140016182  mov     rdx, r12; Src
0x140016185  mov     rcx, rsi; void *
0x140016188  cmp     [rax+40h], dil
0x14001618c  jz      short loc_140016195
0x14001618e  call    RtlCopyFromUser
0x140016193  jmp     short loc_14001619B
0x140016195  call    RtlCopyVolatileMemory
0x14001619a  nop
0x14001619b  mov     ecx, [rsi]
0x14001619d  mov     eax, ecx
0x14001619f  test    ecx, ecx
0x1400161a1  jz      loc_140016E5C
0x1400161a7  mov     ebx, 200h
0x1400161ac  sub     eax, ebx
0x1400161ae  jz      loc_140016B4C
0x1400161b4  mov     edx, 80h
0x1400161b9  sub     eax, edx
0x1400161bb  jz      loc_140016B42
0x1400161c1  sub     eax, 81h
0x1400161c6  jz      loc_1400162A5
0x1400161cc  sub     eax, 7Fh
0x1400161cf  jz      loc_14001626A
0x1400161d5  sub     eax, edx
0x1400161d7  jz      short loc_1400161E8
0x1400161d9  cmp     eax, 1
0x1400161dc  jz      short loc_1400161E8
0x1400161de  mov     ebx, 0C0000010h
0x1400161e3  jmp     loc_140016F69
0x1400161e8  cmp     [rsi+4], edi
0x1400161eb  jnz     short loc_1400161DE
0x1400161ed  mov     eax, 100h
0x1400161f2  cmp     [rsi+8], eax
0x1400161f5  jnz     short loc_140016260
0x1400161f7  cmp     [rsi+0Ch], eax
0x1400161fa  jnz     short loc_140016260
0x1400161fc  cmp     dword ptr [rsi+10h], 1
0x140016200  jnz     short loc_140016260
0x140016202  mov     r14d, 4
0x140016208  cmp     r13d, r14d
0x14001620b  jnb     short loc_14001621C
0x14001620d  mov     [rsp+0AD8h+var_A70], r14
0x140016212  mov     ebx, 0C0000023h
0x140016217  jmp     loc_140016F69
0x14001621c  sub     ecx, 400h
0x140016222  neg     ecx
0x140016224  sbb     eax, eax
0x140016226  add     eax, 404h
0x14001622b  mov     [rsp+0AD8h+var_A48], eax
0x140016232  mov     r9, r14
0x140016235  lea     rcx, [rsp+0AD8h+var_A48]
0x14001623d  xor     r8d, r8d
0x140016240  lea     rax, [rsp+0AD8h+var_A70]
0x140016245  mov     [rsp+0AD8h+Irp], rax
0x14001624a  mov     rdx, r15
0x14001624d  call    cs:__imp_RtlCopyKernelBufferToMdl
0x140016254  nop     dword ptr [rax+rax+00h]
0x140016259  mov     ebx, edi
0x14001625b  jmp     loc_140016F69
0x140016260  mov     ebx, 0C000000Dh
0x140016265  jmp     loc_140016F69
0x14001626a  cmp     dword ptr [rsi+4], 2
0x14001626e  jnb     loc_1400161DE
0x140016274  mov     eax, 100h
0x140016279  cmp     [rsi+8], eax
0x14001627c  jnz     short loc_140016260
0x14001627e  cmp     [rsi+0Ch], eax
0x140016281  jnz     short loc_140016260
0x140016283  cmp     dword ptr [rsi+10h], 1
0x140016287  jnz     short loc_140016260
0x140016289  mov     r14d, 4
0x14001628f  cmp     r13d, r14d
0x140016292  jb      loc_14001620D
0x140016298  mov     [rsp+0AD8h+var_A48], 380h
0x1400162a3  jmp     short loc_140016232
0x1400162a5  mov     ecx, [rsi+4]
0x1400162a8  mov     dword ptr [rsp+0AD8h+Mdl], ecx
0x1400162ac  cmp     ecx, 2
0x1400162af  jnb     loc_1400161DE
0x1400162b5  mov     edx, [rsi+0Ch]
0x1400162b8  mov     eax, 100h
0x1400162bd  cmp     edx, eax
0x1400162bf  jnz     loc_140016853
0x1400162c5  cmp     dword ptr [rsi+10h], 1
0x1400162c9  jnz     loc_140016591
0x1400162cf  mov     r12d, 5Ch ; '\'
0x1400162d5  mov     r8d, r12d; Size
0x1400162d8  xor     edx, edx; Val
0x1400162da  lea     rcx, [rsp+0AD8h+var_9F8]; void *
0x1400162e2  call    memset
0x1400162e7  lea     ebx, [r12+40h]
0x1400162ec  mov     r8d, ebx; Size
0x1400162ef  xor     edx, edx; Val
0x1400162f1  lea     rcx, [rsp+0AD8h+var_718]; void *
0x1400162f9  call    memset
0x1400162fe  xor     edx, edx; Val
0x140016300  lea     r8d, [r12+74h]; Size
0x140016305  lea     rcx, [rsp+0AD8h+var_958]; void *
0x14001630d  call    memset
0x140016312  mov     [rsp+0AD8h+pIfIndex], edi
0x140016316  mov     dword ptr [rsp+0AD8h+var_A50], edi
0x14001631d  xorps   xmm0, xmm0
0x140016320  movups  xmmword ptr [rsp+0AD8h+NetLuid], xmm0
0x140016328  xorps   xmm1, xmm1
0x14001632b  movups  [rsp+0AD8h+var_A18], xmm1
0x140016333  cmp     r13d, r12d
0x140016336  jnb     short loc_140016342
0x140016338  mov     [rsp+0AD8h+var_A70], r12
0x14001633d  jmp     loc_140016212
0x140016342  lea     rax, NPI_MS_IPV6_MODULEID
0x140016349  lea     r13, NPI_MS_IPV4_MODULEID
0x140016350  cmp     dword ptr [rsp+0AD8h+Mdl], edi
0x140016354  cmovnz  r13, rax
0x140016358  mov     r14d, 4
0x14001635e  mov     dword ptr [rsp+0AD8h+var_A88], r14d
0x140016363  lea     rax, [rsp+0AD8h+pIfIndex]
0x140016368  mov     [rsp+0AD8h+var_A90], rax
0x14001636d  mov     dword ptr [rsp+0AD8h+var_A98], 0D0h
0x140016375  lea     rax, [rsp+0AD8h+var_958]
0x14001637d  mov     [rsp+0AD8h+var_AA0], rax
0x140016382  mov     dword ptr [rsp+0AD8h+var_AA8], ebx
0x140016386  lea     rax, [rsp+0AD8h+var_718]
0x14001638e  mov     [rsp+0AD8h+var_AB0], rax
0x140016393  mov     dword ptr [rsp+0AD8h+Irp], edi
0x140016397  xor     r9d, r9d
0x14001639a  lea     r8d, [r14+2]
0x14001639e  mov     rdx, r13
0x1400163a1  lea     ecx, [r14-3]
0x1400163a5  call    cs:__imp_NsiGetAllParameters
0x1400163ac  nop     dword ptr [rax+rax+00h]
0x1400163b1  mov     ebx, eax
0x1400163b3  test    eax, eax
0x1400163b5  jnz     loc_140016F69
0x1400163bb  mov     dword ptr [rsp+0AD8h+var_A50], edi
0x1400163c2  mov     dword ptr [rsp+0AD8h+var_A88], edi
0x1400163c6  mov     [rsp+0AD8h+var_A90], rdi
0x1400163cb  mov     dword ptr [rsp+0AD8h+var_A98], 10h
0x1400163d3  lea     rax, [rsp+0AD8h+var_A18]
0x1400163db  mov     [rsp+0AD8h+var_AA0], rax
0x1400163e0  mov     dword ptr [rsp+0AD8h+var_AA8], 10h
0x1400163e8  lea     rax, [rsp+0AD8h+NetLuid]
0x1400163f0  mov     [rsp+0AD8h+var_AB0], rax
0x1400163f5  mov     dword ptr [rsp+0AD8h+Irp], r14d
0x1400163fa  lea     r9, [rsp+0AD8h+var_A50]
0x140016402  lea     r8d, [r14-2]
0x140016406  mov     rdx, r13
0x140016409  lea     ecx, [rbx+1]
0x14001640c  call    cs:__imp_NsiGetAllParameters
0x140016413  nop     dword ptr [rax+rax+00h]
0x140016418  mov     ebx, eax
0x14001641a  test    eax, eax
0x14001641c  jnz     loc_140016F69
0x140016422  mov     rax, [rsp+0AD8h+var_948]
0x14001642a  mov     [rsp+0AD8h+var_9F0], eax
0x140016431  mov     eax, dword ptr [rsp+0AD8h+var_8D8]
0x140016438  mov     [rsp+0AD8h+var_9EC], eax
0x14001643f  mov     eax, dword ptr [rsp+0AD8h+var_8D0]
0x140016446  mov     [rsp+0AD8h+var_9E8], eax
0x14001644d  mov     rax, [rsp+0AD8h+var_938]
0x140016455  mov     [rsp+0AD8h+var_9E4], eax
0x14001645c  mov     eax, dword ptr [rsp+0AD8h+var_8D0+4]
0x140016463  mov     [rsp+0AD8h+var_9E0], eax
0x14001646a  mov     eax, [rsp+0AD8h+var_8B8]
0x140016471  mov     [rsp+0AD8h+var_9DC], eax
0x140016478  mov     rax, [rsp+0AD8h+var_930]
0x140016480  mov     [rsp+0AD8h+var_9D8], eax
0x140016487  mov     rax, [rsp+0AD8h+var_928]
0x14001648f  mov     [rsp+0AD8h+var_9D4], eax
0x140016496  mov     eax, [rsp+0AD8h+var_89C]
0x14001649d  mov     [rsp+0AD8h+var_9D0], eax
0x1400164a4  mov     eax, [rsp+0AD8h+var_8B0]
0x1400164ab  mov     [rsp+0AD8h+var_9CC], eax
0x1400164b2  mov     eax, [rsp+0AD8h+var_8B4]
0x1400164b9  mov     [rsp+0AD8h+var_9C8], eax
0x1400164c0  mov     eax, [rsp+0AD8h+pIfIndex]
0x1400164c4  mov     [rsp+0AD8h+var_9C4], eax
0x1400164cb  mov     eax, [rsp+0AD8h+var_8C4]
0x1400164d2  mov     [rsp+0AD8h+var_9C0], eax
0x1400164d9  mov     eax, [rsp+0AD8h+var_8C0]
0x1400164e0  mov     [rsp+0AD8h+var_9BC], eax
0x1400164e7  mov     eax, [rsp+0AD8h+var_8BC]
0x1400164ee  mov     [rsp+0AD8h+var_9B8], eax
0x1400164f5  mov     eax, [rsp+0AD8h+var_8A8]
0x1400164fc  mov     [rsp+0AD8h+var_9B4], eax
0x140016503  mov     eax, [rsp+0AD8h+var_8A4]
0x14001650a  mov     [rsp+0AD8h+var_9B0], eax
0x140016511  mov     eax, [rsp+0AD8h+var_8A0]
0x140016518  mov     [rsp+0AD8h+var_9AC], eax
0x14001651f  mov     eax, edi
0x140016521  cmp     dword ptr [rsp+0AD8h+NetLuid], 1
0x140016529  setz    al
0x14001652c  inc     eax
0x14001652e  mov     [rsp+0AD8h+var_9F8], eax
0x140016535  mov     eax, dword ptr [rsp+0AD8h+var_A18]
0x14001653c  mov     [rsp+0AD8h+var_9A8], eax
0x140016543  mov     eax, dword ptr [rsp+0AD8h+var_A18+0Ch]
0x14001654a  mov     [rsp+0AD8h+var_9A4], eax
0x140016551  mov     eax, dword ptr [rsp+0AD8h+var_A18+4]
0x140016558  mov     [rsp+0AD8h+var_9A0], eax
0x14001655f  mov     eax, [rsp+0AD8h+var_700]
0x140016566  mov     ecx, 0FFFFFFFFh
0x14001656b  cmp     dword ptr [rsp+0AD8h+NetLuid+8], ecx
0x140016572  cmovnz  eax, dword ptr [rsp+0AD8h+NetLuid+8]
0x14001657a  mov     [rsp+0AD8h+var_9F4], eax
0x140016581  mov     r9, r12
0x140016584  lea     rcx, [rsp+0AD8h+var_9F8]
0x14001658c  jmp     loc_14001623D
0x140016591  cmp     edx, eax
0x140016593  jnz     loc_140016853
0x140016599  cmp     dword ptr [rsi+10h], 102h
0x1400165a0  jnz     loc_140016853
0x1400165a6  test    ecx, ecx
0x1400165a8  jnz     loc_140016853
0x1400165ae  mov     qword ptr [rsp+0AD8h+var_A18], rdi
0x1400165b6  mov     dword ptr [rsp+0AD8h+var_A18+8], edi
0x1400165bd  xorps   xmm0, xmm0
0x1400165c0  xor     eax, eax
0x1400165c2  movups  [rsp+0AD8h+var_978], xmm0
0x1400165ca  mov     [rsp+0AD8h+var_968], rax
0x1400165d2  movups  xmmword ptr [rsp+0AD8h+NetLuid], xmm0
0x1400165da  xorps   xmm1, xmm1
0x1400165dd  movups  [rsp+0AD8h+var_998], xmm1
0x1400165e5  movups  [rsp+0AD8h+var_998+0Ch], xmm1
0x1400165ed  mov     dword ptr [rsp+0AD8h+var_A50], edi
0x1400165f4  mov     r14d, edi
0x1400165f7  mov     [rsp+0AD8h+pIfIndex], edi
0x1400165fb  mov     dword ptr [rsp+0AD8h+var_A18+0Ch], 1
0x140016606  mov     [rsp+0AD8h+var_A08], 0FFFFh
0x140016612  mov     [rsp+0AD8h+var_A80], edi
0x140016616  mov     [rsp+0AD8h+var_A88], rdi
0x14001661b  mov     dword ptr [rsp+0AD8h+var_A90], edi
0x14001661f  mov     [rsp+0AD8h+var_A98], rdi
0x140016624  mov     dword ptr [rsp+0AD8h+var_AA0], 1Ch
0x14001662c  lea     rax, [rsp+0AD8h+var_998]
0x140016634  mov     [rsp+0AD8h+var_AA8], rax
0x140016639  mov     dword ptr [rsp+0AD8h+var_AB0], 10h
  ... truncated ...
```
