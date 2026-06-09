# NvmeAdapterDeviceControlIrp

- ea: `0x1401a0208`
- end: `0x1401a0fe7`
- name: `NvmeAdapterDeviceControlIrp`
- size: `3551`
- prototype: ``
- caller_count: `1`
- callee_count: `50`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140034cd0`

## callees

- `0x140025144`
- `0x1400378a8`
- `0x14004ac54`
- `0x14004acac`
- `0x140052dd4`
- `0x14006d1c0`
- `0x14006d298`
- `0x14007ade8`
- `0x14008479c`
- `0x1400848c4`
- `0x1400f8330`
- `0x1400f8ed0`
- `0x1400f94ac`
- `0x1400f9ad8`
- `0x1400fa1fc`
- `0x1400fb718`
- `0x1400fd160`
- `0x1400fd580`
- `0x1400ff9c4`
- `0x140100780`
- `0x140138f10`
- `0x14014b400`
- `0x14018761c`
- `0x14019eb48`
- `0x14019f1dc`
- `0x14019f908`
- `0x1401a0208`
- `0x1401a1098`
- `0x1401a152c`
- `0x1401a1adc`
- `0x1401a20b4`
- `0x1401a2b28`
- `0x1401a3088`
- `0x1401a34ac`
- `0x1401a3a0c`
- `0x1401a3fc8`
- `0x1401a458c`
- `0x1401a4a3c`
- `0x1401a4f9c`
- `0x1401a535c`
- `0x1401a5a20`
- `0x1401a6048`
- `0x1401a6500`
- `0x1401a6f4c`
- `0x1401a7a6c`
- `0x1401a8a50`
- `0x1401a9078`
- `0x1401a947c`
- `0x1401a9840`
- `0x1401aa018`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x1401a026e`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401a02e7`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401a0663`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401a0d5f`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401a026e`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401a02e7`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401a0663`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401a0d5f`
- `ntoskrnl!IofCompleteRequest` at `0x1401a0590`
- `ntoskrnl!IofCompleteRequest` at `0x1401a091f`
- `ntoskrnl!IofCompleteRequest` at `0x1401a0590`
- `ntoskrnl!IofCompleteRequest` at `0x1401a091f`

## pseudocode

```c
__int64 __fastcall NvmeAdapterDeviceControlIrp(_QWORD *a1, __int64 a2)
{
  char v2; // r14
  int v5; // r15d
  __int64 v6; // rcx
  unsigned int v7; // ebx
  bool v8; // zf
  unsigned __int64 v9; // rcx
  __int64 v10; // rdx
  int *v11; // rax
  int v12; // ecx
  __int64 *v13; // rdx
  __int64 v14; // rdx
  unsigned int v15; // r12d
  unsigned __int8 v16; // r10
  char *v17; // r11
  char v18; // si
  _BYTE *v19; // r9
  __int64 v20; // r15
  char v21; // r13
  unsigned __int64 v22; // rbx
  __int64 v23; // r8
  int v24; // ecx
  char v25; // cl
  char v26; // bl
  char v27; // r11
  char v28; // r8
  _BYTE *v29; // rax
  char *v30; // r8
  unsigned int v31; // eax
  __int64 v33; // r8
  unsigned int v34; // ebx
  unsigned __int64 v35; // rcx
  unsigned __int8 *v36; // rdx
  int v37; // eax
  int *v38; // rax
  int v39; // ecx
  __int64 *v40; // rdx
  __int64 v41; // rdx
  unsigned int v42; // r13d
  unsigned __int8 v43; // r10
  char *v44; // r11
  _BYTE *v45; // r9
  __int64 v46; // r12
  unsigned __int64 v47; // r15
  __int64 v48; // r8
  int v49; // ecx
  char v50; // r12
  char v51; // cl
  char v52; // r15
  char v53; // r11
  char v54; // r8
  _BYTE *v55; // rax
  char *v56; // r8
  unsigned int v57; // eax
  unsigned int v58; // ebx
  unsigned int v59; // ebx
  unsigned int v60; // ebx
  unsigned int v61; // ebx
  unsigned int NvmeControllerDiscoveryEntriesIoctl; // eax
  unsigned int v63; // ebx
  unsigned int v64; // ebx
  unsigned int v65; // ebx
  unsigned int v66; // ebx
  unsigned int InfoIoctl; // eax
  unsigned int v68; // ebx
  unsigned int v69; // ebx
  unsigned int v70; // ebx
  unsigned int v71; // ebx
  unsigned int v72; // ebx
  unsigned int v73; // ebx
  unsigned int v74; // ebx
  unsigned int v75; // ebx
  unsigned int v76; // ebx
  unsigned int v77; // ebx
  unsigned int v78; // ebx
  unsigned int v79; // ebx
  unsigned int v80; // ebx
  unsigned int v81; // ebx
  unsigned int v82; // ebx
  unsigned int v83; // ebx
  unsigned int v84; // ebx
  unsigned int v85; // ebx
  __int64 v86; // rdx
  unsigned int v87; // r13d
  unsigned __int8 v88; // r11
  char *v89; // r10
  _BYTE *v90; // r9
  __int64 v91; // r12
  unsigned __int64 v92; // r15
  __int64 v93; // r8
  int v94; // ecx
  char v95; // r12
  char v96; // cl
  char v97; // r15
  char v98; // r10
  char v99; // r8
  _BYTE *v100; // rax
  char *v101; // r8
  unsigned int v102; // eax
  char v103; // [rsp+60h] [rbp-9h] BYREF
  char v104; // [rsp+61h] [rbp-8h]
  unsigned int v105; // [rsp+64h] [rbp-5h]
  __int128 v106; // [rsp+68h] [rbp-1h] BYREF
  __int128 v107; // [rsp+78h] [rbp+Fh] BYREF

  v2 = 1;
  v107 = 0;
  v103 = 1;
  v5 = NvmeAdapterAcquireRemoveLock();
  v6 = *(_QWORD *)(a2 + 184);
  v105 = v5;
  v7 = *(_DWORD *)(v6 + 24);
  if ( StorEtwLoggingEnabled )
  {
    IoGetActivityIdIrp(a2, &v107);
    if ( (byte_140177432 & 2) != 0 )
      McTemplateK0pddd_EtwWriteTransfer(
        *(unsigned __int8 *)(*(_QWORD *)(a2 + 184) + 1LL),
        (unsigned int)EventIOCTL,
        (unsigned int)&v107,
        a2,
        **(_BYTE **)(a2 + 184),
        *(_BYTE *)(*(_QWORD *)(a2 + 184) + 1LL),
        v7);
  }
  if ( v5 >= 0 )
  {
    if ( !a1[77] )
      goto LABEL_78;
    if ( v7 > 0x2D1CCC )
    {
      if ( v7 != 3002880 && v7 != 3003328 && v7 != 3005444 && v7 != 3005448 )
      {
LABEL_78:
        if ( (unsigned __int8)RaIsDeviceDFxPoweredDown(a1[1])
          && (unsigned __int8)NvmeAdapterAttemptQueueIrpForDfxPowerDown(a1, a2, v7) )
        {
          v34 = 259;
          goto LABEL_297;
        }
        if ( v7 > 0x2DDC08 )
        {
          if ( v7 <= 0x620034 )
          {
            if ( v7 == 6422580 )
            {
              NvmeControllerDiscoveryEntriesIoctl = NvmeAdapterFabricsGetNvmeControllerDiscoveryEntriesIoctl(a1, a2);
              goto LABEL_163;
            }
            if ( v7 > 0x620004 )
            {
              v76 = v7 - 6422540;
              if ( !v76 )
              {
                NvmeControllerDiscoveryEntriesIoctl = NvmeAdapterFabricsGetSubsystemPortsIoctl(
                                                        (__int64)a1,
                                                        (_QWORD *)a2);
                goto LABEL_163;
              }
              v77 = v76 - 12;
              if ( !v77 )
              {
                NvmeControllerDiscoveryEntriesIoctl = NvmeAdapterFabricsGetControllersIoctl((__int64)a1, (_QWORD *)a2);
                goto LABEL_163;
              }
              v78 = v77 - 20;
              if ( !v78 )
              {
                NvmeControllerDiscoveryEntriesIoctl = NvmeAdapterFabricsGetHostInformationIoctl(a1, a2);
                goto LABEL_163;
              }
              if ( v78 == 4 )
              {
                NvmeControllerDiscoveryEntriesIoctl = NvmeAdapterFabricsGetNamespacesIoctl(a1, a2);
                goto LABEL_163;
              }
            }
            else
            {
              if ( v7 == 6422532 )
              {
                NvmeControllerDiscoveryEntriesIoctl = NvmeAdapterFabricsGetHostGatewayByHandleIoctl(a1, a2);
                goto LABEL_163;
              }
              v72 = v7 - 3005452;
              if ( !v72 )
              {
                NvmeControllerDiscoveryEntriesIoctl = NvmeAdapterBootPartitionDownloadIoctl(a1, a2);
                goto LABEL_163;
              }
              v73 = v72 - 4;
              if ( !v73 )
              {
                NvmeControllerDiscoveryEntriesIoctl = NvmeAdapterBootPartitionActivateIoctl(a1, a2);
                goto LABEL_163;
              }
              v74 = v73 - 320496;
              if ( !v74 || (v75 = v74 - 56) == 0 )
              {
                NvmeControllerDiscoveryEntriesIoctl = RaForwardIrp(a1[3], a2);
                goto LABEL_163;
              }
              if ( v75 == 3096520 )
              {
                NvmeControllerDiscoveryEntriesIoctl = NvmeAdapterFabricsGetHostGatewaysIoctl(a1, a2);
                goto LABEL_163;
              }
            }
            goto LABEL_241;
          }
          if ( v7 <= 0x628024 )
          {
            if ( v7 == 6455332 )
            {
              NvmeControllerDiscoveryEntriesIoctl = NvmeAdapterFabricsAddControllerIoctl((__int64)a1, a2);
              goto LABEL_163;
            }
            v79 = v7 - 6422584;
            if ( !v79 )
            {
              NvmeControllerDiscoveryEntriesIoctl = NvmeAdapterFabricsGetAuthenticationKeysIoctl(a1, a2);
              goto LABEL_163;
            }
            v80 = v79 - 32728;
            if ( !v80 )
            {
              NvmeControllerDiscoveryEntriesIoctl = NvmeAdapterFabricsAddSubsystemPortIoctl(a1, a2);
              goto LABEL_163;
            }
            v81 = v80 - 4;
            if ( !v81 )
            {
              NvmeControllerDiscoveryEntriesIoctl = NvmeAdapterFabricsRemoveSubsystemPortIoctl((__int64)a1, a2, v33);
              goto LABEL_163;
            }
            v82 = v81 - 8;
            if ( !v82 )
            {
              NvmeControllerDiscoveryEntriesIoctl = NvmeAdapterFabricsConnectControllerIoctl((__int64)a1, a2);
              goto LABEL_163;
            }
            if ( v82 == 4 )
            {
              NvmeControllerDiscoveryEntriesIoctl = NvmeAdapterFabricsDisconnectControllerIoctl((__int64)a1, a2);
              goto LABEL_163;
            }
            goto LABEL_241;
          }
          v83 = v7 - 6455336;
          if ( v83 )
          {
            v84 = v83 - 20;
            if ( !v84 )
            {
              NvmeControllerDiscoveryEntriesIoctl = NvmeAdapterFabricsAddAuthenticationKeyIoctl(a1, a2);
              goto LABEL_163;
            }
            v85 = v84 - 4;
            if ( !v85 )
            {
              NvmeControllerDiscoveryEntriesIoctl = NvmeAdapterFabricsCreateAuthenticationKeyIoctl(a1, a2);
              goto LABEL_163;
            }
            if ( v85 == 4 )
            {
              NvmeControllerDiscoveryEntriesIoctl = NvmeAdapterFabricsDeleteAuthenticationKeyIoctl(a1, a2);
              goto LABEL_163;
            }
            goto LABEL_241;
          }
          InfoIoctl = NvmeAdapterFabricsRemoveControllerIoctl((__int64)a1, a2);
        }
        else if ( v7 == 3005448 )
        {
          InfoIoctl = NvmeAdapterFirmwareActivateIoctl(a1, a1[144], a2, 0, &v103);
        }
        else if ( v7 > 0x2D1CCC )
        {
          if ( v7 > 0x2DD04C )
          {
            switch ( v7 )
            {
              case 0x2DD050u:
                NvmeControllerDiscoveryEntriesIoctl = NvmeAdapterMiniportPassthroughRequestIoctl(a1, 0, a2);
                goto LABEL_163;
              case 0x2DD200u:
                InfoIoctl = NvmeAdapterSetTemperatureThresholdIoctl(a1, a2, &v103);
                break;
              case 0x2DD3C0u:
                InfoIoctl = NvmeAdapterStorageProtocolCommandIoctl(a1, a1[144], a2, &v103);
                break;
              case 0x2DDC04u:
                InfoIoctl = NvmeAdapterFirmwareDownloadIoctl(a1, a1[144], a2, &v103);
                break;
              default:
                goto LABEL_241;
            }
          }
          else
          {
            if ( v7 == 3002444 )
            {
              NvmeControllerDiscoveryEntriesIoctl = NvmeAdapterSetPciLinkBandwidthIoctl(a1, a2);
              goto LABEL_163;
            }
            v68 = v7 - 2968604;
            if ( !v68 )
            {
              NvmeControllerDiscoveryEntriesIoctl = StorageGetSystemFeatureSupportIoctl((PIRP)a2);
              goto LABEL_163;
            }
            v69 = v68 - 1068;
            if ( !v69 )
            {
              NvmeControllerDiscoveryEntriesIoctl = NvmeAdapterStorageNotificationGetInfoIoctl(a1, a2);
              goto LABEL_163;
            }
            v70 = v69 - 17332;
            if ( v70 )
            {
              v71 = v70 - 15424;
              if ( !v71 )
              {
                NvmeControllerDiscoveryEntriesIoctl = NvmeAdapterStorageTestErrorInjectionIoctl(a1, a2);
                goto LABEL_163;
              }
              if ( v71 == 8 )
              {
                NvmeControllerDiscoveryEntriesIoctl = NvmeAdapterStorageNotificationConfigureIoctl(a1, a2);
                goto LABEL_163;
              }
              goto LABEL_241;
            }
            InfoIoctl = NvmeAdapterStorageSetProperty(a1, a2, &v103);
          }
        }
        else
        {
          if ( v7 == 2956492 )
          {
            NvmeControllerDiscoveryEntriesIoctl = NvmeAdapterSetLedState(a1, a2);
            goto LABEL_163;
          }
          if ( v7 <= 0x2D1084 )
          {
            if ( v7 == 2953348 )
            {
              NvmeControllerDiscoveryEntriesIoctl = NvmeAdapterGetDeviceNumberEx(a1, a2);
              goto LABEL_163;
            }
            v58 = v7 - 315396;
            if ( v58 )
            {
              v59 = v58 - 16;
              if ( !v59 )
              {
LABEL_164:
                LOBYTE(v33) = 1;
LABEL_165:
                NvmeControllerDiscoveryEntriesIoctl = NvmeAdapterPassThrough(a1, a2, v33);
                goto LABEL_163;
              }
              v60 = v59 - 48;
              if ( v60 )
              {
                v61 = v60 - 4;
                if ( v61 )
                {
                  if ( v61 == 1921980 )
                  {
                    NvmeControllerDiscoveryEntriesIoctl = NvmeAdapterIgnoredNamespacesIoctl(a1, a2);
LABEL_163:
                    v34 = NvmeControllerDiscoveryEntriesIoctl;
                    goto LABEL_297;
                  }
LABEL_241:
                  v8 = StorEtwLoggingEnabled == 0;
                  v34 = -1073741637;
                  *(_DWORD *)(a2 + 48) = -1073741637;
                  *(_BYTE *)(a2 + 141) = -84;
                  if ( v8 )
                    goto LABEL_150;
                  v106 = 0;
                  IoGetActivityIdIrp(a2, &v106);
                  v36 = *(unsigned __int8 **)(a2 + 184);
                  if ( *v36 != 14 )
                  {
                    v37 = *v36 - 15;
                    if ( *v36 == 15 )
                    {
                      if ( byte_140177431 < 0 )
                      {
                        v86 = *((_QWORD *)v36 + 1);
                        if ( *(_BYTE *)(v86 + 2) == 40 )
                        {
                          if ( *(_DWORD *)(v86 + 20) )
                            goto LABEL_150;
                          v87 = *(_DWORD *)(v86 + 56);
                          if ( !v87 )
                            goto LABEL_150;
                          v88 = 0;
                          v89 = 0;
                          v103 = 0;
                          v90 = 0;
                          v104 = 0;
                          v91 = 0;
                          do
                          {
                            v35 = *(unsigned int *)(v86 + 4 * v91 + 120);
                            if ( (unsigned int)v35 >= 0x80 )
                            {
                              v92 = *(unsigned int *)(v86 + 16);
                              if ( (unsigned int)v35 < (unsigned int)v92 )
                              {
                                v93 = (unsigned int)v35;
                                v94 = *(_DWORD *)(v86 + v35) - 64;
                                if ( v94 )
                                {
                                  LODWORD(v35) = v94 - 1;
                                  if ( (_DWORD)v35 )
                                  {
                                    if ( (_DWORD)v35 == 1 )
                                    {
                                      LODWORD(v35) = v93 + 40;
                                      if ( v93 + 40 <= v92 )
                                      {
                                        if ( *(_DWORD *)(v86 + v93 + 12) )
                                          v89 = (char *)(v93 + v86 + 32);
                                        v90 = *(_BYTE **)(v86 + v93 + 24);
LABEL_258:
                                        v95 = *(_BYTE *)(v86 + v93 + 8);
                                        v88 = *(_BYTE *)(v86 + v93 + 9);
                                        goto LABEL_267;
                                      }
                                    }
                                  }
                                  else
                                  {
                                    LODWORD(v35) = v93 + 56;
                                    if ( v93 + 56 <= v92 )
                                    {
                                      v8 = *(_BYTE *)(v86 + v93 + 10) == 0;
                                      v104 = 1;
                                      if ( !v8 )
                                        v89 = (char *)(v93 + v86 + 24);
                                      v90 = *(_BYTE **)(v86 + v93 + 16);
                                      v88 = *(_BYTE *)(v86 + v93 + 9);
                                      v103 = *(_BYTE *)(v86 + v93 + 8);
                                    }
                                  }
                                }
                                else
                                {
                                  LODWORD(v35) = v93 + 40;
                                  if ( v93 + 40 <= v92 )
                                  {
                                    if ( *(_BYTE *)(v86 + v93 + 10) )
                                      v89 = (char *)(v93 + v86 + 24);
                                    v90 = *(_BYTE **)(v86 + v93 + 16);
                                    goto LABEL_258;
                                  }
                                }
                                if ( v104 )
                                  break;
                              }
                            }
                            v91 = (unsigned int)(v91 + 1);
                          }
                          while ( (unsigned int)v91 < v87 );
                          v95 = v103;
LABEL_267:
                          if ( !v89 )
                            goto LABEL_150;
                          v96 = *v89;
                        }
                        else
                        {
                          v96 = *(_BYTE *)(v86 + 72);
                          v90 = *(_BYTE **)(v86 + 32);
                          v88 = *(_BYTE *)(v86 + 11);
                          v95 = *(_BYTE *)(v86 + 4);
                          if ( *(_BYTE *)(v86 + 2) )
                            goto LABEL_150;
                        }
                        LOBYTE(v35) = v96 - 8;
                        if ( (v35 & 0x5D) == 0 )
                        {
                          v97 = *(_BYTE *)(v86 + 3);
                          if ( v97 == 1 || !v90 || !v88 )
                            goto LABEL_290;
                          LOBYTE(v86) = 0;
                          v98 = 0;
                          v99 = 0;
                          v35 = (unsigned __int64)&v90[v88];
                          v100 = v90 + 8;
                          if ( (unsigned __int8)((*v90 & 0x7F) - 114) <= 1u )
                          {
                            if ( (unsigned __int64)v100 <= v35 )
                            {
                              v98 = v90[2];
                              LOBYTE(v86) = v90[1] & 0xF;
                              v99 = v90[3];
                              goto LABEL_289;
                            }
                          }
                          else if ( (unsigned __int64)v100 <= v35 )
                          {
                            v101 = v90 + 13;
                            LOBYTE(v86) = v90[2] & 0xF;
                            v102 = v88;
                            if ( (unsigned int)(unsigned __int8)v90[7] + 8 <= v88 )
                              v102 = (unsigned __int8)v90[7] + 8;
                            v35 = (unsigned __int64)&v90[v102];
                            if ( (unsigned __int64)v101 <= v35 )
                              v98 = v90[12];
                            if ( (unsigned __int64)(v90 + 14) > v35 )
                              v99 = 0;
                            else
                              v99 = *v101;
LABEL_289:
                            if ( v2 )
                            {
LABEL_291:
                              McTemplateK0pduuuuup_EtwWriteTransfer(
                                v35,
                                v86,
                                (unsigned int)&v106,
                                a2,
                                *(_DWORD *)(a2 + 48),
                                v97,
                                v95,
                                v86,
                                v98,
                                v99,
                                a2);
                              goto LABEL_150;
                            }
LABEL_290:
                            LOBYTE(v86) = 0;
                            v98 = 0;
                            v99 = 0;
                            goto LABEL_291;
                          }
                          v2 = 0;
                          goto LABEL_289;
                        }
                      }
LABEL_150:
                      IofCompleteRequest((PIRP)a2, 0);
                      goto LABEL_297;
                    }
                    goto LABEL_88;
                  }
LABEL_147:
                  if ( (byte_140177432 & 8) == 0 )
                    goto LABEL_150;
                  v40 = EventNonReadWriteRequestComplete;
                  goto LABEL_149;
                }
                goto LABEL_164;
              }
            }
            v33 = 0;
            goto LABEL_165;
          }
          v63 = v7 - 2954232;
          if ( !v63 )
          {
            NvmeControllerDiscoveryEntriesIoctl = NvmeAdapterStorageInternalQueryPropertyIoctl(a1, a2);
            goto LABEL_163;
          }
          v64 = v63 - 8;
          if ( v64 )
          {
            v65 = v64 - 2048;
            if ( v65 )
            {
              v66 = v65 - 20;
              if ( !v66 )
              {
                NvmeControllerDiscoveryEntriesIoctl = NvmeAdapterBootPartitionGetInfoIoctl(a1, a2);
                goto LABEL_163;
              }
              if ( v66 == 128 )
              {
                NvmeControllerDiscoveryEntriesIoctl = NvmeAdapterPowerCapIoctl(a1, a2);
                goto LABEL_163;
              }
              goto LABEL_241;
            }
            InfoIoctl = NvmeAdapterFirmwareGetInfoIoctl(a1, a1[144], a2, &v103);
          }
          else
          {
            InfoIoctl = NvmeAdapterStorageQueryProperty(a1, a2, &v103);
          }
        }
        v34 = InfoIoctl;
        if ( !v103 )
          return v34;
LABEL_297:
        NvmeAdapterReleaseRemoveLock(a1);
        return v34;
      }
    }
    else if ( v7 != 2956492 && v7 != 315396 && v7 != 315412 && v7 != 315460 && v7 != 315464 && v7 != 2956288 )
    {
      goto LABEL_78;
    }
    v8 = StorEtwLoggingEnabled == 0;
    v34 = -1073741637;
    *(_DWORD *)(a2 + 48) = -1073741637;
    *(_QWORD *)(a2 + 56) = 0;
    *(_BYTE *)(a2 + 141) = -84;
    if ( v8 )
      goto LABEL_150;
    v106 = 0;
    IoGetActivityIdIrp(a2, &v106);
    v36 = *(unsigned __int8 **)(a2 + 184);
    if ( *v36 == 14 )
      goto LABEL_147;
    v37 = *v36 - 15;
    if ( *v36 != 15 )
    {
LABEL_88:
      if ( v37 != 12 )
        goto LABEL_150;
      if ( v36[1] == 7 && !*((_DWORD *)v36 + 2) )
      {
        if ( (byte_140177432 & 0x40) != 0 )
        {
          v38 = *(int **)(a2 + 56);
          if ( v38 )
            v39 = *v38;
          else
            v39 = 0;
          McTemplateK0pqd_EtwWriteTransfer(v39, (_DWORD)v36, (unsigned int)&v106, a2, v39, *(_DWORD *)(a2 + 48));
        }
        goto LABEL_150;
      }
      if ( (byte_140177432 & 0x20) == 0 )
        goto LABEL_150;
      v40 = EventPnpRequestComplete;
LABEL_149:
      McTemplateK0pd_EtwWriteTransfer(v35, v40, &v106, a2, *(_DWORD *)(a2 + 48));
      goto LABEL_150;
    }
    if ( byte_140177431 >= 0 )
      goto LABEL_150;
    v41 = *((_QWORD *)v36 + 1);
    if ( *(_BYTE *)(v41 + 2) == 40 )
    {
      if ( *(_DWORD *)(v41 + 20) )
        goto LABEL_150;
      v42 = *(_DWORD *)(v41 + 56);
      if ( !v42 )
        goto LABEL_150;
      v43 = 0;
      v44 = 0;
      v103 = 0;
      v45 = 0;
      v104 = 0;
      v46 = 0;
      do
      {
        v35 = *(unsigned int *)(v41 + 4 * v46 + 120);
        if ( (unsigned int)v35 >= 0x80 )
        {
          v47 = *(unsigned int *)(v41 + 16);
          if ( (unsigned int)v35 < (unsigned int)v47 )
          {
            v48 = (unsigned int)v35;
            v49 = *(_DWORD *)(v41 + v35) - 64;
            if ( v49 )
            {
              LODWORD(v35) = v49 - 1;
              if ( (_DWORD)v35 )
              {
                if ( (_DWORD)v35 == 1 )
                {
                  LODWORD(v35) = v48 + 40;
                  if ( v48 + 40 <= v47 )
                  {
                    if ( *(_DWORD *)(v41 + v48 + 12) )
                      v44 = (char *)(v48 + v41 + 32);
                    v45 = *(_BYTE **)(v41 + v48 + 24);
LABEL_112:
                    v50 = *(_BYTE *)(v41 + v48 + 8);
                    v43 = *(_BYTE *)(v41 + v48 + 9);
                    goto LABEL_121;
                  }
                }
              }
              else
              {
                LODWORD(v35) = v48 + 56;
                if ( v48 + 56 <= v47 )
                {
                  v8 = *(_BYTE *)(v41 + v48 + 10) == 0;
                  v104 = 1;
                  if ( !v8 )
                    v44 = (char *)(v48 + v41 + 24);
                  v45 = *(_BYTE **)(v41 + v48 + 16);
                  v43 = *(_BYTE *)(v41 + v48 + 9);
                  v103 = *(_BYTE *)(v41 + v48 + 8);
                }
              }
            }
            else
            {
              LODWORD(v35) = v48 + 40;
              if ( v48 + 40 <= v47 )
              {
                if ( *(_BYTE *)(v41 + v48 + 10) )
                  v44 = (char *)(v48 + v41 + 24);
                v45 = *(_BYTE **)(v41 + v48 + 16);
                goto LABEL_112;
              }
            }
            if ( v104 )
              break;
          }
        }
        v46 = (unsigned int)(v46 + 1);
      }
      while ( (unsigned int)v46 < v42 );
      v50 = v103;
LABEL_121:
      if ( !v44 )
        goto LABEL_150;
      v51 = *v44;
    }
    else
    {
      v51 = *(_BYTE *)(v41 + 72);
      v45 = *(_BYTE **)(v41 + 32);
      v43 = *(_BYTE *)(v41 + 11);
      v50 = *(_BYTE *)(v41 + 4);
      if ( *(_BYTE *)(v41 + 2) )
        goto LABEL_150;
    }
    LOBYTE(v35) = v51 - 8;
    if ( (v35 & 0x5D) != 0 )
      goto LABEL_150;
    v52 = *(_BYTE *)(v41 + 3);
    if ( v52 == 1 || !v45 || !v43 )
      goto LABEL_144;
    LOBYTE(v41) = 0;
    v53 = 0;
    v54 = 0;
    v35 = (unsigned __int64)&v45[v43];
    v55 = v45 + 8;
    if ( (unsigned __int8)((*v45 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v55 <= v35 )
      {
        v53 = v45[2];
        LOBYTE(v41) = v45[1] & 0xF;
        v54 = v45[3];
        goto LABEL_143;
      }
    }
    else if ( (unsigned __int64)v55 <= v35 )
    {
      v56 = v45 + 13;
      LOBYTE(v41) = v45[2] & 0xF;
      v57 = v43;
      if ( (unsigned int)(unsigned __int8)v45[7] + 8 <= v43 )
        v57 = (unsigned __int8)v45[7] + 8;
      v35 = (unsigned __int64)&v45[v57];
      if ( (unsigned __int64)v56 <= v35 )
        v53 = v45[12];
      if ( (unsigned __int64)(v45 + 14) > v35 )
        v54 = 0;
      else
        v54 = *v56;
LABEL_143:
      if ( v2 )
      {
LABEL_145:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v35,
          v41,
          (unsigned int)&v106,
          a2,
          *(_DWORD *)(a2 + 48),
          v52,
          v50,
          v41,
          v53,
          v54,
          a2);
        goto LABEL_150;
      }
LABEL_144:
      LOBYTE(v41) = 0;
      v53 = 0;
      v54 = 0;
      goto LABEL_145;
    }
    v2 = 0;
    goto LABEL_143;
  }
  v8 = StorEtwLoggingEnabled == 0;
  *(_QWORD *)(a2 + 56) = 0;
  *(_BYTE *)(a2 + 141) = -84;
  *(_DWORD *)(a2 + 48) = v5;
  if ( v8 )
    goto LABEL_69;
  v106 = 0;
  IoGetActivityIdIrp(a2, &v106);
  v10 = *(_QWORD *)(a2 + 184);
  if ( *(_BYTE *)v10 == 14 )
  {
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_69;
    v13 = EventNonReadWriteRequestComplete;
    goto LABEL_68;
  }
  if ( *(_BYTE *)v10 != 15 )
  {
    if ( *(_BYTE *)v10 != 27 )
      goto LABEL_69;
    if ( *(_BYTE *)(v10 + 1) == 7 && !*(_DWORD *)(v10 + 8) )
    {
      if ( (byte_140177432 & 0x40) != 0 )
      {
        v11 = *(int **)(a2 + 56);
        if ( v11 )
          v12 = *v11;
        else
          v12 = 0;
        McTemplateK0pqd_EtwWriteTransfer(v12, v10, (unsigned int)&v106, a2, v12, *(_DWORD *)(a2 + 48));
      }
      goto LABEL_69;
    }
    if ( (byte_140177432 & 0x20) == 0 )
      goto LABEL_69;
    v13 = EventPnpRequestComplete;
LABEL_68:
    McTemplateK0pd_EtwWriteTransfer(v9, v13, &v106, a2, *(_DWORD *)(a2 + 48));
    goto LABEL_69;
  }
  if ( byte_140177431 >= 0 )
    goto LABEL_69;
  v14 = *(_QWORD *)(v10 + 8);
  if ( *(_BYTE *)(v14 + 2) == 40 )
  {
    if ( *(_DWORD *)(v14 + 20) )
      goto LABEL_69;
    v15 = *(_DWORD *)(v14 + 56);
    if ( !v15 )
      goto LABEL_69;
    v16 = 0;
    v17 = 0;
    v18 = 0;
    v19 = 0;
    v20 = 0;
    v21 = 0;
    while ( 1 )
    {
      v9 = *(unsigned int *)(v14 + 4 * v20 + 120);
      if ( (unsigned int)v9 >= 0x80 )
      {
        v22 = *(unsigned int *)(v14 + 16);
        if ( (unsigned int)v9 < (unsigned int)v22 )
        {
          v23 = (unsigned int)v9;
          v24 = *(_DWORD *)(v14 + v9) - 64;
          if ( v24 )
          {
            LODWORD(v9) = v24 - 1;
            if ( (_DWORD)v9 )
            {
              if ( (_DWORD)v9 == 1 )
              {
                LODWORD(v9) = v23 + 40;
                if ( v23 + 40 <= v22 )
                {
                  if ( *(_DWORD *)(v14 + v23 + 12) )
                    v17 = (char *)(v23 + v14 + 32);
                  v19 = *(_BYTE **)(v14 + v23 + 24);
                  goto LABEL_43;
                }
              }
            }
            else
            {
              LODWORD(v9) = v23 + 56;
              if ( v23 + 56 <= v22 )
              {
                v21 = 1;
                if ( *(_BYTE *)(v14 + v23 + 10) )
                  v17 = (char *)(v23 + v14 + 24);
                v18 = *(_BYTE *)(v14 + v23 + 8);
                v19 = *(_BYTE **)(v14 + v23 + 16);
                v16 = *(_BYTE *)(v14 + v23 + 9);
              }
            }
          }
          else
          {
            LODWORD(v9) = v23 + 40;
            if ( v23 + 40 <= v22 )
            {
              if ( *(_BYTE *)(v14 + v23 + 10) )
                v17 = (char *)(v23 + v14 + 24);
              v19 = *(_BYTE **)(v14 + v23 + 16);
LABEL_43:
              v16 = *(_BYTE *)(v14 + v23 + 9);
              v18 = *(_BYTE *)(v14 + v23 + 8);
LABEL_44:
              if ( v17 )
              {
                v25 = *v17;
                goto LABEL_47;
              }
              goto LABEL_69;
            }
          }
          if ( v21 )
            goto LABEL_44;
        }
      }
      v20 = (unsigned int)(v20 + 1);
      if ( (unsigned int)v20 >= v15 )
        goto LABEL_44;
    }
  }
  v25 = *(_BYTE *)(v14 + 72);
  v19 = *(_BYTE **)(v14 + 32);
  v16 = *(_BYTE *)(v14 + 11);
  v18 = *(_BYTE *)(v14 + 4);
  if ( *(_BYTE *)(v14 + 2) )
    goto LABEL_69;
LABEL_47:
  LOBYTE(v9) = v25 - 8;
  if ( (v9 & 0x5D) == 0 )
  {
    v26 = *(_BYTE *)(v14 + 3);
    if ( v26 == 1 || !v19 || !v16 )
      goto LABEL_64;
    LOBYTE(v14) = 0;
    v27 = 0;
    v28 = 0;
    v9 = (unsigned __int64)&v19[v16];
    v29 = v19 + 8;
    if ( (unsigned __int8)((*v19 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v29 <= v9 )
      {
        v27 = v19[2];
        LOBYTE(v14) = v19[1] & 0xF;
        v28 = v19[3];
        goto LABEL_63;
      }
    }
    else if ( (unsigned __int64)v29 <= v9 )
    {
      v30 = v19 + 13;
      LOBYTE(v14) = v19[2] & 0xF;
      v31 = v16;
      if ( (unsigned int)(unsigned __int8)v19[7] + 8 <= v16 )
        v31 = (unsigned __int8)v19[7] + 8;
      v9 = (unsigned __int64)&v19[v31];
      if ( (unsigned __int64)v30 <= v9 )
        v27 = v19[12];
      if ( (unsigned __int64)(v19 + 14) > v9 )
        v28 = 0;
      else
        v28 = *v30;
LABEL_63:
      if ( v2 )
      {
LABEL_65:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v9,
          v14,
          (unsigned int)&v106,
          a2,
          *(_DWORD *)(a2 + 48),
          v26,
          v18,
          v14,
          v27,
          v28,
          a2);
        goto LABEL_69;
      }
LABEL_64:
      LOBYTE(v14) = 0;
      v27 = 0;
      v28 = 0;
      goto LABEL_65;
    }
    v2 = 0;
    goto LABEL_63;
  }
LABEL_69:
  IofCompleteRequest((PIRP)a2, 0);
  return v105;
}

```

## disassembly

```asm
0x1401a0208  mov     [rsp-8+arg_10], rbx
0x1401a020d  push    rbp
0x1401a020e  push    rsi
0x1401a020f  push    rdi
0x1401a0210  push    r12
0x1401a0212  push    r13
0x1401a0214  push    r14
0x1401a0216  push    r15
0x1401a0218  lea     rbp, [rsp-27h]
0x1401a021d  sub     rsp, 90h
0x1401a0224  mov     rax, cs:__security_cookie
0x1401a022b  xor     rax, rsp
0x1401a022e  mov     [rbp+57h+var_38], rax
0x1401a0232  xorps   xmm0, xmm0
0x1401a0235  mov     r14d, 1
0x1401a023b  movups  [rbp+57h+var_48], xmm0
0x1401a023f  mov     [rbp+57h+var_60], r14b
0x1401a0243  mov     rdi, rdx
0x1401a0246  mov     rsi, rcx
0x1401a0249  call    NvmeAdapterAcquireRemoveLock
0x1401a024e  cmp     cs:StorEtwLoggingEnabled, 0
0x1401a0255  mov     r15d, eax
0x1401a0258  mov     rcx, [rdi+0B8h]
0x1401a025f  mov     [rbp+57h+var_5C], eax
0x1401a0262  mov     ebx, [rcx+18h]
0x1401a0265  jz      short loc_1401A02B0
0x1401a0267  lea     rdx, [rbp+57h+var_48]
0x1401a026b  mov     rcx, rdi
0x1401a026e  call    cs:__imp_IoGetActivityIdIrp
0x1401a0275  nop     dword ptr [rax+rax+00h]
0x1401a027a  test    cs:byte_140177432, 2
0x1401a0281  jz      short loc_1401A02B0
0x1401a0283  mov     rax, [rdi+0B8h]
0x1401a028a  lea     r8, [rbp+57h+var_48]
0x1401a028e  mov     [rsp+0C0h+var_90], ebx
0x1401a0292  mov     r9, rdi
0x1401a0295  movzx   edx, byte ptr [rax]
0x1401a0298  movzx   ecx, byte ptr [rax+1]
0x1401a029c  mov     [rsp+0C0h+var_98], ecx
0x1401a02a0  mov     dword ptr [rsp+0C0h+var_A0], edx
0x1401a02a4  lea     rdx, EventIOCTL
0x1401a02ab  call    McTemplateK0pddd_EtwWriteTransfer
0x1401a02b0  test    r15d, r15d
0x1401a02b3  jns     loc_1401A05A4
0x1401a02b9  cmp     cs:StorEtwLoggingEnabled, 0
0x1401a02c0  mov     qword ptr [rdi+38h], 0
0x1401a02c8  mov     byte ptr [rdi+8Dh], 0ACh
0x1401a02cf  mov     [rdi+30h], r15d
0x1401a02d3  jz      loc_1401A058B
0x1401a02d9  xorps   xmm0, xmm0
0x1401a02dc  lea     rdx, [rbp+57h+var_58]
0x1401a02e0  mov     rcx, rdi
0x1401a02e3  movups  [rbp+57h+var_58], xmm0
0x1401a02e7  call    cs:__imp_IoGetActivityIdIrp
0x1401a02ee  nop     dword ptr [rax+rax+00h]
0x1401a02f3  mov     rdx, [rdi+0B8h]
0x1401a02fa  movzx   eax, byte ptr [rdx]
0x1401a02fd  sub     eax, 0Eh
0x1401a0300  jz      loc_1401A0568
0x1401a0306  sub     eax, r14d
0x1401a0309  jz      short loc_1401A0371
0x1401a030b  cmp     eax, 0Ch
0x1401a030e  jnz     loc_1401A058B
0x1401a0314  cmp     byte ptr [rdx+1], 7
0x1401a0318  jnz     short loc_1401A0358
0x1401a031a  cmp     dword ptr [rdx+8], 0
0x1401a031e  jnz     short loc_1401A0358
0x1401a0320  test    cs:byte_140177432, 40h
0x1401a0327  jz      loc_1401A058B
0x1401a032d  mov     rax, [rdi+38h]
0x1401a0331  test    rax, rax
0x1401a0334  jz      short loc_1401A033A
0x1401a0336  mov     ecx, [rax]
0x1401a0338  jmp     short loc_1401A033C
0x1401a033a  xor     ecx, ecx
0x1401a033c  mov     eax, [rdi+30h]
0x1401a033f  lea     r8, [rbp+57h+var_58]
0x1401a0343  mov     [rsp+0C0h+var_98], eax
0x1401a0347  mov     r9, rdi
0x1401a034a  mov     dword ptr [rsp+0C0h+var_A0], ecx
0x1401a034e  call    McTemplateK0pqd_EtwWriteTransfer
0x1401a0353  jmp     loc_1401A058B
0x1401a0358  test    cs:byte_140177432, 20h
0x1401a035f  jz      loc_1401A058B
0x1401a0365  lea     rdx, EventPnpRequestComplete
0x1401a036c  jmp     loc_1401A0578
0x1401a0371  cmp     cs:byte_140177431, 0
0x1401a0378  jge     loc_1401A058B
0x1401a037e  mov     rdx, [rdx+8]
0x1401a0382  movzx   eax, byte ptr [rdx+2]
0x1401a0386  cmp     al, 28h ; '('
0x1401a0388  jnz     loc_1401A0473
0x1401a038e  cmp     dword ptr [rdx+14h], 0
0x1401a0392  jnz     loc_1401A058B
0x1401a0398  mov     r12d, [rdx+38h]
0x1401a039c  test    r12d, r12d
0x1401a039f  jz      loc_1401A058B
0x1401a03a5  xor     r10b, r10b
0x1401a03a8  xor     r11d, r11d
0x1401a03ab  xor     sil, sil
0x1401a03ae  xor     r9d, r9d
0x1401a03b1  xor     r15d, r15d
0x1401a03b4  xor     r13b, r13b
0x1401a03b7  mov     ecx, [rdx+r15*4+78h]
0x1401a03bc  cmp     ecx, 80h
0x1401a03c2  jb      short loc_1401A0439
0x1401a03c4  mov     ebx, [rdx+10h]
0x1401a03c7  cmp     ecx, ebx
0x1401a03c9  jnb     short loc_1401A0439
0x1401a03cb  mov     r8d, ecx
0x1401a03ce  mov     ecx, [rdx+rcx]
0x1401a03d1  sub     ecx, 40h ; '@'
0x1401a03d4  jz      short loc_1401A042B
0x1401a03d6  sub     ecx, r14d
0x1401a03d9  jz      short loc_1401A03FF
0x1401a03db  cmp     ecx, r14d
0x1401a03de  jnz     short loc_1401A0434
0x1401a03e0  lea     rcx, [r8+28h]
0x1401a03e4  cmp     rcx, rbx
0x1401a03e7  ja      short loc_1401A0434
0x1401a03e9  cmp     dword ptr [rdx+r8+0Ch], 0
0x1401a03ef  jbe     short loc_1401A03F8
0x1401a03f1  lea     r11, [rdx+20h]
0x1401a03f5  add     r11, r8
0x1401a03f8  mov     r9, [rdx+r8+18h]
0x1401a03fd  jmp     short loc_1401A045B
0x1401a03ff  lea     rcx, [r8+38h]
0x1401a0403  cmp     rcx, rbx
0x1401a0406  ja      short loc_1401A0434
0x1401a0408  cmp     byte ptr [rdx+r8+0Ah], 0
0x1401a040e  mov     r13b, r14b
0x1401a0411  jbe     short loc_1401A041A
0x1401a0413  lea     r11, [rdx+18h]
0x1401a0417  add     r11, r8
0x1401a041a  mov     sil, [rdx+r8+8]
0x1401a041f  mov     r9, [rdx+r8+10h]
0x1401a0424  mov     r10b, [rdx+r8+9]
0x1401a0429  jmp     short loc_1401A0434
0x1401a042b  lea     rcx, [r8+28h]
0x1401a042f  cmp     rcx, rbx
0x1401a0432  jbe     short loc_1401A0447
0x1401a0434  test    r13b, r13b
0x1401a0437  jnz     short loc_1401A0465
0x1401a0439  add     r15d, r14d
0x1401a043c  cmp     r15d, r12d
0x1401a043f  jb      loc_1401A03B7
0x1401a0445  jmp     short loc_1401A0465
0x1401a0447  cmp     byte ptr [rdx+r8+0Ah], 0
0x1401a044d  jbe     short loc_1401A0456
0x1401a044f  lea     r11, [rdx+18h]
0x1401a0453  add     r11, r8
0x1401a0456  mov     r9, [rdx+r8+10h]
0x1401a045b  mov     r10b, [rdx+r8+9]
0x1401a0460  mov     sil, [rdx+r8+8]
0x1401a0465  test    r11, r11
0x1401a0468  jz      loc_1401A058B
0x1401a046e  mov     cl, [r11]
0x1401a0471  jmp     short loc_1401A048A
0x1401a0473  mov     cl, [rdx+48h]
0x1401a0476  mov     r9, [rdx+20h]
0x1401a047a  mov     r10b, [rdx+0Bh]
0x1401a047e  mov     sil, [rdx+4]
0x1401a0482  test    eax, eax
0x1401a0484  jnz     loc_1401A058B
0x1401a048a  sub     cl, 8
0x1401a048d  test    cl, 5Dh
0x1401a0490  jnz     loc_1401A058B
0x1401a0496  mov     bl, [rdx+3]
0x1401a0499  cmp     bl, r14b
0x1401a049c  jz      loc_1401A052F
0x1401a04a2  test    r9, r9
0x1401a04a5  jz      loc_1401A052F
0x1401a04ab  test    r10b, r10b
0x1401a04ae  jz      short loc_1401A052F
0x1401a04b0  mov     al, [r9]
0x1401a04b3  xor     dl, dl
0x1401a04b5  and     al, 7Fh
0x1401a04b7  movzx   ecx, r10b
0x1401a04bb  sub     al, 72h ; 'r'
0x1401a04bd  xor     r11b, r11b
0x1401a04c0  xor     r8b, r8b
0x1401a04c3  add     rcx, r9
0x1401a04c6  cmp     al, r14b
0x1401a04c9  lea     rax, [r9+8]
0x1401a04cd  jbe     short loc_1401A0511
0x1401a04cf  cmp     rax, rcx
0x1401a04d2  ja      short loc_1401A0527
0x1401a04d4  movzx   ecx, byte ptr [r9+7]
0x1401a04d9  lea     r8, [r9+0Dh]
0x1401a04dd  mov     dl, [r9+2]
0x1401a04e1  add     ecx, 8
0x1401a04e4  and     dl, 0Fh
0x1401a04e7  movzx   eax, r10b
0x1401a04eb  cmp     ecx, eax
0x1401a04ed  cmovbe  eax, ecx
0x1401a04f0  mov     ecx, eax
0x1401a04f2  add     rcx, r9
0x1401a04f5  cmp     r8, rcx
0x1401a04f8  ja      short loc_1401A04FE
0x1401a04fa  mov     r11b, [r9+0Ch]
0x1401a04fe  lea     rax, [r9+0Eh]
0x1401a0502  cmp     rax, rcx
0x1401a0505  ja      short loc_1401A050C
0x1401a0507  mov     r8b, [r8]
0x1401a050a  jmp     short loc_1401A052A
0x1401a050c  xor     r8b, r8b
0x1401a050f  jmp     short loc_1401A052A
0x1401a0511  cmp     rax, rcx
0x1401a0514  ja      short loc_1401A0527
0x1401a0516  mov     dl, [r9+1]
0x1401a051a  mov     r11b, [r9+2]
0x1401a051e  and     dl, 0Fh
0x1401a0521  mov     r8b, [r9+3]
0x1401a0525  jmp     short loc_1401A052A
0x1401a0527  xor     r14b, r14b
0x1401a052a  test    r14b, r14b
0x1401a052d  jnz     short loc_1401A0537
0x1401a052f  xor     dl, dl
0x1401a0531  xor     r11b, r11b
0x1401a0534  xor     r8b, r8b
0x1401a0537  mov     eax, [rdi+30h]
0x1401a053a  mov     r9, rdi
0x1401a053d  mov     [rsp+0C0h+var_70], rdi
0x1401a0542  mov     [rsp+0C0h+var_78], r8b
0x1401a0547  lea     r8, [rbp+57h+var_58]
0x1401a054b  mov     [rsp+0C0h+var_80], r11b
0x1401a0550  mov     [rsp+0C0h+var_88], dl
0x1401a0554  mov     byte ptr [rsp+0C0h+var_90], sil
0x1401a0559  mov     byte ptr [rsp+0C0h+var_98], bl
0x1401a055d  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1401a0561  call    McTemplateK0pduuuuup_EtwWriteTransfer
0x1401a0566  jmp     short loc_1401A058B
0x1401a0568  test    cs:byte_140177432, 8
0x1401a056f  jz      short loc_1401A058B
0x1401a0571  lea     rdx, EventNonReadWriteRequestComplete
0x1401a0578  mov     eax, [rdi+30h]
0x1401a057b  lea     r8, [rbp+57h+var_58]
0x1401a057f  mov     r9, rdi
0x1401a0582  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1401a0586  call    McTemplateK0pd_EtwWriteTransfer
0x1401a058b  xor     edx, edx; PriorityBoost
0x1401a058d  mov     rcx, rdi; Irp
0x1401a0590  call    cs:__imp_IofCompleteRequest
0x1401a0597  nop     dword ptr [rax+rax+00h]
0x1401a059c  mov     eax, [rbp+57h+var_5C]
0x1401a059f  jmp     loc_1401A0FBF
0x1401a05a4  cmp     qword ptr [rsi+268h], 0
0x1401a05ac  mov     r12d, 2D1CCCh
0x1401a05b2  mov     r15d, 4
0x1401a05b8  mov     r13d, 2DD200h
0x1401a05be  jz      short loc_1401A05E6
0x1401a05c0  cmp     ebx, r12d
0x1401a05c3  ja      short loc_1401A0617
0x1401a05c5  jz      short loc_1401A0631
0x1401a05c7  mov     eax, ebx
0x1401a05c9  sub     eax, 4D004h
0x1401a05ce  jz      short loc_1401A0631
0x1401a05d0  sub     eax, 10h
0x1401a05d3  jz      short loc_1401A0631
0x1401a05d5  sub     eax, 30h ; '0'
0x1401a05d8  jz      short loc_1401A0631
0x1401a05da  sub     eax, r15d
0x1401a05dd  jz      short loc_1401A0631
0x1401a05df  cmp     eax, 284BB8h
0x1401a05e4  jz      short loc_1401A0631
0x1401a05e6  mov     rcx, [rsi+8]
0x1401a05ea  call    RaIsDeviceDFxPoweredDown
0x1401a05ef  test    al, al
0x1401a05f1  jz      loc_1401A0930
0x1401a05f7  mov     r8d, ebx
0x1401a05fa  mov     rdx, rdi
0x1401a05fd  mov     rcx, rsi
0x1401a0600  call    NvmeAdapterAttemptQueueIrpForDfxPowerDown
0x1401a0605  test    al, al
0x1401a0607  jz      loc_1401A0930
0x1401a060d  mov     ebx, 103h
0x1401a0612  jmp     loc_1401A0FB5
0x1401a0617  mov     eax, ebx
0x1401a0619  sub     eax, r13d
0x1401a061c  jz      short loc_1401A0631
0x1401a061e  sub     eax, 1C0h
0x1401a0623  jz      short loc_1401A0631
0x1401a0625  sub     eax, 844h
0x1401a062a  jz      short loc_1401A0631
0x1401a062c  cmp     eax, r15d
0x1401a062f  jnz     short loc_1401A05E6
0x1401a0631  cmp     cs:StorEtwLoggingEnabled, 0
0x1401a0638  mov     ebx, 0C00000BBh
0x1401a063d  mov     [rdi+30h], ebx
0x1401a0640  mov     qword ptr [rdi+38h], 0
0x1401a0648  mov     byte ptr [rdi+8Dh], 0ACh
0x1401a064f  jz      loc_1401A091A
0x1401a0655  xorps   xmm0, xmm0
0x1401a0658  lea     rdx, [rbp+57h+var_58]
0x1401a065c  mov     rcx, rdi
0x1401a065f  movups  [rbp+57h+var_58], xmm0
0x1401a0663  call    cs:__imp_IoGetActivityIdIrp
0x1401a066a  nop     dword ptr [rax+rax+00h]
0x1401a066f  mov     rdx, [rdi+0B8h]
0x1401a0676  movzx   eax, byte ptr [rdx]
  ... truncated ...
```
