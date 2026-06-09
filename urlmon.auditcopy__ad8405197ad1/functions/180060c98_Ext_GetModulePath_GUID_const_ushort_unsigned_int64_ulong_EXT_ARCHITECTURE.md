# Ext_GetModulePath(_GUID const &,ushort *,unsigned __int64,ulong,_EXT_ARCHITECTURE *)

- ea: `0x180060c98`
- end: `0x1800610b5`
- name: `?Ext_GetModulePath@@YAJAEBU_GUID@@PEAG_KKPEAW4_EXT_ARCHITECTURE@@@Z`
- size: `1053`
- prototype: `__int64 __fastcall(const struct _GUID *, unsigned __int16 *, unsigned __int64, char, enum _EXT_ARCHITECTURE *)`
- caller_count: `5`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180060514`
- `0x1800608b4`
- `0x1800d3998`
- `0x18010e7d0`
- `0x180119538`

## callees

- `0x1800162d4`
- `0x180024ea0`
- `0x180060c98`
- `0x180095984`
- `0x180125a58`
- `0x180128660`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180060e3f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180060e3f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnquoteSpacesW` at `0x18006103a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnquoteSpacesW` at `0x18006103a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180060e55`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180060e55`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060f16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006101b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060f16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006101b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060dba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060fb9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060dba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060fb9`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180061056`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180061056`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x180060ee5`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x180060ee5`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180060d39`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180060d39`
- `api-ms-win-core-com-l1-1-0!CoGetTreatAsClass` at `0x180060ce5`
- `api-ms-win-core-com-l1-1-0!CoGetTreatAsClass` at `0x180060ce5`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x180060e12`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x180060ea2`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x180060ffe`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x180060e12`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x180060ea2`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x180060ffe`

## string_xrefs

- `0x180060d6b`: `CLSID\%s\%s`
- `0x180060f56`: `CLSID\%s\%s`
- `0x180060e4e`: `mscoree.dll`

## pseudocode

```c
__int64 __fastcall Ext_GetModulePath(
        const struct _GUID *a1,
        unsigned __int16 *a2,
        unsigned __int64 a3,
        char a4,
        enum _EXT_ARCHITECTURE *a5)
{
  HRESULT TreatAsClass; // eax
  int ArchitectureHelper; // ebx
  unsigned __int64 v10; // rsi
  unsigned __int16 *pvData; // rdi
  LSTATUS v12; // eax
  bool v13; // zf
  LSTATUS v14; // eax
  const WCHAR *FileNameW; // rax
  LSTATUS v16; // eax
  bool v17; // sf
  unsigned __int16 *v18; // r8
  LSTATUS v19; // eax
  bool v20; // zf
  LSTATUS ValueW; // eax
  DWORD LongPathNameW; // eax
  HKEY hkey; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v25; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcchPath; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD pdwType; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbData; // [rsp+54h] [rbp-ACh] BYREF
  GUID pClsidNew; // [rsp+58h] [rbp-A8h] BYREF
  OLECHAR sz[40]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[264]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR szLongPath[264]; // [rsp+2D0h] [rbp+1D0h] BYREF
  WCHAR pszPath[264]; // [rsp+4E0h] [rbp+3E0h] BYREF

  pClsidNew = 0;
  TreatAsClass = CoGetTreatAsClass(a1, &pClsidNew);
  ArchitectureHelper = TreatAsClass;
  if ( a5 )
    *(_DWORD *)a5 = 0;
  v10 = 260;
  if ( a2 )
    v10 = a3;
  pvData = szLongPath;
  if ( a2 )
    pvData = a2;
  if ( TreatAsClass >= 0 )
  {
    hkey = 0;
    sz[0] = 0;
    ArchitectureHelper = StringFromGUID2(&pClsidNew, sz, 39);
    if ( ArchitectureHelper < 0 )
      goto LABEL_29;
    ArchitectureHelper = StringCchPrintfW(SubKey, 0x104u, L"CLSID\\%s\\%s", sz, L"InProcServer32");
    if ( ArchitectureHelper < 0 )
      goto LABEL_29;
    if ( (a4 & 0x10) != 0 )
    {
      ArchitectureHelper = Ext_GetArchitectureHelper(HKEY_CLASSES_ROOT, SubKey, &hkey, a5);
    }
    else
    {
      v12 = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 1u, &hkey);
      ArchitectureHelper = v12;
      if ( v12 > 0 )
        ArchitectureHelper = (unsigned __int16)v12 | 0x80070000;
    }
    v13 = ArchitectureHelper == 0;
    if ( ArchitectureHelper < 0 )
    {
LABEL_30:
      if ( v13 )
      {
LABEL_44:
        if ( pvData != szLongPath )
        {
          PathUnquoteSpacesW(pvData);
          LongPathNameW = GetLongPathNameW(pvData, szLongPath, 0x104u);
          if ( LongPathNameW - 1 <= 0x102 && LongPathNameW < v10 )
            StringCchCopyW(pvData, v10, szLongPath);
        }
        return (unsigned int)ArchitectureHelper;
      }
      if ( !sz[0] || (a4 & 6) == 0 )
        return (unsigned int)ArchitectureHelper;
      ArchitectureHelper = StringCchPrintfW(SubKey, 0x104u, L"CLSID\\%s\\%s", sz, L"LocalServer32");
      if ( ArchitectureHelper >= 0 )
      {
        pcchPath = 2 * v10;
        v25 = 1;
        if ( (a4 & 0x10) != 0 )
        {
          ArchitectureHelper = Ext_GetArchitectureHelper(HKEY_CLASSES_ROOT, SubKey, &hkey, a5);
        }
        else
        {
          v19 = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 1u, &hkey);
          ArchitectureHelper = v19;
          if ( v19 > 0 )
            ArchitectureHelper = (unsigned __int16)v19 | 0x80070000;
        }
        v20 = ArchitectureHelper == 0;
        if ( ArchitectureHelper < 0 )
        {
LABEL_43:
          if ( !v20 )
            return (unsigned int)ArchitectureHelper;
          goto LABEL_44;
        }
        ValueW = SHRegGetValueW(hkey, 0, 0, 2, &v25, pvData, &pcchPath);
        ArchitectureHelper = ValueW;
        if ( ValueW > 0 )
          ArchitectureHelper = (unsigned __int16)ValueW | 0x80070000;
        RegCloseKey(hkey);
      }
      v20 = ArchitectureHelper == 0;
      goto LABEL_43;
    }
    pcbData = 2 * v10;
    pdwType = 1;
    v14 = SHRegGetValueW(hkey, 0, 0, 2, &pdwType, pvData, &pcbData);
    ArchitectureHelper = v14;
    if ( v14 > 0 )
      ArchitectureHelper = (unsigned __int16)v14 | 0x80070000;
    if ( ArchitectureHelper >= 0 && (a4 & 7) != 0 )
    {
      FileNameW = PathFindFileNameW(pvData);
      if ( !StrCmpICW(FileNameW, L"mscoree.dll") )
      {
        v25 = 520;
        v16 = SHRegGetValueW(hkey, 0, L"CodeBase", 2, &pdwType, SubKey, &v25);
        v17 = v16 < 0;
        if ( v16 > 0 )
          v17 = 1;
        if ( !v17 )
        {
          if ( (unsigned int)GetUrlSchemeW(SubKey) != 9 )
          {
            v18 = SubKey;
            goto LABEL_27;
          }
          pcchPath = 260;
          ArchitectureHelper = PathCreateFromUrlW(SubKey, pszPath, &pcchPath, 0);
          if ( ArchitectureHelper >= 0 )
          {
            v18 = pszPath;
LABEL_27:
            ArchitectureHelper = StringCchCopyW(pvData, v10, v18);
          }
        }
      }
    }
    RegCloseKey(hkey);
LABEL_29:
    v13 = ArchitectureHelper == 0;
    goto LABEL_30;
  }
  return (unsigned int)ArchitectureHelper;
}

```

## disassembly

```asm
0x180060c98  mov     [rsp-8+arg_18], rbx
0x180060c9d  push    rbp
0x180060c9e  push    rsi
0x180060c9f  push    rdi
0x180060ca0  push    r12
0x180060ca2  push    r13
0x180060ca4  push    r14
0x180060ca6  push    r15
0x180060ca8  lea     rbp, [rsp-600h]
0x180060cb0  sub     rsp, 700h
0x180060cb7  mov     rax, cs:__security_cookie
0x180060cbe  xor     rax, rsp
0x180060cc1  mov     [rbp+630h+var_40], rax
0x180060cc8  mov     r12, [rbp+630h+arg_20]
0x180060ccf  mov     r14, rdx
0x180060cd2  xorps   xmm0, xmm0
0x180060cd5  lea     rdx, [rsp+730h+pClsidNew]; pClsidNew
0x180060cda  movups  xmmword ptr [rsp+730h+pClsidNew.Data1], xmm0
0x180060cdf  mov     r15d, r9d
0x180060ce2  mov     rdi, r8
0x180060ce5  call    cs:__imp_CoGetTreatAsClass
0x180060cec  nop     dword ptr [rax+rax+00h]
0x180060cf1  xor     r13d, r13d
0x180060cf4  mov     ebx, eax
0x180060cf6  test    r12, r12
0x180060cf9  jz      short loc_180060CFF
0x180060cfb  mov     [r12], r13d
0x180060cff  test    r14, r14
0x180060d02  mov     esi, 104h
0x180060d07  cmovnz  rsi, rdi
0x180060d0b  lea     rdi, [rbp+630h+szLongPath]
0x180060d12  cmovnz  rdi, r14
0x180060d16  test    eax, eax
0x180060d18  js      loc_180061088
0x180060d1e  mov     r8d, 27h ; '''; cchMax
0x180060d24  mov     [rsp+730h+hkey], r13
0x180060d29  lea     rdx, [rsp+730h+sz]; lpsz
0x180060d2e  mov     [rsp+730h+sz], r13w
0x180060d34  lea     rcx, [rsp+730h+pClsidNew]; rguid
0x180060d39  call    cs:__imp_StringFromGUID2
0x180060d40  nop     dword ptr [rax+rax+00h]
0x180060d45  mov     ebx, eax
0x180060d47  mov     r14d, 80070000h
0x180060d4d  test    eax, eax
0x180060d4f  js      loc_180060F22
0x180060d55  lea     rax, aInprocserver32; "InProcServer32"
0x180060d5c  mov     edx, 104h; unsigned __int64
0x180060d61  lea     r9, [rsp+730h+sz]
0x180060d66  mov     [rsp+730h+phkResult], rax
0x180060d6b  lea     r8, aClsidSS; "CLSID\\%s\\%s"
0x180060d72  lea     rcx, [rbp+630h+SubKey]; unsigned __int16 *
0x180060d76  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180060d7b  mov     ebx, eax
0x180060d7d  test    eax, eax
0x180060d7f  js      loc_180060F22
0x180060d85  lea     rdx, [rbp+630h+SubKey]; lpSubKey
0x180060d89  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180060d90  test    r15b, 10h
0x180060d94  jz      short loc_180060DA7
0x180060d96  mov     r9, r12; enum _EXT_ARCHITECTURE *
0x180060d99  lea     r8, [rsp+730h+hkey]; HKEY *
0x180060d9e  call    ?Ext_GetArchitectureHelper@@YAJPEAUHKEY__@@PEBGPEAPEAU1@PEAW4_EXT_ARCHITECTURE@@@Z; Ext_GetArchitectureHelper(HKEY__ *,ushort const *,HKEY__ * *,_EXT_ARCHITECTURE *)
0x180060da3  mov     ebx, eax
0x180060da5  jmp     short loc_180060DD2
0x180060da7  lea     rax, [rsp+730h+hkey]
0x180060dac  mov     r9d, 1; samDesired
0x180060db2  xor     r8d, r8d; ulOptions
0x180060db5  mov     [rsp+730h+phkResult], rax; phkResult
0x180060dba  call    cs:__imp_RegOpenKeyExW
0x180060dc1  nop     dword ptr [rax+rax+00h]
0x180060dc6  mov     ebx, eax
0x180060dc8  test    eax, eax
0x180060dca  jle     short loc_180060DD2
0x180060dcc  movzx   ebx, ax
0x180060dcf  or      ebx, r14d
0x180060dd2  test    ebx, ebx
0x180060dd4  js      loc_180060F24
0x180060dda  mov     rcx, [rsp+730h+hkey]; hkey
0x180060ddf  lea     eax, [rsi+rsi]
0x180060de2  mov     [rsp+730h+var_6DC], eax
0x180060de6  mov     r9d, 2; srrfFlags
0x180060dec  lea     rax, [rsp+730h+var_6DC]
0x180060df1  mov     [rsp+730h+pdwType], 1
0x180060df9  mov     [rsp+730h+pcbData], rax; pcbData
0x180060dfe  xor     r8d, r8d; pszValue
0x180060e01  lea     rax, [rsp+730h+pdwType]
0x180060e06  mov     [rsp+730h+pvData], rdi; pvData
0x180060e0b  xor     edx, edx; pszSubKey
0x180060e0d  mov     [rsp+730h+phkResult], rax; pdwType
0x180060e12  call    cs:__imp_SHRegGetValueW
0x180060e19  nop     dword ptr [rax+rax+00h]
0x180060e1e  mov     ebx, eax
0x180060e20  test    eax, eax
0x180060e22  jle     short loc_180060E2A
0x180060e24  movzx   ebx, ax
0x180060e27  or      ebx, r14d
0x180060e2a  test    ebx, ebx
0x180060e2c  js      loc_180060F11
0x180060e32  test    r15b, 7
0x180060e36  jz      loc_180060F11
0x180060e3c  mov     rcx, rdi; pszPath
0x180060e3f  call    cs:__imp_PathFindFileNameW
0x180060e46  nop     dword ptr [rax+rax+00h]
0x180060e4b  mov     rcx, rax; pszStr1
0x180060e4e  lea     rdx, aMscoreeDll; "mscoree.dll"
0x180060e55  call    cs:__imp_StrCmpICW
0x180060e5c  nop     dword ptr [rax+rax+00h]
0x180060e61  test    eax, eax
0x180060e63  jnz     loc_180060F11
0x180060e69  mov     rcx, [rsp+730h+hkey]; hkey
0x180060e6e  lea     rax, [rsp+730h+var_6E8]
0x180060e73  mov     [rsp+730h+pcbData], rax; pcbData
0x180060e78  lea     r8, aCodebase_2; "CodeBase"
0x180060e7f  lea     rax, [rbp+630h+SubKey]
0x180060e83  mov     [rsp+730h+var_6E8], 208h
0x180060e8b  mov     [rsp+730h+pvData], rax; pvData
0x180060e90  mov     r9d, 2; srrfFlags
0x180060e96  lea     rax, [rsp+730h+pdwType]
0x180060e9b  xor     edx, edx; pszSubKey
0x180060e9d  mov     [rsp+730h+phkResult], rax; pdwType
0x180060ea2  call    cs:__imp_SHRegGetValueW
0x180060ea9  nop     dword ptr [rax+rax+00h]
0x180060eae  test    eax, eax
0x180060eb0  jle     short loc_180060EBA
0x180060eb2  movzx   eax, ax
0x180060eb5  or      eax, r14d
0x180060eb8  test    eax, eax
0x180060eba  js      short loc_180060F11
0x180060ebc  lea     rcx, [rbp+630h+SubKey]
0x180060ec0  call    GetUrlSchemeW
0x180060ec5  cmp     eax, 9
0x180060ec8  jnz     short loc_180060F00
0x180060eca  xor     r9d, r9d; dwFlags
0x180060ecd  mov     [rsp+730h+pcchPath], 104h
0x180060ed5  lea     r8, [rsp+730h+pcchPath]; pcchPath
0x180060eda  lea     rdx, [rbp+630h+pszPath]; pszPath
0x180060ee1  lea     rcx, [rbp+630h+SubKey]; pszUrl
0x180060ee5  call    cs:__imp_PathCreateFromUrlW
0x180060eec  nop     dword ptr [rax+rax+00h]
0x180060ef1  mov     ebx, eax
0x180060ef3  test    eax, eax
0x180060ef5  js      short loc_180060F11
0x180060ef7  lea     r8, [rbp+630h+pszPath]
0x180060efe  jmp     short loc_180060F04
0x180060f00  lea     r8, [rbp+630h+SubKey]; unsigned __int16 *
0x180060f04  mov     rdx, rsi; unsigned __int64
0x180060f07  mov     rcx, rdi; unsigned __int16 *
0x180060f0a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180060f0f  mov     ebx, eax
0x180060f11  mov     rcx, [rsp+730h+hkey]; hKey
0x180060f16  call    cs:__imp_RegCloseKey
0x180060f1d  nop     dword ptr [rax+rax+00h]
0x180060f22  test    ebx, ebx
0x180060f24  jz      loc_18006102B
0x180060f2a  cmp     [rsp+730h+sz], r13w
0x180060f30  jz      loc_180061088
0x180060f36  test    r15b, 6
0x180060f3a  jz      loc_180061088
0x180060f40  lea     rax, aLocalserver32; "LocalServer32"
0x180060f47  mov     edx, 104h; unsigned __int64
0x180060f4c  lea     r9, [rsp+730h+sz]
0x180060f51  mov     [rsp+730h+phkResult], rax
0x180060f56  lea     r8, aClsidSS; "CLSID\\%s\\%s"
0x180060f5d  lea     rcx, [rbp+630h+SubKey]; unsigned __int16 *
0x180060f61  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180060f66  mov     ebx, eax
0x180060f68  test    eax, eax
0x180060f6a  js      loc_180061027
0x180060f70  lea     eax, [rsi+rsi]
0x180060f73  mov     ecx, 1
0x180060f78  mov     [rsp+730h+pcchPath], eax
0x180060f7c  lea     rdx, [rbp+630h+SubKey]; lpSubKey
0x180060f80  mov     [rsp+730h+var_6E8], ecx
0x180060f84  test    r15b, 10h
0x180060f88  jz      short loc_180060FA2
0x180060f8a  mov     r9, r12; enum _EXT_ARCHITECTURE *
0x180060f8d  lea     r8, [rsp+730h+hkey]; HKEY *
0x180060f92  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180060f99  call    ?Ext_GetArchitectureHelper@@YAJPEAUHKEY__@@PEBGPEAPEAU1@PEAW4_EXT_ARCHITECTURE@@@Z; Ext_GetArchitectureHelper(HKEY__ *,ushort const *,HKEY__ * *,_EXT_ARCHITECTURE *)
0x180060f9e  mov     ebx, eax
0x180060fa0  jmp     short loc_180060FD1
0x180060fa2  lea     rax, [rsp+730h+hkey]
0x180060fa7  mov     r9d, ecx; samDesired
0x180060faa  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180060fb1  mov     [rsp+730h+phkResult], rax; phkResult
0x180060fb6  xor     r8d, r8d; ulOptions
0x180060fb9  call    cs:__imp_RegOpenKeyExW
0x180060fc0  nop     dword ptr [rax+rax+00h]
0x180060fc5  mov     ebx, eax
0x180060fc7  test    eax, eax
0x180060fc9  jle     short loc_180060FD1
0x180060fcb  movzx   ebx, ax
0x180060fce  or      ebx, r14d
0x180060fd1  test    ebx, ebx
0x180060fd3  js      short loc_180061029
0x180060fd5  mov     rcx, [rsp+730h+hkey]; hkey
0x180060fda  lea     rax, [rsp+730h+pcchPath]
0x180060fdf  mov     [rsp+730h+pcbData], rax; pcbData
0x180060fe4  mov     r9d, 2; srrfFlags
0x180060fea  lea     rax, [rsp+730h+var_6E8]
0x180060fef  mov     [rsp+730h+pvData], rdi; pvData
0x180060ff4  xor     r8d, r8d; pszValue
0x180060ff7  mov     [rsp+730h+phkResult], rax; pdwType
0x180060ffc  xor     edx, edx; pszSubKey
0x180060ffe  call    cs:__imp_SHRegGetValueW
0x180061005  nop     dword ptr [rax+rax+00h]
0x18006100a  mov     ebx, eax
0x18006100c  test    eax, eax
0x18006100e  jle     short loc_180061016
0x180061010  movzx   ebx, ax
0x180061013  or      ebx, r14d
0x180061016  mov     rcx, [rsp+730h+hkey]; hKey
0x18006101b  call    cs:__imp_RegCloseKey
0x180061022  nop     dword ptr [rax+rax+00h]
0x180061027  test    ebx, ebx
0x180061029  jnz     short loc_180061088
0x18006102b  lea     rax, [rbp+630h+szLongPath]
0x180061032  cmp     rdi, rax
0x180061035  jz      short loc_180061088
0x180061037  mov     rcx, rdi; lpsz
0x18006103a  call    cs:__imp_PathUnquoteSpacesW
0x180061041  nop     dword ptr [rax+rax+00h]
0x180061046  mov     r8d, 104h; cchBuffer
0x18006104c  lea     rdx, [rbp+630h+szLongPath]; lpszLongPath
0x180061053  mov     rcx, rdi; lpszShortPath
0x180061056  call    cs:__imp_GetLongPathNameW
0x18006105d  nop     dword ptr [rax+rax+00h]
0x180061062  lea     r8d, [rax-1]
0x180061066  cmp     r8d, 102h
0x18006106d  ja      short loc_180061088
0x18006106f  mov     eax, eax
0x180061071  cmp     rax, rsi
0x180061074  jnb     short loc_180061088
0x180061076  lea     r8, [rbp+630h+szLongPath]; unsigned __int16 *
0x18006107d  mov     rdx, rsi; unsigned __int64
0x180061080  mov     rcx, rdi; unsigned __int16 *
0x180061083  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180061088  mov     eax, ebx
0x18006108a  mov     rcx, [rbp+630h+var_40]
0x180061091  xor     rcx, rsp; StackCookie
0x180061094  call    __security_check_cookie
0x180061099  mov     rbx, [rsp+730h+arg_18]
0x1800610a1  add     rsp, 700h
0x1800610a8  pop     r15
0x1800610aa  pop     r14
0x1800610ac  pop     r13
0x1800610ae  pop     r12
0x1800610b0  pop     rdi
0x1800610b1  pop     rsi
0x1800610b2  pop     rbp
0x1800610b3  retn
```
