# JobStore::RegOpenTaskEntryForUpdate(JobMoniker const &,JobSecurity const &,JobStore::TaskIndex const *,int,HKEY__ * *)

- ea: `0x180031cf0`
- end: `0x1800324e5`
- name: `?RegOpenTaskEntryForUpdate@JobStore@@AEBAJAEBVJobMoniker@@AEBVJobSecurity@@PEBW4TaskIndex@1@HPEAPEAUHKEY__@@@Z`
- size: `2037`
- prototype: `__int64 __usercall@<rax>(JobStore *__hidden this@<rcx>, const struct JobMoniker *@<rdx>, const struct JobSecurity *@<r8>, const enum JobStore::TaskIndex *@<r9>, int, HKEY *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180031a40`

## callees

- `0x18002b210`
- `0x18002c2f4`
- `0x18002db40`
- `0x18002db74`
- `0x180031cf0`
- `0x180033700`
- `0x180033f20`
- `0x18004df30`
- `0x1800529a0`
- `0x180056714`
- `0x180059140`
- `0x180067290`
- `0x1800829ee`
- `0x1800829fa`
- `0x180082a40`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180031fc1`
- `msvcrt!memcpy_s` at `0x180031fe5`
- `msvcrt!memcpy_s` at `0x180031fc1`
- `msvcrt!memcpy_s` at `0x180031fe5`
- `msvcrt!_wcsicmp` at `0x1800321c2`
- `msvcrt!_wcsicmp` at `0x1800321c2`
- `OLEAUT32!__imp_SysAllocString` at `0x180031efb`
- `OLEAUT32!__imp_SysAllocString` at `0x180031efb`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180031f72`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180031f72`
- `OLEAUT32!__imp_SysFreeString` at `0x180032005`
- `OLEAUT32!__imp_SysFreeString` at `0x1800320cc`
- `OLEAUT32!__imp_SysFreeString` at `0x18003219c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800321e0`
- `OLEAUT32!__imp_SysFreeString` at `0x18003238a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800324a4`
- `OLEAUT32!__imp_SysFreeString` at `0x180032005`
- `OLEAUT32!__imp_SysFreeString` at `0x1800320cc`
- `OLEAUT32!__imp_SysFreeString` at `0x18003219c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800321e0`
- `OLEAUT32!__imp_SysFreeString` at `0x18003238a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800324a4`
- `OLEAUT32!__imp_SysStringLen` at `0x180031d6e`
- `OLEAUT32!__imp_SysStringLen` at `0x180031dcf`
- `OLEAUT32!__imp_SysStringLen` at `0x180031f45`
- `OLEAUT32!__imp_SysStringLen` at `0x180031f9f`
- `OLEAUT32!__imp_SysStringLen` at `0x180031d6e`
- `OLEAUT32!__imp_SysStringLen` at `0x180031dcf`
- `OLEAUT32!__imp_SysStringLen` at `0x180031f45`
- `OLEAUT32!__imp_SysStringLen` at `0x180031f9f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032302`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800323db`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032302`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800323db`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003204e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003204e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180032123`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180032123`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032476`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003248c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032476`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003248c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180031eb8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180031eb8`

## string_xrefs

- `0x180031ef4`: `TaskCache\Tasks\`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
int __fastcall JobStore::RegOpenTaskEntryForUpdate(
        HKEY *this,
        const struct JobMoniker *a2,
        const struct JobSecurity *a3,
        const BYTE *a4,
        int a5,
        HKEY *a6)
{
  const BYTE *v6; // r15
  HKEY v9; // r14
  BSTR *v10; // rax
  UINT v11; // ecx
  GUID v12; // xmm6
  UINT v13; // eax
  _QWORD *v14; // rax
  __int64 v15; // rbx
  int result; // eax
  const unsigned __int16 *Path; // rax
  OLECHAR *v18; // rbx
  __int64 v19; // rdi
  signed int v20; // eax
  __int64 v21; // r14
  signed int v22; // esi
  signed int v23; // ecx
  BSTR v24; // r15
  errno_t v25; // eax
  errno_t v26; // eax
  LSTATUS v27; // eax
  unsigned int v28; // edi
  const unsigned __int16 *v29; // rax
  int v30; // edx
  const WCHAR *v31; // r9
  LSTATUS v32; // eax
  unsigned int v33; // r9d
  int v34; // edi
  int i; // ecx
  __int64 v36; // rdx
  signed int IndexEntryP; // eax
  signed int v38; // esi
  int v39; // eax
  int v40; // esi
  int v41; // eax
  HKEY v42; // rdi
  LSTATUS v43; // eax
  unsigned int v44; // eax
  __int64 v45; // rax
  const BYTE *v46; // rdx
  LSTATUS v47; // eax
  const unsigned __int16 *v48; // rax
  HKEY v49; // rax
  HKEY v50; // rcx
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  HKEY v52; // [rsp+38h] [rbp-C8h] BYREF
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  wchar_t *String1; // [rsp+48h] [rbp-B8h]
  const enum JobStore::TaskIndex *v56; // [rsp+50h] [rbp-B0h]
  __int128 Buf2; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v58[4]; // [rsp+70h] [rbp-90h] BYREF
  struct _GUID v59; // [rsp+90h] [rbp-70h] BYREF
  GUID rguid; // [rsp+A0h] [rbp-60h] BYREF
  OLECHAR sz[40]; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t Data[260]; // [rsp+100h] [rbp+0h] BYREF
  __int16 v63; // [rsp+308h] [rbp+208h]

  v6 = a4;
  v56 = (const enum JobStore::TaskIndex *)a4;
  v9 = (HKEY)a6;
  v52 = (HKEY)a6;
  v58[0] = 24;
  v58[1] = tsched::StoreSecurity::g_pRestrictedKeySecurity;
  v58[2] = 0;
  v10 = (BSTR *)*((_QWORD *)a2 + 2);
  if ( v10 )
  {
    if ( *v10 )
    {
      v11 = SysStringLen(*v10);
      v10 = (BSTR *)*((_QWORD *)a2 + 2);
    }
    else
    {
      v11 = 0;
    }
    if ( v11 )
    {
      if ( v10 )
        String1 = *v10 + 7;
      else
        String1 = (wchar_t *)14;
      goto LABEL_11;
    }
  }
  else
  {
    v10 = 0;
  }
  String1 = 0;
LABEL_11:
  rguid = 0;
  v12 = *(GUID *)a2;
  Buf2 = *(_OWORD *)a2;
  if ( v10 && (!*v10 ? (v13 = 0) : (v13 = SysStringLen(*v10)), v13) )
  {
    v14 = (_QWORD *)*((_QWORD *)a2 + 2);
    if ( v14 )
      v15 = *v14 + 14LL;
    else
      v15 = 14;
  }
  else
  {
    v15 = 0;
  }
  v59 = 0;
  if ( !memcmp_0(&GUID_NULL, &Buf2, 0x10u) )
  {
    result = JobStore::RegGetTreeInfo((JobStore *)this, (const unsigned __int16 *)v15, &v59, 0);
    if ( result < 0 )
      return result;
    if ( !memcmp_0(&GUID_NULL, &Buf2, 0x10u) )
    {
      v12 = v59;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        Path = JobMoniker::GetPath(a2);
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids, Path);
      }
    }
    else if ( memcmp_0(&Buf2, &v59, 0x10u) )
    {
      return -2147216621;
    }
  }
  rguid = v12;
  if ( !StringFromGUID2(&rguid, sz, 40) )
    return -2147024774;
  v18 = SysAllocString(L"TaskCache\\Tasks\\");
  *(_QWORD *)&v59.Data1 = v18;
  if ( !v18 )
    ATL::PrivateAtlThrow(0x8007000E);
  v19 = -1;
  do
    ++v19;
  while ( sz[v19] );
  if ( (_DWORD)v19 )
  {
    v20 = SysStringLen(v18);
    v21 = v20;
    v22 = v20 + v19;
    if ( v20 + (int)v19 < v20 )
    {
      v23 = -2147024882;
      v9 = v52;
      goto LABEL_44;
    }
    v24 = SysAllocStringLen(0, v22);
    if ( !v24 )
    {
      v23 = -2147024882;
      v9 = v52;
      v6 = (const BYTE *)v56;
      goto LABEL_44;
    }
    if ( SysStringLen(v18) )
    {
      v25 = memcpy_s(v24, 2LL * v22, v18, 2 * v21);
      ATL::AtlCrtErrorCheck(v25);
    }
    v26 = memcpy_s(&v24[v21], 2LL * (int)v19, sz, 2LL * (int)v19);
    ATL::AtlCrtErrorCheck(v26);
    v24[v22] = 0;
    SysFreeString(v18);
    v18 = v24;
    *(_QWORD *)&v59.Data1 = v24;
    v9 = v52;
    v6 = (const BYTE *)v56;
  }
  v23 = 0;
LABEL_44:
  if ( v23 < 0 )
    ATL::PrivateAtlThrow(v23);
  hKey = 0;
  v27 = RegOpenKeyExW(this[2], v18, 0, 0xF003Fu, &hKey);
  v28 = v27;
  if ( v27 )
  {
    if ( v27 > 0 )
      v28 = (unsigned __int16)v27 | 0x80070000;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_54;
    }
    v29 = JobMoniker::GetPath(a2);
    v30 = 46;
    LODWORD(v31) = (_DWORD)v18;
LABEL_53:
    WPP_SF_SSD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v30,
      (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
      (_DWORD)v31,
      (__int64)v29,
      v28);
LABEL_54:
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
    SysFreeString(v18);
    return v28;
  }
  Type = 0;
  memset_0(Data, 0, 0x20Au);
  cbData = 522;
  v32 = RegQueryValueExW(hKey, L"Path", 0, &Type, (LPBYTE)Data, &cbData);
  v28 = v32;
  if ( v32 )
  {
    if ( v32 > 0 )
      v28 = (unsigned __int16)v32 | 0x80070000;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_54;
    }
    v29 = JobMoniker::GetPath(a2);
    v30 = 47;
    v31 = L"Path";
    goto LABEL_53;
  }
  if ( Type != 1 )
  {
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
    SysFreeString(v18);
    return -2147352571;
  }
  v63 = 0;
  if ( _wcsicmp(String1, Data) )
  {
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
    SysFreeString(v18);
    return -2147418113;
  }
  v34 = 1;
LABEL_67:
  if ( v34 < 5 )
  {
    for ( i = 0; i < a5; ++i )
    {
      v36 = *(unsigned int *)&v6[4 * i];
      if ( (_DWORD)v36 == v34 )
      {
        IndexEntryP = JobStore::CreateIndexEntryP(this, v36, sz, v58);
        v38 = 0;
        if ( IndexEntryP != -2147024713 )
          v38 = IndexEntryP;
        if ( v38 < 0 )
        {
LABEL_94:
          wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
          SysFreeString(v18);
          return v38;
        }
LABEL_79:
        ++v34;
        goto LABEL_67;
      }
    }
    v39 = JobStore::RemoveIndexEntryP(this, (unsigned int)v34, sz);
    v38 = v39;
    if ( v39 != -2147023728 && (unsigned int)(v39 + 2147024894) > 1 && v39 < 0 )
      goto LABEL_94;
    goto LABEL_79;
  }
  v52 = 0;
  v40 = (int)String1;
  v41 = JobStore::RegTreeEntryOpen((JobStore *)this, String1, &v52, v33);
  v28 = v41;
  if ( v41 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        48,
        (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
        v40,
        v41);
    }
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&v52);
    goto LABEL_54;
  }
  v42 = v52;
  v43 = RegSetValueExW(v52, L"Index", 0, 4u, v6, 4u);
  v38 = v43;
  if ( v43 )
  {
    if ( v43 > 0 )
      v38 = (unsigned __int16)v43 | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v44 = (unsigned int)JobMoniker::GetPath(a2);
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        49,
        (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
        v44,
        v38);
    }
LABEL_93:
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&v52);
    goto LABEL_94;
  }
  v45 = *((_QWORD *)a2 + 4);
  v46 = (const BYTE *)(v45 + 28);
  if ( !*(_DWORD *)(v45 + 60) )
    v46 = 0;
  if ( v46 )
  {
    v47 = RegSetValueExW(hKey, L"Hash", 0, 3u, v46, 0x20u);
    v38 = v47;
    if ( v47 )
    {
      if ( v47 > 0 )
        v38 = (unsigned __int16)v47 | 0x80070000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v48 = JobMoniker::GetPath(a2);
        WPP_SF_SSD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          50,
          (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
          (unsigned int)L"Hash",
          (__int64)v48,
          v38);
      }
      goto LABEL_93;
    }
  }
  v49 = hKey;
  v50 = 0;
  hKey = 0;
  *(_QWORD *)v9 = v49;
  if ( v42 )
  {
    RegCloseKey(v42);
    v50 = hKey;
  }
  if ( v50 )
  {
    RegCloseKey(v50);
    hKey = 0;
  }
  SysFreeString(v18);
  return 0;
}

```

## disassembly

```asm
0x180031cf0  mov     [rsp-8+arg_10], rbx
0x180031cf5  push    rbp
0x180031cf6  push    rsi
0x180031cf7  push    rdi
0x180031cf8  push    r12
0x180031cfa  push    r13
0x180031cfc  push    r14
0x180031cfe  push    r15
0x180031d00  lea     rbp, [rsp-230h]
0x180031d08  sub     rsp, 330h
0x180031d0f  movaps  [rsp+360h+var_40], xmm6
0x180031d17  mov     rax, cs:__security_cookie
0x180031d1e  xor     rax, rsp
0x180031d21  mov     [rbp+260h+var_50], rax
0x180031d28  mov     r15, r9
0x180031d2b  mov     [rsp+360h+var_310], r9
0x180031d30  mov     r13, rdx
0x180031d33  mov     r12, rcx
0x180031d36  mov     r14, [rbp+260h+arg_28]
0x180031d3d  mov     [rsp+360h+var_328], r14
0x180031d42  mov     [rsp+360h+var_2F0], 18h
0x180031d4b  mov     rax, cs:?g_pRestrictedKeySecurity@StoreSecurity@tsched@@3PEAXEA; void * tsched::StoreSecurity::g_pRestrictedKeySecurity
0x180031d52  mov     [rsp+360h+var_2E8], rax
0x180031d57  xor     esi, esi
0x180031d59  mov     [rbp+260h+var_2E0], rsi
0x180031d5d  mov     rax, [rdx+10h]
0x180031d61  test    rax, rax
0x180031d64  jz      short loc_180031DA9
0x180031d66  mov     rcx, [rax]; pbstr
0x180031d69  test    rcx, rcx
0x180031d6c  jz      short loc_180031D82
0x180031d6e  call    cs:__imp_SysStringLen
0x180031d75  nop     dword ptr [rax+rax+00h]
0x180031d7a  mov     ecx, eax
0x180031d7c  mov     rax, [r13+10h]
0x180031d80  jmp     short loc_180031D84
0x180031d82  mov     ecx, esi
0x180031d84  test    ecx, ecx
0x180031d86  jz      short loc_180031DAC
0x180031d88  test    rax, rax
0x180031d8b  jz      short loc_180031D9B
0x180031d8d  mov     rcx, [rax]
0x180031d90  add     rcx, 0Eh
0x180031d94  mov     [rsp+360h+String1], rcx
0x180031d99  jmp     short loc_180031DB1
0x180031d9b  mov     rcx, rsi
0x180031d9e  add     rcx, 0Eh
0x180031da2  mov     [rsp+360h+String1], rcx
0x180031da7  jmp     short loc_180031DB1
0x180031da9  mov     rax, rsi
0x180031dac  mov     [rsp+360h+String1], rsi
0x180031db1  xorps   xmm0, xmm0
0x180031db4  movups  xmmword ptr [rbp+260h+rguid.Data1], xmm0
0x180031db8  movups  xmm6, xmmword ptr [r13+0]
0x180031dbd  movaps  [rsp+360h+Buf2], xmm6
0x180031dc2  test    rax, rax
0x180031dc5  jz      short loc_180031DFE
0x180031dc7  mov     rcx, [rax]; pbstr
0x180031dca  test    rcx, rcx
0x180031dcd  jz      short loc_180031DDD
0x180031dcf  call    cs:__imp_SysStringLen
0x180031dd6  nop     dword ptr [rax+rax+00h]
0x180031ddb  jmp     short loc_180031DDF
0x180031ddd  mov     eax, esi
0x180031ddf  test    eax, eax
0x180031de1  jz      short loc_180031DFE
0x180031de3  mov     rax, [r13+10h]
0x180031de7  test    rax, rax
0x180031dea  jz      short loc_180031DF5
0x180031dec  mov     rcx, [rax]
0x180031def  lea     rbx, [rcx+0Eh]
0x180031df3  jmp     short loc_180031E01
0x180031df5  mov     rcx, rsi
0x180031df8  lea     rbx, [rcx+0Eh]
0x180031dfc  jmp     short loc_180031E01
0x180031dfe  mov     rbx, rsi
0x180031e01  xorps   xmm0, xmm0
0x180031e04  movups  xmmword ptr [rbp+260h+var_2D0.Data1], xmm0
0x180031e08  mov     r8d, 10h; Size
0x180031e0e  lea     rdx, [rsp+360h+Buf2]; Buf2
0x180031e13  lea     rcx, GUID_NULL; Buf1
0x180031e1a  call    memcmp_0
0x180031e1f  lea     rdi, WPP_GLOBAL_Control
0x180031e26  test    eax, eax
0x180031e28  jnz     short loc_180031EA5
0x180031e2a  xor     r9d, r9d; enum JobStore::TaskIndex *
0x180031e2d  lea     r8, [rbp+260h+var_2D0]; struct _GUID *
0x180031e31  mov     rdx, rbx; unsigned __int16 *
0x180031e34  mov     rcx, r12; this
0x180031e37  call    ?RegGetTreeInfo@JobStore@@QEBAJPEBGPEAU_GUID@@PEAW4TaskIndex@1@@Z; JobStore::RegGetTreeInfo(ushort const *,_GUID *,JobStore::TaskIndex *)
0x180031e3c  test    eax, eax
0x180031e3e  js      loc_1800324B2
0x180031e44  mov     r8d, 10h; Size
0x180031e4a  lea     rdx, [rsp+360h+Buf2]; Buf2
0x180031e4f  lea     rcx, GUID_NULL; Buf1
0x180031e56  call    memcmp_0
0x180031e5b  test    eax, eax
0x180031e5d  jnz     short loc_180031ED2
0x180031e5f  movaps  xmm6, xmmword ptr [rbp+260h+var_2D0.Data1]
0x180031e63  mov     rax, cs:WPP_GLOBAL_Control
0x180031e6a  cmp     rax, rdi
0x180031e6d  jz      short loc_180031EA5
0x180031e6f  test    dword ptr [rax+1Ch], 40000h
0x180031e76  jz      short loc_180031EA5
0x180031e78  cmp     byte ptr [rax+19h], 3
0x180031e7c  jb      short loc_180031EA5
0x180031e7e  mov     rcx, r13; this
0x180031e81  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x180031e86  mov     edx, 51h ; 'Q'
0x180031e8b  mov     r9, rax
0x180031e8e  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x180031e95  mov     rcx, cs:WPP_GLOBAL_Control
0x180031e9c  mov     rcx, [rcx+10h]
0x180031ea0  call    WPP_SF_S
0x180031ea5  movdqa  xmmword ptr [rbp+260h+rguid.Data1], xmm6
0x180031eaa  mov     r8d, 28h ; '('; cchMax
0x180031eb0  lea     rdx, [rbp+260h+sz]; lpsz
0x180031eb4  lea     rcx, [rbp+260h+rguid]; rguid
0x180031eb8  call    cs:__imp_StringFromGUID2
0x180031ebf  nop     dword ptr [rax+rax+00h]
0x180031ec4  test    eax, eax
0x180031ec6  jnz     short loc_180031EF4
0x180031ec8  mov     eax, 8007007Ah
0x180031ecd  jmp     loc_1800324B2
0x180031ed2  mov     r8d, 10h; Size
0x180031ed8  lea     rdx, [rbp+260h+var_2D0]; Buf2
0x180031edc  lea     rcx, [rsp+360h+Buf2]; Buf1
0x180031ee1  call    memcmp_0
0x180031ee6  test    eax, eax
0x180031ee8  jz      short loc_180031EA5
0x180031eea  mov     eax, 80041313h
0x180031eef  jmp     loc_1800324B2
0x180031ef4  lea     rcx, aTaskcacheTasks; "TaskCache\\Tasks\\"
0x180031efb  call    cs:__imp_SysAllocString
0x180031f02  nop     dword ptr [rax+rax+00h]
0x180031f07  mov     rbx, rax
0x180031f0a  mov     qword ptr [rbp+260h+var_2D0.Data1], rax
0x180031f0e  test    rax, rax
0x180031f11  jnz     short loc_180031F1E
0x180031f13  mov     ecx, 8007000Eh; unsigned int
0x180031f18  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x180031f1e  lea     rax, [rbp+260h+sz]
0x180031f22  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180031f29  nop     dword ptr [rax+00000000h]
0x180031f30  inc     rdi
0x180031f33  cmp     word ptr [rax+rdi*2], 0
0x180031f38  jnz     short loc_180031F30
0x180031f3a  test    edi, edi
0x180031f3c  jz      loc_180032022
0x180031f42  mov     rcx, rbx; pbstr
0x180031f45  call    cs:__imp_SysStringLen
0x180031f4c  nop     dword ptr [rax+rax+00h]
0x180031f51  movsxd  r14, eax
0x180031f54  lea     esi, [r14+rdi]
0x180031f58  cmp     esi, r14d
0x180031f5b  jge     short loc_180031F6E
0x180031f5d  mov     ecx, 8007000Eh
0x180031f62  mov     r14, [rsp+360h+var_328]
0x180031f67  xor     esi, esi
0x180031f69  jmp     loc_180032024
0x180031f6e  mov     edx, esi; ui
0x180031f70  xor     ecx, ecx; strIn
0x180031f72  call    cs:__imp_SysAllocStringLen
0x180031f79  nop     dword ptr [rax+rax+00h]
0x180031f7e  mov     r15, rax
0x180031f81  test    rax, rax
0x180031f84  jnz     short loc_180031F9C
0x180031f86  mov     ecx, 8007000Eh
0x180031f8b  mov     r14, [rsp+360h+var_328]
0x180031f90  mov     r15, [rsp+360h+var_310]
0x180031f95  xor     esi, esi
0x180031f97  jmp     loc_180032024
0x180031f9c  mov     rcx, rbx; pbstr
0x180031f9f  call    cs:__imp_SysStringLen
0x180031fa6  nop     dword ptr [rax+rax+00h]
0x180031fab  test    eax, eax
0x180031fad  jz      short loc_180031FD4
0x180031faf  mov     r9, r14
0x180031fb2  add     r9, r9; SourceSize
0x180031fb5  movsxd  rdx, esi
0x180031fb8  add     rdx, rdx; DestinationSize
0x180031fbb  mov     r8, rbx; Source
0x180031fbe  mov     rcx, r15; Destination
0x180031fc1  call    cs:__imp_memcpy_s
0x180031fc8  nop     dword ptr [rax+rax+00h]
0x180031fcd  mov     ecx, eax; int
0x180031fcf  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180031fd4  movsxd  rdx, edi
0x180031fd7  add     rdx, rdx; DestinationSize
0x180031fda  lea     rcx, [r15+r14*2]; Destination
0x180031fde  mov     r9, rdx; SourceSize
0x180031fe1  lea     r8, [rbp+260h+sz]; Source
0x180031fe5  call    cs:__imp_memcpy_s
0x180031fec  nop     dword ptr [rax+rax+00h]
0x180031ff1  mov     ecx, eax; int
0x180031ff3  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180031ff8  movsxd  rcx, esi
0x180031ffb  xor     esi, esi
0x180031ffd  mov     [r15+rcx*2], si
0x180032002  mov     rcx, rbx; bstrString
0x180032005  call    cs:__imp_SysFreeString
0x18003200c  nop     dword ptr [rax+rax+00h]
0x180032011  mov     rbx, r15
0x180032014  mov     qword ptr [rbp+260h+var_2D0.Data1], rbx
0x180032018  mov     r14, [rsp+360h+var_328]
0x18003201d  mov     r15, [rsp+360h+var_310]
0x180032022  mov     ecx, esi; unsigned int
0x180032024  test    ecx, ecx
0x180032026  jns     short loc_18003202E
0x180032028  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18003202e  mov     [rsp+360h+hKey], rsi
0x180032033  lea     rax, [rsp+360h+hKey]
0x180032038  mov     [rsp+360h+phkResult], rax; phkResult
0x18003203d  mov     r9d, 0F003Fh; samDesired
0x180032043  xor     r8d, r8d; ulOptions
0x180032046  mov     rdx, rbx; lpSubKey
0x180032049  mov     rcx, [r12+10h]; hKey
0x18003204e  call    cs:__imp_RegOpenKeyExW
0x180032055  nop     dword ptr [rax+rax+00h]
0x18003205a  mov     edi, eax
0x18003205c  test    eax, eax
0x18003205e  jz      short loc_1800320DF
0x180032060  jle     short loc_18003206B
0x180032062  movzx   edi, ax
0x180032065  or      edi, 80070000h
0x18003206b  mov     rax, cs:WPP_GLOBAL_Control
0x180032072  lea     rdx, WPP_GLOBAL_Control
0x180032079  cmp     rax, rdx
0x18003207c  jz      short loc_1800320BE
0x18003207e  test    dword ptr [rax+1Ch], 40000h
0x180032085  jz      short loc_1800320BE
0x180032087  cmp     byte ptr [rax+19h], 2
0x18003208b  jb      short loc_1800320BE
0x18003208d  mov     rcx, r13; this
0x180032090  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x180032095  mov     edx, 2Eh ; '.'
0x18003209a  mov     r9, rbx
0x18003209d  mov     dword ptr [rsp+360h+lpcbData], edi
0x1800320a1  mov     [rsp+360h+phkResult], rax
0x1800320a6  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x1800320ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800320b4  mov     rcx, [rcx+10h]
0x1800320b8  call    WPP_SF_SSD
0x1800320bd  nop
0x1800320be  lea     rcx, [rsp+360h+hKey]; this
0x1800320c3  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x1800320c8  nop
0x1800320c9  mov     rcx, rbx; bstrString
0x1800320cc  call    cs:__imp_SysFreeString
0x1800320d3  nop     dword ptr [rax+rax+00h]
0x1800320d8  mov     eax, edi
0x1800320da  jmp     loc_1800324B2
0x1800320df  mov     [rsp+360h+Type], esi
0x1800320e3  xor     edx, edx; Val
0x1800320e5  mov     r8d, 20Ah; Size
0x1800320eb  lea     rcx, [rbp+260h+Data]; void *
0x1800320ef  call    memset_0
0x1800320f4  mov     [rsp+360h+cbData], 20Ah
0x1800320fc  lea     rax, [rsp+360h+cbData]
0x180032101  mov     [rsp+360h+lpcbData], rax; lpcbData
0x180032106  lea     rax, [rbp+260h+Data]
0x18003210a  mov     [rsp+360h+phkResult], rax; lpData
0x18003210f  lea     r9, [rsp+360h+Type]; lpType
0x180032114  xor     r8d, r8d; lpReserved
0x180032117  lea     rdx, aPath; "Path"
0x18003211e  mov     rcx, [rsp+360h+hKey]; hKey
0x180032123  call    cs:__imp_RegQueryValueExW
0x18003212a  nop     dword ptr [rax+rax+00h]
0x18003212f  mov     edi, eax
0x180032131  test    eax, eax
0x180032133  jz      short loc_180032187
0x180032135  jle     short loc_180032140
0x180032137  movzx   edi, ax
0x18003213a  or      edi, 80070000h
0x180032140  mov     rax, cs:WPP_GLOBAL_Control
0x180032147  lea     rdx, WPP_GLOBAL_Control
0x18003214e  cmp     rax, rdx
0x180032151  jz      loc_1800320BE
0x180032157  test    dword ptr [rax+1Ch], 40000h
0x18003215e  jz      loc_1800320BE
0x180032164  cmp     byte ptr [rax+19h], 2
0x180032168  jb      loc_1800320BE
0x18003216e  mov     rcx, r13; this
0x180032171  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x180032176  mov     edx, 2Fh ; '/'
0x18003217b  lea     r9, aPath; "Path"
0x180032182  jmp     loc_18003209D
0x180032187  cmp     [rsp+360h+Type], 1
0x18003218c  jz      short loc_1800321B2
0x18003218e  lea     rcx, [rsp+360h+hKey]; this
0x180032193  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180032198  nop
0x180032199  mov     rcx, rbx; bstrString
0x18003219c  call    cs:__imp_SysFreeString
0x1800321a3  nop     dword ptr [rax+rax+00h]
0x1800321a8  mov     eax, 80020005h
0x1800321ad  jmp     loc_1800324B2
0x1800321b2  mov     [rbp+260h+var_58], si
0x1800321b9  lea     rdx, [rbp+260h+Data]; String2
0x1800321bd  mov     rcx, [rsp+360h+String1]; String1
  ... truncated ...
```
