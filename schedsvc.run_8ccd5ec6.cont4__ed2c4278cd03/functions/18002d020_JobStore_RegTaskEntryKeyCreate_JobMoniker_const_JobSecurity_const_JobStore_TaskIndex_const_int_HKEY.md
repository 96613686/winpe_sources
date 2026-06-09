# JobStore::RegTaskEntryKeyCreate(JobMoniker const &,JobSecurity const &,JobStore::TaskIndex const *,int,HKEY__ * *)

- ea: `0x18002d020`
- end: `0x18002db2b`
- name: `?RegTaskEntryKeyCreate@JobStore@@AEBAJAEBVJobMoniker@@AEBVJobSecurity@@PEBW4TaskIndex@1@HPEAPEAUHKEY__@@@Z`
- size: `2827`
- prototype: `__int64 __fastcall(JobStore *__hidden this, const struct JobMoniker *, const struct JobSecurity *, const enum JobStore::TaskIndex *, int, HKEY *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002dbc4`

## callees

- `0x18002c2f4`
- `0x18002d020`
- `0x18002db40`
- `0x18002db74`
- `0x18004df30`
- `0x1800529a0`
- `0x180056714`
- `0x180059140`
- `0x1800829ee`
- `0x1800829fa`
- `0x180082a40`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18002d22d`
- `msvcrt!memcpy_s` at `0x18002d251`
- `msvcrt!memcpy_s` at `0x18002d3e6`
- `msvcrt!memcpy_s` at `0x18002d410`
- `msvcrt!memcpy_s` at `0x18002d22d`
- `msvcrt!memcpy_s` at `0x18002d251`
- `msvcrt!memcpy_s` at `0x18002d3e6`
- `msvcrt!memcpy_s` at `0x18002d410`
- `OLEAUT32!__imp_SysAllocString` at `0x18002d172`
- `OLEAUT32!__imp_SysAllocString` at `0x18002d304`
- `OLEAUT32!__imp_SysAllocString` at `0x18002d172`
- `OLEAUT32!__imp_SysAllocString` at `0x18002d304`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002d1e1`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002d38e`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002d1e1`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002d38e`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d0b6`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d0c5`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d122`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d131`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d15f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d26f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d2f1`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d432`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d514`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d524`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d7a3`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d7b3`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d861`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d871`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d9de`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d9ee`
- `OLEAUT32!__imp_SysFreeString` at `0x18002da52`
- `OLEAUT32!__imp_SysFreeString` at `0x18002da62`
- `OLEAUT32!__imp_SysFreeString` at `0x18002daa5`
- `OLEAUT32!__imp_SysFreeString` at `0x18002dab5`
- `OLEAUT32!__imp_SysFreeString` at `0x18002dae6`
- `OLEAUT32!__imp_SysFreeString` at `0x18002daf5`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d0b6`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d0c5`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d122`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d131`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d15f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d26f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d2f1`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d432`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d514`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d524`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d7a3`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d7b3`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d861`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d871`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d9de`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d9ee`
- `OLEAUT32!__imp_SysFreeString` at `0x18002da52`
- `OLEAUT32!__imp_SysFreeString` at `0x18002da62`
- `OLEAUT32!__imp_SysFreeString` at `0x18002daa5`
- `OLEAUT32!__imp_SysFreeString` at `0x18002dab5`
- `OLEAUT32!__imp_SysFreeString` at `0x18002dae6`
- `OLEAUT32!__imp_SysFreeString` at `0x18002daf5`
- `OLEAUT32!__imp_SysStringLen` at `0x18002d1b5`
- `OLEAUT32!__imp_SysStringLen` at `0x18002d20b`
- `OLEAUT32!__imp_SysStringLen` at `0x18002d35f`
- `OLEAUT32!__imp_SysStringLen` at `0x18002d3c4`
- `OLEAUT32!__imp_SysStringLen` at `0x18002d1b5`
- `OLEAUT32!__imp_SysStringLen` at `0x18002d20b`
- `OLEAUT32!__imp_SysStringLen` at `0x18002d35f`
- `OLEAUT32!__imp_SysStringLen` at `0x18002d3c4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002d59d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002d5e8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002d674`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002d8c3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002d963`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002d59d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002d5e8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002d674`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002d8c3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002d963`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002d49b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002d728`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002d49b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002d728`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d7ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d7e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002da09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d7ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d7e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002da09`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002d110`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002d110`

## string_xrefs

- `0x18002d16b`: `TaskCache\Tasks\`
- `0x18002d2fd`: `TaskCache\Tree\`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
0x18002d020  push    rbp
0x18002d022  push    rbx
0x18002d023  push    rsi
0x18002d024  push    rdi
0x18002d025  push    r12
0x18002d027  push    r13
0x18002d029  push    r14
0x18002d02b  push    r15
0x18002d02d  lea     rbp, [rsp-48h]
0x18002d032  sub     rsp, 148h
0x18002d039  mov     rax, cs:__security_cookie
0x18002d040  xor     rax, rsp
0x18002d043  mov     [rbp+80h+var_50], rax
0x18002d047  mov     [rbp+80h+lpData], r9
0x18002d04b  mov     [rbp+80h+var_C8], r8
0x18002d04f  mov     r14, rdx
0x18002d052  mov     [rsp+180h+var_120], rdx
0x18002d057  mov     [rbp+80h+var_D0], rcx
0x18002d05b  mov     rax, [rbp+80h+arg_28]
0x18002d062  mov     [rbp+80h+var_C0], rax
0x18002d066  xor     r13d, r13d
0x18002d069  mov     [rsp+180h+dwDisposition], r13d
0x18002d06e  mov     [rsp+180h+hKey], r13
0x18002d073  mov     [rsp+180h+var_130], r13
0x18002d078  mov     [rbp+80h+var_100], r13
0x18002d07c  mov     qword ptr [rbp+80h+SecurityAttributes.nLength], 18h
0x18002d084  mov     rax, cs:?g_pRestrictedKeySecurity@StoreSecurity@tsched@@3PEAXEA; void * tsched::StoreSecurity::g_pRestrictedKeySecurity
0x18002d08b  mov     [rbp+80h+SecurityAttributes.lpSecurityDescriptor], rax
0x18002d08f  mov     qword ptr [rbp+80h+SecurityAttributes.bInheritHandle], r13
0x18002d093  movups  xmm0, xmmword ptr [rdx]
0x18002d096  movups  xmmword ptr [rbp+80h+Buf2.Data1], xmm0
0x18002d09a  mov     r8d, 10h; Size
0x18002d0a0  lea     rdx, [rbp+80h+Buf2]; Buf2
0x18002d0a4  lea     rcx, GUID_NULL; Buf1
0x18002d0ab  call    memcmp_0
0x18002d0b0  test    eax, eax
0x18002d0b2  jnz     short loc_18002D0F1
0x18002d0b4  xor     ecx, ecx; bstrString
0x18002d0b6  call    cs:__imp_SysFreeString
0x18002d0bd  nop     dword ptr [rax+rax+00h]
0x18002d0c2  nop
0x18002d0c3  xor     ecx, ecx; bstrString
0x18002d0c5  call    cs:__imp_SysFreeString
0x18002d0cc  nop     dword ptr [rax+rax+00h]
0x18002d0d1  nop
0x18002d0d2  lea     rcx, [rsp+180h+var_130]; this
0x18002d0d7  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18002d0dc  nop
0x18002d0dd  lea     rcx, [rsp+180h+hKey]; this
0x18002d0e2  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18002d0e7  mov     eax, 80070057h
0x18002d0ec  jmp     loc_18002D548
0x18002d0f1  xor     edx, edx; Val
0x18002d0f3  mov     r8d, 50h ; 'P'; Size
0x18002d0f9  lea     rcx, [rbp+80h+sz]; void *
0x18002d0fd  call    memset_0
0x18002d102  mov     r8d, 28h ; '('; cchMax
0x18002d108  lea     rdx, [rbp+80h+sz]; lpsz
0x18002d10c  lea     rcx, [rbp+80h+Buf2]; rguid
0x18002d110  call    cs:__imp_StringFromGUID2
0x18002d117  nop     dword ptr [rax+rax+00h]
0x18002d11c  test    eax, eax
0x18002d11e  jnz     short loc_18002D15D
0x18002d120  xor     ecx, ecx; bstrString
0x18002d122  call    cs:__imp_SysFreeString
0x18002d129  nop     dword ptr [rax+rax+00h]
0x18002d12e  nop
0x18002d12f  xor     ecx, ecx; bstrString
0x18002d131  call    cs:__imp_SysFreeString
0x18002d138  nop     dword ptr [rax+rax+00h]
0x18002d13d  nop
0x18002d13e  lea     rcx, [rsp+180h+var_130]; this
0x18002d143  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18002d148  nop
0x18002d149  lea     rcx, [rsp+180h+hKey]; this
0x18002d14e  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18002d153  mov     eax, 8007007Ah
0x18002d158  jmp     loc_18002D548
0x18002d15d  xor     ecx, ecx; bstrString
0x18002d15f  call    cs:__imp_SysFreeString
0x18002d166  nop     dword ptr [rax+rax+00h]
0x18002d16b  lea     rcx, aTaskcacheTasks; "TaskCache\\Tasks\\"
0x18002d172  call    cs:__imp_SysAllocString
0x18002d179  nop     dword ptr [rax+rax+00h]
0x18002d17e  mov     rdi, rax
0x18002d181  mov     [rbp+80h+var_D8], rax
0x18002d185  test    rax, rax
0x18002d188  jz      loc_18002DB1E
0x18002d18e  lea     rax, [rbp+80h+sz]
0x18002d192  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18002d199  mov     rbx, rsi
0x18002d19c  nop     dword ptr [rax+00h]
0x18002d1a0  inc     rbx
0x18002d1a3  cmp     word ptr [rax+rbx*2], 0
0x18002d1a8  jnz     short loc_18002D1A0
0x18002d1aa  test    ebx, ebx
0x18002d1ac  jz      loc_18002D287
0x18002d1b2  mov     rcx, rdi; pbstr
0x18002d1b5  call    cs:__imp_SysStringLen
0x18002d1bc  nop     dword ptr [rax+rax+00h]
0x18002d1c1  movsxd  r15, eax
0x18002d1c4  lea     r14d, [r15+rbx]
0x18002d1c8  cmp     r14d, r15d
0x18002d1cb  jge     short loc_18002D1DC
0x18002d1cd  mov     ecx, 8007000Eh
0x18002d1d2  mov     r14, [rsp+180h+var_120]
0x18002d1d7  jmp     loc_18002D28A
0x18002d1dc  mov     edx, r14d; ui
0x18002d1df  xor     ecx, ecx; strIn
0x18002d1e1  call    cs:__imp_SysAllocStringLen
0x18002d1e8  nop     dword ptr [rax+rax+00h]
0x18002d1ed  mov     r12, rax
0x18002d1f0  test    rax, rax
0x18002d1f3  jnz     short loc_18002D208
0x18002d1f5  mov     r13d, 8007000Eh
0x18002d1fb  mov     ecx, r13d
0x18002d1fe  mov     r14, [rsp+180h+var_120]
0x18002d203  jmp     loc_18002D290
0x18002d208  mov     rcx, rdi; pbstr
0x18002d20b  call    cs:__imp_SysStringLen
0x18002d212  nop     dword ptr [rax+rax+00h]
0x18002d217  test    eax, eax
0x18002d219  jz      short loc_18002D240
0x18002d21b  mov     r9, r15
0x18002d21e  add     r9, r9; SourceSize
0x18002d221  movsxd  rdx, r14d
0x18002d224  add     rdx, rdx; DestinationSize
0x18002d227  mov     r8, rdi; Source
0x18002d22a  mov     rcx, r12; Destination
0x18002d22d  call    cs:__imp_memcpy_s
0x18002d234  nop     dword ptr [rax+rax+00h]
0x18002d239  mov     ecx, eax; int
0x18002d23b  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002d240  movsxd  rdx, ebx
0x18002d243  add     rdx, rdx; DestinationSize
0x18002d246  lea     rcx, [r12+r15*2]; Destination
0x18002d24a  mov     r9, rdx; SourceSize
0x18002d24d  lea     r8, [rbp+80h+sz]; Source
0x18002d251  call    cs:__imp_memcpy_s
0x18002d258  nop     dword ptr [rax+rax+00h]
0x18002d25d  mov     ecx, eax; int
0x18002d25f  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002d264  movsxd  rcx, r14d
0x18002d267  mov     [r12+rcx*2], r13w
0x18002d26c  mov     rcx, rdi; bstrString
0x18002d26f  call    cs:__imp_SysFreeString
0x18002d276  nop     dword ptr [rax+rax+00h]
0x18002d27b  mov     rdi, r12
0x18002d27e  mov     [rbp+80h+var_D8], r12
0x18002d282  mov     r14, [rsp+180h+var_120]
0x18002d287  mov     ecx, r13d; unsigned int
0x18002d28a  mov     r13d, 8007000Eh
0x18002d290  test    ecx, ecx
0x18002d292  jns     short loc_18002D29A
0x18002d294  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18002d29a  mov     rcx, r14; this
0x18002d29d  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x18002d2a2  mov     r15, rax
0x18002d2a5  mov     [rsp+180h+var_110], rax
0x18002d2aa  test    rax, rax
0x18002d2ad  jz      loc_18002DADE
0x18002d2b3  mov     r12d, 104h
0x18002d2b9  mov     edx, r12d
0x18002d2bc  mov     rcx, rax
0x18002d2bf  nop
0x18002d2c0  cmp     word ptr [rcx], 0
0x18002d2c4  jz      short loc_18002D2D0
0x18002d2c6  add     rcx, 2
0x18002d2ca  sub     rdx, 1
0x18002d2ce  jnz     short loc_18002D2C0
0x18002d2d0  sub     r12, rdx
0x18002d2d3  xor     eax, eax
0x18002d2d5  test    rdx, rdx
0x18002d2d8  cmovz   r12, rax
0x18002d2dc  mov     [rsp+180h+var_108], r12
0x18002d2e1  mov     ebx, 80070057h
0x18002d2e6  cmovnz  ebx, eax
0x18002d2e9  jz      loc_18002DAE3
0x18002d2ef  xor     ecx, ecx; bstrString
0x18002d2f1  call    cs:__imp_SysFreeString
0x18002d2f8  nop     dword ptr [rax+rax+00h]
0x18002d2fd  lea     rcx, aTaskcacheTree_0; "TaskCache\\Tree\\"
0x18002d304  call    cs:__imp_SysAllocString
0x18002d30b  nop     dword ptr [rax+rax+00h]
0x18002d310  mov     rbx, rax
0x18002d313  mov     [rbp+80h+var_100], rax
0x18002d317  test    rax, rax
0x18002d31a  jz      loc_18002DB1E
0x18002d320  mov     eax, 5Ch ; '\'
0x18002d325  cmp     ax, [r15]
0x18002d329  jnz     short loc_18002D338
0x18002d32b  lea     r14, [r15+2]
0x18002d32f  test    r14, r14
0x18002d332  jnz     short loc_18002D340
0x18002d334  xor     esi, esi
0x18002d336  jmp     short loc_18002D34B
0x18002d338  mov     r14, r15
0x18002d33b  nop     dword ptr [rax+rax+00h]
0x18002d340  inc     rsi
0x18002d343  cmp     word ptr [r14+rsi*2], 0
0x18002d349  jnz     short loc_18002D340
0x18002d34b  test    r14, r14
0x18002d34e  jz      loc_18002D451
0x18002d354  test    esi, esi
0x18002d356  jz      loc_18002D451
0x18002d35c  mov     rcx, rbx; pbstr
0x18002d35f  call    cs:__imp_SysStringLen
0x18002d366  nop     dword ptr [rax+rax+00h]
0x18002d36b  movsxd  r12, eax
0x18002d36e  lea     r15d, [r12+rsi]
0x18002d372  cmp     r15d, r12d
0x18002d375  jge     short loc_18002D389
0x18002d377  mov     r15, [rsp+180h+var_110]
0x18002d37c  mov     r12, [rsp+180h+var_108]
0x18002d381  xor     r14d, r14d
0x18002d384  jmp     loc_18002D457
0x18002d389  mov     edx, r15d; ui
0x18002d38c  xor     ecx, ecx; strIn
0x18002d38e  call    cs:__imp_SysAllocStringLen
0x18002d395  nop     dword ptr [rax+rax+00h]
0x18002d39a  mov     r13, rax
0x18002d39d  test    rax, rax
0x18002d3a0  jnz     short loc_18002D3C1
0x18002d3a2  mov     [rsp+180h+var_118], 8007000Eh
0x18002d3aa  mov     r15, [rsp+180h+var_110]
0x18002d3af  mov     r12, [rsp+180h+var_108]
0x18002d3b4  mov     r13d, [rsp+180h+var_118]
0x18002d3b9  xor     r14d, r14d
0x18002d3bc  jmp     loc_18002D457
0x18002d3c1  mov     rcx, rbx; pbstr
0x18002d3c4  call    cs:__imp_SysStringLen
0x18002d3cb  nop     dword ptr [rax+rax+00h]
0x18002d3d0  test    eax, eax
0x18002d3d2  jz      short loc_18002D3F9
0x18002d3d4  mov     r9, r12
0x18002d3d7  add     r9, r9; SourceSize
0x18002d3da  movsxd  rdx, r15d
0x18002d3dd  add     rdx, rdx; DestinationSize
0x18002d3e0  mov     r8, rbx; Source
0x18002d3e3  mov     rcx, r13; Destination
0x18002d3e6  call    cs:__imp_memcpy_s
0x18002d3ed  nop     dword ptr [rax+rax+00h]
0x18002d3f2  mov     ecx, eax; int
0x18002d3f4  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002d3f9  movsxd  rdx, esi
0x18002d3fc  add     rdx, rdx; DestinationSize
0x18002d3ff  lea     rcx, ds:0[r12*2]
0x18002d407  add     rcx, r13; Destination
0x18002d40a  mov     r9, rdx; SourceSize
0x18002d40d  mov     r8, r14; Source
0x18002d410  call    cs:__imp_memcpy_s
0x18002d417  nop     dword ptr [rax+rax+00h]
0x18002d41c  mov     ecx, eax; int
0x18002d41e  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002d423  movsxd  rcx, r15d
0x18002d426  xor     r14d, r14d
0x18002d429  mov     [r13+rcx*2+0], r14w
0x18002d42f  mov     rcx, rbx; bstrString
0x18002d432  call    cs:__imp_SysFreeString
0x18002d439  nop     dword ptr [rax+rax+00h]
0x18002d43e  mov     rbx, r13
0x18002d441  mov     [rbp+80h+var_100], rbx
0x18002d445  mov     r15, [rsp+180h+var_110]
0x18002d44a  mov     r12, [rsp+180h+var_108]
0x18002d44f  jmp     short loc_18002D454
0x18002d451  xor     r14d, r14d
0x18002d454  mov     r13d, r14d
0x18002d457  test    r13d, r13d
0x18002d45a  jns     short loc_18002D465
0x18002d45c  mov     ecx, r13d; unsigned int
0x18002d45f  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18002d465  mov     [rsp+180h+lpdwDisposition], r14; lpdwDisposition
0x18002d46a  lea     rax, [rsp+180h+hKey]
0x18002d46f  mov     [rsp+180h+phkResult], rax; phkResult
0x18002d474  lea     rax, [rbp+80h+SecurityAttributes]
0x18002d478  mov     [rsp+180h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18002d47d  mov     [rsp+180h+samDesired], 0F003Fh; samDesired
0x18002d485  mov     [rsp+180h+dwOptions], r14d; dwOptions
0x18002d48a  xor     r9d, r9d; lpClass
0x18002d48d  xor     r8d, r8d; Reserved
0x18002d490  mov     rdx, rbx; lpSubKey
0x18002d493  mov     r13, [rbp+80h+var_D0]
0x18002d497  mov     rcx, [r13+10h]; hKey
0x18002d49b  call    cs:__imp_RegCreateKeyExW
0x18002d4a2  nop     dword ptr [rax+rax+00h]
0x18002d4a7  mov     esi, eax
0x18002d4a9  test    eax, eax
0x18002d4ab  jz      loc_18002D569
0x18002d4b1  jle     short loc_18002D4BC
0x18002d4b3  movzx   esi, ax
0x18002d4b6  or      esi, 80070000h
0x18002d4bc  lea     rax, WPP_GLOBAL_Control
0x18002d4c3  mov     rdx, cs:WPP_GLOBAL_Control
0x18002d4ca  cmp     rdx, rax
0x18002d4cd  jz      short loc_18002D511
0x18002d4cf  test    dword ptr [rdx+1Ch], 40000h
0x18002d4d6  jz      short loc_18002D511
0x18002d4d8  cmp     byte ptr [rdx+19h], 2
0x18002d4dc  jb      short loc_18002D511
0x18002d4de  mov     rcx, [rsp+180h+var_120]; this
  ... truncated ...
```
