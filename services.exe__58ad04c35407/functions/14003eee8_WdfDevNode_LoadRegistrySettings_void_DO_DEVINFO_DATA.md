# WdfDevNode::LoadRegistrySettings(void *,_DO_DEVINFO_DATA *)

- ea: `0x14003eee8`
- end: `0x14003f9a1`
- name: `?LoadRegistrySettings@WdfDevNode@@AEAAHPEAXPEAU_DO_DEVINFO_DATA@@@Z`
- size: `2745`
- prototype: `__int64 __fastcall(WdfDevNode *__hidden this, void *, struct _DO_DEVINFO_DATA *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14002ba14`

## callees

- `0x140003e54`
- `0x140004c58`
- `0x1400188fc`
- `0x14001f99c`
- `0x140027998`
- `0x14002cca8`
- `0x140032014`
- `0x140035ec4`
- `0x14003eee8`
- `0x140051360`
- `0x140064a90`
- `0x14008e028`
- `0x140091f24`
- `0x140092060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003ef81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003ef81`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003f236`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003f2ae`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003f2ef`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003f94a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003f236`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003f2ae`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003f2ef`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003f94a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003efd1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003f0d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003f132`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003efd1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003f0d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003f132`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003f13f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003f629`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003f637`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003f646`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003f13f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003f629`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003f637`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003f646`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x14003ef4d`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x14003ef4d`

## string_xrefs

- `0x14003f0c9`: `CompanionConfigurations`
- `0x14003f10c`: `CompanionConfigurations`
- `0x14003f18b`: `CompanionConfigurations`
- `0x14003f1b9`: `CompanionServiceList`
- `0x14003f1fe`: `CompanionServiceList`

## pseudocode

```c
__int64 __fastcall WdfDevNode::LoadRegistrySettings(WdfDevNode *this, void *a2, struct _DO_DEVINFO_DATA *a3)
{
  unsigned int v4; // ebx
  HKEY v5; // rax
  HKEY v6; // r15
  DWORD LastError; // eax
  LSTATUS v8; // eax
  PRPC_ASYNC_STATE v9; // rcx
  int v10; // edx
  const WCHAR *v11; // r9
  HKEY v12; // rcx
  unsigned int v13; // eax
  unsigned __int16 *v14; // rax
  PRPC_ASYNC_STATE v15; // rcx
  __int64 v16; // rdx
  const WCHAR *v17; // r9
  LSTATUS v18; // r12d
  unsigned __int16 *v19; // rax
  _DWORD *v20; // r13
  _WORD *v21; // rax
  int v22; // edx
  __int64 v23; // rcx
  PRPC_ASYNC_STATE v24; // rcx
  __int64 v25; // rdx
  unsigned __int128 v26; // rax
  void *v27; // rax
  unsigned int v28; // edx
  _WORD *v29; // r13
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 DebugModeSettingsForBinary; // rax
  char v34; // r8
  char v35; // dl
  __int64 v36; // rax
  __int64 v37; // r9
  _QWORD *v38; // r8
  _WORD *v39; // rdx
  unsigned __int16 *v40; // r10
  unsigned int v41; // edx
  __int64 v42; // r13
  unsigned __int16 *v43; // rax
  __int64 v44; // r11
  int v45; // r8d
  int v46; // r10d
  __int64 v47; // rdx
  int v49; // edx
  __int64 v50; // r9
  WdfDriverManager *v51; // rax
  const wchar_t *v52; // r13
  PRPC_ASYNC_STATE v53; // rcx
  __int64 v54; // rdx
  const wchar_t *v55; // r9
  int v56; // eax
  DWORD cbData; // [rsp+34h] [rbp-3Ch] BYREF
  DWORD Type; // [rsp+38h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int16 *v60; // [rsp+48h] [rbp-28h]
  BYTE Data[8]; // [rsp+50h] [rbp-20h] BYREF
  HKEY v62; // [rsp+58h] [rbp-18h] BYREF
  _WORD *v63; // [rsp+60h] [rbp-10h] BYREF
  HKEY phkResult; // [rsp+C8h] [rbp+58h] BYREF

  Type = 0;
  cbData = 0;
  *(_DWORD *)Data = 0;
  v4 = 0;
  v62 = 0;
  hKey = 0;
  v5 = (HKEY)DevObjOpenDevRegKey(a2, a3, 1);
  v6 = v5;
  if ( v5 != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
  {
    if ( !v5 )
      goto LABEL_114;
    v8 = RegOpenKeyExW(v5, L"WUDF", 0, 0x20019u, &hKey);
    if ( v8 )
    {
      hKey = 0;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) != 0
          && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
        {
          v10 = 74;
          v11 = L"WUDF";
LABEL_14:
          WPP_SF_Sd(
            v9->u.APC.hThread,
            v10,
            (unsigned int)&WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids,
            (_DWORD)v11,
            v8);
          goto LABEL_15;
        }
        v4 = 0;
      }
LABEL_117:
      RegCloseKey(v6);
      goto LABEL_118;
    }
    v12 = hKey;
    v13 = *((_DWORD *)this + 75) - 1;
    *((_QWORD *)this + 14) = 0;
    if ( v13 <= 2 )
    {
      phkResult = 0;
      v8 = RegOpenKeyExW(v12, L"CompanionConfigurations", 0, 0x20019u, &phkResult);
      if ( v8 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control )
          goto LABEL_114;
        if ( (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) != 0
          && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
        {
          v10 = 76;
          v11 = L"CompanionConfigurations";
          goto LABEL_14;
        }
        goto LABEL_15;
      }
      v18 = RegOpenKeyExW(phkResult, *((LPCWSTR *)this + 38), 0, 0x20019u, &v62);
      RegCloseKey(phkResult);
      if ( v18 )
      {
        v62 = 0;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control )
          goto LABEL_114;
        if ( (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) != 0
          && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
        {
          WPP_SF_SSD(
            WPP_GLOBAL_Control->u.APC.hThread,
            77,
            (unsigned int)&WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids,
            (unsigned int)L"CompanionConfigurations",
            *((_QWORD *)this + 38),
            v18);
        }
        goto LABEL_15;
      }
      v19 = WdfRegQueryString(v62, L"CompanionServiceList", &Type, &cbData);
      *((_QWORD *)this + 14) = v19;
      if ( !v19 )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control )
          goto LABEL_114;
        if ( (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) != 0
          && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
        {
          v16 = 78;
          v17 = L"CompanionServiceList";
          goto LABEL_23;
        }
LABEL_15:
        v4 = 0;
        goto LABEL_114;
      }
    }
    else
    {
      v14 = WdfRegQueryString(v12, L"DriverList", &Type, &cbData);
      *((_QWORD *)this + 14) = v14;
      if ( !v14 )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control )
          goto LABEL_114;
        if ( (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) != 0
          && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
        {
          v16 = 75;
          v17 = L"DriverList";
LABEL_23:
          WPP_SF_S(v15->u.APC.hThread, v16, &WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids, v17);
          goto LABEL_15;
        }
        goto LABEL_15;
      }
    }
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"HostTimeoutSeconds", 0, &Type, Data, &cbData) || Type != 4 )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) != 0
        && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->u.APC.hThread, 79, &WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids);
      }
    }
    else
    {
      *((_DWORD *)this + 31) = *(_DWORD *)Data;
    }
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"HostProcessSharingEnabled", 0, &Type, (LPBYTE)this + 128, &cbData) || Type != 4 )
      *((_DWORD *)this + 32) = 1;
    v20 = (_DWORD *)((char *)this + 132);
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"HostPriority", 0, &Type, (LPBYTE)this + 132, &cbData)
      || Type != 4
      || *v20 != 2 && *v20 )
    {
      if ( (unsigned int)(*((_DWORD *)this + 75) - 1) > 2 )
        *v20 = 0;
      else
        *v20 = 2;
    }
    v21 = (_WORD *)*((_QWORD *)this + 14);
    if ( *v21 )
    {
      v22 = *((_DWORD *)this + 34);
      do
      {
        ++v22;
        v23 = -1;
        *((_DWORD *)this + 34) = v22;
        do
          ++v23;
        while ( v21[v23] );
        v21 += v23 + 1;
      }
      while ( *v21 );
    }
    if ( !*((_DWORD *)this + 34) )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) != 0
        && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
      {
        v25 = 80;
LABEL_66:
        WPP_SF_(v24->u.APC.hThread, v25, &WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids);
        goto LABEL_15;
      }
      goto LABEL_113;
    }
    v26 = *((unsigned int *)this + 34) * (unsigned __int128)8uLL;
    if ( !is_mul_ok(*((unsigned int *)this + 34), 8u) )
      *(_QWORD *)&v26 = -1;
    v27 = operator new(v26, *((const struct std::nothrow_t **)&v26 + 1));
    *((_QWORD *)this + 23) = v27;
    if ( !v27 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) != 0
        && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 3u )
      {
        v25 = 81;
        goto LABEL_66;
      }
      goto LABEL_113;
    }
    memset(v27, 0, 8LL * *((unsigned int *)this + 34));
    v28 = 0;
    v29 = (_WORD *)*((_QWORD *)this + 14);
    LODWORD(v60) = 0;
    if ( *((_DWORD *)this + 34) )
    {
      while ( 1 )
      {
        if ( !*v29 )
        {
          v24 = WPP_GLOBAL_Control;
          goto LABEL_87;
        }
        v63 = v29;
        v30 = WdfObjectList<WdfServiceKey,WdfServiceKeyParameters>::Find(*((_QWORD *)DrvMgrExt + 13), &v63, 1);
        v31 = (unsigned int)v60;
        *(_QWORD *)(*((_QWORD *)this + 23) + 8LL * (unsigned int)v60) = v30;
        v32 = *(_QWORD *)(*((_QWORD *)this + 23) + 8 * v31);
        if ( !v32 )
          break;
        DebugModeSettingsForBinary = WdfDriverManager::GetDebugModeSettingsForBinary(
                                       v30,
                                       &phkResult,
                                       *(_QWORD *)(v32 + 96));
        v34 = *(_BYTE *)DebugModeSettingsForBinary;
        v35 = *((_BYTE *)this + 296) & 0xFE ^ (*(_BYTE *)DebugModeSettingsForBinary | *((_BYTE *)this + 296)) & 1;
        LOBYTE(DebugModeSettingsForBinary) = v35 & 0xFD ^ (*(_BYTE *)DebugModeSettingsForBinary | v35) & 2;
        v28 = (_DWORD)v60 + 1;
        *((_BYTE *)this + 296) = DebugModeSettingsForBinary & 0xFB ^ (v34 | DebugModeSettingsForBinary) & 4;
        v36 = -1;
        LODWORD(v60) = v28;
        do
          ++v36;
        while ( v29[v36] );
        v29 += v36 + 1;
        if ( v28 >= *((_DWORD *)this + 34) )
          goto LABEL_80;
      }
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) != 0
        && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
      {
        WPP_SF_S(WPP_GLOBAL_Control->u.APC.hThread, 82, &WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids, v29);
        v24 = WPP_GLOBAL_Control;
      }
      v28 = (unsigned int)v60;
    }
    else
    {
LABEL_80:
      v24 = WPP_GLOBAL_Control;
    }
    if ( *v29 )
      goto LABEL_113;
LABEL_87:
    v37 = *((unsigned int *)this + 34);
    if ( v28 < (unsigned int)v37 )
    {
LABEL_113:
      v4 = 0;
      goto LABEL_114;
    }
    if ( !(_DWORD)v37 )
    {
      if ( v24 != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (*((_BYTE *)&v24->u.NotificationRoutine + 20) & 4) != 0
        && *((_BYTE *)&v24->u.NotificationRoutine + 17) >= 2u )
      {
        v25 = 83;
        goto LABEL_66;
      }
      goto LABEL_113;
    }
    v38 = (_QWORD *)*((_QWORD *)this + 23);
    v39 = (_WORD *)*v38;
    v63 = v39;
    v40 = (unsigned __int16 *)*((_QWORD *)v39 + 13);
    v60 = v40;
    if ( (unsigned int)v37 > 1 )
    {
      v41 = 1;
      while ( 1 )
      {
        v42 = v38[v41];
        v43 = v40;
        v44 = *(_QWORD *)(v42 + 104) - (_QWORD)v40;
        do
        {
          v45 = *(unsigned __int16 *)((char *)v43 + v44);
          v46 = *v43 - v45;
          if ( v46 )
            break;
          ++v43;
        }
        while ( v45 );
        if ( v46 )
          break;
        if ( (unsigned int)(*((_DWORD *)this + 75) - 1) > 2 && (unsigned int)(*(_DWORD *)(v42 + 140) - 1) <= 2 )
        {
          if ( v24 != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (*((_BYTE *)&v24->u.NotificationRoutine + 20) & 4) != 0
            && *((_BYTE *)&v24->u.NotificationRoutine + 17) >= 2u )
          {
            v47 = 85;
            goto LABEL_112;
          }
          goto LABEL_113;
        }
        if ( ++v41 >= (unsigned int)v37 )
        {
          v39 = v63;
          goto LABEL_122;
        }
        v38 = (_QWORD *)*((_QWORD *)this + 23);
        v40 = v60;
      }
      if ( v24 != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (*((_BYTE *)&v24->u.NotificationRoutine + 20) & 4) != 0
        && *((_BYTE *)&v24->u.NotificationRoutine + 17) >= 2u )
      {
        v47 = 84;
        goto LABEL_112;
      }
      goto LABEL_113;
    }
LABEL_122:
    if ( (unsigned int)(*((_DWORD *)this + 75) - 1) <= 2 )
    {
      if ( (_DWORD)v37 != 1 )
      {
        if ( v24 == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (*((_BYTE *)&v24->u.NotificationRoutine + 20) & 4) == 0
          || *((_BYTE *)&v24->u.NotificationRoutine + 17) < 2u )
        {
          goto LABEL_113;
        }
        v47 = 86;
        goto LABEL_112;
      }
      v49 = *((_DWORD *)v39 + 35);
      if ( (unsigned int)(v49 - 1) > 2 )
      {
        if ( v24 == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (*((_BYTE *)&v24->u.NotificationRoutine + 20) & 4) == 0
          || *((_BYTE *)&v24->u.NotificationRoutine + 17) < 2u )
        {
          goto LABEL_113;
        }
        v47 = 87;
        goto LABEL_112;
      }
      *((_DWORD *)this + 75) = v49;
      v24 = WPP_GLOBAL_Control;
    }
    if ( v24 != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      && (*((_BYTE *)&v24->u.NotificationRoutine + 20) & 4) != 0
      && *((_BYTE *)&v24->u.NotificationRoutine + 17) >= 5u )
    {
      WPP_SF_d(v24->u.APC.hThread, 88, &WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids, v37);
    }
    v50 = *((unsigned int *)this + 34);
    *((_QWORD *)this + 18) = v60;
    *((_QWORD *)this + 22) = *((_QWORD *)this + 23);
    v51 = DrvMgrExt;
    *((_DWORD *)this + 38) = v50;
    if ( (unsigned int)v50 > *((_DWORD *)v51 + 36) )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) != 0
        && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->u.APC.hThread, 89, &WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids, v50);
      }
      goto LABEL_113;
    }
    v52 = WdfRegQueryString(hKey, L"DeviceGroupId", &Type, &cbData);
    *((_QWORD *)this + 31) = v52;
    if ( v52 )
    {
      if ( Type != 1 )
      {
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) != 0
          && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->u.APC.hThread, 90, &WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids, Type);
        }
        goto LABEL_113;
      }
      if ( !cbData )
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) == 0
          || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
        {
          goto LABEL_113;
        }
        v47 = 91;
LABEL_112:
        WPP_SF_(v24->u.APC.hThread, v47, &WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids);
        goto LABEL_113;
      }
      if ( !wcsncmp(v52, L"WudfDefaultDevicePool", 0x16u) )
      {
        v53 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) == 0
          || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
        {
          goto LABEL_113;
        }
        v54 = 92;
        v55 = L"WudfDefaultDevicePool";
        goto LABEL_159;
      }
      if ( !wcsncmp(v52, L"WudfDefaultDevicePoolPriorityHigh", 0x22u) )
      {
        v53 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) == 0
          || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
        {
          goto LABEL_113;
        }
        v54 = 93;
        v55 = L"WudfDefaultDevicePoolPriorityHigh";
LABEL_159:
        WPP_SF_S(v53->u.APC.hThread, v54, &WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids, v55);
        goto LABEL_113;
      }
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) != 0
        && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 5u )
      {
        WPP_SF_S(WPP_GLOBAL_Control->u.APC.hThread, 94, &WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids, v52);
      }
    }
    if ( *((_DWORD *)this + 32) && !*((_QWORD *)this + 31)
      || WdfDevNode::RetrieveCustomPoolOptionsFromRegistry(this, hKey) )
    {
      cbData = 4;
      if ( RegQueryValueExW(hKey, L"AutoRestartDeviceInOwnProcess", 0, &Type, Data, &cbData) || Type != 4 )
      {
        if ( *((_QWORD *)this + 31) )
          v56 = 0;
        else
          v56 = *((_DWORD *)DrvMgrExt + 50);
      }
      else
      {
        v56 = *(_DWORD *)Data != 0;
      }
      *((_DWORD *)this + 51) = v56;
      WdfDevNode::InitErrorTag(this, a2, a3);
      v4 = 1;
      goto LABEL_114;
    }
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) != 0
      && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
    {
      v25 = 95;
      goto LABEL_66;
    }
    goto LABEL_113;
  }
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) != 0
      && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(WPP_GLOBAL_Control->u.APC.hThread, 106, &WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids, LastError);
    }
    v4 = 0;
  }
  v6 = 0;
LABEL_114:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v6 )
    goto LABEL_117;
LABEL_118:
  if ( v62 )
    RegCloseKey(v62);
  return v4;
}

```

## disassembly

```asm
0x14003eee8  mov     r11, rsp
0x14003eeeb  mov     [r11+8], rbx
0x14003eeef  mov     [r11+18h], r8
0x14003eef3  mov     [r11+10h], rdx
0x14003eef7  push    rbp
0x14003eef8  push    rsi
0x14003eef9  push    rdi
0x14003eefa  push    r12
0x14003eefc  push    r13
0x14003eefe  push    r14
0x14003ef00  push    r15
0x14003ef02  mov     rbp, rsp
0x14003ef05  sub     rsp, 70h
0x14003ef09  xor     r13d, r13d
0x14003ef0c  mov     rax, r8
0x14003ef0f  mov     r10, rdx
0x14003ef12  mov     [rbp+Type], r13d
0x14003ef16  mov     r14, rcx
0x14003ef19  mov     [rbp+cbData], r13d
0x14003ef1d  mov     r12d, 20019h
0x14003ef23  mov     dword ptr [rbp+Data], r13d
0x14003ef27  lea     edi, [r13+1]
0x14003ef2b  mov     [r11-80h], r12d
0x14003ef2f  mov     ebx, r13d
0x14003ef32  mov     [rbp+var_18], r13
0x14003ef36  mov     r8d, edi
0x14003ef39  mov     [rbp+var_40], ebx
0x14003ef3c  xor     r9d, r9d
0x14003ef3f  mov     [rbp+hKey], r13
0x14003ef43  mov     rdx, rax
0x14003ef46  mov     dword ptr [rsp+70h+phkResult], edi
0x14003ef4a  mov     rcx, r10
0x14003ef4d  call    cs:__imp_DevObjOpenDevRegKey
0x14003ef53  mov     r15, rax
0x14003ef56  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14003ef5a  jnz     short loc_14003EFAF
0x14003ef5c  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003ef63  lea     rdi, WPP_GLOBAL_Control
0x14003ef6a  cmp     rax, rdi
0x14003ef6d  jz      short loc_14003EFA7
0x14003ef6f  lea     ebx, [r13+4]
0x14003ef73  test    [rax+44h], bl
0x14003ef76  jz      short loc_14003EFA4
0x14003ef78  lea     esi, [rbx-2]
0x14003ef7b  cmp     [rax+41h], sil
0x14003ef7f  jb      short loc_14003EFA4
0x14003ef81  call    cs:__imp_GetLastError
0x14003ef87  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ef8e  lea     edx, [rbx+66h]
0x14003ef91  mov     r9d, eax
0x14003ef94  lea     r8, WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids
0x14003ef9b  mov     rcx, [rcx+38h]
0x14003ef9f  call    WPP_SF_d
0x14003efa4  mov     ebx, r13d
0x14003efa7  mov     r15, r13
0x14003efaa  jmp     loc_14003F620
0x14003efaf  test    r15, r15
0x14003efb2  jz      loc_14003F620
0x14003efb8  lea     rax, [rbp+hKey]
0x14003efbc  mov     r9d, r12d; samDesired
0x14003efbf  xor     r8d, r8d; ulOptions
0x14003efc2  mov     [rsp+70h+phkResult], rax; phkResult
0x14003efc7  lea     rdx, aWudf; "WUDF"
0x14003efce  mov     rcx, r15; hKey
0x14003efd1  call    cs:__imp_RegOpenKeyExW
0x14003efd7  test    eax, eax
0x14003efd9  jz      short loc_14003F037
0x14003efdb  mov     [rbp+hKey], r13
0x14003efdf  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003efe6  lea     rdi, WPP_GLOBAL_Control
0x14003efed  cmp     rcx, rdi
0x14003eff0  jz      loc_14003F634
0x14003eff6  mov     ebx, 4
0x14003effb  test    [rcx+44h], bl
0x14003effe  jz      short loc_14003F02F
0x14003f000  lea     esi, [rbx-2]
0x14003f003  cmp     [rcx+41h], sil
0x14003f007  jb      short loc_14003F02F
0x14003f009  lea     edx, [rbx+46h]
0x14003f00c  lea     r9, aWudf; "WUDF"
0x14003f013  mov     rcx, [rcx+38h]
0x14003f017  lea     r8, WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids
0x14003f01e  mov     dword ptr [rsp+70h+phkResult], eax
0x14003f022  call    WPP_SF_Sd
0x14003f027  mov     ebx, r13d
0x14003f02a  jmp     loc_14003F620
0x14003f02f  mov     ebx, r13d
0x14003f032  jmp     loc_14003F634
0x14003f037  mov     eax, [r14+12Ch]
0x14003f03e  mov     esi, 2
0x14003f043  mov     rcx, [rbp+hKey]; hKey
0x14003f047  sub     eax, edi
0x14003f049  mov     [r14+70h], r13
0x14003f04d  cmp     eax, esi
0x14003f04f  jbe     short loc_14003F0B6
0x14003f051  lea     r9, [rbp+cbData]; unsigned int *
0x14003f055  lea     r8, [rbp+Type]; unsigned int *
0x14003f059  lea     rdx, aDriverlist; "DriverList"
0x14003f060  call    ?WdfRegQueryString@@YAPEAGPEAUHKEY__@@PEBGPEAK2@Z; WdfRegQueryString(HKEY__ *,ushort const *,ulong *,ulong *)
0x14003f065  mov     [r14+70h], rax
0x14003f069  test    rax, rax
0x14003f06c  jnz     loc_14003F20A
0x14003f072  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003f079  lea     rdi, WPP_GLOBAL_Control
0x14003f080  cmp     rcx, rdi
0x14003f083  jz      loc_14003F620
0x14003f089  lea     ebx, [rsi+2]
0x14003f08c  test    [rcx+44h], bl
0x14003f08f  jz      short loc_14003F027
0x14003f091  cmp     [rcx+41h], sil
0x14003f095  jb      short loc_14003F027
0x14003f097  lea     edx, [rsi+49h]
0x14003f09a  lea     r9, aDriverlist; "DriverList"
0x14003f0a1  mov     rcx, [rcx+38h]
0x14003f0a5  lea     r8, WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids
0x14003f0ac  call    WPP_SF_S
0x14003f0b1  jmp     loc_14003F027
0x14003f0b6  lea     rax, [rbp+arg_18]
0x14003f0ba  mov     [rbp+arg_18], r13
0x14003f0be  mov     r9d, r12d; samDesired
0x14003f0c1  mov     [rsp+70h+phkResult], rax; phkResult
0x14003f0c6  xor     r8d, r8d; ulOptions
0x14003f0c9  lea     rdx, aCompanionconfi; "CompanionConfigurations"
0x14003f0d0  call    cs:__imp_RegOpenKeyExW
0x14003f0d6  test    eax, eax
0x14003f0d8  jz      short loc_14003F118
0x14003f0da  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003f0e1  lea     rdi, WPP_GLOBAL_Control
0x14003f0e8  cmp     rcx, rdi
0x14003f0eb  jz      loc_14003F620
0x14003f0f1  mov     ebx, 4
0x14003f0f6  test    [rcx+44h], bl
0x14003f0f9  jz      loc_14003F027
0x14003f0ff  cmp     [rcx+41h], sil
0x14003f103  jb      loc_14003F027
0x14003f109  lea     edx, [rbx+48h]
0x14003f10c  lea     r9, aCompanionconfi; "CompanionConfigurations"
0x14003f113  jmp     loc_14003F013
0x14003f118  mov     rdx, [r14+130h]; lpSubKey
0x14003f11f  lea     rax, [rbp+var_18]
0x14003f123  mov     rcx, [rbp+arg_18]; hKey
0x14003f127  mov     r9d, r12d; samDesired
0x14003f12a  xor     r8d, r8d; ulOptions
0x14003f12d  mov     [rsp+70h+phkResult], rax; phkResult
0x14003f132  call    cs:__imp_RegOpenKeyExW
0x14003f138  mov     rcx, [rbp+arg_18]; hKey
0x14003f13c  mov     r12d, eax
0x14003f13f  call    cs:__imp_RegCloseKey
0x14003f145  test    r12d, r12d
0x14003f148  jz      short loc_14003F1AD
0x14003f14a  mov     [rbp+var_18], r13
0x14003f14e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003f155  lea     rdi, WPP_GLOBAL_Control
0x14003f15c  cmp     rcx, rdi
0x14003f15f  jz      loc_14003F620
0x14003f165  mov     ebx, 4
0x14003f16a  test    [rcx+44h], bl
0x14003f16d  jz      loc_14003F027
0x14003f173  cmp     [rcx+41h], sil
0x14003f177  jb      loc_14003F027
0x14003f17d  mov     rax, [r14+130h]
0x14003f184  lea     edx, [rbx+49h]
0x14003f187  mov     rcx, [rcx+38h]
0x14003f18b  lea     r9, aCompanionconfi; "CompanionConfigurations"
0x14003f192  mov     dword ptr [rsp+70h+lpcbData], r12d
0x14003f197  lea     r8, WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids
0x14003f19e  mov     [rsp+70h+phkResult], rax
0x14003f1a3  call    WPP_SF_SSD
0x14003f1a8  jmp     loc_14003F027
0x14003f1ad  mov     rcx, [rbp+var_18]; hKey
0x14003f1b1  lea     r9, [rbp+cbData]; unsigned int *
0x14003f1b5  lea     r8, [rbp+Type]; unsigned int *
0x14003f1b9  lea     rdx, aCompanionservi; "CompanionServiceList"
0x14003f1c0  call    ?WdfRegQueryString@@YAPEAGPEAUHKEY__@@PEBGPEAK2@Z; WdfRegQueryString(HKEY__ *,ushort const *,ulong *,ulong *)
0x14003f1c5  mov     [r14+70h], rax
0x14003f1c9  test    rax, rax
0x14003f1cc  jnz     short loc_14003F20A
0x14003f1ce  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003f1d5  lea     rdi, WPP_GLOBAL_Control
0x14003f1dc  cmp     rcx, rdi
0x14003f1df  jz      loc_14003F620
0x14003f1e5  lea     ebx, [rax+4]
0x14003f1e8  test    [rcx+44h], bl
0x14003f1eb  jz      loc_14003F027
0x14003f1f1  cmp     [rcx+41h], sil
0x14003f1f5  jb      loc_14003F027
0x14003f1fb  lea     edx, [rax+4Eh]
0x14003f1fe  lea     r9, aCompanionservi; "CompanionServiceList"
0x14003f205  jmp     loc_14003F0A1
0x14003f20a  mov     rcx, [rbp+hKey]; hKey
0x14003f20e  lea     rax, [rbp+cbData]
0x14003f212  mov     [rsp+70h+lpcbData], rax; lpcbData
0x14003f217  lea     r9, [rbp+Type]; lpType
0x14003f21b  lea     rax, [rbp+Data]
0x14003f21f  mov     ebx, 4
0x14003f224  xor     r8d, r8d; lpReserved
0x14003f227  mov     [rsp+70h+phkResult], rax; lpData
0x14003f22c  lea     rdx, aHosttimeoutsec; "HostTimeoutSeconds"
0x14003f233  mov     [rbp+cbData], ebx
0x14003f236  call    cs:__imp_RegQueryValueExW
0x14003f23c  lea     r12, WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids
0x14003f243  lea     rdi, WPP_GLOBAL_Control
0x14003f24a  test    eax, eax
0x14003f24c  jnz     short loc_14003F25C
0x14003f24e  cmp     [rbp+Type], ebx
0x14003f251  jnz     short loc_14003F25C
0x14003f253  mov     eax, dword ptr [rbp+Data]
0x14003f256  mov     [r14+7Ch], eax
0x14003f25a  jmp     short loc_14003F284
0x14003f25c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003f263  cmp     rcx, rdi
0x14003f266  jz      short loc_14003F284
0x14003f268  test    byte ptr [rcx+44h], 8
0x14003f26c  jz      short loc_14003F284
0x14003f26e  cmp     [rcx+41h], bl
0x14003f271  jb      short loc_14003F284
0x14003f273  mov     rcx, [rcx+38h]
0x14003f277  mov     edx, 4Fh ; 'O'
0x14003f27c  mov     r8, r12
0x14003f27f  call    WPP_SF_
0x14003f284  mov     rcx, [rbp+hKey]; hKey
0x14003f288  lea     rax, [rbp+cbData]
0x14003f28c  mov     [rsp+70h+lpcbData], rax; lpcbData
0x14003f291  lea     r13, [r14+80h]
0x14003f298  lea     r9, [rbp+Type]; lpType
0x14003f29c  mov     [rsp+70h+phkResult], r13; lpData
0x14003f2a1  xor     r8d, r8d; lpReserved
0x14003f2a4  mov     [rbp+cbData], ebx
0x14003f2a7  lea     rdx, aHostprocesssha; "HostProcessSharingEnabled"
0x14003f2ae  call    cs:__imp_RegQueryValueExW
0x14003f2b4  xor     r8d, r8d; lpReserved
0x14003f2b7  test    eax, eax
0x14003f2b9  jnz     short loc_14003F2C0
0x14003f2bb  cmp     [rbp+Type], ebx
0x14003f2be  jz      short loc_14003F2C8
0x14003f2c0  mov     dword ptr [r13+0], 1
0x14003f2c8  mov     rcx, [rbp+hKey]; hKey
0x14003f2cc  lea     rax, [rbp+cbData]
0x14003f2d0  mov     [rsp+70h+lpcbData], rax; lpcbData
0x14003f2d5  lea     r13, [r14+84h]
0x14003f2dc  lea     r9, [rbp+Type]; lpType
0x14003f2e0  mov     [rsp+70h+phkResult], r13; lpData
0x14003f2e5  lea     rdx, aHostpriority; "HostPriority"
0x14003f2ec  mov     [rbp+cbData], ebx
0x14003f2ef  call    cs:__imp_RegQueryValueExW
0x14003f2f5  xor     ecx, ecx
0x14003f2f7  test    eax, eax
0x14003f2f9  jnz     short loc_14003F30C
0x14003f2fb  cmp     [rbp+Type], ebx
0x14003f2fe  jnz     short loc_14003F30C
0x14003f300  cmp     [r13+0], esi
0x14003f304  jz      short loc_14003F323
0x14003f306  cmp     [r13+0], ecx
0x14003f30a  jz      short loc_14003F323
0x14003f30c  mov     eax, [r14+12Ch]
0x14003f313  dec     eax
0x14003f315  cmp     eax, esi
0x14003f317  ja      short loc_14003F31F
0x14003f319  mov     [r13+0], esi
0x14003f31d  jmp     short loc_14003F323
0x14003f31f  mov     [r13+0], ecx
0x14003f323  mov     rax, [r14+70h]
0x14003f327  xor     r13d, r13d
0x14003f32a  or      r8, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x14003f32e  cmp     [rax], r13w
0x14003f332  jz      short loc_14003F35E
0x14003f334  mov     edx, [r14+88h]
0x14003f33b  inc     edx; unsigned int
0x14003f33d  mov     rcx, r8
0x14003f340  mov     [r14+88h], edx
0x14003f347  inc     rcx
0x14003f34a  cmp     [rax+rcx*2], r13w
0x14003f34f  jnz     short loc_14003F347
0x14003f351  lea     rax, [rax+rcx*2]
0x14003f355  add     rax, rsi
0x14003f358  cmp     [rax], r13w
0x14003f35c  jnz     short loc_14003F33B
0x14003f35e  mov     eax, [r14+88h]
0x14003f365  test    eax, eax
0x14003f367  jnz     short loc_14003F3A0
0x14003f369  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003f370  cmp     rcx, rdi
0x14003f373  jz      loc_14003F61D
0x14003f379  test    [rcx+44h], bl
0x14003f37c  jz      loc_14003F61D
0x14003f382  cmp     [rcx+41h], sil
0x14003f386  jb      loc_14003F61D
0x14003f38c  lea     edx, [rax+50h]
0x14003f38f  mov     rcx, [rcx+38h]
0x14003f393  mov     r8, r12
0x14003f396  call    WPP_SF_
0x14003f39b  jmp     loc_14003F027
0x14003f3a0  mov     rcx, rax
0x14003f3a3  mov     eax, 8
0x14003f3a8  mul     rcx
0x14003f3ab  cmovb   rax, r8
0x14003f3af  mov     rcx, rax; Size
0x14003f3b2  call    ??2@YAPEAX_KK0@Z; operator new(unsigned __int64,ulong,unsigned __int64)
0x14003f3b7  mov     [r14+0B8h], rax
0x14003f3be  test    rax, rax
  ... truncated ...
```
