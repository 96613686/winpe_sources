# WlAccessibilityOnLogon(_WLSM_GLOBAL_CONTEXT *,int)

- ea: `0x1400180f0`
- end: `0x140018e02`
- name: `?WlAccessibilityOnLogon@@YAKPEAU_WLSM_GLOBAL_CONTEXT@@H@Z`
- size: `3346`
- prototype: `__int64 __fastcall(CSession **, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140017240`

## callees

- `0x1400057f4`
- `0x1400180f0`
- `0x140019390`
- `0x1400198e0`
- `0x140019b4c`
- `0x140019df8`
- `0x14001a200`
- `0x140041c34`
- `0x14004df08`
- `0x14005a68c`
- `0x14005a934`
- `0x14005abb4`
- `0x14005ad40`
- `0x14007cf90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x140018314`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x140018522`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14001870e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x140018314`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x140018522`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14001870e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140018639`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140018639`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140018628`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140018628`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400183cb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140018b8b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400183cb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140018b8b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x140018c75`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x140018c75`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400181a7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140018599`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400187ca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400188e4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400181a7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140018599`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400187ca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400188e4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14001821c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400182c5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140018436`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400184df`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140018608`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400186cb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14001821c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400182c5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140018436`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400184df`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140018608`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400186cb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140018379`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140018a48`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140018c13`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140018379`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140018a48`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140018c13`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400183dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140018861`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140018d59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140018d76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140018d90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140018daa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009db32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009dbc7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009dbda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009dbea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009dbfa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400183dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140018861`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140018d59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140018d76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140018d90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140018daa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009db32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009dbc7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009dbda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009dbea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009dbfa`

## string_xrefs

- `0x140018199`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\OOBE`
- `0x14001836b`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility`
- `0x14001858b`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility`
- `0x1400188d6`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility`
- `0x140018c05`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility`
- `0x140018210`: `SettingConfiguration`
- `0x1400182b9`: `SettingConfiguration`
- `0x140018387`: `SettingConfiguration`
- `0x1400183bf`: `SettingConfiguration`
- `0x140018d00`: `atbroker.exe`
- `0x14001842a`: `Configuration`
- `0x1400184d3`: `Configuration`
- `0x1400185fc`: `Configuration`
- `0x1400186bf`: `Configuration`
- `0x140018b46`: `Configuration`
- `0x140018b7f`: `Configuration`
- `0x140018cb8`: `Configuration`
- `0x140018c69`: `ATConfig`

## pseudocode

```c
__int64 __fastcall WlAccessibilityOnLogon(CSession **a1, int a2)
{
  BOOL v4; // r12d
  BOOL v5; // r15d
  int v6; // r14d
  unsigned int v7; // eax
  unsigned int v8; // r8d
  LSTATUS v9; // eax
  BYTE *v10; // rbx
  CUser *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  unsigned int v14; // eax
  LSTATUS v15; // eax
  BYTE *v16; // rbx
  CUser *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r9
  unsigned int v20; // eax
  LSTATUS v21; // eax
  DWORD v22; // ebx
  HANDLE ProcessHeap; // rax
  BYTE *v24; // rbx
  __int64 v25; // rdx
  __int64 v26; // r9
  unsigned int v27; // eax
  CSession *v28; // rax
  unsigned int v29; // ebx
  unsigned int started; // eax
  __int64 v31; // rdx
  __int64 v32; // r9
  CSession *v33; // rax
  __int64 v34; // rdx
  __int64 v35; // r9
  CSession *v36; // rdx
  unsigned int v37; // eax
  HKEY v38; // rcx
  void **phkResult; // [rsp+20h] [rbp-D8h]
  HKEY hKey; // [rsp+58h] [rbp-A0h] BYREF
  HKEY v42; // [rsp+60h] [rbp-98h] BYREF
  HKEY v43; // [rsp+68h] [rbp-90h] BYREF
  DWORD v44; // [rsp+70h] [rbp-88h] BYREF
  HKEY v45; // [rsp+78h] [rbp-80h] BYREF
  BYTE *v46; // [rsp+80h] [rbp-78h] BYREF
  BYTE *v47; // [rsp+88h] [rbp-70h] BYREF
  BYTE *v48; // [rsp+90h] [rbp-68h] BYREF
  HKEY v49; // [rsp+98h] [rbp-60h] BYREF
  int v50; // [rsp+A0h] [rbp-58h]
  BOOL v51; // [rsp+A4h] [rbp-54h]
  BOOL v52; // [rsp+A8h] [rbp-50h]
  LPCWSTR lpSubKey; // [rsp+B0h] [rbp-48h] BYREF
  LPCWSTR v54; // [rsp+B8h] [rbp-40h] BYREF
  HKEY v55; // [rsp+C0h] [rbp-38h] BYREF
  DWORD cbData; // [rsp+110h] [rbp+18h] BYREF
  DWORD lpcbData; // [rsp+118h] [rbp+20h] BYREF

  v49 = 0;
  v43 = 0;
  v42 = 0;
  hKey = 0;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  v7 = CSession::TerminateAtJob(a1[2]);
  if ( v7
    && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids, v7);
  }
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\OOBE",
         0,
         0xF003Fu,
         &hKey) )
  {
    goto LABEL_70;
  }
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids);
  }
  v46 = 0;
  cbData = 0;
  v9 = RegQueryValueExW(hKey, L"SettingConfiguration", 0, 0, 0, &cbData);
  if ( !cbData || v9 )
    goto LABEL_34;
  v10 = (BYTE *)WLAlloc(cbData);
  v46 = v10;
  if ( v10 )
  {
    v14 = RegQueryValueExW(hKey, L"SettingConfiguration", 0, 0, v10, &cbData);
    if ( !v14 )
    {
      if ( (unsigned int)_o__wcsnicmp(L" ", v10, 2) && *v10 )
      {
        v6 = 1;
        v50 = 1;
        v45 = 0;
        if ( !RegCreateKeyExW(
                *((HKEY *)a1[4] + 29),
                L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility",
                0,
                0,
                1u,
                0xF003Fu,
                0,
                &v45,
                0)
          && !WlAccessibilitypCopyConfiguration(v45, hKey, L"SettingConfiguration") )
        {
          RegSetValueExW(hKey, L"SettingConfiguration", 0, 1u, L" ", 4u);
        }
        if ( v45 )
          RegCloseKey(v45);
      }
      else
      {
        v6 = 0;
        v50 = 0;
      }
      goto LABEL_32;
    }
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = 60;
      v13 = v14;
      goto LABEL_18;
    }
  }
  else
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = 59;
      v13 = 14;
LABEL_18:
      WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids, v13);
    }
  }
LABEL_32:
  if ( v10 )
    UHHeapFree(&v46);
LABEL_34:
  v47 = 0;
  lpcbData = 0;
  v15 = RegQueryValueExW(hKey, L"Configuration", 0, 0, 0, &lpcbData);
  if ( !lpcbData || v15 )
  {
LABEL_70:
    v17 = WPP_GLOBAL_Control;
    goto LABEL_55;
  }
  v16 = (BYTE *)WLAlloc(lpcbData);
  v47 = v16;
  if ( v16 )
  {
    v20 = RegQueryValueExW(hKey, L"Configuration", 0, 0, v16, &lpcbData);
    if ( !v20 )
    {
      v5 = (unsigned int)_o__wcsnicmp(L" ", v16, 2) && *v16;
      v51 = v5;
      goto LABEL_52;
    }
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v18 = 62;
      v19 = v20;
      goto LABEL_41;
    }
  }
  else
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v18 = 61;
      v19 = 14;
LABEL_41:
      WPP_SF_d(*((_QWORD *)v17 + 2), v18, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids, v19);
LABEL_52:
      v17 = WPP_GLOBAL_Control;
    }
  }
  if ( v16 )
  {
    UHHeapFree(&v47);
    v17 = WPP_GLOBAL_Control;
  }
LABEL_55:
  if ( v5 && v6 )
    goto LABEL_130;
  if ( RegOpenKeyExW(
         *((HKEY *)a1[4] + 29),
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility",
         0,
         1u,
         &v43) )
  {
    goto LABEL_84;
  }
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids);
  }
  v48 = 0;
  v44 = 0;
  v21 = RegQueryValueExW(v43, L"Configuration", 0, 0, 0, &v44);
  if ( !v44 || v21 )
    goto LABEL_84;
  v22 = v44;
  ProcessHeap = GetProcessHeap();
  v24 = (BYTE *)HeapAlloc(ProcessHeap, 8u, v22);
  v48 = v24;
  if ( v24 )
  {
    v27 = RegQueryValueExW(v43, L"Configuration", 0, 0, v24, &v44);
    if ( !v27 )
    {
      v4 = (unsigned int)_o__wcsnicmp(L" ", v24, 2) && *v24;
      v52 = v4;
      goto LABEL_81;
    }
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_82;
    }
    v25 = 65;
    v26 = v27;
  }
  else
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_82;
    }
    v25 = 64;
    v26 = 14;
  }
  WPP_SF_d(*((_QWORD *)v17 + 2), v25, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids, v26);
LABEL_81:
  v17 = WPP_GLOBAL_Control;
LABEL_82:
  if ( !v24 )
    goto LABEL_85;
  UHHeapFree(&v48);
LABEL_84:
  v17 = WPP_GLOBAL_Control;
LABEL_85:
  if ( !v4 )
  {
    if ( v17 != (CUser *)&WPP_GLOBAL_Control && (*((_DWORD *)v17 + 7) & 0x40000) != 0 && *((_BYTE *)v17 + 25) >= 4u )
      WPP_SF_(*((_QWORD *)v17 + 2), 66, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids);
    v28 = a1[2];
    lpSubKey = 0;
    v29 = WlAccessibilitypConstructSATKeyName(*((_DWORD *)v28 + 22), (unsigned __int16 **)&lpSubKey);
    if ( !v29 )
    {
      v29 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0xF003Fu, &v42);
      UHHeapFree(&lpSubKey);
    }
    if ( v29 == 2 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          67,
          WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids,
          *((unsigned int *)a1[2] + 22));
        v17 = WPP_GLOBAL_Control;
      }
      v29 = 0;
      if ( !v5 && !v6 )
      {
        WlAccessibilityCreateSessionKeyWithPermissions((struct _WLSM_GLOBAL_CONTEXT *)a1, &v42);
LABEL_182:
        v17 = WPP_GLOBAL_Control;
        goto LABEL_183;
      }
    }
    else
    {
      if ( !v29 && !v5 && !v6 )
      {
        if ( v42 )
          RegCloseKey(v42);
        WlAccessibilityCreateSessionKeyWithPermissions((struct _WLSM_GLOBAL_CONTEXT *)a1, &v42);
      }
      v17 = WPP_GLOBAL_Control;
    }
    if ( v29 )
    {
      if ( v17 != (CUser *)&WPP_GLOBAL_Control && (*((_DWORD *)v17 + 7) & 0x40000) != 0 && *((_BYTE *)v17 + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)v17 + 2), 68, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids, v29);
        v17 = WPP_GLOBAL_Control;
      }
      if ( !v5 && !v6 )
        goto LABEL_183;
    }
    started = RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility",
                0,
                1u,
                &v49);
    v29 = started;
    if ( started )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v31 = 69;
LABEL_119:
        v32 = started;
LABEL_120:
        WPP_SF_d(*((_QWORD *)v17 + 2), v31, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids, v32);
        goto LABEL_182;
      }
      goto LABEL_183;
    }
    v29 = WlAccessibilitypCompareConfiguration(v49, v42);
    if ( !v29 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v31 = 70;
        v32 = *((unsigned int *)a1[2] + 22);
        goto LABEL_120;
      }
      goto LABEL_183;
    }
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      LODWORD(phkResult) = *((_DWORD *)a1[2] + 22);
      WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids, v29);
      v17 = WPP_GLOBAL_Control;
    }
  }
LABEL_130:
  if ( v42 )
    goto LABEL_148;
  v55 = 0;
  v42 = 0;
  v33 = a1[2];
  v54 = 0;
  v29 = WlAccessibilitypConstructSATKeyName(*((_DWORD *)v33 + 22), (unsigned __int16 **)&v54);
  if ( !v29 )
  {
    v29 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v54, 0, 0, 1u, 0xF003Fu, 0, &v55, 0);
    UHHeapFree(&v54);
  }
  if ( v29 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v34 = 55;
      v35 = v29;
LABEL_138:
      WPP_SF_d(*((_QWORD *)v17 + 2), v34, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids, v35);
LABEL_146:
      v17 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v29 = 0;
    v36 = a1[4];
    if ( !v36 || (v37 = WlAccessibilitypAclKeyForUser(v55, *((void **)v36 + 20), *((PSID *)v36 + 21)), (v29 = v37) == 0) )
    {
      v42 = v55;
      goto LABEL_146;
    }
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v34 = 56;
      v35 = v37;
      goto LABEL_138;
    }
  }
  if ( v29 )
    goto LABEL_183;
LABEL_148:
  if ( !v5 )
  {
    if ( v4 )
    {
      started = WlAccessibilitypCopyConfiguration(v42, v43, L"Configuration");
      v29 = started;
      if ( started )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v31 = 76;
          goto LABEL_119;
        }
        goto LABEL_183;
      }
    }
LABEL_176:
    started = WlAccessibilitypStartProcessInAtJob((struct _WLSM_GLOBAL_CONTEXT *)a1, L"atbroker.exe", v8, a2, phkResult);
    v29 = started;
    if ( !started )
    {
      v29 = 0;
      goto LABEL_182;
    }
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v31 = 77;
      goto LABEL_119;
    }
    goto LABEL_183;
  }
  if ( v17 != (CUser *)&WPP_GLOBAL_Control && (*((_DWORD *)v17 + 7) & 0x40000) != 0 && *((_BYTE *)v17 + 25) >= 4u )
    WPP_SF_(*((_QWORD *)v17 + 2), 72, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids);
  v29 = WlAccessibilitypCopyConfiguration(v42, hKey, L"Configuration");
  RegSetValueExW(hKey, L"Configuration", 0, 1u, L" ", 4u);
  if ( v29 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v31 = 73;
      v32 = v29;
      goto LABEL_120;
    }
    goto LABEL_183;
  }
  v38 = v43;
  if ( v43 )
  {
LABEL_165:
    v29 = WlAccessibilitypCopyConfigurationSettings(v38, hKey);
    RegDeleteTreeW(hKey, L"ATConfig");
    if ( v29 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v31 = 75;
        v32 = v29;
        goto LABEL_120;
      }
      goto LABEL_183;
    }
    goto LABEL_176;
  }
  started = RegCreateKeyExW(
              *((HKEY *)a1[4] + 29),
              L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility",
              0,
              0,
              1u,
              0xF003Fu,
              0,
              &v43,
              0);
  v29 = started;
  if ( !started )
  {
    v38 = v43;
    goto LABEL_165;
  }
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v31 = 74;
    goto LABEL_119;
  }
LABEL_183:
  if ( v42 )
  {
    RegCloseKey(v42);
    v17 = WPP_GLOBAL_Control;
  }
  if ( v49 )
  {
    RegCloseKey(v49);
    v17 = WPP_GLOBAL_Control;
  }
  if ( v43 )
  {
    RegCloseKey(v43);
    v17 = WPP_GLOBAL_Control;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    v17 = WPP_GLOBAL_Control;
  }
  if ( v17 != (CUser *)&WPP_GLOBAL_Control && (*((_DWORD *)v17 + 7) & 0x40000) != 0 && *((_BYTE *)v17 + 25) >= 4u )
    WPP_SF_d(*((_QWORD *)v17 + 2), 78, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids, v29);
  return v29;
}

```

## disassembly

```asm
0x1400180f0  mov     [rsp+arg_0], rbx
0x1400180f5  mov     [rsp+arg_8], rsi
0x1400180fa  push    rdi
0x1400180fb  push    r12
0x1400180fd  push    r13
0x1400180ff  push    r14
0x140018101  push    r15
0x140018103  sub     rsp, 0D0h
0x14001810a  mov     r13d, edx
0x14001810d  mov     rsi, rcx
0x140018110  xor     ebx, ebx
0x140018112  mov     [rsp+0F8h+var_60], rbx
0x14001811a  mov     [rsp+0F8h+var_90], rbx
0x14001811f  mov     [rsp+0F8h+var_98], rbx
0x140018124  mov     [rsp+0F8h+hKey], rbx
0x140018129  mov     r12d, ebx
0x14001812c  mov     r15d, ebx
0x14001812f  mov     r14d, ebx
0x140018132  mov     rcx, [rcx+10h]; this
0x140018136  call    ?TerminateAtJob@CSession@@QEAAKXZ; CSession::TerminateAtJob(void)
0x14001813b  mov     [rsp+0F8h+var_A8], eax
0x14001813f  test    eax, eax
0x140018141  jz      short loc_14001817F
0x140018143  lea     rdi, WPP_GLOBAL_Control
0x14001814a  mov     rcx, cs:WPP_GLOBAL_Control
0x140018151  cmp     rcx, rdi
0x140018154  jz      short loc_140018186
0x140018156  test    dword ptr [rcx+1Ch], 40000h
0x14001815d  jz      short loc_140018186
0x14001815f  cmp     byte ptr [rcx+19h], 2
0x140018163  jb      short loc_140018186
0x140018165  mov     edx, 39h ; '9'
0x14001816a  mov     r9d, eax
0x14001816d  lea     r8, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids
0x140018174  mov     rcx, [rcx+10h]
0x140018178  call    WPP_SF_d
0x14001817d  jmp     short loc_140018186
0x14001817f  lea     rdi, WPP_GLOBAL_Control
0x140018186  lea     rax, [rsp+0F8h+hKey]
0x14001818b  mov     [rsp+0F8h+phkResult], rax; phkResult
0x140018190  mov     r9d, 0F003Fh; samDesired
0x140018196  xor     r8d, r8d; ulOptions
0x140018199  lea     rdx, aSoftwareMicros_36; "Software\\Microsoft\\Windows NT\\Curren"...
0x1400181a0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400181a7  call    cs:__imp_RegOpenKeyExW
0x1400181ad  mov     [rsp+0F8h+var_A8], eax
0x1400181b1  test    eax, eax
0x1400181b3  jnz     loc_14001869E
0x1400181b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400181c0  cmp     rcx, rdi
0x1400181c3  jz      short loc_1400181E9
0x1400181c5  test    dword ptr [rcx+1Ch], 40000h
0x1400181cc  jz      short loc_1400181E9
0x1400181ce  cmp     byte ptr [rcx+19h], 4
0x1400181d2  jb      short loc_1400181E9
0x1400181d4  mov     edx, 3Ah ; ':'
0x1400181d9  lea     r8, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids
0x1400181e0  mov     rcx, [rcx+10h]
0x1400181e4  call    WPP_SF_
0x1400181e9  mov     [rsp+0F8h+var_78], rbx
0x1400181f1  mov     [rsp+0F8h+cbData], ebx
0x1400181f8  lea     rax, [rsp+0F8h+cbData]
0x140018200  mov     [rsp+0F8h+lpcbData], rax; lpcbData
0x140018205  mov     [rsp+0F8h+phkResult], rbx; lpData
0x14001820a  xor     r9d, r9d; lpType
0x14001820d  xor     r8d, r8d; lpReserved
0x140018210  lea     rdx, aSettingconfigu; "SettingConfiguration"
0x140018217  mov     rcx, [rsp+0F8h+hKey]; hKey
0x14001821c  call    cs:__imp_RegQueryValueExW
0x140018222  mov     [rsp+0F8h+var_A8], eax
0x140018226  mov     ecx, [rsp+0F8h+cbData]; unsigned __int64
0x14001822d  test    ecx, ecx
0x14001822f  jz      loc_140018403
0x140018235  test    eax, eax
0x140018237  jnz     loc_140018403
0x14001823d  call    ?WLAlloc@@YAPEAX_K@Z; WLAlloc(unsigned __int64)
0x140018242  mov     rbx, rax
0x140018245  mov     [rsp+0F8h+var_78], rax
0x14001824d  test    rax, rax
0x140018250  jnz     short loc_1400182A1
0x140018252  mov     [rsp+0F8h+var_A8], 0Eh
0x14001825a  mov     rcx, cs:WPP_GLOBAL_Control
0x140018261  cmp     rcx, rdi
0x140018264  jz      loc_1400183EF
0x14001826a  test    dword ptr [rcx+1Ch], 40000h
0x140018271  jz      loc_1400183EF
0x140018277  cmp     byte ptr [rcx+19h], 2
0x14001827b  jb      loc_1400183EF
0x140018281  mov     edx, 3Bh ; ';'
0x140018286  mov     r9d, 0Eh
0x14001828c  lea     r8, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids
0x140018293  mov     rcx, [rcx+10h]
0x140018297  call    WPP_SF_d
0x14001829c  jmp     loc_1400183EF
0x1400182a1  lea     rax, [rsp+0F8h+cbData]
0x1400182a9  mov     [rsp+0F8h+lpcbData], rax; lpcbData
0x1400182ae  mov     [rsp+0F8h+phkResult], rbx; lpData
0x1400182b3  xor     r9d, r9d; lpType
0x1400182b6  xor     r8d, r8d; lpReserved
0x1400182b9  lea     rdx, aSettingconfigu; "SettingConfiguration"
0x1400182c0  mov     rcx, [rsp+0F8h+hKey]; hKey
0x1400182c5  call    cs:__imp_RegQueryValueExW
0x1400182cb  mov     [rsp+0F8h+var_A8], eax
0x1400182cf  test    eax, eax
0x1400182d1  jz      short loc_140018304
0x1400182d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400182da  cmp     rcx, rdi
0x1400182dd  jz      loc_1400183EF
0x1400182e3  test    dword ptr [rcx+1Ch], 40000h
0x1400182ea  jz      loc_1400183EF
0x1400182f0  cmp     byte ptr [rcx+19h], 2
0x1400182f4  jb      loc_1400183EF
0x1400182fa  mov     edx, 3Ch ; '<'
0x1400182ff  mov     r9d, eax
0x140018302  jmp     short loc_14001828C
0x140018304  mov     r8d, 2
0x14001830a  mov     rdx, rbx
0x14001830d  lea     rcx, Data; " "
0x140018314  call    cs:__imp__o__wcsnicmp
0x14001831a  test    eax, eax
0x14001831c  jz      loc_1400183E4
0x140018322  cmp     byte ptr [rbx], 0
0x140018325  jz      loc_1400183E4
0x14001832b  mov     r14d, 1
0x140018331  mov     [rsp+0F8h+var_58], r14d
0x140018339  xor     edx, edx
0x14001833b  mov     [rsp+0F8h+var_80], rdx
0x140018340  mov     rcx, [rsi+20h]
0x140018344  mov     [rsp+0F8h+lpdwDisposition], rdx; lpdwDisposition
0x140018349  lea     rax, [rsp+0F8h+var_80]
0x14001834e  mov     [rsp+0F8h+var_C0], rax; phkResult
0x140018353  mov     [rsp+0F8h+lpSecurityAttributes], rdx; lpSecurityAttributes
0x140018358  mov     dword ptr [rsp+0F8h+lpcbData], 0F003Fh; samDesired
0x140018360  mov     dword ptr [rsp+0F8h+phkResult], r14d; dwOptions
0x140018365  xor     r9d, r9d; lpClass
0x140018368  xor     r8d, r8d; Reserved
0x14001836b  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Windows NT\\Curren"...
0x140018372  mov     rcx, [rcx+0E8h]; hKey
0x140018379  call    cs:__imp_RegCreateKeyExW
0x14001837f  mov     [rsp+0F8h+var_A8], eax
0x140018383  test    eax, eax
0x140018385  jnz     short loc_1400183D2
0x140018387  lea     r8, aSettingconfigu; "SettingConfiguration"
0x14001838e  mov     rdx, [rsp+0F8h+hKey]; HKEY
0x140018393  mov     rcx, [rsp+0F8h+var_80]; hKey
0x140018398  call    ?WlAccessibilitypCopyConfiguration@@YAKPEAUHKEY__@@0PEBG@Z; WlAccessibilitypCopyConfiguration(HKEY__ *,HKEY__ *,ushort const *)
0x14001839d  mov     [rsp+0F8h+var_A8], eax
0x1400183a1  test    eax, eax
0x1400183a3  jnz     short loc_1400183D2
0x1400183a5  mov     dword ptr [rsp+0F8h+lpcbData], 4; cbData
0x1400183ad  lea     rax, Data; " "
0x1400183b4  mov     [rsp+0F8h+phkResult], rax; lpData
0x1400183b9  mov     r9d, r14d; dwType
0x1400183bc  xor     r8d, r8d; Reserved
0x1400183bf  lea     rdx, aSettingconfigu; "SettingConfiguration"
0x1400183c6  mov     rcx, [rsp+0F8h+hKey]; hKey
0x1400183cb  call    cs:__imp_RegSetValueExW
0x1400183d1  nop
0x1400183d2  mov     rcx, [rsp+0F8h+var_80]; hKey
0x1400183d7  test    rcx, rcx
0x1400183da  jz      short loc_1400183EF
0x1400183dc  call    cs:__imp_RegCloseKey
0x1400183e2  jmp     short loc_1400183EF
0x1400183e4  xor     r14d, r14d
0x1400183e7  mov     [rsp+0F8h+var_58], r14d
0x1400183ef  test    rbx, rbx
0x1400183f2  jz      short loc_140018401
0x1400183f4  lea     rcx, [rsp+0F8h+var_78]
0x1400183fc  call    UHHeapFree
0x140018401  xor     ebx, ebx
0x140018403  mov     [rsp+0F8h+var_70], rbx
0x14001840b  mov     [rsp+0F8h+arg_18], ebx
0x140018412  lea     rax, [rsp+0F8h+arg_18]
0x14001841a  mov     [rsp+0F8h+lpcbData], rax; lpcbData
0x14001841f  mov     [rsp+0F8h+phkResult], rbx; lpData
0x140018424  xor     r9d, r9d; lpType
0x140018427  xor     r8d, r8d; lpReserved
0x14001842a  lea     rdx, ValueName; "Configuration"
0x140018431  mov     rcx, [rsp+0F8h+hKey]; hKey
0x140018436  call    cs:__imp_RegQueryValueExW
0x14001843c  mov     [rsp+0F8h+var_A8], eax
0x140018440  mov     ecx, [rsp+0F8h+arg_18]; unsigned __int64
0x140018447  test    ecx, ecx
0x140018449  jz      loc_14001869E
0x14001844f  test    eax, eax
0x140018451  jnz     loc_14001869E
0x140018457  call    ?WLAlloc@@YAPEAX_K@Z; WLAlloc(unsigned __int64)
0x14001845c  mov     rbx, rax
0x14001845f  mov     [rsp+0F8h+var_70], rax
0x140018467  test    rax, rax
0x14001846a  jnz     short loc_1400184BB
0x14001846c  mov     [rsp+0F8h+var_A8], 0Eh
0x140018474  mov     rcx, cs:WPP_GLOBAL_Control
0x14001847b  cmp     rcx, rdi
0x14001847e  jz      loc_14001854B
0x140018484  test    dword ptr [rcx+1Ch], 40000h
0x14001848b  jz      loc_14001854B
0x140018491  cmp     byte ptr [rcx+19h], 2
0x140018495  jb      loc_14001854B
0x14001849b  mov     edx, 3Dh ; '='
0x1400184a0  mov     r9d, 0Eh
0x1400184a6  lea     r8, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids
0x1400184ad  mov     rcx, [rcx+10h]
0x1400184b1  call    WPP_SF_d
0x1400184b6  jmp     loc_140018544
0x1400184bb  lea     rax, [rsp+0F8h+arg_18]
0x1400184c3  mov     [rsp+0F8h+lpcbData], rax; lpcbData
0x1400184c8  mov     [rsp+0F8h+phkResult], rbx; lpData
0x1400184cd  xor     r9d, r9d; lpType
0x1400184d0  xor     r8d, r8d; lpReserved
0x1400184d3  lea     rdx, ValueName; "Configuration"
0x1400184da  mov     rcx, [rsp+0F8h+hKey]; hKey
0x1400184df  call    cs:__imp_RegQueryValueExW
0x1400184e5  mov     [rsp+0F8h+var_A8], eax
0x1400184e9  test    eax, eax
0x1400184eb  jz      short loc_140018512
0x1400184ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400184f4  cmp     rcx, rdi
0x1400184f7  jz      short loc_14001854B
0x1400184f9  test    dword ptr [rcx+1Ch], 40000h
0x140018500  jz      short loc_14001854B
0x140018502  cmp     byte ptr [rcx+19h], 2
0x140018506  jb      short loc_14001854B
0x140018508  mov     edx, 3Eh ; '>'
0x14001850d  mov     r9d, eax
0x140018510  jmp     short loc_1400184A6
0x140018512  mov     r8d, 2
0x140018518  mov     rdx, rbx
0x14001851b  lea     rcx, Data; " "
0x140018522  call    cs:__imp__o__wcsnicmp
0x140018528  test    eax, eax
0x14001852a  jz      short loc_140018539
0x14001852c  cmp     byte ptr [rbx], 0
0x14001852f  jz      short loc_140018539
0x140018531  mov     r15d, 1
0x140018537  jmp     short loc_14001853C
0x140018539  xor     r15d, r15d
0x14001853c  mov     [rsp+0F8h+var_54], r15d
0x140018544  mov     rcx, cs:WPP_GLOBAL_Control
0x14001854b  test    rbx, rbx
0x14001854e  jz      short loc_140018564
0x140018550  lea     rcx, [rsp+0F8h+var_70]
0x140018558  call    UHHeapFree
0x14001855d  mov     rcx, cs:WPP_GLOBAL_Control
0x140018564  xor     ebx, ebx
0x140018566  test    r15d, r15d
0x140018569  jz      short loc_140018574
0x14001856b  test    r14d, r14d
0x14001856e  jnz     loc_1400189CF
0x140018574  mov     rcx, [rsi+20h]
0x140018578  lea     rax, [rsp+0F8h+var_90]
0x14001857d  mov     [rsp+0F8h+phkResult], rax; phkResult
0x140018582  mov     r9d, 1; samDesired
0x140018588  xor     r8d, r8d; ulOptions
0x14001858b  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Windows NT\\Curren"...
0x140018592  mov     rcx, [rcx+0E8h]; hKey
0x140018599  call    cs:__imp_RegOpenKeyExW
0x14001859f  mov     [rsp+0F8h+var_A8], eax
0x1400185a3  test    eax, eax
0x1400185a5  jnz     loc_140018749
0x1400185ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400185b2  cmp     rcx, rdi
0x1400185b5  jz      short loc_1400185DB
0x1400185b7  test    dword ptr [rcx+1Ch], 40000h
0x1400185be  jz      short loc_1400185DB
0x1400185c0  cmp     byte ptr [rcx+19h], 4
0x1400185c4  jb      short loc_1400185DB
0x1400185c6  mov     edx, 3Fh ; '?'
0x1400185cb  lea     r8, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids
0x1400185d2  mov     rcx, [rcx+10h]
0x1400185d6  call    WPP_SF_
0x1400185db  mov     [rsp+0F8h+var_68], rbx
0x1400185e3  mov     [rsp+0F8h+var_88], ebx
0x1400185e7  lea     rax, [rsp+0F8h+var_88]
0x1400185ec  mov     [rsp+0F8h+lpcbData], rax; lpcbData
0x1400185f1  mov     [rsp+0F8h+phkResult], rbx; lpData
0x1400185f6  xor     r9d, r9d; lpType
0x1400185f9  xor     r8d, r8d; lpReserved
0x1400185fc  lea     rdx, ValueName; "Configuration"
0x140018603  mov     rcx, [rsp+0F8h+var_90]; hKey
0x140018608  call    cs:__imp_RegQueryValueExW
0x14001860e  mov     [rsp+0F8h+var_A8], eax
0x140018612  mov     ecx, [rsp+0F8h+var_88]
0x140018616  test    ecx, ecx
0x140018618  jz      loc_140018749
0x14001861e  test    eax, eax
0x140018620  jnz     loc_140018749
0x140018626  mov     ebx, ecx
0x140018628  call    cs:__imp_GetProcessHeap
0x14001862e  mov     rcx, rax; hHeap
0x140018631  mov     r8d, ebx; dwBytes
0x140018634  mov     edx, 8; dwFlags
0x140018639  call    cs:__imp_HeapAlloc
0x14001863f  mov     rbx, rax
0x140018642  mov     [rsp+0F8h+var_68], rax
0x14001864a  test    rax, rax
0x14001864d  jnz     short loc_1400186AA
0x14001864f  mov     [rsp+0F8h+var_A8], 0Eh
0x140018657  mov     rcx, cs:WPP_GLOBAL_Control
0x14001865e  cmp     rcx, rdi
  ... truncated ...
```
