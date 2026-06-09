# HrRegisterWizardComponentLink(tagXW_COMPONENT_TYPE,ushort * const,tagXW_COMPONENT_TYPE,ushort * const,ulong,ushort * const,void * const)

- ea: `0x180008b4c`
- end: `0x180009597`
- name: `?HrRegisterWizardComponentLink@@YAJW4tagXW_COMPONENT_TYPE@@QEAG01K1QEAX@Z`
- size: `2635`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800085ac`

## callees

- `0x180007820`
- `0x180008b4c`
- `0x18000a948`
- `0x18000a9d4`
- `0x18000ab24`
- `0x18000abbc`
- `0x18000ac34`
- `0x18000ace0`
- `0x18000e40c`
- `0x18000e61c`
- `0x18000fba4`
- `0x180010130`
- `0x180012800`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008c10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800094ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800094f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009529`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009534`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008c10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800094ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800094f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009529`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009534`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008d21`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180009274`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008d21`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180009274`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008ddd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000931d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008ddd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000931d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008d8e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008e54`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008ed5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008f31`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008fa9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000901f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800092ce`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800093b9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009438`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008d8e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008e54`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008ed5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008f31`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008fa9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000901f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800092ce`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800093b9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009438`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800090e6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800090e6`

## string_xrefs

- `0x180008f94`: `Command Line`
- `0x180008c7a`: `Components`
- `0x1800091b5`: `Components`

## pseudocode

```c
__int64 __fastcall HrRegisterWizardComponentLink(
        int a1,
        unsigned __int16 *a2,
        int a3,
        unsigned __int16 *a4,
        int a5,
        BYTE *lpData,
        HKEY *a7)
{
  BYTE *v7; // r12
  int WizardComponentFriendlyName; // ebx
  _QWORD *v11; // rcx
  int v12; // edx
  int v13; // r9d
  __int64 v14; // rdx
  LSTATUS v15; // eax
  __int64 v16; // rax
  bool v17; // sf
  _QWORD *v18; // rcx
  int v19; // edx
  HKEY *v20; // r12
  unsigned __int16 *v21; // r12
  LSTATUS v22; // eax
  const BYTE *v23; // rcx
  __int64 v24; // rax
  bool v25; // sf
  LSTATUS v26; // eax
  __int64 v27; // rax
  bool v28; // sf
  bool v29; // sf
  LSTATUS v30; // eax
  unsigned int v31; // r11d
  LSTATUS v32; // eax
  __int64 v33; // r12
  __int64 v34; // rax
  bool v35; // sf
  _QWORD *v36; // rcx
  int v37; // edx
  BYTE *v38; // rdi
  LSTATUS v39; // eax
  const BYTE *v40; // rcx
  bool v41; // sf
  PHKEY phkResult; // [rsp+38h] [rbp-C8h]
  HKEY *v44; // [rsp+50h] [rbp-B0h]
  BYTE v45[8]; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v47; // [rsp+68h] [rbp-98h]
  BYTE *v48; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwDisposition; // [rsp+78h] [rbp-88h] BYREF
  BYTE Data[4]; // [rsp+80h] [rbp-80h] BYREF
  BYTE v51[4]; // [rsp+88h] [rbp-78h] BYREF
  LPVOID pv; // [rsp+90h] [rbp-70h] BYREF
  DWORD cbData; // [rsp+98h] [rbp-68h] BYREF
  WCHAR SubKey[160]; // [rsp+A0h] [rbp-60h] BYREF

  v7 = lpData;
  v47 = a2;
  *(_DWORD *)Data = a1;
  *(_DWORD *)v51 = a3;
  v44 = a7;
  hKey = 0;
  *(_DWORD *)v45 = 0;
  dwDisposition = 0;
  pv = 0;
  v48 = 0;
  WizardComponentFriendlyName = HrGetWizardComponentFriendlyName(a2, (unsigned __int16 **)&pv);
  if ( WizardComponentFriendlyName >= 0 )
  {
    WizardComponentFriendlyName = HrGetWizardComponentFriendlyName(a4, (unsigned __int16 **)&v48);
    if ( WizardComponentFriendlyName < 0 )
    {
      CoTaskMemFree(pv);
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        return (unsigned int)WizardComponentFriendlyName;
      v12 = 37;
      goto LABEL_122;
    }
    WizardComponentFriendlyName = HrGetWizardComponentCount(a4, v14, v45);
    if ( WizardComponentFriendlyName < 0 )
    {
      CoTaskMemFree(pv);
      CoTaskMemFree(v48);
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        return (unsigned int)WizardComponentFriendlyName;
      v12 = 38;
LABEL_122:
      v13 = (int)a4;
      goto LABEL_123;
    }
    ++*(_DWORD *)v45;
    SubKey[0] = 0;
    StringCchCopyW(SubKey, 0x9Du, L"Software\\Microsoft\\Windows\\CurrentVersion\\XWizards\\");
    StringCchCatW(SubKey, 0x9Du, L"Components");
    StringCchCatW(SubKey, 0x9Du, L"\\");
    StringCchCatW(SubKey, 0x9Du, a4);
    StringCchCatW(SubKey, 0x9Du, L"\\");
    StringCchCatW(SubKey, 0x9Du, L"Children");
    StringCchCatW(SubKey, 0x9Du, L"\\");
    StringCchCatW(SubKey, 0x9Du, a2);
    v15 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, &dwDisposition);
    WizardComponentFriendlyName = v15;
    if ( v15 )
    {
      if ( v15 > 0 )
        WizardComponentFriendlyName = (unsigned __int16)v15 | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          47,
          (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
          (unsigned int)SubKey,
          WizardComponentFriendlyName);
      if ( WizardComponentFriendlyName < 0 )
        goto LABEL_115;
      v21 = v47;
      goto LABEL_76;
    }
    if ( dwDisposition != 1 )
    {
      WizardComponentFriendlyName = 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          45,
          (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
          (unsigned int)SubKey,
          1);
      v20 = v44;
      if ( v44 )
      {
        *(_DWORD *)v45 = 0;
        cbData = 4;
        v30 = RegQueryValueExW(hKey, L"Ordinal", 0, 0, v45, &cbData);
        if ( (v30 || !*(_DWORD *)v45)
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_LSD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            46,
            (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
            *(_DWORD *)v45,
            (__int64)SubKey,
            v30);
        }
      }
      goto LABEL_23;
    }
    if ( !pv )
      goto LABEL_25;
    v16 = -1;
    do
      ++v16;
    while ( *((_WORD *)pv + v16) );
    WizardComponentFriendlyName = RegSetValueExW(hKey, 0, 0, 1u, (const BYTE *)pv, 2 * v16 + 2);
    v17 = WizardComponentFriendlyName < 0;
    if ( WizardComponentFriendlyName > 0 )
    {
      WizardComponentFriendlyName = (unsigned __int16)WizardComponentFriendlyName | 0x80070000;
      v17 = WizardComponentFriendlyName < 0;
    }
    if ( v17 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_22;
      v19 = 39;
    }
    else
    {
LABEL_25:
      v22 = RegSetValueExW(hKey, L"Class Type", 0, 4u, Data, 4u);
      WizardComponentFriendlyName = v22;
      if ( v22 > 0 )
        WizardComponentFriendlyName = (unsigned __int16)v22 | 0x80070000;
      if ( WizardComponentFriendlyName >= 0 )
      {
        v23 = (const BYTE *)qword_18001D1A0[2 * *(int *)Data + 1];
        v24 = -1;
        do
          ++v24;
        while ( *(_WORD *)&v23[2 * v24] );
        WizardComponentFriendlyName = RegSetValueExW(hKey, L"Class Description", 0, 1u, v23, 2 * v24 + 2);
        v25 = WizardComponentFriendlyName < 0;
        if ( WizardComponentFriendlyName > 0 )
        {
          WizardComponentFriendlyName = (unsigned __int16)WizardComponentFriendlyName | 0x80070000;
          v25 = WizardComponentFriendlyName < 0;
        }
        if ( v25 )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
            goto LABEL_22;
          v19 = 41;
        }
        else
        {
          v26 = RegSetValueExW(hKey, L"User Flags", 0, 4u, (const BYTE *)&a5, 4u);
          WizardComponentFriendlyName = v26;
          if ( v26 > 0 )
            WizardComponentFriendlyName = (unsigned __int16)v26 | 0x80070000;
          if ( WizardComponentFriendlyName >= 0 )
          {
            if ( !v7 )
              goto LABEL_54;
            v27 = -1;
            do
              ++v27;
            while ( *(_WORD *)&v7[2 * v27] );
            WizardComponentFriendlyName = RegSetValueExW(hKey, L"Command Line", 0, 1u, v7, 2 * v27 + 2);
            v28 = WizardComponentFriendlyName < 0;
            if ( WizardComponentFriendlyName > 0 )
            {
              WizardComponentFriendlyName = (unsigned __int16)WizardComponentFriendlyName | 0x80070000;
              v28 = WizardComponentFriendlyName < 0;
            }
            if ( v28 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                WPP_SF_SSD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  43,
                  (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
                  (_DWORD)v7,
                  (__int64)SubKey,
                  WizardComponentFriendlyName);
            }
            else
            {
LABEL_54:
              WizardComponentFriendlyName = RegSetValueExW(hKey, L"Ordinal", 0, 4u, v45, 4u);
              v29 = WizardComponentFriendlyName < 0;
              if ( WizardComponentFriendlyName > 0 )
              {
                WizardComponentFriendlyName = (unsigned __int16)WizardComponentFriendlyName | 0x80070000;
                v29 = WizardComponentFriendlyName < 0;
              }
              if ( v29 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                WPP_SF_LSD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  44,
                  (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
                  *(_DWORD *)v45,
                  (__int64)SubKey,
                  WizardComponentFriendlyName);
            }
            goto LABEL_22;
          }
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          {
LABEL_22:
            v20 = v44;
LABEL_23:
            RegCloseKey(hKey);
            if ( WizardComponentFriendlyName < 0 )
              goto LABEL_115;
            phkResult = v20;
            v21 = v47;
            HrWriteManifestChildLink(
              a4,
              v47,
              pv,
              qword_18001D1A0[2 * *(int *)Data + 1],
              *(_DWORD *)Data,
              *(_DWORD *)v45,
              a5,
              phkResult);
LABEL_76:
            SubKey[0] = 0;
            StringCchCopyW(SubKey, 0x9Du, L"Software\\Microsoft\\Windows\\CurrentVersion\\XWizards\\");
            StringCchCatW(SubKey, v31, L"Components");
            StringCchCatW(SubKey, 0x9Du, L"\\");
            StringCchCatW(SubKey, 0x9Du, v21);
            StringCchCatW(SubKey, 0x9Du, L"\\");
            StringCchCatW(SubKey, 0x9Du, L"Parents");
            StringCchCatW(SubKey, 0x9Du, L"\\");
            StringCchCatW(SubKey, 0x9Du, a4);
            v32 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, &dwDisposition);
            WizardComponentFriendlyName = v32;
            if ( !v32 )
            {
              if ( dwDisposition != 1 )
              {
                WizardComponentFriendlyName = 1;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                  WPP_SF_SD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    51,
                    (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
                    (unsigned int)SubKey,
                    1);
                goto LABEL_89;
              }
              v33 = -1;
              if ( !v48 )
                goto LABEL_93;
              v34 = -1;
              do
                ++v34;
              while ( *(_WORD *)&v48[2 * v34] );
              WizardComponentFriendlyName = RegSetValueExW(hKey, 0, 0, 1u, v48, 2 * v34 + 2);
              v35 = WizardComponentFriendlyName < 0;
              if ( WizardComponentFriendlyName > 0 )
              {
                WizardComponentFriendlyName = (unsigned __int16)WizardComponentFriendlyName | 0x80070000;
                v35 = WizardComponentFriendlyName < 0;
              }
              if ( v35 )
              {
                v36 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
                  goto LABEL_88;
                v37 = 48;
              }
              else
              {
LABEL_93:
                v39 = RegSetValueExW(hKey, L"Class Type", 0, 4u, v51, 4u);
                WizardComponentFriendlyName = v39;
                if ( v39 > 0 )
                  WizardComponentFriendlyName = (unsigned __int16)v39 | 0x80070000;
                if ( WizardComponentFriendlyName >= 0 )
                {
                  v40 = (const BYTE *)qword_18001D1A0[2 * *(int *)v51 + 1];
                  do
                    ++v33;
                  while ( *(_WORD *)&v40[2 * v33] );
                  WizardComponentFriendlyName = RegSetValueExW(hKey, L"Class Description", 0, 1u, v40, 2 * v33 + 2);
                  v41 = WizardComponentFriendlyName < 0;
                  if ( WizardComponentFriendlyName > 0 )
                  {
                    WizardComponentFriendlyName = (unsigned __int16)WizardComponentFriendlyName | 0x80070000;
                    v41 = WizardComponentFriendlyName < 0;
                  }
                  if ( !v41 )
                    goto LABEL_88;
                  v36 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
                    goto LABEL_88;
                  v37 = 50;
                }
                else
                {
                  v36 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
                    goto LABEL_88;
                  v37 = 49;
                }
              }
              WPP_SF_SD(
                v36[2],
                v37,
                (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
                (unsigned int)SubKey,
                WizardComponentFriendlyName);
LABEL_88:
              v21 = v47;
LABEL_89:
              RegCloseKey(hKey);
              v38 = v48;
              if ( WizardComponentFriendlyName >= 0 )
              {
                HrWriteManifestParentLink(v21, a4, v48, qword_18001D1A0[2 * *(int *)v51 + 1], *(_DWORD *)v51, v44);
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                  WPP_SF_SS(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    52,
                    (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
                    (_DWORD)a4,
                    (__int64)v21);
              }
              goto LABEL_116;
            }
            if ( v32 > 0 )
              WizardComponentFriendlyName = (unsigned __int16)v32 | 0x80070000;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_SD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                53,
                (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
                (unsigned int)SubKey,
                WizardComponentFriendlyName);
LABEL_115:
            v38 = v48;
LABEL_116:
            CoTaskMemFree(pv);
            CoTaskMemFree(v38);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
              WPP_SF_D(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                54,
                &WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
                (unsigned int)WizardComponentFriendlyName);
            return (unsigned int)WizardComponentFriendlyName;
          }
          v19 = 42;
        }
      }
      else
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_22;
        v19 = 40;
      }
    }
    WPP_SF_SD(
      v18[2],
      v19,
      (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
      (unsigned int)SubKey,
      WizardComponentFriendlyName);
    goto LABEL_22;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v12 = 36;
    v13 = (int)a2;
LABEL_123:
    WPP_SF_SD(
      v11[2],
      v12,
      (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
      v13,
      WizardComponentFriendlyName);
  }
  return (unsigned int)WizardComponentFriendlyName;
}

```

## disassembly

```asm
0x180008b4c  push    rbp
0x180008b4e  push    rbx
0x180008b4f  push    rsi
0x180008b50  push    rdi
0x180008b51  push    r12
0x180008b53  push    r13
0x180008b55  push    r14
0x180008b57  push    r15
0x180008b59  lea     rbp, [rsp-0F8h]
0x180008b61  sub     rsp, 1F8h
0x180008b68  mov     rax, cs:__security_cookie
0x180008b6f  xor     rax, rsp
0x180008b72  mov     [rbp+130h+var_50], rax
0x180008b79  mov     rax, [rbp+130h+arg_30]
0x180008b80  xor     edi, edi
0x180008b82  mov     r12, [rbp+130h+lpData]
0x180008b89  mov     r14, rdx
0x180008b8c  mov     [rsp+230h+var_1C8], rdx
0x180008b91  mov     r13, r9
0x180008b94  mov     dword ptr [rbp+130h+Data], ecx
0x180008b97  lea     rdx, [rbp+130h+pv]; unsigned __int16 **
0x180008b9b  mov     rcx, r14; unsigned __int16 *
0x180008b9e  mov     dword ptr [rbp+130h+var_1A8], r8d
0x180008ba2  mov     [rsp+230h+var_1E0], rax
0x180008ba7  mov     [rsp+230h+hKey], rdi
0x180008bac  mov     dword ptr [rsp+230h+var_1D8], edi
0x180008bb0  mov     [rsp+230h+dwDisposition], edi
0x180008bb4  mov     [rbp+130h+pv], rdi
0x180008bb8  mov     [rsp+230h+var_1C0], rdi
0x180008bbd  call    ?HrGetWizardComponentFriendlyName@@YAJQEAGPEAPEAG@Z; HrGetWizardComponentFriendlyName(ushort * const,ushort * *)
0x180008bc2  mov     ebx, eax
0x180008bc4  test    eax, eax
0x180008bc6  jns     short loc_180008BF9
0x180008bc8  mov     rcx, cs:WPP_GLOBAL_Control
0x180008bcf  lea     rsi, WPP_GLOBAL_Control
0x180008bd6  cmp     rcx, rsi
0x180008bd9  jz      loc_180009572
0x180008bdf  mov     edi, 4
0x180008be4  test    [rcx+1Ch], dil
0x180008be8  jz      loc_180009572
0x180008bee  lea     edx, [rdi+20h]
0x180008bf1  mov     r9, r14
0x180008bf4  jmp     loc_18000955E
0x180008bf9  lea     rdx, [rsp+230h+var_1C0]; unsigned __int16 **
0x180008bfe  mov     rcx, r13; unsigned __int16 *
0x180008c01  call    ?HrGetWizardComponentFriendlyName@@YAJQEAGPEAPEAG@Z; HrGetWizardComponentFriendlyName(ushort * const,ushort * *)
0x180008c06  mov     ebx, eax
0x180008c08  test    eax, eax
0x180008c0a  jns     short loc_180008C44
0x180008c0c  mov     rcx, [rbp+130h+pv]; pv
0x180008c10  call    cs:__imp_CoTaskMemFree
0x180008c16  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c1d  lea     rsi, WPP_GLOBAL_Control
0x180008c24  cmp     rcx, rsi
0x180008c27  jz      loc_180009572
0x180008c2d  mov     edi, 4
0x180008c32  test    [rcx+1Ch], dil
0x180008c36  jz      loc_180009572
0x180008c3c  lea     edx, [rdi+21h]
0x180008c3f  jmp     loc_18000955B
0x180008c44  lea     r8, [rsp+230h+var_1D8]
0x180008c49  mov     rcx, r13
0x180008c4c  call    ?HrGetWizardComponentCount@@YAJQEAGW4tagXW_COMPONENT_HIERARCHY@@PEAK@Z; HrGetWizardComponentCount(ushort * const,tagXW_COMPONENT_HIERARCHY,ulong *)
0x180008c51  mov     ebx, eax
0x180008c53  test    eax, eax
0x180008c55  js      loc_180009525
0x180008c5b  inc     dword ptr [rsp+230h+var_1D8]
0x180008c5f  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180008c66  mov     ebx, 9Dh
0x180008c6b  mov     [rbp+130h+SubKey], di
0x180008c6f  mov     edx, ebx; unsigned __int64
0x180008c71  lea     rcx, [rbp+130h+SubKey]; unsigned __int16 *
0x180008c75  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008c7a  lea     r8, aComponents; "Components"
0x180008c81  mov     edx, ebx; unsigned __int64
0x180008c83  lea     rcx, [rbp+130h+SubKey]; unsigned __int16 *
0x180008c87  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008c8c  lea     rsi, asc_180016A5C; "\\"
0x180008c93  mov     edx, ebx; unsigned __int64
0x180008c95  mov     r8, rsi; unsigned __int16 *
0x180008c98  lea     rcx, [rbp+130h+SubKey]; unsigned __int16 *
0x180008c9c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008ca1  mov     r8, r13; unsigned __int16 *
0x180008ca4  lea     rcx, [rbp+130h+SubKey]; unsigned __int16 *
0x180008ca8  mov     edx, ebx; unsigned __int64
0x180008caa  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008caf  mov     r8, rsi; unsigned __int16 *
0x180008cb2  lea     rcx, [rbp+130h+SubKey]; unsigned __int16 *
0x180008cb6  mov     edx, ebx; unsigned __int64
0x180008cb8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008cbd  lea     r8, aChildren; "Children"
0x180008cc4  mov     edx, ebx; unsigned __int64
0x180008cc6  lea     rcx, [rbp+130h+SubKey]; unsigned __int16 *
0x180008cca  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008ccf  mov     r8, rsi; unsigned __int16 *
0x180008cd2  lea     rcx, [rbp+130h+SubKey]; unsigned __int16 *
0x180008cd6  mov     edx, ebx; unsigned __int64
0x180008cd8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008cdd  mov     r8, r14; unsigned __int16 *
0x180008ce0  lea     rcx, [rbp+130h+SubKey]; unsigned __int16 *
0x180008ce4  mov     edx, ebx; unsigned __int64
0x180008ce6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008ceb  lea     rax, [rsp+230h+dwDisposition]
0x180008cf0  xor     r9d, r9d; lpClass
0x180008cf3  mov     [rsp+230h+lpdwDisposition], rax; lpdwDisposition
0x180008cf8  lea     rdx, [rbp+130h+SubKey]; lpSubKey
0x180008cfc  lea     rax, [rsp+230h+hKey]
0x180008d01  xor     r8d, r8d; Reserved
0x180008d04  mov     [rsp+230h+phkResult], rax; phkResult
0x180008d09  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008d10  mov     [rsp+230h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180008d15  mov     [rsp+230h+samDesired], 2001Fh; samDesired
0x180008d1d  mov     [rsp+230h+dwOptions], edi; dwOptions
0x180008d21  call    cs:__imp_RegCreateKeyExW
0x180008d27  mov     ebx, eax
0x180008d29  mov     r15d, 80070000h
0x180008d2f  test    eax, eax
0x180008d31  jnz     loc_180009145
0x180008d37  lea     r8d, [rax+1]
0x180008d3b  lea     edi, [rax+4]
0x180008d3e  lea     r14, WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids
0x180008d45  lea     rsi, WPP_GLOBAL_Control
0x180008d4c  cmp     [rsp+230h+dwDisposition], r8d
0x180008d51  jnz     loc_18000907B
0x180008d57  mov     rcx, [rbp+130h+pv]
0x180008d5b  xor     edx, edx; lpValueName
0x180008d5d  test    rcx, rcx
0x180008d60  jz      loc_180008E35
0x180008d66  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008d6a  inc     rax
0x180008d6d  cmp     [rcx+rax*2], dx
0x180008d71  jnz     short loc_180008D6A
0x180008d73  lea     eax, ds:2[rax*2]
0x180008d7a  mov     r9d, r8d; dwType
0x180008d7d  mov     [rsp+230h+samDesired], eax; cbData
0x180008d81  xor     r8d, r8d; Reserved
0x180008d84  mov     qword ptr [rsp+230h+dwOptions], rcx; lpData
0x180008d89  mov     rcx, [rsp+230h+hKey]; hKey
0x180008d8e  call    cs:__imp_RegSetValueExW
0x180008d94  mov     ebx, eax
0x180008d96  test    eax, eax
0x180008d98  jle     short loc_180008DA2
0x180008d9a  movzx   ebx, bx
0x180008d9d  or      ebx, r15d
0x180008da0  test    ebx, ebx
0x180008da2  jns     loc_180008E35
0x180008da8  mov     rcx, cs:WPP_GLOBAL_Control
0x180008daf  cmp     rcx, rsi
0x180008db2  jz      short loc_180008DD3
0x180008db4  test    [rcx+1Ch], dil
0x180008db8  jz      short loc_180008DD3
0x180008dba  mov     edx, 27h ; '''
0x180008dbf  mov     rcx, [rcx+10h]
0x180008dc3  lea     r9, [rbp+130h+SubKey]
0x180008dc7  mov     r8, r14
0x180008dca  mov     [rsp+230h+dwOptions], ebx
0x180008dce  call    WPP_SF_SD
0x180008dd3  mov     r12, [rsp+230h+var_1E0]
0x180008dd8  mov     rcx, [rsp+230h+hKey]; hKey
0x180008ddd  call    cs:__imp_RegCloseKey
0x180008de3  test    ebx, ebx
0x180008de5  js      loc_1800094E5
0x180008deb  movsxd  rcx, dword ptr [rbp+130h+Data]
0x180008def  mov     eax, [rbp+130h+arg_20]
0x180008df5  mov     r9, rcx
0x180008df8  mov     r8, [rbp+130h+pv]
0x180008dfc  add     r9, r9
0x180008dff  mov     [rsp+230h+phkResult], r12
0x180008e04  mov     r12, [rsp+230h+var_1C8]
0x180008e09  mov     dword ptr [rsp+230h+lpSecurityAttributes], eax
0x180008e0d  mov     rdx, r12
0x180008e10  mov     eax, dword ptr [rsp+230h+var_1D8]
0x180008e14  mov     [rsp+230h+samDesired], eax
0x180008e18  lea     rax, qword_18001D1A0
0x180008e1f  mov     r9, [rax+r9*8+8]
0x180008e24  mov     [rsp+230h+dwOptions], ecx
0x180008e28  mov     rcx, r13
0x180008e2b  call    ?HrWriteManifestChildLink@@YAJQEAG000W4tagXW_COMPONENT_TYPE@@KKQEAX@Z; HrWriteManifestChildLink(ushort * const,ushort * const,ushort * const,ushort * const,tagXW_COMPONENT_TYPE,ulong,ulong,void * const)
0x180008e30  jmp     loc_180009196
0x180008e35  mov     rcx, [rsp+230h+hKey]; hKey
0x180008e3a  lea     rax, [rbp+130h+Data]
0x180008e3e  mov     [rsp+230h+samDesired], edi; cbData
0x180008e42  lea     rdx, ValueName; "Class Type"
0x180008e49  mov     r9d, edi; dwType
0x180008e4c  mov     qword ptr [rsp+230h+dwOptions], rax; lpData
0x180008e51  xor     r8d, r8d; Reserved
0x180008e54  call    cs:__imp_RegSetValueExW
0x180008e5a  xor     edx, edx
0x180008e5c  mov     ebx, eax
0x180008e5e  test    eax, eax
0x180008e60  jle     short loc_180008E68
0x180008e62  movzx   ebx, ax
0x180008e65  or      ebx, r15d
0x180008e68  test    ebx, ebx
0x180008e6a  jns     short loc_180008E90
0x180008e6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e73  cmp     rcx, rsi
0x180008e76  jz      loc_180008DD3
0x180008e7c  test    [rcx+1Ch], dil
0x180008e80  jz      loc_180008DD3
0x180008e86  mov     edx, 28h ; '('
0x180008e8b  jmp     loc_180008DBF
0x180008e90  movsxd  rax, dword ptr [rbp+130h+Data]
0x180008e94  lea     rcx, qword_18001D1A0
0x180008e9b  add     rax, rax
0x180008e9e  mov     rcx, [rcx+rax*8+8]
0x180008ea3  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008ea7  inc     rax
0x180008eaa  cmp     [rcx+rax*2], dx
0x180008eae  jnz     short loc_180008EA7
0x180008eb0  lea     eax, ds:2[rax*2]
0x180008eb7  mov     r9d, 1; dwType
0x180008ebd  mov     [rsp+230h+samDesired], eax; cbData
0x180008ec1  lea     rdx, aClassDescripti; "Class Description"
0x180008ec8  mov     qword ptr [rsp+230h+dwOptions], rcx; lpData
0x180008ecd  xor     r8d, r8d; Reserved
0x180008ed0  mov     rcx, [rsp+230h+hKey]; hKey
0x180008ed5  call    cs:__imp_RegSetValueExW
0x180008edb  mov     ebx, eax
0x180008edd  test    eax, eax
0x180008edf  jle     short loc_180008EE9
0x180008ee1  movzx   ebx, bx
0x180008ee4  or      ebx, r15d
0x180008ee7  test    ebx, ebx
0x180008ee9  jns     short loc_180008F0F
0x180008eeb  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ef2  cmp     rcx, rsi
0x180008ef5  jz      loc_180008DD3
0x180008efb  test    [rcx+1Ch], dil
0x180008eff  jz      loc_180008DD3
0x180008f05  mov     edx, 29h ; ')'
0x180008f0a  jmp     loc_180008DBF
0x180008f0f  mov     rcx, [rsp+230h+hKey]; hKey
0x180008f14  lea     rax, [rbp+130h+arg_20]
0x180008f1b  mov     [rsp+230h+samDesired], edi; cbData
0x180008f1f  lea     rdx, aUserFlags; "User Flags"
0x180008f26  mov     r9d, edi; dwType
0x180008f29  mov     qword ptr [rsp+230h+dwOptions], rax; lpData
0x180008f2e  xor     r8d, r8d; Reserved
0x180008f31  call    cs:__imp_RegSetValueExW
0x180008f37  xor     ecx, ecx
0x180008f39  mov     ebx, eax
0x180008f3b  test    eax, eax
0x180008f3d  jle     short loc_180008F45
0x180008f3f  movzx   ebx, ax
0x180008f42  or      ebx, r15d
0x180008f45  test    ebx, ebx
0x180008f47  jns     short loc_180008F6D
0x180008f49  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f50  cmp     rcx, rsi
0x180008f53  jz      loc_180008DD3
0x180008f59  test    [rcx+1Ch], dil
0x180008f5d  jz      loc_180008DD3
0x180008f63  mov     edx, 2Ah ; '*'
0x180008f68  jmp     loc_180008DBF
0x180008f6d  test    r12, r12
0x180008f70  jz      loc_180008FFF
0x180008f76  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008f7a  inc     rax
0x180008f7d  cmp     [r12+rax*2], cx
0x180008f82  jnz     short loc_180008F7A
0x180008f84  mov     rcx, [rsp+230h+hKey]; hKey
0x180008f89  lea     eax, ds:2[rax*2]
0x180008f90  mov     [rsp+230h+samDesired], eax; cbData
0x180008f94  lea     rdx, aCommandLine; "Command Line"
0x180008f9b  mov     r9d, 1; dwType
0x180008fa1  mov     qword ptr [rsp+230h+dwOptions], r12; lpData
0x180008fa6  xor     r8d, r8d; Reserved
0x180008fa9  call    cs:__imp_RegSetValueExW
0x180008faf  mov     ebx, eax
0x180008fb1  test    eax, eax
0x180008fb3  jle     short loc_180008FBD
0x180008fb5  movzx   ebx, bx
0x180008fb8  or      ebx, r15d
0x180008fbb  test    ebx, ebx
0x180008fbd  jns     short loc_180008FFF
0x180008fbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180008fc6  cmp     rcx, rsi
0x180008fc9  jz      loc_180008DD3
0x180008fcf  test    [rcx+1Ch], dil
0x180008fd3  jz      loc_180008DD3
0x180008fd9  mov     rcx, [rcx+10h]
0x180008fdd  lea     rax, [rbp+130h+SubKey]
0x180008fe1  mov     edx, 2Bh ; '+'
0x180008fe6  mov     [rsp+230h+samDesired], ebx
0x180008fea  mov     r9, r12
0x180008fed  mov     qword ptr [rsp+230h+dwOptions], rax
0x180008ff2  mov     r8, r14
0x180008ff5  call    WPP_SF_SSD
0x180008ffa  jmp     loc_180008DD3
0x180008fff  mov     rcx, [rsp+230h+hKey]; hKey
0x180009004  lea     rax, [rsp+230h+var_1D8]
0x180009009  mov     [rsp+230h+samDesired], edi; cbData
0x18000900d  lea     rdx, aOrdinal; "Ordinal"
0x180009014  mov     r9d, edi; dwType
0x180009017  mov     qword ptr [rsp+230h+dwOptions], rax; lpData
0x18000901c  xor     r8d, r8d; Reserved
0x18000901f  call    cs:__imp_RegSetValueExW
0x180009025  mov     ebx, eax
0x180009027  test    eax, eax
  ... truncated ...
```
