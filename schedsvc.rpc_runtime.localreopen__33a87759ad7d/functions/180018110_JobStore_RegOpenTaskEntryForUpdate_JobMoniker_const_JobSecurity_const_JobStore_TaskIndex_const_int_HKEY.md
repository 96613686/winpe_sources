# JobStore::RegOpenTaskEntryForUpdate(JobMoniker const &,JobSecurity const &,JobStore::TaskIndex const *,int,HKEY__ * *)

- ea: `0x180018110`
- end: `0x180018a14`
- name: `?RegOpenTaskEntryForUpdate@JobStore@@AEBAJAEBVJobMoniker@@AEBVJobSecurity@@PEBW4TaskIndex@1@HPEAPEAUHKEY__@@@Z`
- size: `2308`
- prototype: `__int64 __usercall@<rax>(JobStore *__hidden this@<rcx>, const struct JobMoniker *@<rdx>, const struct JobSecurity *@<r8>, const enum JobStore::TaskIndex *@<r9>, int, HKEY *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180017e70`

## callees

- `0x180017410`
- `0x180018110`
- `0x18001ec90`
- `0x18001fc54`
- `0x180021300`
- `0x18002132c`
- `0x18002643c`
- `0x180049b74`
- `0x18004ba7c`
- `0x1800504b4`
- `0x180053e54`
- `0x180056794`
- `0x18006420c`
- `0x18007e67e`
- `0x18007e68a`
- `0x18007e6d0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800183b0`
- `msvcrt!memcpy_s` at `0x1800183ce`
- `msvcrt!memcpy_s` at `0x1800183b0`
- `msvcrt!memcpy_s` at `0x1800183ce`
- `msvcrt!_wcsicmp` at `0x18001857b`
- `msvcrt!_wcsicmp` at `0x18001857b`
- `OLEAUT32!__imp_SysAllocString` at `0x180018307`
- `OLEAUT32!__imp_SysAllocString` at `0x180018307`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001836e`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001836e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800183e8`
- `OLEAUT32!__imp_SysFreeString` at `0x18001849e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001855b`
- `OLEAUT32!__imp_SysFreeString` at `0x180018593`
- `OLEAUT32!__imp_SysFreeString` at `0x18001874e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001878d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800187b0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800188d8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800189da`
- `OLEAUT32!__imp_SysFreeString` at `0x1800183e8`
- `OLEAUT32!__imp_SysFreeString` at `0x18001849e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001855b`
- `OLEAUT32!__imp_SysFreeString` at `0x180018593`
- `OLEAUT32!__imp_SysFreeString` at `0x18001874e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001878d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800187b0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800188d8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800189da`
- `OLEAUT32!__imp_SysStringLen` at `0x18001818c`
- `OLEAUT32!__imp_SysStringLen` at `0x1800181e7`
- `OLEAUT32!__imp_SysStringLen` at `0x180018345`
- `OLEAUT32!__imp_SysStringLen` at `0x180018394`
- `OLEAUT32!__imp_SysStringLen` at `0x18001818c`
- `OLEAUT32!__imp_SysStringLen` at `0x1800181e7`
- `OLEAUT32!__imp_SysStringLen` at `0x180018345`
- `OLEAUT32!__imp_SysStringLen` at `0x180018394`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001885a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018923`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001885a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018923`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800186d6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800186d6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001842d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018668`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001842d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018668`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800184ef`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800184ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001877b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800189b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800189c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001877b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800189b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800189c8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800182ca`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800182ca`

## string_xrefs

- `0x180018300`: `TaskCache\Tasks\`
- `0x18001862e`: `TaskCache\Boot`
- `0x180018625`: `TaskCache\Logon`
- `0x18001861c`: `TaskCache\Plain`
- `0x180018613`: `TaskCache\Maintenance`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
int __fastcall JobStore::RegOpenTaskEntryForUpdate(
        HKEY *this,
        const struct JobMoniker *a2,
        const struct JobSecurity *a3,
        BYTE *a4,
        int a5,
        HKEY *a6)
{
  HKEY v8; // r15
  BSTR *v9; // rax
  UINT v10; // ecx
  GUID v11; // xmm6
  UINT v12; // eax
  _QWORD *v13; // rax
  __int64 v14; // rbx
  int result; // eax
  const unsigned __int16 *Path; // rax
  OLECHAR *v17; // rbx
  __int64 v18; // rdi
  signed int v19; // eax
  __int64 v20; // r14
  signed int v21; // esi
  signed int v22; // ecx
  BSTR v23; // r15
  errno_t v24; // eax
  errno_t v25; // eax
  LSTATUS v26; // eax
  signed int v27; // edi
  const unsigned __int16 *v28; // rax
  int v29; // edx
  const WCHAR *v30; // r9
  LSTATUS v31; // eax
  unsigned int v32; // r9d
  int v33; // esi
  int i; // ecx
  __int64 v35; // rdx
  signed int IndexEntryP; // eax
  WCHAR *v37; // rdi
  const wchar_t *v38; // rdx
  LSTATUS v39; // eax
  int v40; // edx
  unsigned int v41; // r14d
  _QWORD *v42; // rcx
  int v43; // edx
  LSTATUS v44; // eax
  int v45; // edx
  int v46; // r14d
  HKEY v47; // rdi
  LSTATUS v48; // eax
  unsigned int v49; // esi
  unsigned int v50; // eax
  __int64 v51; // rax
  const BYTE *v52; // rdx
  LSTATUS v53; // eax
  const unsigned __int16 *v54; // rax
  HKEY v55; // rax
  HKEY v56; // rcx
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  __int128 Buf2; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+54h] [rbp-ACh] BYREF
  wchar_t *String1; // [rsp+58h] [rbp-A8h]
  BYTE *lpData; // [rsp+60h] [rbp-A0h]
  _QWORD v64[3]; // [rsp+68h] [rbp-98h] BYREF
  struct _GUID v65; // [rsp+80h] [rbp-80h] BYREF
  GUID rguid; // [rsp+90h] [rbp-70h] BYREF
  OLECHAR sz[40]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t Data[260]; // [rsp+F0h] [rbp-10h] BYREF
  __int16 v69; // [rsp+2F8h] [rbp+1F8h]

  lpData = a4;
  v8 = (HKEY)a6;
  phkResult = (HKEY)a6;
  v64[0] = 24;
  v64[1] = tsched::StoreSecurity::g_pRestrictedKeySecurity;
  v64[2] = 0;
  v9 = (BSTR *)*((_QWORD *)a2 + 2);
  if ( v9 )
  {
    if ( *v9 )
    {
      v10 = SysStringLen(*v9);
      v9 = (BSTR *)*((_QWORD *)a2 + 2);
    }
    else
    {
      v10 = 0;
    }
    if ( v10 )
    {
      if ( v9 )
        String1 = *v9 + 7;
      else
        String1 = (wchar_t *)14;
      goto LABEL_11;
    }
  }
  else
  {
    v9 = 0;
  }
  String1 = 0;
LABEL_11:
  rguid = 0;
  v11 = *(GUID *)a2;
  Buf2 = *(_OWORD *)a2;
  if ( v9 && (!*v9 ? (v12 = 0) : (v12 = SysStringLen(*v9)), v12) )
  {
    v13 = (_QWORD *)*((_QWORD *)a2 + 2);
    if ( v13 )
      v14 = *v13 + 14LL;
    else
      v14 = 14;
  }
  else
  {
    v14 = 0;
  }
  v65 = 0;
  if ( !memcmp_0(&GUID_NULL, &Buf2, 0x10u) )
  {
    result = JobStore::RegGetTreeInfo((JobStore *)this, (const unsigned __int16 *)v14, &v65, 0);
    if ( result < 0 )
      return result;
    if ( !memcmp_0(&GUID_NULL, &Buf2, 0x10u) )
    {
      v11 = v65;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        Path = JobMoniker::GetPath(a2);
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids, Path);
      }
    }
    else if ( memcmp_0(&Buf2, &v65, 0x10u) )
    {
      return -2147216621;
    }
  }
  rguid = v11;
  if ( !StringFromGUID2(&rguid, sz, 40) )
    return -2147024774;
  v17 = SysAllocString(L"TaskCache\\Tasks\\");
  *(_QWORD *)&v65.Data1 = v17;
  if ( !v17 )
    ATL::PrivateAtlThrow(0x8007000E);
  v18 = -1;
  do
    ++v18;
  while ( sz[v18] );
  if ( !(_DWORD)v18 )
    goto LABEL_43;
  v19 = SysStringLen(v17);
  v20 = v19;
  v21 = v19 + v18;
  if ( v19 + (int)v18 >= v19 )
  {
    v23 = SysAllocStringLen(0, v21);
    if ( !v23 )
    {
      v22 = -2147024882;
      v8 = phkResult;
      goto LABEL_44;
    }
    if ( SysStringLen(v17) )
    {
      v24 = memcpy_s(v23, 2LL * v21, v17, 2 * v20);
      ATL::AtlCrtErrorCheck(v24);
    }
    v25 = memcpy_s(&v23[v20], 2LL * (int)v18, sz, 2LL * (int)v18);
    ATL::AtlCrtErrorCheck(v25);
    v23[v21] = 0;
    SysFreeString(v17);
    v17 = v23;
    *(_QWORD *)&v65.Data1 = v23;
    v8 = phkResult;
LABEL_43:
    v22 = 0;
    goto LABEL_44;
  }
  v22 = -2147024882;
LABEL_44:
  if ( v22 < 0 )
    ATL::PrivateAtlThrow(v22);
  hKey = 0;
  v26 = RegOpenKeyExW(this[2], v17, 0, 0xF003Fu, &hKey);
  v27 = v26;
  if ( v26 )
  {
    if ( v26 > 0 )
      v27 = (unsigned __int16)v26 | 0x80070000;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_54;
    }
    v28 = JobMoniker::GetPath(a2);
    v29 = 46;
    LODWORD(v30) = (_DWORD)v17;
    goto LABEL_53;
  }
  Type = 0;
  memset_0(Data, 0, 0x20Au);
  cbData = 522;
  v31 = RegQueryValueExW(hKey, L"Path", 0, &Type, (LPBYTE)Data, &cbData);
  v27 = v31;
  if ( v31 )
  {
    if ( v31 > 0 )
      v27 = (unsigned __int16)v31 | 0x80070000;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_54;
    }
    v28 = JobMoniker::GetPath(a2);
    v29 = 47;
    v30 = L"Path";
LABEL_53:
    WPP_SF_SSD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v29,
      (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
      (_DWORD)v30,
      (__int64)v28,
      v27);
    goto LABEL_54;
  }
  if ( Type != 1 )
  {
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
    SysFreeString(v17);
    return -2147352571;
  }
  v69 = 0;
  if ( _wcsicmp(String1, Data) )
  {
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
    SysFreeString(v17);
    return -2147418113;
  }
  v33 = 1;
LABEL_67:
  if ( v33 >= 5 )
  {
    phkResult = 0;
    v46 = (int)String1;
    v27 = JobStore::RegTreeEntryOpen((JobStore *)this, String1, &phkResult, v32);
    if ( v27 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          48,
          (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
          v46,
          v27);
      }
      wmi::AutoRegKey::Close((wmi::AutoRegKey *)&phkResult);
      goto LABEL_54;
    }
    v47 = phkResult;
    v48 = RegSetValueExW(phkResult, L"Index", 0, 4u, lpData, 4u);
    v49 = v48;
    if ( v48 )
    {
      if ( v48 > 0 )
        v49 = (unsigned __int16)v48 | 0x80070000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v50 = (unsigned int)JobMoniker::GetPath(a2);
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          49,
          (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
          v50,
          v49);
      }
    }
    else
    {
      v51 = *((_QWORD *)a2 + 4);
      v52 = (const BYTE *)(v51 + 28);
      if ( !*(_DWORD *)(v51 + 60) )
        v52 = 0;
      if ( !v52 || (v53 = RegSetValueExW(hKey, L"Hash", 0, 3u, v52, 0x20u), (v49 = v53) == 0) )
      {
        v55 = hKey;
        v56 = 0;
        hKey = 0;
        *(_QWORD *)v8 = v55;
        if ( v47 )
        {
          RegCloseKey(v47);
          v56 = hKey;
        }
        if ( v56 )
        {
          RegCloseKey(v56);
          hKey = 0;
        }
        SysFreeString(v17);
        return 0;
      }
      if ( v53 > 0 )
        v49 = (unsigned __int16)v53 | 0x80070000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v54 = JobMoniker::GetPath(a2);
        WPP_SF_SSD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          50,
          (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
          (unsigned int)L"Hash",
          (__int64)v54,
          v49);
      }
    }
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&phkResult);
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
    SysFreeString(v17);
    return v49;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= a5 )
    {
      v37 = 0;
      *(_QWORD *)&Buf2 = 0;
      switch ( v33 )
      {
        case 1:
          v38 = L"TaskCache\\Boot";
          break;
        case 2:
          v38 = L"TaskCache\\Logon";
          break;
        case 3:
          v38 = L"TaskCache\\Plain";
          break;
        case 4:
          v38 = L"TaskCache\\Maintenance";
          break;
        default:
          goto LABEL_85;
      }
      ATL::CComBSTR::operator=(&Buf2, v38);
      v37 = (WCHAR *)Buf2;
LABEL_85:
      phkResult = 0;
      v39 = RegOpenKeyExW(this[2], v37, 0, 0x20019u, &phkResult);
      v41 = v39;
      if ( v39 )
      {
        if ( v39 > 0 )
          v41 = (unsigned __int16)v39 | 0x80070000;
        if ( !tsched::IsErrorNotFound((tsched *)v41, v40) )
        {
          v42 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v43 = 61;
LABEL_101:
            WPP_SF_Sd(v42[2], v43, (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids, (unsigned int)sz, v41);
          }
        }
      }
      else
      {
        v44 = RegDeleteKeyExW(phkResult, sz, 0, 0);
        v41 = v44;
        if ( !v44 )
        {
          if ( phkResult )
          {
            RegCloseKey(phkResult);
            phkResult = 0;
          }
          SysFreeString(v37);
          v41 = 0;
LABEL_109:
          if ( (v41 & 0x80000000) != 0 )
          {
            wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
            SysFreeString(v17);
            return v41;
          }
LABEL_110:
          ++v33;
          goto LABEL_67;
        }
        if ( v44 > 0 )
          v41 = (unsigned __int16)v44 | 0x80070000;
        if ( !tsched::IsErrorNotFound((tsched *)v41, v45) )
        {
          v42 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v43 = 62;
            goto LABEL_101;
          }
        }
      }
      wmi::AutoRegKey::Close((wmi::AutoRegKey *)&phkResult);
      SysFreeString(v37);
      if ( v41 == -2147023728 || v41 == -2147024893 || v41 == -2147024894 )
        goto LABEL_110;
      goto LABEL_109;
    }
    v35 = *(unsigned int *)&lpData[4 * i];
    if ( (_DWORD)v35 == v33 )
      break;
  }
  IndexEntryP = JobStore::CreateIndexEntryP(this, v35, sz, v64);
  v27 = 0;
  if ( IndexEntryP != -2147024713 )
    v27 = IndexEntryP;
  if ( v27 >= 0 )
    goto LABEL_110;
LABEL_54:
  wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
  SysFreeString(v17);
  return v27;
}

```

## disassembly

```asm
0x180018110  mov     [rsp-8+arg_10], rbx
0x180018115  push    rbp
0x180018116  push    rsi
0x180018117  push    rdi
0x180018118  push    r12
0x18001811a  push    r13
0x18001811c  push    r14
0x18001811e  push    r15
0x180018120  lea     rbp, [rsp-220h]
0x180018128  sub     rsp, 320h
0x18001812f  movaps  [rsp+350h+var_40], xmm6
0x180018137  mov     rax, cs:__security_cookie
0x18001813e  xor     rax, rsp
0x180018141  mov     [rbp+250h+var_50], rax
0x180018148  mov     [rsp+350h+lpData], r9
0x18001814d  mov     r13, rdx
0x180018150  mov     r12, rcx
0x180018153  mov     r15, [rbp+250h+arg_28]
0x18001815a  mov     [rsp+350h+var_318], r15
0x18001815f  mov     [rsp+350h+var_2E8], 18h
0x180018168  mov     rax, cs:?g_pRestrictedKeySecurity@StoreSecurity@tsched@@3PEAXEA; void * tsched::StoreSecurity::g_pRestrictedKeySecurity
0x18001816f  mov     [rsp+350h+var_2E0], rax
0x180018174  xor     esi, esi
0x180018176  mov     [rsp+350h+var_2D8], rsi
0x18001817b  mov     rax, [rdx+10h]
0x18001817f  test    rax, rax
0x180018182  jz      short loc_1800181C1
0x180018184  mov     rcx, [rax]; pbstr
0x180018187  test    rcx, rcx
0x18001818a  jz      short loc_18001819A
0x18001818c  call    cs:__imp_SysStringLen
0x180018192  mov     ecx, eax
0x180018194  mov     rax, [r13+10h]
0x180018198  jmp     short loc_18001819C
0x18001819a  mov     ecx, esi
0x18001819c  test    ecx, ecx
0x18001819e  jz      short loc_1800181C4
0x1800181a0  test    rax, rax
0x1800181a3  jz      short loc_1800181B3
0x1800181a5  mov     rcx, [rax]
0x1800181a8  add     rcx, 0Eh
0x1800181ac  mov     [rsp+350h+String1], rcx
0x1800181b1  jmp     short loc_1800181C9
0x1800181b3  mov     rcx, rsi
0x1800181b6  add     rcx, 0Eh
0x1800181ba  mov     [rsp+350h+String1], rcx
0x1800181bf  jmp     short loc_1800181C9
0x1800181c1  mov     rax, rsi
0x1800181c4  mov     [rsp+350h+String1], rsi
0x1800181c9  xorps   xmm0, xmm0
0x1800181cc  movups  xmmword ptr [rbp+250h+rguid.Data1], xmm0
0x1800181d0  movups  xmm6, xmmword ptr [r13+0]
0x1800181d5  movaps  [rsp+350h+Buf2], xmm6
0x1800181da  test    rax, rax
0x1800181dd  jz      short loc_180018210
0x1800181df  mov     rcx, [rax]; pbstr
0x1800181e2  test    rcx, rcx
0x1800181e5  jz      short loc_1800181EF
0x1800181e7  call    cs:__imp_SysStringLen
0x1800181ed  jmp     short loc_1800181F1
0x1800181ef  mov     eax, esi
0x1800181f1  test    eax, eax
0x1800181f3  jz      short loc_180018210
0x1800181f5  mov     rax, [r13+10h]
0x1800181f9  test    rax, rax
0x1800181fc  jz      short loc_180018207
0x1800181fe  mov     rcx, [rax]
0x180018201  lea     rbx, [rcx+0Eh]
0x180018205  jmp     short loc_180018213
0x180018207  mov     rcx, rsi
0x18001820a  lea     rbx, [rcx+0Eh]
0x18001820e  jmp     short loc_180018213
0x180018210  mov     rbx, rsi
0x180018213  xorps   xmm0, xmm0
0x180018216  movups  xmmword ptr [rbp+250h+var_2D0.Data1], xmm0
0x18001821a  mov     r8d, 10h; Size
0x180018220  lea     rdx, [rsp+350h+Buf2]; Buf2
0x180018225  lea     rcx, GUID_NULL; Buf1
0x18001822c  call    memcmp_0
0x180018231  lea     r14, WPP_GLOBAL_Control
0x180018238  test    eax, eax
0x18001823a  jnz     short loc_1800182B7
0x18001823c  xor     r9d, r9d; enum JobStore::TaskIndex *
0x18001823f  lea     r8, [rbp+250h+var_2D0]; struct _GUID *
0x180018243  mov     rdx, rbx; unsigned __int16 *
0x180018246  mov     rcx, r12; this
0x180018249  call    ?RegGetTreeInfo@JobStore@@QEBAJPEBGPEAU_GUID@@PEAW4TaskIndex@1@@Z; JobStore::RegGetTreeInfo(ushort const *,_GUID *,JobStore::TaskIndex *)
0x18001824e  test    eax, eax
0x180018250  js      loc_1800189E2
0x180018256  mov     r8d, 10h; Size
0x18001825c  lea     rdx, [rsp+350h+Buf2]; Buf2
0x180018261  lea     rcx, GUID_NULL; Buf1
0x180018268  call    memcmp_0
0x18001826d  test    eax, eax
0x18001826f  jnz     short loc_1800182DE
0x180018271  movaps  xmm6, xmmword ptr [rbp+250h+var_2D0.Data1]
0x180018275  mov     rax, cs:WPP_GLOBAL_Control
0x18001827c  cmp     rax, r14
0x18001827f  jz      short loc_1800182B7
0x180018281  test    dword ptr [rax+1Ch], 40000h
0x180018288  jz      short loc_1800182B7
0x18001828a  cmp     byte ptr [rax+19h], 3
0x18001828e  jb      short loc_1800182B7
0x180018290  mov     rcx, r13; this
0x180018293  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x180018298  mov     edx, 51h ; 'Q'
0x18001829d  mov     r9, rax
0x1800182a0  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x1800182a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800182ae  mov     rcx, [rcx+10h]
0x1800182b2  call    WPP_SF_S
0x1800182b7  movdqa  xmmword ptr [rbp+250h+rguid.Data1], xmm6
0x1800182bc  mov     r8d, 28h ; '('; cchMax
0x1800182c2  lea     rdx, [rbp+250h+sz]; lpsz
0x1800182c6  lea     rcx, [rbp+250h+rguid]; rguid
0x1800182ca  call    cs:__imp_StringFromGUID2
0x1800182d0  test    eax, eax
0x1800182d2  jnz     short loc_180018300
0x1800182d4  mov     eax, 8007007Ah
0x1800182d9  jmp     loc_1800189E2
0x1800182de  mov     r8d, 10h; Size
0x1800182e4  lea     rdx, [rbp+250h+var_2D0]; Buf2
0x1800182e8  lea     rcx, [rsp+350h+Buf2]; Buf1
0x1800182ed  call    memcmp_0
0x1800182f2  test    eax, eax
0x1800182f4  jz      short loc_1800182B7
0x1800182f6  mov     eax, 80041313h
0x1800182fb  jmp     loc_1800189E2
0x180018300  lea     rcx, aTaskcacheTasks; "TaskCache\\Tasks\\"
0x180018307  call    cs:__imp_SysAllocString
0x18001830d  mov     rbx, rax
0x180018310  mov     qword ptr [rbp+250h+var_2D0.Data1], rax
0x180018314  test    rax, rax
0x180018317  jnz     short loc_180018324
0x180018319  mov     ecx, 8007000Eh; unsigned int
0x18001831e  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x180018324  lea     rax, [rbp+250h+sz]
0x180018328  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18001832f  nop
0x180018330  inc     rdi
0x180018333  cmp     word ptr [rax+rdi*2], 0
0x180018338  jnz     short loc_180018330
0x18001833a  test    edi, edi
0x18001833c  jz      loc_180018401
0x180018342  mov     rcx, rbx; pbstr
0x180018345  call    cs:__imp_SysStringLen
0x18001834b  movsxd  r14, eax
0x18001834e  lea     esi, [r14+rdi]
0x180018352  cmp     esi, r14d
0x180018355  jge     short loc_18001836A
0x180018357  mov     ecx, 8007000Eh
0x18001835c  xor     esi, esi
0x18001835e  lea     r14, WPP_GLOBAL_Control
0x180018365  jmp     loc_180018403
0x18001836a  mov     edx, esi; ui
0x18001836c  xor     ecx, ecx; strIn
0x18001836e  call    cs:__imp_SysAllocStringLen
0x180018374  mov     r15, rax
0x180018377  test    rax, rax
0x18001837a  jnz     short loc_180018391
0x18001837c  mov     ecx, 8007000Eh
0x180018381  mov     r15, [rsp+350h+var_318]
0x180018386  xor     esi, esi
0x180018388  lea     r14, WPP_GLOBAL_Control
0x18001838f  jmp     short loc_180018403
0x180018391  mov     rcx, rbx; pbstr
0x180018394  call    cs:__imp_SysStringLen
0x18001839a  test    eax, eax
0x18001839c  jz      short loc_1800183BD
0x18001839e  mov     r9, r14
0x1800183a1  add     r9, r9; SourceSize
0x1800183a4  movsxd  rdx, esi
0x1800183a7  add     rdx, rdx; DestinationSize
0x1800183aa  mov     r8, rbx; Source
0x1800183ad  mov     rcx, r15; Destination
0x1800183b0  call    cs:__imp_memcpy_s
0x1800183b6  mov     ecx, eax; int
0x1800183b8  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800183bd  movsxd  rdx, edi
0x1800183c0  add     rdx, rdx; DestinationSize
0x1800183c3  lea     rcx, [r15+r14*2]; Destination
0x1800183c7  mov     r9, rdx; SourceSize
0x1800183ca  lea     r8, [rbp+250h+sz]; Source
0x1800183ce  call    cs:__imp_memcpy_s
0x1800183d4  mov     ecx, eax; int
0x1800183d6  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800183db  movsxd  rcx, esi
0x1800183de  xor     esi, esi
0x1800183e0  mov     [r15+rcx*2], si
0x1800183e5  mov     rcx, rbx; bstrString
0x1800183e8  call    cs:__imp_SysFreeString
0x1800183ee  mov     rbx, r15
0x1800183f1  mov     qword ptr [rbp+250h+var_2D0.Data1], rbx
0x1800183f5  mov     r15, [rsp+350h+var_318]
0x1800183fa  lea     r14, WPP_GLOBAL_Control
0x180018401  mov     ecx, esi; unsigned int
0x180018403  test    ecx, ecx
0x180018405  jns     short loc_18001840D
0x180018407  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18001840d  mov     [rsp+350h+hKey], rsi
0x180018412  lea     rax, [rsp+350h+hKey]
0x180018417  mov     [rsp+350h+phkResult], rax; phkResult
0x18001841c  mov     r9d, 0F003Fh; samDesired
0x180018422  xor     r8d, r8d; ulOptions
0x180018425  mov     rdx, rbx; lpSubKey
0x180018428  mov     rcx, [r12+10h]; hKey
0x18001842d  call    cs:__imp_RegOpenKeyExW
0x180018433  mov     edi, eax
0x180018435  test    eax, eax
0x180018437  jz      short loc_1800184AB
0x180018439  jle     short loc_180018444
0x18001843b  movzx   edi, ax
0x18001843e  or      edi, 80070000h
0x180018444  mov     rax, cs:WPP_GLOBAL_Control
0x18001844b  cmp     rax, r14
0x18001844e  jz      short loc_180018490
0x180018450  test    dword ptr [rax+1Ch], 40000h
0x180018457  jz      short loc_180018490
0x180018459  cmp     byte ptr [rax+19h], 2
0x18001845d  jb      short loc_180018490
0x18001845f  mov     rcx, r13; this
0x180018462  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x180018467  mov     edx, 2Eh ; '.'
0x18001846c  mov     r9, rbx
0x18001846f  mov     dword ptr [rsp+350h+lpcbData], edi
0x180018473  mov     [rsp+350h+phkResult], rax
0x180018478  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x18001847f  mov     rcx, cs:WPP_GLOBAL_Control
0x180018486  mov     rcx, [rcx+10h]
0x18001848a  call    WPP_SF_SSD
0x18001848f  nop
0x180018490  lea     rcx, [rsp+350h+hKey]; this
0x180018495  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18001849a  nop
0x18001849b  mov     rcx, rbx; bstrString
0x18001849e  call    cs:__imp_SysFreeString
0x1800184a4  mov     eax, edi
0x1800184a6  jmp     loc_1800189E2
0x1800184ab  mov     [rsp+350h+Type], esi
0x1800184af  xor     edx, edx; Val
0x1800184b1  mov     r8d, 20Ah; Size
0x1800184b7  lea     rcx, [rbp+250h+Data]; void *
0x1800184bb  call    memset_0
0x1800184c0  mov     [rsp+350h+cbData], 20Ah
0x1800184c8  lea     rax, [rsp+350h+cbData]
0x1800184cd  mov     [rsp+350h+lpcbData], rax; lpcbData
0x1800184d2  lea     rax, [rbp+250h+Data]
0x1800184d6  mov     [rsp+350h+phkResult], rax; lpData
0x1800184db  lea     r9, [rsp+350h+Type]; lpType
0x1800184e0  xor     r8d, r8d; lpReserved
0x1800184e3  lea     rdx, aPath; "Path"
0x1800184ea  mov     rcx, [rsp+350h+hKey]; hKey
0x1800184ef  call    cs:__imp_RegQueryValueExW
0x1800184f5  mov     edi, eax
0x1800184f7  test    eax, eax
0x1800184f9  jz      short loc_180018546
0x1800184fb  jle     short loc_180018506
0x1800184fd  movzx   edi, ax
0x180018500  or      edi, 80070000h
0x180018506  mov     rax, cs:WPP_GLOBAL_Control
0x18001850d  cmp     rax, r14
0x180018510  jz      loc_180018490
0x180018516  test    dword ptr [rax+1Ch], 40000h
0x18001851d  jz      loc_180018490
0x180018523  cmp     byte ptr [rax+19h], 2
0x180018527  jb      loc_180018490
0x18001852d  mov     rcx, r13; this
0x180018530  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x180018535  mov     edx, 2Fh ; '/'
0x18001853a  lea     r9, aPath; "Path"
0x180018541  jmp     loc_18001846F
0x180018546  cmp     [rsp+350h+Type], 1
0x18001854b  jz      short loc_18001856B
0x18001854d  lea     rcx, [rsp+350h+hKey]; this
0x180018552  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180018557  nop
0x180018558  mov     rcx, rbx; bstrString
0x18001855b  call    cs:__imp_SysFreeString
0x180018561  mov     eax, 80020005h
0x180018566  jmp     loc_1800189E2
0x18001856b  mov     [rbp+250h+var_58], si
0x180018572  lea     rdx, [rbp+250h+Data]; String2
0x180018576  mov     rcx, [rsp+350h+String1]; String1
0x18001857b  call    cs:__imp__wcsicmp
0x180018581  test    eax, eax
0x180018583  jz      short loc_1800185A3
0x180018585  lea     rcx, [rsp+350h+hKey]; this
0x18001858a  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18001858f  nop
0x180018590  mov     rcx, rbx; bstrString
0x180018593  call    cs:__imp_SysFreeString
0x180018599  mov     eax, 8000FFFFh
0x18001859e  jmp     loc_1800189E2
0x1800185a3  mov     esi, 1
0x1800185a8  cmp     esi, 5
0x1800185ab  jge     loc_1800187BE
0x1800185b1  xor     ecx, ecx
0x1800185b3  cmp     ecx, [rbp+250h+arg_20]
0x1800185b9  jge     short loc_1800185F6
0x1800185bb  movsxd  rax, ecx
  ... truncated ...
```
