# WofPreFsctlSetExternalBacking

- ea: `0x140035118`
- end: `0x140035ec6`
- name: `WofPreFsctlSetExternalBacking`
- size: `3502`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x140034740`

## callees

- `0x1400014d0`
- `0x140007740`
- `0x140009910`
- `0x14000b1e8`
- `0x14000dc88`
- `0x14000e36c`
- `0x14000e3dc`
- `0x140011560`
- `0x140011640`
- `0x140033930`
- `0x140035118`
- `0x140036670`
- `0x14003d26c`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x140035513`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140035e42`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140035513`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140035e42`
- `ntoskrnl!ExAcquireFastMutex` at `0x140035c39`
- `ntoskrnl!ExAcquireFastMutex` at `0x140035c39`
- `ntoskrnl!ExReleaseFastMutex` at `0x140035c4e`
- `ntoskrnl!ExReleaseFastMutex` at `0x140035c4e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400358b1`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003597f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140035a17`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140035de8`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140035dff`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400358b1`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003597f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140035a17`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140035de8`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140035dff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035e2d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035e2d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003543d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003543d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140035872`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140035907`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003595b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400359e5`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140035dc4`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140035872`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140035907`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003595b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400359e5`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140035dc4`
- `FLTMGR!FltTagFile` at `0x1400357f1`
- `FLTMGR!FltTagFile` at `0x1400357f1`
- `FLTMGR!FltIsDirectory` at `0x140035333`
- `FLTMGR!FltIsDirectory` at `0x140035333`
- `FLTMGR!FltSetInformationFile` at `0x1400356a3`
- `FLTMGR!FltSetInformationFile` at `0x140035a53`
- `FLTMGR!FltSetInformationFile` at `0x140035be9`
- `FLTMGR!FltSetInformationFile` at `0x140035ced`
- `FLTMGR!FltSetInformationFile` at `0x140035e7a`
- `FLTMGR!FltSetInformationFile` at `0x1400356a3`
- `FLTMGR!FltSetInformationFile` at `0x140035a53`
- `FLTMGR!FltSetInformationFile` at `0x140035be9`
- `FLTMGR!FltSetInformationFile` at `0x140035ced`
- `FLTMGR!FltSetInformationFile` at `0x140035e7a`
- `FLTMGR!FltFsControlFile` at `0x140035abc`
- `FLTMGR!FltFsControlFile` at `0x140035afc`
- `FLTMGR!FltFsControlFile` at `0x140035b96`
- `FLTMGR!FltFsControlFile` at `0x140035c96`
- `FLTMGR!FltFsControlFile` at `0x140035d6f`
- `FLTMGR!FltFsControlFile` at `0x140035abc`
- `FLTMGR!FltFsControlFile` at `0x140035afc`
- `FLTMGR!FltFsControlFile` at `0x140035b96`
- `FLTMGR!FltFsControlFile` at `0x140035c96`
- `FLTMGR!FltFsControlFile` at `0x140035d6f`
- `FLTMGR!FltGetStreamContext` at `0x140035747`
- `FLTMGR!FltGetStreamContext` at `0x140035747`
- `FLTMGR!FltReleaseContext` at `0x14003523d`
- `FLTMGR!FltReleaseContext` at `0x14003525b`
- `FLTMGR!FltReleaseContext` at `0x14003540a`
- `FLTMGR!FltReleaseContext` at `0x14003545c`
- `FLTMGR!FltReleaseContext` at `0x140035590`
- `FLTMGR!FltReleaseContext` at `0x14003561a`
- `FLTMGR!FltReleaseContext` at `0x14003566a`
- `FLTMGR!FltReleaseContext` at `0x140035e0f`
- `FLTMGR!FltReleaseContext` at `0x14003523d`
- `FLTMGR!FltReleaseContext` at `0x14003525b`
- `FLTMGR!FltReleaseContext` at `0x14003540a`
- `FLTMGR!FltReleaseContext` at `0x14003545c`
- `FLTMGR!FltReleaseContext` at `0x140035590`
- `FLTMGR!FltReleaseContext` at `0x14003561a`
- `FLTMGR!FltReleaseContext` at `0x14003566a`
- `FLTMGR!FltReleaseContext` at `0x140035e0f`

## pseudocode

```c
__int64 __fastcall WofPreFsctlSetExternalBacking(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  unsigned int *Parameters; // r15
  struct _EX_RUNDOWN_REF *v6; // r13
  ULONG Options; // ecx
  ULONG v8; // r14d
  __int64 v9; // rax
  __int64 v10; // r12
  NTSTATUS v11; // eax
  int v13; // edx
  int v14; // r9d
  struct _FILE_OBJECT *v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // r8
  char *v20; // r14
  __int64 (__fastcall *v21)(PFLT_CALLBACK_DATA, char *, unsigned int *, _QWORD, char *, _QWORD, unsigned int *); // rax
  char *v22; // rdx
  unsigned int *PoolWithTag; // rax
  unsigned int *v24; // r8
  int v25; // eax
  ULONG_PTR v26; // rcx
  __int64 v27; // rdx
  char v28; // cl
  int v29; // r9d
  __int64 (__fastcall *v30)(char *, __int64, unsigned int *); // rax
  NTSTATUS v31; // eax
  int v32; // edx
  struct _FILE_OBJECT *v33; // rdx
  struct _FLT_INSTANCE *v34; // rcx
  __int64 Count; // rax
  unsigned int *v36; // r14
  int v37; // edx
  NTSTATUS v38; // ecx
  struct _FILE_OBJECT *v39; // rdx
  struct _FLT_INSTANCE *v40; // rcx
  int StreamContext; // eax
  __int64 v42; // rcx
  USHORT v43; // ax
  bool v44; // zf
  char v45; // r15
  int v46; // edx
  int v47; // ecx
  __int64 v48; // rcx
  NTSTATUS v49; // eax
  int v50; // edx
  int v51; // r9d
  struct _FILE_OBJECT *v52; // rdx
  struct _FLT_INSTANCE *v53; // rcx
  int v54; // ecx
  struct _FILE_OBJECT *v55; // rdx
  NTSTATUS v56; // eax
  struct _FLT_INSTANCE *v57; // rcx
  struct _FILE_OBJECT *v58; // rdx
  int v59; // eax
  int v60; // eax
  __int64 v61; // r14
  char v62; // cl
  struct _FAST_MUTEX *v63; // rcx
  int v64; // eax
  int v65; // eax
  int v66; // edx
  PFLT_CONTEXT v67; // rcx
  struct _FILE_OBJECT *v68; // rdx
  struct _FLT_INSTANCE *v69; // rcx
  NTSTATUS DataBufferLength; // [rsp+28h] [rbp-B1h]
  int OutputBufferLength; // [rsp+30h] [rbp-A9h]
  char v72[8]; // [rsp+50h] [rbp-89h] BYREF
  PFLT_CONTEXT Context; // [rsp+58h] [rbp-81h]
  PFLT_CONTEXT v74; // [rsp+60h] [rbp-79h] BYREF
  unsigned __int8 IsDirectory; // [rsp+68h] [rbp-71h] BYREF
  char v76; // [rsp+69h] [rbp-70h] BYREF
  char v77; // [rsp+6Ah] [rbp-6Fh]
  char v78; // [rsp+6Bh] [rbp-6Eh]
  _WORD OutputBuffer[2]; // [rsp+6Ch] [rbp-6Dh] BYREF
  char v80; // [rsp+70h] [rbp-69h]
  int OpenContext; // [rsp+74h] [rbp-65h]
  USHORT InputBuffer[2]; // [rsp+78h] [rbp-61h] BYREF
  unsigned int v83; // [rsp+7Ch] [rbp-5Dh] BYREF
  __int64 v84; // [rsp+80h] [rbp-59h] BYREF
  unsigned int *v85; // [rsp+88h] [rbp-51h]
  unsigned int *v86; // [rsp+90h] [rbp-49h]
  __int64 v87; // [rsp+98h] [rbp-41h] BYREF
  __int64 v88; // [rsp+A0h] [rbp-39h]
  __int64 v89; // [rsp+A8h] [rbp-31h]
  unsigned int *v90; // [rsp+B0h] [rbp-29h]
  __int128 v91; // [rsp+B8h] [rbp-21h] BYREF
  __int64 v92; // [rsp+C8h] [rbp-11h]
  __m128i FileInformation; // [rsp+D0h] [rbp-9h] BYREF
  __m128i v94; // [rsp+E0h] [rbp+7h]
  __int64 v95; // [rsp+F0h] [rbp+17h]

  Iopb = CallbackData->Iopb;
  v74 = 0;
  v87 = 0;
  Context = 0;
  Parameters = (unsigned int *)Iopb->Parameters.CreatePipe.Parameters;
  v6 = 0;
  Options = Iopb->Parameters.Create.Options;
  v90 = Parameters;
  *(_DWORD *)InputBuffer = Options;
  v76 = 0;
  v84 = 0;
  v92 = 0;
  v72[0] = 0;
  IsDirectory = 0;
  OutputBuffer[0] = 0;
  v91 = 0;
  if ( Parameters && (v8 = Options - 8, Options - 8 <= 0xFFF7) )
  {
    if ( *Parameters == 1 )
    {
      v9 = Parameters[1];
      if ( (unsigned int)v9 < 4
        && *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 424 * v9)
        && (int)WofGetVolumeContext(*(PFLT_INSTANCE *)(a2 + 24)) >= 0 )
      {
        v89 = Parameters[1];
        v10 = 424 * v89;
        v86 = Parameters + 2;
        v88 = v8;
        v11 = (*((__int64 (__fastcall **)(unsigned int *, _QWORD, _QWORD))&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels
               + 53 * v89
               + 43))(
                Parameters + 2,
                v8,
                0);
        CallbackData->IoStatus.Status = v11;
        if ( v11 < 0 )
        {
LABEL_8:
          FltReleaseContext(Context);
          return 4;
        }
        if ( *(_QWORD *)(a2 + 40) )
        {
          FltReleaseContext(Context);
          CallbackData->IoStatus.Status = -1072103334;
          return 4;
        }
        if ( (int)WofIsDataAlternateStream(CallbackData) < 0 )
        {
          CallbackData->IoStatus.Status = -1073741811;
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_8;
          v14 = 11;
LABEL_15:
          LOBYTE(v13) = 2;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v13,
            7,
            v14,
            (__int64)WPP_dcfac5c580c33e55513b631fbc558444_Traceguids,
            13);
          goto LABEL_8;
        }
        if ( v72[0] )
        {
          CallbackData->IoStatus.Status = -1073741811;
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_8;
          v14 = 12;
          goto LABEL_15;
        }
        v15 = *(struct _FILE_OBJECT **)(a2 + 32);
        if ( (v15->Flags & 0x400000) != 0 )
        {
          CallbackData->IoStatus.Status = -1073741811;
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_8;
          v14 = 13;
          goto LABEL_15;
        }
        v16 = FltIsDirectory(v15, *(PFLT_INSTANCE *)(a2 + 24), &IsDirectory);
        CallbackData->IoStatus.Status = v16;
        if ( v16 < 0 )
          goto LABEL_8;
        if ( IsDirectory )
        {
          CallbackData->IoStatus.Status = -1073741811;
          goto LABEL_8;
        }
        v17 = *(_QWORD *)(a2 + 32);
        v78 = 0;
        v77 = 0;
        v18 = *(_DWORD *)(v17 + 80);
        if ( (v18 & 0x8000) == 0 )
        {
          v77 = 1;
          *(_DWORD *)(v17 + 80) = v18 | 0x8000;
        }
        v19 = *(_QWORD *)(a2 + 32);
        v80 = *(_BYTE *)(v19 + 75);
        if ( WofBreakOnExternalFileCreation )
          WofCheckForFilenameBreak(&WofBreakOnExternalFileCreation, 0x8000, v19 + 88);
        v20 = (char *)Context;
        v21 = *(__int64 (__fastcall **)(PFLT_CALLBACK_DATA, char *, unsigned int *, _QWORD, char *, _QWORD, unsigned int *))((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v10 + 336);
        if ( !v21 )
          goto LABEL_38;
        v22 = (char *)Context + *(unsigned int *)((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v10 + 20);
        v83 = 0;
        v72[0] = 0;
        OpenContext = v21(CallbackData, v22, Parameters + 2, (unsigned int)v88, v72, 0, &v83);
        if ( OpenContext < 0 )
        {
          Parameters = 0;
          goto LABEL_32;
        }
        if ( v72[0] )
        {
          PoolWithTag = (unsigned int *)ExAllocatePoolWithTag(PagedPool, v83 + 8LL, 0x47666F57u);
          Context = PoolWithTag;
          Parameters = PoolWithTag;
          if ( !PoolWithTag )
          {
            FltReleaseContext(v20);
            CallbackData->IoStatus.Status = -1073741670;
            goto LABEL_115;
          }
          v85 = PoolWithTag + 2;
          v24 = v86;
          *(_QWORD *)PoolWithTag = *(_QWORD *)v90;
          OpenContext = (*(__int64 (__fastcall **)(PFLT_CALLBACK_DATA, char *, unsigned int *, _QWORD, _QWORD, _QWORD *, unsigned int *))((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v10 + 336))(
                          CallbackData,
                          &v20[*(unsigned int *)((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v10 + 20)],
                          v24,
                          (unsigned int)v88,
                          0,
                          (_QWORD *)PoolWithTag + 1,
                          &v83);
          if ( OpenContext < 0 )
          {
LABEL_32:
            FltReleaseContext(v20);
            CallbackData->IoStatus.Status = OpenContext;
LABEL_115:
            if ( v77 )
              *(_DWORD *)(*(_QWORD *)(a2 + 32) + 80LL) &= ~0x8000u;
            *(_BYTE *)(*(_QWORD *)(a2 + 32) + 75LL) = v80;
            v67 = v74;
            if ( v74 )
            {
              if ( v78 )
              {
                WofDeflateTelemetry(v74, a2, v86, (unsigned int)CallbackData->IoStatus.Status);
                ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)v74 + 32LL));
                *((_DWORD *)v74 + 2) &= ~0x10u;
                ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)v74 + 32LL));
                ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(*(_QWORD *)v74 + 16LL));
                v67 = v74;
              }
              FltReleaseContext(v67);
            }
            if ( Parameters && Parameters != v90 )
              ExFreePoolWithTag(Parameters, 0);
            if ( v6 )
              ExReleaseRundownProtection(v6 + 2);
            v68 = *(struct _FILE_OBJECT **)(a2 + 32);
            v69 = *(struct _FLT_INSTANCE **)(a2 + 24);
            FileInformation = _mm_load_si128((const __m128i *)&_xmm_fffffffffffffffefffffffffffffffe);
            v95 = 0;
            v94 = FileInformation;
            FltSetInformationFile(v69, v68, &FileInformation, 0x28u, FileBasicInformation);
            return 4;
          }
          *(_DWORD *)InputBuffer = v83 + 8;
        }
        else
        {
LABEL_38:
          v85 = v86;
          Context = Parameters;
        }
        v25 = WofLocateInNamedScope(CallbackData, v20, &v87);
        v6 = (struct _EX_RUNDOWN_REF *)v87;
        if ( v25 >= 0 && (_DWORD)v89 != *(_DWORD *)(v87 + 40) )
        {
          ExReleaseRundownProtection((PEX_RUNDOWN_REF)(v87 + 16));
          v6 = 0;
        }
        if ( !*(_QWORD *)((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v10 + 120) )
        {
          v26 = v6 ? v6[6].Count : 0LL;
          LOBYTE(OutputBufferLength) = 0;
          if ( (*(int (__fastcall **)(PFLT_CALLBACK_DATA, char *, __int64, _QWORD, unsigned int *, ULONG_PTR, int, _QWORD, _QWORD))((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v10 + 184))(
                 CallbackData,
                 &v20[*(unsigned int *)((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v10 + 20)],
                 a2,
                 *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 32) + 24LL) + 32LL),
                 v85,
                 v26,
                 OutputBufferLength,
                 0,
                 0) < 0 )
          {
            FltReleaseContext(v20);
            v28 = 13;
            CallbackData->IoStatus.Status = -1073741811;
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_115;
            v29 = 14;
LABEL_49:
            LOBYTE(v27) = 2;
            WPP_RECORDER_SF_d(
              WPP_GLOBAL_Control->DeviceExtension,
              v27,
              7,
              v29,
              (__int64)WPP_dcfac5c580c33e55513b631fbc558444_Traceguids,
              v28);
            goto LABEL_115;
          }
        }
        v30 = *(__int64 (__fastcall **)(char *, __int64, unsigned int *))((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels
                                                                        + v10
                                                                        + 112);
        if ( v30 )
        {
          v31 = v30(&v20[*(unsigned int *)((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v10 + 20)], a2, v85);
          CallbackData->IoStatus.Status = v31;
          if ( v31 < 0 )
          {
            FltReleaseContext(v20);
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v32) = 2;
              WPP_RECORDER_SF_(
                WPP_GLOBAL_Control->DeviceExtension,
                v32,
                7,
                15,
                (__int64)WPP_dcfac5c580c33e55513b631fbc558444_Traceguids);
            }
            goto LABEL_115;
          }
        }
        FltReleaseContext(v20);
        v33 = *(struct _FILE_OBJECT **)(a2 + 32);
        v34 = *(struct _FLT_INSTANCE **)(a2 + 24);
        v95 = 0;
        FileInformation = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
        v94 = FileInformation;
        FltSetInformationFile(v34, v33, &FileInformation, 0x28u, FileBasicInformation);
        if ( v6 )
          Count = v6[6].Count;
        else
          Count = 0;
        v36 = v85;
        OpenContext = WofCreateOpenContext((_DWORD)CallbackData, a2, v89, (_DWORD)v85, Count, 0, 0, 1);
        v38 = OpenContext;
        if ( OpenContext < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v37) = 2;
            WPP_RECORDER_SF_d(
              WPP_GLOBAL_Control->DeviceExtension,
              v37,
              7,
              16,
              (__int64)WPP_dcfac5c580c33e55513b631fbc558444_Traceguids,
              OpenContext);
            v38 = OpenContext;
          }
          CallbackData->IoStatus.Status = v38;
          goto LABEL_115;
        }
        v39 = *(struct _FILE_OBJECT **)(a2 + 32);
        v40 = *(struct _FLT_INSTANCE **)(a2 + 24);
        v78 = 1;
        StreamContext = FltGetStreamContext(v40, v39, &v74);
        CallbackData->IoStatus.Status = StreamContext;
        v28 = StreamContext;
        if ( StreamContext < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_115;
          v29 = 17;
          goto LABEL_49;
        }
        v27 = *(_QWORD *)(a2 + 32);
        v42 = *(_QWORD *)(v27 + 24);
        if ( v42 && (*(_BYTE *)(v42 + 7) & 0xF0u) >= 0x40 && *(_DWORD *)(v42 + 104) )
        {
          v28 = -57;
          CallbackData->IoStatus.Status = -1073740601;
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_115;
          v29 = 18;
          goto LABEL_49;
        }
        v43 = InputBuffer[0];
        v44 = OpenContext == 51314690;
        *(_BYTE *)(v27 + 75) = 1;
        v45 = v44;
        v47 = FltTagFile(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), FileTag, 0, Context, v43);
        CallbackData->IoStatus.Status = v47;
        if ( v47 < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v46) = 2;
            WPP_RECORDER_SF_d(
              WPP_GLOBAL_Control->DeviceExtension,
              v46,
              7,
              19,
              (__int64)WPP_dcfac5c580c33e55513b631fbc558444_Traceguids,
              v47);
          }
          WofMarkFileAsInflated(a2, v74);
          goto LABEL_114;
        }
        v48 = *(_QWORD *)v74;
        if ( *(_QWORD *)((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v10 + 120) )
        {
          ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v48 + 32));
          *((_DWORD *)v74 + 2) &= 0xF0FFFFFF;
          *((_DWORD *)v74 + 2) |= 0x4000020u;
          **(_DWORD **)v74 &= ~1u;
          ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)v74 + 32LL));
          v49 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64, unsigned int *))((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels
                                                                                   + v10
                                                                                   + 120))(
                  *(_QWORD *)(*(_QWORD *)v74 + 8LL)
                + *(unsigned int *)((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v10 + 20),
                  (char *)v74 + 64,
                  a2,
                  v36);
          CallbackData->IoStatus.Status = v49;
          if ( v49 == 51314691 )
          {
            v45 = 1;
            CallbackData->IoStatus.Status = 0;
          }
          else if ( v49 )
          {
            ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)v74 + 32LL));
            *((_DWORD *)v74 + 2) &= ~0x20u;
            ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)v74 + 32LL));
            WofMarkFileAsInflated(a2, v74);
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v51 = 20;
              DataBufferLength = CallbackData->IoStatus.Status;
LABEL_81:
              LOBYTE(v50) = 2;
              WPP_RECORDER_SF_d(
                WPP_GLOBAL_Control->DeviceExtension,
                v50,
                7,
                v51,
                (__int64)WPP_dcfac5c580c33e55513b631fbc558444_Traceguids,
                DataBufferLength);
              goto LABEL_114;
            }
            goto LABEL_114;
          }
          ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)v74 + 32LL));
          *((_DWORD *)v74 + 2) &= 0xF0FFFFDB;
          *((_DWORD *)v74 + 2) |= 0x1000010u;
          if ( v45 )
            *((_DWORD *)v74 + 2) |= 0x40u;
        }
        else
        {
          ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v48 + 32));
          *((_DWORD *)v74 + 2) |= 0x10u;
          **(_DWORD **)v74 &= ~1u;
        }
        ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)v74 + 32LL));
        WofWaitForIoToUnknownFile(*(_QWORD *)(a2 + 32));
        if ( !v45 )
        {
          v52 = *(struct _FILE_OBJECT **)(a2 + 32);
          v53 = *(struct _FLT_INSTANCE **)(a2 + 24);
          v84 = 0;
          v54 = FltSetInformationFile(v53, v52, &v84, 8u, FileAllocationInformation);
          CallbackData->IoStatus.Status = v54;
          if ( v54 < 0 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_114;
            v51 = 21;
            goto LABEL_87;
          }
          FltFsControlFile(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), 0x9003Cu, 0, 0, OutputBuffer, 2u, 0);
          if ( OutputBuffer[0] )
          {
            v55 = *(struct _FILE_OBJECT **)(a2 + 32);
            InputBuffer[0] = 0;
            FltFsControlFile(*(PFLT_INSTANCE *)(a2 + 24), v55, 0x9C040u, InputBuffer, 2u, 0, 0, 0);
          }
        }
        v56 = (*(__int64 (__fastcall **)(char *, __int64 *, _QWORD))((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels
                                                                   + v10
                                                                   + 320))(
                (char *)v74 + 64,
                &v84,
                0);
        CallbackData->IoStatus.Status = v56;
        LOBYTE(v54) = v56;
        if ( v56 < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_114;
          v51 = 22;
          goto LABEL_87;
        }
        *((_QWORD *)&v91 + 1) = v84;
        *(_QWORD *)&v91 = 0;
        v57 = *(struct _FLT_INSTANCE **)(a2 + 24);
        v76 = 1;
        v58 = *(struct _FILE_OBJECT **)(a2 + 32);
        LODWORD(v92) = v45 != 0;
        v59 = FltFsControlFile(v57, v58, 0x900C4u, &v76, 1u, 0, 0, 0);
        CallbackData->IoStatus.Status = v59;
        LOBYTE(v54) = v59;
        if ( v59 < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_114;
          v51 = 23;
          goto LABEL_87;
        }
        if ( !v45 )
        {
          v60 = FltSetInformationFile(
                  *(PFLT_INSTANCE *)(a2 + 24),
                  *(PFILE_OBJECT *)(a2 + 32),
                  &v84,
                  8u,
                  FileEndOfFileInformation);
          CallbackData->IoStatus.Status = v60;
          LOBYTE(v54) = v60;
          if ( v60 < 0 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_114;
            v51 = 24;
            goto LABEL_87;
          }
        }
        v61 = *(_QWORD *)(*(_QWORD *)(a2 + 32) + 24LL);
        v62 = *(_BYTE *)(v61 + 6);
        if ( (v62 & 4) != 0 )
        {
          if ( (*(_BYTE *)(v61 + 4) & 0x40) != 0 )
          {
            ExAcquireFastMutex(*(PFAST_MUTEX *)(v61 + 48));
            v63 = *(struct _FAST_MUTEX **)(v61 + 48);
            *(_BYTE *)(v61 + 6) &= ~4u;
            ExReleaseFastMutex(v63);
          }
          else
          {
            *(_BYTE *)(v61 + 6) = v62 & 0xFB;
          }
        }
        if ( OpenContext == 51314690
          || (v64 = FltFsControlFile(
                      *(PFLT_INSTANCE *)(a2 + 24),
                      *(PFILE_OBJECT *)(a2 + 32),
                      0x980C8u,
                      &v91,
                      0x18u,
                      0,
                      0,
                      0),
              CallbackData->IoStatus.Status = v64,
              LOBYTE(v54) = v64,
              v64 >= 0) )
        {
          if ( !v45 )
          {
            v65 = FltSetInformationFile(
                    *(PFLT_INSTANCE *)(a2 + 24),
                    *(PFILE_OBJECT *)(a2 + 32),
                    &v84,
                    8u,
                    FileValidDataLengthInformation);
            CallbackData->IoStatus.Status = v65;
            if ( v65 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v66) = 2;
              WPP_RECORDER_SF_d(
                WPP_GLOBAL_Control->DeviceExtension,
                v66,
                7,
                26,
                (__int64)WPP_dcfac5c580c33e55513b631fbc558444_Traceguids,
                v65);
            }
            if ( OutputBuffer[0] )
              FltFsControlFile(
                *(PFLT_INSTANCE *)(a2 + 24),
                *(PFILE_OBJECT *)(a2 + 32),
                0x9C040u,
                OutputBuffer,
                2u,
                0,
                0,
                0);
          }
          goto LABEL_114;
        }
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v51 = 25;
LABEL_87:
          LOBYTE(DataBufferLength) = v54;
          goto LABEL_81;
        }
LABEL_114:
        Parameters = (unsigned int *)Context;
        goto LABEL_115;
      }
    }
    return 5;
  }
  else
  {
    CallbackData->IoStatus.Status = -1073741306;
    return 4;
  }
}

```

## disassembly

```asm
0x140035118  mov     [rsp-8+arg_10], rbx
0x14003511d  push    rbp
0x14003511e  push    rsi
0x14003511f  push    rdi
0x140035120  push    r12
0x140035122  push    r13
0x140035124  push    r14
0x140035126  push    r15
0x140035128  lea     rbp, [rsp-27h]
0x14003512d  sub     rsp, 100h
0x140035134  mov     rax, cs:__security_cookie
0x14003513b  xor     rax, rsp
0x14003513e  mov     [rbp+57h+var_38], rax
0x140035142  mov     rax, [rcx+10h]
0x140035146  xor     r12d, r12d
0x140035149  mov     [rbp+57h+var_D0], r12
0x14003514d  mov     rdi, rcx
0x140035150  xorps   xmm0, xmm0
0x140035153  mov     [rbp+57h+var_98], r12
0x140035157  mov     rbx, rdx
0x14003515a  mov     [rsp+130h+Context], r12
0x14003515f  mov     r15, [rax+30h]
0x140035163  mov     r13d, r12d
0x140035166  mov     ecx, [rax+20h]
0x140035169  xor     eax, eax
0x14003516b  mov     [rbp+57h+var_80], r15
0x14003516f  mov     dword ptr [rbp+57h+InputBuffer], ecx
0x140035172  mov     [rbp+57h+var_C7], r12b
0x140035176  mov     [rbp+57h+var_B0], r12
0x14003517a  mov     [rbp+57h+var_68], rax
0x14003517e  mov     [rsp+130h+var_E0], r12b
0x140035183  mov     [rbp+57h+IsDirectory], r12b
0x140035187  mov     [rbp+57h+OutputBuffer], r12w
0x14003518c  movups  [rbp+57h+var_78], xmm0
0x140035190  test    r15, r15
0x140035193  jz      loc_140035E92
0x140035199  lea     r14d, [rcx-8]
0x14003519d  cmp     r14d, 0FFF7h
0x1400351a4  ja      loc_140035E92
0x1400351aa  cmp     dword ptr [r15], 1
0x1400351ae  jnz     loc_140035E8B
0x1400351b4  mov     eax, [r15+4]
0x1400351b8  lea     esi, [r12+4]
0x1400351bd  cmp     eax, esi
0x1400351bf  jnb     loc_140035E8B
0x1400351c5  imul    rcx, rax, 1A8h
0x1400351cc  lea     rax, WPP_MAIN_CB.Queue+10h
0x1400351d3  cmp     [rcx+rax], r12b
0x1400351d7  jz      loc_140035E8B
0x1400351dd  mov     rcx, [rbx+18h]; Instance
0x1400351e1  lea     rdx, [rsp+130h+Context]
0x1400351e6  call    WofGetVolumeContext
0x1400351eb  test    eax, eax
0x1400351ed  js      loc_140035E8B
0x1400351f3  mov     eax, [r15+4]
0x1400351f7  lea     rdx, WPP_MAIN_CB.Queue+10h
0x1400351fe  lea     r9, [r15+8]
0x140035202  mov     [rbp+57h+var_88], rax
0x140035206  imul    r12, rax, 1A8h
0x14003520d  mov     ecx, r14d
0x140035210  mov     [rbp+57h+var_A0], r9
0x140035214  mov     [rbp+57h+var_90], rcx
0x140035218  xor     r8d, r8d
0x14003521b  mov     rcx, r9
0x14003521e  mov     rax, [r12+rdx+158h]
0x140035226  mov     edx, r14d
0x140035229  call    _guard_dispatch_icall
0x14003522e  xor     r14d, r14d
0x140035231  mov     [rdi+18h], eax
0x140035234  test    eax, eax
0x140035236  jns     short loc_140035250
0x140035238  mov     rcx, [rsp+130h+Context]; Context
0x14003523d  call    cs:__imp_FltReleaseContext
0x140035244  nop     dword ptr [rax+rax+00h]
0x140035249  mov     eax, esi
0x14003524b  jmp     loc_140035E9E
0x140035250  cmp     [rbx+28h], r14
0x140035254  jz      short loc_140035270
0x140035256  mov     rcx, [rsp+130h+Context]; Context
0x14003525b  call    cs:__imp_FltReleaseContext
0x140035262  nop     dword ptr [rax+rax+00h]
0x140035267  mov     dword ptr [rdi+18h], 0C019005Ah
0x14003526e  jmp     short loc_140035249
0x140035270  lea     rdx, [rsp+130h+var_E0]
0x140035275  mov     rcx, rdi; CallbackData
0x140035278  call    WofIsDataAlternateStream
0x14003527d  test    eax, eax
0x14003527f  jns     short loc_1400352CC
0x140035281  mov     ecx, 0C000000Dh
0x140035286  mov     [rdi+18h], ecx
0x140035289  lea     rax, WPP_RECORDER_INITIALIZED
0x140035290  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140035297  jz      short loc_140035238
0x140035299  mov     r9d, 0Bh
0x14003529f  mov     dword ptr [rsp+130h+DataBufferLength], ecx
0x1400352a3  lea     rax, WPP_dcfac5c580c33e55513b631fbc558444_Traceguids
0x1400352aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400352b1  mov     r8d, 7
0x1400352b7  mov     dl, 2
0x1400352b9  mov     qword ptr [rsp+130h+FileInformationClass], rax
0x1400352be  mov     rcx, [rcx+40h]
0x1400352c2  call    WPP_RECORDER_SF_d
0x1400352c7  jmp     loc_140035238
0x1400352cc  cmp     [rsp+130h+var_E0], r14b
0x1400352d1  jz      short loc_1400352F7
0x1400352d3  mov     ecx, 0C000000Dh
0x1400352d8  mov     [rdi+18h], ecx
0x1400352db  lea     rax, WPP_RECORDER_INITIALIZED
0x1400352e2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400352e9  jz      loc_140035238
0x1400352ef  mov     r9d, 0Ch
0x1400352f5  jmp     short loc_14003529F
0x1400352f7  mov     rcx, [rbx+20h]; FileObject
0x1400352fb  test    dword ptr [rcx+50h], 400000h
0x140035302  jz      short loc_14003532B
0x140035304  mov     ecx, 0C000000Dh
0x140035309  mov     [rdi+18h], ecx
0x14003530c  lea     rax, WPP_RECORDER_INITIALIZED
0x140035313  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003531a  jz      loc_140035238
0x140035320  mov     r9d, 0Dh
0x140035326  jmp     loc_14003529F
0x14003532b  mov     rdx, [rbx+18h]; Instance
0x14003532f  lea     r8, [rbp+57h+IsDirectory]; IsDirectory
0x140035333  call    cs:__imp_FltIsDirectory
0x14003533a  nop     dword ptr [rax+rax+00h]
0x14003533f  mov     [rdi+18h], eax
0x140035342  test    eax, eax
0x140035344  js      loc_140035238
0x14003534a  cmp     [rbp+57h+IsDirectory], r14b
0x14003534e  jz      short loc_14003535C
0x140035350  mov     dword ptr [rdi+18h], 0C000000Dh
0x140035357  jmp     loc_140035238
0x14003535c  mov     rcx, [rbx+20h]
0x140035360  mov     edx, 8000h
0x140035365  mov     [rbp+57h+var_C5], r14b
0x140035369  mov     [rbp+57h+var_C6], r14b
0x14003536d  mov     eax, [rcx+50h]
0x140035370  test    edx, eax
0x140035372  jnz     short loc_14003537D
0x140035374  or      eax, edx
0x140035376  mov     [rbp+57h+var_C6], 1
0x14003537a  mov     [rcx+50h], eax
0x14003537d  cmp     cs:WofBreakOnExternalFileCreation, r14w
0x140035385  mov     r8, [rbx+20h]
0x140035389  mov     al, [r8+4Bh]
0x14003538d  mov     [rbp+57h+var_C0], al
0x140035390  jz      short loc_1400353A2
0x140035392  add     r8, 58h ; 'X'
0x140035396  lea     rcx, WofBreakOnExternalFileCreation
0x14003539d  call    WofCheckForFilenameBreak
0x1400353a2  mov     r14, [rsp+130h+Context]
0x1400353a7  lea     rcx, WPP_MAIN_CB.Queue+10h
0x1400353ae  mov     rax, [r12+rcx+150h]
0x1400353b6  xor     r8d, r8d
0x1400353b9  test    rax, rax
0x1400353bc  jz      loc_1400354D6
0x1400353c2  mov     edx, [r12+rcx+14h]
0x1400353c7  lea     rcx, [rbp+57h+var_B4]
0x1400353cb  mov     r9d, dword ptr [rbp+57h+var_90]
0x1400353cf  add     rdx, r14
0x1400353d2  mov     qword ptr [rsp+130h+OutputBufferLength], rcx
0x1400353d7  lea     rcx, [rsp+130h+var_E0]
0x1400353dc  mov     qword ptr [rsp+130h+DataBufferLength], r8
0x1400353e1  mov     qword ptr [rsp+130h+FileInformationClass], rcx
0x1400353e6  mov     rcx, rdi
0x1400353e9  mov     [rbp+57h+var_B4], r8d
0x1400353ed  mov     [rsp+130h+var_E0], r8b
0x1400353f2  lea     r8, [r15+8]
0x1400353f6  call    _guard_dispatch_icall
0x1400353fb  xor     ecx, ecx
0x1400353fd  mov     [rbp+57h+var_BC], eax
0x140035400  test    eax, eax
0x140035402  jns     short loc_140035421
0x140035404  mov     r15d, ecx
0x140035407  mov     rcx, r14; Context
0x14003540a  call    cs:__imp_FltReleaseContext
0x140035411  nop     dword ptr [rax+rax+00h]
0x140035416  mov     eax, [rbp+57h+var_BC]
0x140035419  mov     [rdi+18h], eax
0x14003541c  jmp     loc_140035D80
0x140035421  cmp     [rsp+130h+var_E0], cl
0x140035425  jz      loc_1400354DE
0x14003542b  mov     edx, [rbp+57h+var_B4]
0x14003542e  mov     ecx, 1; PoolType
0x140035433  add     rdx, 8; NumberOfBytes
0x140035437  mov     r8d, 47666F57h; Tag
0x14003543d  call    cs:__imp_ExAllocatePoolWithTag
0x140035444  nop     dword ptr [rax+rax+00h]
0x140035449  xor     r9d, r9d
0x14003544c  mov     [rsp+130h+Context], rax
0x140035451  mov     r15, rax
0x140035454  test    rax, rax
0x140035457  jnz     short loc_140035474
0x140035459  mov     rcx, r14; Context
0x14003545c  call    cs:__imp_FltReleaseContext
0x140035463  nop     dword ptr [rax+rax+00h]
0x140035468  mov     dword ptr [rdi+18h], 0C000009Ah
0x14003546f  jmp     loc_140035D80
0x140035474  lea     rcx, [rax+8]
0x140035478  mov     rax, [rbp+57h+var_80]
0x14003547c  lea     r8, [rbp+57h+var_B4]
0x140035480  mov     [rbp+57h+var_A8], rcx
0x140035484  mov     qword ptr [rsp+130h+OutputBufferLength], r8
0x140035489  mov     r8, [rbp+57h+var_A0]
0x14003548d  mov     rax, [rax]
0x140035490  mov     [r15], rax
0x140035493  lea     rax, WPP_MAIN_CB.Queue+10h
0x14003549a  mov     edx, [r12+rax+14h]
0x14003549f  mov     rax, [r12+rax+150h]
0x1400354a7  add     rdx, r14
0x1400354aa  mov     qword ptr [rsp+130h+DataBufferLength], rcx
0x1400354af  mov     rcx, rdi
0x1400354b2  mov     qword ptr [rsp+130h+FileInformationClass], r9
0x1400354b7  mov     r9d, dword ptr [rbp+57h+var_90]
0x1400354bb  call    _guard_dispatch_icall
0x1400354c0  mov     [rbp+57h+var_BC], eax
0x1400354c3  test    eax, eax
0x1400354c5  js      loc_140035407
0x1400354cb  mov     eax, [rbp+57h+var_B4]
0x1400354ce  add     eax, 8
0x1400354d1  mov     dword ptr [rbp+57h+InputBuffer], eax
0x1400354d4  jmp     short loc_1400354EB
0x1400354d6  mov     r13d, dword ptr [rbp+57h+InputBuffer]
0x1400354da  mov     dword ptr [rbp+57h+InputBuffer], r13d
0x1400354de  mov     rax, [rbp+57h+var_A0]
0x1400354e2  mov     [rbp+57h+var_A8], rax
0x1400354e6  mov     [rsp+130h+Context], r15
0x1400354eb  lea     r8, [rbp+57h+var_98]
0x1400354ef  mov     rdx, r14
0x1400354f2  mov     rcx, rdi
0x1400354f5  call    WofLocateInNamedScope
0x1400354fa  mov     r13, [rbp+57h+var_98]
0x1400354fe  xor     r8d, r8d
0x140035501  test    eax, eax
0x140035503  js      short loc_140035525
0x140035505  mov     rax, [rbp+57h+var_88]
0x140035509  cmp     eax, [r13+28h]
0x14003550d  jz      short loc_140035525
0x14003550f  lea     rcx, [r13+10h]; RunRef
0x140035513  call    cs:__imp_ExReleaseRundownProtection
0x14003551a  nop     dword ptr [rax+rax+00h]
0x14003551f  xor     r8d, r8d
0x140035522  mov     r13d, r8d
0x140035525  lea     r10, WPP_MAIN_CB.Queue+10h
0x14003552c  cmp     [r12+r10+78h], r8
0x140035531  jnz     loc_1400355F2
0x140035537  test    r13, r13
0x14003553a  jz      short loc_140035542
0x14003553c  mov     rcx, [r13+30h]
0x140035540  jmp     short loc_140035545
0x140035542  mov     rcx, r8
0x140035545  mov     rax, [rbx+20h]
0x140035549  mov     edx, [r12+r10+14h]
0x14003554e  mov     [rsp+130h+var_F0], r8
0x140035553  add     rdx, r14
0x140035556  mov     [rsp+130h+LengthReturned], r8
0x14003555b  mov     r9, [rax+18h]
0x14003555f  mov     rax, [r12+r10+0B8h]
0x140035567  mov     byte ptr [rsp+130h+OutputBufferLength], r8b
0x14003556c  mov     r8, rbx
0x14003556f  mov     qword ptr [rsp+130h+DataBufferLength], rcx
0x140035574  mov     rcx, [rbp+57h+var_A8]
0x140035578  mov     r9, [r9+20h]
0x14003557c  mov     qword ptr [rsp+130h+FileInformationClass], rcx
0x140035581  mov     rcx, rdi
0x140035584  call    _guard_dispatch_icall
0x140035589  test    eax, eax
0x14003558b  jns     short loc_1400355EB
0x14003558d  mov     rcx, r14; Context
0x140035590  call    cs:__imp_FltReleaseContext
0x140035597  nop     dword ptr [rax+rax+00h]
0x14003559c  mov     ecx, 0C000000Dh
0x1400355a1  mov     [rdi+18h], ecx
0x1400355a4  lea     rax, WPP_RECORDER_INITIALIZED
0x1400355ab  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400355b2  jz      loc_140035D80
0x1400355b8  mov     r9d, 0Eh
0x1400355be  mov     dword ptr [rsp+130h+DataBufferLength], ecx
0x1400355c2  lea     rax, WPP_dcfac5c580c33e55513b631fbc558444_Traceguids
0x1400355c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400355d0  mov     r8d, 7
0x1400355d6  mov     dl, 2
0x1400355d8  mov     qword ptr [rsp+130h+FileInformationClass], rax
0x1400355dd  mov     rcx, [rcx+40h]
0x1400355e1  call    WPP_RECORDER_SF_d
0x1400355e6  jmp     loc_140035D80
0x1400355eb  lea     r10, WPP_MAIN_CB.Queue+10h
0x1400355f2  mov     rax, [r12+r10+70h]
0x1400355f7  test    rax, rax
0x1400355fa  jz      short loc_140035667
0x1400355fc  mov     ecx, [r12+r10+14h]
0x140035601  mov     rdx, rbx
0x140035604  mov     r8, [rbp+57h+var_A8]
0x140035608  add     rcx, r14
0x14003560b  call    _guard_dispatch_icall
0x140035610  mov     [rdi+18h], eax
0x140035613  test    eax, eax
0x140035615  jns     short loc_140035667
0x140035617  mov     rcx, r14; Context
  ... truncated ...
```
