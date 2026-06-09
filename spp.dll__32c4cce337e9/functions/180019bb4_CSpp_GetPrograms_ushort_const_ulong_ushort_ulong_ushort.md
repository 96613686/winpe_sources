# CSpp::_GetPrograms(ushort const *,ulong *,ushort * * *,ulong *,ushort * * *)

- ea: `0x180019bb4`
- end: `0x18001a374`
- name: `?_GetPrograms@CSpp@@AEAAJPEBGPEAKPEAPEAPEAG12@Z`
- size: `1984`
- prototype: `__int64 __fastcall(CSpp *this, const unsigned __int16 *, unsigned int *, unsigned __int16 ***, unsigned int *, unsigned __int16 ***)`
- caller_count: `3`
- callee_count: `25`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000a280`
- `0x18000b0d0`
- `0x18001176c`

## callees

- `0x1800037e4`
- `0x18000702c`
- `0x180007544`
- `0x180007908`
- `0x180008cd0`
- `0x18000dd40`
- `0x18000e308`
- `0x18000e34c`
- `0x180010c18`
- `0x180019bb4`
- `0x180020710`
- `0x180020968`
- `0x1800268b4`
- `0x1800269ac`
- `0x1800299c4`
- `0x18002be5c`
- `0x18002ddfc`
- `0x18002e2ac`
- `0x18002e6e0`
- `0x180034d70`
- `0x180034f3c`
- `0x180035390`
- `0x180035b00`
- `0x180035b9a`
- `0x180035bd0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001a21f`
- `msvcrt!_wcsicmp` at `0x18001a21f`
- `msvcrt!qsort` at `0x18001a1f8`
- `msvcrt!qsort` at `0x18001a1f8`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x18001a0e9`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x18001a0e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a22d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a28c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a22d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a28c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019e21`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019e38`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019f0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019f24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a308`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a32f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019e21`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019e38`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019f0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019f24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a308`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a32f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019e61`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019f4b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019e61`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019f4b`

## string_xrefs

- `0x180019dcd`: `Microsoft\Windows\CurrentVersion\Uninstall`
- `0x180019df0`: `Microsoft\Windows\CurrentVersion\Uninstall`
- `0x180019f9a`: `SystemComponent`
- `0x18001a06c`: `UninstallString`
- `0x18001a096`: `InstallLocation`

## pseudocode

```c
__int64 __fastcall CSpp::_GetPrograms(
        CSpp *this,
        const unsigned __int16 *a2,
        unsigned int *a3,
        unsigned __int16 ***a4,
        unsigned int *a5,
        unsigned __int16 ***a6)
{
  unsigned int *v6; // r14
  const unsigned __int16 *v9; // rsi
  struct CSxStringMap *v10; // r15
  const unsigned __int16 **v11; // r13
  __int16 v12; // ax
  int v13; // eax
  unsigned int i; // ebx
  bool v15; // sf
  HKEY v16; // rcx
  LSTATUS v17; // eax
  DWORD j; // esi
  int v19; // eax
  HKEY v20; // rcx
  unsigned __int16 *v21; // rbx
  CSpp *v22; // rcx
  CSpp *v23; // rcx
  CSpp *v24; // rcx
  __int64 v25; // rbx
  int v26; // eax
  _QWORD *v27; // rdx
  unsigned int v28; // ecx
  unsigned __int16 **v29; // rax
  _QWORD *v30; // rdi
  unsigned int v31; // esi
  unsigned __int16 ***v32; // rbx
  _QWORD *v33; // rdx
  unsigned __int16 **v34; // rcx
  unsigned int v35; // eax
  unsigned int v36; // ebx
  __int64 v37; // r8
  char *v38; // rdx
  const unsigned __int16 *v40; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *v41; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *v42; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v43; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v44; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v45; // [rsp+50h] [rbp-B0h]
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  int v48; // [rsp+70h] [rbp-90h] BYREF
  __int16 v49; // [rsp+74h] [rbp-8Ch]
  __int16 v50; // [rsp+76h] [rbp-8Ah]
  unsigned int v51; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v52; // [rsp+ACh] [rbp-54h]
  LPVOID pv; // [rsp+B0h] [rbp-50h] BYREF
  const unsigned __int16 **v54; // [rsp+B8h] [rbp-48h] BYREF
  void *Block; // [rsp+C0h] [rbp-40h] BYREF
  void *v56; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 *Src; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v58; // [rsp+D8h] [rbp-28h]
  struct CSxStringMap *v59; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 *v60; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v61; // [rsp+F0h] [rbp-10h]
  LPCWSTR lpSubKey[2]; // [rsp+F8h] [rbp-8h] BYREF
  LPCWSTR v63[2]; // [rsp+108h] [rbp+8h] BYREF
  const unsigned __int16 *v64; // [rsp+118h] [rbp+18h]
  unsigned int *v65; // [rsp+120h] [rbp+20h]
  unsigned __int16 ***v66; // [rsp+128h] [rbp+28h]
  _QWORD v67[2]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v68[2]; // [rsp+140h] [rbp+40h] BYREF
  WCHAR szVolumeName; // [rsp+150h] [rbp+50h] BYREF
  char v70[526]; // [rsp+152h] [rbp+52h] BYREF

  v6 = a5;
  v65 = a5;
  v9 = a2;
  v66 = a6;
  v64 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v48, "CSpp::_GetPrograms", 2541, 1);
  hKey = 0;
  v10 = 0;
  v63[1] = 0;
  v11 = 0;
  phkResult = 0;
  v58 = 0;
  v51 = 0;
  v56 = 0;
  Block = 0;
  pv = 0;
  v68[1] = 0;
  v59 = 0;
  v67[1] = 0;
  v54 = 0;
  lpSubKey[1] = 0;
  szVolumeName = 0;
  v63[0] = &FileName;
  Src = (unsigned __int16 *)&FileName;
  v68[0] = &FileName;
  v67[0] = &FileName;
  lpSubKey[0] = &FileName;
  memset_0(v70, 0, 0x208u);
  v60 = (unsigned __int16 *)&FileName;
  v61 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  if ( a6 )
    *a6 = 0;
  v12 = 2567;
  if ( !v9 || (v49 = 2567, v12 = 2569, (a3 == 0) != (a4 == 0)) || (v49 = 2569, v12 = 2570, (a5 == 0) != (a6 == 0)) )
  {
    v48 = -2147024809;
LABEL_14:
    v50 = v12;
    goto LABEL_87;
  }
  v48 = 0;
  v49 = 2570;
  v48 = CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>::CreateInstance(&v56);
  v12 = 2572;
  if ( v48 < 0 )
    goto LABEL_14;
  v49 = 2572;
  v48 = CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>::CreateInstance(&Block);
  v12 = 2573;
  if ( v48 < 0 )
    goto LABEL_14;
  v49 = 2573;
  v13 = CSxStringMap::CreateInstance(&v59);
  v10 = v59;
  v15 = v13 < 0;
  v48 = v13;
  v12 = 2575;
  if ( v15 )
    goto LABEL_14;
  v49 = 2575;
  for ( i = 0; ; ++i )
  {
    v52 = i;
    if ( i >= 2 )
      break;
    if ( i == 1 )
    {
      v48 = CBsString::SetPath(
              (CBsString *)lpSubKey,
              v9,
              L"Wow6432Node",
              L"Microsoft\\Windows\\CurrentVersion\\Uninstall",
              0,
              v40,
              v41,
              v42,
              v43,
              v44,
              v45);
      v15 = v48 < 0;
      v12 = 2589;
    }
    else
    {
      v48 = CBsString::SetPath(
              (CBsString *)lpSubKey,
              v9,
              L"Microsoft\\Windows\\CurrentVersion\\Uninstall",
              0,
              0,
              v40,
              v41,
              v42,
              v43,
              v44,
              v45);
      v15 = v48 < 0;
      v12 = 2594;
    }
    if ( v15 )
      goto LABEL_14;
    v16 = hKey;
    v49 = v12;
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(hKey);
      v16 = 0;
      hKey = 0;
    }
    if ( (unsigned __int64)v16 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(v16);
      hKey = 0;
    }
    v17 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0x20019u, &hKey);
    if ( !v17 )
    {
      for ( j = 0; ; ++j )
      {
        CBsString::Empty((CBsString *)&Src);
        CBsString::Empty((CBsString *)&v60);
        v19 = SxRegEnumKey(hKey, j, (struct CBsString *)v63);
        v48 = v19;
        if ( v19 < 0 )
          break;
        v49 = 2622;
        if ( v19 )
        {
          i = v52;
          v9 = v64;
          goto LABEL_59;
        }
        v20 = phkResult;
        if ( phkResult )
        {
          if ( phkResult != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
          {
            RegCloseKey(phkResult);
            v20 = 0;
            phkResult = 0;
          }
          if ( (unsigned __int64)v20 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            RegCloseKey(v20);
            phkResult = 0;
          }
        }
        if ( !RegOpenKeyExW(hKey, v63[0], 0, 0x20019u, &phkResult)
          && (int)SxRegReadString(phkResult, L"DisplayName", (struct CBsString *)&Src) >= 0 )
        {
          if ( (_DWORD)v58 )
          {
            v21 = Src;
            if ( *Src != 64 && ((int)SxRegReadDWORD(phkResult, L"SystemComponent", &v51, 0) < 0 || !v51) )
            {
              SxRegReadString(phkResult, L"DisplayVersion", (struct CBsString *)&v60);
              if ( (_DWORD)v61 )
              {
                v48 = CBsString::Append((CBsString *)&Src, L" ", v60);
                v12 = 2668;
                if ( v48 < 0 )
                  goto LABEL_14;
                v21 = Src;
                v49 = 2668;
              }
              v48 = SxCopyString(v21, (unsigned __int16 **)&pv);
              v12 = 2674;
              if ( v48 < 0 )
                goto LABEL_14;
              v49 = 2674;
              v48 = CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>::Append(
                      v56,
                      &pv);
              v12 = 2675;
              if ( v48 < 0 )
                goto LABEL_14;
              v49 = 2675;
              v48 = CSpp::_AddInstallDrives(v22, v10, phkResult, L"DisplayIcon");
              v12 = 2683;
              if ( v48 < 0 )
                goto LABEL_14;
              v49 = 2683;
              v48 = CSpp::_AddInstallDrives(v23, v10, phkResult, L"UninstallString");
              v12 = 2684;
              if ( v48 < 0 )
                goto LABEL_14;
              v49 = 2684;
              v48 = CSpp::_AddInstallDrives(v24, v10, phkResult, L"InstallLocation");
              v12 = 2685;
              if ( v48 < 0 )
                goto LABEL_14;
              v49 = 2685;
            }
          }
        }
      }
      v12 = 2622;
      goto LABEL_14;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        (unsigned int)&WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids,
        lpSubKey[0],
        v17);
LABEL_59:
    ;
  }
  LODWORD(v25) = 0;
  while ( RtlNumberGenericTableElementsAvl(*(PRTL_AVL_TABLE *)v10) )
  {
    if ( v11 )
    {
      v54 = 0;
      CVolumeEntry::Release((CVolumeEntry *)v11);
    }
    v26 = CSxRefMap<CSxStringMap,CSxStringEntry>::First(v10, &v54);
    v11 = v54;
    v15 = v26 < 0;
    v48 = v26;
    v12 = 2695;
    if ( v15 )
      goto LABEL_14;
    v49 = 2695;
    v48 = CSxRefMap<CVolumeEntryMap,CVolumeEntry>::Delete(v10, v54);
    v12 = 2696;
    if ( v48 < 0 )
      goto LABEL_14;
    v49 = 2696;
    szVolumeName = 0;
    if ( (int)SxGetUniqueVolumeForPath(v11[1], &szVolumeName, 0x105u) >= 0 )
    {
      v48 = SxCopyString(&szVolumeName, (unsigned __int16 **)&pv);
      v12 = 2708;
      if ( v48 < 0 )
        goto LABEL_14;
      v49 = 2708;
      v48 = CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>::Append(
              Block,
              &pv);
      if ( v48 < 0 )
      {
        v50 = 2709;
        goto LABEL_87;
      }
      v49 = 2709;
    }
  }
  if ( !a3 )
    goto LABEL_84;
  if ( !a4 )
    goto LABEL_84;
  v27 = v56;
  v28 = *((_DWORD *)v56 + 4);
  v29 = (unsigned __int16 **)*((_QWORD *)v56 + 1);
  *((_QWORD *)v56 + 1) = 0;
  v27[2] = 0;
  *a4 = v29;
  *a3 = v28;
  qsort(*a4, v28, 8u, CSpp::_StringSortRoutine);
  if ( !*a3 )
    goto LABEL_84;
  v30 = *a4;
  v31 = 1;
  if ( *a3 <= 1 )
    goto LABEL_83;
  do
  {
    if ( _wcsicmp((const wchar_t *)v30[(unsigned int)v25], (const wchar_t *)v30[v31]) )
    {
      v25 = (unsigned int)(v25 + 1);
      if ( v31 == (_DWORD)v25 )
        goto LABEL_81;
      v30[v25] = v30[v31];
    }
    else
    {
      CoTaskMemFree((LPVOID)v30[v31]);
    }
    v30[v31] = 0;
LABEL_81:
    ++v31;
  }
  while ( v31 < *a3 );
  v6 = v65;
LABEL_83:
  *a3 = v25 + 1;
LABEL_84:
  if ( v6 )
  {
    v32 = v66;
    if ( v66 )
    {
      v33 = Block;
      v34 = (unsigned __int16 **)*((_QWORD *)Block + 1);
      v35 = *((_DWORD *)Block + 4);
      *((_QWORD *)Block + 1) = 0;
      v33[2] = 0;
      *v32 = v34;
      *v6 = v35;
    }
  }
LABEL_87:
  CoTaskMemFree(pv);
  v36 = v48;
  CBsString::_Release((CBsString *)&v60);
  CBsString::_Release((CBsString *)lpSubKey);
  if ( v11 )
    CVolumeEntry::Release((CVolumeEntry *)v11);
  CBsString::_Release((CBsString *)v67);
  if ( v10 )
    CSxStringMap::Release(v10);
  CBsString::_Release((CBsString *)v68);
  if ( Block )
    CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>::Release(Block);
  if ( v56 )
    CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>::Release(v56);
  CBsString::_Release((CBsString *)&Src);
  if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  CBsString::_Release((CBsString *)v63);
  v38 = (char *)hKey - 1;
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v48, (__int64)v38, v37);
  return v36;
}

```

## disassembly

```asm
0x180019bb4  mov     [rsp-8+arg_0], rbx
0x180019bb9  push    rbp
0x180019bba  push    rsi
0x180019bbb  push    rdi
0x180019bbc  push    r12
0x180019bbe  push    r13
0x180019bc0  push    r14
0x180019bc2  push    r15
0x180019bc4  lea     rbp, [rsp-270h]
0x180019bcc  sub     rsp, 370h
0x180019bd3  mov     rax, cs:__security_cookie
0x180019bda  xor     rax, rsp
0x180019bdd  mov     [rbp+2A0h+var_40], rax
0x180019be4  mov     r14, [rbp+2A0h+arg_20]
0x180019beb  mov     rdi, r9
0x180019bee  mov     rbx, [rbp+2A0h+arg_28]
0x180019bf5  mov     r12, r8
0x180019bf8  mov     [rbp+2A0h+var_280], r14
0x180019bfc  mov     rsi, rdx
0x180019bff  mov     [rbp+2A0h+var_278], rbx
0x180019c03  mov     [rbp+2A0h+var_288], rdx
0x180019c07  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c0e  lea     rax, WPP_GLOBAL_Control
0x180019c15  cmp     rcx, rax
0x180019c18  jz      short loc_180019C38
0x180019c1a  test    dword ptr [rcx+1Ch], 20000000h
0x180019c21  jz      short loc_180019C38
0x180019c23  mov     rcx, [rcx+10h]
0x180019c27  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x180019c2e  mov     edx, 18h
0x180019c33  call    WPP_SF_
0x180019c38  mov     r9d, 1; unsigned __int16
0x180019c3e  lea     rdx, aCsppGetprogram_0; "CSpp::_GetPrograms"
0x180019c45  mov     r8d, 9EDh; unsigned __int16
0x180019c4b  lea     rcx, [rsp+3A0h+var_330]; this
0x180019c50  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180019c55  xor     ecx, ecx
0x180019c57  lea     rax, FileName
0x180019c5e  mov     [rsp+3A0h+hKey], rcx
0x180019c63  mov     r15d, ecx
0x180019c66  mov     [rbp+2A0h+var_290], rcx
0x180019c6a  mov     r13d, ecx
0x180019c6d  mov     [rsp+3A0h+var_340], rcx
0x180019c72  xor     edx, edx; Val
0x180019c74  mov     [rbp+2A0h+var_2C8], rcx
0x180019c78  mov     r8d, 208h; Size
0x180019c7e  mov     [rbp+2A0h+var_2F8], ecx
0x180019c81  mov     [rbp+2A0h+var_2D8], rcx
0x180019c85  mov     [rbp+2A0h+Block], rcx
0x180019c89  mov     [rbp+2A0h+pv], rcx
0x180019c8d  mov     [rbp+2A0h+var_258], rcx
0x180019c91  mov     [rbp+2A0h+var_2C0], rcx
0x180019c95  mov     [rbp+2A0h+var_268], rcx
0x180019c99  mov     [rbp+2A0h+var_2E8], rcx
0x180019c9d  mov     [rbp+2A0h+var_2A0], rcx
0x180019ca1  mov     [rbp+2A0h+szVolumeName], cx
0x180019ca5  lea     rcx, [rbp+2A0h+var_24E]; void *
0x180019ca9  mov     [rbp+2A0h+var_298], rax
0x180019cad  mov     [rbp+2A0h+Src], rax
0x180019cb1  mov     [rbp+2A0h+var_260], rax
0x180019cb5  mov     [rbp+2A0h+var_270], rax
0x180019cb9  mov     [rbp+2A0h+lpSubKey], rax
0x180019cbd  call    memset_0
0x180019cc2  xor     edx, edx
0x180019cc4  lea     rax, FileName
0x180019ccb  mov     [rbp+2A0h+var_2B8], rax
0x180019ccf  mov     [rbp+2A0h+var_2B0], rdx
0x180019cd3  test    r12, r12
0x180019cd6  jz      short loc_180019CDC
0x180019cd8  mov     [r12], edx
0x180019cdc  test    rdi, rdi
0x180019cdf  jz      short loc_180019CE4
0x180019ce1  mov     [rdi], rdx
0x180019ce4  test    r14, r14
0x180019ce7  jz      short loc_180019CEC
0x180019ce9  mov     [r14], edx
0x180019cec  test    rbx, rbx
0x180019cef  jz      short loc_180019CF4
0x180019cf1  mov     [rbx], rdx
0x180019cf4  mov     eax, 0A07h
0x180019cf9  test    rsi, rsi
0x180019cfc  jnz     short loc_180019D10
0x180019cfe  mov     [rsp+3A0h+var_330], 80070057h
0x180019d06  mov     [rsp+3A0h+var_32A], ax
0x180019d0b  jmp     loc_18001A288
0x180019d10  test    rdi, rdi
0x180019d13  mov     [rsp+3A0h+var_32C], ax
0x180019d18  mov     eax, edx
0x180019d1a  mov     ecx, edx
0x180019d1c  setz    cl
0x180019d1f  test    r12, r12
0x180019d22  setz    al
0x180019d25  cmp     eax, ecx
0x180019d27  mov     eax, 0A09h
0x180019d2c  jnz     short loc_180019CFE
0x180019d2e  test    rbx, rbx
0x180019d31  mov     [rsp+3A0h+var_32C], ax
0x180019d36  mov     eax, edx
0x180019d38  mov     ecx, edx
0x180019d3a  setz    cl
0x180019d3d  test    r14, r14
0x180019d40  setz    al
0x180019d43  cmp     eax, ecx
0x180019d45  mov     eax, 0A0Ah
0x180019d4a  jnz     short loc_180019CFE
0x180019d4c  lea     rcx, [rbp+2A0h+var_2D8]
0x180019d50  mov     [rsp+3A0h+var_330], edx
0x180019d54  mov     [rsp+3A0h+var_32C], ax
0x180019d59  call    ?CreateInstance@?$CSxArrayBuilder@PEAG$1?Free_String@@YAXPEAPEAG@Z$1??$SxDefaultInit@PEAG@@YAX0@Z$1??$SxDefaultTransfer@PEAG@@YAX00@Z@@SAJPEAPEAV1@@Z; CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>::CreateInstance(CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)> * *)
0x180019d5e  mov     [rsp+3A0h+var_330], eax
0x180019d62  test    eax, eax
0x180019d64  mov     eax, 0A0Ch
0x180019d69  js      short loc_180019D06
0x180019d6b  lea     rcx, [rbp+2A0h+Block]
0x180019d6f  mov     [rsp+3A0h+var_32C], ax
0x180019d74  call    ?CreateInstance@?$CSxArrayBuilder@PEAG$1?Free_String@@YAXPEAPEAG@Z$1??$SxDefaultInit@PEAG@@YAX0@Z$1??$SxDefaultTransfer@PEAG@@YAX00@Z@@SAJPEAPEAV1@@Z; CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>::CreateInstance(CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)> * *)
0x180019d79  mov     [rsp+3A0h+var_330], eax
0x180019d7d  test    eax, eax
0x180019d7f  mov     eax, 0A0Dh
0x180019d84  js      short loc_180019D06
0x180019d86  lea     rcx, [rbp+2A0h+var_2C0]; struct CSxStringMap **
0x180019d8a  mov     [rsp+3A0h+var_32C], ax
0x180019d8f  call    ?CreateInstance@CSxStringMap@@SAJPEAPEAV1@@Z; CSxStringMap::CreateInstance(CSxStringMap * *)
0x180019d94  mov     r15, [rbp+2A0h+var_2C0]
0x180019d98  test    eax, eax
0x180019d9a  mov     [rsp+3A0h+var_330], eax
0x180019d9e  mov     eax, 0A0Fh
0x180019da3  js      loc_180019D06
0x180019da9  mov     [rsp+3A0h+var_32C], ax
0x180019dae  xor     ebx, ebx
0x180019db0  mov     [rbp+2A0h+var_2F4], ebx
0x180019db3  cmp     ebx, 2
0x180019db6  jnb     loc_18001A0DF
0x180019dbc  mov     [rsp+3A0h+phkResult], r13; unsigned __int16 *
0x180019dc1  mov     rdx, rsi; unsigned __int16 *
0x180019dc4  lea     rcx, [rbp+2A0h+lpSubKey]; this
0x180019dc8  cmp     ebx, 1
0x180019dcb  jnz     short loc_180019DED
0x180019dcd  lea     r9, aMicrosoftWindo; "Microsoft\\Windows\\CurrentVersion\\Uni"...
0x180019dd4  lea     r8, aWow6432node; "Wow6432Node"
0x180019ddb  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180019de0  mov     [rsp+3A0h+var_330], eax
0x180019de4  test    eax, eax
0x180019de6  mov     eax, 0A1Dh
0x180019deb  jmp     short loc_180019E07
0x180019ded  xor     r9d, r9d; unsigned __int16 *
0x180019df0  lea     r8, aMicrosoftWindo; "Microsoft\\Windows\\CurrentVersion\\Uni"...
0x180019df7  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180019dfc  mov     [rsp+3A0h+var_330], eax
0x180019e00  test    eax, eax
0x180019e02  mov     eax, 0A22h
0x180019e07  js      loc_180019D06
0x180019e0d  mov     rcx, [rsp+3A0h+hKey]; hKey
0x180019e12  mov     [rsp+3A0h+var_32C], ax
0x180019e17  lea     rax, [rcx-1]
0x180019e1b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180019e1f  ja      short loc_180019E2E
0x180019e21  call    cs:__imp_RegCloseKey
0x180019e27  xor     ecx, ecx; hKey
0x180019e29  mov     [rsp+3A0h+hKey], rcx
0x180019e2e  lea     rax, [rcx-1]
0x180019e32  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180019e36  ja      short loc_180019E43
0x180019e38  call    cs:__imp_RegCloseKey
0x180019e3e  mov     [rsp+3A0h+hKey], r13
0x180019e43  mov     rdx, [rbp+2A0h+lpSubKey]; lpSubKey
0x180019e47  lea     rax, [rsp+3A0h+hKey]
0x180019e4c  mov     r9d, 20019h; samDesired
0x180019e52  mov     [rsp+3A0h+phkResult], rax; phkResult
0x180019e57  xor     r8d, r8d; ulOptions
0x180019e5a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180019e61  call    cs:__imp_RegOpenKeyExW
0x180019e67  test    eax, eax
0x180019e69  jz      short loc_180019EBD
0x180019e6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180019e72  lea     rdx, WPP_GLOBAL_Control
0x180019e79  cmp     rcx, rdx
0x180019e7c  jz      loc_18001A0CE
0x180019e82  test    dword ptr [rcx+1Ch], 4000000h
0x180019e89  jz      loc_18001A0CE
0x180019e8f  test    eax, eax
0x180019e91  jle     short loc_180019E9B
0x180019e93  movzx   eax, ax
0x180019e96  or      eax, 80070000h
0x180019e9b  mov     r9, [rbp+2A0h+lpSubKey]
0x180019e9f  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x180019ea6  mov     rcx, [rcx+10h]
0x180019eaa  mov     edx, 19h
0x180019eaf  mov     dword ptr [rsp+3A0h+phkResult], eax
0x180019eb3  call    WPP_SF_Sd
0x180019eb8  jmp     loc_18001A0CE
0x180019ebd  xor     esi, esi
0x180019ebf  lea     rcx, [rbp+2A0h+Src]; this
0x180019ec3  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x180019ec8  lea     rcx, [rbp+2A0h+var_2B8]; this
0x180019ecc  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x180019ed1  mov     rcx, [rsp+3A0h+hKey]; hKey
0x180019ed6  lea     r8, [rbp+2A0h+var_298]; this
0x180019eda  mov     edx, esi; dwIndex
0x180019edc  call    ?SxRegEnumKey@@YAJPEAUHKEY__@@KPEAVCBsString@@@Z; SxRegEnumKey(HKEY__ *,ulong,CBsString *)
0x180019ee1  mov     [rsp+3A0h+var_330], eax
0x180019ee5  test    eax, eax
0x180019ee7  js      loc_18001A0D5
0x180019eed  mov     ecx, 0A3Eh
0x180019ef2  mov     [rsp+3A0h+var_32C], cx
0x180019ef7  jnz     loc_18001A0C7
0x180019efd  mov     rcx, [rsp+3A0h+var_340]; hKey
0x180019f02  test    rcx, rcx
0x180019f05  jz      short loc_180019F2F
0x180019f07  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180019f0b  jz      short loc_180019F1A
0x180019f0d  call    cs:__imp_RegCloseKey
0x180019f13  xor     ecx, ecx; hKey
0x180019f15  mov     [rsp+3A0h+var_340], rcx
0x180019f1a  lea     rax, [rcx-1]
0x180019f1e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180019f22  ja      short loc_180019F2F
0x180019f24  call    cs:__imp_RegCloseKey
0x180019f2a  mov     [rsp+3A0h+var_340], r13
0x180019f2f  mov     rdx, [rbp+2A0h+var_298]; lpSubKey
0x180019f33  lea     rax, [rsp+3A0h+var_340]
0x180019f38  mov     rcx, [rsp+3A0h+hKey]; hKey
0x180019f3d  mov     r9d, 20019h; samDesired
0x180019f43  xor     r8d, r8d; ulOptions
0x180019f46  mov     [rsp+3A0h+phkResult], rax; phkResult
0x180019f4b  call    cs:__imp_RegOpenKeyExW
0x180019f51  test    eax, eax
0x180019f53  jnz     loc_18001A0C0
0x180019f59  mov     rcx, [rsp+3A0h+var_340]; hKey
0x180019f5e  lea     r8, [rbp+2A0h+Src]; this
0x180019f62  lea     rdx, aDisplayname; "DisplayName"
0x180019f69  call    ?SxRegReadString@@YAJPEAUHKEY__@@PEBGPEAVCBsString@@@Z; SxRegReadString(HKEY__ *,ushort const *,CBsString *)
0x180019f6e  test    eax, eax
0x180019f70  js      loc_18001A0C0
0x180019f76  cmp     dword ptr [rbp+2A0h+var_2C8], r13d
0x180019f7a  jz      loc_18001A0C0
0x180019f80  mov     rbx, [rbp+2A0h+Src]
0x180019f84  cmp     word ptr [rbx], 40h ; '@'
0x180019f88  jz      loc_18001A0C0
0x180019f8e  mov     rcx, [rsp+3A0h+var_340]; hKey
0x180019f93  lea     r8, [rbp+2A0h+var_2F8]; unsigned int *
0x180019f97  xor     r9d, r9d; int
0x180019f9a  lea     rdx, aSystemcomponen; "SystemComponent"
0x180019fa1  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x180019fa6  test    eax, eax
0x180019fa8  js      short loc_180019FB4
0x180019faa  cmp     [rbp+2A0h+var_2F8], r13d
0x180019fae  jnz     loc_18001A0C0
0x180019fb4  mov     rcx, [rsp+3A0h+var_340]; hKey
0x180019fb9  lea     r8, [rbp+2A0h+var_2B8]; this
0x180019fbd  lea     rdx, aDisplayversion; "DisplayVersion"
0x180019fc4  call    ?SxRegReadString@@YAJPEAUHKEY__@@PEBGPEAVCBsString@@@Z; SxRegReadString(HKEY__ *,ushort const *,CBsString *)
0x180019fc9  cmp     dword ptr [rbp+2A0h+var_2B0], r13d
0x180019fcd  jz      short loc_180019FFD
0x180019fcf  mov     r8, [rbp+2A0h+var_2B8]; unsigned __int16 *
0x180019fd3  lea     rdx, asc_18003A418; " "
0x180019fda  lea     rcx, [rbp+2A0h+Src]; this
0x180019fde  call    ?Append@CBsString@@QEAAJPEBG0@Z; CBsString::Append(ushort const *,ushort const *)
0x180019fe3  mov     [rsp+3A0h+var_330], eax
0x180019fe7  test    eax, eax
0x180019fe9  mov     eax, 0A6Ch
0x180019fee  js      loc_180019D06
0x180019ff4  mov     rbx, [rbp+2A0h+Src]
0x180019ff8  mov     [rsp+3A0h+var_32C], ax
0x180019ffd  lea     rdx, [rbp+2A0h+pv]; unsigned __int16 **
0x18001a001  mov     rcx, rbx; Src
0x18001a004  call    ?SxCopyString@@YAJPEBGPEAPEAG@Z; SxCopyString(ushort const *,ushort * *)
0x18001a009  mov     [rsp+3A0h+var_330], eax
0x18001a00d  test    eax, eax
0x18001a00f  mov     eax, 0A72h
0x18001a014  js      loc_180019D06
0x18001a01a  mov     rcx, [rbp+2A0h+var_2D8]
0x18001a01e  lea     rdx, [rbp+2A0h+pv]
0x18001a022  mov     [rsp+3A0h+var_32C], ax
0x18001a027  call    ?Append@?$CSxArrayBuilder@PEAG$1?Free_String@@YAXPEAPEAG@Z$1??$SxDefaultInit@PEAG@@YAX0@Z$1??$SxDefaultTransfer@PEAG@@YAX00@Z@@QEAAJPEAPEAG@Z; CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>::Append(ushort * *)
0x18001a02c  mov     [rsp+3A0h+var_330], eax
0x18001a030  test    eax, eax
0x18001a032  mov     eax, 0A73h
0x18001a037  js      loc_180019D06
0x18001a03d  mov     r8, [rsp+3A0h+var_340]; HKEY
0x18001a042  lea     r9, aDisplayicon; "DisplayIcon"
0x18001a049  mov     rdx, r15; struct CSxStringMap *
0x18001a04c  mov     [rsp+3A0h+var_32C], ax
0x18001a051  call    ?_AddInstallDrives@CSpp@@AEAAJPEAVCSxStringMap@@PEAUHKEY__@@PEBG@Z; CSpp::_AddInstallDrives(CSxStringMap *,HKEY__ *,ushort const *)
0x18001a056  mov     [rsp+3A0h+var_330], eax
0x18001a05a  test    eax, eax
0x18001a05c  mov     eax, 0A7Bh
0x18001a061  js      loc_180019D06
0x18001a067  mov     r8, [rsp+3A0h+var_340]; HKEY
0x18001a06c  lea     r9, aUninstallstrin; "UninstallString"
0x18001a073  mov     rdx, r15; struct CSxStringMap *
0x18001a076  mov     [rsp+3A0h+var_32C], ax
0x18001a07b  call    ?_AddInstallDrives@CSpp@@AEAAJPEAVCSxStringMap@@PEAUHKEY__@@PEBG@Z; CSpp::_AddInstallDrives(CSxStringMap *,HKEY__ *,ushort const *)
0x18001a080  mov     [rsp+3A0h+var_330], eax
0x18001a084  test    eax, eax
0x18001a086  mov     eax, 0A7Ch
0x18001a08b  js      loc_180019D06
0x18001a091  mov     r8, [rsp+3A0h+var_340]; HKEY
0x18001a096  lea     r9, aInstalllocatio; "InstallLocation"
0x18001a09d  mov     rdx, r15; struct CSxStringMap *
  ... truncated ...
```
