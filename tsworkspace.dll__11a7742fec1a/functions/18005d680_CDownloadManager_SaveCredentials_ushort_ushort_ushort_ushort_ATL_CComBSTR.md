# CDownloadManager::SaveCredentials(ushort *,ushort *,ushort *,ushort *,ATL::CComBSTR)

- ea: `0x18005d680`
- end: `0x18005e16b`
- name: `?SaveCredentials@CDownloadManager@@UEAAJPEAG000VCComBSTR@ATL@@@Z`
- size: `2795`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800044bf`
- `0x180005374`
- `0x18000b1d8`
- `0x18000ec54`
- `0x18000ec94`
- `0x18000ece0`
- `0x18001b780`
- `0x180020bf0`
- `0x18003ce1c`
- `0x18005a3d0`
- `0x18005d680`
- `0x18005e660`
- `0x180088798`
- `0x18009a520`
- `0x1800a3010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18005dba7`
- `ole32!CoCreateInstance` at `0x18005dba7`
- `ADVAPI32!CredWriteW` at `0x18005df11`
- `ADVAPI32!CredWriteW` at `0x18005e038`
- `ADVAPI32!CredWriteW` at `0x18005df11`
- `ADVAPI32!CredWriteW` at `0x18005e038`
- `ADVAPI32!CredGetSessionTypes` at `0x18005dcdf`
- `ADVAPI32!CredGetSessionTypes` at `0x18005dcdf`
- `OLEAUT32!__imp_SysAllocString` at `0x18005d979`
- `OLEAUT32!__imp_SysAllocString` at `0x18005d9dd`
- `OLEAUT32!__imp_SysAllocString` at `0x18005da41`
- `OLEAUT32!__imp_SysAllocString` at `0x18005daa1`
- `OLEAUT32!__imp_SysAllocString` at `0x18005db2d`
- `OLEAUT32!__imp_SysAllocString` at `0x18005d979`
- `OLEAUT32!__imp_SysAllocString` at `0x18005d9dd`
- `OLEAUT32!__imp_SysAllocString` at `0x18005da41`
- `OLEAUT32!__imp_SysAllocString` at `0x18005daa1`
- `OLEAUT32!__imp_SysAllocString` at `0x18005db2d`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d867`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d879`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d887`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d89d`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e140`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d867`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d879`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d887`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d89d`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e140`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005dd08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005dd38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005df22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e046`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005dd08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005dd38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005df22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e046`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005d845`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005d855`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005d845`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005d855`

## string_xrefs

- `0x18005dbe8`: `CoCreateInstance failed`
- `0x18005df59`: `CredWrite`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDownloadManager::SaveCredentials(
        __int64 a1,
        const OLECHAR *a2,
        const OLECHAR *a3,
        const OLECHAR *a4,
        const char *a5,
        BSTR *a6)
{
  PVOID *v10; // rax
  const char *v11; // r8
  const char *v12; // rcx
  int SecurePasswordString; // ebx
  _BYTE *v14; // r13
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v16; // edx
  const char *v17; // rcx
  OLECHAR *v18; // rdi
  BSTR *v19; // r14
  __int64 v20; // rdx
  _BYTE *v21; // rax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  BSTR v26; // rdi
  unsigned int v27; // eax
  unsigned int v28; // eax
  DWORD LastError; // ebx
  unsigned int v30; // eax
  signed int v31; // eax
  DWORD v32; // edi
  PVOID *v33; // rbx
  unsigned int v34; // eax
  unsigned int v35; // eax
  unsigned int v36; // eax
  unsigned int v37; // eax
  signed int v38; // eax
  unsigned int v39; // eax
  int v40; // edx
  const char *v41; // rcx
  unsigned int v42; // eax
  signed int v43; // eax
  unsigned int v44; // eax
  unsigned int v45; // eax
  __int64 v47; // [rsp+28h] [rbp-D8h]
  BSTR v48; // [rsp+30h] [rbp-D0h]
  BSTR v49; // [rsp+60h] [rbp-A0h]
  unsigned int v50[2]; // [rsp+70h] [rbp-90h] BYREF
  HLOCAL v51; // [rsp+78h] [rbp-88h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp-80h]
  BSTR v53; // [rsp+88h] [rbp-78h]
  BSTR v54; // [rsp+90h] [rbp-70h]
  LPVOID ppv; // [rsp+98h] [rbp-68h] BYREF
  HLOCAL hMem; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int64 v57[3]; // [rsp+A8h] [rbp-58h] BYREF
  _CREDENTIALW Credential; // [rsp+C0h] [rbp-40h] BYREF
  DWORD MaximumPersist[8]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v60[264]; // [rsp+130h] [rbp+30h] BYREF

  v57[1] = -2;
  v57[2] = (unsigned __int64)a6;
  memset_0(&Credential, 0, sizeof(Credential));
  hMem = 0;
  v50[0] = 0;
  v57[0] = 0;
  v51 = 0;
  ppv = 0;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = a5;
    if ( !a5 )
      v11 = L"NULL";
    v12 = (const char *)a4;
    if ( !a4 )
      v12 = L"NULL";
    WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v12, (__int64)v11);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 && *a2 && a4 && *a4 )
  {
    v49 = 0;
    bstrString = 0;
    v53 = 0;
    v54 = 0;
    SecurePasswordString = CDownloadManager::GetSecurePasswordString(
                             (CDownloadManager *)a1,
                             (unsigned __int16 **)&hMem,
                             v50);
    v14 = hMem;
    if ( SecurePasswordString < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_19;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v16 = 35;
      v17 = "GetSecurePasswordString failed";
LABEL_18:
      LODWORD(v47) = SecurePasswordString;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v16,
        (unsigned int)&WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v17,
        v47);
LABEL_19:
      v18 = v49;
LABEL_20:
      v19 = a6;
LABEL_21:
      if ( v14 )
      {
        v20 = v50[0];
        v21 = v14;
        if ( v50[0] )
        {
          do
          {
            *v21++ = 0;
            --v20;
          }
          while ( v20 );
        }
        LocalFree(v14);
      }
      if ( v51 )
        LocalFree(v51);
      if ( bstrString )
        SysFreeString(bstrString);
      if ( v53 )
        SysFreeString(v53);
      if ( v18 )
        SysFreeString(v18);
      if ( v54 )
        SysFreeString(v54);
      goto LABEL_157;
    }
    if ( !hMem || !v50[0] )
    {
      SecurePasswordString = -2147024809;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v44 = RdpWppGetCurrentThreadActivityIdPrefix();
        LODWORD(v47) = -2147024809;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          36,
          (unsigned int)&WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
          v44,
          (__int64)"Null or empty Password failed",
          v47);
      }
      goto LABEL_19;
    }
    SecurePasswordString = StringCbLengthW((const unsigned __int16 *)hMem, v50[0], v57);
    if ( SecurePasswordString < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_19;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v16 = 37;
      v17 = "String length of password";
      goto LABEL_18;
    }
    if ( *(_DWORD *)(a1 + 2072) )
    {
      SecurePasswordString = TsCryptEncryptAndEncodeString(v14, &v51);
      if ( SecurePasswordString < 0 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_19;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v16 = 38;
        v17 = "TsCryptEncryptAndEncodeString failed!";
        goto LABEL_18;
      }
      v54 = SysAllocString(a4);
      if ( !v54 )
      {
        SecurePasswordString = -2147024882;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v22 = RdpWppGetCurrentThreadActivityIdPrefix();
          LODWORD(v47) = -2147024882;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            39,
            (unsigned int)&WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
            v22,
            (__int64)"redirector Alloc failed",
            v47);
        }
        goto LABEL_19;
      }
      v53 = SysAllocString((const OLECHAR *)v51);
      if ( !v53 )
      {
        SecurePasswordString = -2147024882;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v23 = RdpWppGetCurrentThreadActivityIdPrefix();
          LODWORD(v47) = -2147024882;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            40,
            (unsigned int)&WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
            v23,
            (__int64)"pwd Alloc failed",
            v47);
        }
        goto LABEL_19;
      }
      bstrString = SysAllocString((const OLECHAR *)(a1 + 432));
      if ( !bstrString )
      {
        SecurePasswordString = -2147024882;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v24 = RdpWppGetCurrentThreadActivityIdPrefix();
          LODWORD(v47) = -2147024882;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            41,
            (unsigned int)&WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
            v24,
            (__int64)"username alloc failed",
            v47);
        }
        goto LABEL_19;
      }
      v18 = SysAllocString(a2);
      v49 = v18;
      if ( !v18 )
      {
        SecurePasswordString = -2147024882;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v25 = RdpWppGetCurrentThreadActivityIdPrefix();
          LODWORD(v47) = -2147024882;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            42,
            (unsigned int)&WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
            v25,
            (__int64)"workspaceID alloc failed",
            v47);
        }
        goto LABEL_20;
      }
      if ( a3 && *a3 )
      {
        v26 = SysAllocString(a3);
        if ( !v26 )
        {
          SecurePasswordString = -2147024882;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v27 = RdpWppGetCurrentThreadActivityIdPrefix();
            LODWORD(v47) = -2147024882;
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              43,
              (unsigned int)&WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
              v27,
              (__int64)"AppContainer alloc failed",
              v47);
          }
          goto LABEL_19;
        }
      }
      else
      {
        v26 = 0;
      }
      SecurePasswordString = CoCreateInstance(
                               &GUID_4f1dfca6_3aad_48e1_8406_4bc21a501d7c,
                               0,
                               4u,
                               &GUID_531e6512_2cbf_4bd2_80a5_d90a71636a9a,
                               &ppv);
      if ( SecurePasswordString < 0 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_19;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v16 = 44;
        v17 = "CoCreateInstance failed";
        goto LABEL_18;
      }
      v19 = a6;
      v48 = v26;
      v18 = v49;
      SecurePasswordString = (*(__int64 (__fastcall **)(LPVOID, BSTR, _QWORD, BSTR, BSTR, BSTR, BSTR, BSTR, _DWORD, int))(*(_QWORD *)ppv + 112LL))(
                               ppv,
                               v49,
                               0,
                               v54,
                               bstrString,
                               v53,
                               v48,
                               *a6,
                               *(_DWORD *)(a1 + 2072),
                               6);
      if ( SecurePasswordString < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v28 = RdpWppGetCurrentThreadActivityIdPrefix();
          LODWORD(v47) = SecurePasswordString;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            45,
            (unsigned int)&WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
            v28,
            (__int64)"m_pWorkspaceScriptable->StartWorkspaceEx failed",
            v47);
        }
        goto LABEL_21;
      }
    }
    else
    {
      v18 = 0;
      v19 = a6;
    }
    if ( !*(_DWORD *)(a1 + 1980) )
      goto LABEL_21;
    memset(MaximumPersist, 0, 28);
    if ( !CredGetSessionTypes(7u, MaximumPersist) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        v30 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          46,
          &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
          v30,
          LastError);
      }
      v31 = GetLastError();
      SecurePasswordString = v31;
      if ( v31 > 0 )
        SecurePasswordString = (unsigned __int16)v31 | 0x80070000;
LABEL_95:
      v18 = v49;
      goto LABEL_21;
    }
    v32 = MaximumPersist[2];
    if ( MaximumPersist[2] > 2 )
    {
      v32 = 2;
      MaximumPersist[2] = 2;
    }
    if ( v32 == 1 )
    {
      v33 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      {
LABEL_104:
        memset_0(&Credential, 0, sizeof(Credential));
        Credential.Type = 2;
        Credential.Persist = v32;
        Credential.TargetName = v60;
        Credential.CredentialBlob = v14;
        Credential.CredentialBlobSize = v57[0];
        Credential.UserName = (LPWSTR)(a1 + 432);
        if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 1) != 0 && *((_BYTE *)v33 + 25) >= 4u )
        {
          v35 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            49,
            (unsigned int)&WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
            v35,
            (__int64)a4);
        }
        SecurePasswordString = StringCbPrintfW(v60, 0x20Au, L"TERMSRV/%s", a4);
        if ( SecurePasswordString < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v36 = RdpWppGetCurrentThreadActivityIdPrefix();
            LODWORD(v47) = SecurePasswordString;
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              50,
              (unsigned int)&WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
              v36,
              (__int64)"StringCbPrintf",
              v47);
          }
          goto LABEL_95;
        }
        if ( CredWriteW(&Credential, 0) )
          goto LABEL_160;
        v38 = GetLastError();
        SecurePasswordString = v38;
        if ( v38 > 0 )
          SecurePasswordString = (unsigned __int16)v38 | 0x80070000;
        if ( SecurePasswordString >= 0 )
        {
LABEL_160:
          if ( !a5 || !*(_WORD *)a5 )
            goto LABEL_128;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            v42 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_DS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              52,
              (unsigned int)&WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
              v42,
              (__int64)a5);
          }
          SecurePasswordString = StringCbPrintfW(v60, 0x20Au, L"%s", a5);
          if ( SecurePasswordString < 0 )
          {
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_128;
            }
            v39 = RdpWppGetCurrentThreadActivityIdPrefix();
            v40 = 53;
            v41 = "StringCbPrintf";
            goto LABEL_127;
          }
          if ( CredWriteW(&Credential, 0) )
            goto LABEL_128;
          v43 = GetLastError();
          SecurePasswordString = v43;
          if ( v43 > 0 )
            SecurePasswordString = (unsigned __int16)v43 | 0x80070000;
          if ( SecurePasswordString >= 0
            || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_128;
          }
          v39 = RdpWppGetCurrentThreadActivityIdPrefix();
          v40 = 54;
        }
        else
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_128;
          }
          v39 = RdpWppGetCurrentThreadActivityIdPrefix();
          v40 = 51;
        }
        v41 = "CredWrite";
LABEL_127:
        LODWORD(v47) = SecurePasswordString;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v40,
          (unsigned int)&WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
          v39,
          (__int64)v41,
          v47);
LABEL_128:
        v18 = v49;
        goto LABEL_21;
      }
      v34 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids, v34);
      v32 = MaximumPersist[2];
    }
    else if ( !v32 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v37 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids, v37);
      }
      goto LABEL_95;
    }
    v33 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_104;
  }
  SecurePasswordString = -2147024809;
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 && *((_BYTE *)v10 + 25) >= 2u )
  {
    v45 = RdpWppGetCurrentThreadActivityIdPrefix();
    LODWORD(v47) = -2147024809;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      34,
      (unsigned int)&WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
      v45,
      (__int64)"SaveCredentials failed",
      v47);
  }
  v19 = a6;
LABEL_157:
  ATL::CComPtr<IXMLDOMSchemaCollection>::~CComPtr<IXMLDOMSchemaCollection>(&ppv);
  SysFreeString(*v19);
  return (unsigned int)SecurePasswordString;
}

```

## disassembly

```asm
0x18005d680  push    rbp
0x18005d682  push    rbx
0x18005d683  push    rsi
0x18005d684  push    rdi
0x18005d685  push    r12
0x18005d687  push    r13
0x18005d689  push    r14
0x18005d68b  push    r15
0x18005d68d  lea     rbp, [rsp-258h]
0x18005d695  sub     rsp, 358h
0x18005d69c  mov     [rbp+290h+var_2E0], 0FFFFFFFFFFFFFFFEh
0x18005d6a4  mov     rax, cs:__security_cookie
0x18005d6ab  xor     rax, rsp
0x18005d6ae  mov     [rbp+290h+var_50], rax
0x18005d6b5  mov     rsi, r9
0x18005d6b8  mov     r14, r8
0x18005d6bb  mov     rdi, rdx
0x18005d6be  mov     r15, rcx
0x18005d6c1  mov     r12, [rbp+290h+arg_20]
0x18005d6c8  mov     rax, [rbp+290h+arg_28]
0x18005d6cf  mov     [rsp+390h+var_328], rax
0x18005d6d4  mov     [rbp+290h+var_2D8], rax
0x18005d6d8  xor     edx, edx; Val
0x18005d6da  lea     r8d, [rdx+50h]; Size
0x18005d6de  lea     rcx, [rbp+290h+Credential]; void *
0x18005d6e2  call    memset_0
0x18005d6e7  xor     ebx, ebx
0x18005d6e9  mov     [rbp+290h+hMem], rbx
0x18005d6ed  mov     [rsp+390h+var_320], ebx
0x18005d6f1  mov     [rbp+290h+var_2E8], rbx
0x18005d6f5  mov     [rsp+390h+var_318], rbx
0x18005d6fa  mov     [rbp+290h+var_2F8], rbx
0x18005d6fe  lea     rcx, WPP_GLOBAL_Control
0x18005d705  mov     rax, cs:WPP_GLOBAL_Control
0x18005d70c  cmp     rax, rcx
0x18005d70f  jz      short loc_18005D772
0x18005d711  test    byte ptr [rax+1Ch], 1
0x18005d715  jz      short loc_18005D772
0x18005d717  cmp     byte ptr [rax+19h], 4
0x18005d71b  jb      short loc_18005D772
0x18005d71d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005d722  lea     rdx, aNull_1; "NULL"
0x18005d729  mov     r8, r12
0x18005d72c  test    r12, r12
0x18005d72f  cmovz   r8, rdx
0x18005d733  mov     rcx, rsi
0x18005d736  test    rsi, rsi
0x18005d739  cmovz   rcx, rdx
0x18005d73d  lea     edx, [rbx+21h]
0x18005d740  mov     [rsp+390h+var_368], r8; __int64
0x18005d745  mov     [rsp+390h+ppv], rcx; __int64
0x18005d74a  mov     r9d, eax
0x18005d74d  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x18005d754  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d75b  mov     rcx, [rcx+10h]; LoggerHandle
0x18005d75f  call    WPP_SF_DSS
0x18005d764  mov     rax, cs:WPP_GLOBAL_Control
0x18005d76b  lea     rcx, WPP_GLOBAL_Control
0x18005d772  test    rdi, rdi
0x18005d775  jz      loc_18005E0E0
0x18005d77b  cmp     [rdi], bx
0x18005d77e  jz      loc_18005E0E0
0x18005d784  test    rsi, rsi
0x18005d787  jz      loc_18005E0E0
0x18005d78d  cmp     [rsi], bx
0x18005d790  jz      loc_18005E0E0
0x18005d796  mov     [rsp+390h+var_330], rbx
0x18005d79b  mov     [rbp+290h+bstrString], rbx
0x18005d79f  mov     [rbp+290h+var_308], rbx
0x18005d7a3  mov     [rbp+290h+var_300], rbx
0x18005d7a7  lea     r8, [rsp+390h+var_320]; unsigned int *
0x18005d7ac  lea     rdx, [rbp+290h+hMem]; unsigned __int16 **
0x18005d7b0  mov     rcx, r15; this
0x18005d7b3  call    ?GetSecurePasswordString@CDownloadManager@@IEAAJPEAPEAGPEAK@Z; CDownloadManager::GetSecurePasswordString(ushort * *,ulong *)
0x18005d7b8  mov     ebx, eax
0x18005d7ba  mov     r13, [rbp+290h+hMem]
0x18005d7be  test    eax, eax
0x18005d7c0  jns     loc_18005D8A8
0x18005d7c6  mov     rax, cs:WPP_GLOBAL_Control
0x18005d7cd  lea     rdx, WPP_GLOBAL_Control
0x18005d7d4  cmp     rax, rdx
0x18005d7d7  jz      short loc_18005D819
0x18005d7d9  test    byte ptr [rax+1Ch], 8
0x18005d7dd  jz      short loc_18005D819
0x18005d7df  cmp     byte ptr [rax+19h], 2
0x18005d7e3  jb      short loc_18005D819
0x18005d7e5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005d7ea  mov     edx, 23h ; '#'
0x18005d7ef  lea     rcx, aGetsecurepassw; "GetSecurePasswordString failed"
0x18005d7f6  mov     dword ptr [rsp+390h+var_368], ebx
0x18005d7fa  mov     [rsp+390h+ppv], rcx
0x18005d7ff  mov     r9d, eax
0x18005d802  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x18005d809  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d810  mov     rcx, [rcx+10h]
0x18005d814  call    WPP_SF_DsD
0x18005d819  mov     rdi, [rsp+390h+var_330]
0x18005d81e  mov     r14, [rsp+390h+var_328]
0x18005d823  xor     esi, esi
0x18005d825  test    r13, r13
0x18005d828  jz      short loc_18005D84B
0x18005d82a  mov     edx, [rsp+390h+var_320]
0x18005d82e  mov     rax, r13
0x18005d831  test    rdx, rdx
0x18005d834  jz      short loc_18005D842
0x18005d836  mov     [rax], sil
0x18005d839  inc     rax
0x18005d83c  sub     rdx, 1
0x18005d840  jnz     short loc_18005D836
0x18005d842  mov     rcx, r13; hMem
0x18005d845  call    cs:__imp_LocalFree
0x18005d84b  mov     rcx, [rsp+390h+var_318]; hMem
0x18005d850  test    rcx, rcx
0x18005d853  jz      short loc_18005D85B
0x18005d855  call    cs:__imp_LocalFree
0x18005d85b  mov     rax, [rbp+290h+bstrString]
0x18005d85f  test    rax, rax
0x18005d862  jz      short loc_18005D86D
0x18005d864  mov     rcx, rax; bstrString
0x18005d867  call    cs:__imp_SysFreeString
0x18005d86d  mov     rax, [rbp+290h+var_308]
0x18005d871  test    rax, rax
0x18005d874  jz      short loc_18005D87F
0x18005d876  mov     rcx, rax; bstrString
0x18005d879  call    cs:__imp_SysFreeString
0x18005d87f  test    rdi, rdi
0x18005d882  jz      short loc_18005D88D
0x18005d884  mov     rcx, rdi; bstrString
0x18005d887  call    cs:__imp_SysFreeString
0x18005d88d  mov     rax, [rbp+290h+var_300]
0x18005d891  test    rax, rax
0x18005d894  jz      loc_18005E133
0x18005d89a  mov     rcx, rax; bstrString
0x18005d89d  call    cs:__imp_SysFreeString
0x18005d8a3  jmp     loc_18005E133
0x18005d8a8  test    r13, r13
0x18005d8ab  jz      loc_18005E092
0x18005d8b1  cmp     [rsp+390h+var_320], 1
0x18005d8b6  jb      loc_18005E092
0x18005d8bc  mov     edx, [rsp+390h+var_320]; unsigned __int64
0x18005d8c0  lea     r8, [rbp+290h+var_2E8]; unsigned __int64 *
0x18005d8c4  mov     rcx, r13; unsigned __int16 *
0x18005d8c7  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18005d8cc  mov     ebx, eax
0x18005d8ce  xor     eax, eax
0x18005d8d0  test    ebx, ebx
0x18005d8d2  jns     short loc_18005D915
0x18005d8d4  mov     rax, cs:WPP_GLOBAL_Control
0x18005d8db  lea     rdx, WPP_GLOBAL_Control
0x18005d8e2  cmp     rax, rdx
0x18005d8e5  jz      loc_18005D819
0x18005d8eb  test    byte ptr [rax+1Ch], 8
0x18005d8ef  jz      loc_18005D819
0x18005d8f5  cmp     byte ptr [rax+19h], 2
0x18005d8f9  jb      loc_18005D819
0x18005d8ff  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005d904  mov     edx, 25h ; '%'
0x18005d909  lea     rcx, aStringLengthOf; "String length of password"
0x18005d910  jmp     loc_18005D7F6
0x18005d915  cmp     [r15+818h], eax
0x18005d91c  jbe     loc_18005DCB6
0x18005d922  lea     rdx, [rsp+390h+var_318]
0x18005d927  mov     rcx, r13
0x18005d92a  call    TsCryptEncryptAndEncodeString
0x18005d92f  mov     ebx, eax
0x18005d931  test    eax, eax
0x18005d933  jns     short loc_18005D976
0x18005d935  mov     rax, cs:WPP_GLOBAL_Control
0x18005d93c  lea     rdx, WPP_GLOBAL_Control
0x18005d943  cmp     rax, rdx
0x18005d946  jz      loc_18005D819
0x18005d94c  test    byte ptr [rax+1Ch], 8
0x18005d950  jz      loc_18005D819
0x18005d956  cmp     byte ptr [rax+19h], 2
0x18005d95a  jb      loc_18005D819
0x18005d960  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005d965  mov     edx, 26h ; '&'
0x18005d96a  lea     rcx, aTscryptencrypt; "TsCryptEncryptAndEncodeString failed!"
0x18005d971  jmp     loc_18005D7F6
0x18005d976  mov     rcx, rsi; psz
0x18005d979  call    cs:__imp_SysAllocString
0x18005d97f  mov     [rbp+290h+var_300], rax
0x18005d983  xor     ebx, ebx
0x18005d985  test    rax, rax
0x18005d988  jnz     short loc_18005D9D8
0x18005d98a  mov     ebx, 8007000Eh
0x18005d98f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d996  lea     rdx, WPP_GLOBAL_Control
0x18005d99d  cmp     rcx, rdx
0x18005d9a0  jz      loc_18005D819
0x18005d9a6  test    byte ptr [rcx+1Ch], 8
0x18005d9aa  jz      loc_18005D819
0x18005d9b0  cmp     byte ptr [rcx+19h], 2
0x18005d9b4  jb      loc_18005D819
0x18005d9ba  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005d9bf  mov     edx, 27h ; '''
0x18005d9c4  mov     dword ptr [rsp+390h+var_368], 8007000Eh
0x18005d9cc  lea     rcx, aRedirectorAllo; "redirector Alloc failed"
0x18005d9d3  jmp     loc_18005D7FA
0x18005d9d8  mov     rcx, [rsp+390h+var_318]; psz
0x18005d9dd  call    cs:__imp_SysAllocString
0x18005d9e3  mov     [rbp+290h+var_308], rax
0x18005d9e7  test    rax, rax
0x18005d9ea  jnz     short loc_18005DA3A
0x18005d9ec  mov     ebx, 8007000Eh
0x18005d9f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d9f8  lea     rdx, WPP_GLOBAL_Control
0x18005d9ff  cmp     rcx, rdx
0x18005da02  jz      loc_18005D819
0x18005da08  test    byte ptr [rcx+1Ch], 8
0x18005da0c  jz      loc_18005D819
0x18005da12  cmp     byte ptr [rcx+19h], 2
0x18005da16  jb      loc_18005D819
0x18005da1c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005da21  mov     edx, 28h ; '('
0x18005da26  mov     dword ptr [rsp+390h+var_368], 8007000Eh
0x18005da2e  lea     rcx, aPwdAllocFailed; "pwd Alloc failed"
0x18005da35  jmp     loc_18005D7FA
0x18005da3a  lea     rcx, [r15+1B0h]; psz
0x18005da41  call    cs:__imp_SysAllocString
0x18005da47  mov     [rbp+290h+bstrString], rax
0x18005da4b  test    rax, rax
0x18005da4e  jnz     short loc_18005DA9E
0x18005da50  mov     ebx, 8007000Eh
0x18005da55  mov     rcx, cs:WPP_GLOBAL_Control
0x18005da5c  lea     rdx, WPP_GLOBAL_Control
0x18005da63  cmp     rcx, rdx
0x18005da66  jz      loc_18005D819
0x18005da6c  test    byte ptr [rcx+1Ch], 8
0x18005da70  jz      loc_18005D819
0x18005da76  cmp     byte ptr [rcx+19h], 2
0x18005da7a  jb      loc_18005D819
0x18005da80  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005da85  mov     edx, 29h ; ')'
0x18005da8a  mov     dword ptr [rsp+390h+var_368], 8007000Eh
0x18005da92  lea     rcx, aUsernameAllocF; "username alloc failed"
0x18005da99  jmp     loc_18005D7FA
0x18005da9e  mov     rcx, rdi; psz
0x18005daa1  call    cs:__imp_SysAllocString
0x18005daa7  mov     rdi, rax
0x18005daaa  mov     [rsp+390h+var_330], rax
0x18005daaf  test    rax, rax
0x18005dab2  jnz     short loc_18005DB1F
0x18005dab4  mov     ebx, 8007000Eh
0x18005dab9  mov     rcx, cs:WPP_GLOBAL_Control
0x18005dac0  lea     rdx, WPP_GLOBAL_Control
0x18005dac7  cmp     rcx, rdx
0x18005daca  jz      loc_18005D81E
0x18005dad0  test    byte ptr [rcx+1Ch], 8
0x18005dad4  jz      loc_18005D81E
0x18005dada  cmp     byte ptr [rcx+19h], 2
0x18005dade  jb      loc_18005D81E
0x18005dae4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005dae9  lea     edx, [rdi+2Ah]
0x18005daec  mov     dword ptr [rsp+390h+var_368], 8007000Eh
0x18005daf4  lea     rcx, aWorkspaceidAll; "workspaceID alloc failed"
0x18005dafb  mov     [rsp+390h+ppv], rcx
0x18005db00  mov     r9d, eax
0x18005db03  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x18005db0a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005db11  mov     rcx, [rcx+10h]
0x18005db15  call    WPP_SF_DsD
0x18005db1a  jmp     loc_18005D81E
0x18005db1f  test    r14, r14
0x18005db22  jz      short loc_18005DB87
0x18005db24  cmp     [r14], bx
0x18005db28  jz      short loc_18005DB87
0x18005db2a  mov     rcx, r14; psz
0x18005db2d  call    cs:__imp_SysAllocString
0x18005db33  mov     rdi, rax
0x18005db36  test    rax, rax
0x18005db39  jnz     short loc_18005DB8A
0x18005db3b  mov     ebx, 8007000Eh
0x18005db40  mov     rax, cs:WPP_GLOBAL_Control
0x18005db47  lea     rdx, WPP_GLOBAL_Control
0x18005db4e  cmp     rax, rdx
0x18005db51  jz      loc_18005D819
0x18005db57  test    byte ptr [rax+1Ch], 8
0x18005db5b  jz      loc_18005D819
0x18005db61  cmp     byte ptr [rax+19h], 2
0x18005db65  jb      loc_18005D819
0x18005db6b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005db70  lea     edx, [rdi+2Bh]
0x18005db73  mov     dword ptr [rsp+390h+var_368], 8007000Eh
0x18005db7b  lea     rcx, aAppcontainerAl; "AppContainer alloc failed"
0x18005db82  jmp     loc_18005D7FA
0x18005db87  mov     rdi, rbx
0x18005db8a  lea     rax, [rbp+290h+var_2F8]
0x18005db8e  mov     [rsp+390h+ppv], rax; ppv
0x18005db93  lea     r9, _GUID_531e6512_2cbf_4bd2_80a5_d90a71636a9a; riid
0x18005db9a  xor     edx, edx; pUnkOuter
0x18005db9c  lea     r8d, [rdx+4]; dwClsContext
0x18005dba0  lea     rcx, _GUID_4f1dfca6_3aad_48e1_8406_4bc21a501d7c; rclsid
0x18005dba7  call    cs:__imp_CoCreateInstance
0x18005dbad  mov     ebx, eax
0x18005dbaf  test    eax, eax
0x18005dbb1  jns     short loc_18005DBF4
0x18005dbb3  mov     rax, cs:WPP_GLOBAL_Control
0x18005dbba  lea     rdx, WPP_GLOBAL_Control
0x18005dbc1  cmp     rax, rdx
  ... truncated ...
```
