# VhdmpiInitializeMirror(_VHD_HANDLE_CONTEXT *,_VHD_ASYNC_OP_CONTEXT *,void *,ulong)

- ea: `0x1400b36d0`
- end: `0x1400b445c`
- name: `?VhdmpiInitializeMirror@@YAJPEAU_VHD_HANDLE_CONTEXT@@PEAU_VHD_ASYNC_OP_CONTEXT@@PEAXK@Z`
- size: `3468`
- prototype: `int(struct _VHD_HANDLE_CONTEXT *, struct _VHD_ASYNC_OP_CONTEXT *, void *, unsigned int)`
- caller_count: `0`
- callee_count: `38`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1400010d0`
- `0x140001130`
- `0x1400011c0`
- `0x140001340`
- `0x140014b00`
- `0x14001bc1c`
- `0x14001c088`
- `0x1400205f0`
- `0x140020c94`
- `0x140023980`
- `0x140026764`
- `0x140026930`
- `0x140029590`
- `0x14002966c`
- `0x14002cfcc`
- `0x140033268`
- `0x140036284`
- `0x140049cdc`
- `0x140049d48`
- `0x14004dc10`
- `0x14004def0`
- `0x14004e2c8`
- `0x14004e498`
- `0x14005dbb0`
- `0x14005dc30`
- `0x14005e100`
- `0x1400a6550`
- `0x1400a7078`
- `0x1400affbc`
- `0x1400b2ee0`
- `0x1400b36d0`
- `0x1400b5ebc`
- `0x1400b6ca4`
- `0x1400cef98`
- `0x1400cfc8c`
- `0x1400cfd88`
- `0x1400d12bc`
- `0x1400e55ec`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x1400b374b`
- `ntoskrnl!EtwActivityIdControl` at `0x1400b374b`
- `ntoskrnl!ExAllocatePool2` at `0x1400b4202`
- `ntoskrnl!ExAllocatePool2` at `0x1400b4202`

## string_xrefs

- `0x1400b3931`: `Failed to create mirror 0x%08x`
- `0x1400b37ec`: `Failed to update dynamic global policy fields 0x%08x`
- `0x1400b41b3`: `Failed to create the mirror ct log file 0x%08x`
- `0x1400b3d45`: `Failed to send the FSCTL for SMB compression 0x%08x`

## pseudocode

```c
__int64 __fastcall VhdmpiInitializeMirror(
        struct _VHD_HANDLE_CONTEXT *a1,
        struct _VHD_ASYNC_OP_CONTEXT *a2,
        char *a3,
        unsigned int a4)
{
  __int64 v4; // r13
  struct _VHD_BACKING_STORE_HEADER *v7; // r14
  __int64 v8; // r15
  int v11; // r9d
  const wchar_t *v12; // rcx
  unsigned int v13; // ecx
  int updated; // r8d
  unsigned int v15; // edx
  __int64 v16; // rax
  int v17; // eax
  int RctFiles; // edi
  __int64 v19; // rdx
  bool v20; // al
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  __int64 v24; // rdx
  __int64 v25; // rcx
  int v26; // r8d
  const void *v27; // rdi
  int v28; // eax
  __int64 v29; // r9
  unsigned int v30; // edx
  int v31; // r8d
  unsigned int v32; // edx
  int v33; // r8d
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // r9
  int v37; // ebx
  int v38; // eax
  __int64 v39; // r9
  __int64 v40; // rdx
  unsigned __int16 v41; // dx
  char *v42; // rax
  unsigned int v43; // r9d
  __int64 v44; // rax
  __int64 v45; // rbx
  unsigned int v46; // edx
  __int64 v47; // rax
  unsigned int v48; // edx
  __int64 Pool2; // rax
  int v50; // edx
  int v51; // ecx
  int v52; // r8d
  int v53; // ecx
  int v54; // eax
  int *v55; // rax
  const wchar_t *v56; // rcx
  struct _VHD_FILE_MATCHING_CONTEXT *v58; // [rsp+28h] [rbp-D8h]
  _BYTE v59[8]; // [rsp+80h] [rbp-80h] BYREF
  struct _VHD_BACKING_STORE_HEADER *v60; // [rsp+88h] [rbp-78h] BYREF
  int v61; // [rsp+90h] [rbp-70h] BYREF
  int v62; // [rsp+94h] [rbp-6Ch] BYREF
  int v63; // [rsp+98h] [rbp-68h] BYREF
  int v64; // [rsp+9Ch] [rbp-64h] BYREF
  int v65; // [rsp+A0h] [rbp-60h] BYREF
  const wchar_t *v66; // [rsp+A8h] [rbp-58h] BYREF
  struct _VHD_HANDLE_CONTEXT *v67; // [rsp+B0h] [rbp-50h] BYREF
  char v68[8]; // [rsp+B8h] [rbp-48h] BYREF
  const wchar_t *v69; // [rsp+C0h] [rbp-40h] BYREF
  int *v70; // [rsp+C8h] [rbp-38h] BYREF
  const char *v71; // [rsp+D0h] [rbp-30h] BYREF
  struct _UNICODE_STRING v72; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v73; // [rsp+E8h] [rbp-18h] BYREF
  struct _UNICODE_STRING v74; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v75; // [rsp+100h] [rbp+0h] BYREF
  __int64 v76; // [rsp+110h] [rbp+10h]
  GUID ActivityId; // [rsp+118h] [rbp+18h] BYREF
  char *v78; // [rsp+128h] [rbp+28h]
  __int64 v79; // [rsp+130h] [rbp+30h] BYREF
  int v80; // [rsp+138h] [rbp+38h]
  int v81; // [rsp+13Ch] [rbp+3Ch]
  int v82; // [rsp+140h] [rbp+40h]

  v4 = *((_QWORD *)a1 + 7);
  v67 = a1;
  v76 = 0;
  v73 = 0;
  *(_QWORD *)v68 = 0;
  v72 = 0;
  v7 = 0;
  v75 = 0;
  v8 = *(_QWORD *)(v4 + 144);
  ActivityId = 0;
  v78 = 0;
  v60 = 0;
  v74 = 0;
  EtwActivityIdControl(3u, &ActivityId);
  v78 = (char *)a2 + 144;
  if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x10000) )
  {
    v12 = L"Unknown";
    if ( *((_QWORD *)a2 + 21) )
      v12 = (const wchar_t *)*((_QWORD *)a2 + 21);
    v66 = v12;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (_DWORD)v12,
      (unsigned int)byte_14007D69B,
      (unsigned int)&ActivityId,
      v11,
      (__int64)&v66);
  }
  updated = VhdmpiUpdateDynamicGlobalPolicy((__int64)&VhdmpGlobalPolicy);
  if ( updated < 0 )
  {
    v13 = dword_1400876D0;
    if ( (unsigned int)dword_1400876D0 > 3 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x40000) )
        TraceEvents(
          "VhdmpiInitializeMirror",
          0x8Du,
          3u,
          v15,
          "Failed to update dynamic global policy fields 0x%08x",
          updated);
    }
  }
  if ( a4 < 0xC )
    goto LABEL_111;
  v16 = *(unsigned int *)a3;
  if ( (unsigned int)v16 < 0xC )
    goto LABEL_111;
  v13 = *((_DWORD *)a3 + 1);
  if ( !v13 || (v13 & 1) != 0 || a4 < (unsigned int)v16 || a4 - (unsigned int)v16 < v13 )
    goto LABEL_111;
  v72.Length = *((_DWORD *)a3 + 1);
  v72.Buffer = (PWSTR)&a3[v16];
  v17 = *((_DWORD *)a1 + 1);
  v72.MaximumLength = v13;
  if ( (v17 & 1) != 0 )
  {
    RctFiles = -1073741637;
LABEL_112:
    if ( (Microsoft_Windows_VHDMPEnableBits & 4) != 0 )
      McTemplateK0szq_EtwWriteTransfer(
        v13,
        (unsigned int)VhdMetaOpsError,
        updated,
        (unsigned int)"Mirror",
        *(_QWORD *)(*(_QWORD *)(v4 + 144) + 120LL),
        RctFiles);
    VhdmpiCleanupMirror(a2);
    goto LABEL_115;
  }
  *((_BYTE *)a2 + 186) = a3[8];
  *((_BYTE *)a2 + 187) = a3[10];
  RctFiles = VhdmpiAcquireBackingStoreAndRctAccess(
               (struct _VHD_HANDLE_CONTEXT *)((char *)a1 + 16),
               (struct _VHD_BACKING_STORE_HEADER *)v8);
  if ( RctFiles < 0 )
    goto LABEL_112;
  *((_BYTE *)a2 + 184) = 1;
  VhdmpiAcquirePassiveLock(v4 + 1888);
  *(_BYTE *)(v4 + 2080) = 1;
  VhdmpiReleasePassiveLock(v4 + 1888);
  RctFiles = VhdmpiCreateBackingStore(v67, *(struct _BACKING_STORE_PARSER **)v8, &v72, v4, 0, 0, 0, 2u, &v60);
  if ( RctFiles < 0 )
  {
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
      TraceEvents("VhdmpiInitializeMirror", 0xFAu, 2u, 8u, "Failed to create mirror 0x%08x", RctFiles);
    v7 = v60;
    goto LABEL_112;
  }
  *((_BYTE *)a2 + 188) = 0;
  v20 = a3[10] && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v8 + 120LL))(v8);
  v7 = v60;
  if ( v20 )
  {
    if ( *(_BYTE *)(v8 + 1808) )
    {
      if ( byte_14008E397 )
      {
        if ( *((_BYTE *)v60 + 1808) )
        {
          *((_BYTE *)a2 + 188) = 1;
          if ( (unsigned int)dword_1400876D0 > 4 )
          {
            if ( (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x40000) )
              TraceEvents(
                "VhdmpiInitializeMirror",
                0x137u,
                4u,
                0x40000u,
                "Preserving Sparseness when migrating Fixed VHDs because the file sits on ABC.");
          }
        }
      }
    }
    else if ( byte_14008E396 )
    {
      if ( *(_BYTE *)(v8 + 1806) )
      {
        if ( *((_BYTE *)v60 + 1806) )
        {
          v59[0] = 0;
          if ( (int)VhdmpiCheckFileSparse(v8, v59) >= 0 && v59[0] && (int)VhdmpiFileSetSparse(v7) >= 0 )
          {
            if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x40000) )
              TraceEvents(
                "VhdmpiInitializeMirror",
                0x122u,
                4u,
                0x40000u,
                "Preserving Sparseness when migrating Fixed VHDs");
            *((_BYTE *)a2 + 188) = 1;
          }
        }
      }
    }
  }
  *((_BYTE *)v7 + 1809) = 0;
  if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x40000) )
  {
    v60 = (struct _VHD_BACKING_STORE_HEADER *)*((_QWORD *)a2 + 25);
    v61 = *((_DWORD *)a2 + 48);
    v62 = *((unsigned __int8 *)a2 + 188);
    v63 = *((unsigned __int8 *)a2 + 187);
    v64 = *((unsigned __int8 *)v7 + 1808);
    v69 = (const wchar_t *)*((_QWORD *)v7 + 15);
    v65 = *(unsigned __int8 *)(v8 + 1808);
    v70 = *(int **)(v8 + 120);
    LODWORD(v66) = 328;
    v71 = "VhdmpiInitializeMirror";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v21,
      (unsigned int)word_14007D41A,
      v22,
      v23,
      (__int64)&v71,
      (__int64)&v66,
      (__int64)&v70,
      (__int64)&v65,
      (__int64)&v69,
      (__int64)&v64,
      (__int64)&v63,
      (__int64)&v62,
      (__int64)&v61,
      (__int64)&v60);
  }
  if ( (unsigned __int8)VhdmpiIsRemoteSmbFile((char *)v7 + 72, v19) )
  {
    if ( (int)VhdmpiFileWrapperPinFile(v25, 1, 0, v68) >= 0 )
    {
      v27 = *(const void **)v68;
      v28 = VhdmpiSendSyncFSIoControlToFile((char *)v7 + 72, 1311728, *(_QWORD *)v68, 0, 0, 0, 0, 0);
      v29 = 0;
      if ( v28 < 0 && (unsigned int)dword_1400876D0 > 3 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x40000) )
      {
        TraceEvents(
          "VhdmpiInitializeMirror",
          0x178u,
          3u,
          v30,
          "Failed to enable turbo I/O for file object %p with status 0x%08x",
          v27,
          v31);
        v29 = 0;
      }
      if ( a3[9] == 1 || byte_14008E394 == 1 )
      {
        v81 = 1;
        v82 = 2;
        v80 = 2;
        v79 = 0;
        if ( (int)VhdmpiSendSyncFSIoControlToFile((char *)v7 + 72, 1311232, v27, &v79, 20, v29, v29, v29) < 0
          && (unsigned int)dword_1400876D0 > 3
          && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x40000) )
        {
          TraceEvents(
            "VhdmpiInitializeMirror",
            0x19Eu,
            3u,
            v32,
            "Failed to send the FSCTL for SMB compression 0x%08x",
            v33);
        }
      }
      VhdmpiFileWrapperUnpinFile((char *)v7 + 72, 1);
    }
    else if ( (unsigned int)dword_1400876D0 > 3 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x40000) )
    {
      TraceEvents(
        "VhdmpiInitializeMirror",
        0x15Eu,
        3u,
        v24,
        "Failed to pin a safe file reference in the file wrapper 0x%08x",
        v26);
    }
  }
  *((_QWORD *)a2 + 22) = v7;
  if ( (unsigned __int8)VhdmpiIsRctEnabled(v8, v24) )
  {
    RctFiles = VhdmpiCreateRctFiles(v7);
    if ( RctFiles < 0 )
      goto LABEL_112;
  }
  else
  {
    VhdmpiDeleteRctFiles(&v72, v34, v35, v36);
  }
  RctFiles = VhdmpiAcquireRctAccessForBackingStore((struct _VHD_HANDLE_CONTEXT *)((char *)v67 + 16), v7);
  if ( RctFiles < 0 )
    goto LABEL_112;
  *((_BYTE *)a2 + 185) = 1;
  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v8 + 120LL))(v8) )
    v37 = 0;
  else
    v37 = ((*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v8 + 112LL))(v8) != 0) + 1;
  memset((char *)a2 + 524, 0, 0x9Cu);
  *((_DWORD *)a2 + 130) = v37;
  if ( v37 )
    v38 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 232LL))(v8);
  else
    v38 = 0;
  *((_DWORD *)a2 + 131) = v38;
  *((_DWORD *)a2 + 132) = *(_DWORD *)(v8 + 64);
  *((_DWORD *)a2 + 133) = *(_DWORD *)(v8 + 68);
  (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v8 + 216LL))(v8, (char *)a2 + 536);
  *(_OWORD *)((char *)a2 + 552) = *(_OWORD *)((char *)a2 + 536);
  *((_QWORD *)a2 + 71) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 160LL))(v8);
  LOBYTE(v39) = 1;
  *((_QWORD *)a2 + 72) = *(_QWORD *)(v8 + 1144);
  *((_QWORD *)a2 + 73) = v8;
  v75 = (unsigned __int64)a2;
  v76 = 100;
  RctFiles = (*(__int64 (__fastcall **)(struct _VHD_BACKING_STORE_HEADER *, __int128 *, char *, __int64))(*(_QWORD *)v7 + 168LL))(
               v7,
               &v75,
               (char *)a2 + 520,
               v39);
  if ( RctFiles < 0 )
  {
    if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
      goto LABEL_112;
    v41 = 500;
    v42 = "Initializing the new VHD failed 0x%08x";
    goto LABEL_79;
  }
  if ( (unsigned __int8)VhdmpiIsRctEnabled(v7, v40) )
  {
    RctFiles = VhdmpiPopulateRctFiles(*((struct VHD_RCT_STATE **)v7 + 227), 2, *(_QWORD *)(v8 + 1816));
    if ( RctFiles < 0 )
      goto LABEL_112;
  }
  RctFiles = VhdmpiInitAndLoadAndVerifyBackingStore(v7, 3);
  if ( RctFiles < 0 )
  {
    if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
      goto LABEL_112;
    v41 = 527;
    v42 = "Loading the initialized VHD failed 0x%08x";
    goto LABEL_79;
  }
  VhdmpiAcquirePassiveLock(v8 + 1120);
  RctFiles = (*(__int64 (__fastcall **)(struct _VHD_BACKING_STORE_HEADER *))(*(_QWORD *)v7 + 176LL))(v7);
  VhdmpiReleasePassiveLock(v8 + 1120);
  if ( RctFiles < 0 )
  {
    if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
      goto LABEL_112;
    v41 = 545;
    v42 = "Pre-extending the new VHD failed 0x%08x";
LABEL_79:
    v43 = 8;
LABEL_80:
    LODWORD(v58) = RctFiles;
    TraceEvents("VhdmpiInitializeMirror", v41, 2u, v43, v42, v58);
    goto LABEL_112;
  }
  RctFiles = VhdmpiLinkBackingStoreLinkageId(v4, v7, 0);
  if ( RctFiles < 0 )
    goto LABEL_112;
  v44 = (*(__int64 (__fastcall **)(struct _VHD_BACKING_STORE_HEADER *))(*(_QWORD *)v7 + 160LL))(v7);
  *((_QWORD *)a2 + 25) = v44;
  *((_DWORD *)a2 + 48) = dword_14008E390;
  *((_QWORD *)a2 + 14) = v44;
  RctFiles = VhdmpiInitializeInternalIoContext((char *)a2 + 232, (__int64)v7);
  if ( RctFiles < 0 )
    goto LABEL_112;
  *((_BYTE *)a2 + 283) = *((_BYTE *)a2 + 187);
  *((_BYTE *)a2 + 284) = *((_BYTE *)a2 + 188);
  *((_BYTE *)a2 + 680) = 0;
  *((_QWORD *)a2 + 89) = 0;
  if ( !(unsigned __int8)VhdmpiIsCTLogTrackingEnabled(v4) )
    goto LABEL_108;
  v45 = *(_QWORD *)(v4 + 1536);
  if ( !v45 )
  {
LABEL_111:
    RctFiles = -1073741811;
    goto LABEL_112;
  }
  *((_BYTE *)a2 + 680) = 1;
  RctFiles = VhdmpiCTLogMirroringConstructMirrorLogFileName(&v72, v45, &v74);
  if ( RctFiles < 0 )
  {
    if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4096) )
      goto LABEL_112;
    v42 = "Failed to construct the mirror log file name. 0x%08x";
    v43 = v46;
    v41 = 603;
    goto LABEL_80;
  }
  RctFiles = VhdmpiCTLogCreateBackingStore(
               &v74,
               0,
               v45 + 144,
               v45 + 160,
               (struct _VHD_HANDLE_CONTEXT *)((char *)v67 + 248),
               0,
               (const void **)&v73,
               *(_DWORD *)(v45 + 4436));
  v47 = v73;
  if ( v73 )
  {
    *(_BYTE *)(v73 + 4432) = 1;
    *(_QWORD *)(v47 + 72) = v4;
    *((_QWORD *)a2 + 86) = v47;
    Pool2 = ExAllocatePool2(64, 0x800000, 1749305430);
    *((_QWORD *)a2 + 89) = Pool2;
    if ( !Pool2 )
    {
      RctFiles = -1073741670;
      goto LABEL_112;
    }
    VhdmpiSetLogBufferManagerMaxDirtyBufferThreshold((struct _CTLOG_BUFFER_MANAGER *)(v4 + 1912), 0);
LABEL_108:
    VhdmpiTryInitializeMirrorAsyncCopyContext(a2, (struct _VHD_ASYNC_OP_CONTEXT *)((char *)a2 + 720));
    if ( (Microsoft_Windows_VHDMPEnableBits & 8) != 0 )
      McTemplateK0szz_EtwWriteTransfer(
        v51,
        v50,
        v52,
        (unsigned int)"Mirror",
        *(_QWORD *)(v8 + 120),
        *((_QWORD *)v7 + 15));
    RctFiles = 0;
    goto LABEL_115;
  }
  if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4096) )
    TraceEvents("VhdmpiInitializeMirror", 0x26Fu, 2u, v48, "Failed to create the mirror ct log file 0x%08x", RctFiles);
  if ( RctFiles < 0 )
    goto LABEL_112;
LABEL_115:
  VhdmpiFreeFilePath(&v74);
  if ( RctFiles < 0 && (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x10000) )
  {
    LODWORD(v66) = RctFiles;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v53,
      (unsigned int)word_14007D612,
      (unsigned int)&ActivityId,
      (_DWORD)v78,
      (__int64)&v66);
  }
  if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x10000) )
  {
    v71 = (const char *)*((_QWORD *)a2 + 25);
    v65 = *((_DWORD *)a2 + 48);
    v64 = *((unsigned __int8 *)a2 + 188);
    v63 = *((unsigned __int8 *)a2 + 187);
    v62 = *((unsigned __int8 *)a2 + 186);
    v61 = *((unsigned __int8 *)a2 + 185);
    *(_DWORD *)v68 = *((unsigned __int8 *)a2 + 184);
    LODWORD(v66) = RctFiles;
    if ( v7 )
      v54 = *((unsigned __int8 *)v7 + 1808);
    else
      v54 = 0;
    LODWORD(v67) = v54;
    LODWORD(v60) = *(unsigned __int8 *)(v8 + 1808);
    if ( v7 )
      v55 = (int *)*((_QWORD *)v7 + 15);
    else
      v55 = &dword_1400613A4;
    v56 = L"Unknown";
    v70 = v55;
    if ( *((_QWORD *)a2 + 21) )
      v56 = (const wchar_t *)*((_QWORD *)a2 + 21);
    v69 = v56;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (_DWORD)v56,
      (unsigned int)word_14007D4FA,
      (unsigned int)&ActivityId,
      (_DWORD)v78,
      (__int64)&v69,
      (__int64)&v70,
      (__int64)&v60,
      (__int64)&v67,
      (__int64)v68,
      (__int64)&v61,
      (__int64)&v62,
      (__int64)&v63,
      (__int64)&v64,
      (__int64)&v65,
      (__int64)&v71,
      (__int64)&v66);
  }
  return (unsigned int)RctFiles;
}

```

## disassembly

```asm
0x1400b36d0  mov     [rsp-8+arg_18], rbx
0x1400b36d5  push    rbp
0x1400b36d6  push    rsi
0x1400b36d7  push    rdi
0x1400b36d8  push    r12
0x1400b36da  push    r13
0x1400b36dc  push    r14
0x1400b36de  push    r15
0x1400b36e0  lea     rbp, [rsp-50h]
0x1400b36e5  sub     rsp, 150h
0x1400b36ec  mov     rax, cs:__security_cookie
0x1400b36f3  xor     rax, rsp
0x1400b36f6  mov     [rbp+80h+var_38], rax
0x1400b36fa  mov     r13, [rcx+38h]
0x1400b36fe  xor     eax, eax
0x1400b3700  xorps   xmm0, xmm0
0x1400b3703  mov     [rbp+80h+var_D0], rcx
0x1400b3707  xorps   xmm1, xmm1
0x1400b370a  mov     [rbp+80h+var_70], rax
0x1400b370e  mov     rsi, rdx
0x1400b3711  mov     [rbp+80h+var_98], rax
0x1400b3715  mov     rdi, rcx
0x1400b3718  mov     qword ptr [rbp+80h+var_C8], rax
0x1400b371c  movups  [rbp+80h+var_A8], xmm0
0x1400b3720  xor     r14d, r14d
0x1400b3723  lea     ecx, [rax+3]; ControlCode
0x1400b3726  movups  [rbp+80h+var_80], xmm1
0x1400b372a  mov     r15, [r13+90h]
0x1400b3731  lea     rdx, [rbp+80h+ActivityId]; ActivityId
0x1400b3735  movups  xmmword ptr [rbp+80h+ActivityId.Data1], xmm1
0x1400b3739  mov     [rbp+80h+var_58], rax
0x1400b373d  mov     ebx, r9d
0x1400b3740  mov     r12, r8
0x1400b3743  mov     [rbp+80h+var_F8], r14
0x1400b3747  movups  xmmword ptr [rbp+80h+var_90.Length], xmm0
0x1400b374b  call    cs:__imp_EtwActivityIdControl
0x1400b3752  nop     dword ptr [rax+rax+00h]
0x1400b3757  mov     eax, cs:dword_140087708
0x1400b375d  lea     r9, [rsi+90h]
0x1400b3764  mov     [rbp+80h+var_58], r9
0x1400b3768  cmp     eax, 4
0x1400b376b  jbe     short loc_1400B37B4
0x1400b376d  mov     edx, 10000h
0x1400b3772  lea     rcx, dword_140087708
0x1400b3779  call    _tlgKeywordOn
0x1400b377e  test    al, al
0x1400b3780  jz      short loc_1400B37B4
0x1400b3782  mov     rax, [rsi+0A8h]
0x1400b3789  lea     rcx, aUnknown
0x1400b3790  test    rax, rax
0x1400b3793  lea     r8, [rbp+80h+ActivityId]
0x1400b3797  lea     rdx, byte_14007D69B
0x1400b379e  cmovnz  rcx, rax
0x1400b37a2  lea     rax, [rbp+80h+var_D8]
0x1400b37a6  mov     [rsp+180h+var_160], rax
0x1400b37ab  mov     [rbp+80h+var_D8], rcx
0x1400b37af  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z
0x1400b37b4  lea     rcx, VhdmpGlobalPolicy
0x1400b37bb  call    VhdmpiUpdateDynamicGlobalPolicy
0x1400b37c0  mov     r8d, eax
0x1400b37c3  mov     edx, 40000h
0x1400b37c8  test    eax, eax
0x1400b37ca  jns     short loc_1400B3814
0x1400b37cc  mov     ecx, cs:dword_1400876D0
0x1400b37d2  cmp     ecx, 3
0x1400b37d5  jbe     short loc_1400B3814
0x1400b37d7  lea     rcx, dword_1400876D0
0x1400b37de  call    _tlgKeywordOn
0x1400b37e3  test    al, al
0x1400b37e5  jz      short loc_1400B3814
0x1400b37e7  mov     dword ptr [rsp+180h+var_158], r8d; char
0x1400b37ec  lea     rax, aFailedToUpdate
0x1400b37f3  mov     ecx, 8Dh
0x1400b37f8  mov     [rsp+180h+var_160], rax; char *
0x1400b37fd  mov     r9d, edx; int
0x1400b3800  mov     r8d, 3; int
0x1400b3806  mov     edx, ecx; int
0x1400b3808  lea     rcx, aVhdmpiinitiali_16
0x1400b380f  call    TraceEvents
0x1400b3814  cmp     ebx, 0Ch
0x1400b3817  jb      loc_1400B4269
0x1400b381d  mov     eax, [r12]
0x1400b3821  cmp     eax, 0Ch
0x1400b3824  jb      loc_1400B4269
0x1400b382a  mov     ecx, [r12+4]
0x1400b382f  test    ecx, ecx
0x1400b3831  jz      loc_1400B4269
0x1400b3837  test    cl, 1
0x1400b383a  jnz     loc_1400B4269
0x1400b3840  cmp     ebx, eax
0x1400b3842  jb      loc_1400B4269
0x1400b3848  sub     ebx, eax
0x1400b384a  cmp     ebx, ecx
0x1400b384c  jb      loc_1400B4269
0x1400b3852  add     rax, r12
0x1400b3855  mov     word ptr [rbp+80h+var_A8], cx
0x1400b3859  mov     qword ptr [rbp+80h+var_A8+8], rax
0x1400b385d  movzx   eax, cx
0x1400b3860  mov     eax, [rdi+4]
0x1400b3863  mov     word ptr [rbp+80h+var_A8+2], cx
0x1400b3867  test    al, 1
0x1400b3869  jz      short loc_1400B3875
0x1400b386b  mov     edi, 0C00000BBh
0x1400b3870  jmp     loc_1400B426E
0x1400b3875  mov     al, [r12+8]
0x1400b387a  lea     rcx, [rdi+10h]; struct VHD_SECURITY_CONTEXT *
0x1400b387e  xor     r9d, r9d
0x1400b3881  mov     [rsi+0BAh], al
0x1400b3887  mov     al, [r12+0Ah]
0x1400b388c  mov     rdx, r15; struct _VHD_BACKING_STORE_HEADER *
0x1400b388f  mov     [rsi+0BBh], al
0x1400b3895  lea     r8d, [r9+2]
0x1400b3899  call    VhdmpiAcquireBackingStoreAndRctAccess
0x1400b389e  mov     edi, eax
0x1400b38a0  test    eax, eax
0x1400b38a2  js      loc_1400B426E
0x1400b38a8  lea     rbx, [r13+760h]
0x1400b38af  mov     byte ptr [rsi+0B8h], 1
0x1400b38b6  mov     rcx, rbx
0x1400b38b9  call    VhdmpiAcquirePassiveLock
0x1400b38be  mov     rcx, rbx
0x1400b38c1  mov     byte ptr [r13+820h], 1
0x1400b38c9  call    VhdmpiReleasePassiveLock
0x1400b38ce  mov     rdx, [r15]; struct _BACKING_STORE_PARSER *
0x1400b38d1  lea     rax, [rbp+80h+var_F8]
0x1400b38d5  mov     rcx, [rbp+80h+var_D0]; struct _VHD_HANDLE_CONTEXT *
0x1400b38d9  lea     r8, [rbp+80h+var_A8]
0x1400b38dd  mov     [rsp+180h+var_140], rax; __int64
0x1400b38e2  mov     r9, r13
0x1400b38e5  mov     [rsp+180h+var_148], 2; int
0x1400b38ed  mov     dword ptr [rsp+180h+var_150], r14d; int
0x1400b38f2  mov     [rsp+180h+var_158], r14; char
0x1400b38f7  mov     dword ptr [rsp+180h+var_160], r14d; int
0x1400b38fc  call    VhdmpiCreateBackingStore
0x1400b3901  mov     edi, eax
0x1400b3903  test    eax, eax
0x1400b3905  jns     short loc_1400B395B
0x1400b3907  mov     eax, cs:dword_1400876D0
0x1400b390d  cmp     eax, 2
0x1400b3910  jbe     short loc_1400B3952
0x1400b3912  mov     edx, 8
0x1400b3917  lea     rcx, dword_1400876D0
0x1400b391e  call    _tlgKeywordOn
0x1400b3923  test    al, al
0x1400b3925  jz      short loc_1400B3952
0x1400b3927  mov     r9d, 8; int
0x1400b392d  mov     dword ptr [rsp+180h+var_158], edi; char
0x1400b3931  lea     rax, aFailedToCreate_1
0x1400b3938  mov     edx, 0FAh; int
0x1400b393d  lea     rcx, aVhdmpiinitiali_16
0x1400b3944  mov     [rsp+180h+var_160], rax; char *
0x1400b3949  lea     r8d, [r9-6]; int
0x1400b394d  call    TraceEvents
0x1400b3952  mov     r14, [rbp+80h+var_F8]
0x1400b3956  jmp     loc_1400B426E
0x1400b395b  mov     [rsi+0BCh], r14b
0x1400b3962  cmp     [r12+0Ah], r14b
0x1400b3967  jz      short loc_1400B3980
0x1400b3969  mov     rax, [r15]
0x1400b396c  mov     rcx, r15
0x1400b396f  mov     rax, [rax+78h]
0x1400b3973  call    _guard_dispatch_icall
0x1400b3978  test    al, al
0x1400b397a  jz      short loc_1400B3980
0x1400b397c  mov     al, 1
0x1400b397e  jmp     short loc_1400B3982
0x1400b3980  xor     al, al
0x1400b3982  mov     r14, [rbp+80h+var_F8]
0x1400b3986  test    al, al
0x1400b3988  jz      loc_1400B3ABD
0x1400b398e  cmp     byte ptr [r15+710h], 0
0x1400b3996  jnz     loc_1400B3A55
0x1400b399c  cmp     cs:byte_14008E396, 0
0x1400b39a3  jz      loc_1400B3ABD
0x1400b39a9  cmp     byte ptr [r15+70Eh], 0
0x1400b39b1  jz      loc_1400B3ABD
0x1400b39b7  cmp     byte ptr [r14+70Eh], 0
0x1400b39bf  jz      loc_1400B3ABD
0x1400b39c5  lea     rdx, [rbp+80h+var_100]
0x1400b39c9  mov     [rbp+80h+var_100], 0
0x1400b39cd  mov     rcx, r15
0x1400b39d0  call    VhdmpiCheckFileSparse
0x1400b39d5  test    eax, eax
0x1400b39d7  js      loc_1400B3ABD
0x1400b39dd  cmp     [rbp+80h+var_100], 0
0x1400b39e1  jz      loc_1400B3ABD
0x1400b39e7  mov     rcx, r14
0x1400b39ea  call    VhdmpiFileSetSparse
0x1400b39ef  test    eax, eax
0x1400b39f1  js      loc_1400B3ABD
0x1400b39f7  mov     eax, cs:dword_1400876D0
0x1400b39fd  cmp     eax, 4
0x1400b3a00  jbe     short loc_1400B3A45
0x1400b3a02  mov     edx, 40000h
0x1400b3a07  lea     rcx, dword_1400876D0
0x1400b3a0e  call    _tlgKeywordOn
0x1400b3a13  lea     rbx, aVhdmpiinitiali_16
0x1400b3a1a  test    al, al
0x1400b3a1c  jz      short loc_1400B3A4C
0x1400b3a1e  lea     rax, aPreservingSpar
0x1400b3a25  mov     edx, 122h; int
0x1400b3a2a  mov     r9d, 40000h; int
0x1400b3a30  mov     [rsp+180h+var_160], rax; char *
0x1400b3a35  mov     r8d, 4; int
0x1400b3a3b  mov     rcx, rbx; int
0x1400b3a3e  call    TraceEvents
0x1400b3a43  jmp     short loc_1400B3A4C
0x1400b3a45  lea     rbx, aVhdmpiinitiali_16
0x1400b3a4c  mov     byte ptr [rsi+0BCh], 1
0x1400b3a53  jmp     short loc_1400B3AC4
0x1400b3a55  cmp     cs:byte_14008E397, 0
0x1400b3a5c  jz      short loc_1400B3ABD
0x1400b3a5e  cmp     byte ptr [r14+710h], 0
0x1400b3a66  jz      short loc_1400B3ABD
0x1400b3a68  mov     byte ptr [rsi+0BCh], 1
0x1400b3a6f  mov     eax, cs:dword_1400876D0
0x1400b3a75  cmp     eax, 4
0x1400b3a78  jbe     short loc_1400B3ABD
0x1400b3a7a  mov     edx, 40000h
0x1400b3a7f  lea     rcx, dword_1400876D0
0x1400b3a86  call    _tlgKeywordOn
0x1400b3a8b  lea     rbx, aVhdmpiinitiali_16
0x1400b3a92  test    al, al
0x1400b3a94  jz      short loc_1400B3AC4
0x1400b3a96  lea     rax, aPreservingSpar_0
0x1400b3a9d  mov     edx, 137h; int
0x1400b3aa2  mov     r9d, 40000h; int
0x1400b3aa8  mov     [rsp+180h+var_160], rax; char *
0x1400b3aad  mov     r8d, 4; int
0x1400b3ab3  mov     rcx, rbx; int
0x1400b3ab6  call    TraceEvents
0x1400b3abb  jmp     short loc_1400B3AC4
0x1400b3abd  lea     rbx, aVhdmpiinitiali_16
0x1400b3ac4  mov     byte ptr [r14+711h], 0
0x1400b3acc  mov     eax, cs:dword_1400876D0
0x1400b3ad2  cmp     eax, 4
0x1400b3ad5  jbe     loc_1400B3BB3
0x1400b3adb  mov     edx, 40000h
0x1400b3ae0  lea     rcx, dword_1400876D0
0x1400b3ae7  call    _tlgKeywordOn
0x1400b3aec  test    al, al
0x1400b3aee  jz      loc_1400B3BB3
0x1400b3af4  mov     rax, [rsi+0C8h]
0x1400b3afb  lea     rdx, word_14007D41A
0x1400b3b02  mov     [rbp+80h+var_F8], rax
0x1400b3b06  mov     eax, [rsi+0C0h]
0x1400b3b0c  mov     [rbp+80h+var_F0], eax
0x1400b3b0f  movzx   eax, byte ptr [rsi+0BCh]
0x1400b3b16  mov     [rbp+80h+var_EC], eax
0x1400b3b19  movzx   eax, byte ptr [rsi+0BBh]
0x1400b3b20  mov     [rbp+80h+var_E8], eax
0x1400b3b23  movzx   eax, byte ptr [r14+710h]
0x1400b3b2b  mov     [rbp+80h+var_E4], eax
0x1400b3b2e  mov     rax, [r14+78h]
0x1400b3b32  mov     [rbp+80h+var_C0], rax
0x1400b3b36  movzx   eax, byte ptr [r15+710h]
0x1400b3b3e  mov     [rbp+80h+var_E0], eax
0x1400b3b41  mov     rax, [r15+78h]
0x1400b3b45  mov     [rbp+80h+var_B8], rax
0x1400b3b49  lea     rax, [rbp+80h+var_F8]
0x1400b3b4d  mov     [rsp+180h+var_118], rax
0x1400b3b52  lea     rax, [rbp+80h+var_F0]
0x1400b3b56  mov     [rsp+180h+var_120], rax
0x1400b3b5b  lea     rax, [rbp+80h+var_EC]
0x1400b3b5f  mov     [rsp+180h+var_128], rax
0x1400b3b64  lea     rax, [rbp+80h+var_E8]
0x1400b3b68  mov     [rsp+180h+var_130], rax
0x1400b3b6d  lea     rax, [rbp+80h+var_E4]
0x1400b3b71  mov     [rsp+180h+var_138], rax
0x1400b3b76  lea     rax, [rbp+80h+var_C0]
0x1400b3b7a  mov     [rsp+180h+var_140], rax
0x1400b3b7f  lea     rax, [rbp+80h+var_E0]
0x1400b3b83  mov     qword ptr [rsp+180h+var_148], rax
0x1400b3b88  lea     rax, [rbp+80h+var_B8]
0x1400b3b8c  mov     [rsp+180h+var_150], rax
0x1400b3b91  lea     rax, [rbp+80h+var_D8]
0x1400b3b95  mov     [rsp+180h+var_158], rax
0x1400b3b9a  lea     rax, [rbp+80h+var_B0]
0x1400b3b9e  mov     [rsp+180h+var_160], rax
0x1400b3ba3  mov     dword ptr [rbp+80h+var_D8], 148h
0x1400b3baa  mov     [rbp+80h+var_B0], rbx
0x1400b3bae  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U3@U2@U2@U2@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@454444AEBU?$_tlgWrapperByVal@$07@@@Z
0x1400b3bb3  lea     rbx, [r14+48h]
0x1400b3bb7  mov     rcx, rbx
0x1400b3bba  call    VhdmpiIsRemoteSmbFile
0x1400b3bbf  xor     edi, edi
0x1400b3bc1  test    al, al
0x1400b3bc3  jz      loc_1400B3D7A
0x1400b3bc9  lea     r9, [rbp+80h+var_C8]
0x1400b3bcd  xor     r8d, r8d
0x1400b3bd0  lea     edx, [rdi+1]
0x1400b3bd3  call    VhdmpiFileWrapperPinFile
0x1400b3bd8  mov     r8d, eax
0x1400b3bdb  test    eax, eax
0x1400b3bdd  jns     short loc_1400B3C37
0x1400b3bdf  mov     ecx, cs:dword_1400876D0
0x1400b3be5  cmp     ecx, 3
0x1400b3be8  jbe     loc_1400B3D7A
0x1400b3bee  mov     edx, 40000h
0x1400b3bf3  lea     rcx, dword_1400876D0
  ... truncated ...
```
