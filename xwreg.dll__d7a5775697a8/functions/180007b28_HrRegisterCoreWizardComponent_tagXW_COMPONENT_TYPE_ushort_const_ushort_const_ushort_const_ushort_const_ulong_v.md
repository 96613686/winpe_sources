# HrRegisterCoreWizardComponent(tagXW_COMPONENT_TYPE,ushort * const,ushort * const,ushort * const,ushort * const,ulong,void * const)

- ea: `0x180007b28`
- end: `0x1800085a6`
- name: `?HrRegisterCoreWizardComponent@@YAJW4tagXW_COMPONENT_TYPE@@QEAG111KQEAX@Z`
- size: `2686`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800085ac`

## callees

- `0x180007820`
- `0x180007b28`
- `0x18000a948`
- `0x18000a9d4`
- `0x18000abbc`
- `0x18000ac34`
- `0x18000ace0`
- `0x18000ae4c`
- `0x18000daac`
- `0x18000ded4`
- `0x18000ebc0`
- `0x18000f010`
- `0x18000fd80`
- `0x180010400`
- `0x180010518`
- `0x1800127d6`
- `0x180012800`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000850b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000850b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180007ceb`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180007ceb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007ec1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007ec1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007c37`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007c37`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007e4c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007ee1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007e4c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007ee1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007ded`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008100`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000817e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008216`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800082b1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008311`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008387`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007ded`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008100`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000817e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008216`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800082b1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008311`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008387`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007cc2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007cc2`

## string_xrefs

- `0x18000807c`: `xwizards.dll`
- `0x180008257`: `%SystemRoot%\System32\xwizards.dll`
- `0x180008373`: `Wrapped CLSID`
- `0x180007bc8`: `Components`
- `0x180007e8b`: `Components`
- `0x1800084b2`: `Components`

## pseudocode

```c
__int64 __fastcall HrRegisterCoreWizardComponent(
        int a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        const WCHAR *a4,
        const BYTE *a5,
        int a6,
        void *a7)
{
  int v10; // r15d
  LSTATUS v11; // eax
  int v12; // ebx
  BYTE *v13; // r12
  int v14; // ecx
  HRESULT v15; // eax
  enum tagXW_COMPONENT_TYPE *v16; // rdx
  int ComponentInfo; // eax
  PVOID *v18; // rcx
  void *v19; // r15
  __int16 v20; // r11
  __int64 v21; // r15
  bool v22; // sf
  __int64 v23; // rsi
  unsigned int v24; // r11d
  _QWORD *v25; // rcx
  int v26; // edx
  const WCHAR *v27; // rdx
  __int64 v28; // r15
  __int64 v29; // rax
  LSTATUS v30; // eax
  LSTATUS v31; // eax
  _QWORD *v32; // rcx
  int v33; // edx
  const BYTE *v34; // rcx
  __int64 v35; // rax
  LSTATUS v36; // eax
  const unsigned __int16 *v37; // r11
  const BYTE *v38; // r11
  __int64 v39; // rax
  LSTATUS v40; // eax
  LSTATUS v41; // eax
  LSTATUS v42; // eax
  PVOID *v43; // rcx
  void *v45; // [rsp+58h] [rbp-A8h]
  BYTE *lpData; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  HKEY v48; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v49; // [rsp+78h] [rbp-88h] BYREF
  BYTE v50[4]; // [rsp+80h] [rbp-80h] BYREF
  BYTE v51[4]; // [rsp+88h] [rbp-78h] BYREF
  BOOL v52; // [rsp+8Ch] [rbp-74h]
  DWORD dwDisposition; // [rsp+90h] [rbp-70h] BYREF
  BYTE Data[4]; // [rsp+94h] [rbp-6Ch] BYREF
  DWORD cbData; // [rsp+98h] [rbp-68h] BYREF
  CLSID pclsid; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR SubKey[112]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v58[264]; // [rsp+190h] [rbp+90h] BYREF

  v45 = a7;
  v48 = (HKEY)a3;
  *(_DWORD *)v50 = a1;
  if ( !a4 || (v10 = 1, *a4 != 42) )
    v10 = 0;
  v49 = 0;
  memset_0(v58, 0, 0x20Au);
  SubKey[0] = 0;
  StringCchCopyW(SubKey, 0x69u, L"Software\\Microsoft\\Windows\\CurrentVersion\\XWizards\\");
  StringCchCatW(SubKey, 0x69u, L"Components");
  StringCchCatW(SubKey, 0x69u, L"\\");
  StringCchCatW(SubKey, 0x69u, a2);
  hKey = 0;
  dwDisposition = 0;
  v11 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, &dwDisposition);
  v12 = v11;
  if ( !v11 )
  {
    v52 = 0;
    v13 = 0;
    lpData = 0;
    if ( (_WORD)a6 == 0xBACE )
    {
      v14 = 0x10000;
    }
    else
    {
      v14 = (unsigned __int16)a6;
      if ( HIWORD(a6) == 0xBACE )
        v14 = (unsigned __int16)a6 | 0x10000;
    }
    *(_DWORD *)v51 = v14;
    if ( dwDisposition != 1 )
    {
      *(_DWORD *)Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"Class Type", 0, 0, Data, &cbData) )
      {
        if ( *(_DWORD *)Data )
        {
          pclsid = 0;
          v15 = CLSIDFromString(a2, &pclsid);
          v12 = v15;
          if ( v15 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_SD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                31,
                (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
                (_DWORD)a2,
                v15);
            goto LABEL_29;
          }
          ComponentInfo = HrGetComponentInfo(&pclsid, v16, &v49);
          if ( ComponentInfo < 0 )
          {
            v18 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
              goto LABEL_18;
            WPP_SF_SD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              26,
              (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
              (_DWORD)a2,
              ComponentInfo);
          }
          v18 = (PVOID *)WPP_GLOBAL_Control;
LABEL_18:
          if ( !v10 )
          {
            if ( (unsigned int)IsComponentModuleNameResolved(&pclsid) )
            {
              v12 = 1;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                WPP_SF_SD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  29,
                  (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
                  (unsigned int)SubKey,
                  1);
              v19 = a7;
              if ( !a7 )
                goto LABEL_30;
              if ( (int)HrEnsureCOMRegistration(a2, a4, (unsigned __int16 **const)&lpData, a7) >= 0 )
              {
                v13 = lpData;
                v58[0] = 0;
                StringCchCopyW(v58, 0x105u, (const unsigned __int16 *)lpData);
                goto LABEL_30;
              }
              goto LABEL_40;
            }
            v19 = a7;
            v12 = HrEnsureCOMRegistration(a2, a4, (unsigned __int16 **const)&lpData, a7);
            if ( v12 >= 0 )
            {
              v13 = lpData;
              v58[0] = 0;
              v52 = v12 == 0;
              v49 = *(_DWORD *)v51;
              StringCchCopyW(v58, 0x105u, (const unsigned __int16 *)lpData);
              v21 = -1;
              do
                ++v21;
              while ( *(_WORD *)&v13[2 * v21] != v20 );
              v12 = RegSetValueExW(hKey, L"File Name", 0, 2u, v13, 2 * v21 + 2);
              v22 = v12 < 0;
              if ( v12 > 0 )
              {
                v12 = (unsigned __int16)v12 | 0x80070000;
                v22 = v12 < 0;
              }
              if ( v22 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                WPP_SF_SSD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  27,
                  (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
                  (_DWORD)v13,
                  (__int64)SubKey,
                  v12);
LABEL_29:
              v19 = a7;
LABEL_30:
              v23 = (__int64)a5;
              goto LABEL_31;
            }
            v25 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
            {
LABEL_40:
              v13 = lpData;
              goto LABEL_30;
            }
            v26 = 28;
LABEL_39:
            WPP_SF_SSD(
              v25[2],
              v26,
              (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
              (_DWORD)a2,
              (__int64)a4,
              v12);
            goto LABEL_40;
          }
          v12 = 1;
          if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 0x10) != 0 )
            WPP_SF_SD(
              (unsigned int)v18[2],
              30,
              (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
              (unsigned int)SubKey,
              1);
          v19 = a7;
          v23 = (__int64)a5;
          if ( a7 )
            v19 = 0;
LABEL_31:
          RegCloseKey(hKey);
          if ( v12 >= 0 )
          {
            HrWriteManifestCoreEntry(a2, v23, v58);
            v43 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              WPP_SF_sSSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a2, v23, qword_18001D1A0[2 * *(int *)v50 + 1]);
              v43 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( !v48
              || (HrWriteManifestWrappedEntry(L"Components", a2, (unsigned __int16 *const)v48, v19),
                  v43 = (PVOID *)WPP_GLOBAL_Control,
                  WPP_GLOBAL_Control == &WPP_GLOBAL_Control)
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
            {
LABEL_124:
              if ( v13 != (BYTE *)L"*" )
              {
                CoTaskMemFree(v13);
LABEL_131:
                v43 = (PVOID *)WPP_GLOBAL_Control;
                goto LABEL_132;
              }
              goto LABEL_132;
            }
            WPP_SF_SS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              33,
              (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
              (_DWORD)v48,
              (__int64)a2);
          }
          else
          {
            if ( v52 )
              HrRegisterOrUnregisterWithCOM((LPCWSTR)v13, 0);
            SubKey[0] = 0;
            StringCchCopyW(SubKey, 0x69u, L"Software\\Microsoft\\Windows\\CurrentVersion\\XWizards\\");
            StringCchCatW(SubKey, v24, L"Components");
            v48 = 0;
            if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20006u, &v48) )
            {
              HrRegDeleteSubKeyTree(v48, a2);
              RegCloseKey(v48);
            }
          }
          v43 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_124;
        }
      }
    }
    if ( v10 )
    {
      v13 = (BYTE *)L"*";
      v45 = 0;
      v12 = 1;
    }
    else
    {
      v19 = a7;
      if ( a3 )
      {
        v12 = HrEnsureCOMRegistration(a3, a4, (unsigned __int16 **const)&lpData, a7);
        if ( v12 < 0 )
          goto LABEL_113;
      }
      v27 = L"xwizards.dll";
      if ( !a3 )
        v27 = a4;
      v12 = HrEnsureCOMRegistration(a2, v27, (unsigned __int16 **const)&lpData, a7);
      if ( v12 < 0 )
      {
LABEL_113:
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          goto LABEL_40;
        v26 = 25;
        goto LABEL_39;
      }
      v13 = lpData;
    }
    v28 = -1;
    v52 = v12 == 0;
    if ( a5 )
    {
      v29 = -1;
      do
        ++v29;
      while ( *(_WORD *)&a5[2 * v29] );
      v30 = RegSetValueExW(hKey, 0, 0, 1u, a5, 2 * v29 + 2);
      v12 = v30;
      if ( v30 > 0 )
        v12 = (unsigned __int16)v30 | 0x80070000;
      if ( v12 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          v23 = (__int64)a5;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_SSD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              19,
              (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
              (_DWORD)a5,
              (__int64)SubKey,
              v12);
          goto LABEL_112;
        }
        goto LABEL_111;
      }
    }
    v31 = RegSetValueExW(hKey, L"Class Type", 0, 4u, v50, 4u);
    v12 = v31;
    if ( v31 > 0 )
      v12 = (unsigned __int16)v31 | 0x80070000;
    if ( v12 >= 0 )
    {
      v34 = (const BYTE *)qword_18001D1A0[2 * *(int *)v50 + 1];
      v35 = -1;
      do
        ++v35;
      while ( *(_WORD *)&v34[2 * v35] );
      v36 = RegSetValueExW(hKey, L"Class Description", 0, 1u, v34, 2 * v35 + 2);
      v12 = v36;
      if ( v36 > 0 )
        v12 = (unsigned __int16)v36 | 0x80070000;
      if ( v12 >= 0 )
      {
        v37 = L"%SystemRoot%\\System32\\xwizards.dll";
        v58[0] = 0;
        if ( !v48 )
          v37 = (const unsigned __int16 *)v13;
        StringCchCopyW(v58, 0x105u, v37);
        v39 = -1;
        do
          ++v39;
        while ( *(_WORD *)&v38[2 * v39] );
        v40 = RegSetValueExW(hKey, L"File Name", 0, 2u, v38, 2 * v39 + 2);
        v12 = v40;
        if ( v40 > 0 )
          v12 = (unsigned __int16)v40 | 0x80070000;
        if ( v12 >= 0 )
        {
          v49 = *(_DWORD *)v51;
          v41 = RegSetValueExW(hKey, L"Behavior", 0, 4u, v51, 4u);
          v12 = v41;
          if ( v41 > 0 )
            v12 = (unsigned __int16)v41 | 0x80070000;
          if ( v12 >= 0 )
          {
            if ( v48 )
            {
              do
                ++v28;
              while ( *((_WORD *)v48 + v28) );
              v42 = RegSetValueExW(hKey, L"Wrapped CLSID", 0, 1u, (const BYTE *)v48, 2 * v28 + 2);
              v12 = v42;
              if ( v42 > 0 )
                v12 = (unsigned __int16)v42 | 0x80070000;
              if ( v12 < 0
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              {
                WPP_SF_SSD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  24,
                  (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
                  (_DWORD)v48,
                  (__int64)SubKey,
                  v12);
              }
            }
            goto LABEL_111;
          }
          v32 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          {
LABEL_111:
            v23 = (__int64)a5;
LABEL_112:
            v19 = v45;
            goto LABEL_31;
          }
          v33 = 23;
        }
        else
        {
          v32 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
            goto LABEL_111;
          v33 = 22;
        }
      }
      else
      {
        v32 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_111;
        v33 = 21;
      }
    }
    else
    {
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_111;
      v33 = 20;
    }
    WPP_SF_SD(v32[2], v33, (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids, (unsigned int)SubKey, v12);
    goto LABEL_111;
  }
  if ( v11 > 0 )
    v12 = (unsigned __int16)v11 | 0x80070000;
  v43 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
        (unsigned int)SubKey,
        v12);
      goto LABEL_131;
    }
LABEL_132:
    if ( v43 != &WPP_GLOBAL_Control && (*((_BYTE *)v43 + 28) & 0x10) != 0 )
      WPP_SF_D(v43[2], 35, &WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids, (unsigned int)v12);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180007b28  push    rbp
0x180007b2a  push    rbx
0x180007b2b  push    rsi
0x180007b2c  push    rdi
0x180007b2d  push    r12
0x180007b2f  push    r13
0x180007b31  push    r14
0x180007b33  push    r15
0x180007b35  lea     rbp, [rsp-2B8h]
0x180007b3d  sub     rsp, 3B8h
0x180007b44  mov     rax, cs:__security_cookie
0x180007b4b  xor     rax, rsp
0x180007b4e  mov     [rbp+2F0h+var_50], rax
0x180007b55  mov     rax, [rbp+2F0h+arg_20]
0x180007b5c  xor     ebx, ebx
0x180007b5e  mov     [rsp+3F0h+var_3A0], rax
0x180007b63  mov     r14, r9
0x180007b66  mov     rax, [rbp+2F0h+arg_30]
0x180007b6d  mov     rdi, r8
0x180007b70  mov     [rsp+3F0h+var_398], rax
0x180007b75  mov     r13, rdx
0x180007b78  mov     [rsp+3F0h+var_380], r8
0x180007b7d  mov     dword ptr [rbp+2F0h+var_370], ecx
0x180007b80  test    r9, r9
0x180007b83  jz      short loc_180007B92
0x180007b85  lea     eax, [rbx+2Ah]
0x180007b88  lea     r15d, [rbx+1]
0x180007b8c  cmp     ax, [r9]
0x180007b90  jz      short loc_180007B95
0x180007b92  mov     r15d, ebx
0x180007b95  xor     edx, edx; Val
0x180007b97  mov     [rsp+3F0h+var_378], ebx
0x180007b9b  mov     r8d, 20Ah; Size
0x180007ba1  lea     rcx, [rbp+2F0h+var_260]; void *
0x180007ba8  call    memset_0
0x180007bad  mov     esi, 69h ; 'i'
0x180007bb2  mov     [rbp+2F0h+SubKey], bx
0x180007bb6  mov     edx, esi; unsigned __int64
0x180007bb8  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180007bbf  lea     rcx, [rbp+2F0h+SubKey]; unsigned __int16 *
0x180007bc3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007bc8  lea     r8, aComponents; "Components"
0x180007bcf  mov     edx, esi; unsigned __int64
0x180007bd1  lea     rcx, [rbp+2F0h+SubKey]; unsigned __int16 *
0x180007bd5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007bda  lea     r8, asc_180016A5C; "\\"
0x180007be1  mov     edx, esi; unsigned __int64
0x180007be3  lea     rcx, [rbp+2F0h+SubKey]; unsigned __int16 *
0x180007be7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007bec  mov     r8, r13; unsigned __int16 *
0x180007bef  lea     rcx, [rbp+2F0h+SubKey]; unsigned __int16 *
0x180007bf3  mov     edx, esi; unsigned __int64
0x180007bf5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007bfa  lea     rax, [rbp+2F0h+dwDisposition]
0x180007bfe  mov     [rsp+3F0h+hKey], rbx
0x180007c03  mov     [rsp+3F0h+lpdwDisposition], rax; lpdwDisposition
0x180007c08  lea     rdx, [rbp+2F0h+SubKey]; lpSubKey
0x180007c0c  lea     rax, [rsp+3F0h+hKey]
0x180007c11  mov     [rbp+2F0h+dwDisposition], ebx
0x180007c14  mov     [rsp+3F0h+phkResult], rax; phkResult
0x180007c19  xor     r9d, r9d; lpClass
0x180007c1c  mov     [rsp+3F0h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180007c21  xor     r8d, r8d; Reserved
0x180007c24  mov     [rsp+3F0h+samDesired], 2001Fh; samDesired
0x180007c2c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007c33  mov     [rsp+3F0h+dwOptions], ebx; dwOptions
0x180007c37  call    cs:__imp_RegCreateKeyExW
0x180007c3d  xor     r11d, r11d
0x180007c40  mov     ebx, eax
0x180007c42  test    eax, eax
0x180007c44  jnz     loc_180008513
0x180007c4a  mov     ecx, [rbp+2F0h+arg_28]
0x180007c50  mov     edx, 0BACEh
0x180007c55  mov     [rbp+2F0h+var_364], r11d
0x180007c59  mov     r12d, r11d
0x180007c5c  mov     [rsp+3F0h+lpData], r11
0x180007c61  cmp     dx, cx
0x180007c64  jnz     short loc_180007C6D
0x180007c66  mov     ecx, 10000h
0x180007c6b  jmp     short loc_180007C7E
0x180007c6d  mov     eax, ecx
0x180007c6f  movzx   ecx, cx
0x180007c72  shr     eax, 10h
0x180007c75  cmp     dx, ax
0x180007c78  jnz     short loc_180007C7E
0x180007c7a  bts     ecx, 10h
0x180007c7e  cmp     [rbp+2F0h+dwDisposition], 1
0x180007c82  lea     rax, asc_180016B4C; "*"
0x180007c89  mov     dword ptr [rbp+2F0h+var_368], ecx
0x180007c8c  mov     esi, 4
0x180007c91  jz      loc_18000803E
0x180007c97  mov     rcx, [rsp+3F0h+hKey]; hKey
0x180007c9c  lea     rax, [rbp+2F0h+cbData]
0x180007ca0  mov     qword ptr [rsp+3F0h+samDesired], rax; lpcbData
0x180007ca5  lea     rdx, ValueName; "Class Type"
0x180007cac  lea     rax, [rbp+2F0h+Data]
0x180007cb0  mov     dword ptr [rbp+2F0h+Data], r11d
0x180007cb4  xor     r9d, r9d; lpType
0x180007cb7  mov     qword ptr [rsp+3F0h+dwOptions], rax; lpData
0x180007cbc  xor     r8d, r8d; lpReserved
0x180007cbf  mov     [rbp+2F0h+cbData], esi
0x180007cc2  call    cs:__imp_RegQueryValueExW
0x180007cc8  xor     r11d, r11d
0x180007ccb  test    eax, eax
0x180007ccd  jnz     loc_180008037
0x180007cd3  cmp     dword ptr [rbp+2F0h+Data], r11d
0x180007cd7  jz      loc_180008037
0x180007cdd  xorps   xmm0, xmm0
0x180007ce0  lea     rdx, [rbp+2F0h+pclsid]; pclsid
0x180007ce4  mov     rcx, r13; lpsz
0x180007ce7  movups  xmmword ptr [rbp+2F0h+pclsid.Data1], xmm0
0x180007ceb  call    cs:__imp_CLSIDFromString
0x180007cf1  mov     ebx, eax
0x180007cf3  test    eax, eax
0x180007cf5  js      loc_180007FF5
0x180007cfb  lea     r8, [rsp+3F0h+var_378]; unsigned int *
0x180007d00  lea     rcx, [rbp+2F0h+pclsid]; rguid
0x180007d04  call    ?HrGetComponentInfo@@YAJPEBU_GUID@@PEAW4tagXW_COMPONENT_TYPE@@PEAK@Z; HrGetComponentInfo(_GUID const *,tagXW_COMPONENT_TYPE *,ulong *)
0x180007d09  lea     rdi, WPP_GLOBAL_Control
0x180007d10  test    eax, eax
0x180007d12  jns     short loc_180007D40
0x180007d14  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d1b  cmp     rcx, rdi
0x180007d1e  jz      short loc_180007D47
0x180007d20  test    [rcx+1Ch], sil
0x180007d24  jz      short loc_180007D47
0x180007d26  mov     rcx, [rcx+10h]
0x180007d2a  lea     edx, [rsi+16h]
0x180007d2d  mov     r9, r13
0x180007d30  mov     [rsp+3F0h+dwOptions], eax
0x180007d34  lea     r8, WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids
0x180007d3b  call    WPP_SF_SD
0x180007d40  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d47  test    r15d, r15d
0x180007d4a  jnz     loc_180007FAB
0x180007d50  lea     rcx, [rbp+2F0h+pclsid]; struct _GUID *
0x180007d54  call    ?IsComponentModuleNameResolved@@YAHPEBU_GUID@@@Z; IsComponentModuleNameResolved(_GUID const *)
0x180007d59  test    eax, eax
0x180007d5b  jnz     loc_180007F29
0x180007d61  mov     r15, [rsp+3F0h+var_398]
0x180007d66  lea     r8, [rsp+3F0h+lpData]; unsigned __int16 **
0x180007d6b  mov     r9, r15; void *
0x180007d6e  mov     rdx, r14; lpSrc
0x180007d71  mov     rcx, r13; unsigned __int16 *
0x180007d74  call    ?HrEnsureCOMRegistration@@YAJQEAG0QEAPEAGQEAX@Z; HrEnsureCOMRegistration(ushort * const,ushort * const,ushort * * const,void * const)
0x180007d79  xor     r11d, r11d
0x180007d7c  mov     ebx, eax
0x180007d7e  test    eax, eax
0x180007d80  js      loc_180007EEC
0x180007d86  mov     r12, [rsp+3F0h+lpData]
0x180007d8b  lea     rcx, [rbp+2F0h+var_260]; unsigned __int16 *
0x180007d92  mov     eax, r11d
0x180007d95  mov     [rbp+2F0h+var_260], r11w
0x180007d9d  test    ebx, ebx
0x180007d9f  mov     r8, r12; unsigned __int16 *
0x180007da2  mov     edx, 105h; unsigned __int64
0x180007da7  setz    al
0x180007daa  mov     [rbp+2F0h+var_364], eax
0x180007dad  mov     eax, dword ptr [rbp+2F0h+var_368]
0x180007db0  mov     [rsp+3F0h+var_378], eax
0x180007db4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007db9  or      r15, 0FFFFFFFFFFFFFFFFh
0x180007dbd  inc     r15
0x180007dc0  cmp     [r12+r15*2], r11w
0x180007dc5  jnz     short loc_180007DBD
0x180007dc7  mov     rcx, [rsp+3F0h+hKey]; hKey
0x180007dcc  lea     eax, ds:2[r15*2]
0x180007dd4  mov     [rsp+3F0h+samDesired], eax; cbData
0x180007dd8  lea     rdx, aFileName; "File Name"
0x180007ddf  mov     r9d, 2; dwType
0x180007de5  mov     qword ptr [rsp+3F0h+dwOptions], r12; lpData
0x180007dea  xor     r8d, r8d; Reserved
0x180007ded  call    cs:__imp_RegSetValueExW
0x180007df3  mov     ebx, eax
0x180007df5  test    eax, eax
0x180007df7  jle     short loc_180007E04
0x180007df9  movzx   ebx, bx
0x180007dfc  or      ebx, 80070000h
0x180007e02  test    ebx, ebx
0x180007e04  jns     short loc_180007E3D
0x180007e06  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e0d  cmp     rcx, rdi
0x180007e10  jz      short loc_180007E3D
0x180007e12  test    [rcx+1Ch], sil
0x180007e16  jz      short loc_180007E3D
0x180007e18  mov     rcx, [rcx+10h]
0x180007e1c  lea     rax, [rbp+2F0h+SubKey]
0x180007e20  mov     edx, 1Bh
0x180007e25  mov     [rsp+3F0h+samDesired], ebx
0x180007e29  mov     r9, r12
0x180007e2c  mov     qword ptr [rsp+3F0h+dwOptions], rax
0x180007e31  lea     r8, WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids
0x180007e38  call    WPP_SF_SSD
0x180007e3d  mov     r15, [rsp+3F0h+var_398]
0x180007e42  mov     rsi, [rsp+3F0h+var_3A0]
0x180007e47  mov     rcx, [rsp+3F0h+hKey]; hKey
0x180007e4c  call    cs:__imp_RegCloseKey
0x180007e52  xor     r14d, r14d
0x180007e55  test    ebx, ebx
0x180007e57  jns     loc_180008410
0x180007e5d  xor     esi, esi
0x180007e5f  cmp     [rbp+2F0h+var_364], esi
0x180007e62  jz      short loc_180007E6E
0x180007e64  xor     edx, edx; int
0x180007e66  mov     rcx, r12; lpSrc
0x180007e69  call    ?HrRegisterOrUnregisterWithCOM@@YAJQEAGH@Z; HrRegisterOrUnregisterWithCOM(ushort * const,int)
0x180007e6e  mov     r11d, 69h ; 'i'
0x180007e74  mov     [rbp+2F0h+SubKey], si
0x180007e78  mov     edx, r11d; unsigned __int64
0x180007e7b  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180007e82  lea     rcx, [rbp+2F0h+SubKey]; unsigned __int16 *
0x180007e86  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007e8b  lea     r8, aComponents; "Components"
0x180007e92  mov     edx, r11d; unsigned __int64
0x180007e95  lea     rcx, [rbp+2F0h+SubKey]; unsigned __int16 *
0x180007e99  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007e9e  lea     rax, [rsp+3F0h+var_380]
0x180007ea3  mov     [rsp+3F0h+var_380], rsi
0x180007ea8  mov     r9d, 20006h; samDesired
0x180007eae  mov     qword ptr [rsp+3F0h+dwOptions], rax; phkResult
0x180007eb3  xor     r8d, r8d; ulOptions
0x180007eb6  lea     rdx, [rbp+2F0h+SubKey]; lpSubKey
0x180007eba  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007ec1  call    cs:__imp_RegOpenKeyExW
0x180007ec7  test    eax, eax
0x180007ec9  jnz     loc_1800084F5
0x180007ecf  mov     rcx, [rsp+3F0h+var_380]; HKEY
0x180007ed4  mov     rdx, r13; unsigned __int16 *
0x180007ed7  call    ?HrRegDeleteSubKeyTree@@YAJPEAUHKEY__@@PEAG@Z; HrRegDeleteSubKeyTree(HKEY__ *,ushort *)
0x180007edc  mov     rcx, [rsp+3F0h+var_380]; hKey
0x180007ee1  call    cs:__imp_RegCloseKey
0x180007ee7  jmp     loc_1800084F5
0x180007eec  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ef3  cmp     rcx, rdi
0x180007ef6  jz      short loc_180007F1F
0x180007ef8  test    byte ptr [rcx+1Ch], 10h
0x180007efc  jz      short loc_180007F1F
0x180007efe  mov     edx, 1Ch
0x180007f03  mov     rcx, [rcx+10h]
0x180007f07  lea     r8, WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids
0x180007f0e  mov     [rsp+3F0h+samDesired], ebx
0x180007f12  mov     r9, r13
0x180007f15  mov     qword ptr [rsp+3F0h+dwOptions], r14
0x180007f1a  call    WPP_SF_SSD
0x180007f1f  mov     r12, [rsp+3F0h+lpData]
0x180007f24  jmp     loc_180007E42
0x180007f29  mov     eax, 1
0x180007f2e  mov     ebx, eax
0x180007f30  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f37  cmp     rcx, rdi
0x180007f3a  jz      short loc_180007F5D
0x180007f3c  test    byte ptr [rcx+1Ch], 10h
0x180007f40  jz      short loc_180007F5D
0x180007f42  mov     rcx, [rcx+10h]
0x180007f46  lea     edx, [rax+1Ch]
0x180007f49  lea     r9, [rbp+2F0h+SubKey]
0x180007f4d  mov     [rsp+3F0h+dwOptions], eax
0x180007f51  lea     r8, WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids
0x180007f58  call    WPP_SF_SD
0x180007f5d  mov     r15, [rsp+3F0h+var_398]
0x180007f62  test    r15, r15
0x180007f65  jz      loc_180007E42
0x180007f6b  mov     r9, r15; void *
0x180007f6e  lea     r8, [rsp+3F0h+lpData]; unsigned __int16 **
0x180007f73  mov     rdx, r14; lpSrc
0x180007f76  mov     rcx, r13; unsigned __int16 *
0x180007f79  call    ?HrEnsureCOMRegistration@@YAJQEAG0QEAPEAGQEAX@Z; HrEnsureCOMRegistration(ushort * const,ushort * const,ushort * * const,void * const)
0x180007f7e  xor     r11d, r11d
0x180007f81  test    eax, eax
0x180007f83  js      short loc_180007F1F
0x180007f85  mov     r12, [rsp+3F0h+lpData]
0x180007f8a  lea     rcx, [rbp+2F0h+var_260]; unsigned __int16 *
0x180007f91  mov     r8, r12; unsigned __int16 *
0x180007f94  mov     [rbp+2F0h+var_260], r11w
0x180007f9c  mov     edx, 105h; unsigned __int64
0x180007fa1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007fa6  jmp     loc_180007E42
0x180007fab  mov     eax, 1
0x180007fb0  mov     ebx, eax
0x180007fb2  cmp     rcx, rdi
0x180007fb5  jz      short loc_180007FD8
0x180007fb7  test    byte ptr [rcx+1Ch], 10h
0x180007fbb  jz      short loc_180007FD8
0x180007fbd  mov     rcx, [rcx+10h]
0x180007fc1  lea     edx, [rax+1Dh]
0x180007fc4  lea     r9, [rbp+2F0h+SubKey]
0x180007fc8  mov     [rsp+3F0h+dwOptions], eax
0x180007fcc  lea     r8, WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids
0x180007fd3  call    WPP_SF_SD
0x180007fd8  mov     r15, [rsp+3F0h+var_398]
0x180007fdd  xor     eax, eax
0x180007fdf  mov     rsi, [rsp+3F0h+var_3A0]
0x180007fe4  test    r15, r15
0x180007fe7  jz      loc_180007E47
0x180007fed  mov     r15d, eax
0x180007ff0  jmp     loc_180007E47
0x180007ff5  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ffc  lea     rdi, WPP_GLOBAL_Control
0x180008003  cmp     rcx, rdi
0x180008006  jz      loc_180007E3D
  ... truncated ...
```
