# Ext_GetModulePath(_GUID const &,ushort *,unsigned __int64,ulong,_EXT_ARCHITECTURE *)

- ea: `0x18005b884`
- end: `0x18005bc4c`
- name: `?Ext_GetModulePath@@YAJAEBU_GUID@@PEAG_KKPEAW4_EXT_ARCHITECTURE@@@Z`
- size: `968`
- prototype: `int(const struct _GUID *, unsigned __int16 *, unsigned __int64, unsigned int, enum _EXT_ARCHITECTURE *)`
- caller_count: `5`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005b194`
- `0x18005b4dc`
- `0x1800caf48`
- `0x1801034f0`
- `0x18010d9b0`

## callees

- `0x18001054c`
- `0x18001e340`
- `0x18005b884`
- `0x18008f59c`
- `0x18011905c`
- `0x18011baa0`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18005ba13`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18005ba13`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnquoteSpacesW` at `0x18005bbde`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnquoteSpacesW` at `0x18005bbde`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18005ba23`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18005ba23`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bad2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bbc5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bad2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bbc5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005b99a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005bb6f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005b99a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005bb6f`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18005bbf4`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18005bbf4`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x18005baa7`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x18005baa7`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18005b91f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18005b91f`
- `api-ms-win-core-com-l1-1-0!CoGetTreatAsClass` at `0x18005b8d1`
- `api-ms-win-core-com-l1-1-0!CoGetTreatAsClass` at `0x18005b8d1`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x18005b9ec`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x18005ba6a`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x18005bbae`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x18005b9ec`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x18005ba6a`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x18005bbae`

## string_xrefs

- `0x18005b94b`: `CLSID\%s\%s`
- `0x18005bb0c`: `CLSID\%s\%s`
- `0x18005ba1c`: `mscoree.dll`

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
  WCHAR *v18; // r8
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
0x18005b884  mov     [rsp-8+arg_18], rbx
0x18005b889  push    rbp
0x18005b88a  push    rsi
0x18005b88b  push    rdi
0x18005b88c  push    r12
0x18005b88e  push    r13
0x18005b890  push    r14
0x18005b892  push    r15
0x18005b894  lea     rbp, [rsp-600h]
0x18005b89c  sub     rsp, 700h
0x18005b8a3  mov     rax, cs:__security_cookie
0x18005b8aa  xor     rax, rsp
0x18005b8ad  mov     [rbp+630h+var_40], rax
0x18005b8b4  mov     r12, [rbp+630h+arg_20]
0x18005b8bb  mov     r14, rdx
0x18005b8be  xorps   xmm0, xmm0
0x18005b8c1  lea     rdx, [rsp+730h+pClsidNew]; pClsidNew
0x18005b8c6  movups  xmmword ptr [rsp+730h+pClsidNew.Data1], xmm0
0x18005b8cb  mov     r15d, r9d
0x18005b8ce  mov     rdi, r8
0x18005b8d1  call    cs:__imp_CoGetTreatAsClass
0x18005b8d7  xor     r13d, r13d
0x18005b8da  mov     ebx, eax
0x18005b8dc  test    r12, r12
0x18005b8df  jz      short loc_18005B8E5
0x18005b8e1  mov     [r12], r13d
0x18005b8e5  test    r14, r14
0x18005b8e8  mov     esi, 104h
0x18005b8ed  cmovnz  rsi, rdi
0x18005b8f1  lea     rdi, [rbp+630h+szLongPath]
0x18005b8f8  cmovnz  rdi, r14
0x18005b8fc  test    eax, eax
0x18005b8fe  js      loc_18005BC20
0x18005b904  mov     r8d, 27h ; '''; cchMax
0x18005b90a  mov     [rsp+730h+hkey], r13
0x18005b90f  lea     rdx, [rsp+730h+sz]; lpsz
0x18005b914  mov     [rsp+730h+sz], r13w
0x18005b91a  lea     rcx, [rsp+730h+pClsidNew]; rguid
0x18005b91f  call    cs:__imp_StringFromGUID2
0x18005b925  mov     ebx, eax
0x18005b927  mov     r14d, 80070000h
0x18005b92d  test    eax, eax
0x18005b92f  js      loc_18005BAD8
0x18005b935  lea     rax, aInprocserver32; "InProcServer32"
0x18005b93c  mov     edx, 104h; unsigned __int64
0x18005b941  lea     r9, [rsp+730h+sz]
0x18005b946  mov     [rsp+730h+phkResult], rax
0x18005b94b  lea     r8, aClsidSS; "CLSID\\%s\\%s"
0x18005b952  lea     rcx, [rbp+630h+SubKey]; unsigned __int16 *
0x18005b956  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005b95b  mov     ebx, eax
0x18005b95d  test    eax, eax
0x18005b95f  js      loc_18005BAD8
0x18005b965  lea     rdx, [rbp+630h+SubKey]; lpSubKey
0x18005b969  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18005b970  test    r15b, 10h
0x18005b974  jz      short loc_18005B987
0x18005b976  mov     r9, r12; enum _EXT_ARCHITECTURE *
0x18005b979  lea     r8, [rsp+730h+hkey]; HKEY *
0x18005b97e  call    ?Ext_GetArchitectureHelper@@YAJPEAUHKEY__@@PEBGPEAPEAU1@PEAW4_EXT_ARCHITECTURE@@@Z; Ext_GetArchitectureHelper(HKEY__ *,ushort const *,HKEY__ * *,_EXT_ARCHITECTURE *)
0x18005b983  mov     ebx, eax
0x18005b985  jmp     short loc_18005B9AC
0x18005b987  lea     rax, [rsp+730h+hkey]
0x18005b98c  mov     r9d, 1; samDesired
0x18005b992  xor     r8d, r8d; ulOptions
0x18005b995  mov     [rsp+730h+phkResult], rax; phkResult
0x18005b99a  call    cs:__imp_RegOpenKeyExW
0x18005b9a0  mov     ebx, eax
0x18005b9a2  test    eax, eax
0x18005b9a4  jle     short loc_18005B9AC
0x18005b9a6  movzx   ebx, ax
0x18005b9a9  or      ebx, r14d
0x18005b9ac  test    ebx, ebx
0x18005b9ae  js      loc_18005BADA
0x18005b9b4  mov     rcx, [rsp+730h+hkey]; hkey
0x18005b9b9  lea     eax, [rsi+rsi]
0x18005b9bc  mov     [rsp+730h+var_6DC], eax
0x18005b9c0  mov     r9d, 2; srrfFlags
0x18005b9c6  lea     rax, [rsp+730h+var_6DC]
0x18005b9cb  mov     [rsp+730h+pdwType], 1
0x18005b9d3  mov     [rsp+730h+pcbData], rax; pcbData
0x18005b9d8  xor     r8d, r8d; pszValue
0x18005b9db  lea     rax, [rsp+730h+pdwType]
0x18005b9e0  mov     [rsp+730h+pvData], rdi; pvData
0x18005b9e5  xor     edx, edx; pszSubKey
0x18005b9e7  mov     [rsp+730h+phkResult], rax; pdwType
0x18005b9ec  call    cs:__imp_SHRegGetValueW
0x18005b9f2  mov     ebx, eax
0x18005b9f4  test    eax, eax
0x18005b9f6  jle     short loc_18005B9FE
0x18005b9f8  movzx   ebx, ax
0x18005b9fb  or      ebx, r14d
0x18005b9fe  test    ebx, ebx
0x18005ba00  js      loc_18005BACD
0x18005ba06  test    r15b, 7
0x18005ba0a  jz      loc_18005BACD
0x18005ba10  mov     rcx, rdi; pszPath
0x18005ba13  call    cs:__imp_PathFindFileNameW
0x18005ba19  mov     rcx, rax; pszStr1
0x18005ba1c  lea     rdx, aMscoreeDll; "mscoree.dll"
0x18005ba23  call    cs:__imp_StrCmpICW
0x18005ba29  test    eax, eax
0x18005ba2b  jnz     loc_18005BACD
0x18005ba31  mov     rcx, [rsp+730h+hkey]; hkey
0x18005ba36  lea     rax, [rsp+730h+var_6E8]
0x18005ba3b  mov     [rsp+730h+pcbData], rax; pcbData
0x18005ba40  lea     r8, aCodebase_2; "CodeBase"
0x18005ba47  lea     rax, [rbp+630h+SubKey]
0x18005ba4b  mov     [rsp+730h+var_6E8], 208h
0x18005ba53  mov     [rsp+730h+pvData], rax; pvData
0x18005ba58  mov     r9d, 2; srrfFlags
0x18005ba5e  lea     rax, [rsp+730h+pdwType]
0x18005ba63  xor     edx, edx; pszSubKey
0x18005ba65  mov     [rsp+730h+phkResult], rax; pdwType
0x18005ba6a  call    cs:__imp_SHRegGetValueW
0x18005ba70  test    eax, eax
0x18005ba72  jle     short loc_18005BA7C
0x18005ba74  movzx   eax, ax
0x18005ba77  or      eax, r14d
0x18005ba7a  test    eax, eax
0x18005ba7c  js      short loc_18005BACD
0x18005ba7e  lea     rcx, [rbp+630h+SubKey]
0x18005ba82  call    GetUrlSchemeW
0x18005ba87  cmp     eax, 9
0x18005ba8a  jnz     short loc_18005BABC
0x18005ba8c  xor     r9d, r9d; dwFlags
0x18005ba8f  mov     [rsp+730h+pcchPath], 104h
0x18005ba97  lea     r8, [rsp+730h+pcchPath]; pcchPath
0x18005ba9c  lea     rdx, [rbp+630h+pszPath]; pszPath
0x18005baa3  lea     rcx, [rbp+630h+SubKey]; pszUrl
0x18005baa7  call    cs:__imp_PathCreateFromUrlW
0x18005baad  mov     ebx, eax
0x18005baaf  test    eax, eax
0x18005bab1  js      short loc_18005BACD
0x18005bab3  lea     r8, [rbp+630h+pszPath]
0x18005baba  jmp     short loc_18005BAC0
0x18005babc  lea     r8, [rbp+630h+SubKey]; unsigned __int16 *
0x18005bac0  mov     rdx, rsi; unsigned __int64
0x18005bac3  mov     rcx, rdi; unsigned __int16 *
0x18005bac6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005bacb  mov     ebx, eax
0x18005bacd  mov     rcx, [rsp+730h+hkey]; hKey
0x18005bad2  call    cs:__imp_RegCloseKey
0x18005bad8  test    ebx, ebx
0x18005bada  jz      loc_18005BBCF
0x18005bae0  cmp     [rsp+730h+sz], r13w
0x18005bae6  jz      loc_18005BC20
0x18005baec  test    r15b, 6
0x18005baf0  jz      loc_18005BC20
0x18005baf6  lea     rax, aLocalserver32; "LocalServer32"
0x18005bafd  mov     edx, 104h; unsigned __int64
0x18005bb02  lea     r9, [rsp+730h+sz]
0x18005bb07  mov     [rsp+730h+phkResult], rax
0x18005bb0c  lea     r8, aClsidSS; "CLSID\\%s\\%s"
0x18005bb13  lea     rcx, [rbp+630h+SubKey]; unsigned __int16 *
0x18005bb17  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005bb1c  mov     ebx, eax
0x18005bb1e  test    eax, eax
0x18005bb20  js      loc_18005BBCB
0x18005bb26  lea     eax, [rsi+rsi]
0x18005bb29  mov     ecx, 1
0x18005bb2e  mov     [rsp+730h+pcchPath], eax
0x18005bb32  lea     rdx, [rbp+630h+SubKey]; lpSubKey
0x18005bb36  mov     [rsp+730h+var_6E8], ecx
0x18005bb3a  test    r15b, 10h
0x18005bb3e  jz      short loc_18005BB58
0x18005bb40  mov     r9, r12; enum _EXT_ARCHITECTURE *
0x18005bb43  lea     r8, [rsp+730h+hkey]; HKEY *
0x18005bb48  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18005bb4f  call    ?Ext_GetArchitectureHelper@@YAJPEAUHKEY__@@PEBGPEAPEAU1@PEAW4_EXT_ARCHITECTURE@@@Z; Ext_GetArchitectureHelper(HKEY__ *,ushort const *,HKEY__ * *,_EXT_ARCHITECTURE *)
0x18005bb54  mov     ebx, eax
0x18005bb56  jmp     short loc_18005BB81
0x18005bb58  lea     rax, [rsp+730h+hkey]
0x18005bb5d  mov     r9d, ecx; samDesired
0x18005bb60  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18005bb67  mov     [rsp+730h+phkResult], rax; phkResult
0x18005bb6c  xor     r8d, r8d; ulOptions
0x18005bb6f  call    cs:__imp_RegOpenKeyExW
0x18005bb75  mov     ebx, eax
0x18005bb77  test    eax, eax
0x18005bb79  jle     short loc_18005BB81
0x18005bb7b  movzx   ebx, ax
0x18005bb7e  or      ebx, r14d
0x18005bb81  test    ebx, ebx
0x18005bb83  js      short loc_18005BBCD
0x18005bb85  mov     rcx, [rsp+730h+hkey]; hkey
0x18005bb8a  lea     rax, [rsp+730h+pcchPath]
0x18005bb8f  mov     [rsp+730h+pcbData], rax; pcbData
0x18005bb94  mov     r9d, 2; srrfFlags
0x18005bb9a  lea     rax, [rsp+730h+var_6E8]
0x18005bb9f  mov     [rsp+730h+pvData], rdi; pvData
0x18005bba4  xor     r8d, r8d; pszValue
0x18005bba7  mov     [rsp+730h+phkResult], rax; pdwType
0x18005bbac  xor     edx, edx; pszSubKey
0x18005bbae  call    cs:__imp_SHRegGetValueW
0x18005bbb4  mov     ebx, eax
0x18005bbb6  test    eax, eax
0x18005bbb8  jle     short loc_18005BBC0
0x18005bbba  movzx   ebx, ax
0x18005bbbd  or      ebx, r14d
0x18005bbc0  mov     rcx, [rsp+730h+hkey]; hKey
0x18005bbc5  call    cs:__imp_RegCloseKey
0x18005bbcb  test    ebx, ebx
0x18005bbcd  jnz     short loc_18005BC20
0x18005bbcf  lea     rax, [rbp+630h+szLongPath]
0x18005bbd6  cmp     rdi, rax
0x18005bbd9  jz      short loc_18005BC20
0x18005bbdb  mov     rcx, rdi; lpsz
0x18005bbde  call    cs:__imp_PathUnquoteSpacesW
0x18005bbe4  mov     r8d, 104h; cchBuffer
0x18005bbea  lea     rdx, [rbp+630h+szLongPath]; lpszLongPath
0x18005bbf1  mov     rcx, rdi; lpszShortPath
0x18005bbf4  call    cs:__imp_GetLongPathNameW
0x18005bbfa  lea     r8d, [rax-1]
0x18005bbfe  cmp     r8d, 102h
0x18005bc05  ja      short loc_18005BC20
0x18005bc07  mov     eax, eax
0x18005bc09  cmp     rax, rsi
0x18005bc0c  jnb     short loc_18005BC20
0x18005bc0e  lea     r8, [rbp+630h+szLongPath]; unsigned __int16 *
0x18005bc15  mov     rdx, rsi; unsigned __int64
0x18005bc18  mov     rcx, rdi; unsigned __int16 *
0x18005bc1b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005bc20  mov     eax, ebx
0x18005bc22  mov     rcx, [rbp+630h+var_40]
0x18005bc29  xor     rcx, rsp; StackCookie
0x18005bc2c  call    __security_check_cookie
0x18005bc31  mov     rbx, [rsp+730h+arg_18]
0x18005bc39  add     rsp, 700h
0x18005bc40  pop     r15
0x18005bc42  pop     r14
0x18005bc44  pop     r13
0x18005bc46  pop     r12
0x18005bc48  pop     rdi
0x18005bc49  pop     rsi
0x18005bc4a  pop     rbp
0x18005bc4b  retn
```
