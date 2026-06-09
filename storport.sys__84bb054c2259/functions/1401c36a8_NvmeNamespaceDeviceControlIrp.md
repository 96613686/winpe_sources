# NvmeNamespaceDeviceControlIrp

- ea: `0x1401c36a8`
- end: `0x1401c47f0`
- name: `NvmeNamespaceDeviceControlIrp`
- size: `4424`
- prototype: `__int64 __fastcall(PVOID Context, PIRP Irp)`
- caller_count: `1`
- callee_count: `44`
- tags: `broker_com_uri`

## callers

- `0x140034cd0`

## callees

- `0x1400378a8`
- `0x1400421f4`
- `0x14004acac`
- `0x14004b048`
- `0x14004bd80`
- `0x14006d1c0`
- `0x14006d298`
- `0x140071370`
- `0x14007ade8`
- `0x14007ccdc`
- `0x14008479c`
- `0x1400848c4`
- `0x14011c16c`
- `0x14011ebcc`
- `0x140120050`
- `0x1401203d0`
- `0x140120750`
- `0x14012209c`
- `0x1401225b4`
- `0x140122b1c`
- `0x140122f04`
- `0x1401233d8`
- `0x140126968`
- `0x14012a564`
- `0x14014b400`
- `0x140187e98`
- `0x14018b800`
- `0x1401ac6cc`
- `0x1401acda4`
- `0x1401adc80`
- `0x1401ae050`
- `0x1401ae3d4`
- `0x1401ae770`
- `0x1401af1e4`
- `0x1401b107c`
- `0x1401b1420`
- `0x1401b1bb8`
- `0x1401b2998`
- `0x1401b2d0c`
- `0x1401b2d8c`
- `0x1401b3260`
- `0x1401b35f8`
- `0x1401b5070`
- `0x1401c36a8`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x1401c3703`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401c37a0`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401c395d`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401c3dd0`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401c42c7`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401c461a`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401c3703`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401c37a0`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401c395d`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401c3dd0`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401c42c7`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401c461a`
- `ntoskrnl!IofCallDriver` at `0x1401c41c4`
- `ntoskrnl!IofCallDriver` at `0x1401c41c4`
- `ntoskrnl!IofCompleteRequest` at `0x1401c3b90`
- `ntoskrnl!IofCompleteRequest` at `0x1401c408c`
- `ntoskrnl!IofCompleteRequest` at `0x1401c4583`
- `ntoskrnl!IofCompleteRequest` at `0x1401c3b90`
- `ntoskrnl!IofCompleteRequest` at `0x1401c408c`
- `ntoskrnl!IofCompleteRequest` at `0x1401c4583`

## pseudocode

```c
__int64 __fastcall NvmeNamespaceDeviceControlIrp(_BYTE *Context, PIRP Irp)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  char v3; // r14
  unsigned int LowPart; // edi
  int v7; // ecx
  bool v9; // zf
  unsigned __int64 v10; // rcx
  _IO_STACK_LOCATION *v11; // rdx
  int v12; // eax
  int *Information; // rax
  int v14; // ecx
  __int64 *v15; // rdx
  _IO_SECURITY_CONTEXT *SecurityContext; // rdx
  int v17; // eax
  unsigned int AccessState; // r12d
  unsigned __int8 v19; // r10
  char *v20; // r11
  char v21; // si
  _ACCESS_STATE *v22; // r9
  __int64 v23; // r15
  char v24; // r13
  unsigned __int64 DesiredAccess; // rdi
  __int64 v26; // r8
  int v27; // ecx
  char v28; // r8
  int v29; // eax
  unsigned int v30; // r12d
  __int64 v31; // r15
  char v32; // r13
  unsigned __int64 v33; // rdi
  int v34; // ecx
  char v35; // cl
  char v36; // di
  char v37; // r11
  unsigned __int8 *v38; // rax
  char *v39; // r8
  unsigned int v40; // eax
  __int64 v41; // rcx
  __int64 v42; // r8
  unsigned int v43; // edi
  unsigned int v44; // edi
  unsigned int v45; // edi
  unsigned int v46; // edi
  unsigned int v47; // edi
  unsigned int QOSIoctl; // eax
  unsigned int v49; // edi
  unsigned int v50; // edi
  unsigned int v51; // edi
  unsigned int v52; // edi
  unsigned int InfoIoctl; // eax
  __int64 v54; // rcx
  unsigned int v55; // edi
  unsigned int v56; // edi
  unsigned int v57; // edi
  unsigned __int64 v58; // rcx
  _IO_STACK_LOCATION *v59; // rdx
  int v60; // eax
  int *v61; // rax
  int v62; // ecx
  __int64 *v63; // rdx
  _IO_SECURITY_CONTEXT *v64; // rdx
  int v65; // eax
  unsigned int v66; // r13d
  unsigned __int8 v67; // r10
  char *v68; // r11
  _ACCESS_STATE *v69; // r9
  __int64 v70; // r12
  unsigned __int64 v71; // r15
  __int64 v72; // r8
  int v73; // ecx
  char v74; // r12
  char SecurityQos; // cl
  char v76; // r15
  char Flags; // r11
  char LowPart_high; // r8
  unsigned __int8 *p_SecurityEvaluated; // rax
  char *v80; // r8
  unsigned int v81; // eax
  unsigned int v82; // edi
  unsigned int v83; // edi
  unsigned int v84; // edi
  unsigned int v85; // edi
  unsigned int v86; // edi
  unsigned int v87; // edi
  unsigned int v88; // edi
  unsigned int v89; // edi
  unsigned int v90; // edi
  unsigned int v91; // edi
  unsigned int v92; // edi
  unsigned __int64 v93; // rcx
  _IO_STACK_LOCATION *v94; // rdx
  int *v95; // rax
  int v96; // ecx
  __int64 *v97; // rdx
  _IO_SECURITY_CONTEXT *v98; // rdx
  unsigned int v99; // r13d
  unsigned __int8 v100; // r10
  char *v101; // r11
  _ACCESS_STATE *v102; // r9
  __int64 v103; // r12
  unsigned __int64 v104; // r15
  __int64 v105; // r8
  int v106; // ecx
  char v107; // r12
  char v108; // cl
  char v109; // r15
  char v110; // r11
  char v111; // r8
  unsigned __int8 *v112; // rax
  char *v113; // r8
  unsigned int v114; // eax
  unsigned int v115; // edi
  unsigned int v116; // edi
  unsigned int v117; // edi
  unsigned int v118; // r13d
  __int64 v119; // r12
  unsigned __int64 v120; // r15
  __int64 v121; // r8
  int v122; // ecx
  char v123; // [rsp+60h] [rbp-19h] BYREF
  char v124; // [rsp+61h] [rbp-18h]
  char v125; // [rsp+62h] [rbp-17h]
  unsigned int v126; // [rsp+68h] [rbp-11h]
  __int128 v127; // [rsp+70h] [rbp-9h] BYREF
  __int128 v128; // [rsp+80h] [rbp+7h] BYREF

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v3 = 1;
  v128 = 0;
  v123 = 1;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( StorEtwLoggingEnabled )
  {
    IoGetActivityIdIrp(Irp, &v128);
    if ( (byte_140177432 & 2) != 0 )
      McTemplateK0pddd_EtwWriteTransfer(
        v7,
        (unsigned int)EventIOCTL,
        (unsigned int)&v128,
        (_DWORD)Irp,
        Irp->Tail.Overlay.CurrentStackLocation->MajorFunction,
        Irp->Tail.Overlay.CurrentStackLocation->MinorFunction,
        LowPart);
  }
  if ( LowPart == 2955532 )
    return NvmeNamespaceQueryFinalRemovePendingIoctl(Context, Irp);
  if ( (Context[112] & 2) == 0 )
  {
    v9 = StorEtwLoggingEnabled == 0;
    v126 = -1073741808;
    Irp->IoStatus.Status = -1073741808;
    Irp->IoStatus.Information = 0;
    *((_BYTE *)&Irp->Tail.CompletionKey + 21) = -84;
    if ( v9 )
      goto LABEL_95;
    v127 = 0;
    IoGetActivityIdIrp(Irp, &v127);
    v11 = Irp->Tail.Overlay.CurrentStackLocation;
    if ( v11->MajorFunction != 14 )
    {
      v12 = v11->MajorFunction - 15;
      if ( v11->MajorFunction != 15 )
      {
LABEL_10:
        if ( v12 != 12 )
          goto LABEL_95;
        if ( v11->MinorFunction == 7 && !v11->Parameters.Read.Length )
        {
          if ( (byte_140177432 & 0x40) != 0 )
          {
            Information = (int *)Irp->IoStatus.Information;
            if ( Information )
              v14 = *Information;
            else
              v14 = 0;
            McTemplateK0pqd_EtwWriteTransfer(
              v14,
              (_DWORD)v11,
              (unsigned int)&v127,
              (_DWORD)Irp,
              v14,
              Irp->IoStatus.Status);
          }
          goto LABEL_95;
        }
        if ( (byte_140177432 & 0x20) == 0 )
          goto LABEL_95;
        v15 = EventPnpRequestComplete;
LABEL_94:
        McTemplateK0pd_EtwWriteTransfer(v10, v15, &v127, Irp, Irp->IoStatus.Status);
        goto LABEL_95;
      }
      if ( byte_140177431 >= 0 )
        goto LABEL_95;
      SecurityContext = v11->Parameters.Create.SecurityContext;
      v17 = BYTE2(SecurityContext->SecurityQos);
      if ( (_BYTE)v17 == 40 )
      {
        if ( !SecurityContext->FullCreateOptions )
        {
          AccessState = (unsigned int)SecurityContext[2].AccessState;
          if ( AccessState )
          {
            v19 = 0;
            v20 = 0;
            v21 = 0;
            v22 = 0;
            v23 = 0;
            v24 = 0;
            while ( 1 )
            {
              v10 = *((unsigned int *)&SecurityContext[5].SecurityQos + v23);
              if ( (unsigned int)v10 >= 0x80 )
              {
                DesiredAccess = SecurityContext->DesiredAccess;
                if ( (unsigned int)v10 < (unsigned int)DesiredAccess )
                {
                  v26 = (unsigned int)v10;
                  v27 = *(_DWORD *)((char *)&SecurityContext->SecurityQos + v10) - 64;
                  if ( v27 )
                  {
                    LODWORD(v10) = v27 - 1;
                    if ( (_DWORD)v10 )
                    {
                      if ( (_DWORD)v10 == 1 )
                      {
                        LODWORD(v10) = v26 + 40;
                        if ( v26 + 40 <= DesiredAccess )
                          goto LABEL_31;
                      }
                    }
                    else
                    {
                      LODWORD(v10) = v26 + 56;
                      if ( v26 + 56 <= DesiredAccess )
                      {
                        v24 = 1;
                        if ( *((_BYTE *)&SecurityContext->AccessState + v26 + 2) )
                          v20 = (char *)&SecurityContext[1] + v26;
                        v21 = *((_BYTE *)&SecurityContext->AccessState + v26);
                        v22 = *(_ACCESS_STATE **)((char *)&SecurityContext->DesiredAccess + v26);
                        v19 = *((_BYTE *)&SecurityContext->AccessState + v26 + 1);
                      }
                    }
                  }
                  else
                  {
                    LODWORD(v10) = v26 + 40;
                    if ( v26 + 40 <= DesiredAccess )
                      goto LABEL_67;
                  }
                  if ( v24 )
                    goto LABEL_71;
                }
              }
              v23 = (unsigned int)(v23 + 1);
              if ( (unsigned int)v23 >= AccessState )
                goto LABEL_71;
            }
          }
        }
        goto LABEL_95;
      }
      goto LABEL_73;
    }
LABEL_92:
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_95;
    v15 = EventNonReadWriteRequestComplete;
    goto LABEL_94;
  }
  v29 = NvmeNamespaceAcquireRemoveLock(Context, Irp);
  v126 = v29;
  if ( v29 >= 0 )
  {
    if ( (unsigned __int8)RaIsDeviceDFxPoweredDown(*((_QWORD *)Context + 1))
      && (unsigned __int8)NvmeNamespaceAttemptQueueIrpForDfxPowerDown(Context, Irp, LowPart) )
    {
      v43 = 259;
LABEL_351:
      NvmeNamespaceReleaseRemoveLock(Context);
LABEL_352:
      if ( StorEtwLoggingEnabled && (byte_140177432 & 8) != 0 )
        McTemplateK0pd_EtwWriteTransfer(v54, EventNonReadWriteRequestComplete, &v128, Irp, v43);
      return v43;
    }
    if ( LowPart <= 0x2D2810 )
    {
      if ( LowPart == 2959376 )
      {
        QOSIoctl = NvmeNamespaceGetQOSIoctl(Context, Irp);
        goto LABEL_111;
      }
      if ( LowPart <= 0x2D08C0 )
      {
        if ( LowPart == 2951360 )
        {
          QOSIoctl = NvmeNamespaceManageBypassIO(Context, Irp);
          goto LABEL_111;
        }
        if ( LowPart <= 0x70014 )
        {
          if ( LowPart == 458772 )
          {
            QOSIoctl = NvmeNamespaceDiskVerifyIoctl(Context, Irp);
            goto LABEL_111;
          }
          v44 = LowPart - 266264;
          if ( !v44 )
          {
            QOSIoctl = NvmeNamespaceScsiGetAddressIoctl(Context, Irp);
            goto LABEL_111;
          }
          v45 = v44 - 49132;
          if ( !v45 || (v46 = v45 - 16) == 0 || (v47 = v46 - 48) == 0 || v47 == 4 )
          {
            QOSIoctl = NvmeNamespaceScsiPassThroughIoctl(Context, Irp);
LABEL_111:
            v43 = QOSIoctl;
            goto LABEL_351;
          }
          goto LABEL_316;
        }
        switch ( LowPart )
        {
          case 0x70024u:
            QOSIoctl = NvmeNamespaceDiskIsWritableIoctl(Context, Irp);
            goto LABEL_111;
          case 0x740D4u:
            QOSIoctl = NvmeNamespaceDiskGetCacheInformationIoctl(Context, Irp);
            goto LABEL_111;
          case 0x7C0D8u:
            QOSIoctl = NvmeNamespaceDiskSetCacheInformationIoctl(Context, Irp);
            goto LABEL_111;
        }
        if ( LowPart != 2951168 )
          goto LABEL_316;
LABEL_118:
        QOSIoctl = NvmeNamespaceStorageCheckVerifyIoctl(v41, Irp);
        goto LABEL_111;
      }
      if ( LowPart > 0x2D1C80 )
      {
        v55 = LowPart - 2956436;
        if ( !v55 )
        {
          QOSIoctl = NvmeNamespacePowerCapIoctl(Context, Irp);
          goto LABEL_111;
        }
        v56 = v55 - 48;
        if ( !v56 )
        {
          QOSIoctl = NvmeNamespaceGetDeviceInternalLogIoctl(Context, Irp);
          goto LABEL_111;
        }
        v57 = v56 - 8;
        if ( !v57 )
        {
          if ( (*(_BYTE *)(*((_QWORD *)Context + 2) + 136LL) & 2) == 0 )
          {
            QOSIoctl = NvmeNamespaceSetLedState(Context, Irp);
            goto LABEL_111;
          }
          v9 = StorEtwLoggingEnabled == 0;
          v43 = -1073741637;
          Irp->IoStatus.Status = -1073741637;
          Irp->IoStatus.Information = 0;
          *((_BYTE *)&Irp->Tail.CompletionKey + 21) = -84;
          if ( v9 )
            goto LABEL_206;
          v127 = 0;
          IoGetActivityIdIrp(Irp, &v127);
          v59 = Irp->Tail.Overlay.CurrentStackLocation;
          if ( v59->MajorFunction != 14 )
          {
            v60 = v59->MajorFunction - 15;
            if ( v59->MajorFunction == 15 )
            {
              if ( byte_140177431 >= 0 )
                goto LABEL_206;
              v64 = v59->Parameters.Create.SecurityContext;
              v65 = BYTE2(v64->SecurityQos);
              if ( (_BYTE)v65 == 40 )
              {
                if ( v64->FullCreateOptions )
                  goto LABEL_206;
                v66 = (unsigned int)v64[2].AccessState;
                if ( !v66 )
                  goto LABEL_206;
                v67 = 0;
                v68 = 0;
                v123 = 0;
                v69 = 0;
                v124 = 0;
                v70 = 0;
                do
                {
                  v58 = *((unsigned int *)&v64[5].SecurityQos + v70);
                  if ( (unsigned int)v58 >= 0x80 )
                  {
                    v71 = v64->DesiredAccess;
                    if ( (unsigned int)v58 < (unsigned int)v71 )
                    {
                      v72 = (unsigned int)v58;
                      v73 = *(_DWORD *)((char *)&v64->SecurityQos + v58) - 64;
                      if ( v73 )
                      {
                        LODWORD(v58) = v73 - 1;
                        if ( (_DWORD)v58 )
                        {
                          if ( (_DWORD)v58 == 1 )
                          {
                            LODWORD(v58) = v72 + 40;
                            if ( v72 + 40 <= v71 )
                            {
                              if ( *(_DWORD *)((char *)&v64->AccessState + v72 + 4) )
                                v68 = (char *)&v64[1].AccessState + v72;
                              v69 = *(_ACCESS_STATE **)((char *)&v64[1].SecurityQos + v72);
LABEL_169:
                              v74 = *((_BYTE *)&v64->AccessState + v72);
                              v67 = *((_BYTE *)&v64->AccessState + v72 + 1);
                              goto LABEL_178;
                            }
                          }
                        }
                        else
                        {
                          LODWORD(v58) = v72 + 56;
                          if ( v72 + 56 <= v71 )
                          {
                            v9 = *((_BYTE *)&v64->AccessState + v72 + 2) == 0;
                            v124 = 1;
                            if ( !v9 )
                              v68 = (char *)&v64[1] + v72;
                            v69 = *(_ACCESS_STATE **)((char *)&v64->DesiredAccess + v72);
                            v67 = *((_BYTE *)&v64->AccessState + v72 + 1);
                            v123 = *((_BYTE *)&v64->AccessState + v72);
                          }
                        }
                      }
                      else
                      {
                        LODWORD(v58) = v72 + 40;
                        if ( v72 + 40 <= v71 )
                        {
                          if ( *((_BYTE *)&v64->AccessState + v72 + 2) )
                            v68 = (char *)&v64[1] + v72;
                          v69 = *(_ACCESS_STATE **)((char *)&v64->DesiredAccess + v72);
                          goto LABEL_169;
                        }
                      }
                      if ( v124 )
                        break;
                    }
                  }
                  v70 = (unsigned int)(v70 + 1);
                }
                while ( (unsigned int)v70 < v66 );
                v74 = v123;
LABEL_178:
                if ( !v68 )
                  goto LABEL_206;
                SecurityQos = *v68;
                goto LABEL_184;
              }
LABEL_183:
              v74 = BYTE4(v64->SecurityQos);
              v67 = BYTE3(v64->AccessState);
              v69 = v64[1].AccessState;
              SecurityQos = (char)v64[3].SecurityQos;
              if ( v65 )
                goto LABEL_206;
LABEL_184:
              LOBYTE(v58) = SecurityQos - 8;
              if ( (v58 & 0x5D) == 0 )
              {
                v76 = BYTE3(v64->SecurityQos);
                if ( v76 == 1 || !v69 || !v67 )
                  goto LABEL_201;
                LOBYTE(v64) = 0;
                Flags = 0;
                LowPart_high = 0;
                v58 = (unsigned __int64)v69 + v67;
                p_SecurityEvaluated = &v69->SecurityEvaluated;
                if ( (unsigned __int8)((v69->OperationID.LowPart & 0x7F) - 114) <= 1u )
                {
                  if ( (unsigned __int64)p_SecurityEvaluated <= v58 )
                  {
                    Flags = BYTE2(v69->OperationID.LowPart);
                    LOBYTE(v64) = BYTE1(v69->OperationID.LowPart) & 0xF;
                    LowPart_high = HIBYTE(v69->OperationID.LowPart);
                    goto LABEL_200;
                  }
                }
                else if ( (unsigned __int64)p_SecurityEvaluated <= v58 )
                {
                  v80 = (char *)&v69->Flags + 1;
                  LOBYTE(v64) = BYTE2(v69->OperationID.LowPart) & 0xF;
                  v81 = v67;
                  if ( (unsigned int)HIBYTE(v69->OperationID.HighPart) + 8 <= v67 )
                    v81 = HIBYTE(v69->OperationID.HighPart) + 8;
                  v58 = (unsigned __int64)v69 + v81;
                  if ( (unsigned __int64)v80 <= v58 )
                    Flags = v69->Flags;
                  if ( (unsigned __int64)&v69->Flags + 2 > v58 )
                    LowPart_high = 0;
                  else
                    LowPart_high = *v80;
LABEL_200:
                  if ( v3 )
                  {
LABEL_202:
                    McTemplateK0pduuuuup_EtwWriteTransfer(
                      v58,
                      (_DWORD)v64,
                      (unsigned int)&v127,
                      (_DWORD)Irp,
                      Irp->IoStatus.Status,
                      v76,
                      v74,
                      (char)v64,
                      Flags,
                      LowPart_high,
                      (char)Irp);
                    goto LABEL_206;
                  }
LABEL_201:
                  LOBYTE(v64) = 0;
                  Flags = 0;
                  LowPart_high = 0;
                  goto LABEL_202;
                }
                v3 = 0;
                goto LABEL_200;
              }
LABEL_206:
              IofCompleteRequest(Irp, 0);
              goto LABEL_351;
            }
            goto LABEL_145;
          }
LABEL_203:
          if ( (byte_140177432 & 8) == 0 )
            goto LABEL_206;
          v63 = EventNonReadWriteRequestComplete;
          goto LABEL_205;
        }
        if ( v57 == 2880 )
        {
          QOSIoctl = NvmeNamespaceTelemetryIdIoctl((__int64)Context, (__int64)Irp);
          goto LABEL_111;
        }
LABEL_316:
        v9 = StorEtwLoggingEnabled == 0;
        v43 = -1073741637;
        Irp->IoStatus.Status = -1073741637;
        *((_BYTE *)&Irp->Tail.CompletionKey + 21) = -84;
        if ( v9 )
          goto LABEL_206;
        v127 = 0;
        IoGetActivityIdIrp(Irp, &v127);
        v59 = Irp->Tail.Overlay.CurrentStackLocation;
        if ( v59->MajorFunction != 14 )
        {
          v60 = v59->MajorFunction - 15;
          if ( v59->MajorFunction == 15 )
          {
            if ( byte_140177431 >= 0 )
              goto LABEL_206;
            v64 = v59->Parameters.Create.SecurityContext;
            v65 = BYTE2(v64->SecurityQos);
            if ( (_BYTE)v65 == 40 )
            {
              if ( v64->FullCreateOptions )
                goto LABEL_206;
              v118 = (unsigned int)v64[2].AccessState;
              if ( !v118 )
                goto LABEL_206;
              v67 = 0;
              v68 = 0;
              v124 = 0;
              v69 = 0;
              v125 = 0;
              v119 = 0;
              do
              {
                v58 = *((unsigned int *)&v64[5].SecurityQos + v119);
                if ( (unsigned int)v58 >= 0x80 )
                {
                  v120 = v64->DesiredAccess;
                  if ( (unsigned int)v58 < (unsigned int)v120 )
                  {
                    v121 = (unsigned int)v58;
                    v122 = *(_DWORD *)((char *)&v64->SecurityQos + v58) - 64;
                    if ( v122 )
                    {
                      LODWORD(v58) = v122 - 1;
                      if ( (_DWORD)v58 )
                      {
                        if ( (_DWORD)v58 == 1 )
                        {
                          LODWORD(v58) = v121 + 40;
                          if ( v121 + 40 <= v120 )
                          {
                            if ( *(_DWORD *)((char *)&v64->AccessState + v121 + 4) )
                              v68 = (char *)&v64[1].AccessState + v121;
                            v69 = *(_ACCESS_STATE **)((char *)&v64[1].SecurityQos + v121);
LABEL_333:
                            v74 = *((_BYTE *)&v64->AccessState + v121);
                            v67 = *((_BYTE *)&v64->AccessState + v121 + 1);
                            goto LABEL_178;
                          }
                        }
                      }
                      else
                      {
                        LODWORD(v58) = v121 + 56;
                        if ( v121 + 56 <= v120 )
                        {
                          v9 = *((_BYTE *)&v64->AccessState + v121 + 2) == 0;
                          v125 = 1;
                          if ( !v9 )
                            v68 = (char *)&v64[1] + v121;
                          v69 = *(_ACCESS_STATE **)((char *)&v64->DesiredAccess + v121);
                          v67 = *((_BYTE *)&v64->AccessState + v121 + 1);
                          v124 = *((_BYTE *)&v64->AccessState + v121);
                        }
                      }
                    }
                    else
                    {
                      LODWORD(v58) = v121 + 40;
                      if ( v121 + 40 <= v120 )
                      {
                        if ( *((_BYTE *)&v64->AccessState + v121 + 2) )
                          v68 = (char *)&v64[1] + v121;
                        v69 = *(_ACCESS_STATE **)((char *)&v64->DesiredAccess + v121);
                        goto LABEL_333;
                      }
                    }
                    if ( v125 )
                      break;
                  }
                }
                v119 = (unsigned int)(v119 + 1);
              }
              while ( (unsigned int)v119 < v118 );
              v74 = v124;
              goto LABEL_178;
            }
            goto LABEL_183;
          }
LABEL_145:
          if ( v60 != 12 )
            goto LABEL_206;
          if ( v59->MinorFunction == 7 && !v59->Parameters.Read.Length )
          {
            if ( (byte_140177432 & 0x40) != 0 )
            {
              v61 = (int *)Irp->IoStatus.Information;
              if ( v61 )
                v62 = *v61;
              else
                v62 = 0;
              McTemplateK0pqd_EtwWriteTransfer(
                v62,
                (_DWORD)v59,
                (unsigned int)&v127,
                (_DWORD)Irp,
                v62,
                Irp->IoStatus.Status);
            }
            goto LABEL_206;
          }
          if ( (byte_140177432 & 0x20) == 0 )
            goto LABEL_206;
          v63 = EventPnpRequestComplete;
LABEL_205:
          McTemplateK0pd_EtwWriteTransfer(v58, v63, &v127, Irp, Irp->IoStatus.Status);
          goto LABEL_206;
        }
        goto LABEL_203;
      }
      if ( LowPart == 2956416 )
      {
        QOSIoctl = NvmeNamespaceEnableIdlePower(Context, Irp);
        goto LABEL_111;
      }
      v49 = LowPart - 2954232;
      if ( v49 )
      {
        v50 = v49 - 8;
        if ( v50 )
        {
          v51 = v50 - 587;
          if ( !v51 )
          {
            QOSIoctl = NvmeNamespaceStorageGetDumpInfoIoctl(Context, Irp);
            goto LABEL_111;
          }
          v52 = v51 - 1461;
          if ( v52 )
          {
            if ( v52 != 20 )
              goto LABEL_316;
            goto LABEL_130;
          }
          InfoIoctl = NvmeNamespaceFirmwareGetInfoIoctl(Context, Irp, &v123);
        }
        else
        {
          InfoIoctl = NvmeNamespaceStorageQueryPropertyIoctl(Context, Irp, &v123);
        }
      }
      else
      {
        InfoIoctl = NvmeNamespaceInternalQueryPropertyIoctl(Context, Irp, &v123);
      }
      goto LABEL_349;
    }
    if ( LowPart <= 0x2DD044 )
    {
      if ( LowPart == 3002436 )
        goto LABEL_221;
      if ( LowPart <= 0x2D93FC )
      {
        if ( LowPart != 2987004 )
        {
          v82 = LowPart - 2967552;
          if ( !v82 )
            goto LABEL_118;
          v83 = v82 - 1052;
          if ( !v83 )
          {
            QOSIoctl = StorageGetSystemFeatureSupportIoctl(Irp);
            goto LABEL_111;
          }
          v84 = v83 - 1020;
          if ( !v84 )
          {
            QOSIoctl = NvmeNamespacePersistentReserveInIoctl(Context, Irp);
            goto LABEL_111;
          }
          v85 = v84 - 48;
          if ( v85 )
          {
            if ( v85 == 1532 )
            {
              QOSIoctl = NvmeNamespaceStorageDumpNotification(Context, Irp);
              goto LABEL_111;
            }
            goto LABEL_316;
          }
LABEL_221:
          QOSIoctl = NvmeNamespaceStorageNotificationGetInfoIoctl(Context, Irp);
          goto LABEL_111;
        }
        InfoIoctl = NvmeNamespaceStorageSetPropertyIoctl(Context, Irp, &v123);
LABEL_349:
        v43 = InfoIoctl;
LABEL_350:
        if ( !v123 )
          goto LABEL_352;
        goto LABEL_351;
      }
      v86 = LowPart - 2987012;
      if ( !v86 )
      {
        QOSIoctl = NvmeNamespaceDataSetManagementIoctl(Context, Irp);
        goto LABEL_111;
      }
      v87 = v86 - 572;
      if ( !v87 )
      {
        QOSIoctl = NvmeNamespaceReinitializeMediaIoctl(Context, Irp);
        goto LABEL_111;
      }
      v88 = v87 - 14812;
      if ( !v88 )
      {
        QOSIoctl = NvmeNamespacePersistentReserveOutIoctl(Context, Irp);
        goto LABEL_111;
      }
      if ( v88 != 32 )
        goto LABEL_316;
LABEL_229:
      Irp->IoStatus.Information = 0;
      goto LABEL_230;
    }
    if ( LowPart > 0x2DDC08 )
    {
      v115 = LowPart - 3005452;
      if ( v115 )
      {
        v116 = v115 - 4;
        if ( v116 )
        {
          v117 = v116 - 140;
          if ( !v117 )
          {
            QOSIoctl = NvmeNamespaceAttributeManagementIoctl(Context, Irp);
            goto LABEL_111;
          }
          if ( v117 == 2936 )
          {
            QOSIoctl = NvmeNamespaceSetQOSIoctl(Context, Irp);
            goto LABEL_111;
          }
          goto LABEL_316;
        }
LABEL_130:
        QOSIoctl = NvmeNamespaceBootPartitionActivateIoctl(Context, Irp);
        goto LABEL_111;
      }
      InfoIoctl = NvmeNamespaceBootPartitionActivateIoctl(Context, Irp);
      goto LABEL_349;
    }
    if ( LowPart == 3005448 )
    {
      InfoIoctl = NvmeNamespaceFirmwareActivateIoctl(Context, Irp, v42, &v123);
      goto LABEL_349;
    }
    v89 = LowPart - 3002444;
    if ( !v89 )
      goto LABEL_229;
    v90 = v89 - 4;
    if ( !v90 )
    {
      QOSIoctl = NvmeAdapterMiniportPassthroughRequestIoctl(*(_QWORD *)(*((_QWORD *)Context + 2) + 128LL), Context, Irp);
      goto LABEL_111;
    }
    v91 = v90 - 432;
    if ( v91 )
    {
      v92 = v91 - 448;
      if ( v92 )
      {
        if ( v92 != 2116 )
          goto LABEL_316;
        InfoIoctl = NvmeNamespaceFirmwareDownloadIoctl(Context, Irp, &v123);
      }
      else
      {
        InfoIoctl = NvmeNamespaceStorageProtocolCommandIoctl(Context, Irp, &v123);
      }
      goto LABEL_349;
    }
    v9 = (*(_DWORD *)(*((_QWORD *)Context + 2) + 136LL) & 2) == 0;
    Irp->IoStatus.Information = 0;
    if ( v9 )
    {
LABEL_230:
      ++Irp->CurrentLocation;
      ++Irp->Tail.Overlay.CurrentStackLocation;
      QOSIoctl = IofCallDriver(*(PDEVICE_OBJECT *)(*(_QWORD *)(*((_QWORD *)Context + 2) + 128LL) + 8LL), Irp);
      goto LABEL_111;
    }
    v9 = StorEtwLoggingEnabled == 0;
    v43 = -1073741637;
    Irp->IoStatus.Status = -1073741637;
    *((_BYTE *)&Irp->Tail.CompletionKey + 21) = -84;
    if ( v9 )
      goto LABEL_309;
    v127 = 0;
    IoGetActivityIdIrp(Irp, &v127);
    v94 = Irp->Tail.Overlay.CurrentStackLocation;
    if ( v94->MajorFunction == 14 )
    {
      if ( (byte_140177432 & 8) != 0 )
      {
        v97 = EventNonReadWriteRequestComplete;
        goto LABEL_308;
      }
LABEL_309:
      IofCompleteRequest(Irp, 0);
      goto LABEL_350;
    }
    if ( v94->MajorFunction != 15 )
    {
      if ( v94->MajorFunction == 27 )
      {
        if ( v94->MinorFunction == 7 && !v94->Parameters.Read.Length )
        {
          if ( (byte_140177432 & 0x40) != 0 )
          {
            v95 = (int *)Irp->IoStatus.Information;
            if ( v95 )
              v96 = *v95;
            else
              v96 = 0;
            McTemplateK0pqd_EtwWriteTransfer(
              v96,
              (_DWORD)v94,
              (unsigned int)&v127,
              (_DWORD)Irp,
              v96,
              Irp->IoStatus.Status);
          }
          goto LABEL_309;
        }
        if ( (byte_140177432 & 0x20) != 0 )
        {
          v97 = EventPnpRequestComplete;
LABEL_308:
          McTemplateK0pd_EtwWriteTransfer(v93, v97, &v127, Irp, Irp->IoStatus.Status);
          goto LABEL_309;
        }
      }
      goto LABEL_309;
    }
    if ( byte_140177431 >= 0 )
      goto LABEL_309;
    v98 = v94->Parameters.Create.SecurityContext;
    if ( BYTE2(v98->SecurityQos) == 40 )
    {
      if ( v98->FullCreateOptions )
        goto LABEL_309;
      v99 = (unsigned int)v98[2].AccessState;
      if ( !v99 )
        goto LABEL_309;
      v100 = 0;
      v101 = 0;
      v124 = 0;
      v102 = 0;
      v125 = 0;
      v103 = 0;
      do
      {
        v93 = *((unsigned int *)&v98[5].SecurityQos + v103);
        if ( (unsigned int)v93 >= 0x80 )
        {
          v104 = v98->DesiredAccess;
          if ( (unsigned int)v93 < (unsigned int)v104 )
          {
            v105 = (unsigned int)v93;
            v106 = *(_DWORD *)((char *)&v98->SecurityQos + v93) - 64;
            if ( v106 )
            {
              LODWORD(v93) = v106 - 1;
              if ( (_DWORD)v93 )
              {
                if ( (_DWORD)v93 == 1 )
                {
                  LODWORD(v93) = v105 + 40;
                  if ( v105 + 40 <= v104 )
                  {
                    if ( *(_DWORD *)((char *)&v98->AccessState + v105 + 4) )
                      v101 = (char *)&v98[1].AccessState + v105;
                    v102 = *(_ACCESS_STATE **)((char *)&v98[1].SecurityQos + v105);
LABEL_272:
                    v107 = *((_BYTE *)&v98->AccessState + v105);
                    v100 = *((_BYTE *)&v98->AccessState + v105 + 1);
                    goto LABEL_281;
                  }
                }
              }
              else
              {
                LODWORD(v93) = v105 + 56;
                if ( v105 + 56 <= v104 )
                {
                  v9 = *((_BYTE *)&v98->AccessState + v105 + 2) == 0;
                  v125 = 1;
                  if ( !v9 )
                    v101 = (char *)&v98[1] + v105;
                  v102 = *(_ACCESS_STATE **)((char *)&v98->DesiredAccess + v105);
                  v100 = *((_BYTE *)&v98->AccessState + v105 + 1);
                  v124 = *((_BYTE *)&v98->AccessState + v105);
                }
              }
            }
            else
            {
              LODWORD(v93) = v105 + 40;
              if ( v105 + 40 <= v104 )
              {
                if ( *((_BYTE *)&v98->AccessState + v105 + 2) )
                  v101 = (char *)&v98[1] + v105;
                v102 = *(_ACCESS_STATE **)((char *)&v98->DesiredAccess + v105);
                goto LABEL_272;
              }
            }
            if ( v125 )
              break;
          }
        }
        v103 = (unsigned int)(v103 + 1);
      }
      while ( (unsigned int)v103 < v99 );
      v107 = v124;
LABEL_281:
      if ( !v101 )
        goto LABEL_309;
      v108 = *v101;
    }
    else
    {
      v108 = (char)v98[3].SecurityQos;
      v102 = v98[1].AccessState;
      v100 = BYTE3(v98->AccessState);
      v107 = BYTE4(v98->SecurityQos);
      if ( BYTE2(v98->SecurityQos) )
        goto LABEL_309;
    }
    LOBYTE(v93) = v108 - 8;
    if ( (v93 & 0x5D) != 0 )
      goto LABEL_309;
    v109 = BYTE3(v98->SecurityQos);
    if ( v109 == 1 || !v102 || !v100 )
      goto LABEL_304;
    LOBYTE(v98) = 0;
    v110 = 0;
    v111 = 0;
    v93 = (unsigned __int64)v102 + v100;
    v112 = &v102->SecurityEvaluated;
    if ( (unsigned __int8)((v102->OperationID.LowPart & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v112 <= v93 )
      {
        v110 = BYTE2(v102->OperationID.LowPart);
        LOBYTE(v98) = BYTE1(v102->OperationID.LowPart) & 0xF;
        v111 = HIBYTE(v102->OperationID.LowPart);
        goto LABEL_303;
      }
    }
    else if ( (unsigned __int64)v112 <= v93 )
    {
      v113 = (char *)&v102->Flags + 1;
      LOBYTE(v98) = BYTE2(v102->OperationID.LowPart) & 0xF;
      v114 = v100;
      if ( (unsigned int)HIBYTE(v102->OperationID.HighPart) + 8 <= v100 )
        v114 = HIBYTE(v102->OperationID.HighPart) + 8;
      v93 = (unsigned __int64)v102 + v114;
      if ( (unsigned __int64)v113 <= v93 )
        v110 = v102->Flags;
      if ( (unsigned __int64)&v102->Flags + 2 > v93 )
        v111 = 0;
      else
        v111 = *v113;
LABEL_303:
      if ( v3 )
      {
LABEL_305:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v93,
          (_DWORD)v98,
          (unsigned int)&v127,
          (_DWORD)Irp,
          Irp->IoStatus.Status,
          v109,
          v107,
          (char)v98,
          v110,
          v111,
          (char)Irp);
        goto LABEL_309;
      }
LABEL_304:
      LOBYTE(v98) = 0;
      v110 = 0;
      v111 = 0;
      goto LABEL_305;
    }
    v3 = 0;
    goto LABEL_303;
  }
  v9 = StorEtwLoggingEnabled == 0;
  Irp->IoStatus.Information = 0;
  *((_BYTE *)&Irp->Tail.CompletionKey + 21) = -84;
  Irp->IoStatus.Status = v29;
  if ( v9 )
    goto LABEL_95;
  v127 = 0;
  IoGetActivityIdIrp(Irp, &v127);
  v11 = Irp->Tail.Overlay.CurrentStackLocation;
  if ( v11->MajorFunction == 14 )
    goto LABEL_92;
  v12 = v11->MajorFunction - 15;
  if ( v11->MajorFunction != 15 )
    goto LABEL_10;
  if ( byte_140177431 >= 0 )
    goto LABEL_95;
  SecurityContext = v11->Parameters.Create.SecurityContext;
  v17 = BYTE2(SecurityContext->SecurityQos);
  if ( (_BYTE)v17 == 40 )
  {
    if ( SecurityContext->FullCreateOptions )
      goto LABEL_95;
    v30 = (unsigned int)SecurityContext[2].AccessState;
    if ( !v30 )
      goto LABEL_95;
    v19 = 0;
    v20 = 0;
    v21 = 0;
    v22 = 0;
    v31 = 0;
    v32 = 0;
    while ( 1 )
    {
      v10 = *((unsigned int *)&SecurityContext[5].SecurityQos + v31);
      if ( (unsigned int)v10 >= 0x80 )
      {
        v33 = SecurityContext->DesiredAccess;
        if ( (unsigned int)v10 < (unsigned int)v33 )
        {
          v26 = (unsigned int)v10;
          v34 = *(_DWORD *)((char *)&SecurityContext->SecurityQos + v10) - 64;
          if ( v34 )
          {
            LODWORD(v10) = v34 - 1;
            if ( (_DWORD)v10 )
            {
              if ( (_DWORD)v10 == 1 )
              {
                LODWORD(v10) = v26 + 40;
                if ( v26 + 40 <= v33 )
                {
LABEL_31:
                  if ( *(_DWORD *)((char *)&SecurityContext->AccessState + v26 + 4) )
                    v20 = (char *)&SecurityContext[1].AccessState + v26;
                  v22 = *(_ACCESS_STATE **)((char *)&SecurityContext[1].SecurityQos + v26);
                  goto LABEL_70;
                }
              }
            }
            else
            {
              LODWORD(v10) = v26 + 56;
              if ( v26 + 56 <= v33 )
              {
                v32 = 1;
                if ( *((_BYTE *)&SecurityContext->AccessState + v26 + 2) )
                  v20 = (char *)&SecurityContext[1] + v26;
                v21 = *((_BYTE *)&SecurityContext->AccessState + v26);
                v22 = *(_ACCESS_STATE **)((char *)&SecurityContext->DesiredAccess + v26);
                v19 = *((_BYTE *)&SecurityContext->AccessState + v26 + 1);
              }
            }
          }
          else
          {
            LODWORD(v10) = v26 + 40;
            if ( v26 + 40 <= v33 )
            {
LABEL_67:
              if ( *((_BYTE *)&SecurityContext->AccessState + v26 + 2) )
                v20 = (char *)&SecurityContext[1] + v26;
              v22 = *(_ACCESS_STATE **)((char *)&SecurityContext->DesiredAccess + v26);
LABEL_70:
              v19 = *((_BYTE *)&SecurityContext->AccessState + v26 + 1);
              v21 = *((_BYTE *)&SecurityContext->AccessState + v26);
LABEL_71:
              if ( v20 )
              {
                v35 = *v20;
                goto LABEL_74;
              }
              goto LABEL_95;
            }
          }
          if ( v32 )
            goto LABEL_71;
        }
      }
      v31 = (unsigned int)(v31 + 1);
      if ( (unsigned int)v31 >= v30 )
        goto LABEL_71;
    }
  }
LABEL_73:
  v21 = BYTE4(SecurityContext->SecurityQos);
  v19 = BYTE3(SecurityContext->AccessState);
  v22 = SecurityContext[1].AccessState;
  v35 = (char)SecurityContext[3].SecurityQos;
  if ( v17 )
    goto LABEL_95;
LABEL_74:
  LOBYTE(v10) = v35 - 8;
  if ( (v10 & 0x5D) == 0 )
  {
    v36 = BYTE3(SecurityContext->SecurityQos);
    if ( v36 == 1 || !v22 || !v19 )
      goto LABEL_90;
    LOBYTE(SecurityContext) = 0;
    v37 = 0;
    v28 = 0;
    v10 = (unsigned __int64)v22 + v19;
    v38 = &v22->SecurityEvaluated;
    if ( (unsigned __int8)((v22->OperationID.LowPart & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v38 <= v10 )
      {
        v37 = BYTE2(v22->OperationID.LowPart);
        LOBYTE(SecurityContext) = BYTE1(v22->OperationID.LowPart) & 0xF;
        v28 = HIBYTE(v22->OperationID.LowPart);
        goto LABEL_89;
      }
    }
    else if ( (unsigned __int64)v38 <= v10 )
    {
      v39 = (char *)&v22->Flags + 1;
      LOBYTE(SecurityContext) = BYTE2(v22->OperationID.LowPart) & 0xF;
      v40 = v19;
      if ( (unsigned int)HIBYTE(v22->OperationID.HighPart) + 8 <= v19 )
        v40 = HIBYTE(v22->OperationID.HighPart) + 8;
      v10 = (unsigned __int64)v22 + v40;
      if ( (unsigned __int64)v39 <= v10 )
        v37 = v22->Flags;
      if ( (unsigned __int64)&v22->Flags + 2 > v10 )
        v28 = 0;
      else
        v28 = *v39;
LABEL_89:
      if ( v3 )
      {
LABEL_91:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v10,
          (_DWORD)SecurityContext,
          (unsigned int)&v127,
          (_DWORD)Irp,
          Irp->IoStatus.Status,
          v36,
          v21,
          (char)SecurityContext,
          v37,
          v28,
          (char)Irp);
        goto LABEL_95;
      }
LABEL_90:
      LOBYTE(SecurityContext) = 0;
      v37 = 0;
      v28 = 0;
      goto LABEL_91;
    }
    v3 = 0;
    goto LABEL_89;
  }
LABEL_95:
  IofCompleteRequest(Irp, 0);
  return v126;
}

```

## disassembly

```asm
0x1401c36a8  mov     [rsp-8+arg_10], rbx
0x1401c36ad  push    rbp
0x1401c36ae  push    rsi
0x1401c36af  push    rdi
0x1401c36b0  push    r12
0x1401c36b2  push    r13
0x1401c36b4  push    r14
0x1401c36b6  push    r15
0x1401c36b8  lea     rbp, [rsp-27h]
0x1401c36bd  sub     rsp, 0A0h
0x1401c36c4  mov     rax, cs:__security_cookie
0x1401c36cb  xor     rax, rsp
0x1401c36ce  mov     [rbp+57h+var_40], rax
0x1401c36d2  cmp     cs:StorEtwLoggingEnabled, 0
0x1401c36d9  xorps   xmm0, xmm0
0x1401c36dc  mov     rax, [rdx+0B8h]
0x1401c36e3  mov     r14d, 1
0x1401c36e9  movups  [rbp+57h+var_50], xmm0
0x1401c36ed  mov     rbx, rdx
0x1401c36f0  mov     [rbp+57h+var_70], r14b
0x1401c36f4  mov     rsi, rcx
0x1401c36f7  mov     edi, [rax+18h]
0x1401c36fa  jz      short loc_1401C3749
0x1401c36fc  lea     rdx, [rbp+57h+var_50]
0x1401c3700  mov     rcx, rbx
0x1401c3703  call    cs:__imp_IoGetActivityIdIrp
0x1401c370a  nop     dword ptr [rax+rax+00h]
0x1401c370f  test    cs:byte_140177432, 2
0x1401c3716  jz      short loc_1401C3749
0x1401c3718  mov     rax, [rbx+0B8h]
0x1401c371f  lea     rdx, EventIOCTL
0x1401c3726  mov     [rsp+0D0h+var_A0], edi
0x1401c372a  movzx   r8d, byte ptr [rax+1]
0x1401c372f  movzx   r9d, byte ptr [rax]
0x1401c3733  mov     [rsp+0D0h+var_A8], r8d
0x1401c3738  lea     r8, [rbp+57h+var_50]
0x1401c373c  mov     [rsp+0D0h+var_B0], r9d
0x1401c3741  mov     r9, rbx
0x1401c3744  call    McTemplateK0pddd_EtwWriteTransfer
0x1401c3749  cmp     edi, 2D190Ch
0x1401c374f  jnz     short loc_1401C3761
0x1401c3751  mov     rdx, rbx
0x1401c3754  mov     rcx, rsi
0x1401c3757  call    NvmeNamespaceQueryFinalRemovePendingIoctl
0x1401c375c  jmp     loc_1401C47C8
0x1401c3761  test    byte ptr [rsi+70h], 2
0x1401c3765  jnz     loc_1401C391A
0x1401c376b  cmp     cs:StorEtwLoggingEnabled, 0
0x1401c3772  mov     eax, 0C0000010h
0x1401c3777  mov     [rbp+57h+var_68], eax
0x1401c377a  mov     [rbx+30h], eax
0x1401c377d  mov     qword ptr [rbx+38h], 0
0x1401c3785  mov     byte ptr [rbx+8Dh], 0ACh
0x1401c378c  jz      loc_1401C3B8B
0x1401c3792  xorps   xmm0, xmm0
0x1401c3795  lea     rdx, [rbp+57h+var_60]
0x1401c3799  mov     rcx, rbx
0x1401c379c  movups  [rbp+57h+var_60], xmm0
0x1401c37a0  call    cs:__imp_IoGetActivityIdIrp
0x1401c37a7  nop     dword ptr [rax+rax+00h]
0x1401c37ac  mov     rdx, [rbx+0B8h]
0x1401c37b3  movzx   eax, byte ptr [rdx]
0x1401c37b6  sub     eax, 0Eh
0x1401c37b9  jz      loc_1401C3B68
0x1401c37bf  sub     eax, r14d
0x1401c37c2  jz      short loc_1401C382A
0x1401c37c4  cmp     eax, 0Ch
0x1401c37c7  jnz     loc_1401C3B8B
0x1401c37cd  cmp     byte ptr [rdx+1], 7
0x1401c37d1  jnz     short loc_1401C3811
0x1401c37d3  cmp     dword ptr [rdx+8], 0
0x1401c37d7  jnz     short loc_1401C3811
0x1401c37d9  test    cs:byte_140177432, 40h
0x1401c37e0  jz      loc_1401C3B8B
0x1401c37e6  mov     rax, [rbx+38h]
0x1401c37ea  test    rax, rax
0x1401c37ed  jz      short loc_1401C37F3
0x1401c37ef  mov     ecx, [rax]
0x1401c37f1  jmp     short loc_1401C37F5
0x1401c37f3  xor     ecx, ecx
0x1401c37f5  mov     eax, [rbx+30h]
0x1401c37f8  lea     r8, [rbp+57h+var_60]
0x1401c37fc  mov     [rsp+0D0h+var_A8], eax
0x1401c3800  mov     r9, rbx
0x1401c3803  mov     [rsp+0D0h+var_B0], ecx
0x1401c3807  call    McTemplateK0pqd_EtwWriteTransfer
0x1401c380c  jmp     loc_1401C3B8B
0x1401c3811  test    cs:byte_140177432, 20h
0x1401c3818  jz      loc_1401C3B8B
0x1401c381e  lea     rdx, EventPnpRequestComplete
0x1401c3825  jmp     loc_1401C3B78
0x1401c382a  cmp     cs:byte_140177431, 0
0x1401c3831  jge     loc_1401C3B8B
0x1401c3837  mov     rdx, [rdx+8]
0x1401c383b  movzx   eax, byte ptr [rdx+2]
0x1401c383f  cmp     al, 28h ; '('
0x1401c3841  jnz     loc_1401C3A72
0x1401c3847  cmp     dword ptr [rdx+14h], 0
0x1401c384b  jnz     loc_1401C3B8B
0x1401c3851  mov     r12d, [rdx+38h]
0x1401c3855  test    r12d, r12d
0x1401c3858  jz      loc_1401C3B8B
0x1401c385e  xor     r10b, r10b
0x1401c3861  xor     r11d, r11d
0x1401c3864  xor     sil, sil
0x1401c3867  xor     r9d, r9d
0x1401c386a  xor     r15d, r15d
0x1401c386d  xor     r13b, r13b
0x1401c3870  mov     ecx, [rdx+r15*4+78h]
0x1401c3875  cmp     ecx, 80h
0x1401c387b  jb      loc_1401C3901
0x1401c3881  mov     edi, [rdx+10h]
0x1401c3884  cmp     ecx, edi
0x1401c3886  jnb     short loc_1401C3901
0x1401c3888  mov     r8d, ecx
0x1401c388b  mov     ecx, [rcx+rdx]
0x1401c388e  sub     ecx, 40h ; '@'
0x1401c3891  jz      short loc_1401C38EB
0x1401c3893  sub     ecx, r14d
0x1401c3896  jz      short loc_1401C38BF
0x1401c3898  cmp     ecx, r14d
0x1401c389b  jnz     short loc_1401C38F8
0x1401c389d  lea     rcx, [r8+28h]
0x1401c38a1  cmp     rcx, rdi
0x1401c38a4  ja      short loc_1401C38F8
0x1401c38a6  cmp     dword ptr [r8+rdx+0Ch], 0
0x1401c38ac  jbe     short loc_1401C38B5
0x1401c38ae  lea     r11, [rdx+20h]
0x1401c38b2  add     r11, r8
0x1401c38b5  mov     r9, [r8+rdx+18h]
0x1401c38ba  jmp     loc_1401C3A5A
0x1401c38bf  lea     rcx, [r8+38h]
0x1401c38c3  cmp     rcx, rdi
0x1401c38c6  ja      short loc_1401C38F8
0x1401c38c8  cmp     byte ptr [r8+rdx+0Ah], 0
0x1401c38ce  mov     r13b, r14b
0x1401c38d1  jbe     short loc_1401C38DA
0x1401c38d3  lea     r11, [rdx+18h]
0x1401c38d7  add     r11, r8
0x1401c38da  mov     sil, [r8+rdx+8]
0x1401c38df  mov     r9, [r8+rdx+10h]
0x1401c38e4  mov     r10b, [r8+rdx+9]
0x1401c38e9  jmp     short loc_1401C38F8
0x1401c38eb  lea     rcx, [r8+28h]
0x1401c38ef  cmp     rcx, rdi
0x1401c38f2  jbe     loc_1401C3A46
0x1401c38f8  test    r13b, r13b
0x1401c38fb  jnz     loc_1401C3A64
0x1401c3901  add     r15d, r14d
0x1401c3904  cmp     r15d, r12d
0x1401c3907  jb      loc_1401C3870
0x1401c390d  jmp     loc_1401C3A64
0x1401c3912  xor     r8b, r8b
0x1401c3915  jmp     loc_1401C3B29
0x1401c391a  mov     rdx, rbx
0x1401c391d  mov     rcx, rsi
0x1401c3920  call    NvmeNamespaceAcquireRemoveLock
0x1401c3925  mov     [rbp+57h+var_68], eax
0x1401c3928  test    eax, eax
0x1401c392a  jns     loc_1401C3BA4
0x1401c3930  cmp     cs:StorEtwLoggingEnabled, 0
0x1401c3937  mov     qword ptr [rbx+38h], 0
0x1401c393f  mov     byte ptr [rbx+8Dh], 0ACh
0x1401c3946  mov     [rbx+30h], eax
0x1401c3949  jz      loc_1401C3B8B
0x1401c394f  xorps   xmm0, xmm0
0x1401c3952  lea     rdx, [rbp+57h+var_60]
0x1401c3956  mov     rcx, rbx
0x1401c3959  movups  [rbp+57h+var_60], xmm0
0x1401c395d  call    cs:__imp_IoGetActivityIdIrp
0x1401c3964  nop     dword ptr [rax+rax+00h]
0x1401c3969  mov     rdx, [rbx+0B8h]
0x1401c3970  movzx   eax, byte ptr [rdx]
0x1401c3973  sub     eax, 0Eh
0x1401c3976  jz      loc_1401C3B68
0x1401c397c  sub     eax, r14d
0x1401c397f  jnz     loc_1401C37C4
0x1401c3985  cmp     cs:byte_140177431, al
0x1401c398b  jge     loc_1401C3B8B
0x1401c3991  mov     rdx, [rdx+8]
0x1401c3995  movzx   eax, byte ptr [rdx+2]
0x1401c3999  cmp     al, 28h ; '('
0x1401c399b  jnz     loc_1401C3A72
0x1401c39a1  cmp     dword ptr [rdx+14h], 0
0x1401c39a5  jnz     loc_1401C3B8B
0x1401c39ab  mov     r12d, [rdx+38h]
0x1401c39af  test    r12d, r12d
0x1401c39b2  jz      loc_1401C3B8B
0x1401c39b8  xor     r10b, r10b
0x1401c39bb  xor     r11d, r11d
0x1401c39be  xor     sil, sil
0x1401c39c1  xor     r9d, r9d
0x1401c39c4  xor     r15d, r15d
0x1401c39c7  xor     r13b, r13b
0x1401c39ca  mov     ecx, [rdx+r15*4+78h]
0x1401c39cf  cmp     ecx, 80h
0x1401c39d5  jb      short loc_1401C3A3C
0x1401c39d7  mov     edi, [rdx+10h]
0x1401c39da  cmp     ecx, edi
0x1401c39dc  jnb     short loc_1401C3A3C
0x1401c39de  mov     r8d, ecx
0x1401c39e1  mov     ecx, [rcx+rdx]
0x1401c39e4  sub     ecx, 40h ; '@'
0x1401c39e7  jz      short loc_1401C3A2E
0x1401c39e9  sub     ecx, r14d
0x1401c39ec  jz      short loc_1401C3A02
0x1401c39ee  cmp     ecx, r14d
0x1401c39f1  jnz     short loc_1401C3A37
0x1401c39f3  lea     rcx, [r8+28h]
0x1401c39f7  cmp     rcx, rdi
0x1401c39fa  jbe     loc_1401C38A6
0x1401c3a00  jmp     short loc_1401C3A37
0x1401c3a02  lea     rcx, [r8+38h]
0x1401c3a06  cmp     rcx, rdi
0x1401c3a09  ja      short loc_1401C3A37
0x1401c3a0b  cmp     byte ptr [r8+rdx+0Ah], 0
0x1401c3a11  mov     r13b, r14b
0x1401c3a14  jbe     short loc_1401C3A1D
0x1401c3a16  lea     r11, [rdx+18h]
0x1401c3a1a  add     r11, r8
0x1401c3a1d  mov     sil, [r8+rdx+8]
0x1401c3a22  mov     r9, [r8+rdx+10h]
0x1401c3a27  mov     r10b, [r8+rdx+9]
0x1401c3a2c  jmp     short loc_1401C3A37
0x1401c3a2e  lea     rcx, [r8+28h]
0x1401c3a32  cmp     rcx, rdi
0x1401c3a35  jbe     short loc_1401C3A46
0x1401c3a37  test    r13b, r13b
0x1401c3a3a  jnz     short loc_1401C3A64
0x1401c3a3c  add     r15d, r14d
0x1401c3a3f  cmp     r15d, r12d
0x1401c3a42  jb      short loc_1401C39CA
0x1401c3a44  jmp     short loc_1401C3A64
0x1401c3a46  cmp     byte ptr [r8+rdx+0Ah], 0
0x1401c3a4c  jbe     short loc_1401C3A55
0x1401c3a4e  lea     r11, [rdx+18h]
0x1401c3a52  add     r11, r8
0x1401c3a55  mov     r9, [r8+rdx+10h]
0x1401c3a5a  mov     r10b, [r8+rdx+9]
0x1401c3a5f  mov     sil, [r8+rdx+8]
0x1401c3a64  test    r11, r11
0x1401c3a67  jz      loc_1401C3B8B
0x1401c3a6d  mov     cl, [r11]
0x1401c3a70  jmp     short loc_1401C3A89
0x1401c3a72  mov     sil, [rdx+4]
0x1401c3a76  mov     r10b, [rdx+0Bh]
0x1401c3a7a  mov     r9, [rdx+20h]
0x1401c3a7e  mov     cl, [rdx+48h]
0x1401c3a81  test    eax, eax
0x1401c3a83  jnz     loc_1401C3B8B
0x1401c3a89  sub     cl, 8
0x1401c3a8c  test    cl, 5Dh
0x1401c3a8f  jnz     loc_1401C3B8B
0x1401c3a95  mov     dil, [rdx+3]
0x1401c3a99  cmp     dil, r14b
0x1401c3a9c  jz      loc_1401C3B2E
0x1401c3aa2  test    r9, r9
0x1401c3aa5  jz      loc_1401C3B2E
0x1401c3aab  test    r10b, r10b
0x1401c3aae  jz      short loc_1401C3B2E
0x1401c3ab0  mov     al, [r9]
0x1401c3ab3  xor     dl, dl
0x1401c3ab5  and     al, 7Fh
0x1401c3ab7  movzx   ecx, r10b
0x1401c3abb  sub     al, 72h ; 'r'
0x1401c3abd  xor     r11b, r11b
0x1401c3ac0  xor     r8b, r8b
0x1401c3ac3  add     rcx, r9
0x1401c3ac6  cmp     al, r14b
0x1401c3ac9  lea     rax, [r9+8]
0x1401c3acd  jbe     short loc_1401C3B10
0x1401c3acf  cmp     rax, rcx
0x1401c3ad2  ja      short loc_1401C3B26
0x1401c3ad4  movzx   ecx, byte ptr [r9+7]
0x1401c3ad9  lea     r8, [r9+0Dh]
0x1401c3add  mov     dl, [r9+2]
0x1401c3ae1  add     ecx, 8
0x1401c3ae4  and     dl, 0Fh
0x1401c3ae7  movzx   eax, r10b
0x1401c3aeb  cmp     ecx, eax
0x1401c3aed  cmovbe  eax, ecx
0x1401c3af0  mov     ecx, eax
0x1401c3af2  add     rcx, r9
0x1401c3af5  cmp     r8, rcx
0x1401c3af8  ja      short loc_1401C3AFE
0x1401c3afa  mov     r11b, [r9+0Ch]
0x1401c3afe  lea     rax, [r9+0Eh]
0x1401c3b02  cmp     rax, rcx
0x1401c3b05  ja      loc_1401C3912
0x1401c3b0b  mov     r8b, [r8]
0x1401c3b0e  jmp     short loc_1401C3B29
0x1401c3b10  cmp     rax, rcx
0x1401c3b13  ja      short loc_1401C3B26
0x1401c3b15  mov     dl, [r9+1]
0x1401c3b19  mov     r11b, [r9+2]
0x1401c3b1d  and     dl, 0Fh
0x1401c3b20  mov     r8b, [r9+3]
0x1401c3b24  jmp     short loc_1401C3B29
0x1401c3b26  xor     r14b, r14b
0x1401c3b29  test    r14b, r14b
  ... truncated ...
```
