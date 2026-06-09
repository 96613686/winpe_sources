# BlbRestoreFilesThreadFunc(void *)

- ea: `0x140070400`
- end: `0x140071037`
- name: `?BlbRestoreFilesThreadFunc@@YAKPEAX@Z`
- size: `3127`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `31`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140006948`
- `0x140006ca8`
- `0x14000aee8`
- `0x14000b0bc`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140013008`
- `0x140014200`
- `0x140014384`
- `0x14002cbe8`
- `0x14003c434`
- `0x140070400`
- `0x140071438`
- `0x140071490`
- `0x1400715e4`
- `0x140071874`
- `0x140071f1c`
- `0x1400736b0`
- `0x140073fe8`
- `0x14007404c`
- `0x1400740d8`
- `0x140074138`
- `0x1400741b4`
- `0x140074230`
- `0x14008b088`
- `0x140092a20`
- `0x1400d740c`
- `0x1400e0f24`
- `0x1400e1424`
- `0x1400e2c70`
- `0x140137010`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x140070844`
- `KERNEL32!GetTickCount` at `0x14007087e`
- `KERNEL32!GetTickCount` at `0x140070aa9`
- `KERNEL32!GetTickCount` at `0x140070b0a`
- `KERNEL32!GetTickCount` at `0x140070844`
- `KERNEL32!GetTickCount` at `0x14007087e`
- `KERNEL32!GetTickCount` at `0x140070aa9`
- `KERNEL32!GetTickCount` at `0x140070b0a`
- `msvcrt!_wcsicmp` at `0x140070907`
- `msvcrt!_wcsicmp` at `0x14007091f`
- `msvcrt!_wcsicmp` at `0x1400709c7`
- `msvcrt!_wcsicmp` at `0x140070907`
- `msvcrt!_wcsicmp` at `0x14007091f`
- `msvcrt!_wcsicmp` at `0x1400709c7`
- `ole32!CoTaskMemFree` at `0x140070d27`
- `ole32!CoTaskMemFree` at `0x140070d38`
- `ole32!CoTaskMemFree` at `0x140070d49`
- `ole32!CoTaskMemFree` at `0x140070def`
- `ole32!CoTaskMemFree` at `0x140070df8`
- `ole32!CoTaskMemFree` at `0x140070e12`
- `ole32!CoTaskMemFree` at `0x140070e3b`
- `ole32!CoTaskMemFree` at `0x140070e7b`
- `ole32!CoTaskMemFree` at `0x140070e85`
- `ole32!CoTaskMemFree` at `0x140070e8e`
- `ole32!CoTaskMemFree` at `0x140070ea0`
- `ole32!CoTaskMemFree` at `0x140070eaa`
- `ole32!CoTaskMemFree` at `0x140070eb4`
- `ole32!CoTaskMemFree` at `0x140070ebd`
- `ole32!CoTaskMemFree` at `0x140070d27`
- `ole32!CoTaskMemFree` at `0x140070d38`
- `ole32!CoTaskMemFree` at `0x140070d49`
- `ole32!CoTaskMemFree` at `0x140070def`
- `ole32!CoTaskMemFree` at `0x140070df8`
- `ole32!CoTaskMemFree` at `0x140070e12`
- `ole32!CoTaskMemFree` at `0x140070e3b`
- `ole32!CoTaskMemFree` at `0x140070e7b`
- `ole32!CoTaskMemFree` at `0x140070e85`
- `ole32!CoTaskMemFree` at `0x140070e8e`
- `ole32!CoTaskMemFree` at `0x140070ea0`
- `ole32!CoTaskMemFree` at `0x140070eaa`
- `ole32!CoTaskMemFree` at `0x140070eb4`
- `ole32!CoTaskMemFree` at `0x140070ebd`
- `ole32!CoCreateInstance` at `0x140070636`
- `ole32!CoCreateInstance` at `0x140070636`
- `ole32!CoInitializeEx` at `0x14007054d`
- `ole32!CoInitializeEx` at `0x14007054d`
- `ole32!CoUninitialize` at `0x140070ec9`
- `ole32!CoUninitialize` at `0x140070ec9`
- `OLEAUT32!__imp_SysFreeString` at `0x1400709de`
- `OLEAUT32!__imp_SysFreeString` at `0x1400709e9`
- `OLEAUT32!__imp_SysFreeString` at `0x140070dcd`
- `OLEAUT32!__imp_SysFreeString` at `0x140070dd8`
- `OLEAUT32!__imp_SysFreeString` at `0x1400709de`
- `OLEAUT32!__imp_SysFreeString` at `0x1400709e9`
- `OLEAUT32!__imp_SysFreeString` at `0x140070dcd`
- `OLEAUT32!__imp_SysFreeString` at `0x140070dd8`

## string_xrefs

- `0x140070ccb`: `base\stor\blb\engine\service\restorefiles.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall BlbRestoreFilesThreadFunc(char *Parameter)
{
  const wchar_t **v2; // rdi
  CBlbRestoreFileContext *v3; // r14
  int v4; // r15d
  HRESULT RestoreFileNames; // r12d
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  unsigned __int16 *v10; // rbx
  wchar_t *v11; // rsi
  wchar_t *v12; // rbx
  DWORD TickCount; // ebx
  int v14; // esi
  PVOID *v15; // rcx
  int v16; // ebx
  bool v17; // bl
  char v18; // si
  PVOID *v19; // rcx
  const wchar_t *v20; // r9
  char v21; // al
  const wchar_t *v22; // r9
  const wchar_t *v23; // r9
  DWORD v24; // r15d
  __int64 (__fastcall *v25)(struct IBlbsrvRestoreFiles *, _QWORD, __int64, _QWORD, int, __int64, char *, __int64); // r14
  __int64 v26; // rbx
  char v27; // di
  char v28; // si
  unsigned int OverwriteOption; // eax
  __int64 v30; // r8
  int v31; // edi
  __int64 v32; // rax
  __int64 v33; // rbx
  __int64 v34; // rsi
  __int64 v35; // rbx
  unsigned __int16 **v36; // rax
  unsigned __int16 *v37; // rcx
  LPVOID *v38; // rbx
  CBlbAsync *v39; // rbx
  LPVOID *ppva; // [rsp+20h] [rbp-89h]
  int ppv; // [rsp+20h] [rbp-89h]
  __int64 v43; // [rsp+28h] [rbp-81h]
  unsigned __int16 *v44; // [rsp+50h] [rbp-59h]
  wchar_t *v45; // [rsp+58h] [rbp-51h]
  struct IBlbsrvRestoreFiles *v46; // [rsp+60h] [rbp-49h] BYREF
  unsigned __int16 *v47; // [rsp+68h] [rbp-41h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-39h] BYREF
  unsigned __int16 **v49; // [rsp+78h] [rbp-31h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp-29h] BYREF
  __int64 v51; // [rsp+88h] [rbp-21h] BYREF
  struct _BLBSRV_VOLUME_MAP *v52; // [rsp+90h] [rbp-19h] BYREF
  CBlbRestoreFileContext *v53; // [rsp+98h] [rbp-11h]
  __int64 v54; // [rsp+A0h] [rbp-9h]
  struct _GUID v55; // [rsp+B0h] [rbp+7h] BYREF
  wchar_t *String2; // [rsp+110h] [rbp+67h] BYREF
  char v57; // [rsp+118h] [rbp+6Fh]
  int v58; // [rsp+120h] [rbp+77h]
  unsigned int v59; // [rsp+128h] [rbp+7Fh] BYREF

  v2 = 0;
  pv = 0;
  v52 = 0;
  v57 = 0;
  v46 = 0;
  v51 = 0;
  v3 = 0;
  v44 = 0;
  v47 = 0;
  v45 = 0;
  String2 = 0;
  v59 = 0;
  v4 = 0;
  v58 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
  }
  v49 = 0;
  RestoreFileNames = CBlbRestoreFilesAsync::GetRestoreFileNames((CBlbRestoreFilesAsync *)Parameter, &v49, &v59);
  if ( RestoreFileNames < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_140;
    }
    v7 = 83;
    goto LABEL_10;
  }
  v55 = *(struct _GUID *)(Parameter + 252);
  if ( PublishRestoreStartedEvent(&v55, v49, v59, *(struct _FILETIME *)(Parameter + 536)) < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
  }
  RestoreFileNames = CoInitializeEx(0, 0);
  if ( RestoreFileNames < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_140;
    }
    v9 = 85;
    goto LABEL_21;
  }
  v57 = 1;
  CBlbRestoreFilesAsync::SetState(Parameter, 3);
  RestoreFileNames = (**(__int64 (__fastcall ***)(char *, GUID *, __int64 *))Parameter)(
                       Parameter,
                       &IID_IBlbsrvProgressCallback,
                       &v51);
  if ( RestoreFileNames < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_140;
    }
    v9 = 86;
LABEL_21:
    WPP_SF_d(v8[2], v9, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
    goto LABEL_140;
  }
  RestoreFileNames = CBlbRestoreFilesAsync::GetVolumeMap((CBlbRestoreFilesAsync *)Parameter, &v52);
  if ( RestoreFileNames < 0 )
    goto LABEL_140;
  RestoreFileNames = CoCreateInstance(&CLSID_BlbsrvRestoreFiles, 0, 1u, &IID_IBlbsrvRestoreFiles, (LPVOID *)&v46);
  if ( RestoreFileNames < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_140;
    }
    v7 = 87;
    goto LABEL_10;
  }
  RestoreFileNames = BlbutilGetLoggingPaths(
                       *(struct _FILETIME *)(Parameter + 536),
                       L"FileRestore",
                       L"FileRestore_Error",
                       &v47,
                       &String2);
  if ( RestoreFileNames < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_SSD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        88,
        (unsigned int)WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids,
        (unsigned int)L"FileRestore",
        (__int64)L"FileRestore_Error",
        RestoreFileNames);
    }
    v10 = v47;
    v11 = String2;
    goto LABEL_142;
  }
  v12 = String2;
  v45 = String2;
  v44 = v47;
  RestoreFileNames = (*(__int64 (__fastcall **)(struct IBlbsrvRestoreFiles *, unsigned __int16 *, wchar_t *))(*(_QWORD *)v46 + 40LL))(
                       v46,
                       v47,
                       String2);
  if ( RestoreFileNames < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_140;
    }
    ppva = (LPVOID *)v12;
    v10 = v44;
    WPP_SF_SSD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      89,
      (unsigned int)WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids,
      (_DWORD)v44,
      (__int64)ppva,
      RestoreFileNames);
    goto LABEL_141;
  }
  *((_QWORD *)Parameter + 26) = v44;
  v44 = 0;
  *((_QWORD *)Parameter + 27) = v45;
  v45 = 0;
  RestoreFileNames = CBlbRestoreFilesAsync::InitializeExclusions((CBlbRestoreFilesAsync *)Parameter, v46);
  if ( RestoreFileNames < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_140;
    }
    v7 = 90;
LABEL_10:
    WPP_SF_d(v6[2], v7, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
    goto LABEL_140;
  }
  v54 = 0;
  *(_QWORD *)&v55.Data1 = 0;
  LODWORD(v47) = 0;
  if ( !*((_DWORD *)Parameter + 67) )
    goto LABEL_140;
  while ( 1 )
  {
    v3 = (CBlbRestoreFileContext *)(*((_QWORD *)Parameter + 28) + 72LL * *((unsigned int *)Parameter + 58));
    v53 = v3;
    RestoreFileNames = CBlbRestoreFilesAsync::GetRestoreFileSpec(
                         (CBlbRestoreFilesAsync *)Parameter,
                         v3,
                         (struct _BLBSRV_FILESPEC_INFO **)&pv);
    if ( RestoreFileNames < 0 )
    {
      v2 = (const wchar_t **)pv;
      goto LABEL_140;
    }
    CBlbRestoreFileContext::SetState(v3, 2);
    TickCount = GetTickCount();
    v2 = (const wchar_t **)pv;
    v14 = (*(__int64 (__fastcall **)(struct IBlbsrvRestoreFiles *, LPVOID, __int64, struct _BLBSRV_VOLUME_MAP *, int, __int64))(*(_QWORD *)v46 + 24LL))(
            v46,
            pv,
            1,
            v52,
            1,
            v51);
    *((_DWORD *)Parameter + 137) = GetTickCount() - TickCount;
    if ( v14 < 0 )
    {
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
        v15 = (PVOID *)WPP_GLOBAL_Control;
      }
      v4 = v14;
      v58 = v14;
      v16 = -2139619299;
      if ( v14 != -2139619299 )
        v16 = -2139619245;
      goto LABEL_110;
    }
    v17 = 0;
    CBlbRestoreFileContext::SetState(v3, 3);
    if ( !_wcsicmp(v2[1], L"*") || (v18 = 0, !_wcsicmp(v2[1], L"*.*")) )
      v18 = 1;
    v19 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v20 = L"TRUE";
      if ( !v18 )
        v20 = (const wchar_t *)L"FALSE";
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids, v20);
      v19 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( Parameter[628] )
      break;
LABEL_73:
    v21 = 1;
    LOBYTE(String2) = 1;
    if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 1) != 0 && *((_BYTE *)v19 + 25) >= 4u )
    {
      v22 = L"TRUE";
      if ( !v17 )
        v22 = (const wchar_t *)L"FALSE";
      WPP_SF_S(v19[2], 94, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids, v22);
      v19 = (PVOID *)WPP_GLOBAL_Control;
      v21 = (char)String2;
    }
    if ( v18 && (!Parameter[628] || !v17) )
    {
      v21 = 0;
      LOBYTE(String2) = 0;
    }
    if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 1) != 0 && *((_BYTE *)v19 + 25) >= 4u )
    {
      v23 = L"TRUE";
      if ( !v21 )
        v23 = (const wchar_t *)L"FALSE";
      WPP_SF_S(v19[2], 95, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids, v23);
    }
    v24 = GetTickCount();
    v25 = *(__int64 (__fastcall **)(struct IBlbsrvRestoreFiles *, _QWORD, __int64, _QWORD, int, __int64, char *, __int64))(*(_QWORD *)v46 + 32LL);
    v26 = v51;
    v27 = Parameter[317];
    v28 = Parameter[308];
    OverwriteOption = CBlbRestoreFilesAsync::GetOverwriteOption(Parameter);
    LOBYTE(v43) = (_BYTE)String2;
    LOBYTE(ppv) = v27;
    LOBYTE(v30) = v28;
    v31 = v25(v46, OverwriteOption, v30, 0, ppv, v43, Parameter + 420, v26);
    *((_DWORD *)Parameter + 138) = GetTickCount() - v24;
    if ( v31 < 0 )
    {
      if ( v31 != -2147024784 )
        goto LABEL_98;
      LOBYTE(String2) = 0;
      RestoreFileNames = BlbutilIsVolumeDedupOptimized(
                           *((unsigned __int16 **)Parameter + 35),
                           (unsigned __int8 *)&String2);
      if ( RestoreFileNames >= 0 )
      {
        if ( (_BYTE)String2 )
          v31 = -2139618942;
LABEL_98:
        v15 = (PVOID *)WPP_GLOBAL_Control;
LABEL_99:
        if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 && *((_BYTE *)v15 + 25) >= 2u )
        {
          WPP_SF_d(v15[2], 97, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
          v15 = (PVOID *)WPP_GLOBAL_Control;
        }
      }
      else
      {
        v15 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
            goto LABEL_98;
          }
          goto LABEL_99;
        }
      }
      v4 = v31;
      v58 = v31;
      v16 = -2139619299;
      if ( v31 != -2139619299 )
        v16 = -2139619045;
      v3 = v53;
LABEL_109:
      v2 = (const wchar_t **)pv;
LABEL_110:
      if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 && *((_BYTE *)v15 + 25) >= 2u )
        WPP_SF_d(v15[2], 98, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
      CBlbRestoreFileContext::SetAborted(v3, v16, v4);
      if ( v4 < 0 && IsCriticalError(v4) || v16 == -2139619299 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
        }
        RestoreFileNames = -2139619299;
        goto LABEL_140;
      }
      goto LABEL_127;
    }
    v3 = v53;
    v32 = *((_QWORD *)v53 + 4);
    if ( v32 )
    {
      if ( *((__int64 *)v53 + 5) > 0 )
      {
        if ( v32 <= 0 )
          BlbAssert(
            "base\\stor\\blb\\engine\\service\\restorefiles.cpp",
            0xA86u,
            "pRestoreFileContext->m_cNumberOfFilesProcessed > 0");
        CBlbRestoreFileContext::SetResult(v3, -2139619173, 0);
      }
    }
    else if ( *((__int64 *)v53 + 5) > 0 )
    {
      v16 = -2139619174;
      v15 = (PVOID *)WPP_GLOBAL_Control;
      v4 = v58;
      goto LABEL_109;
    }
    CBlbRestoreFileContext::SetState(v3, 5);
    v2 = (const wchar_t **)pv;
    v4 = v58;
LABEL_127:
    v33 = *((_QWORD *)v3 + 4) + v54;
    v54 = v33;
    v34 = *((_QWORD *)v3 + 5) + *(_QWORD *)&v55.Data1;
    *(_QWORD *)&v55.Data1 = v34;
    *((_QWORD *)Parameter + 70) += *((_QWORD *)v3 + 3);
    if ( v2 )
    {
      CoTaskMemFree((LPVOID)*v2);
      *v2 = 0;
      CoTaskMemFree((LPVOID)v2[1]);
      v2[1] = 0;
      CoTaskMemFree(v2);
      v2 = 0;
      pv = 0;
    }
    CBlbAsync::LockedIncrement((CBlbAsync *)(Parameter + 16), (unsigned int *)Parameter + 58);
    LODWORD(v47) = (_DWORD)v47 + 1;
    if ( (unsigned int)v47 >= *((_DWORD *)Parameter + 67) )
    {
      if ( !v33 && v34 > 0 )
        RestoreFileNames = -2139619174;
      goto LABEL_140;
    }
  }
  String2 = 0;
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, *v2);
  SlashTerminate((struct ATL::CComBSTR *)&bstrString);
  RestoreFileNames = ExtractVolumePath((const struct ATL::CComBSTR *)&bstrString, (struct ATL::CComBSTR *)&String2);
  if ( RestoreFileNames >= 0 )
  {
    if ( v18 )
      v17 = _wcsicmp(*v2, String2) == 0;
    SysFreeString(bstrString);
    SysFreeString(String2);
    v19 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_73;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
  }
  SysFreeString(bstrString);
  SysFreeString(String2);
LABEL_140:
  v10 = v44;
LABEL_141:
  v11 = v45;
LABEL_142:
  CoTaskMemFree(v10);
  CoTaskMemFree(v11);
  v35 = 0;
  if ( v59 )
  {
    v36 = v49;
    do
    {
      v37 = v36[v35];
      if ( v37 )
      {
        CoTaskMemFree(v37);
        v36 = v49;
        v49[v35] = 0;
      }
      v35 = (unsigned int)(v35 + 1);
    }
    while ( (unsigned int)v35 < v59 );
    v4 = v58;
  }
  if ( v49 )
    CoTaskMemFree(v49);
  if ( v51 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
  if ( v46 )
  {
    (*(void (__fastcall **)(struct IBlbsrvRestoreFiles *))(*(_QWORD *)v46 + 16LL))(v46);
    v46 = 0;
  }
  if ( v2 )
  {
    CoTaskMemFree((LPVOID)*v2);
    CoTaskMemFree((LPVOID)v2[1]);
    CoTaskMemFree(v2);
  }
  v38 = (LPVOID *)v52;
  if ( v52 )
  {
    CoTaskMemFree(*(LPVOID *)v52);
    CoTaskMemFree(v38[2]);
    CoTaskMemFree(v38[1]);
    CoTaskMemFree(v38);
  }
  if ( v57 )
    CoUninitialize();
  CBlbRestoreFilesAsync::Uninitialize((CBlbRestoreFilesAsync *)Parameter);
  if ( RestoreFileNames >= 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
    }
    CBlbRestoreFilesAsync::SetState(Parameter, 5);
    v39 = (CBlbAsync *)(Parameter + 16);
  }
  else
  {
    v39 = (CBlbAsync *)(Parameter + 16);
    if ( !CBlbAsync::CheckPoint((CBlbAsync *)(Parameter + 16)) )
    {
      RestoreFileNames = -2139618969;
      CBlbRestoreFileContext::SetResult(v3, -2139618969, 0);
      CBlbAsync::SetResult((CBlbAsync *)(Parameter + 16), -2139618969, 0, 0);
    }
    CBlbRestoreFilesAsync::SetAborted((CBlbRestoreFilesAsync *)Parameter, RestoreFileNames, v4);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
    }
  }
  if ( (int)CBlbRestoreFilesAsync::PublishFileRestoreStopEvent((CBlbRestoreFilesAsync *)Parameter, RestoreFileNames) < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
  }
  CBlbAsync::Done(v39);
  (*(void (__fastcall **)(char *))(*(_QWORD *)Parameter + 16LL))(Parameter);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x140070400  push    rbp
0x140070402  push    rbx
0x140070403  push    rsi
0x140070404  push    rdi
0x140070405  push    r12
0x140070407  push    r13
0x140070409  push    r14
0x14007040b  push    r15
0x14007040d  lea     rbp, [rsp-1Fh]
0x140070412  sub     rsp, 0C8h
0x140070419  mov     r13, rcx
0x14007041c  xor     esi, esi
0x14007041e  mov     edi, esi
0x140070420  mov     [rbp+57h+pv], rsi
0x140070424  mov     [rbp+57h+var_70], rsi
0x140070428  mov     [rbp+57h+arg_8], sil
0x14007042c  mov     [rbp+57h+var_A0], rsi
0x140070430  mov     [rbp+57h+var_78], rsi
0x140070434  mov     r14d, esi
0x140070437  mov     eax, esi
0x140070439  mov     [rbp+57h+var_B0], rax
0x14007043d  mov     [rbp+57h+var_98], rax
0x140070441  mov     ebx, esi
0x140070443  mov     [rbp+57h+var_A8], rbx
0x140070447  mov     [rbp+57h+String2], rbx
0x14007044b  mov     [rbp+57h+arg_18], esi
0x14007044e  mov     r15d, esi
0x140070451  mov     [rbp+57h+arg_10], esi
0x140070454  lea     rax, WPP_GLOBAL_Control
0x14007045b  lea     ebx, [rsi+1]
0x14007045e  mov     rcx, cs:WPP_GLOBAL_Control
0x140070465  cmp     rcx, rax
0x140070468  jz      short loc_140070488
0x14007046a  test    [rcx+1Ch], bl
0x14007046d  jz      short loc_140070488
0x14007046f  cmp     byte ptr [rcx+19h], 4
0x140070473  jb      short loc_140070488
0x140070475  lea     edx, [rsi+52h]
0x140070478  lea     r8, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids
0x14007047f  mov     rcx, [rcx+10h]
0x140070483  call    WPP_SF_
0x140070488  mov     [rbp+57h+var_88], rsi
0x14007048c  lea     r8, [rbp+57h+arg_18]; unsigned int *
0x140070490  lea     rdx, [rbp+57h+var_88]; unsigned __int16 ***
0x140070494  mov     rcx, r13; this
0x140070497  call    ?GetRestoreFileNames@CBlbRestoreFilesAsync@@AEAAJAEAPEAPEAGAEAK@Z; CBlbRestoreFilesAsync::GetRestoreFileNames(ushort * * &,ulong &)
0x14007049c  mov     r12d, eax
0x14007049f  test    eax, eax
0x1400704a1  jns     short loc_1400704EA
0x1400704a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400704aa  lea     rax, WPP_GLOBAL_Control
0x1400704b1  cmp     rcx, rax
0x1400704b4  jz      loc_140070DE4
0x1400704ba  test    [rcx+1Ch], bl
0x1400704bd  jz      loc_140070DE4
0x1400704c3  cmp     byte ptr [rcx+19h], 2
0x1400704c7  jb      loc_140070DE4
0x1400704cd  mov     edx, 53h ; 'S'
0x1400704d2  mov     r9d, r12d
0x1400704d5  lea     r8, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids
0x1400704dc  mov     rcx, [rcx+10h]
0x1400704e0  call    WPP_SF_d
0x1400704e5  jmp     loc_140070DE4
0x1400704ea  movups  xmm0, xmmword ptr [r13+0FCh]
0x1400704f2  movdqu  xmmword ptr [rbp+57h+var_50.Data1], xmm0
0x1400704f7  mov     r9, [r13+218h]; struct _FILETIME
0x1400704fe  mov     r8d, [rbp+57h+arg_18]; unsigned int
0x140070502  mov     rdx, [rbp+57h+var_88]; unsigned __int16 **
0x140070506  lea     rcx, [rbp+57h+var_50]; struct _GUID
0x14007050a  call    ?PublishRestoreStartedEvent@@YAJU_GUID@@PEAPEAGIU_FILETIME@@@Z; PublishRestoreStartedEvent(_GUID,ushort * *,uint,_FILETIME)
0x14007050f  test    eax, eax
0x140070511  jns     short loc_140070549
0x140070513  mov     rcx, cs:WPP_GLOBAL_Control
0x14007051a  lea     rdx, WPP_GLOBAL_Control
0x140070521  cmp     rcx, rdx
0x140070524  jz      short loc_140070549
0x140070526  test    [rcx+1Ch], bl
0x140070529  jz      short loc_140070549
0x14007052b  cmp     byte ptr [rcx+19h], 2
0x14007052f  jb      short loc_140070549
0x140070531  mov     edx, 54h ; 'T'
0x140070536  mov     r9d, eax
0x140070539  lea     r8, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids
0x140070540  mov     rcx, [rcx+10h]
0x140070544  call    WPP_SF_d
0x140070549  xor     edx, edx; dwCoInit
0x14007054b  xor     ecx, ecx; pvReserved
0x14007054d  call    cs:__imp_CoInitializeEx
0x140070553  mov     r12d, eax
0x140070556  test    eax, eax
0x140070558  jns     short loc_1400705A1
0x14007055a  mov     rcx, cs:WPP_GLOBAL_Control
0x140070561  lea     rax, WPP_GLOBAL_Control
0x140070568  cmp     rcx, rax
0x14007056b  jz      loc_140070DE4
0x140070571  test    [rcx+1Ch], bl
0x140070574  jz      loc_140070DE4
0x14007057a  cmp     byte ptr [rcx+19h], 2
0x14007057e  jb      loc_140070DE4
0x140070584  mov     edx, 55h ; 'U'
0x140070589  mov     r9d, r12d
0x14007058c  lea     r8, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids
0x140070593  mov     rcx, [rcx+10h]
0x140070597  call    WPP_SF_d
0x14007059c  jmp     loc_140070DE4
0x1400705a1  mov     [rbp+57h+arg_8], bl
0x1400705a4  mov     edx, 3
0x1400705a9  mov     rcx, r13
0x1400705ac  call    ?SetState@CBlbRestoreFilesAsync@@AEAAXW4_BLB_RESTORE_FILES_STATE@@@Z; CBlbRestoreFilesAsync::SetState(_BLB_RESTORE_FILES_STATE)
0x1400705b1  mov     rax, [r13+0]
0x1400705b5  lea     r8, [rbp+57h+var_78]
0x1400705b9  lea     rdx, IID_IBlbsrvProgressCallback
0x1400705c0  mov     rcx, r13
0x1400705c3  mov     rax, [rax]
0x1400705c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400705cb  mov     r12d, eax
0x1400705ce  test    eax, eax
0x1400705d0  jns     short loc_140070603
0x1400705d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400705d9  lea     rax, WPP_GLOBAL_Control
0x1400705e0  cmp     rcx, rax
0x1400705e3  jz      loc_140070DE4
0x1400705e9  test    [rcx+1Ch], bl
0x1400705ec  jz      loc_140070DE4
0x1400705f2  cmp     byte ptr [rcx+19h], 2
0x1400705f6  jb      loc_140070DE4
0x1400705fc  mov     edx, 56h ; 'V'
0x140070601  jmp     short loc_140070589
0x140070603  lea     rdx, [rbp+57h+var_70]; struct _BLBSRV_VOLUME_MAP **
0x140070607  mov     rcx, r13; this
0x14007060a  call    ?GetVolumeMap@CBlbRestoreFilesAsync@@QEAAJPEAPEAU_BLBSRV_VOLUME_MAP@@@Z; CBlbRestoreFilesAsync::GetVolumeMap(_BLBSRV_VOLUME_MAP * *)
0x14007060f  mov     r12d, eax
0x140070612  test    eax, eax
0x140070614  js      loc_140070DE4
0x14007061a  lea     rax, [rbp+57h+var_A0]
0x14007061e  mov     [rsp+100h+ppv], rax; ppv
0x140070623  lea     r9, IID_IBlbsrvRestoreFiles; riid
0x14007062a  mov     r8d, ebx; dwClsContext
0x14007062d  xor     edx, edx; pUnkOuter
0x14007062f  lea     rcx, CLSID_BlbsrvRestoreFiles; rclsid
0x140070636  call    cs:__imp_CoCreateInstance
0x14007063c  mov     r12d, eax
0x14007063f  test    eax, eax
0x140070641  jns     short loc_140070677
0x140070643  mov     rcx, cs:WPP_GLOBAL_Control
0x14007064a  lea     rax, WPP_GLOBAL_Control
0x140070651  cmp     rcx, rax
0x140070654  jz      loc_140070DE4
0x14007065a  test    [rcx+1Ch], bl
0x14007065d  jz      loc_140070DE4
0x140070663  cmp     byte ptr [rcx+19h], 2
0x140070667  jb      loc_140070DE4
0x14007066d  mov     edx, 57h ; 'W'
0x140070672  jmp     loc_1400704D2
0x140070677  lea     rax, [rbp+57h+String2]
0x14007067b  mov     [rsp+100h+ppv], rax; unsigned __int16 **
0x140070680  lea     r9, [rbp+57h+var_98]; unsigned __int16 **
0x140070684  lea     r8, aFilerestoreErr; "FileRestore_Error"
0x14007068b  lea     rdx, aFilerestore; "FileRestore"
0x140070692  mov     rcx, [r13+218h]; struct _FILETIME
0x140070699  call    ?BlbutilGetLoggingPaths@@YAJU_FILETIME@@PEAG1PEAPEAG2@Z; BlbutilGetLoggingPaths(_FILETIME,ushort *,ushort *,ushort * *,ushort * *)
0x14007069e  mov     r12d, eax
0x1400706a1  test    eax, eax
0x1400706a3  jns     short loc_1400706FD
0x1400706a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400706ac  lea     rax, WPP_GLOBAL_Control
0x1400706b3  cmp     rcx, rax
0x1400706b6  jz      short loc_1400706F0
0x1400706b8  test    [rcx+1Ch], bl
0x1400706bb  jz      short loc_1400706F0
0x1400706bd  cmp     byte ptr [rcx+19h], 2
0x1400706c1  jb      short loc_1400706F0
0x1400706c3  mov     edx, 58h ; 'X'
0x1400706c8  mov     dword ptr [rsp+100h+var_D8], r12d
0x1400706cd  lea     rax, aFilerestoreErr; "FileRestore_Error"
0x1400706d4  mov     [rsp+100h+ppv], rax
0x1400706d9  lea     r9, aFilerestore; "FileRestore"
0x1400706e0  lea     r8, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids
0x1400706e7  mov     rcx, [rcx+10h]
0x1400706eb  call    WPP_SF_SSD
0x1400706f0  mov     rbx, [rbp+57h+var_98]
0x1400706f4  mov     rsi, [rbp+57h+String2]
0x1400706f8  jmp     loc_140070DEC
0x1400706fd  mov     rcx, [rbp+57h+var_A0]
0x140070701  mov     rax, [rcx]
0x140070704  mov     rbx, [rbp+57h+String2]
0x140070708  mov     [rbp+57h+var_A8], rbx
0x14007070c  mov     r8, rbx
0x14007070f  mov     rdx, [rbp+57h+var_98]
0x140070713  mov     [rbp+57h+var_B0], rdx
0x140070717  mov     rax, [rax+28h]
0x14007071b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140070720  mov     r12d, eax
0x140070723  test    eax, eax
0x140070725  jns     short loc_140070781
0x140070727  mov     rcx, cs:WPP_GLOBAL_Control
0x14007072e  lea     rax, WPP_GLOBAL_Control
0x140070735  cmp     rcx, rax
0x140070738  jz      loc_140070DE4
0x14007073e  mov     edx, 1
0x140070743  test    [rcx+1Ch], dl
0x140070746  jz      loc_140070DE4
0x14007074c  cmp     byte ptr [rcx+19h], 2
0x140070750  jb      loc_140070DE4
0x140070756  mov     edx, 59h ; 'Y'
0x14007075b  mov     dword ptr [rsp+100h+var_D8], r12d
0x140070760  mov     [rsp+100h+ppv], rbx
0x140070765  mov     rbx, [rbp+57h+var_B0]
0x140070769  mov     r9, rbx
0x14007076c  lea     r8, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids
0x140070773  mov     rcx, [rcx+10h]
0x140070777  call    WPP_SF_SSD
0x14007077c  jmp     loc_140070DE8
0x140070781  mov     rbx, [rbp+57h+var_B0]
0x140070785  mov     [r13+0D0h], rbx
0x14007078c  mov     [rbp+57h+var_B0], rsi
0x140070790  mov     rsi, [rbp+57h+var_A8]
0x140070794  mov     [r13+0D8h], rsi
0x14007079b  xor     esi, esi
0x14007079d  mov     [rbp+57h+var_A8], rsi
0x1400707a1  mov     rdx, [rbp+57h+var_A0]; struct IBlbsrvRestoreFiles *
0x1400707a5  mov     rcx, r13; this
0x1400707a8  call    ?InitializeExclusions@CBlbRestoreFilesAsync@@AEAAJPEAUIBlbsrvRestoreFiles@@@Z; CBlbRestoreFilesAsync::InitializeExclusions(IBlbsrvRestoreFiles *)
0x1400707ad  mov     r12d, eax
0x1400707b0  test    eax, eax
0x1400707b2  jns     short loc_1400707E9
0x1400707b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400707bb  lea     rax, WPP_GLOBAL_Control
0x1400707c2  cmp     rcx, rax
0x1400707c5  jz      loc_140070DE4
0x1400707cb  lea     edx, [rsi+1]
0x1400707ce  test    [rcx+1Ch], dl
0x1400707d1  jz      loc_140070DE4
0x1400707d7  cmp     byte ptr [rcx+19h], 2
0x1400707db  jb      loc_140070DE4
0x1400707e1  lea     edx, [rsi+5Ah]
0x1400707e4  jmp     loc_1400704D2
0x1400707e9  mov     [rbp+57h+var_60], rsi
0x1400707ed  mov     qword ptr [rbp+57h+var_50.Data1], rsi
0x1400707f1  mov     dword ptr [rbp+57h+var_98], esi
0x1400707f4  cmp     [r13+10Ch], esi
0x1400707fb  jbe     loc_140070DE4
0x140070801  lea     rax, [r13+0E8h]
0x140070808  mov     eax, [rax]
0x14007080a  lea     rcx, [rax+rax*8]
0x14007080e  mov     rax, [r13+0E0h]
0x140070815  lea     r14, [rax+rcx*8]
0x140070819  mov     [rbp+57h+var_68], r14
0x14007081d  lea     r8, [rbp+57h+pv]; struct _BLBSRV_FILESPEC_INFO **
0x140070821  mov     rdx, r14; struct CBlbRestoreFileContext *
0x140070824  mov     rcx, r13; this
0x140070827  call    ?GetRestoreFileSpec@CBlbRestoreFilesAsync@@QEAAJPEAVCBlbRestoreFileContext@@PEAPEAU_BLBSRV_FILESPEC_INFO@@@Z; CBlbRestoreFilesAsync::GetRestoreFileSpec(CBlbRestoreFileContext *,_BLBSRV_FILESPEC_INFO * *)
0x14007082c  mov     r12d, eax
0x14007082f  test    eax, eax
0x140070831  js      loc_140070DE0
0x140070837  mov     edx, 2
0x14007083c  mov     rcx, r14
0x14007083f  call    ?SetState@CBlbRestoreFileContext@@QEAAXW4_BLB_RESTORE_FILES_STATE@@@Z; CBlbRestoreFileContext::SetState(_BLB_RESTORE_FILES_STATE)
0x140070844  call    cs:__imp_GetTickCount
0x14007084a  mov     ebx, eax
0x14007084c  mov     rcx, [rbp+57h+var_A0]
0x140070850  mov     rdx, [rcx]
0x140070853  mov     rax, [rdx+18h]
0x140070857  mov     rdx, [rbp+57h+var_78]
0x14007085b  mov     [rsp+100h+var_D8], rdx
0x140070860  mov     edx, 1
0x140070865  mov     dword ptr [rsp+100h+ppv], edx
0x140070869  mov     r9, [rbp+57h+var_70]
0x14007086d  mov     r8d, edx
0x140070870  mov     rdi, [rbp+57h+pv]
0x140070874  mov     rdx, rdi
0x140070877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007087c  mov     esi, eax
0x14007087e  call    cs:__imp_GetTickCount
0x140070884  sub     eax, ebx
0x140070886  mov     [r13+224h], eax
0x14007088d  test    esi, esi
0x14007088f  jns     short loc_1400708ED
0x140070891  mov     rcx, cs:WPP_GLOBAL_Control
0x140070898  lea     rax, WPP_GLOBAL_Control
0x14007089f  cmp     rcx, rax
0x1400708a2  jz      short loc_1400708D3
0x1400708a4  mov     edx, 1
0x1400708a9  test    [rcx+1Ch], dl
0x1400708ac  jz      short loc_1400708D3
0x1400708ae  cmp     byte ptr [rcx+19h], 2
0x1400708b2  jb      short loc_1400708D3
0x1400708b4  mov     edx, 5Bh ; '['
0x1400708b9  mov     r9d, r12d
0x1400708bc  lea     r8, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids
0x1400708c3  mov     rcx, [rcx+10h]
0x1400708c7  call    WPP_SF_d
0x1400708cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400708d3  mov     r15d, esi
0x1400708d6  mov     [rbp+57h+arg_10], esi
0x1400708d9  mov     edx, 8078001Dh
0x1400708de  mov     ebx, edx
0x1400708e0  lea     eax, [rdx+36h]
0x1400708e3  cmp     esi, edx
0x1400708e5  cmovnz  ebx, eax
  ... truncated ...
```
