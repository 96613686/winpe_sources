# CSyncClientSession::Sync(Sync_Hint)

- ea: `0x1800c47f0`
- end: `0x1800c5c4c`
- name: `?Sync@CSyncClientSession@@UEAAJW4Sync_Hint@@@Z`
- size: `5212`
- prototype: ``
- caller_count: `0`
- callee_count: `29`
- tags: `reparse_path, service_task, installer_update, broker_com_uri`

## callees

- `0x180002ab0`
- `0x1800035f8`
- `0x180007e10`
- `0x180007f1c`
- `0x180008108`
- `0x180009188`
- `0x1800091ac`
- `0x18000a694`
- `0x18000a6ec`
- `0x180011314`
- `0x18001133c`
- `0x18001137c`
- `0x180021508`
- `0x18003cab8`
- `0x180058d88`
- `0x180088020`
- `0x1800b83fc`
- `0x1800b9224`
- `0x1800bb948`
- `0x1800c2ab8`
- `0x1800c3318`
- `0x1800c342c`
- `0x1800c3c04`
- `0x1800c466c`
- `0x1800c47f0`
- `0x1800c5c54`
- `0x180113274`
- `0x1801152b4`
- `0x18013e010`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x1800c48d7`
- `KERNEL32!GetTickCount64` at `0x1800c50fe`
- `KERNEL32!GetTickCount64` at `0x1800c59d7`
- `KERNEL32!GetTickCount64` at `0x1800c48d7`
- `KERNEL32!GetTickCount64` at `0x1800c50fe`
- `KERNEL32!GetTickCount64` at `0x1800c59d7`
- `WinSync!__imp_CreateSyncServiceInstance` at `0x1800c4af5`
- `WinSync!__imp_CreateSyncServiceInstance` at `0x1800c4af5`

## pseudocode

```c
// Hidden C++ exception states: #wind=39
__int64 __fastcall CSyncClientSession::Sync(__int64 a1, unsigned int a2)
{
  _BYTE *v3; // rax
  int v4; // r15d
  char v5; // cl
  __int64 v6; // r13
  int v7; // esi
  __int16 v8; // ax
  int v9; // ebx
  unsigned int v10; // r14d
  __int16 v11; // ax
  __int64 v12; // rcx
  __int16 v13; // ax
  enum __MIDL___MIDL_itf_winsync_0000_0000_0004 v14; // ecx
  CSyncClientSession *v15; // rcx
  struct IUnknown *v16; // r13
  __int64 *v17; // r14
  __int16 v18; // ax
  unsigned int v19; // ebx
  PVOID *v20; // rcx
  int v21; // eax
  struct IUnknown *v22; // rdx
  PWSTR v23; // rcx
  PVOID v24; // rcx
  __int64 v25; // rbx
  PVOID v26; // rcx
  __int64 v27; // rcx
  int v28; // esi
  struct IUnknown *v29; // rdx
  struct IChangeUpdater *v30; // rcx
  struct IChangeUpdater *v31; // rcx
  const unsigned __int16 *v32; // r9
  unsigned int v33; // ebx
  struct ISyncFileSystemInterface *v34; // rax
  struct IFileSyncSessionState *v35; // rcx
  struct IFileSyncReplicaMetadata *v36; // rdx
  bool v37; // sf
  __int16 v38; // ax
  PVOID v39; // rcx
  __int64 v40; // rbx
  PVOID v41; // rcx
  __int64 v42; // rax
  PVOID v43; // rcx
  __int16 v44; // ax
  __int64 v45; // rdx
  __int64 v46; // r8
  ULONGLONG v47; // r14
  __int64 v48; // rcx
  __int64 v49; // r9
  __int64 v50; // rcx
  PVOID *v51; // rcx
  char v52; // bl
  __int64 v53; // rdx
  int v54; // ecx
  __int64 v55; // rbx
  __int64 v56; // rcx
  __int64 v57; // rcx
  DWORD v58; // ebx
  __int64 v60; // [rsp+50h] [rbp-B0h] BYREF
  struct IUnknown *v61; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v62; // [rsp+60h] [rbp-A0h]
  struct IChangeUpdater *v63; // [rsp+68h] [rbp-98h] BYREF
  DWORD dwMessageId; // [rsp+70h] [rbp-90h] BYREF
  int v65; // [rsp+74h] [rbp-8Ch]
  char v66; // [rsp+78h] [rbp-88h]
  const char *v67; // [rsp+80h] [rbp-80h]
  __int64 v68; // [rsp+88h] [rbp-78h]
  int v69[2]; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v70; // [rsp+98h] [rbp-68h]
  char v71; // [rsp+9Ch] [rbp-64h]
  char v72[3]; // [rsp+9Dh] [rbp-63h] BYREF
  __int64 v73; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v74; // [rsp+A8h] [rbp-58h]
  __int64 v75; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v76; // [rsp+B8h] [rbp-48h] BYREF
  PWSTR FileName; // [rsp+C0h] [rbp-40h] BYREF
  bool v78; // [rsp+C8h] [rbp-38h] BYREF
  int v79; // [rsp+CCh] [rbp-34h] BYREF
  unsigned int v80; // [rsp+D0h] [rbp-30h]
  unsigned int v81; // [rsp+D4h] [rbp-2Ch]
  __int64 v82; // [rsp+D8h] [rbp-28h] BYREF
  ULONGLONG TickCount64; // [rsp+E0h] [rbp-20h]
  ULONGLONG v84; // [rsp+E8h] [rbp-18h]
  __int64 v85; // [rsp+F0h] [rbp-10h] BYREF
  struct _GUID v86; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int16 v87; // [rsp+110h] [rbp+10h] BYREF
  char v88[2046]; // [rsp+112h] [rbp+12h] BYREF

  v74 = a2;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 15, &WPP_d137b8dcec5f3be627c7f38638002dcc_Traceguids);
    v3 = WPP_GLOBAL_Control;
  }
  v4 = 1;
  if ( (v3[68] & 0x20) == 0 || (v5 = 1, v3[65] < 6u) )
    v5 = 0;
  dwMessageId = 0;
  v65 = 246;
  v66 = v5;
  v67 = "CSyncClientSession::Sync";
  v68 = 0;
  v82 = 0;
  v85 = 0;
  v76 = 0;
  v71 = 0;
  v6 = (a1 + 8) & -(__int64)(a1 != 0);
  v62 = v6;
  LODWORD(v75) = 0;
  v7 = 0;
  v70 = 0;
  v80 = 0;
  v69[0] = 0;
  v81 = 0;
  TickCount64 = GetTickCount64();
  v84 = 0;
  v72[0] = 0;
  if ( !(unsigned int)CFileSyncSessionState::SetActivityStateStarted(*(CFileSyncSessionState **)(a1 + 80)) )
  {
    dwMessageId = -2147418113;
    v8 = 269;
LABEL_10:
    HIWORD(v65) = v8;
    goto LABEL_217;
  }
  dwMessageId = CSyncClientSession::GetSyncMode((CSyncClientSession *)a1, (enum FS_SYNC_MODE *)&v75);
  v8 = 272;
  if ( (dwMessageId & 0x80000000) != 0 )
    goto LABEL_10;
  LOWORD(v65) = 272;
  v9 = v75;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) == 0 )
  {
    v10 = v74;
  }
  else
  {
    v10 = v74;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        16,
        &WPP_d137b8dcec5f3be627c7f38638002dcc_Traceguids,
        v74,
        (_DWORD)v75);
  }
  v11 = 276;
  if ( v9 == 2 )
  {
    dwMessageId = -2147418113;
LABEL_19:
    HIWORD(v65) = v11;
    goto LABEL_217;
  }
  LOWORD(v65) = 276;
  if ( v10 == 16 && v9 != 1 )
  {
    dwMessageId = -2147024736;
    v11 = 278;
    goto LABEL_19;
  }
  dwMessageId = 0;
  LOWORD(v65) = 278;
  *(_QWORD *)(a1 + 136) = 0;
  *(_DWORD *)(a1 + 152) = 1;
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 24LL))((a1 + 8) & -(__int64)(a1 != 0), 3);
    v71 = 1;
  }
  FileName = 0;
  dwMessageId = (*(__int64 (__fastcall **)(_QWORD, PWSTR *))(**(_QWORD **)(a1 + 72) + 56LL))(
                  *(_QWORD *)(a1 + 72),
                  &FileName);
  v11 = 301;
  if ( (dwMessageId & 0x80000000) != 0 )
    goto LABEL_19;
  LOWORD(v65) = 301;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 17, &WPP_d137b8dcec5f3be627c7f38638002dcc_Traceguids, FileName);
  }
  dwMessageId = CPathUtilities::GetNormalizedWin32Path(FileName, &v76);
  v11 = 304;
  if ( (dwMessageId & 0x80000000) != 0 )
    goto LABEL_19;
  LOWORD(v65) = 304;
  if ( (Microsoft_Windows_WorkFoldersEnableBits & 0x40) != 0 )
    McTemplateU0z_EventWriteTransfer(v12, ECSHOST_EVENT_CORESYNC_SYNCPARTNERSHIP_START, v76);
  v60 = 0;
  v61 = 0;
  v86 = 0;
  v79 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 18, &WPP_d137b8dcec5f3be627c7f38638002dcc_Traceguids);
  }
  dwMessageId = CreateSyncServiceInstance(&GUID_34a978e9_e7f2_46da_997b_33efb5413ac5, &v60);
  v13 = 316;
  if ( (dwMessageId & 0x80000000) != 0 )
    goto LABEL_38;
  LOWORD(v65) = 316;
  dwMessageId = (*(__int64 (__fastcall **)(_QWORD, struct _GUID *))(**(_QWORD **)(a1 + 72) + 48LL))(
                  *(_QWORD *)(a1 + 72),
                  &v86);
  v13 = 319;
  if ( (dwMessageId & 0x80000000) != 0
    || (LOWORD(v65) = 319,
        dwMessageId = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)(a1 + 88) + 240LL))(
                        *(_QWORD *)(a1 + 88),
                        &v79),
        v13 = 324,
        (dwMessageId & 0x80000000) != 0)
    || (LOWORD(v65) = 324,
        dwMessageId = CMsfSyncCallback::CreateInstance(v14, (struct ISyncCallback **)&v61),
        v13 = 327,
        (dwMessageId & 0x80000000) != 0) )
  {
LABEL_38:
    HIWORD(v65) = v13;
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v61);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v60);
    goto LABEL_217;
  }
  LOWORD(v65) = 327;
  v16 = v61;
  v17 = (__int64 *)(a1 + 144);
  if ( *(struct IUnknown **)(a1 + 144) != v61 )
    ATL::AtlComPtrAssign((struct IUnknown **)(a1 + 144), v61);
  if ( v9 != 1 )
  {
    LOBYTE(v19) = v74;
    goto LABEL_121;
  }
  v81 = 1;
  v18 = 347;
  if ( (v79 & 1) == 0 || (LOWORD(v65) = 347, v18 = 349, *(_DWORD *)(a1 + 36)) )
  {
    dwMessageId = -2147418113;
LABEL_47:
    HIWORD(v65) = v18;
LABEL_48:
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v61);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v60);
    goto LABEL_216;
  }
  dwMessageId = 0;
  LOWORD(v65) = 349;
  if ( (Microsoft_Windows_WorkFoldersEnableBits & 0x40) != 0 )
    McTemplateU0z_EventWriteTransfer(v15, ECSHOST_EVENT_CORESYNC_RECONCILIATION_SYNC_START, v76);
  v19 = v74;
  if ( v74 == 16 )
    goto LABEL_65;
  if ( (int)CSyncClientSession::IsNamespaceEmpty(v15, v76, v69) >= 0 )
  {
    v21 = v69[0];
    v20 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v20 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 19, &WPP_d137b8dcec5f3be627c7f38638002dcc_Traceguids);
      v20 = (PVOID *)WPP_GLOBAL_Control;
    }
    v21 = 0;
  }
  v80 = v21;
  if ( !v21 )
  {
LABEL_65:
    v73 = 0;
    *(_QWORD *)v69 = 0;
    v63 = 0;
    if ( *(_QWORD *)(a1 + 104) )
    {
      FileName = 0;
      v22 = *(struct IUnknown **)(a1 + 104);
      v23 = 0;
      if ( v22 )
      {
        ATL::AtlComQIPtrAssign((struct IUnknown **)&FileName, v22, &GUID_3ba24905_0be2_4ec7_8943_12bc92b634bf);
        v23 = FileName;
      }
      if ( v23 )
      {
        if ( (Microsoft_Windows_WorkFoldersEnableBits & 0x40) != 0 )
        {
          McTemplateU0z_EventWriteTransfer(v23, ECSHOST_EVENT_CORESYNC_RECONCILIATION_CLEANUP_START, v76);
          v23 = FileName;
        }
        if ( (*(int (__fastcall **)(PWSTR))(*(_QWORD *)v23 + 72LL))(v23) < 0 )
        {
          v24 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 3u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 22, &WPP_d137b8dcec5f3be627c7f38638002dcc_Traceguids);
          }
        }
        else
        {
          v24 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 21, &WPP_d137b8dcec5f3be627c7f38638002dcc_Traceguids);
          }
        }
        if ( (Microsoft_Windows_WorkFoldersEnableBits & 0x40) != 0 )
          McTemplateU0z_EventWriteTransfer(v24, ECSHOST_EVENT_CORESYNC_RECONCILIATION_CLEANUP_STOP, v76);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&FileName);
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 23, &WPP_d137b8dcec5f3be627c7f38638002dcc_Traceguids);
    }
    v25 = v62;
    dwMessageId = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, __int64, int *))(**(_QWORD **)(a1 + 56)
                                                                                            + 24LL))(
                    *(_QWORD *)(a1 + 56),
                    *(_QWORD *)(a1 + 72),
                    *(_QWORD *)(a1 + 80),
                    *(_QWORD *)(a1 + 88),
                    v62,
                    v69);
    if ( (dwMessageId & 0x80000000) == 0 )
    {
      LOWORD(v65) = 413;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 24, &WPP_d137b8dcec5f3be627c7f38638002dcc_Traceguids);
      }
      dwMessageId = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, __int64, struct IChangeUpdater **))(**(_QWORD **)(a1 + 64) + 24LL))(
                      *(_QWORD *)(a1 + 64),
                      *(_QWORD *)(a1 + 72),
                      *(_QWORD *)(a1 + 80),
                      (a1 + 16) & -(__int64)(a1 != 0),
                      v25,
                      &v63);
      if ( (dwMessageId & 0x80000000) == 0 )
      {
        LOWORD(v65) = 420;
        dwMessageId = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64))v69)(
                        *(_QWORD *)v69,
                        &GUID_9e5c7f9b_2c03_4533_940c_6b2b1f2b9418,
                        a1 + 112);
        if ( (dwMessageId & 0x80000000) == 0 )
        {
          LOWORD(v65) = 424;
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 25, &WPP_d137b8dcec5f3be627c7f38638002dcc_Traceguids);
          }
          if ( (Microsoft_Windows_WorkFoldersEnableBits & 0x40) != 0 )
            McTemplateU0z_EventWriteTransfer(v26, ECSHOST_EVENT_CORESYNC_SYNCPARTNERSHIP_DOWNLOAD_START, v76);
          dwMessageId = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IChangeUpdater *, __int64 *))(*(_QWORD *)v60 + 24LL))(
                          v60,
                          *(_QWORD *)v69,
                          v63,
                          &v73);
          if ( (dwMessageId & 0x80000000) == 0 )
          {
            LOWORD(v65) = 428;
            *(_DWORD *)(*v17 + 8) = 0;
            dwMessageId = (*(__int64 (__fastcall **)(__int64, struct IUnknown *))(*(_QWORD *)v73 + 24LL))(v73, v16);
            if ( (dwMessageId & 0x80000000) == 0 )
            {
              LOWORD(v65) = 432;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 26, &WPP_d137b8dcec5f3be627c7f38638002dcc_Traceguids);
              }
              dwMessageId = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v73 + 32LL))(
                              v73,
                              0,
                              &v82);
              if ( (dwMessageId & 0x80000000) == 0 )
              {
                LOWORD(v65) = 438;
                ATL::CComPtrBase<IItemMetadata>::Release(a1 + 112);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v63);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v69);
                ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v73);
                v19 = v74;
                goto LABEL_115;
              }
              HIWORD(v65) = 438;
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v63);
            }
            else
            {
              HIWORD(v65) = 432;
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v63);
            }
          }
          else
          {
            HIWORD(v65) = 428;
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v63);
          }
        }
        else
        {
          HIWORD(v65) = 424;
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v63);
        }
      }
      else
      {
        HIWORD(v65) = 420;
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v63);
      }
    }
    else
    {
      HIWORD(v65) = 413;
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v63);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v69);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v73);
    goto LABEL_48;
  }
  if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 68) & 0x20) != 0 && *((_BYTE *)v20 + 65) >= 4u )
    WPP_SF_(v20[7], 20, &WPP_d137b8dcec5f3be627c7f38638002dcc_Traceguids);
LABEL_115:
  dwMessageId = CSyncClientSession::SetSyncMode(a1, 0);
  v18 = 449;
  if ( (dwMessageId & 0x80000000) != 0 )
    goto LABEL_47;
  LOWORD(v65) = 449;
  if ( (Microsoft_Windows_WorkFoldersEnableBits & 0x40) != 0 )
    McTemplateU0z_EventWriteTransfer(v27, ECSHOST_EVENT_CORESYNC_RECONCILIATION_SYNC_STOP, v76);
  v84 = GetTickCount64() - TickCount64;
  if ( v19 == 16 )
  {
    dwMessageId = 0;
    LOWORD(v65) = 458;
    goto LABEL_48;
  }
LABEL_121:
  dwMessageId = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 80) + 48LL))(*(_QWORD *)(a1 + 80));
  v18 = 465;
  if ( (dwMessageId & 0x80000000) != 0 )
    goto LABEL_47;
  LOWORD(v65) = 465;
  dwMessageId = CSyncClientSession::GetSyncMode((CSyncClientSession *)a1, (enum FS_SYNC_MODE *)&v75);
  v18 = 467;
  if ( (dwMessageId & 0x80000000) != 0 )
    goto LABEL_47;
  LOWORD(v65) = 467;
  v28 = v19 & 8;
  if ( (v19 & 8) != 0 && *(_QWORD *)(a1 + 96) )
  {
    v63 = 0;
    FileName = 0;
    v29 = *(struct IUnknown **)(a1 + 64);
    if ( v29 )
    {
      ATL::AtlComQIPtrAssign((struct IUnknown **)&FileName, v29, &GUID_175b09a8_6c26_4ba7_abfc_22c473b43f88);
      if ( FileName )
        (*(void (__fastcall **)(PWSTR, unsigned __int16 *, _QWORD, _QWORD, struct IChangeUpdater **))(*(_QWORD *)FileName + 24LL))(
          FileName,
          v76,
          *(_QWORD *)(a1 + 88),
          *(_QWORD *)(a1 + 96),
          &v63);
    }
    v30 = v63;
    if ( v63 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 27, &WPP_d137b8dcec5f3be627c7f38638002dcc_Traceguids);
        v30 = v63;
      }
      (*(void (__fastcall **)(struct IChangeUpdater *))(*(_QWORD *)v30 + 24LL))(v30);
      v31 = v63;
      if ( v63 )
      {
        v63 = 0;
        (*(void (__fastcall **)(struct IChangeUpdater *))(*(_QWORD *)v31 + 16LL))(v31);
      }
    }
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&FileName);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v63);
  }
  if ( !*(_DWORD *)(a1 + 32) )
  {
    v32 = 0;
    FileName = 0;
    v33 = 2;
    if ( v28 )
    {
      v78 = 0;
      dwMessageId = CSelectiveWipe::GetEnterpriseIdForEncryption(
                      *(struct ISyncClientPartnership **)(a1 + 72),
                      &v78,
                      (const unsigned __int16 **)&FileName,
                      0);
      if ( (dwMessageId & 0x80000000) != 0 )
      {
        HIWORD(v65) = 511;
        ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v61);
        ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v60);
        v7 = v70;
        v6 = v62;
        goto LABEL_217;
      }
      LOWORD(v65) = 511;
      v33 = 3;
      v32 = FileName;
    }
    v63 = 0;
    v34 = *(struct ISyncFileSystemInterface **)(a1 + 96);
    v35 = *(struct IFileSyncSessionState **)(a1 + 80);
    v36 = *(struct IFileSyncReplicaMetadata **)(a1 + 88);
    if ( v34 )
    {
      dwMessageId = ChangeUpdaterCreateInstance(1, v76, &v86, v32, v36, v34, v35, &v63);
      v37 = (dwMessageId & 0x80000000) != 0;
      v38 = 520;
    }
    else
    {
      dwMessageId = ChangeUpdaterCreateInstance(1, v76, &v86, v32, v36, 0, v35, &v63);
      v37 = (dwMessageId & 0x80000000) != 0;
      v38 = 524;
    }
    if ( v37 )
      goto LABEL_144;
    LOWORD(v65) = v38;
    dwMessageId = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 88) + 232LL))(
                    *(_QWORD *)(a1 + 88),
                    v79 | 2u);
    v38 = 542;
    if ( (dwMessageId & 0x80000000) != 0 )
      goto LABEL_144;
    LOWORD(v65) = 542;
    v39 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 28, &WPP_d137b8dcec5f3be627c7f38638002dcc_Traceguids);
    }
    if ( (Microsoft_Windows_WorkFoldersEnableBits & 0x40) != 0 )
      McTemplateU0z_EventWriteTransfer(v39, ECSHOST_EVENT_CORESYNC_SYNCPARTNERSHIP_CHANGEUPDATE_START, v76);
    dwMessageId = (*(__int64 (__fastcall **)(struct IChangeUpdater *, _QWORD, int *, __int64))(*(_QWORD *)v63 + 24LL))(
                    v63,
                    v33,
                    &v79,
                    a1 + 8);
    v38 = 547;
    if ( (dwMessageId & 0x80000000) != 0
      || (LOWORD(v65) = 547,
          v79 &= ~2u,
          dwMessageId = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 88) + 232LL))(*(_QWORD *)(a1 + 88)),
          v38 = 551,
          (dwMessageId & 0x80000000) != 0) )
    {
LABEL_144:
      HIWORD(v65) = v38;
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v63);
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v61);
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v60);
      v7 = v70;
      goto LABEL_216;
    }
    LOWORD(v65) = 551;
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v63);
  }
  if ( v28 )
    CSyncClientSession::DoTombstoneCleanup((CSyncClientSession *)a1, v76);
  dwMessageId = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 80) + 48LL))(*(_QWORD *)(a1 + 80));
  v7 = 0;
  v18 = 566;
  if ( (dwMessageId & 0x80000000) != 0 )
    goto LABEL_47;
  LOWORD(v65) = 566;
  *(_QWORD *)v69 = 0;
  v75 = 0;
  v73 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 29, &WPP_d137b8dcec5f3be627c7f38638002dcc_Traceguids);
  }
  v40 = v62;
  dwMessageId = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, __int64, int *))(**(_QWORD **)(a1 + 56) + 24LL))(
                  *(_QWORD *)(a1 + 56),
                  *(_QWORD *)(a1 + 72),
                  *(_QWORD *)(a1 + 80),
                  *(_QWORD *)(a1 + 88),
                  v62,
                  v69);
  if ( (dwMessageId & 0x80000000) != 0 )
  {
    HIWORD(v65) = 580;
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v73);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v75);
LABEL_165:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v69);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v61);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v60);
    v7 = v70;
    goto LABEL_216;
  }
  LOWORD(v65) = 580;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 30, &WPP_d137b8dcec5f3be627c7f38638002dcc_Traceguids);
  }
  dwMessageId = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, __int64, __int64 *))(**(_QWORD **)(a1 + 64)
                                                                                               + 24LL))(
                  *(_QWORD *)(a1 + 64),
                  *(_QWORD *)(a1 + 72),
                  *(_QWORD *)(a1 + 80),
                  a1 + 16,
                  v40,
                  &v75);
  if ( (dwMessageId & 0x80000000) != 0 )
  {
    HIWORD(v65) = 587;
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v73);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v75);
    goto LABEL_165;
  }
  LOWORD(v65) = 587;
  dwMessageId = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64))v69)(
                  *(_QWORD *)v69,
                  &GUID_9e5c7f9b_2c03_4533_940c_6b2b1f2b9418,
                  a1 + 112);
  if ( (dwMessageId & 0x80000000) != 0 )
  {
    HIWORD(v65) = 591;
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v73);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v75);
    goto LABEL_165;
  }
  LOWORD(v65) = 591;
  v41 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 31, &WPP_d137b8dcec5f3be627c7f38638002dcc_Traceguids);
  }
  if ( (Microsoft_Windows_WorkFoldersEnableBits & 0x40) != 0 )
    McTemplateU0z_EventWriteTransfer(v41, ECSHOST_EVENT_CORESYNC_SYNCPARTNERSHIP_DOWNLOAD_START, v76);
  dwMessageId = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v60 + 24LL))(
                  v60,
                  *(_QWORD *)v69,
                  v75,
                  &v73);
  if ( (dwMessageId & 0x80000000) != 0 )
  {
    HIWORD(v65) = 595;
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v73);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v75);
    goto LABEL_165;
  }
  LOWORD(v65) = 595;
  v42 = *v17;
  v7 = *(_DWORD *)(*v17 + 8);
  v70 = v7;
  *(_DWORD *)(v42 + 8) = 0;
  dwMessageId = (*(__int64 (__fastcall **)(__int64, struct IUnknown *))(*(_QWORD *)v73 + 24LL))(v73, v16);
  if ( (dwMessageId & 0x80000000) == 0 )
  {
    LOWORD(v65) = 600;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 32, &WPP_d137b8dcec5f3be627c7f38638002dcc_Traceguids);
    }
    dwMessageId = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v73 + 32LL))(v73, 0, &v82);
    if ( (dwMessageId & 0x80000000) == 0 )
    {
      LOWORD(v65) = 603;
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v73);
      dwMessageId = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 80) + 48LL))(*(_QWORD *)(a1 + 80));
      if ( (dwMessageId & 0x80000000) == 0 )
      {
        LOWORD(v65) = 606;
        v63 = 0;
        v43 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 33, &WPP_d137b8dcec5f3be627c7f38638002dcc_Traceguids);
        }
        if ( (Microsoft_Windows_WorkFoldersEnableBits & 0x40) != 0 )
          McTemplateU0z_EventWriteTransfer(v43, ECSHOST_EVENT_CORESYNC_SYNCPARTNERSHIP_UPLOAD_START, v76);
        dwMessageId = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, struct IChangeUpdater **))(*(_QWORD *)v60 + 24LL))(
                        v60,
                        v75,
                        *(_QWORD *)v69,
                        &v63);
        if ( (dwMessageId & 0x80000000) == 0 )
        {
          LOWORD(v65) = 612;
          if ( v7 )
            v7 = 1;
          else
            v7 = *(_DWORD *)(*v17 + 8);
          v70 = v7;
          *(_DWORD *)(*v17 + 8) = 0;
          dwMessageId = (*(__int64 (__fastcall **)(struct IChangeUpdater *, struct IUnknown *))(*(_QWORD *)v63 + 24LL))(
                          v63,
                          v16);
          if ( (dwMessageId & 0x80000000) == 0 )
          {
            LOWORD(v65) = 617;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 34, &WPP_d137b8dcec5f3be627c7f38638002dcc_Traceguids);
            }
            dwMessageId = (*(__int64 (__fastcall **)(struct IChangeUpdater *, _QWORD, __int64 *))(*(_QWORD *)v63 + 32LL))(
                            v63,
                            0,
                            &v85);
            if ( (dwMessageId & 0x80000000) == 0 )
            {
              LOWORD(v65) = 620;
              ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v63);
              ATL::CComPtrBase<IItemMetadata>::Release(a1 + 112);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v75);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v69);
              ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v61);
              ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v60);
              dwMessageId = *(_DWORD *)(a1 + 136);
              v44 = 628;
              if ( (dwMessageId & 0x80000000) != 0
                || (LOWORD(v65) = 628, dwMessageId = *(_DWORD *)(a1 + 140), v44 = 629, (dwMessageId & 0x80000000) != 0) )
              {
                HIWORD(v65) = v44;
              }
              else
              {
                LOWORD(v65) = 629;
              }
              goto LABEL_216;
            }
            HIWORD(v65) = 620;
            ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v63);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v75);
          }
          else
          {
            HIWORD(v65) = 617;
            ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v63);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v75);
          }
        }
        else
        {
          HIWORD(v65) = 612;
          ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v63);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v75);
        }
      }
      else
      {
        HIWORD(v65) = 606;
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v75);
      }
    }
    else
    {
      HIWORD(v65) = 603;
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v73);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v75);
    }
  }
  else
  {
    HIWORD(v65) = 600;
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v73);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v75);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v69);
  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v61);
  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v60);
LABEL_216:
  v6 = v62;
LABEL_217:
  v47 = GetTickCount64() - TickCount64;
  v48 = *(_QWORD *)(a1 + 144);
  if ( v48 )
  {
    if ( v7 )
      v49 = 1;
    else
      v49 = *(unsigned int *)(v48 + 8);
  }
  else
  {
    v49 = v70;
  }
  if ( (Microsoft_Windows_WorkFoldersEnableBits & 0x40) != 0 )
    McTemplateU0zt_EventWriteTransfer(v48, v45, v76, v49);
  v69[0] = 0;
  v50 = *(_QWORD *)(a1 + 112);
  if ( !v50 )
  {
    v51 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_234;
  }
  if ( (*(int (__fastcall **)(__int64, int *, __int64, __int64))(*(_QWORD *)v50 + 32LL))(v50, v69, v46, v49) >= 0 )
    goto LABEL_230;
  v51 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 35, &WPP_d137b8dcec5f3be627c7f38638002dcc_Traceguids);
LABEL_230:
    v51 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !v69[0] )
  {
LABEL_234:
    if ( dwMessageId + 2134375927 > 1 )
      goto LABEL_243;
  }
  if ( (int)CSyncClientSession::SetSyncMode(a1, 2) >= 0 )
  {
    LOBYTE(v75) = Microsoft_Windows_WorkFoldersEnableBits & 1;
    if ( (Microsoft_Windows_WorkFoldersEnableBits & 1) != 0 )
    {
      v87 = 0;
      memset_0(v88, 0, sizeof(v88));
      v52 = dwMessageId;
      CEcsFunctionTracer::GetErrorText(dwMessageId, v53, &v87);
      McTemplateU0zzd_EventWriteTransfer(
        v54,
        (unsigned int)ECSHOST_EVENT_CORESYNC_RECREATE_REPLICA,
        (_DWORD)v76,
        (unsigned int)&v87,
        v52);
    }
    goto LABEL_242;
  }
  v51 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 36, &WPP_d137b8dcec5f3be627c7f38638002dcc_Traceguids);
LABEL_242:
    v51 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_243:
  if ( v6 && v71 )
  {
    (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v6 + 40LL))(v6, dwMessageId, 3);
    v51 = (PVOID *)WPP_GLOBAL_Control;
  }
  v55 = *(_QWORD *)(a1 + 80);
  if ( v51 != &WPP_GLOBAL_Control && (*((_BYTE *)v51 + 68) & 0x20) != 0 && *((_BYTE *)v51 + 65) >= 4u )
    WPP_SF_d(v51[7], 24, WPP_7ff00e9817d339554fdc5e96d7b1e72e_Traceguids);
  _InterlockedExchange((volatile __int32 *)(v55 + 12), 0);
  ATL::CComPtrBase<IItemMetadata>::Release(a1 + 112);
  v56 = *(_QWORD *)(a1 + 144);
  if ( v56 )
  {
    *(_QWORD *)(a1 + 144) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
  }
  if ( (*(int (__fastcall **)(_QWORD, char *))(**(_QWORD **)(a1 + 72) + 88LL))(*(_QWORD *)(a1 + 72), v72) >= 0 && v72[0] )
    v4 = 2;
  CSyncClientSession::LogSessionTelemetry(v57, v74, v81, v80, v4, v84, v47, dwMessageId, *(_DWORD *)(a1 + 152));
  v58 = dwMessageId;
  CEcsMemPtr<unsigned short,0>::~CEcsMemPtr<unsigned short,0>(&v76);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&dwMessageId);
  return v58;
}

```

## disassembly

```asm
0x1800c47f0  mov     [rsp-8+arg_10], rbx
0x1800c47f5  push    rbp
0x1800c47f6  push    rsi
0x1800c47f7  push    rdi
0x1800c47f8  push    r12
0x1800c47fa  push    r13
0x1800c47fc  push    r14
0x1800c47fe  push    r15
0x1800c4800  lea     rbp, [rsp-820h]
0x1800c4808  sub     rsp, 920h
0x1800c480f  mov     rax, cs:__security_cookie
0x1800c4816  xor     rax, rsp
0x1800c4819  mov     [rbp+850h+var_40], rax
0x1800c4820  mov     [rbp+850h+var_8A8], edx
0x1800c4823  mov     rdi, rcx
0x1800c4826  lea     rcx, WPP_GLOBAL_Control
0x1800c482d  mov     rax, cs:WPP_GLOBAL_Control
0x1800c4834  cmp     rax, rcx
0x1800c4837  jz      short loc_1800C4861
0x1800c4839  test    byte ptr [rax+44h], 20h
0x1800c483d  jz      short loc_1800C4861
0x1800c483f  cmp     byte ptr [rax+41h], 6
0x1800c4843  jb      short loc_1800C4861
0x1800c4845  mov     edx, 0Fh
0x1800c484a  lea     r8, WPP_d137b8dcec5f3be627c7f38638002dcc_Traceguids
0x1800c4851  mov     rcx, [rax+38h]
0x1800c4855  call    WPP_SF_
0x1800c485a  mov     rax, cs:WPP_GLOBAL_Control
0x1800c4861  xor     r14d, r14d
0x1800c4864  lea     r15d, [r14+1]
0x1800c4868  test    byte ptr [rax+44h], 20h
0x1800c486c  jz      short loc_1800C4877
0x1800c486e  cmp     byte ptr [rax+41h], 6
0x1800c4872  mov     cl, r15b
0x1800c4875  jnb     short loc_1800C487A
0x1800c4877  mov     cl, r14b
0x1800c487a  mov     [rsp+950h+dwMessageId], r14d
0x1800c487f  mov     [rsp+950h+var_8DC], 0F6h
0x1800c4887  mov     [rsp+950h+var_8D8], cl
0x1800c488b  lea     rax, aCsyncclientses_12; "CSyncClientSession::Sync"
0x1800c4892  mov     [rbp+850h+var_8D0], rax
0x1800c4896  mov     [rbp+850h+var_8C8], r14
0x1800c489a  mov     [rbp+850h+var_878], r14
0x1800c489e  mov     [rbp+850h+var_860], r14
0x1800c48a2  mov     [rbp+850h+var_898], r14
0x1800c48a6  mov     [rbp+850h+var_8B4], r14b
0x1800c48aa  lea     r12, [rdi+8]
0x1800c48ae  mov     rax, rdi
0x1800c48b1  neg     rax
0x1800c48b4  sbb     r13, r13
0x1800c48b7  and     r13, r12
0x1800c48ba  mov     [rsp+950h+var_8F0], r13
0x1800c48bf  mov     dword ptr [rbp+850h+var_8A0], r14d
0x1800c48c3  mov     esi, r14d
0x1800c48c6  mov     [rbp+850h+var_8B8], r14d
0x1800c48ca  mov     eax, r14d
0x1800c48cd  mov     [rbp+850h+var_880], eax
0x1800c48d0  mov     [rbp+850h+var_8C0], eax
0x1800c48d3  mov     [rbp+850h+var_87C], r14d
0x1800c48d7  call    cs:__imp_GetTickCount64
0x1800c48dd  mov     [rbp+850h+var_870], rax
0x1800c48e1  mov     [rbp+850h+var_868], r14
0x1800c48e5  mov     [rbp+850h+var_8B3], r14b
0x1800c48e9  mov     rcx, [rdi+50h]; this
0x1800c48ed  call    ?SetActivityStateStarted@CFileSyncSessionState@@QEAAHXZ; CFileSyncSessionState::SetActivityStateStarted(void)
0x1800c48f2  mov     ebx, 2
0x1800c48f7  test    eax, eax
0x1800c48f9  jnz     short loc_1800C4919
0x1800c48fb  mov     [rsp+950h+dwMessageId], 8000FFFFh
0x1800c4903  mov     eax, 10Dh
0x1800c4908  mov     word ptr [rsp+950h+var_8DC+2], ax
0x1800c490d  lea     r12, WPP_GLOBAL_Control
0x1800c4914  jmp     loc_1800C59D7
0x1800c4919  lea     rdx, [rbp+850h+var_8A0]; enum FS_SYNC_MODE *
0x1800c491d  mov     rcx, rdi; this
0x1800c4920  call    ?GetSyncMode@CSyncClientSession@@AEAAJPEAW4FS_SYNC_MODE@@@Z; CSyncClientSession::GetSyncMode(FS_SYNC_MODE *)
0x1800c4925  mov     [rsp+950h+dwMessageId], eax
0x1800c4929  test    eax, eax
0x1800c492b  mov     eax, 110h
0x1800c4930  js      short loc_1800C4908
0x1800c4932  mov     word ptr [rsp+950h+var_8DC], ax
0x1800c4937  mov     ebx, dword ptr [rbp+850h+var_8A0]
0x1800c493a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c4941  lea     rax, WPP_GLOBAL_Control
0x1800c4948  cmp     rcx, rax
0x1800c494b  jz      short loc_1800C497B
0x1800c494d  test    byte ptr [rcx+44h], 20h
0x1800c4951  jz      short loc_1800C497B
0x1800c4953  mov     r14d, [rbp+850h+var_8A8]
0x1800c4957  cmp     byte ptr [rcx+41h], 4
0x1800c495b  jb      short loc_1800C497F
0x1800c495d  mov     edx, 10h
0x1800c4962  mov     dword ptr [rsp+950h+var_930], ebx
0x1800c4966  mov     r9d, r14d
0x1800c4969  lea     r8, WPP_d137b8dcec5f3be627c7f38638002dcc_Traceguids
0x1800c4970  mov     rcx, [rcx+38h]
0x1800c4974  call    WPP_SF_dd
0x1800c4979  jmp     short loc_1800C497F
0x1800c497b  mov     r14d, [rbp+850h+var_8A8]
0x1800c497f  mov     eax, 114h
0x1800c4984  cmp     ebx, 2
0x1800c4987  jnz     short loc_1800C49A2
0x1800c4989  mov     [rsp+950h+dwMessageId], 8000FFFFh
0x1800c4991  mov     word ptr [rsp+950h+var_8DC+2], ax
0x1800c4996  lea     r12, WPP_GLOBAL_Control
0x1800c499d  jmp     loc_1800C59D2
0x1800c49a2  mov     word ptr [rsp+950h+var_8DC], ax
0x1800c49a7  cmp     r14d, 10h
0x1800c49ab  jnz     short loc_1800C49C1
0x1800c49ad  cmp     ebx, r15d
0x1800c49b0  jz      short loc_1800C49C1
0x1800c49b2  mov     [rsp+950h+dwMessageId], 800700A0h
0x1800c49ba  mov     eax, 116h
0x1800c49bf  jmp     short loc_1800C4991
0x1800c49c1  xor     r14d, r14d
0x1800c49c4  mov     [rsp+950h+dwMessageId], r14d
0x1800c49c9  mov     eax, 116h
0x1800c49ce  mov     word ptr [rsp+950h+var_8DC], ax
0x1800c49d3  mov     [rdi+88h], r14
0x1800c49da  mov     [rdi+98h], r15d
0x1800c49e1  test    r13, r13
0x1800c49e4  jz      short loc_1800C49FE
0x1800c49e6  mov     rax, [r13+0]
0x1800c49ea  lea     edx, [r14+3]
0x1800c49ee  mov     rcx, r13
0x1800c49f1  mov     rax, [rax+18h]
0x1800c49f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c49fa  mov     [rbp+850h+var_8B4], r15b
0x1800c49fe  mov     [rbp+850h+FileName], r14
0x1800c4a02  mov     rcx, [rdi+48h]
0x1800c4a06  mov     rax, [rcx]
0x1800c4a09  lea     rdx, [rbp+850h+FileName]
0x1800c4a0d  mov     rax, [rax+38h]
0x1800c4a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4a16  mov     [rsp+950h+dwMessageId], eax
0x1800c4a1a  test    eax, eax
0x1800c4a1c  mov     eax, 12Dh
0x1800c4a21  js      loc_1800C4991
0x1800c4a27  mov     word ptr [rsp+950h+var_8DC], ax
0x1800c4a2c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c4a33  lea     rax, WPP_GLOBAL_Control
0x1800c4a3a  cmp     rcx, rax
0x1800c4a3d  jz      short loc_1800C4A64
0x1800c4a3f  test    byte ptr [rcx+44h], 20h
0x1800c4a43  jz      short loc_1800C4A64
0x1800c4a45  cmp     byte ptr [rcx+41h], 4
0x1800c4a49  jb      short loc_1800C4A64
0x1800c4a4b  mov     edx, 11h
0x1800c4a50  mov     r9, [rbp+850h+FileName]
0x1800c4a54  lea     r8, WPP_d137b8dcec5f3be627c7f38638002dcc_Traceguids
0x1800c4a5b  mov     rcx, [rcx+38h]
0x1800c4a5f  call    WPP_SF_S
0x1800c4a64  lea     rdx, [rbp+850h+var_898]; unsigned __int16 **
0x1800c4a68  mov     rcx, [rbp+850h+FileName]; FileName
0x1800c4a6c  call    ?GetNormalizedWin32Path@CPathUtilities@@SAJPEBGPEAPEAG@Z; CPathUtilities::GetNormalizedWin32Path(ushort const *,ushort * *)
0x1800c4a71  mov     [rsp+950h+dwMessageId], eax
0x1800c4a75  test    eax, eax
0x1800c4a77  mov     eax, 130h
0x1800c4a7c  js      loc_1800C4991
0x1800c4a82  mov     word ptr [rsp+950h+var_8DC], ax
0x1800c4a87  test    byte ptr cs:Microsoft_Windows_WorkFoldersEnableBits, 40h
0x1800c4a8e  jz      short loc_1800C4AA0
0x1800c4a90  mov     r8, [rbp+850h+var_898]
0x1800c4a94  lea     rdx, ECSHOST_EVENT_CORESYNC_SYNCPARTNERSHIP_START
0x1800c4a9b  call    McTemplateU0z_EventWriteTransfer
0x1800c4aa0  mov     [rsp+950h+var_900], r14
0x1800c4aa5  mov     [rsp+950h+var_8F8], r14
0x1800c4aaa  xorps   xmm0, xmm0
0x1800c4aad  movups  xmmword ptr [rbp+850h+var_858.Data1], xmm0
0x1800c4ab1  mov     [rbp+850h+var_884], r14d
0x1800c4ab5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c4abc  lea     rax, WPP_GLOBAL_Control
0x1800c4ac3  cmp     rcx, rax
0x1800c4ac6  jz      short loc_1800C4AE9
0x1800c4ac8  test    byte ptr [rcx+44h], 20h
0x1800c4acc  jz      short loc_1800C4AE9
0x1800c4ace  cmp     byte ptr [rcx+41h], 4
0x1800c4ad2  jb      short loc_1800C4AE9
0x1800c4ad4  mov     edx, 12h
0x1800c4ad9  lea     r8, WPP_d137b8dcec5f3be627c7f38638002dcc_Traceguids
0x1800c4ae0  mov     rcx, [rcx+38h]
0x1800c4ae4  call    WPP_SF_
0x1800c4ae9  lea     rdx, [rsp+950h+var_900]
0x1800c4aee  lea     rcx, _GUID_34a978e9_e7f2_46da_997b_33efb5413ac5
0x1800c4af5  call    cs:__imp_CreateSyncServiceInstance
0x1800c4afb  mov     [rsp+950h+dwMessageId], eax
0x1800c4aff  test    eax, eax
0x1800c4b01  mov     eax, 13Ch
0x1800c4b06  jns     short loc_1800C4B26
0x1800c4b08  mov     word ptr [rsp+950h+var_8DC+2], ax
0x1800c4b0d  lea     rcx, [rsp+950h+var_8F8]
0x1800c4b12  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800c4b17  lea     rcx, [rsp+950h+var_900]
0x1800c4b1c  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800c4b21  jmp     loc_1800C4996
0x1800c4b26  mov     word ptr [rsp+950h+var_8DC], ax
0x1800c4b2b  mov     rcx, [rdi+48h]
0x1800c4b2f  mov     rax, [rcx]
0x1800c4b32  lea     rdx, [rbp+850h+var_858]
0x1800c4b36  mov     rax, [rax+30h]
0x1800c4b3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4b3f  mov     [rsp+950h+dwMessageId], eax
0x1800c4b43  test    eax, eax
0x1800c4b45  mov     eax, 13Fh
0x1800c4b4a  js      short loc_1800C4B08
0x1800c4b4c  mov     word ptr [rsp+950h+var_8DC], ax
0x1800c4b51  mov     rcx, [rdi+58h]
0x1800c4b55  mov     rax, [rcx]
0x1800c4b58  lea     rdx, [rbp+850h+var_884]
0x1800c4b5c  mov     rax, [rax+0F0h]
0x1800c4b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4b68  mov     [rsp+950h+dwMessageId], eax
0x1800c4b6c  test    eax, eax
0x1800c4b6e  mov     eax, 144h
0x1800c4b73  js      short loc_1800C4B08
0x1800c4b75  mov     word ptr [rsp+950h+var_8DC], ax
0x1800c4b7a  lea     rdx, [rsp+950h+var_8F8]; struct ISyncCallback **
0x1800c4b7f  call    ?CreateInstance@CMsfSyncCallback@@SAJW4__MIDL___MIDL_itf_winsync_0000_0000_0004@@PEAPEAUISyncCallback@@@Z; CMsfSyncCallback::CreateInstance(__MIDL___MIDL_itf_winsync_0000_0000_0004,ISyncCallback * *)
0x1800c4b84  mov     [rsp+950h+dwMessageId], eax
0x1800c4b88  test    eax, eax
0x1800c4b8a  mov     eax, 147h
0x1800c4b8f  js      loc_1800C4B08
0x1800c4b95  mov     word ptr [rsp+950h+var_8DC], ax
0x1800c4b9a  mov     r13, [rsp+950h+var_8F8]
0x1800c4b9f  lea     r14, [rdi+90h]
0x1800c4ba6  cmp     [r14], r13
0x1800c4ba9  jz      short loc_1800C4BB6
0x1800c4bab  mov     rdx, r13; struct IUnknown *
0x1800c4bae  mov     rcx, r14; struct IUnknown **
0x1800c4bb1  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800c4bb6  cmp     ebx, r15d
0x1800c4bb9  jnz     loc_1800C5128
0x1800c4bbf  mov     [rbp+850h+var_87C], r15d
0x1800c4bc3  mov     eax, 15Bh
0x1800c4bc8  test    byte ptr [rbp+850h+var_884], r15b
0x1800c4bcc  jnz     short loc_1800C4BFB
0x1800c4bce  mov     [rsp+950h+dwMessageId], 8000FFFFh
0x1800c4bd6  mov     word ptr [rsp+950h+var_8DC+2], ax
0x1800c4bdb  lea     rcx, [rsp+950h+var_8F8]
0x1800c4be0  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800c4be5  lea     rcx, [rsp+950h+var_900]
0x1800c4bea  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800c4bef  lea     r12, WPP_GLOBAL_Control
0x1800c4bf6  jmp     loc_1800C59CD
0x1800c4bfb  mov     word ptr [rsp+950h+var_8DC], ax
0x1800c4c00  mov     eax, 15Dh
0x1800c4c05  cmp     [rdi+24h], esi
0x1800c4c08  jnz     short loc_1800C4BCE
0x1800c4c0a  mov     [rsp+950h+dwMessageId], esi
0x1800c4c0e  mov     word ptr [rsp+950h+var_8DC], ax
0x1800c4c13  test    byte ptr cs:Microsoft_Windows_WorkFoldersEnableBits, 40h
0x1800c4c1a  jz      short loc_1800C4C2C
0x1800c4c1c  mov     r8, [rbp+850h+var_898]
0x1800c4c20  lea     rdx, ECSHOST_EVENT_CORESYNC_RECONCILIATION_SYNC_START
0x1800c4c27  call    McTemplateU0z_EventWriteTransfer
0x1800c4c2c  mov     ebx, [rbp+850h+var_8A8]
0x1800c4c2f  cmp     ebx, 10h
0x1800c4c32  jz      loc_1800C4CDA
0x1800c4c38  lea     r8, [rbp+850h+var_8C0]; int *
0x1800c4c3c  mov     rdx, [rbp+850h+var_898]; unsigned __int16 *
0x1800c4c40  call    ?IsNamespaceEmpty@CSyncClientSession@@AEAAJPEBGPEAH@Z; CSyncClientSession::IsNamespaceEmpty(ushort const *,int *)
0x1800c4c45  test    eax, eax
0x1800c4c47  jns     short loc_1800C4C8B
0x1800c4c49  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c4c50  lea     rdx, WPP_GLOBAL_Control
0x1800c4c57  cmp     rcx, rdx
0x1800c4c5a  jz      short loc_1800C4C87
0x1800c4c5c  test    byte ptr [rcx+44h], 20h
0x1800c4c60  jz      short loc_1800C4C87
0x1800c4c62  cmp     byte ptr [rcx+41h], 3
0x1800c4c66  jb      short loc_1800C4C87
0x1800c4c68  mov     edx, 13h
0x1800c4c6d  mov     r9d, eax
0x1800c4c70  lea     r8, WPP_d137b8dcec5f3be627c7f38638002dcc_Traceguids
0x1800c4c77  mov     rcx, [rcx+38h]
0x1800c4c7b  call    WPP_SF_d
0x1800c4c80  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c4c87  xor     eax, eax
0x1800c4c89  jmp     short loc_1800C4C95
0x1800c4c8b  mov     eax, [rbp+850h+var_8C0]
0x1800c4c8e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c4c95  mov     [rbp+850h+var_880], eax
0x1800c4c98  test    eax, eax
0x1800c4c9a  jz      short loc_1800C4CDA
0x1800c4c9c  lea     rax, WPP_GLOBAL_Control
0x1800c4ca3  cmp     rcx, rax
0x1800c4ca6  jz      loc_1800C50C5
0x1800c4cac  test    byte ptr [rcx+44h], 20h
0x1800c4cb0  jz      loc_1800C50C5
0x1800c4cb6  cmp     byte ptr [rcx+41h], 4
0x1800c4cba  jb      loc_1800C50C5
0x1800c4cc0  mov     edx, 14h
0x1800c4cc5  lea     r8, WPP_d137b8dcec5f3be627c7f38638002dcc_Traceguids
0x1800c4ccc  mov     rcx, [rcx+38h]
0x1800c4cd0  call    WPP_SF_
0x1800c4cd5  jmp     loc_1800C50C5
0x1800c4cda  mov     [rbp+850h+var_8B0], rsi
0x1800c4cde  mov     qword ptr [rbp+850h+var_8C0], rsi
0x1800c4ce2  mov     [rsp+950h+var_8E8], 0
0x1800c4ceb  cmp     qword ptr [rdi+68h], 0
  ... truncated ...
```
