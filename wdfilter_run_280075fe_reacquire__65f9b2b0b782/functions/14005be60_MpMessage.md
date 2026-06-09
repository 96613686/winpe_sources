# MpMessage

- ea: `0x14005be60`
- end: `0x14005d2e8`
- name: `MpMessage`
- size: `5256`
- prototype: `NTSTATUS __stdcall(PVOID PortCookie, PVOID InputBuffer, ULONG InputBufferLength, PVOID OutputBuffer, ULONG OutputBufferLength, PULONG ReturnOutputBufferLength)`
- caller_count: `0`
- callee_count: `60`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update`

## callees

- `0x1400018a4`
- `0x1400034e0`
- `0x140003950`
- `0x140003d20`
- `0x140003e30`
- `0x1400049dc`
- `0x140004d24`
- `0x1400051bc`
- `0x1400062f0`
- `0x140007030`
- `0x14000a624`
- `0x14000a760`
- `0x14000a970`
- `0x14000aa0c`
- `0x14000b998`
- `0x140011890`
- `0x140011900`
- `0x140011bc0`
- `0x14002b000`
- `0x14002c108`
- `0x14002d158`
- `0x140030060`
- `0x14003a570`
- `0x14005a980`
- `0x14005b334`
- `0x14005b510`
- `0x14005be60`
- `0x14005d2f0`
- `0x14005db70`
- `0x14005dfd4`
- `0x14005e6d0`
- `0x14005ee44`
- `0x14006a5c8`
- `0x14006cec4`
- `0x14006ee20`
- `0x140071cb4`
- `0x140072464`
- `0x1400736f8`
- `0x140073af0`
- `0x140074c84`
- `0x140074eb0`
- `0x140074f80`
- `0x140075108`
- `0x140075e0c`
- `0x140076b78`
- `0x140077994`
- `0x140079118`
- `0x140079260`
- `0x140079328`
- `0x14007a254`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005ca22`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005ca22`
- `ntoskrnl!ProbeForRead` at `0x14005bf2f`
- `ntoskrnl!ProbeForRead` at `0x14005bf2f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ca16`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ca16`
- `ntoskrnl!ProbeForWrite` at `0x14005bf4b`
- `ntoskrnl!ProbeForWrite` at `0x14005bf4b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005c87d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005c87d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005c868`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005c868`
- `ntoskrnl!KeInitializeEvent` at `0x14005c97a`
- `ntoskrnl!KeInitializeEvent` at `0x14005c97a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c14b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c48c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c14b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c48c`
- `ntoskrnl!KeInitializeSemaphore` at `0x14005c8fc`
- `ntoskrnl!KeInitializeSemaphore` at `0x14005c91e`
- `ntoskrnl!KeInitializeSemaphore` at `0x14005c940`
- `ntoskrnl!KeInitializeSemaphore` at `0x14005c8fc`
- `ntoskrnl!KeInitializeSemaphore` at `0x14005c91e`
- `ntoskrnl!KeInitializeSemaphore` at `0x14005c940`
- `ntoskrnl!ExQueryDepthSList` at `0x14005c0cf`
- `ntoskrnl!ExQueryDepthSList` at `0x14005c2b8`
- `ntoskrnl!ExQueryDepthSList` at `0x14005c0cf`
- `ntoskrnl!ExQueryDepthSList` at `0x14005c2b8`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005c0ed`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005c2d6`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005c0ed`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14005c2d6`

## pseudocode

```c
__int64 __fastcall MpMessage(
        PVOID PortCookie,
        PVOID InputBuffer,
        ULONG InputBufferLength,
        PVOID OutputBuffer,
        ULONG OutputBufferLength,
        PULONG ReturnOutputBufferLength)
{
  size_t v7; // rdi
  NTSTATUS Name; // r14d
  unsigned __int8 *PoolWithQuotaTag; // rsi
  __int64 v11; // r15
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rcx
  ULONG v15; // r12d
  int v16; // r8d
  NTSTATUS EaFile; // eax
  ULONG_PTR v18; // rbx
  USHORT v19; // di
  USHORT DepthSList; // ax
  int v22; // ecx
  int v23; // ecx
  unsigned __int8 *v24; // rax
  ULONG_PTR v25; // rdi
  USHORT v26; // bx
  USHORT v27; // ax
  PDEVICE_OBJECT v28; // rcx
  __int64 v29; // rdx
  PVOID v30; // rax
  unsigned int v31; // ebx
  __int64 v32; // rdx
  int v33; // ecx
  ULONG_PTR v34; // rbx
  LONG v35; // r9d
  int v36; // eax
  LONG v37; // edx
  ULONG_PTR v38; // rcx
  __int64 v39; // r9
  unsigned __int8 v40; // cl
  _BYTE *v41; // rax
  unsigned __int8 v42; // cl
  ULONG_PTR v43; // rax
  bool v44; // zf
  int v45; // ecx
  unsigned int v46; // edx
  __int64 v47; // r9
  __int64 v48; // rdx
  unsigned int v49; // edx
  unsigned __int8 v50; // cl
  unsigned __int8 v51; // dl
  _BYTE *v52; // rax
  __int64 v53; // r9
  __int64 v54; // rax
  unsigned int v55; // r9d
  __int64 v56; // rcx
  int v57; // r10d
  unsigned int v58; // r10d
  unsigned int v59; // eax
  int v60; // [rsp+20h] [rbp-88h]
  int v61; // [rsp+28h] [rbp-80h]
  unsigned __int8 v62; // [rsp+40h] [rbp-68h]
  LONG Limit; // [rsp+44h] [rbp-64h]
  LONG Count; // [rsp+48h] [rbp-60h] BYREF
  __int64 v65; // [rsp+50h] [rbp-58h] BYREF
  unsigned __int8 *v66; // [rsp+58h] [rbp-50h]
  __int64 v67; // [rsp+60h] [rbp-48h]

  v7 = InputBufferLength;
  Name = 0;
  PoolWithQuotaTag = 0;
  v11 = 0;
  *ReturnOutputBufferLength = 0;
  if ( InputBufferLength < 0x10 || OutputBufferLength < 8 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        52,
        WPP_1a3d4887b9bd3cba22fd3e00f3d9a078_Traceguids,
        KeGetCurrentThread());
    goto LABEL_27;
  }
  if ( !InputBuffer || !OutputBuffer )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        53,
        WPP_1a3d4887b9bd3cba22fd3e00f3d9a078_Traceguids,
        KeGetCurrentThread());
    Name = -1073741811;
    goto LABEL_28;
  }
  if ( InputBufferLength <= 0x80 )
  {
    v24 = (unsigned __int8 *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)(MpData + 1664));
    PoolWithQuotaTag = v24;
    v66 = v24;
    if ( v24 )
      memset(v24, 0, v7);
  }
  else
  {
    _mm_lfence();
    PoolWithQuotaTag = (unsigned __int8 *)MpAllocatePoolWithQuotaTag(PortCookie, InputBufferLength, 1919307853);
    v66 = PoolWithQuotaTag;
  }
  if ( !PoolWithQuotaTag )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_86;
    v32 = 54;
    goto LABEL_85;
  }
  if ( OutputBufferLength <= 0x210 )
  {
    v30 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)(MpData + 1792));
    v11 = (__int64)v30;
    v67 = (__int64)v30;
    if ( v30 )
      memset(v30, 0, OutputBufferLength);
  }
  else
  {
    _mm_lfence();
    v11 = MpAllocatePoolWithQuotaTag(v12, OutputBufferLength, 1919307853);
    v67 = v11;
  }
  if ( !v11 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_86;
    v32 = 55;
LABEL_85:
    WPP_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v32,
      WPP_1a3d4887b9bd3cba22fd3e00f3d9a078_Traceguids,
      KeGetCurrentThread());
LABEL_86:
    Name = -1073741670;
    goto LABEL_28;
  }
  _mm_lfence();
  ProbeForRead(InputBuffer, v7, 1u);
  ProbeForWrite(OutputBuffer, OutputBufferLength, 1u);
  memmove(PoolWithQuotaTag, InputBuffer, v7);
  v13 = *((_DWORD *)PoolWithQuotaTag + 2);
  if ( v13 != 1 )
  {
    _mm_lfence();
    v23 = *PoolWithQuotaTag;
    if ( (_BYTE)v23 != 0xA5 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        WPP_SF_qdddd(
          WPP_GLOBAL_Control->AttachedDevice,
          57,
          WPP_1a3d4887b9bd3cba22fd3e00f3d9a078_Traceguids,
          KeGetCurrentThread(),
          v23,
          PoolWithQuotaTag[1],
          165,
          1);
      }
      Name = -1073741735;
      goto LABEL_28;
    }
  }
  _mm_lfence();
  if ( v13 != 1 )
  {
    _mm_lfence();
    v22 = PoolWithQuotaTag[1];
    if ( (_BYTE)v22 != 1
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
    {
      _mm_lfence();
      WPP_SF_qdddd(
        WPP_GLOBAL_Control->AttachedDevice,
        58,
        WPP_1a3d4887b9bd3cba22fd3e00f3d9a078_Traceguids,
        KeGetCurrentThread(),
        *PoolWithQuotaTag,
        v22,
        165,
        1);
    }
  }
  v14 = *((unsigned int *)PoolWithQuotaTag + 2);
  if ( (unsigned int)(v14 - 1) > 0x3F )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        59,
        WPP_1a3d4887b9bd3cba22fd3e00f3d9a078_Traceguids,
        KeGetCurrentThread(),
        v14);
    Name = -1073741808;
    goto LABEL_28;
  }
  _mm_lfence();
  if ( *((_DWORD *)PoolWithQuotaTag + 1) != (_DWORD)v7 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_27;
    v29 = 60;
    v61 = v7;
    v60 = *((_DWORD *)PoolWithQuotaTag + 1);
    goto LABEL_65;
  }
  _mm_lfence();
  if ( (unsigned int)v7 < (unsigned __int16)FunctionInputBufferLength[*((int *)PoolWithQuotaTag + 2)] )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_27;
    v29 = 61;
    v61 = *((_DWORD *)PoolWithQuotaTag + 2);
    v60 = v7;
LABEL_65:
    _mm_lfence();
    WPP_SF_qDD(
      WPP_GLOBAL_Control->AttachedDevice,
      v29,
      WPP_1a3d4887b9bd3cba22fd3e00f3d9a078_Traceguids,
      KeGetCurrentThread(),
      v60,
      v61);
LABEL_27:
    Name = -1073741306;
LABEL_28:
    v15 = OutputBufferLength;
    goto LABEL_29;
  }
  _mm_lfence();
  v15 = OutputBufferLength;
  if ( OutputBufferLength >= (unsigned __int16)FunctionMinimumOutputBufferLength[*((int *)PoolWithQuotaTag + 2)] )
  {
    if ( (_DWORD)v14 == 3 || (_DWORD)v14 == 6 )
    {
      _mm_lfence();
      Name = MpQueryName(PoolWithQuotaTag, OutputBuffer, OutputBufferLength, ReturnOutputBufferLength);
      goto LABEL_29;
    }
    _mm_lfence();
    if ( (_DWORD)v14 == 12 )
    {
      Name = MpQueryDosName(PoolWithQuotaTag, OutputBuffer, OutputBufferLength, ReturnOutputBufferLength);
      goto LABEL_29;
    }
    if ( (_DWORD)v14 == 24 )
    {
      Name = MpQueryRuntimeDrivers(PoolWithQuotaTag, v11, OutputBuffer, OutputBufferLength, ReturnOutputBufferLength);
      goto LABEL_29;
    }
    *(_WORD *)v11 = 421;
    *(_DWORD *)(v11 + 4) = (unsigned __int16)FunctionMinimumOutputBufferLength[*((int *)PoolWithQuotaTag + 2)];
    v16 = *((_DWORD *)PoolWithQuotaTag + 2);
    if ( v16 == 18 )
    {
      _mm_lfence();
      EaFile = MpQueryEaFile(PoolWithQuotaTag, v11, OutputBufferLength);
    }
    else
    {
      if ( v16 != 20 )
      {
        switch ( v16 )
        {
          case 1:
            *(_WORD *)(v11 + 8) = 421;
            goto LABEL_24;
          case 2:
            _mm_lfence();
            EaFile = MpCreateSection((__int64)PoolWithQuotaTag, (union _LARGE_INTEGER *)v11);
            goto LABEL_23;
          case 4:
            MpPurgeCache();
            goto LABEL_24;
          case 5:
            _mm_lfence();
            EaFile = MpQueryStatistics(v11);
            goto LABEL_23;
          case 7:
            _mm_lfence();
            EaFile = MpSetProcessExclusions((unsigned int)v7, PoolWithQuotaTag);
            goto LABEL_23;
          case 8:
            _mm_lfence();
            EaFile = MpSetVolumeExclusions((unsigned int)v7, PoolWithQuotaTag);
            goto LABEL_23;
          case 9:
            *(_BYTE *)(v11 + 8) = *(_BYTE *)(MpData + 208);
            goto LABEL_24;
          case 10:
            _mm_lfence();
            EaFile = MpRegUpdateData((unsigned int)v7, PoolWithQuotaTag);
            goto LABEL_23;
          case 11:
            _mm_lfence();
            MpSetMonitorFlags(PoolWithQuotaTag[16], *((unsigned int *)PoolWithQuotaTag + 5));
            goto LABEL_24;
          case 13:
            _mm_lfence();
            EaFile = MpSetFileTimeouts(*((unsigned int *)PoolWithQuotaTag + 4), *((unsigned int *)PoolWithQuotaTag + 5));
            goto LABEL_23;
          case 14:
            v33 = *((_DWORD *)PoolWithQuotaTag + 4);
            if ( v33 && (unsigned int)(v33 - 1) > 1 )
              v33 = 0;
            *(_DWORD *)(MpData + 2440) = v33;
            Name = 0;
            goto LABEL_57;
          case 15:
            *(_DWORD *)(MpData + 2444) = PoolWithQuotaTag[16];
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                63,
                WPP_1a3d4887b9bd3cba22fd3e00f3d9a078_Traceguids,
                *(unsigned int *)(MpData + 2444));
            }
            goto LABEL_56;
          case 16:
            *(_BYTE *)(MpData + 2448) = PoolWithQuotaTag[16];
            Name = 0;
            goto LABEL_57;
          case 17:
            _mm_lfence();
            EaFile = MpSetDocOpenData((unsigned int)v7, PoolWithQuotaTag);
            goto LABEL_23;
          case 19:
            _mm_lfence();
            EaFile = MpQueryFileUsn(PoolWithQuotaTag, v11);
            goto LABEL_23;
          case 21:
            _mm_lfence();
            EaFile = MpRegisterThreadBoost(PoolWithQuotaTag);
            goto LABEL_23;
          case 22:
            v34 = MpData;
            KeEnterCriticalRegion();
            ExAcquireResourceExclusiveLite((PERESOURCE)(v34 + 752), 1u);
            if ( *(_DWORD *)(MpData + 444) )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 65, WPP_1a3d4887b9bd3cba22fd3e00f3d9a078_Traceguids);
              }
            }
            else
            {
              _mm_lfence();
              v35 = *((_DWORD *)PoolWithQuotaTag + 4) / 2;
              v36 = *((_DWORD *)PoolWithQuotaTag + 4) / 5;
              v37 = 1;
              if ( *((_DWORD *)PoolWithQuotaTag + 4) != 1 )
                v37 = *((_DWORD *)PoolWithQuotaTag + 4) - 1;
              LODWORD(v65) = v37;
              if ( !v35 )
                v35 = 1;
              Count = v35;
              if ( !v36 )
                v36 = 1;
              Limit = v36;
              KeInitializeSemaphore((PRKSEMAPHORE)(MpData + 448), v37, v37);
              KeInitializeSemaphore((PRKSEMAPHORE)(MpData + 480), Count, Count);
              KeInitializeSemaphore((PRKSEMAPHORE)(MpData + 512), Limit, Limit);
              v38 = MpData;
              *(_DWORD *)(MpData + 3952) = 1;
              *(_QWORD *)(v38 + 3960) = 0;
              *(_DWORD *)(v38 + 3968) = 0;
              KeInitializeEvent((PRKEVENT)(v38 + 3976), SynchronizationEvent, 0);
              *(_DWORD *)(MpData + 444) = 1;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
              {
                WPP_SF_DDD(
                  WPP_GLOBAL_Control->AttachedDevice,
                  64,
                  WPP_1a3d4887b9bd3cba22fd3e00f3d9a078_Traceguids,
                  (unsigned int)v65,
                  Count,
                  Limit);
              }
            }
            ExReleaseResourceLite((PERESOURCE)(MpData + 752));
            KeLeaveCriticalRegion();
            v39 = *((unsigned int *)PoolWithQuotaTag + 4);
            *(_DWORD *)(MpData + 440) = v39;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 66, WPP_1a3d4887b9bd3cba22fd3e00f3d9a078_Traceguids, v39);
            }
            goto LABEL_24;
          case 23:
            _mm_lfence();
            EaFile = MpQueryTrustedProcesses(v14, v11);
            goto LABEL_23;
          case 25:
            _mm_lfence();
            EaFile = MpSetProcessInfoFromRequest(PoolWithQuotaTag);
            goto LABEL_23;
          case 26:
            _mm_lfence();
            EaFile = MpRegisterFriendlyProcess(
                       *((_QWORD *)PoolWithQuotaTag + 2),
                       *((unsigned int *)PoolWithQuotaTag + 6));
            goto LABEL_23;
          case 27:
            _mm_lfence();
            EaFile = MpWriteBootSector(PoolWithQuotaTag);
            goto LABEL_23;
          case 28:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                67,
                WPP_1a3d4887b9bd3cba22fd3e00f3d9a078_Traceguids,
                *(unsigned int *)(MpData + 3256));
            }
            *(_DWORD *)(v11 + 8) = *(_DWORD *)(MpData + 3256);
            *(_DWORD *)(MpData + 3256) = 0;
            Name = 0;
            goto LABEL_57;
          case 29:
            _mm_lfence();
            EaFile = MpFgUpdateUserData((unsigned int)v7, PoolWithQuotaTag);
            goto LABEL_23;
          case 30:
            _mm_lfence();
            EaFile = MpFgUpdateDispatchConfig(v14, PoolWithQuotaTag);
            goto LABEL_23;
          case 31:
            _mm_lfence();
            EaFile = MpUpdateSyncMonitorConfig(v14, PoolWithQuotaTag);
            goto LABEL_23;
          case 32:
            _mm_lfence();
            EaFile = MpUpdateDirectoryMonitorConfig(v14, PoolWithQuotaTag);
            goto LABEL_23;
          case 33:
            v40 = PoolWithQuotaTag[16];
            v41 = MpDlpData;
            if ( MpDlpData )
            {
              *((_BYTE *)MpDlpData + 32) = v40;
              if ( v40 )
                v41[269] = 0;
              MpDlpInitializeSystemFolders();
              Name = 0;
            }
            else
            {
              Name = -1073741595;
            }
            goto LABEL_24;
          case 34:
            _mm_lfence();
            MpTraceLogTrustlabelHardeningFlags(
              *(unsigned int *)(MpData + 3912),
              *((unsigned int *)PoolWithQuotaTag + 4));
            *(_DWORD *)(MpData + 3912) = *((_DWORD *)PoolWithQuotaTag + 4);
            goto LABEL_24;
          case 35:
            v45 = *((_DWORD *)PoolWithQuotaTag + 4);
            *(_DWORD *)(MpData + 3928) = v45;
            v43 = MpData;
            if ( *(_BYTE *)(MpData + 3932) )
              goto LABEL_24;
            v44 = v45 == 1;
            goto LABEL_151;
          case 36:
            v42 = PoolWithQuotaTag[16];
            *(_BYTE *)(MpData + 3932) = v42;
            v43 = MpData;
            if ( v42 )
            {
              *(_QWORD *)(*(_QWORD *)(MpData + 8) + 104LL) = *(_QWORD *)(MpData + 3920);
            }
            else
            {
              v44 = *(_DWORD *)(MpData + 3928) == 1;
LABEL_151:
              if ( v44 )
                *(_QWORD *)(*(_QWORD *)(v43 + 8) + 104LL) = 0;
              else
                *(_QWORD *)(*(_QWORD *)(v43 + 8) + 104LL) = *(_QWORD *)(v43 + 3920);
            }
            goto LABEL_24;
          case 37:
            _mm_lfence();
            EaFile = MpSetProcessTaintInfo(PoolWithQuotaTag + 16);
            goto LABEL_23;
          case 38:
            v46 = PoolWithQuotaTag[16];
            *(_BYTE *)(MpData + 4008) = v46;
            v28 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
            {
              goto LABEL_56;
            }
            v47 = v46;
            v48 = 68;
            goto LABEL_159;
          case 39:
            _mm_lfence();
            EaFile = MpDlpSetEnlightenedAppMarker(PoolWithQuotaTag, (unsigned int)v7);
            goto LABEL_23;
          case 40:
            v49 = PoolWithQuotaTag[16];
            *(_BYTE *)(MpData + 4024) = v49;
            v28 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
            {
              goto LABEL_56;
            }
            v47 = v49;
            v48 = 69;
            goto LABEL_159;
          case 41:
            MpResetRunningProcessesHardeningExclusions();
            goto LABEL_24;
          case 42:
            *(_BYTE *)(MpData + 4040) = PoolWithQuotaTag[16] == 1
                                     && *(_QWORD *)(MpData + 176)
                                     && *(_QWORD *)(MpData + 184);
            *(_BYTE *)(v11 + 8) = *(_BYTE *)(MpData + 4040);
            v28 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
            {
              goto LABEL_56;
            }
            v47 = *(unsigned __int8 *)(MpData + 4040);
            v48 = 70;
LABEL_159:
            WPP_SF_d(v28->AttachedDevice, v48, WPP_1a3d4887b9bd3cba22fd3e00f3d9a078_Traceguids, v47);
            Name = 0;
            goto LABEL_57;
          case 43:
            MpLogFilterData();
            goto LABEL_24;
          case 44:
            if ( MpDlpData )
            {
              *((_BYTE *)MpDlpData + 240) = PoolWithQuotaTag[16];
              Name = 0;
            }
            else
            {
              Name = -1073741595;
            }
            goto LABEL_24;
          case 45:
            _mm_lfence();
            EaFile = MpDlpSetNetworkEnforcementState(PoolWithQuotaTag[16]);
            goto LABEL_23;
          case 46:
            _mm_lfence();
            EaFile = MpSetTrustedInstallerHardeningExcludeFlags(*((unsigned int *)PoolWithQuotaTag + 4));
            goto LABEL_23;
          case 47:
            *(_BYTE *)(MpData + 4048) = PoolWithQuotaTag[16] != 0;
            goto LABEL_56;
          case 48:
            *(_BYTE *)(MpData + 4049) = PoolWithQuotaTag[16] != 0;
            goto LABEL_56;
          case 49:
            _mm_lfence();
            EaFile = MpSetEfsHardeningFlags(*((unsigned int *)PoolWithQuotaTag + 4));
            goto LABEL_23;
          case 50:
            _mm_lfence();
            v31 = *((_DWORD *)PoolWithQuotaTag + 4);
            MpTraceLogPageFileHardeningChanged((unsigned int)dword_140026A20, v31);
            dword_140026A20 = v31;
            EaFile = MpSavePreventPagingFileAbuseConfig();
            goto LABEL_23;
          case 51:
            _mm_lfence();
            MpSetDevVolumeNumber(*((unsigned int *)PoolWithQuotaTag + 4));
            goto LABEL_24;
          case 52:
            v57 = *((_DWORD *)PoolWithQuotaTag + 5);
            _mm_lfence();
            if ( !v57 )
            {
              EaFile = MpFsHardeningSetServiceHardeningItems(0, *((unsigned int *)PoolWithQuotaTag + 4));
              goto LABEL_23;
            }
            Count = 0;
            Name = RtlULongSub(*((_DWORD *)PoolWithQuotaTag + 1), 0x18u, (ULONG *)&Count);
            if ( Name >= 0 )
            {
              if ( Count >= v58 )
              {
                v59 = *((_DWORD *)PoolWithQuotaTag + 6);
                if ( v58 == v59 && v59 >= 0x10 )
                {
                  _mm_lfence();
                  EaFile = MpFsHardeningSetServiceHardeningItems(
                             PoolWithQuotaTag + 24,
                             *((unsigned int *)PoolWithQuotaTag + 4));
                  goto LABEL_23;
                }
              }
              else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                     && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
              {
                _mm_lfence();
                WPP_SF_dd(
                  WPP_GLOBAL_Control->AttachedDevice,
                  72,
                  WPP_1a3d4887b9bd3cba22fd3e00f3d9a078_Traceguids,
                  v58,
                  Count);
              }
              Name = -1073741811;
              goto LABEL_29;
            }
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              _mm_lfence();
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                71,
                WPP_1a3d4887b9bd3cba22fd3e00f3d9a078_Traceguids,
                (unsigned int)Name);
            }
            goto LABEL_24;
          case 53:
            *(_BYTE *)(MpData + 4056) = PoolWithQuotaTag[16] != 0;
            goto LABEL_56;
          case 54:
            *(_BYTE *)(v11 + 8) = (*(_DWORD *)(MpData + 868) & 0x2000) == 0;
            *(_DWORD *)(v11 + 12) = *(_DWORD *)(MpData + 4060);
            goto LABEL_56;
          case 55:
            MpTerminateActiveConnections();
LABEL_56:
            Name = 0;
            goto LABEL_57;
          case 56:
            _mm_lfence();
            EaFile = MpFcKernelUpdateFeatureControlsFromRequest(PoolWithQuotaTag);
            goto LABEL_23;
          case 57:
            if ( *(int *)(MpData + 868) < 0 )
            {
              *((_BYTE *)MpDlpData + 264) = PoolWithQuotaTag[16];
              goto LABEL_24;
            }
            Name = -1073741790;
            goto LABEL_29;
          case 58:
            v50 = PoolWithQuotaTag[18];
            v51 = PoolWithQuotaTag[17];
            v52 = MpDlpData;
            if ( MpDlpData )
            {
              *((_BYTE *)MpDlpData + 265) = PoolWithQuotaTag[16];
              v52[267] = v51;
              v52[268] = v50;
              Name = 0;
            }
            else
            {
              Name = -1073741595;
            }
            goto LABEL_24;
          case 59:
            if ( MpDlpData )
            {
              *((_DWORD *)MpDlpData + 68) = *((_DWORD *)PoolWithQuotaTag + 4);
              Name = 0;
            }
            else
            {
              Name = -1073741595;
            }
            goto LABEL_24;
          case 60:
            if ( MpDlpData )
            {
              *((_DWORD *)MpDlpData + 74) = *((_DWORD *)PoolWithQuotaTag + 4);
              Name = 0;
            }
            else
            {
              Name = -1073741595;
            }
            goto LABEL_24;
          case 61:
            v62 = PoolWithQuotaTag[16];
            if ( PoolWithQuotaTag == (unsigned __int8 *)-20LL )
            {
              Name = -1073741811;
              goto LABEL_24;
            }
            _mm_lfence();
            v53 = *((unsigned int *)PoolWithQuotaTag + 5);
            if ( !(_DWORD)v53 || (_DWORD)v53 == 4 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
              {
                WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 186, WPP_4c1363a434f0368aee73563b7bc19017_Traceguids, v53);
              }
            }
            else
            {
              _mm_lfence();
              v65 = 0;
              v54 = MpFileTimeToUlong64(*((_QWORD *)PoolWithQuotaTag + 3));
              Name = MpGetProcessContextByIdAndCreationTime(v55, v54, &v65);
              if ( Name < 0 || (v56 = v65) == 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    187,
                    WPP_4c1363a434f0368aee73563b7bc19017_Traceguids,
                    (unsigned int)Name);
                }
LABEL_24:
                if ( Name >= 0 )
                {
LABEL_57:
                  _mm_lfence();
                  memmove(OutputBuffer, (const void *)v11, *(unsigned int *)(v11 + 4));
                  *ReturnOutputBufferLength = *(_DWORD *)(v11 + 4);
                }
                goto LABEL_29;
              }
              *(_BYTE *)(v65 + 232) = v62;
              MpReleaseProcessContext(v56);
            }
            Name = 0;
            goto LABEL_24;
          case 62:
            if ( MpDlpData )
            {
              *((_BYTE *)MpDlpData + 266) = PoolWithQuotaTag[16];
              Name = 0;
            }
            else
            {
              Name = -1073741595;
            }
            goto LABEL_24;
          case 63:
            _mm_lfence();
            EaFile = MpDlpSetTestProcessInformation(PoolWithQuotaTag + 16, PoolWithQuotaTag + 28);
            goto LABEL_23;
          case 64:
            _mm_lfence();
            EaFile = MpWriteKernelEa(PoolWithQuotaTag);
            goto LABEL_23;
          default:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              WPP_SF_qD(
                WPP_GLOBAL_Control->AttachedDevice,
                73,
                WPP_1a3d4887b9bd3cba22fd3e00f3d9a078_Traceguids,
                KeGetCurrentThread(),
                v16);
            }
            Name = -1073741808;
            goto LABEL_24;
        }
      }
      _mm_lfence();
      EaFile = MpQueryMotwAds(PoolWithQuotaTag, v11);
    }
LABEL_23:
    Name = EaFile;
    goto LABEL_24;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    _mm_lfence();
    WPP_SF_qDD(
      WPP_GLOBAL_Control->AttachedDevice,
      62,
      WPP_1a3d4887b9bd3cba22fd3e00f3d9a078_Traceguids,
      KeGetCurrentThread(),
      OutputBufferLength,
      v14);
  }
  Name = -1073741789;
LABEL_29:
  if ( PoolWithQuotaTag )
  {
    if ( (unsigned int)v7 > 0x80 )
    {
      _mm_lfence();
      ExFreePoolWithTag(PoolWithQuotaTag, 0x7266504Du);
    }
    else
    {
      v18 = MpData + 1664;
      ++*(_DWORD *)(MpData + 1692);
      v19 = *(_WORD *)(v18 + 16);
      DepthSList = ExQueryDepthSList((PSLIST_HEADER)v18);
      _mm_lfence();
      if ( DepthSList >= v19 )
      {
        ++*(_DWORD *)(v18 + 32);
        (*(void (__fastcall **)(unsigned __int8 *))(v18 + 56))(PoolWithQuotaTag);
      }
      else
      {
        ExpInterlockedPushEntrySList((PSLIST_HEADER)v18, (PSLIST_ENTRY)PoolWithQuotaTag);
      }
    }
  }
  if ( v11 )
  {
    if ( v15 <= 0x210 )
    {
      v25 = MpData + 1792;
      ++*(_DWORD *)(MpData + 1820);
      v26 = *(_WORD *)(v25 + 16);
      v27 = ExQueryDepthSList((PSLIST_HEADER)v25);
      _mm_lfence();
      if ( v27 >= v26 )
      {
        ++*(_DWORD *)(v25 + 32);
        (*(void (__fastcall **)(__int64))(v25 + 56))(v11);
      }
      else
      {
        ExpInterlockedPushEntrySList((PSLIST_HEADER)v25, (PSLIST_ENTRY)v11);
      }
    }
    else
    {
      _mm_lfence();
      ExFreePoolWithTag((PVOID)v11, 0x7266504Du);
    }
  }
  return (unsigned int)Name;
}

```

## disassembly

```asm
0x14005be60  mov     [rsp+arg_18], r9
0x14005be65  mov     [rsp+arg_10], r8d
0x14005be6a  mov     [rsp+arg_8], rdx
0x14005be6f  push    rbx
0x14005be70  push    rsi
0x14005be71  push    rdi
0x14005be72  push    r12
0x14005be74  push    r13
0x14005be76  push    r14
0x14005be78  push    r15
0x14005be7a  sub     rsp, 70h
0x14005be7e  mov     r13, r9
0x14005be81  mov     edi, r8d
0x14005be84  mov     r12, rdx
0x14005be87  xor     r14d, r14d
0x14005be8a  xor     esi, esi
0x14005be8c  xor     r15d, r15d
0x14005be8f  mov     rax, [rsp+0A8h+ReturnOutputBufferLength]
0x14005be97  mov     [rax], esi
0x14005be99  cmp     r8d, 10h
0x14005be9d  jb      loc_14005C081
0x14005bea3  mov     ebx, dword ptr [rsp+0A8h+Length]
0x14005beaa  cmp     ebx, 8
0x14005bead  jb      loc_14005C081
0x14005beb3  test    rdx, rdx
0x14005beb6  jz      loc_14005D166
0x14005bebc  test    r9, r9
0x14005bebf  jz      loc_14005D166
0x14005bec5  cmp     edi, 80h
0x14005becb  jbe     loc_14005C24D
0x14005bed1  lfence
0x14005bed4  mov     edx, edi
0x14005bed6  mov     r8d, 7266504Dh
0x14005bedc  call    MpAllocatePoolWithQuotaTag
0x14005bee1  mov     rsi, rax
0x14005bee4  mov     [rsp+0A8h+var_50], rax
0x14005bee9  test    rsi, rsi
0x14005beec  jz      loc_14005C5C7
0x14005bef2  cmp     ebx, 210h
0x14005bef8  jbe     loc_14005C44B
0x14005befe  lfence
0x14005bf01  mov     rdx, rbx
0x14005bf04  mov     r8d, 7266504Dh
0x14005bf0a  call    MpAllocatePoolWithQuotaTag
0x14005bf0f  mov     r15, rax
0x14005bf12  mov     [rsp+0A8h+var_48], rax
0x14005bf17  test    r15, r15
0x14005bf1a  jz      loc_14005C618
0x14005bf20  lfence
0x14005bf23  mov     r8d, 1; Alignment
0x14005bf29  mov     rdx, rdi; Length
0x14005bf2c  mov     rcx, r12; Address
0x14005bf2f  call    cs:__imp_ProbeForRead
0x14005bf36  nop     dword ptr [rax+rax+00h]
0x14005bf3b  mov     edx, dword ptr [rsp+0A8h+Length]; Length
0x14005bf42  mov     r8d, 1; Alignment
0x14005bf48  mov     rcx, r13; Address
0x14005bf4b  call    cs:__imp_ProbeForWrite
0x14005bf52  nop     dword ptr [rax+rax+00h]
0x14005bf57  mov     r8, rdi; Size
0x14005bf5a  mov     rdx, r12; Src
0x14005bf5d  mov     rcx, rsi; void *
0x14005bf60  call    memmove
0x14005bf65  jmp     short loc_14005BF8B
0x14005bf67  mov     r14d, eax
0x14005bf6a  mov     r13, [rsp+0A8h+arg_18]
0x14005bf72  mov     edi, [rsp+0A8h+arg_10]
0x14005bf79  mov     r12, [rsp+0A8h+arg_8]
0x14005bf81  mov     rsi, [rsp+0A8h+var_50]
0x14005bf86  mov     r15, [rsp+0A8h+var_48]
0x14005bf8b  test    r14d, r14d
0x14005bf8e  js      loc_14005C634
0x14005bf94  mov     eax, [rsi+8]
0x14005bf97  cmp     eax, 1
0x14005bf9a  jnz     loc_14005C1D5
0x14005bfa0  lfence
0x14005bfa3  cmp     eax, 1
0x14005bfa6  jnz     loc_14005C159
0x14005bfac  lea     rbx, WPP_GLOBAL_Control
0x14005bfb3  mov     ecx, [rsi+8]
0x14005bfb6  lea     eax, [rcx-1]
0x14005bfb9  cmp     eax, 3Fh ; '?'
0x14005bfbc  ja      loc_14005D11F
0x14005bfc2  lfence
0x14005bfc5  mov     r8d, [rsi+4]
0x14005bfc9  cmp     r8d, edi
0x14005bfcc  jnz     loc_14005C685
0x14005bfd2  lfence
0x14005bfd5  movsxd  rax, dword ptr [rsi+8]
0x14005bfd9  lea     rdx, cs:140000000h
0x14005bfe0  movzx   eax, rva FunctionInputBufferLength[rdx+rax*2]
0x14005bfe8  cmp     edi, eax
0x14005bfea  jb      loc_14005C3EB
0x14005bff0  lfence
0x14005bff3  movsxd  rax, dword ptr [rsi+8]
0x14005bff7  movzx   eax, rva FunctionMinimumOutputBufferLength[rdx+rax*2]
0x14005bfff  mov     r12d, dword ptr [rsp+0A8h+Length]
0x14005c007  cmp     r12d, eax
0x14005c00a  jb      loc_14005C6B3
0x14005c010  cmp     ecx, 3
0x14005c013  jz      loc_14005C112
0x14005c019  cmp     ecx, 6
0x14005c01c  jz      loc_14005C112
0x14005c022  lfence
0x14005c025  cmp     ecx, 0Ch
0x14005c028  jz      loc_14005C386
0x14005c02e  cmp     ecx, 18h
0x14005c031  jz      loc_14005C702
0x14005c037  mov     word ptr [r15], 1A5h
0x14005c03d  movsxd  rax, dword ptr [rsi+8]
0x14005c041  movzx   eax, rva FunctionMinimumOutputBufferLength[rdx+rax*2]
0x14005c049  mov     [r15+4], eax
0x14005c04d  mov     r8d, [rsi+8]
0x14005c051  cmp     r8d, 12h
0x14005c055  jnz     loc_14005C283
0x14005c05b  lfence
0x14005c05e  mov     r8d, r12d
0x14005c061  mov     rdx, r15
0x14005c064  mov     rcx, rsi
0x14005c067  call    MpQueryEaFile
0x14005c06c  mov     r14d, eax
0x14005c06f  lea     rbx, WPP_GLOBAL_Control
0x14005c076  test    r14d, r14d
0x14005c079  jns     loc_14005C32B
0x14005c07f  jmp     short loc_14005C0A6
0x14005c081  lea     rax, WPP_GLOBAL_Control
0x14005c088  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c08f  cmp     rcx, rax
0x14005c092  jnz     loc_14005D1B0
0x14005c098  mov     r14d, 0C0000206h
0x14005c09e  mov     r12d, dword ptr [rsp+0A8h+Length]
0x14005c0a6  test    rsi, rsi
0x14005c0a9  jz      short loc_14005C0F9
0x14005c0ab  cmp     edi, 80h
0x14005c0b1  ja      loc_14005C481
0x14005c0b7  mov     rbx, cs:MpData
0x14005c0be  add     rbx, 680h
0x14005c0c5  inc     dword ptr [rbx+1Ch]
0x14005c0c8  movzx   edi, word ptr [rbx+10h]
0x14005c0cc  mov     rcx, rbx; SListHead
0x14005c0cf  call    cs:__imp_ExQueryDepthSList
0x14005c0d6  nop     dword ptr [rax+rax+00h]
0x14005c0db  lfence
0x14005c0de  cmp     ax, di
0x14005c0e1  jnb     loc_14005C3D6
0x14005c0e7  mov     rdx, rsi; ListEntry
0x14005c0ea  mov     rcx, rbx; ListHead
0x14005c0ed  call    cs:__imp_ExpInterlockedPushEntrySList
0x14005c0f4  nop     dword ptr [rax+rax+00h]
0x14005c0f9  test    r15, r15
0x14005c0fc  jnz     short loc_14005C133
0x14005c0fe  mov     eax, r14d
0x14005c101  add     rsp, 70h
0x14005c105  pop     r15
0x14005c107  pop     r14
0x14005c109  pop     r13
0x14005c10b  pop     r12
0x14005c10d  pop     rdi
0x14005c10e  pop     rsi
0x14005c10f  pop     rbx
0x14005c110  retn
0x14005c112  lfence
0x14005c115  mov     r9, [rsp+0A8h+ReturnOutputBufferLength]
0x14005c11d  mov     r8d, r12d
0x14005c120  mov     rdx, r13
0x14005c123  mov     rcx, rsi
0x14005c126  call    MpQueryName
0x14005c12b  mov     r14d, eax
0x14005c12e  jmp     loc_14005C0A6
0x14005c133  cmp     r12d, 210h
0x14005c13a  jbe     loc_14005C2A0
0x14005c140  lfence
0x14005c143  mov     edx, 7266504Dh; Tag
0x14005c148  mov     rcx, r15; P
0x14005c14b  call    cs:__imp_ExFreePoolWithTag
0x14005c152  nop     dword ptr [rax+rax+00h]
0x14005c157  jmp     short loc_14005C0FE
0x14005c159  lfence
0x14005c15c  movzx   ecx, byte ptr [rsi+1]
0x14005c160  cmp     cl, 1
0x14005c163  jz      loc_14005BFAC
0x14005c169  lea     rbx, WPP_GLOBAL_Control
0x14005c170  mov     rax, cs:WPP_GLOBAL_Control
0x14005c177  cmp     rax, rbx
0x14005c17a  jz      loc_14005BFB3
0x14005c180  mov     eax, [rax+2Ch]
0x14005c183  test    al, 2
0x14005c185  jz      loc_14005BFB3
0x14005c18b  lfence
0x14005c18e  mov     eax, ecx
0x14005c190  movzx   ecx, byte ptr [rsi]
0x14005c193  mov     r9, gs:188h
0x14005c19c  mov     edx, 3Ah ; ':'
0x14005c1a1  mov     [rsp+0A8h+var_70], 1
0x14005c1a9  mov     [rsp+0A8h+var_78], 0A5h
0x14005c1b1  mov     [rsp+0A8h+var_80], eax
0x14005c1b5  mov     dword ptr [rsp+0A8h+var_88], ecx
0x14005c1b9  lea     r8, WPP_1a3d4887b9bd3cba22fd3e00f3d9a078_Traceguids
0x14005c1c0  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c1c7  mov     rcx, [rcx+18h]
0x14005c1cb  call    WPP_SF_qdddd
0x14005c1d0  jmp     loc_14005BFB3
0x14005c1d5  lfence
0x14005c1d8  movzx   ecx, byte ptr [rsi]
0x14005c1db  cmp     cl, 0A5h
0x14005c1de  jz      loc_14005BFA0
0x14005c1e4  lea     rbx, WPP_GLOBAL_Control
0x14005c1eb  mov     rax, cs:WPP_GLOBAL_Control
0x14005c1f2  cmp     rax, rbx
0x14005c1f5  jz      short loc_14005C242
0x14005c1f7  mov     eax, [rax+2Ch]
0x14005c1fa  test    al, 1
0x14005c1fc  jz      short loc_14005C242
0x14005c1fe  lfence
0x14005c201  movzx   eax, byte ptr [rsi+1]
0x14005c205  mov     r9, gs:188h
0x14005c20e  mov     edx, 39h ; '9'
0x14005c213  mov     [rsp+0A8h+var_70], 1
0x14005c21b  mov     [rsp+0A8h+var_78], 0A5h
0x14005c223  mov     [rsp+0A8h+var_80], eax
0x14005c227  mov     dword ptr [rsp+0A8h+var_88], ecx
0x14005c22b  lea     r8, WPP_1a3d4887b9bd3cba22fd3e00f3d9a078_Traceguids
0x14005c232  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c239  mov     rcx, [rcx+18h]
0x14005c23d  call    WPP_SF_qdddd
0x14005c242  mov     r14d, 0C0000059h
0x14005c248  jmp     loc_14005C09E
0x14005c24d  mov     rcx, cs:MpData
0x14005c254  add     rcx, 680h; Lookaside
0x14005c25b  call    ExAllocateFromPagedLookasideList
0x14005c260  mov     rsi, rax
0x14005c263  mov     [rsp+0A8h+var_50], rax
0x14005c268  test    rax, rax
0x14005c26b  jz      loc_14005BEE9
0x14005c271  mov     r8, rdi; Size
0x14005c274  xor     edx, edx; Val
0x14005c276  mov     rcx, rax; void *
0x14005c279  call    memset
0x14005c27e  jmp     loc_14005BEE9
0x14005c283  cmp     r8d, 14h
0x14005c287  jnz     loc_14005C3A4
0x14005c28d  lfence
0x14005c290  mov     rdx, r15
0x14005c293  mov     rcx, rsi
0x14005c296  call    MpQueryMotwAds
0x14005c29b  jmp     loc_14005C06C
0x14005c2a0  mov     rdi, cs:MpData
0x14005c2a7  add     rdi, 700h
0x14005c2ae  inc     dword ptr [rdi+1Ch]
0x14005c2b1  movzx   ebx, word ptr [rdi+10h]
0x14005c2b5  mov     rcx, rdi; SListHead
0x14005c2b8  call    cs:__imp_ExQueryDepthSList
0x14005c2bf  nop     dword ptr [rax+rax+00h]
0x14005c2c4  lfence
0x14005c2c7  cmp     ax, bx
0x14005c2ca  jnb     loc_14005C4AF
0x14005c2d0  mov     rdx, r15; ListEntry
0x14005c2d3  mov     rcx, rdi; ListHead
0x14005c2d6  call    cs:__imp_ExpInterlockedPushEntrySList
0x14005c2dd  nop     dword ptr [rax+rax+00h]
0x14005c2e2  jmp     loc_14005C0FE
0x14005c2e7  cmp     byte ptr [rsi+10h], 1; jumptable 000000014005C3BD case 42
0x14005c2eb  jz      loc_14005CCED
0x14005c2f1  mov     rax, cs:MpData
0x14005c2f8  mov     byte ptr [rax+0FC8h], 0
0x14005c2ff  mov     rax, cs:MpData
0x14005c306  movzx   ecx, byte ptr [rax+0FC8h]
0x14005c30d  mov     [r15+8], cl
0x14005c311  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c318  cmp     rcx, rbx
0x14005c31b  jnz     loc_14005CD1C
0x14005c321  xor     r14d, r14d
0x14005c324  lea     rbx, WPP_GLOBAL_Control
0x14005c32b  lfence
0x14005c32e  mov     r8d, [r15+4]; Size
0x14005c332  mov     rdx, r15; Src
0x14005c335  mov     rcx, r13; void *
0x14005c338  call    memmove
0x14005c33d  jmp     short loc_14005C36A
0x14005c33f  mov     r14d, eax
0x14005c342  lea     rbx, WPP_GLOBAL_Control
0x14005c349  mov     r13, [rsp+0A8h+arg_18]
0x14005c351  mov     edi, [rsp+0A8h+arg_10]
0x14005c358  mov     rsi, [rsp+0A8h+var_50]
0x14005c35d  mov     r15, [rsp+0A8h+var_48]
0x14005c362  mov     r12d, dword ptr [rsp+0A8h+Length]
0x14005c36a  test    r14d, r14d
0x14005c36d  js      loc_14005D0D5
0x14005c373  mov     eax, [r15+4]
0x14005c377  mov     rcx, [rsp+0A8h+ReturnOutputBufferLength]
0x14005c37f  mov     [rcx], eax
0x14005c381  jmp     loc_14005C0A6
0x14005c386  mov     r9, [rsp+0A8h+ReturnOutputBufferLength]
0x14005c38e  mov     r8d, r12d
0x14005c391  mov     rdx, r13
0x14005c394  mov     rcx, rsi
0x14005c397  call    MpQueryDosName
0x14005c39c  mov     r14d, eax
0x14005c39f  jmp     loc_14005C0A6
0x14005c3a4  lea     eax, [r8-1]; switch 64 cases
  ... truncated ...
```
