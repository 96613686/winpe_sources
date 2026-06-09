# SC_ENV::EventWrite(ulong,...)

- ea: `0x1400044d0`
- end: `0x1400057e6`
- name: `?EventWrite@SC_ENV@@SAXKZZ`
- size: `4886`
- prototype: `void(unsigned int, ...)`
- caller_count: `49`
- callee_count: `39`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140004410`
- `0x140005a50`
- `0x14000cd20`
- `0x14001dd60`
- `0x14001eb50`
- `0x140026130`
- `0x14002aa3c`
- `0x14003e440`
- `0x14004088c`
- `0x140040ef0`
- `0x140041f48`
- `0x1400429b0`
- `0x140043ad8`
- `0x140043c94`
- `0x140049214`
- `0x140049338`
- `0x14004954c`
- `0x14004c604`
- `0x14004c9c0`
- `0x14004e140`
- `0x14005201c`
- `0x1400539b4`
- `0x140059af0`
- `0x14005aa10`
- `0x14005aed8`
- `0x14005b090`
- `0x14005b76c`
- `0x140062ec0`
- `0x140065ec0`
- `0x140066028`
- `0x140066368`
- `0x140066438`
- `0x140066480`
- `0x14008d3f4`
- `0x14009d1fc`
- `0x14009d930`
- `0x14009df5c`
- `0x14009f82c`
- `0x1400a0fb0`
- `0x1400a54d0`
- `0x1400b0a80`
- `0x1400b0c40`
- `0x1400b1190`
- `0x1400b1528`
- `0x1400b18b4`
- `0x1400b1c98`
- `0x1400b2348`
- `0x1400b25c0`
- `0x1400b305c`

## callees

- `0x1400044d0`
- `0x14001f330`
- `0x14002bff4`
- `0x14002fa18`
- `0x14002fa80`
- `0x14002faf8`
- `0x14002fbac`
- `0x14002fc40`
- `0x14002fcec`
- `0x14002fdb0`
- `0x14002fe10`
- `0x14002fed0`
- `0x14002ff44`
- `0x14002ffd0`
- `0x14003005c`
- `0x140030100`
- `0x1400301b4`
- `0x1400302c0`
- `0x140030380`
- `0x140030410`
- `0x1400304c4`
- `0x140030578`
- `0x140030634`
- `0x14003072c`
- `0x1400307c0`
- `0x140030864`
- `0x140030918`
- `0x14003098c`
- `0x140030a30`
- `0x140030acc`
- `0x140030b70`
- `0x140030c2c`
- `0x140030ce4`
- `0x140030d5c`
- `0x140030e10`
- `0x140030e8c`
- `0x140030f40`
- `0x140068110`
- `0x140068150`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000573f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000573f`
- `ntoskrnl!IoGetActivityIdThread` at `0x140004571`
- `ntoskrnl!IoGetActivityIdThread` at `0x140004808`
- `ntoskrnl!IoGetActivityIdThread` at `0x140004899`
- `ntoskrnl!IoGetActivityIdThread` at `0x1400048e1`
- `ntoskrnl!IoGetActivityIdThread` at `0x140004571`
- `ntoskrnl!IoGetActivityIdThread` at `0x140004808`
- `ntoskrnl!IoGetActivityIdThread` at `0x140004899`
- `ntoskrnl!IoGetActivityIdThread` at `0x1400048e1`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140004bd1`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140004da8`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140004dd1`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140004bd1`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140004da8`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140004dd1`
- `ntoskrnl!EtwWriteTransfer` at `0x1400046ab`
- `ntoskrnl!EtwWriteTransfer` at `0x140005071`
- `ntoskrnl!EtwWriteTransfer` at `0x1400046ab`
- `ntoskrnl!EtwWriteTransfer` at `0x140005071`

## pseudocode

```c
void SC_ENV::EventWrite(
        unsigned int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int *a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        char a9,
        char a10,
        unsigned __int8 a11,
        char a12,
        ...)
{
  __int64 v12; // rcx
  int v13; // eax
  int v14; // edx
  int v15; // ecx
  int ActivityIdThread; // eax
  int v17; // edx
  int v18; // ecx
  __int64 v19; // rcx
  int v20; // eax
  int v21; // ecx
  int v22; // eax
  int v23; // edx
  int v24; // ecx
  ULONGLONG v25; // rcx
  int v26; // r8d
  unsigned __int64 v27; // rdi
  ULONGLONG v28; // rbx
  ULONGLONG v29; // rcx
  int v30; // r8d
  unsigned __int64 v31; // rdi
  int *v32; // rax
  __int64 v33; // rdi
  int v34; // esi
  int v35; // r14d
  int v36; // eax
  int v37; // edx
  int v38; // ecx
  int v39; // r8d
  int v40; // ebx
  __int64 v41; // rsi
  int v42; // r14d
  int v43; // r15d
  int v44; // eax
  int v45; // edx
  int v46; // ecx
  int v47; // r8d
  unsigned int v48; // ecx
  unsigned int v49; // ecx
  unsigned int v50; // ecx
  unsigned int v51; // ecx
  unsigned int v52; // ecx
  __int64 v53; // rcx
  PVOID v54; // rax
  unsigned int v55; // [rsp+70h] [rbp-90h] BYREF
  int v56; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v57; // [rsp+78h] [rbp-88h] BYREF
  int v58; // [rsp+7Ch] [rbp-84h] BYREF
  ULONGLONG v59; // [rsp+80h] [rbp-80h] BYREF
  EVENT_DESCRIPTOR v60; // [rsp+88h] [rbp-78h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+98h] [rbp-68h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+B0h] [rbp-50h] BYREF
  char *v63; // [rsp+C0h] [rbp-40h]
  int v64; // [rsp+C8h] [rbp-38h]
  int v65; // [rsp+CCh] [rbp-34h]
  __int64 v66; // [rsp+D0h] [rbp-30h]
  __int64 v67; // [rsp+D8h] [rbp-28h]
  __int64 v68; // [rsp+E0h] [rbp-20h]
  __int64 v69; // [rsp+E8h] [rbp-18h]
  EVENT_DESCRIPTOR *p_EventDescriptor; // [rsp+F0h] [rbp-10h]
  __int64 v71; // [rsp+F8h] [rbp-8h]
  EVENT_DESCRIPTOR *v72; // [rsp+100h] [rbp+0h]
  __int64 v73; // [rsp+108h] [rbp+8h]
  unsigned int *v74; // [rsp+110h] [rbp+10h]
  __int64 v75; // [rsp+118h] [rbp+18h]
  unsigned int *v76; // [rsp+120h] [rbp+20h]
  __int64 v77; // [rsp+128h] [rbp+28h]
  _DWORD *v78; // [rsp+130h] [rbp+30h]
  __int64 v79; // [rsp+138h] [rbp+38h]
  _DWORD *v80; // [rsp+140h] [rbp+40h]
  __int64 v81; // [rsp+148h] [rbp+48h]
  _DWORD *v82; // [rsp+150h] [rbp+50h]
  __int64 v83; // [rsp+158h] [rbp+58h]
  ULONGLONG *v84; // [rsp+160h] [rbp+60h]
  __int64 v85; // [rsp+168h] [rbp+68h]

  *(_QWORD *)&EventDescriptor.Id = 0;
  if ( a1 <= 0x3E8 )
  {
    if ( a1 == 1000 )
    {
      if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x20) != 0 )
      {
        ActivityIdThread = IoGetActivityIdThread();
        McTemplateK0jsqq_EtwWriteTransfer(v18, v17, ActivityIdThread, a2, a3, a4, (char)a5);
      }
    }
    else
    {
      v12 = a1 - 302;
      switch ( (int)v12 )
      {
        case 0:
          if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 1) != 0 )
            McTemplateK0jq_EtwWriteTransfer(v12, SpaceConfigWriteFailure, 0, a2 + 16, a3);
          if ( (unsigned int)dword_14007F050 > 5
            && (qword_14007F060 & 0x400000000000LL) != 0
            && (qword_14007F068 & 0x400000000000LL) == qword_14007F068 )
          {
            EventDescriptor.Keyword = 0x400000000000LL;
            p_EventDescriptor = (EVENT_DESCRIPTOR *)&v58;
            *(_DWORD *)&EventDescriptor.Level = 5;
            UserData.Ptr = (ULONGLONG)off_14007F058;
            v58 = a3;
            v71 = 4;
            v68 = a2 + 16;
            v69 = 16;
            v66 = a2;
            v67 = 16;
            *(_DWORD *)&EventDescriptor.Id = 184549376;
            UserData.Size = *(unsigned __int16 *)off_14007F058;
            v63 = &byte_14007534F;
            UserData.Reserved = 2;
            v64 = 65;
            v65 = 1;
            LODWORD(v59) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
          }
          break;
        case 1:
          if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 1) != 0 )
          {
            v13 = IoGetActivityIdThread();
            McTemplateK0jjs_EtwWriteTransfer(v15, v14, v13, a2, a3, a4);
          }
          break;
        case 12:
          if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 4) != 0 )
            McTemplateK0jxxxqq_EtwWriteTransfer(v12, 0x40000000u, a3, a2, a3, a4, (char)a5, a6, a7);
          break;
        case 13:
          if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 1) != 0 )
            McTemplateK0jqxqq_EtwWriteTransfer(v12, 0x40000000u, a3, a2, a3, a4, (char)a5, a6);
          break;
        case 14:
          if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 1) != 0 )
            McTemplateK0jq_EtwWriteTransfer(v12, SpaceColumnUpdateFailed, 0, a2, a3);
          break;
        case 206:
          if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x10) != 0 )
            McTemplateK0jq_EtwWriteTransfer(v12, SpacesPdReadDriveHeaderFailure, 0, a2, a3);
          break;
        case 207:
          if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x10) != 0 )
            McTemplateK0jq_EtwWriteTransfer(v12, SpacesPdConfigLoadFailure, 0, a2, a3);
          break;
        case 208:
          if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x10) != 0 )
            McTemplateK0jq_EtwWriteTransfer(v12, SpacesPdDrtInitFailure, 0, a2, a3);
          break;
        default:
          return;
      }
    }
    return;
  }
  if ( a1 > 0x643 )
  {
    if ( a1 > 0x837 )
    {
      v51 = a1 - 2104;
      if ( v51 )
      {
        v52 = v51 - 496;
        if ( v52 )
        {
          if ( v52 == 1 && (byte_14007F4C1 & 0x10) != 0 )
            McTemplateK0jxqqxqqxq_EtwWriteTransfer(1, a2, a3, a2, a3, a4, (char)a5, a6, a7, a8, a9, a10);
        }
        else if ( (byte_14007F4C1 & 8) != 0 )
        {
          v53 = *(_QWORD *)(a4 + 120);
          if ( (*(_BYTE *)(v53 + 10) & 5) != 0 )
            v54 = *(PVOID *)(v53 + 24);
          else
            v54 = MmMapLockedPagesSpecifyCache((PMDL)v53, 0, MmCached, 0, 0, 0x40000020u);
          McTemplateK0qqqqhhhub8_EtwWriteTransfer(
            *(_QWORD *)(a4 + 8),
            *(_DWORD *)(a4 + 180) >> 31,
            *(unsigned __int8 *)(*(_QWORD *)(a4 + 8) + 169LL),
            *(_DWORD *)(a2 + 24),
            a3,
            *(_DWORD *)(a4 + 136),
            *(_DWORD *)(a4 + 144),
            *(_BYTE *)(*(_QWORD *)(a4 + 8) + 169LL),
            *(_WORD *)(a4 + 156),
            *(_WORD *)(a4 + 148),
            *(int *)(a4 + 180) < 0,
            (__int64)v54);
        }
      }
      else if ( (byte_14007F4C1 & 4) != 0 )
      {
        McTemplateK0jqqq_EtwWriteTransfer(0, (unsigned int)LogAdvance, a3, a2, a3, a4, (char)a5);
      }
    }
    else if ( a1 == 2103 )
    {
      if ( (byte_14007F4C1 & 4) != 0 )
        McTemplateK0jqxqu_EtwWriteTransfer(2103, (unsigned int)LogRemove, a3, a2, a3, a4, (char)a5, a6);
    }
    else
    {
      v48 = a1 - 1607;
      if ( v48 )
      {
        v49 = v48 - 493;
        if ( v49 )
        {
          v50 = v49 - 1;
          if ( v50 )
          {
            if ( v50 == 1 && (byte_14007F4C1 & 4) != 0 )
              McTemplateK0jqqq_EtwWriteTransfer(1, (unsigned int)LogFlush, a3, a2, a3, a4, (char)a5);
          }
          else if ( (byte_14007F4C1 & 4) != 0 )
          {
            McTemplateK0jqxqu_EtwWriteTransfer(0, (unsigned int)LogInsert, a3, a2, a3, a4, (char)a5, a6);
          }
        }
        else if ( (byte_14007F4C1 & 4) != 0 )
        {
          McTemplateK0jqx_EtwWriteTransfer(0, (unsigned int)LogUsage, 0, a2, a3, a4);
        }
      }
      else if ( (byte_14007F4C1 & 1) != 0 )
      {
        McTemplateK0jxq_EtwWriteTransfer(0, (unsigned int)UnmapSlabFailed, a3, a2, a3, a4);
      }
    }
  }
  else if ( a1 == 1603 )
  {
    if ( (byte_14007F4C1 & 1) != 0 )
      McTemplateK0jtqqqNR4_EtwWriteTransfer((unsigned __int8)a3, a2, a3, a2, a3, a4, (char)a5, a6, a7, a8);
  }
  else
  {
    v19 = a1 - 1003;
    switch ( (int)v19 )
    {
      case 0:
        if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
        {
          v20 = IoGetActivityIdThread();
          McTemplateK0jqx_EtwWriteTransfer(v21, (unsigned int)SpaceTransactionStart, v20, a2, a3, a4);
        }
        return;
      case 1:
        if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
        {
          v22 = IoGetActivityIdThread();
          McTemplateK0jqqx_EtwWriteTransfer(v24, v23, v22, a2, a3, a4, (char)a5);
        }
        return;
      case 10:
        if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x20) != 0 )
          McTemplateK0jxqqqq_EtwWriteTransfer(v19, 0x40000000u, a3, a2, a3, a4, (char)a5, a6, a7);
        return;
      case 16:
        if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
          McTemplateK0jqqqqq_EtwWriteTransfer(v19, 0x40000000u, a3, a2, a3, a4, (char)a5, a6, a7);
        return;
      case 18:
        v25 = KeQueryUnbiasedInterruptTime() - a3;
        v27 = v25 / 0xA;
        if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
          McTemplateK0jjxx_EtwWriteTransfer(
            v25,
            (v25 * (unsigned __int128)0xCCCCCCCCCCCCCCCDuLL) >> 64,
            v26,
            a2,
            a2 + 16,
            v25 / 0xA,
            a4);
        if ( (unsigned int)dword_14007F050 > 5
          && (qword_14007F060 & 0x400000000000LL) != 0
          && (qword_14007F068 & 0x400000000000LL) == qword_14007F068 )
        {
          v58 = a5[2];
          v55 = a5[1];
          v56 = *a5;
          v84 = &v59;
          v82 = a5 + 20;
          v80 = a5 + 11;
          v78 = a5 + 3;
          v76 = (unsigned int *)&v58;
          v74 = &v55;
          v72 = (EVENT_DESCRIPTOR *)&v56;
          p_EventDescriptor = &EventDescriptor;
          *(_DWORD *)&v60.Level = 5;
          UserData.Ptr = (ULONGLONG)off_14007F058;
          v60.Keyword = 0x400000000000LL;
          LODWORD(v59) = 4;
          *(_QWORD *)&EventDescriptor.Id = v27;
          v85 = 4;
          v83 = 36;
          v81 = 36;
          v79 = 32;
          v77 = 4;
          v75 = 4;
          v73 = 4;
          v71 = 8;
          v68 = a2 + 16;
          v69 = 16;
          v66 = a2;
          v67 = 16;
          *(_DWORD *)&v60.Id = 184549376;
          UserData.Size = *(unsigned __int16 *)off_14007F058;
          v63 = (char *)&unk_1400754D0;
          UserData.Reserved = 2;
          v64 = 173;
          v65 = 1;
          v57 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwWriteTransfer(RegHandle, &v60, 0, 0, 0xCu, &UserData);
        }
        return;
      case 19:
      case 26:
        v28 = (KeQueryUnbiasedInterruptTime() - a4) / 0xA;
        v29 = KeQueryUnbiasedInterruptTime() - (_QWORD)a5;
        v31 = v29 / 0xA;
        if ( a1 == 1029 )
        {
          if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x20) != 0 )
            McTemplateK0jjxxqq_EtwWriteTransfer(
              v29,
              (unsigned int)SpaceAttachFailed,
              v30,
              a2,
              a3,
              v28,
              v29 / 0xA,
              a6,
              a7);
          if ( (unsigned int)dword_14007F050 > 5
            && (qword_14007F060 & 0x400000000000LL) != 0
            && (qword_14007F068 & 0x400000000000LL) == qword_14007F068 )
          {
            v57 = a7;
            v76 = &v57;
            v74 = (unsigned int *)&v56;
            v72 = &EventDescriptor;
            p_EventDescriptor = (EVENT_DESCRIPTOR *)&v59;
            *(_DWORD *)&v60.Level = 5;
            UserData.Ptr = (ULONGLONG)off_14007F058;
            v56 = a6;
            *(_QWORD *)&EventDescriptor.Id = v31;
            v59 = v28;
            v77 = 4;
            v75 = 4;
            v73 = 8;
            v71 = 8;
            v68 = a3;
            v69 = 16;
            v66 = a2;
            v67 = 16;
            *(_DWORD *)&v60.Id = 184549376;
            v60.Keyword = 0x400000000000LL;
            UserData.Size = *(unsigned __int16 *)off_14007F058;
            v32 = (int *)&byte_140075437;
            v64 = 141;
LABEL_72:
            v63 = (char *)v32;
            UserData.Reserved = 2;
            v65 = 1;
            v55 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EtwWriteTransfer(RegHandle, &v60, 0, 0, 8u, &UserData);
            return;
          }
        }
        else
        {
          if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
            McTemplateK0jjxxqq_EtwWriteTransfer(v29, (unsigned int)SpaceDetach, v30, a2, a3, v28, v29 / 0xA, a6, a7);
          if ( (unsigned int)dword_14007F050 > 5
            && (qword_14007F060 & 0x400000000000LL) != 0
            && (qword_14007F068 & 0x400000000000LL) == qword_14007F068 )
          {
            v57 = a7;
            v76 = &v57;
            v74 = (unsigned int *)&v56;
            v72 = &EventDescriptor;
            p_EventDescriptor = (EVENT_DESCRIPTOR *)&v59;
            *(_DWORD *)&v60.Level = 5;
            UserData.Ptr = (ULONGLONG)off_14007F058;
            v56 = a6;
            *(_QWORD *)&EventDescriptor.Id = v31;
            v59 = v28;
            v77 = 4;
            v75 = 4;
            v73 = 8;
            v71 = 8;
            v68 = a3;
            v69 = 16;
            v66 = a2;
            v67 = 16;
            *(_DWORD *)&v60.Id = 184549376;
            v60.Keyword = 0x400000000000LL;
            UserData.Size = *(unsigned __int16 *)off_14007F058;
            v32 = &dword_14007539C;
            v64 = 143;
            goto LABEL_72;
          }
        }
        break;
      case 20:
        if ( Microsoft_Windows_StorageSpaces_DriverEnableBits < 0 )
          McTemplateK0jqq_EtwWriteTransfer(v19, (unsigned int)DrtDirty, a3, a2, a3, a4);
        return;
      case 21:
        if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
          McTemplateK0jq_EtwWriteTransfer(v19, DrtClean, 0, a2, a3);
        return;
      case 22:
        if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
          McTemplateK0jqqqq_EtwWriteTransfer(v19, 0x40000000u, a3, a2, a3, a4, (char)a5, a6);
        return;
      case 23:
        if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
          McTemplateK0jquq_EtwWriteTransfer(v19, 0x40000000u, a3, a2, a3, a4, (char)a5);
        return;
      case 35:
        if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
          McTemplateK0jqqxxxqxqq_EtwWriteTransfer(v19, 0x40000000u, a3, a2, a3, a4, (char)a5, a6, a7, a8, a9, a10, a11);
        return;
      case 36:
        if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x20) != 0 )
          McTemplateK0jquxq_EtwWriteTransfer(v19, 0x40000000u, a3, a2, a3, a4, (char)a5, a6);
        return;
      case 37:
        if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x20) != 0 )
          McTemplateK0jqq_EtwWriteTransfer(v19, (unsigned int)CacheError, a3, a2, a3, a4);
        return;
      case 38:
        if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x20) != 0 )
          McTemplateK0jqq_EtwWriteTransfer(v19, (unsigned int)VdtError, a3, a2, a3, a4);
        return;
      case 39:
        if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x20) != 0 )
          McTemplateK0jquxqq_EtwWriteTransfer(v19, 0x40000000u, a3, a2, a3, a4, (char)a5, a6, a7);
        return;
      case 40:
        if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
          McTemplateK0jqqqqqqqqtx_EtwWriteTransfer(
            a11,
            0x40000000u,
            a3,
            a2,
            a3,
            a4,
            (char)a5,
            a6,
            a7,
            a8,
            a9,
            a10,
            a11,
            a12);
        return;
      case 41:
        if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
          McTemplateK0jqqqqtx_EtwWriteTransfer((unsigned __int8)a7, 0x40000000u, a3, a2, a3, a4, (char)a5, a6, a7, a8);
        return;
      case 43:
        if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
          McTemplateK0jqqbr2_EtwWriteTransfer(v19, (unsigned int)WriteSst, a3, a2, a3, a4, (__int64)a5);
        return;
      case 44:
        if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x20) != 0 )
          McTemplateK0jq_EtwWriteTransfer(v19, WriteSstFailed, 0, a2, a3);
        return;
      case 45:
        if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
          McTemplateK0jqqbr2_EtwWriteTransfer(v19, (unsigned int)DistributeSst, a3, a2, a3, a4, (__int64)a5);
        return;
      case 46:
        if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
          McTemplateK0j_EtwWriteTransfer(v19, CacheReserveEnabled, a3, a2);
        return;
      case 47:
        if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
          McTemplateK0jxx_EtwWriteTransfer(v19, (unsigned int)CacheReserveDisabled, a3, a2, a3, a4);
        return;
      case 48:
        if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x20) != 0 )
          McTemplateK0jqxxx_EtwWriteTransfer(v19, 0x40000000u, a3, a2, a3, a4, (char)a5, a6);
        return;
      case 50:
        if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
          McTemplateK0jqqq_EtwWriteTransfer(v19, (unsigned int)ConfigToleranceUpdate, a3, a2, a3, a4, (char)a5);
        return;
      case 97:
        if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
          McTemplateK0jqqxjx_EtwWriteTransfer(v19, 0x40000000u, a3, a2, a3, a4, (char)a5, a6, a7);
        return;
      case 98:
        if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x20) != 0 )
          McTemplateK0jqqQR2XR2HR2_EtwWriteTransfer(v19, 0x40000000u, a3, a2, a3, a4, (__int64)a5, a6, a7);
        return;
      case 99:
        if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
          McTemplateK0jqJR1QR1XR1HR1_EtwWriteTransfer(v19, 0x40000000u, a3, a2, a3, a4, (__int64)a5, a6, a7);
        return;
      case 100:
        if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
          McTemplateK0jj_EtwWriteTransfer(v19, (unsigned int)PathRemoved, a3, a2, a3);
        return;
      case 101:
        if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
          McTemplateK0jj_EtwWriteTransfer(v19, (unsigned int)PathSynchronize, a3, a2, a3);
        return;
      case 102:
        if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x20) != 0 )
          McTemplateK0jjq_EtwWriteTransfer(v19, (unsigned int)PathSynchronizeFailed, a3, a2, a3);
        return;
      case 103:
        if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x20) != 0 )
          McTemplateK0jjq_EtwWriteTransfer(v19, (unsigned int)PathFailed, a3, a2, a3);
        return;
      case 104:
        if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x20) != 0 )
        {
          v33 = *(_QWORD *)(a2 + 56);
          v34 = *(_DWORD *)(a2 + 296);
          v35 = *(_DWORD *)(a2 + 300);
          v36 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
          McTemplateK0jqqxqq_EtwWriteTransfer(v38, v37, v39, v36, v35, v34, v33, a3, a4);
        }
        return;
      case 105:
        if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x20) != 0 )
        {
          v40 = *(_DWORD *)(a2 + 304);
          v41 = *(_QWORD *)(a2 + 56);
          v42 = *(_DWORD *)(a2 + 296);
          v43 = *(_DWORD *)(a2 + 300);
          v44 = (*(__int64 (**)(void))(*(_QWORD *)a2 + 16LL))();
          McTemplateK0jqqxqxq_EtwWriteTransfer(v46, v45, v47, v44, v43, v42, v41, a3, a4, v40);
        }
        return;
      default:
        return;
    }
  }
}

```

## disassembly

```asm
0x1400044d0  mov     [rsp-8+arg_0], ecx
0x1400044d4  mov     [rsp-8+arg_8], rdx
0x1400044d9  mov     [rsp-8+arg_10], r8
0x1400044de  mov     [rsp-8+arg_18], r9
0x1400044e3  push    rbp
0x1400044e4  push    rbx
0x1400044e5  push    rsi
0x1400044e6  push    rdi
0x1400044e7  push    r13
0x1400044e9  push    r14
0x1400044eb  lea     rbp, [rsp-98h]
0x1400044f3  sub     rsp, 198h
0x1400044fa  mov     rax, cs:__security_cookie
0x140004501  xor     rax, rsp
0x140004504  mov     [rbp+0C0h+var_50], rax
0x140004508  xor     r13d, r13d
0x14000450b  lea     r9, [rbp+0C0h+arg_8]
0x140004512  mov     qword ptr [rbp+0C0h+EventDescriptor.Id], r13
0x140004516  cmp     ecx, 3E8h
0x14000451c  ja      loc_140004831
0x140004522  jz      loc_1400047EC
0x140004528  add     ecx, 0FFFFFED2h; switch 209 cases
0x14000452e  cmp     ecx, 0D0h
0x140004534  ja      def_140004553; jumptable 0000000140004553 default case, cases 304-313,317-507
0x14000453a  lea     rdx, cs:140000000h
0x140004541  movzx   eax, ds:(byte_140073464 - 140000000h)[rdx+rcx]
0x140004549  mov     ecx, ds:(jpt_140004553 - 140000000h)[rdx+rax*4]
0x140004550  add     rcx, rdx
0x140004553  jmp     rcx; switch jump
0x140004559  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 1; jumptable 0000000140004553 case 303
0x140004560  jz      def_140004553; jumptable 0000000140004553 default case, cases 304-313,317-507
0x140004566  mov     rsi, [r9]
0x140004569  mov     rdi, [r9+8]
0x14000456d  mov     rbx, [r9+10h]
0x140004571  call    cs:__imp_IoGetActivityIdThread
0x140004578  nop     dword ptr [rax+rax+00h]
0x14000457d  mov     [rsp+1C0h+UserData], rbx
0x140004582  mov     r9, rsi
0x140004585  mov     r8, rax
0x140004588  mov     qword ptr [rsp+1C0h+UserDataCount], rdi
0x14000458d  call    McTemplateK0jjs_EtwWriteTransfer
0x140004592  jmp     def_140004553; jumptable 0000000140004553 default case, cases 304-313,317-507
0x140004597  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 1; jumptable 0000000140004553 case 302
0x14000459e  mov     rsi, [r9]
0x1400045a1  mov     edi, [r9+8]
0x1400045a5  lea     rbx, [rsi+10h]
0x1400045a9  jz      short loc_1400045C1
0x1400045ab  mov     r9, rbx
0x1400045ae  mov     [rsp+1C0h+UserDataCount], edi
0x1400045b2  xor     r8d, r8d
0x1400045b5  lea     rdx, SpaceConfigWriteFailure
0x1400045bc  call    McTemplateK0jq_EtwWriteTransfer
0x1400045c1  mov     eax, cs:dword_14007F050
0x1400045c7  cmp     eax, 5
0x1400045ca  jbe     def_140004553; jumptable 0000000140004553 default case, cases 304-313,317-507
0x1400045d0  mov     rdx, cs:qword_14007F068
0x1400045d7  mov     rcx, 400000000000h
0x1400045e1  mov     rax, cs:qword_14007F060
0x1400045e8  test    rcx, rax
0x1400045eb  jz      def_140004553; jumptable 0000000140004553 default case, cases 304-313,317-507
0x1400045f1  mov     rax, rdx
0x1400045f4  and     rax, rcx
0x1400045f7  cmp     rax, rdx
0x1400045fa  jnz     def_140004553; jumptable 0000000140004553 default case, cases 304-313,317-507
0x140004600  mov     [rbp+0C0h+EventDescriptor.Keyword], rcx
0x140004604  lea     rax, [rsp+1C0h+var_144]
0x140004609  mov     [rbp+0C0h+var_D0], rax
0x14000460d  lea     rcx, _TraceLoggingMetadata
0x140004614  movzx   eax, cs:word_140075345
0x14000461b  lea     rdx, [rbp+0C0h+EventDescriptor]; EventDescriptor
0x14000461f  mov     dword ptr [rbp+0C0h+EventDescriptor.Level], eax
0x140004622  xor     r9d, r9d; RelatedActivityId
0x140004625  mov     rax, cs:off_14007F058
0x14000462c  xor     r8d, r8d; ActivityId
0x14000462f  mov     [rbp+0C0h+var_110.Ptr], rax
0x140004633  mov     [rsp+1C0h+var_144], edi
0x140004637  mov     [rbp+0C0h+var_C8], 4
0x14000463f  mov     [rbp+0C0h+var_E0], rbx
0x140004643  mov     [rbp+0C0h+var_D8], 10h
0x14000464b  mov     [rbp+0C0h+var_F0], rsi
0x14000464f  mov     [rbp+0C0h+var_E8], 10h
0x140004657  mov     dword ptr [rbp+0C0h+EventDescriptor.Id], 0B000000h
0x14000465e  movzx   eax, word ptr [rax]
0x140004661  mov     [rbp+0C0h+var_110.Size], eax
0x140004664  lea     rax, byte_14007534F
0x14000466b  mov     [rbp+0C0h+var_100], rax
0x14000466f  lea     rax, _TraceLoggingMetadataEnd
0x140004676  sub     eax, ecx
0x140004678  mov     dword ptr [rbp+0C0h+var_110.0Ch], 2
0x14000467f  mov     [rbp+0C0h+var_F8], 41h ; 'A'
0x140004686  mov     [rbp+0C0h+var_F4], 1
0x14000468d  mov     dword ptr [rbp+0C0h+var_140], eax
0x140004690  mov     eax, dword ptr [rbp+0C0h+var_140]
0x140004693  mov     rcx, cs:RegHandle; RegHandle
0x14000469a  lea     rax, [rbp+0C0h+var_110]
0x14000469e  mov     [rsp+1C0h+UserData], rax; UserData
0x1400046a3  mov     [rsp+1C0h+UserDataCount], 5; UserDataCount
0x1400046ab  call    cs:__imp_EtwWriteTransfer
0x1400046b2  nop     dword ptr [rax+rax+00h]
0x1400046b7  jmp     def_140004553; jumptable 0000000140004553 default case, cases 304-313,317-507
0x1400046bc  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 4; jumptable 0000000140004553 case 314
0x1400046c3  jz      def_140004553; jumptable 0000000140004553 default case, cases 304-313,317-507
0x1400046c9  mov     eax, [r9+28h]
0x1400046cd  mov     dword ptr [rsp+1C0h+var_180], eax
0x1400046d1  mov     eax, [r9+20h]
0x1400046d5  mov     dword ptr [rsp+1C0h+var_188], eax
0x1400046d9  mov     rax, [r9+18h]
0x1400046dd  mov     [rsp+1C0h+var_190], rax
0x1400046e2  mov     rax, [r9+10h]
0x1400046e6  mov     [rsp+1C0h+UserData], rax
0x1400046eb  mov     rax, [r9+8]
0x1400046ef  mov     r9, [r9]
0x1400046f2  mov     qword ptr [rsp+1C0h+UserDataCount], rax
0x1400046f7  call    McTemplateK0jxxxqq_EtwWriteTransfer
0x1400046fc  jmp     def_140004553; jumptable 0000000140004553 default case, cases 304-313,317-507
0x140004701  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 1; jumptable 0000000140004553 case 315
0x140004708  jz      def_140004553; jumptable 0000000140004553 default case, cases 304-313,317-507
0x14000470e  mov     eax, [r9+20h]
0x140004712  mov     dword ptr [rsp+1C0h+var_188], eax
0x140004716  mov     eax, [r9+18h]
0x14000471a  mov     dword ptr [rsp+1C0h+var_190], eax
0x14000471e  mov     rax, [r9+10h]
0x140004722  mov     [rsp+1C0h+UserData], rax
0x140004727  mov     eax, [r9+8]
0x14000472b  mov     r9, [r9]
0x14000472e  mov     [rsp+1C0h+UserDataCount], eax
0x140004732  call    McTemplateK0jqxqq_EtwWriteTransfer
0x140004737  jmp     def_140004553; jumptable 0000000140004553 default case, cases 304-313,317-507
0x14000473c  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 10h; jumptable 0000000140004553 case 508
0x140004743  jz      def_140004553; jumptable 0000000140004553 default case, cases 304-313,317-507
0x140004749  mov     eax, [r9+8]
0x14000474d  lea     rdx, SpacesPdReadDriveHeaderFailure
0x140004754  mov     r9, [r9]
0x140004757  xor     r8d, r8d
0x14000475a  mov     [rsp+1C0h+UserDataCount], eax
0x14000475e  call    McTemplateK0jq_EtwWriteTransfer
0x140004763  jmp     def_140004553; jumptable 0000000140004553 default case, cases 304-313,317-507
0x140004768  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 10h; jumptable 0000000140004553 case 509
0x14000476f  jz      def_140004553; jumptable 0000000140004553 default case, cases 304-313,317-507
0x140004775  mov     eax, [r9+8]
0x140004779  lea     rdx, SpacesPdConfigLoadFailure
0x140004780  mov     r9, [r9]
0x140004783  xor     r8d, r8d
0x140004786  mov     [rsp+1C0h+UserDataCount], eax
0x14000478a  call    McTemplateK0jq_EtwWriteTransfer
0x14000478f  jmp     def_140004553; jumptable 0000000140004553 default case, cases 304-313,317-507
0x140004794  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 10h; jumptable 0000000140004553 case 510
0x14000479b  jz      def_140004553; jumptable 0000000140004553 default case, cases 304-313,317-507
0x1400047a1  mov     eax, [r9+8]
0x1400047a5  lea     rdx, SpacesPdDrtInitFailure
0x1400047ac  mov     r9, [r9]
0x1400047af  xor     r8d, r8d
0x1400047b2  mov     [rsp+1C0h+UserDataCount], eax
0x1400047b6  call    McTemplateK0jq_EtwWriteTransfer
0x1400047bb  jmp     def_140004553; jumptable 0000000140004553 default case, cases 304-313,317-507
0x1400047c0  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 1; jumptable 0000000140004553 case 316
0x1400047c7  jz      def_140004553; jumptable 0000000140004553 default case, cases 304-313,317-507
0x1400047cd  mov     eax, [r9+8]
0x1400047d1  lea     rdx, SpaceColumnUpdateFailed
0x1400047d8  mov     r9, [r9]
0x1400047db  xor     r8d, r8d
0x1400047de  mov     [rsp+1C0h+UserDataCount], eax
0x1400047e2  call    McTemplateK0jq_EtwWriteTransfer
0x1400047e7  jmp     def_140004553; jumptable 0000000140004553 default case, cases 304-313,317-507
0x1400047ec  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 20h
0x1400047f3  jz      def_140004553; jumptable 0000000140004553 default case, cases 304-313,317-507
0x1400047f9  mov     r14, [r9]
0x1400047fc  mov     rsi, [r9+8]
0x140004800  mov     edi, [r9+10h]
0x140004804  mov     ebx, [r9+18h]
0x140004808  call    cs:__imp_IoGetActivityIdThread
0x14000480f  nop     dword ptr [rax+rax+00h]
0x140004814  mov     dword ptr [rsp+1C0h+var_190], ebx
0x140004818  mov     r9, r14
0x14000481b  mov     r8, rax
0x14000481e  mov     dword ptr [rsp+1C0h+UserData], edi
0x140004822  mov     qword ptr [rsp+1C0h+UserDataCount], rsi
0x140004827  call    McTemplateK0jsqq_EtwWriteTransfer
0x14000482c  jmp     def_140004553; jumptable 0000000140004553 default case, cases 304-313,317-507
0x140004831  cmp     ecx, 643h
0x140004837  ja      loc_140005527
0x14000483d  jz      loc_1400054DB
0x140004843  add     ecx, 0FFFFFC15h; switch 106 cases
0x140004849  cmp     ecx, 69h
0x14000484c  ja      def_140004553; jumptable 0000000140004553 default case, cases 304-313,317-507
0x140004852  mov     [rsp+1C0h+var_30], r12
0x14000485a  lea     rdx, cs:140000000h
0x140004861  mov     [rsp+1C0h+var_38], r15
0x140004869  movzx   eax, ds:(byte_1400735BD - 140000000h)[rdx+rcx]
0x140004871  mov     ecx, ds:(jpt_14000487B - 140000000h)[rdx+rax*4]
0x140004878  add     rcx, rdx
0x14000487b  jmp     rcx; switch jump
0x140004881  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 40h; jumptable 000000014000487B case 1003
0x140004888  jz      loc_14000538E; jumptable 000000014000487B cases 1005-1012,1014-1018,1020,1027,1028,1030-1037,1045,1052,1054-1099
0x14000488e  mov     rsi, [r9]
0x140004891  mov     edi, [r9+8]
0x140004895  mov     rbx, [r9+10h]
0x140004899  call    cs:__imp_IoGetActivityIdThread
0x1400048a0  nop     dword ptr [rax+rax+00h]
0x1400048a5  mov     [rsp+1C0h+UserData], rbx
0x1400048aa  lea     rdx, SpaceTransactionStart
0x1400048b1  mov     r8, rax
0x1400048b4  mov     [rsp+1C0h+UserDataCount], edi
0x1400048b8  mov     r9, rsi
0x1400048bb  call    McTemplateK0jqx_EtwWriteTransfer
0x1400048c0  jmp     loc_14000538E; jumptable 000000014000487B cases 1005-1012,1014-1018,1020,1027,1028,1030-1037,1045,1052,1054-1099
0x1400048c5  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 40h; jumptable 000000014000487B case 1004
0x1400048cc  jz      loc_14000538E; jumptable 000000014000487B cases 1005-1012,1014-1018,1020,1027,1028,1030-1037,1045,1052,1054-1099
0x1400048d2  mov     r14, [r9]
0x1400048d5  mov     esi, [r9+8]
0x1400048d9  mov     edi, [r9+10h]
0x1400048dd  mov     rbx, [r9+18h]
0x1400048e1  call    cs:__imp_IoGetActivityIdThread
0x1400048e8  nop     dword ptr [rax+rax+00h]
0x1400048ed  mov     [rsp+1C0h+var_190], rbx
0x1400048f2  mov     r9, r14
0x1400048f5  mov     r8, rax
0x1400048f8  mov     dword ptr [rsp+1C0h+UserData], edi
0x1400048fc  mov     [rsp+1C0h+UserDataCount], esi
0x140004900  call    McTemplateK0jqqx_EtwWriteTransfer
0x140004905  jmp     loc_14000538E; jumptable 000000014000487B cases 1005-1012,1014-1018,1020,1027,1028,1030-1037,1045,1052,1054-1099
0x14000490a  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 20h; jumptable 000000014000487B case 1013
0x140004911  jz      loc_14000538E; jumptable 000000014000487B cases 1005-1012,1014-1018,1020,1027,1028,1030-1037,1045,1052,1054-1099
0x140004917  mov     eax, [r9+28h]
0x14000491b  mov     dword ptr [rsp+1C0h+var_180], eax
0x14000491f  mov     eax, [r9+20h]
0x140004923  mov     dword ptr [rsp+1C0h+var_188], eax
0x140004927  mov     eax, [r9+18h]
0x14000492b  mov     dword ptr [rsp+1C0h+var_190], eax
0x14000492f  mov     eax, [r9+10h]
0x140004933  mov     dword ptr [rsp+1C0h+UserData], eax
0x140004937  mov     rax, [r9+8]
0x14000493b  mov     r9, [r9]
0x14000493e  mov     qword ptr [rsp+1C0h+UserDataCount], rax
0x140004943  call    McTemplateK0jxqqqq_EtwWriteTransfer
0x140004948  jmp     loc_14000538E; jumptable 000000014000487B cases 1005-1012,1014-1018,1020,1027,1028,1030-1037,1045,1052,1054-1099
0x14000494d  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 40h; jumptable 000000014000487B case 1026
0x140004954  jz      loc_14000538E; jumptable 000000014000487B cases 1005-1012,1014-1018,1020,1027,1028,1030-1037,1045,1052,1054-1099
0x14000495a  mov     eax, [r9+18h]
0x14000495e  mov     dword ptr [rsp+1C0h+var_190], eax
0x140004962  movzx   eax, byte ptr [r9+10h]
0x140004967  mov     byte ptr [rsp+1C0h+UserData], al
0x14000496b  mov     eax, [r9+8]
0x14000496f  mov     r9, [r9]
0x140004972  mov     [rsp+1C0h+UserDataCount], eax
0x140004976  call    McTemplateK0jquq_EtwWriteTransfer
0x14000497b  jmp     loc_14000538E; jumptable 000000014000487B cases 1005-1012,1014-1018,1020,1027,1028,1030-1037,1045,1052,1054-1099
0x140004980  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 40h; jumptable 000000014000487B case 1019
0x140004987  jz      loc_14000538E; jumptable 000000014000487B cases 1005-1012,1014-1018,1020,1027,1028,1030-1037,1045,1052,1054-1099
0x14000498d  mov     eax, [r9+28h]
0x140004991  mov     dword ptr [rsp+1C0h+var_180], eax
0x140004995  mov     eax, [r9+20h]
0x140004999  mov     dword ptr [rsp+1C0h+var_188], eax
0x14000499d  mov     eax, [r9+18h]
0x1400049a1  mov     dword ptr [rsp+1C0h+var_190], eax
0x1400049a5  mov     eax, [r9+10h]
0x1400049a9  mov     dword ptr [rsp+1C0h+UserData], eax
0x1400049ad  mov     eax, [r9+8]
0x1400049b1  mov     r9, [r9]
0x1400049b4  mov     [rsp+1C0h+UserDataCount], eax
0x1400049b8  call    McTemplateK0jqqqqq_EtwWriteTransfer
0x1400049bd  jmp     loc_14000538E; jumptable 000000014000487B cases 1005-1012,1014-1018,1020,1027,1028,1030-1037,1045,1052,1054-1099
0x1400049c2  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 40h; jumptable 000000014000487B case 1038
0x1400049c9  jz      loc_14000538E; jumptable 000000014000487B cases 1005-1012,1014-1018,1020,1027,1028,1030-1037,1045,1052,1054-1099
0x1400049cf  mov     eax, [r9+48h]
0x1400049d3  mov     [rsp+1C0h+var_160], eax
0x1400049d7  mov     eax, [r9+40h]
0x1400049db  mov     dword ptr [rsp+1C0h+var_168], eax
0x1400049df  mov     rax, [r9+38h]
0x1400049e3  mov     [rsp+1C0h+var_170], rax
0x1400049e8  mov     eax, [r9+30h]
0x1400049ec  mov     dword ptr [rsp+1C0h+var_178], eax
0x1400049f0  mov     rax, [r9+28h]
0x1400049f4  mov     [rsp+1C0h+var_180], rax
0x1400049f9  mov     rax, [r9+20h]
0x1400049fd  mov     [rsp+1C0h+var_188], rax
0x140004a02  mov     rax, [r9+18h]
0x140004a06  mov     [rsp+1C0h+var_190], rax
0x140004a0b  mov     eax, [r9+10h]
0x140004a0f  mov     dword ptr [rsp+1C0h+UserData], eax
0x140004a13  mov     eax, [r9+8]
0x140004a17  mov     r9, [r9]
0x140004a1a  mov     [rsp+1C0h+UserDataCount], eax
0x140004a1e  call    McTemplateK0jqqxxxqxqq_EtwWriteTransfer
0x140004a23  jmp     loc_14000538E; jumptable 000000014000487B cases 1005-1012,1014-1018,1020,1027,1028,1030-1037,1045,1052,1054-1099
0x140004a28  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 20h; jumptable 000000014000487B case 1039
0x140004a2f  jz      loc_14000538E; jumptable 000000014000487B cases 1005-1012,1014-1018,1020,1027,1028,1030-1037,1045,1052,1054-1099
0x140004a35  mov     eax, [r9+20h]
0x140004a39  mov     dword ptr [rsp+1C0h+var_188], eax
0x140004a3d  mov     rax, [r9+18h]
0x140004a41  mov     [rsp+1C0h+var_190], rax
0x140004a46  movzx   eax, byte ptr [r9+10h]
0x140004a4b  mov     byte ptr [rsp+1C0h+UserData], al
0x140004a4f  mov     eax, [r9+8]
0x140004a53  mov     r9, [r9]
0x140004a56  mov     [rsp+1C0h+UserDataCount], eax
0x140004a5a  call    McTemplateK0jquxq_EtwWriteTransfer
0x140004a5f  jmp     loc_14000538E; jumptable 000000014000487B cases 1005-1012,1014-1018,1020,1027,1028,1030-1037,1045,1052,1054-1099
0x140004a64  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 20h; jumptable 000000014000487B case 1040
0x140004a6b  jz      loc_14000538E; jumptable 000000014000487B cases 1005-1012,1014-1018,1020,1027,1028,1030-1037,1045,1052,1054-1099
  ... truncated ...
```
