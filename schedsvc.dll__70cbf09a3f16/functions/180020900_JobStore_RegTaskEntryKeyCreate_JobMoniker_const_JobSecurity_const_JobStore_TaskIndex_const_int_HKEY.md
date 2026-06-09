# JobStore::RegTaskEntryKeyCreate(JobMoniker const &,JobSecurity const &,JobStore::TaskIndex const *,int,HKEY__ * *)

- ea: `0x180020900`
- end: `0x1800212f3`
- name: `?RegTaskEntryKeyCreate@JobStore@@AEBAJAEBVJobMoniker@@AEBVJobSecurity@@PEBW4TaskIndex@1@HPEAPEAUHKEY__@@@Z`
- size: `2547`
- prototype: `__int64 __fastcall(JobStore *this, const struct JobMoniker *, const struct JobSecurity *, BYTE *, int, HKEY *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002db7c`

## callees

- `0x18001fc54`
- `0x180020900`
- `0x180021300`
- `0x18002132c`
- `0x18004ba7c`
- `0x1800504b4`
- `0x180053e54`
- `0x180056794`
- `0x18007e67e`
- `0x18007e68a`
- `0x18007e6d0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180020aca`
- `msvcrt!memcpy_s` at `0x180020ae8`
- `msvcrt!memcpy_s` at `0x180020c51`
- `msvcrt!memcpy_s` at `0x180020c75`
- `msvcrt!memcpy_s` at `0x180020aca`
- `msvcrt!memcpy_s` at `0x180020ae8`
- `msvcrt!memcpy_s` at `0x180020c51`
- `msvcrt!memcpy_s` at `0x180020c75`
- `OLEAUT32!__imp_SysAllocString` at `0x180020a2e`
- `OLEAUT32!__imp_SysAllocString` at `0x180020b8e`
- `OLEAUT32!__imp_SysAllocString` at `0x180020a2e`
- `OLEAUT32!__imp_SysAllocString` at `0x180020b8e`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180020a8d`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180020c08`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180020a8d`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180020c08`
- `OLEAUT32!__imp_SysFreeString` at `0x180020996`
- `OLEAUT32!__imp_SysFreeString` at `0x18002099f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800209f0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800209f9`
- `OLEAUT32!__imp_SysFreeString` at `0x180020a21`
- `OLEAUT32!__imp_SysFreeString` at `0x180020b00`
- `OLEAUT32!__imp_SysFreeString` at `0x180020b81`
- `OLEAUT32!__imp_SysFreeString` at `0x180020c91`
- `OLEAUT32!__imp_SysFreeString` at `0x180020d67`
- `OLEAUT32!__imp_SysFreeString` at `0x180020d71`
- `OLEAUT32!__imp_SysFreeString` at `0x180020fd1`
- `OLEAUT32!__imp_SysFreeString` at `0x180020fdb`
- `OLEAUT32!__imp_SysFreeString` at `0x180021077`
- `OLEAUT32!__imp_SysFreeString` at `0x180021081`
- `OLEAUT32!__imp_SysFreeString` at `0x1800211dc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800211e6`
- `OLEAUT32!__imp_SysFreeString` at `0x18002123e`
- `OLEAUT32!__imp_SysFreeString` at `0x180021248`
- `OLEAUT32!__imp_SysFreeString` at `0x180021285`
- `OLEAUT32!__imp_SysFreeString` at `0x18002128f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800212ba`
- `OLEAUT32!__imp_SysFreeString` at `0x1800212c3`
- `OLEAUT32!__imp_SysFreeString` at `0x180020996`
- `OLEAUT32!__imp_SysFreeString` at `0x18002099f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800209f0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800209f9`
- `OLEAUT32!__imp_SysFreeString` at `0x180020a21`
- `OLEAUT32!__imp_SysFreeString` at `0x180020b00`
- `OLEAUT32!__imp_SysFreeString` at `0x180020b81`
- `OLEAUT32!__imp_SysFreeString` at `0x180020c91`
- `OLEAUT32!__imp_SysFreeString` at `0x180020d67`
- `OLEAUT32!__imp_SysFreeString` at `0x180020d71`
- `OLEAUT32!__imp_SysFreeString` at `0x180020fd1`
- `OLEAUT32!__imp_SysFreeString` at `0x180020fdb`
- `OLEAUT32!__imp_SysFreeString` at `0x180021077`
- `OLEAUT32!__imp_SysFreeString` at `0x180021081`
- `OLEAUT32!__imp_SysFreeString` at `0x1800211dc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800211e6`
- `OLEAUT32!__imp_SysFreeString` at `0x18002123e`
- `OLEAUT32!__imp_SysFreeString` at `0x180021248`
- `OLEAUT32!__imp_SysFreeString` at `0x180021285`
- `OLEAUT32!__imp_SysFreeString` at `0x18002128f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800212ba`
- `OLEAUT32!__imp_SysFreeString` at `0x1800212c3`
- `OLEAUT32!__imp_SysStringLen` at `0x180020a67`
- `OLEAUT32!__imp_SysStringLen` at `0x180020aae`
- `OLEAUT32!__imp_SysStringLen` at `0x180020bdf`
- `OLEAUT32!__imp_SysStringLen` at `0x180020c35`
- `OLEAUT32!__imp_SysStringLen` at `0x180020a67`
- `OLEAUT32!__imp_SysStringLen` at `0x180020aae`
- `OLEAUT32!__imp_SysStringLen` at `0x180020bdf`
- `OLEAUT32!__imp_SysStringLen` at `0x180020c35`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180020de3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180020e28`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180020eae`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800210cd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180021167`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180020de3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180020e28`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180020eae`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800210cd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180021167`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180020cf4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180020f5c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180020cf4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180020f5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020fec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021005`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800211fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020fec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021005`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800211fb`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800209e4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800209e4`

## string_xrefs

- `0x180020a27`: `TaskCache\Tasks\`
- `0x180020b87`: `TaskCache\Tree\`

## pseudocode

```c
__int64 __fastcall JobStore::RegTaskEntryKeyCreate(
        JobStore *this,
        const struct JobMoniker *a2,
        const struct JobSecurity *a3,
        BYTE *a4,
        int a5,
        HKEY *a6)
{
  const struct JobMoniker *v6; // r14
  OLECHAR *v8; // rdi
  __int64 v9; // rsi
  __int64 v10; // rbx
  signed int v11; // eax
  __int64 v12; // r15
  signed int v13; // r14d
  signed int v14; // ecx
  BSTR v15; // r12
  signed int v16; // r13d
  errno_t v17; // eax
  errno_t v18; // eax
  BYTE *Path; // rax
  BYTE *v20; // r15
  __int64 v21; // rdx
  BYTE *v22; // rcx
  __int64 v23; // r12
  OLECHAR *v24; // rbx
  BYTE *v25; // r14
  signed int v26; // eax
  signed int v27; // r15d
  BSTR v28; // r13
  errno_t v29; // eax
  errno_t v30; // eax
  JobStore *v31; // r13
  LSTATUS v32; // eax
  unsigned int v33; // esi
  const unsigned __int16 *v34; // rax
  int v35; // edx
  const WCHAR *v36; // r9
  LSTATUS v37; // eax
  LSTATUS v38; // eax
  const unsigned __int16 *v39; // rax
  int v40; // edx
  const WCHAR *v41; // r9
  LSTATUS v42; // eax
  unsigned int v43; // eax
  LSTATUS v44; // eax
  HKEY v45; // rcx
  const unsigned __int16 *v46; // rax
  LSTATUS v47; // eax
  JobMoniker *v48; // r14
  __int64 v49; // rax
  const BYTE *v50; // r8
  LSTATUS v51; // eax
  const unsigned __int16 *v52; // rax
  int i; // esi
  int v54; // r14d
  HKEY v55; // rax
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  JobMoniker *v58; // [rsp+60h] [rbp-A0h]
  int v59; // [rsp+68h] [rbp-98h]
  DWORD dwDisposition; // [rsp+6Ch] [rbp-94h] BYREF
  BYTE *v61; // [rsp+70h] [rbp-90h]
  __int64 v62; // [rsp+78h] [rbp-88h]
  OLECHAR *v63; // [rsp+80h] [rbp-80h]
  BYTE *lpData; // [rsp+88h] [rbp-78h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+90h] [rbp-70h] BYREF
  OLECHAR *v66; // [rsp+A8h] [rbp-58h]
  JobStore *v67; // [rsp+B0h] [rbp-50h]
  const struct JobSecurity *v68; // [rsp+B8h] [rbp-48h]
  HKEY *v69; // [rsp+C0h] [rbp-40h]
  GUID Buf2; // [rsp+C8h] [rbp-38h] BYREF
  OLECHAR sz[40]; // [rsp+E0h] [rbp-20h] BYREF

  lpData = a4;
  v68 = a3;
  v6 = a2;
  v58 = a2;
  v67 = this;
  v69 = a6;
  dwDisposition = 0;
  hKey = 0;
  phkResult = 0;
  v63 = 0;
  *(_QWORD *)&SecurityAttributes.nLength = 24;
  SecurityAttributes.lpSecurityDescriptor = tsched::StoreSecurity::g_pRestrictedKeySecurity;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
  Buf2 = *(GUID *)a2;
  if ( !memcmp_0(&GUID_NULL, &Buf2, 0x10u) )
  {
    SysFreeString(0);
    SysFreeString(0);
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&phkResult);
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
    return 2147942487LL;
  }
  memset_0(sz, 0, sizeof(sz));
  if ( !StringFromGUID2(&Buf2, sz, 40) )
  {
    SysFreeString(0);
    SysFreeString(0);
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&phkResult);
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
    return 2147942522LL;
  }
  SysFreeString(0);
  v8 = SysAllocString(L"TaskCache\\Tasks\\");
  v66 = v8;
  if ( !v8 )
    goto LABEL_120;
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( sz[v10] );
  if ( !(_DWORD)v10 )
  {
LABEL_16:
    v14 = 0;
    goto LABEL_17;
  }
  v11 = SysStringLen(v8);
  v12 = v11;
  v13 = v11 + v10;
  if ( v11 + (int)v10 >= v11 )
  {
    v15 = SysAllocStringLen(0, v13);
    if ( !v15 )
    {
      v16 = -2147024882;
      v14 = -2147024882;
      v6 = v58;
      goto LABEL_18;
    }
    if ( SysStringLen(v8) )
    {
      v17 = memcpy_s(v15, 2LL * v13, v8, 2 * v12);
      ATL::AtlCrtErrorCheck(v17);
    }
    v18 = memcpy_s(&v15[v12], 2LL * (int)v10, sz, 2LL * (int)v10);
    ATL::AtlCrtErrorCheck(v18);
    v15[v13] = 0;
    SysFreeString(v8);
    v8 = v15;
    v66 = v15;
    v6 = v58;
    goto LABEL_16;
  }
  v14 = -2147024882;
  v6 = v58;
LABEL_17:
  v16 = -2147024882;
LABEL_18:
  if ( v14 < 0 )
    ATL::PrivateAtlThrow(v14);
  Path = (BYTE *)JobMoniker::GetPath(v6);
  v20 = Path;
  v61 = Path;
  if ( !Path )
    goto LABEL_119;
  v21 = 260;
  v22 = Path;
  do
  {
    if ( !*(_WORD *)v22 )
      break;
    v22 += 2;
    --v21;
  }
  while ( v21 );
  v23 = 260 - v21;
  if ( !v21 )
    v23 = 0;
  v62 = v23;
  if ( !v21 )
  {
LABEL_119:
    SysFreeString(v8);
    SysFreeString(0);
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&phkResult);
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
    return 2147942487LL;
  }
  SysFreeString(0);
  v24 = SysAllocString(L"TaskCache\\Tree\\");
  v63 = v24;
  if ( !v24 )
LABEL_120:
    ATL::PrivateAtlThrow(0x8007000E);
  if ( *(_WORD *)v20 == 92 )
  {
    v25 = v20 + 2;
    if ( v20 == (BYTE *)-2LL )
    {
      LODWORD(v9) = 0;
      goto LABEL_33;
    }
  }
  else
  {
    v25 = v20;
  }
  do
    ++v9;
  while ( *(_WORD *)&v25[2 * v9] );
LABEL_33:
  if ( !v25 || !(_DWORD)v9 )
    goto LABEL_42;
  v26 = SysStringLen(v24);
  v23 = v26;
  v27 = v26 + v9;
  if ( v26 + (int)v9 >= v26 )
  {
    v28 = SysAllocStringLen(0, v27);
    if ( !v28 )
    {
      v59 = -2147024882;
      v20 = v61;
      LODWORD(v23) = v62;
      v16 = -2147024882;
      goto LABEL_43;
    }
    if ( SysStringLen(v24) )
    {
      v29 = memcpy_s(v28, 2LL * v27, v24, 2 * v23);
      ATL::AtlCrtErrorCheck(v29);
    }
    v30 = memcpy_s(&v28[v23], 2LL * (int)v9, v25, 2LL * (int)v9);
    ATL::AtlCrtErrorCheck(v30);
    v28[v27] = 0;
    SysFreeString(v24);
    v24 = v28;
    v63 = v28;
    v20 = v61;
    LODWORD(v23) = v62;
LABEL_42:
    v16 = 0;
    goto LABEL_43;
  }
  v20 = v61;
  LODWORD(v23) = v62;
LABEL_43:
  if ( v16 < 0 )
    ATL::PrivateAtlThrow(v16);
  v31 = v67;
  v32 = RegCreateKeyExW(*((HKEY *)v67 + 2), v24, 0, 0, 0, 0xF003Fu, &SecurityAttributes, &hKey, 0);
  v33 = v32;
  if ( v32 )
  {
    if ( v32 > 0 )
      v33 = (unsigned __int16)v32 | 0x80070000;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_53;
    }
    v34 = JobMoniker::GetPath(v58);
    v35 = 37;
    LODWORD(v36) = (_DWORD)v24;
    goto LABEL_52;
  }
  if ( !*(_QWORD *)v68 )
  {
    v33 = -2147023537;
    goto LABEL_53;
  }
  v37 = RegSetValueExW(hKey, L"SD", 0, 3u, *(const BYTE **)v68, *((_DWORD *)v68 + 2));
  v33 = v37;
  if ( v37 )
  {
    if ( v37 > 0 )
      v33 = (unsigned __int16)v37 | 0x80070000;
    if ( (v33 & 0x80000000) != 0 )
      goto LABEL_53;
  }
  v38 = RegSetValueExW(hKey, L"Id", 0, 1u, (const BYTE *)sz, 0x50u);
  v33 = v38;
  if ( v38 )
  {
    if ( v38 > 0 )
      v33 = (unsigned __int16)v38 | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v39 = JobMoniker::GetPath(v58);
      v40 = 38;
      v41 = L"Id";
LABEL_82:
      WPP_SF_SSD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v40,
        (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
        (_DWORD)v41,
        (__int64)v39,
        v33);
      goto LABEL_83;
    }
    goto LABEL_83;
  }
  v42 = RegSetValueExW(hKey, L"Index", 0, 4u, lpData, 4u);
  v33 = v42;
  if ( v42 )
  {
    if ( v42 > 0 )
      v33 = (unsigned __int16)v42 | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v43 = (unsigned int)JobMoniker::GetPath(v58);
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
        v43,
        v33);
    }
    goto LABEL_53;
  }
  v44 = RegCreateKeyExW(*((HKEY *)v31 + 2), v8, 0, 0, 0, 0xF003Fu, &SecurityAttributes, &phkResult, &dwDisposition);
  v33 = v44;
  if ( v44 )
  {
    if ( v44 > 0 )
      v33 = (unsigned __int16)v44 | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v39 = JobMoniker::GetPath(v58);
      v40 = 40;
      LODWORD(v41) = (_DWORD)v8;
      goto LABEL_82;
    }
LABEL_83:
    SysFreeString(v8);
    SysFreeString(v24);
    v45 = phkResult;
    if ( !phkResult )
      goto LABEL_85;
    goto LABEL_84;
  }
  if ( dwDisposition == 1 )
  {
    v47 = RegSetValueExW(phkResult, L"Path", 0, 1u, v20, 2 * v23 + 2);
    v33 = v47;
    if ( v47 )
    {
      if ( v47 > 0 )
        v33 = (unsigned __int16)v47 | 0x80070000;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_53;
      }
      v34 = JobMoniker::GetPath(v58);
      v35 = 42;
      v36 = L"Path";
LABEL_52:
      WPP_SF_SSD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v35,
        (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
        (_DWORD)v36,
        (__int64)v34,
        v33);
LABEL_53:
      SysFreeString(v8);
      SysFreeString(v24);
      wmi::AutoRegKey::Close((wmi::AutoRegKey *)&phkResult);
      wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
      return v33;
    }
    v48 = v58;
    v49 = *((_QWORD *)v58 + 4);
    v50 = (const BYTE *)(v49 + 28);
    if ( !*(_DWORD *)(v49 + 60) )
      v50 = 0;
    v51 = RegSetValueExW(phkResult, L"Hash", 0, 3u, v50, 0x20u);
    v33 = v51;
    if ( v51 )
    {
      if ( v51 > 0 )
        v33 = (unsigned __int16)v51 | 0x80070000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v52 = JobMoniker::GetPath(v48);
        WPP_SF_SSD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
          (unsigned int)L"Hash",
          (__int64)v52,
          v33);
      }
      SysFreeString(v8);
      SysFreeString(v24);
      v45 = phkResult;
      if ( !phkResult )
        goto LABEL_85;
LABEL_84:
      RegCloseKey(v45);
      phkResult = 0;
LABEL_85:
      if ( hKey )
        RegCloseKey(hKey);
      return v33;
    }
    for ( i = 0; i < a5; ++i )
    {
      v54 = JobStore::CreateIndexEntryP(v31, *(unsigned int *)&lpData[4 * i], sz, &SecurityAttributes);
      if ( v54 < 0 )
      {
        SysFreeString(v8);
        SysFreeString(v24);
        wmi::AutoRegKey::Close((wmi::AutoRegKey *)&phkResult);
        wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
        return (unsigned int)v54;
      }
    }
    if ( v69 )
    {
      v55 = phkResult;
      phkResult = 0;
      *v69 = v55;
    }
    SysFreeString(v8);
    SysFreeString(v24);
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&phkResult);
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v46 = JobMoniker::GetPath(v58);
      WPP_SF_SSD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
        (_DWORD)v8,
        (__int64)v46,
        183);
    }
    SysFreeString(v8);
    SysFreeString(v24);
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&phkResult);
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
    return 2147942583LL;
  }
}

```

## disassembly

```asm
0x180020900  push    rbp
0x180020902  push    rbx
0x180020903  push    rsi
0x180020904  push    rdi
0x180020905  push    r12
0x180020907  push    r13
0x180020909  push    r14
0x18002090b  push    r15
0x18002090d  lea     rbp, [rsp-48h]
0x180020912  sub     rsp, 148h
0x180020919  mov     rax, cs:__security_cookie
0x180020920  xor     rax, rsp
0x180020923  mov     [rbp+80h+var_50], rax
0x180020927  mov     [rbp+80h+lpData], r9
0x18002092b  mov     [rbp+80h+var_C8], r8
0x18002092f  mov     r14, rdx
0x180020932  mov     [rsp+180h+var_120], rdx
0x180020937  mov     [rbp+80h+var_D0], rcx
0x18002093b  mov     rax, [rbp+80h+arg_28]
0x180020942  mov     [rbp+80h+var_C0], rax
0x180020946  xor     r13d, r13d
0x180020949  mov     [rsp+180h+dwDisposition], r13d
0x18002094e  mov     [rsp+180h+hKey], r13
0x180020953  mov     [rsp+180h+var_130], r13
0x180020958  mov     [rbp+80h+var_100], r13
0x18002095c  mov     qword ptr [rbp+80h+SecurityAttributes.nLength], 18h
0x180020964  mov     rax, cs:?g_pRestrictedKeySecurity@StoreSecurity@tsched@@3PEAXEA; void * tsched::StoreSecurity::g_pRestrictedKeySecurity
0x18002096b  mov     [rbp+80h+SecurityAttributes.lpSecurityDescriptor], rax
0x18002096f  mov     qword ptr [rbp+80h+SecurityAttributes.bInheritHandle], r13
0x180020973  movups  xmm0, xmmword ptr [rdx]
0x180020976  movups  xmmword ptr [rbp+80h+Buf2.Data1], xmm0
0x18002097a  mov     r8d, 10h; Size
0x180020980  lea     rdx, [rbp+80h+Buf2]; Buf2
0x180020984  lea     rcx, GUID_NULL; Buf1
0x18002098b  call    memcmp_0
0x180020990  test    eax, eax
0x180020992  jnz     short loc_1800209C5
0x180020994  xor     ecx, ecx; bstrString
0x180020996  call    cs:__imp_SysFreeString
0x18002099c  nop
0x18002099d  xor     ecx, ecx; bstrString
0x18002099f  call    cs:__imp_SysFreeString
0x1800209a5  nop
0x1800209a6  lea     rcx, [rsp+180h+var_130]; this
0x1800209ab  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x1800209b0  nop
0x1800209b1  lea     rcx, [rsp+180h+hKey]; this
0x1800209b6  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x1800209bb  mov     eax, 80070057h
0x1800209c0  jmp     loc_180020D8F
0x1800209c5  xor     edx, edx; Val
0x1800209c7  mov     r8d, 50h ; 'P'; Size
0x1800209cd  lea     rcx, [rbp+80h+sz]; void *
0x1800209d1  call    memset_0
0x1800209d6  mov     r8d, 28h ; '('; cchMax
0x1800209dc  lea     rdx, [rbp+80h+sz]; lpsz
0x1800209e0  lea     rcx, [rbp+80h+Buf2]; rguid
0x1800209e4  call    cs:__imp_StringFromGUID2
0x1800209ea  test    eax, eax
0x1800209ec  jnz     short loc_180020A1F
0x1800209ee  xor     ecx, ecx; bstrString
0x1800209f0  call    cs:__imp_SysFreeString
0x1800209f6  nop
0x1800209f7  xor     ecx, ecx; bstrString
0x1800209f9  call    cs:__imp_SysFreeString
0x1800209ff  nop
0x180020a00  lea     rcx, [rsp+180h+var_130]; this
0x180020a05  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180020a0a  nop
0x180020a0b  lea     rcx, [rsp+180h+hKey]; this
0x180020a10  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180020a15  mov     eax, 8007007Ah
0x180020a1a  jmp     loc_180020D8F
0x180020a1f  xor     ecx, ecx; bstrString
0x180020a21  call    cs:__imp_SysFreeString
0x180020a27  lea     rcx, aTaskcacheTasks; "TaskCache\\Tasks\\"
0x180020a2e  call    cs:__imp_SysAllocString
0x180020a34  mov     rdi, rax
0x180020a37  mov     [rbp+80h+var_D8], rax
0x180020a3b  test    rax, rax
0x180020a3e  jz      loc_1800212E6
0x180020a44  lea     rax, [rbp+80h+sz]
0x180020a48  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180020a4f  mov     rbx, rsi
0x180020a52  inc     rbx
0x180020a55  cmp     word ptr [rax+rbx*2], 0
0x180020a5a  jnz     short loc_180020A52
0x180020a5c  test    ebx, ebx
0x180020a5e  jz      loc_180020B12
0x180020a64  mov     rcx, rdi; pbstr
0x180020a67  call    cs:__imp_SysStringLen
0x180020a6d  movsxd  r15, eax
0x180020a70  lea     r14d, [r15+rbx]
0x180020a74  cmp     r14d, r15d
0x180020a77  jge     short loc_180020A88
0x180020a79  mov     ecx, 8007000Eh
0x180020a7e  mov     r14, [rsp+180h+var_120]
0x180020a83  jmp     loc_180020B15
0x180020a88  mov     edx, r14d; ui
0x180020a8b  xor     ecx, ecx; strIn
0x180020a8d  call    cs:__imp_SysAllocStringLen
0x180020a93  mov     r12, rax
0x180020a96  test    rax, rax
0x180020a99  jnz     short loc_180020AAB
0x180020a9b  mov     r13d, 8007000Eh
0x180020aa1  mov     ecx, r13d
0x180020aa4  mov     r14, [rsp+180h+var_120]
0x180020aa9  jmp     short loc_180020B1B
0x180020aab  mov     rcx, rdi; pbstr
0x180020aae  call    cs:__imp_SysStringLen
0x180020ab4  test    eax, eax
0x180020ab6  jz      short loc_180020AD7
0x180020ab8  mov     r9, r15
0x180020abb  add     r9, r9; SourceSize
0x180020abe  movsxd  rdx, r14d
0x180020ac1  add     rdx, rdx; DestinationSize
0x180020ac4  mov     r8, rdi; Source
0x180020ac7  mov     rcx, r12; Destination
0x180020aca  call    cs:__imp_memcpy_s
0x180020ad0  mov     ecx, eax; int
0x180020ad2  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180020ad7  movsxd  rdx, ebx
0x180020ada  add     rdx, rdx; DestinationSize
0x180020add  lea     rcx, [r12+r15*2]; Destination
0x180020ae1  mov     r9, rdx; SourceSize
0x180020ae4  lea     r8, [rbp+80h+sz]; Source
0x180020ae8  call    cs:__imp_memcpy_s
0x180020aee  mov     ecx, eax; int
0x180020af0  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180020af5  movsxd  rcx, r14d
0x180020af8  mov     [r12+rcx*2], r13w
0x180020afd  mov     rcx, rdi; bstrString
0x180020b00  call    cs:__imp_SysFreeString
0x180020b06  mov     rdi, r12
0x180020b09  mov     [rbp+80h+var_D8], r12
0x180020b0d  mov     r14, [rsp+180h+var_120]
0x180020b12  mov     ecx, r13d; unsigned int
0x180020b15  mov     r13d, 8007000Eh
0x180020b1b  test    ecx, ecx
0x180020b1d  jns     short loc_180020B25
0x180020b1f  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x180020b25  mov     rcx, r14; this
0x180020b28  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x180020b2d  mov     r15, rax
0x180020b30  mov     [rsp+180h+var_110], rax
0x180020b35  test    rax, rax
0x180020b38  jz      loc_1800212B2
0x180020b3e  mov     r12d, 104h
0x180020b44  mov     edx, r12d
0x180020b47  mov     rcx, rax
0x180020b4a  nop     word ptr [rax+rax+00h]
0x180020b50  cmp     word ptr [rcx], 0
0x180020b54  jz      short loc_180020B60
0x180020b56  add     rcx, 2
0x180020b5a  sub     rdx, 1
0x180020b5e  jnz     short loc_180020B50
0x180020b60  sub     r12, rdx
0x180020b63  xor     eax, eax
0x180020b65  test    rdx, rdx
0x180020b68  cmovz   r12, rax
0x180020b6c  mov     [rsp+180h+var_108], r12
0x180020b71  mov     ebx, 80070057h
0x180020b76  cmovnz  ebx, eax
0x180020b79  jz      loc_1800212B7
0x180020b7f  xor     ecx, ecx; bstrString
0x180020b81  call    cs:__imp_SysFreeString
0x180020b87  lea     rcx, aTaskcacheTree_0; "TaskCache\\Tree\\"
0x180020b8e  call    cs:__imp_SysAllocString
0x180020b94  mov     rbx, rax
0x180020b97  mov     [rbp+80h+var_100], rax
0x180020b9b  test    rax, rax
0x180020b9e  jz      loc_1800212E6
0x180020ba4  mov     eax, 5Ch ; '\'
0x180020ba9  cmp     ax, [r15]
0x180020bad  jnz     short loc_180020BBC
0x180020baf  lea     r14, [r15+2]
0x180020bb3  test    r14, r14
0x180020bb6  jnz     short loc_180020BC0
0x180020bb8  xor     esi, esi
0x180020bba  jmp     short loc_180020BCB
0x180020bbc  mov     r14, r15
0x180020bbf  nop
0x180020bc0  inc     rsi
0x180020bc3  cmp     word ptr [r14+rsi*2], 0
0x180020bc9  jnz     short loc_180020BC0
0x180020bcb  test    r14, r14
0x180020bce  jz      loc_180020CAA
0x180020bd4  test    esi, esi
0x180020bd6  jz      loc_180020CAA
0x180020bdc  mov     rcx, rbx; pbstr
0x180020bdf  call    cs:__imp_SysStringLen
0x180020be5  movsxd  r12, eax
0x180020be8  lea     r15d, [r12+rsi]
0x180020bec  cmp     r15d, r12d
0x180020bef  jge     short loc_180020C03
0x180020bf1  mov     r15, [rsp+180h+var_110]
0x180020bf6  mov     r12, [rsp+180h+var_108]
0x180020bfb  xor     r14d, r14d
0x180020bfe  jmp     loc_180020CB0
0x180020c03  mov     edx, r15d; ui
0x180020c06  xor     ecx, ecx; strIn
0x180020c08  call    cs:__imp_SysAllocStringLen
0x180020c0e  mov     r13, rax
0x180020c11  test    rax, rax
0x180020c14  jnz     short loc_180020C32
0x180020c16  mov     [rsp+180h+var_118], 8007000Eh
0x180020c1e  mov     r15, [rsp+180h+var_110]
0x180020c23  mov     r12, [rsp+180h+var_108]
0x180020c28  mov     r13d, [rsp+180h+var_118]
0x180020c2d  xor     r14d, r14d
0x180020c30  jmp     short loc_180020CB0
0x180020c32  mov     rcx, rbx; pbstr
0x180020c35  call    cs:__imp_SysStringLen
0x180020c3b  test    eax, eax
0x180020c3d  jz      short loc_180020C5E
0x180020c3f  mov     r9, r12
0x180020c42  add     r9, r9; SourceSize
0x180020c45  movsxd  rdx, r15d
0x180020c48  add     rdx, rdx; DestinationSize
0x180020c4b  mov     r8, rbx; Source
0x180020c4e  mov     rcx, r13; Destination
0x180020c51  call    cs:__imp_memcpy_s
0x180020c57  mov     ecx, eax; int
0x180020c59  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180020c5e  movsxd  rdx, esi
0x180020c61  add     rdx, rdx; DestinationSize
0x180020c64  lea     rcx, ds:0[r12*2]
0x180020c6c  add     rcx, r13; Destination
0x180020c6f  mov     r9, rdx; SourceSize
0x180020c72  mov     r8, r14; Source
0x180020c75  call    cs:__imp_memcpy_s
0x180020c7b  mov     ecx, eax; int
0x180020c7d  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180020c82  movsxd  rcx, r15d
0x180020c85  xor     r14d, r14d
0x180020c88  mov     [r13+rcx*2+0], r14w
0x180020c8e  mov     rcx, rbx; bstrString
0x180020c91  call    cs:__imp_SysFreeString
0x180020c97  mov     rbx, r13
0x180020c9a  mov     [rbp+80h+var_100], rbx
0x180020c9e  mov     r15, [rsp+180h+var_110]
0x180020ca3  mov     r12, [rsp+180h+var_108]
0x180020ca8  jmp     short loc_180020CAD
0x180020caa  xor     r14d, r14d
0x180020cad  mov     r13d, r14d
0x180020cb0  test    r13d, r13d
0x180020cb3  jns     short loc_180020CBE
0x180020cb5  mov     ecx, r13d; unsigned int
0x180020cb8  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x180020cbe  mov     [rsp+180h+lpdwDisposition], r14; lpdwDisposition
0x180020cc3  lea     rax, [rsp+180h+hKey]
0x180020cc8  mov     [rsp+180h+phkResult], rax; phkResult
0x180020ccd  lea     rax, [rbp+80h+SecurityAttributes]
0x180020cd1  mov     [rsp+180h+lpSecurityAttributes], rax; lpSecurityAttributes
0x180020cd6  mov     [rsp+180h+samDesired], 0F003Fh; samDesired
0x180020cde  mov     [rsp+180h+dwOptions], r14d; dwOptions
0x180020ce3  xor     r9d, r9d; lpClass
0x180020ce6  xor     r8d, r8d; Reserved
0x180020ce9  mov     rdx, rbx; lpSubKey
0x180020cec  mov     r13, [rbp+80h+var_D0]
0x180020cf0  mov     rcx, [r13+10h]; hKey
0x180020cf4  call    cs:__imp_RegCreateKeyExW
0x180020cfa  mov     esi, eax
0x180020cfc  test    eax, eax
0x180020cfe  jz      loc_180020DAF
0x180020d04  jle     short loc_180020D0F
0x180020d06  movzx   esi, ax
0x180020d09  or      esi, 80070000h
0x180020d0f  lea     rax, WPP_GLOBAL_Control
0x180020d16  mov     rdx, cs:WPP_GLOBAL_Control
0x180020d1d  cmp     rdx, rax
0x180020d20  jz      short loc_180020D64
0x180020d22  test    dword ptr [rdx+1Ch], 40000h
0x180020d29  jz      short loc_180020D64
0x180020d2b  cmp     byte ptr [rdx+19h], 2
0x180020d2f  jb      short loc_180020D64
0x180020d31  mov     rcx, [rsp+180h+var_120]; this
0x180020d36  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x180020d3b  mov     edx, 25h ; '%'
0x180020d40  mov     r9, rbx
0x180020d43  mov     [rsp+180h+samDesired], esi
0x180020d47  mov     qword ptr [rsp+180h+dwOptions], rax
0x180020d4c  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x180020d53  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d5a  mov     rcx, [rcx+10h]
0x180020d5e  call    WPP_SF_SSD
0x180020d63  nop
0x180020d64  mov     rcx, rdi; bstrString
0x180020d67  call    cs:__imp_SysFreeString
0x180020d6d  nop
0x180020d6e  mov     rcx, rbx; bstrString
0x180020d71  call    cs:__imp_SysFreeString
0x180020d77  nop
0x180020d78  lea     rcx, [rsp+180h+var_130]; this
0x180020d7d  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180020d82  nop
0x180020d83  lea     rcx, [rsp+180h+hKey]; this
0x180020d88  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180020d8d  mov     eax, esi
0x180020d8f  mov     rcx, [rbp+80h+var_50]
  ... truncated ...
```
