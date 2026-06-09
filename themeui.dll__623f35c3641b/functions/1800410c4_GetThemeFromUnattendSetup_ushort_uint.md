# GetThemeFromUnattendSetup(ushort *,uint)

- ea: `0x1800410c4`
- end: `0x18004159d`
- name: `?GetThemeFromUnattendSetup@@YAJPEAGI@Z`
- size: `1241`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180040fcc`

## callees

- `0x18000ab10`
- `0x18000c470`
- `0x18000cc2c`
- `0x1800104c0`
- `0x180015660`
- `0x18001a930`
- `0x18001ea1c`
- `0x18001ed40`
- `0x180030f64`
- `0x1800358c0`
- `0x180040abc`
- `0x18004102c`
- `0x1800410c4`
- `0x180042664`
- `0x18006d010`

## import_xrefs

- `SHLWAPI!PathFileExistsW` at `0x1800410f9`
- `SHLWAPI!PathFileExistsW` at `0x18004120a`
- `SHLWAPI!PathFileExistsW` at `0x1800410f9`
- `SHLWAPI!PathFileExistsW` at `0x18004120a`
- `SHLWAPI!StrToIntExW` at `0x1800413ae`
- `SHLWAPI!StrToIntExW` at `0x1800413ae`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180041153`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800411d0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800412fd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180041367`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180041153`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800411d0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800412fd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180041367`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180041248`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180041248`

## string_xrefs

- `0x180041516`: `shell\themes\themeui\dllreg.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetThemeFromUnattendSetup(unsigned __int16 *a1)
{
  int ValueW; // ebx
  __int16 v3; // ax
  bool v4; // sf
  LSTATUS v5; // eax
  unsigned int v6; // edx
  unsigned int v7; // r8d
  LSTATUS v8; // eax
  bool v9; // sf
  LSTATUS v10; // eax
  unsigned int v11; // r9d
  bool v12; // sf
  unsigned int v13; // r9d
  unsigned int v14; // r9d
  __int64 (__fastcall *v15)(struct ITheme *, GUID *, _QWORD *); // rbx
  int v16; // eax
  int pdwType; // [rsp+20h] [rbp-E0h]
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  struct ITheme *v20; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v21[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszPath[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR NewFileName[264]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR pszString[520]; // [rsp+480h] [rbp+380h] BYREF
  _WORD pvData[520]; // [rsp+890h] [rbp+790h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+CD8h] [rbp+BD8h]

  if ( !PathFileExistsW(a1) )
    return (unsigned int)-2147024809;
  pcbData = 1040;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes",
             L"ThemeName",
             2u,
             0,
             pvData,
             &pcbData);
  if ( ValueW )
  {
    v3 = 0;
    pvData[0] = 0;
    v4 = ValueW < 0;
    if ( ValueW <= 0 )
      goto LABEL_8;
    ValueW = (unsigned __int16)ValueW | 0x80070000;
  }
  else
  {
    v3 = pvData[0];
  }
  v4 = ValueW < 0;
LABEL_8:
  if ( !v4 )
  {
    if ( !v3 )
      ValueW = -2147467259;
    if ( ValueW >= 0 )
    {
      pcbData = 520;
      v5 = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes",
             L"DesktopBackground",
             2u,
             0,
             pszPath,
             &pcbData);
      ValueW = v5;
      if ( v5 )
      {
        pszPath[0] = 0;
        if ( v5 > 0 )
          ValueW = (unsigned __int16)v5 | 0x80070000;
      }
      if ( ValueW >= 0 )
      {
        ValueW = ExpandResourceDir(pszPath, v6);
        if ( ValueW >= 0 )
        {
          if ( PathFileExistsW(pszPath) || (ValueW = ResultFromKnownLastError(), ValueW >= 0) )
          {
            ValueW = GetOEMThemeFileName(1, NewFileName, v7);
            if ( ValueW >= 0 )
            {
              if ( CopyFileW(a1, NewFileName, 0) || (ValueW = ResultFromKnownLastError(), ValueW >= 0) )
              {
                v20 = 0;
                ValueW = CThemeFile_CreateInstance(NewFileName, &v20);
                if ( ValueW >= 0 )
                {
                  ValueW = (*(__int64 (__fastcall **)(struct ITheme *, _WORD *))(*(_QWORD *)v20 + 32LL))(v20, pvData);
                  if ( ValueW >= 0 )
                  {
                    ValueW = (*(__int64 (__fastcall **)(struct ITheme *, WCHAR *))(*(_QWORD *)v20 + 176LL))(
                               v20,
                               pszPath);
                    if ( ValueW >= 0 )
                    {
                      pcbData = 1040;
                      v8 = RegGetValueW(
                             HKEY_LOCAL_MACHINE,
                             L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes",
                             L"BrandIcon",
                             2u,
                             0,
                             pszString,
                             &pcbData);
                      v9 = v8 < 0;
                      if ( v8 )
                      {
                        pszString[0] = 0;
                        if ( v8 > 0 )
                          v9 = 1;
                      }
                      if ( !v9 )
                        (*(void (__fastcall **)(struct ITheme *, WCHAR *))(*(_QWORD *)v20 + 544LL))(v20, pszString);
                      pcbData = 1040;
                      v10 = RegGetValueW(
                              HKEY_LOCAL_MACHINE,
                              L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes",
                              L"WindowColor",
                              2u,
                              0,
                              pszString,
                              &pcbData);
                      v12 = v10 < 0;
                      if ( v10 )
                      {
                        pszString[0] = 0;
                        if ( v10 > 0 )
                          v12 = 1;
                      }
                      if ( !v12 )
                      {
                        pcbData = 0;
                        if ( (CanonicalGlassColorToDWORD(pszString, &pcbData)
                           || StrToIntExW(pszString, 1, (int *)&pcbData))
                          && (*(int (__fastcall **)(struct ITheme *, _QWORD))(*(_QWORD *)v20 + 112LL))(v20, pcbData) >= 0 )
                        {
                          (*(void (__fastcall **)(struct ITheme *, _QWORD))(*(_QWORD *)v20 + 424LL))(v20, 0);
                        }
                      }
                      pcbData = 0;
                      if ( (int)SHRegGetBOOLWithREGSAM(
                                  HKEY_LOCAL_MACHINE,
                                  L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\Background",
                                  L"OEMBackground",
                                  v11,
                                  (int *)&pcbData) >= 0
                        && pcbData )
                      {
                        (*(void (__fastcall **)(struct ITheme *))(*(_QWORD *)v20 + 400LL))(v20);
                      }
                      pcbData = 0;
                      if ( (int)SHRegGetBOOLWithREGSAM(
                                  HKEY_LOCAL_MACHINE,
                                  L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes",
                                  L"UWPAppsUseLightTheme",
                                  v13,
                                  (int *)&pcbData) >= 0 )
                        (*(void (__fastcall **)(struct ITheme *, _QWORD))(*(_QWORD *)v20 + 144LL))(v20, pcbData);
                      wil::details::FeatureImpl<__WilFeatureTraits_Feature_SystemLightTheme>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_SystemLightTheme>::GetImpl'::`2'::impl);
                      if ( (int)SHRegGetBOOLWithREGSAM(
                                  HKEY_LOCAL_MACHINE,
                                  L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes",
                                  L"SystemUsesLightTheme",
                                  v14,
                                  (int *)&pcbData) >= 0 )
                        (*(void (__fastcall **)(struct ITheme *, _QWORD))(*(_QWORD *)v20 + 160LL))(v20, pcbData);
                      if ( IsDesktopSpotlightAllowedByPolicy() )
                      {
                        pcbData = 0;
                        if ( (int)SHRegGetDWORD(
                                    HKEY_LOCAL_MACHINE,
                                    L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes",
                                    L"WindowsSpotlight",
                                    &pcbData) >= 0 )
                        {
                          v21[0] = 0;
                          v15 = **(__int64 (__fastcall ***)(struct ITheme *, GUID *, _QWORD *))v20;
                          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v21);
                          v16 = v15(v20, &GUID_6a0522b4_8e09_4aa8_985a_9e52d534977a, v21);
                          if ( v16 >= 0 )
                            (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v21[0] + 24LL))(v21[0], pcbData);
                          else
                            wil::details::in1diag3::_Log_Hr(
                              retaddr,
                              (void *)0x417,
                              (unsigned int)"shell\\themes\\themeui\\dllreg.cpp",
                              (const char *)(unsigned int)v16,
                              pdwType);
                          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v21);
                        }
                      }
                      ValueW = StringCchCopyW(a1, 0x104u, NewFileName);
                    }
                  }
                  (*(void (__fastcall **)(struct ITheme *))(*(_QWORD *)v20 + 16LL))(v20);
                }
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)ValueW;
}

```

## disassembly

```asm
0x1800410c4  mov     [rsp-8+arg_8], rbx
0x1800410c9  mov     [rsp-8+arg_10], rsi
0x1800410ce  push    rbp
0x1800410cf  push    rdi
0x1800410d0  push    r12
0x1800410d2  push    r14
0x1800410d4  push    r15
0x1800410d6  lea     rbp, [rsp-0BB0h]
0x1800410de  sub     rsp, 0CB0h
0x1800410e5  mov     rax, cs:__security_cookie
0x1800410ec  xor     rax, rsp
0x1800410ef  mov     [rbp+0BD0h+var_30], rax
0x1800410f6  mov     rdi, rcx
0x1800410f9  call    cs:__imp_PathFileExistsW
0x1800410ff  xor     esi, esi
0x180041101  test    eax, eax
0x180041103  jnz     short loc_18004110F
0x180041105  mov     ebx, 80070057h
0x18004110a  jmp     loc_180041570
0x18004110f  mov     [rsp+0CD0h+var_C90], 410h
0x180041117  lea     rax, [rsp+0CD0h+var_C90]
0x18004111c  mov     [rsp+0CD0h+pcbData], rax; pcbData
0x180041121  lea     rax, [rbp+0BD0h+var_440]
0x180041128  mov     [rsp+0CD0h+pvData], rax; pvData
0x18004112d  mov     [rsp+0CD0h+pdwType], rsi; pdwType
0x180041132  mov     r9d, 2; dwFlags
0x180041138  lea     r8, aThemename; "ThemeName"
0x18004113f  lea     r15, pszKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180041146  mov     rdx, r15; lpSubKey
0x180041149  mov     r14, 0FFFFFFFF80000002h
0x180041150  mov     rcx, r14; hkey
0x180041153  call    cs:__imp_RegGetValueW
0x180041159  mov     ebx, eax
0x18004115b  mov     r12d, 80070000h
0x180041161  test    eax, eax
0x180041163  jz      short loc_18004117A
0x180041165  mov     eax, esi
0x180041167  mov     [rbp+0BD0h+var_440], ax
0x18004116e  test    ebx, ebx
0x180041170  jle     short loc_180041183
0x180041172  movzx   ebx, bx
0x180041175  or      ebx, r12d
0x180041178  jmp     short loc_180041181
0x18004117a  movzx   eax, [rbp+0BD0h+var_440]
0x180041181  test    ebx, ebx
0x180041183  js      loc_180041570
0x180041189  mov     ecx, 80004005h
0x18004118e  test    ax, ax
0x180041191  cmovz   ebx, ecx
0x180041194  test    ebx, ebx
0x180041196  js      loc_180041570
0x18004119c  mov     [rsp+0CD0h+var_C90], 208h
0x1800411a4  lea     rax, [rsp+0CD0h+var_C90]
0x1800411a9  mov     [rsp+0CD0h+pcbData], rax; pcbData
0x1800411ae  lea     rax, [rsp+0CD0h+pszPath]
0x1800411b3  mov     [rsp+0CD0h+pvData], rax; pvData
0x1800411b8  mov     [rsp+0CD0h+pdwType], rsi; pdwType
0x1800411bd  mov     r9d, 2; dwFlags
0x1800411c3  lea     r8, aDesktopbackgro; "DesktopBackground"
0x1800411ca  mov     rdx, r15; lpSubKey
0x1800411cd  mov     rcx, r14; hkey
0x1800411d0  call    cs:__imp_RegGetValueW
0x1800411d6  mov     ebx, eax
0x1800411d8  test    eax, eax
0x1800411da  jz      short loc_1800411E9
0x1800411dc  mov     [rsp+0CD0h+pszPath], si
0x1800411e1  jle     short loc_1800411E9
0x1800411e3  movzx   ebx, ax
0x1800411e6  or      ebx, r12d
0x1800411e9  test    ebx, ebx
0x1800411eb  js      loc_180041570
0x1800411f1  lea     rcx, [rsp+0CD0h+pszPath]; unsigned __int16 *
0x1800411f6  call    ?ExpandResourceDir@@YAJPEAGK@Z; ExpandResourceDir(ushort *,ulong)
0x1800411fb  mov     ebx, eax
0x1800411fd  test    eax, eax
0x1800411ff  js      loc_180041570
0x180041205  lea     rcx, [rsp+0CD0h+pszPath]; pszPath
0x18004120a  call    cs:__imp_PathFileExistsW
0x180041210  test    eax, eax
0x180041212  jnz     short loc_180041223
0x180041214  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180041219  mov     ebx, eax
0x18004121b  test    eax, eax
0x18004121d  js      loc_180041570
0x180041223  lea     rdx, [rbp+0BD0h+NewFileName]; unsigned __int16 *
0x18004122a  mov     cl, 1; bool
0x18004122c  call    ?GetOEMThemeFileName@@YAJ_NPEAGI@Z; GetOEMThemeFileName(bool,ushort *,uint)
0x180041231  mov     ebx, eax
0x180041233  test    eax, eax
0x180041235  js      loc_180041570
0x18004123b  xor     r8d, r8d; bFailIfExists
0x18004123e  lea     rdx, [rbp+0BD0h+NewFileName]; lpNewFileName
0x180041245  mov     rcx, rdi; lpExistingFileName
0x180041248  call    cs:__imp_CopyFileW
0x18004124e  test    eax, eax
0x180041250  jnz     short loc_180041261
0x180041252  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180041257  mov     ebx, eax
0x180041259  test    eax, eax
0x18004125b  js      loc_180041570
0x180041261  mov     [rsp+0CD0h+var_C88], rsi
0x180041266  lea     rdx, [rsp+0CD0h+var_C88]; struct ITheme **
0x18004126b  lea     rcx, [rbp+0BD0h+NewFileName]; unsigned __int16 *
0x180041272  call    ?CThemeFile_CreateInstance@@YAJPEBGPEAPEAUITheme@@@Z; CThemeFile_CreateInstance(ushort const *,ITheme * *)
0x180041277  mov     ebx, eax
0x180041279  test    eax, eax
0x18004127b  js      loc_180041570
0x180041281  mov     rcx, [rsp+0CD0h+var_C88]
0x180041286  mov     rax, [rcx]
0x180041289  lea     rdx, [rbp+0BD0h+var_440]
0x180041290  mov     rax, [rax+20h]
0x180041294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041299  mov     ebx, eax
0x18004129b  test    eax, eax
0x18004129d  js      loc_18004155F
0x1800412a3  mov     rcx, [rsp+0CD0h+var_C88]
0x1800412a8  mov     rax, [rcx]
0x1800412ab  lea     rdx, [rsp+0CD0h+pszPath]
0x1800412b0  mov     rax, [rax+0B0h]
0x1800412b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800412bc  mov     ebx, eax
0x1800412be  test    eax, eax
0x1800412c0  js      loc_18004155F
0x1800412c6  mov     ebx, 410h
0x1800412cb  mov     [rsp+0CD0h+var_C90], ebx
0x1800412cf  lea     rax, [rsp+0CD0h+var_C90]
0x1800412d4  mov     [rsp+0CD0h+pcbData], rax; pcbData
0x1800412d9  lea     rax, [rbp+0BD0h+pszString]
0x1800412e0  mov     [rsp+0CD0h+pvData], rax; pvData
0x1800412e5  mov     [rsp+0CD0h+pdwType], rsi; pdwType
0x1800412ea  mov     r9d, 2; dwFlags
0x1800412f0  lea     r8, aBrandicon; "BrandIcon"
0x1800412f7  mov     rdx, r15; lpSubKey
0x1800412fa  mov     rcx, r14; hkey
0x1800412fd  call    cs:__imp_RegGetValueW
0x180041303  test    eax, eax
0x180041305  jz      short loc_180041318
0x180041307  mov     [rbp+0BD0h+pszString], si
0x18004130e  jle     short loc_180041318
0x180041310  movzx   eax, ax
0x180041313  or      eax, r12d
0x180041316  test    eax, eax
0x180041318  js      short loc_180041335
0x18004131a  mov     rcx, [rsp+0CD0h+var_C88]
0x18004131f  mov     rax, [rcx]
0x180041322  lea     rdx, [rbp+0BD0h+pszString]
0x180041329  mov     rax, [rax+220h]
0x180041330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041335  mov     [rsp+0CD0h+var_C90], ebx
0x180041339  lea     rax, [rsp+0CD0h+var_C90]
0x18004133e  mov     [rsp+0CD0h+pcbData], rax; pcbData
0x180041343  lea     rax, [rbp+0BD0h+pszString]
0x18004134a  mov     [rsp+0CD0h+pvData], rax; pvData
0x18004134f  mov     [rsp+0CD0h+pdwType], rsi; pdwType
0x180041354  mov     r9d, 2; dwFlags
0x18004135a  lea     r8, aWindowcolor; "WindowColor"
0x180041361  mov     rdx, r15; lpSubKey
0x180041364  mov     rcx, r14; hkey
0x180041367  call    cs:__imp_RegGetValueW
0x18004136d  test    eax, eax
0x18004136f  jz      short loc_180041382
0x180041371  mov     [rbp+0BD0h+pszString], si
0x180041378  jle     short loc_180041382
0x18004137a  movzx   eax, ax
0x18004137d  or      eax, r12d
0x180041380  test    eax, eax
0x180041382  js      short loc_1800413E7
0x180041384  mov     [rsp+0CD0h+var_C90], esi
0x180041388  lea     rdx, [rsp+0CD0h+var_C90]; unsigned int *
0x18004138d  lea     rcx, [rbp+0BD0h+pszString]; lpString2
0x180041394  call    ?CanonicalGlassColorToDWORD@@YA_NPEBGPEAK@Z; CanonicalGlassColorToDWORD(ushort const *,ulong *)
0x180041399  test    al, al
0x18004139b  jnz     short loc_1800413B8
0x18004139d  lea     r8, [rsp+0CD0h+var_C90]; piRet
0x1800413a2  mov     edx, 1; dwFlags
0x1800413a7  lea     rcx, [rbp+0BD0h+pszString]; pszString
0x1800413ae  call    cs:__imp_StrToIntExW
0x1800413b4  test    eax, eax
0x1800413b6  jz      short loc_1800413E7
0x1800413b8  mov     rcx, [rsp+0CD0h+var_C88]
0x1800413bd  mov     rax, [rcx]
0x1800413c0  mov     edx, [rsp+0CD0h+var_C90]
0x1800413c4  mov     rax, [rax+70h]
0x1800413c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800413cd  test    eax, eax
0x1800413cf  js      short loc_1800413E7
0x1800413d1  mov     rcx, [rsp+0CD0h+var_C88]
0x1800413d6  mov     rax, [rcx]
0x1800413d9  xor     edx, edx
0x1800413db  mov     rax, [rax+1A8h]
0x1800413e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800413e7  mov     [rsp+0CD0h+var_C90], esi
0x1800413eb  lea     rax, [rsp+0CD0h+var_C90]
0x1800413f0  mov     [rsp+0CD0h+pdwType], rax; int *
0x1800413f5  lea     r8, aOembackground_0; "OEMBackground"
0x1800413fc  lea     rdx, aSoftwareMicros_26; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180041403  mov     rcx, r14; HKEY
0x180041406  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x18004140b  test    eax, eax
0x18004140d  js      short loc_180041429
0x18004140f  cmp     [rsp+0CD0h+var_C90], esi
0x180041413  jz      short loc_180041429
0x180041415  mov     rcx, [rsp+0CD0h+var_C88]
0x18004141a  mov     rax, [rcx]
0x18004141d  mov     rax, [rax+190h]
0x180041424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041429  mov     [rsp+0CD0h+var_C90], esi
0x18004142d  lea     rax, [rsp+0CD0h+var_C90]
0x180041432  mov     [rsp+0CD0h+pdwType], rax; int *
0x180041437  lea     r8, aUwpappsuseligh; "UWPAppsUseLightTheme"
0x18004143e  mov     rdx, r15; unsigned __int16 *
0x180041441  mov     rcx, r14; HKEY
0x180041444  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x180041449  test    eax, eax
0x18004144b  js      short loc_180041465
0x18004144d  mov     rcx, [rsp+0CD0h+var_C88]
0x180041452  mov     rax, [rcx]
0x180041455  mov     edx, [rsp+0CD0h+var_C90]
0x180041459  mov     rax, [rax+90h]
0x180041460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041465  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SystemLightTheme@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SystemLightTheme@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SystemLightTheme> `wil::Feature<__WilFeatureTraits_Feature_SystemLightTheme>::GetImpl(void)'::`2'::impl
0x18004146c  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_SystemLightTheme@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SystemLightTheme>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x180041471  lea     rax, [rsp+0CD0h+var_C90]
0x180041476  mov     [rsp+0CD0h+pdwType], rax; int
0x18004147b  lea     r8, aSystemusesligh; "SystemUsesLightTheme"
0x180041482  mov     rdx, r15; unsigned __int16 *
0x180041485  mov     rcx, r14; HKEY
0x180041488  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x18004148d  test    eax, eax
0x18004148f  js      short loc_1800414A9
0x180041491  mov     rcx, [rsp+0CD0h+var_C88]
0x180041496  mov     rax, [rcx]
0x180041499  mov     edx, [rsp+0CD0h+var_C90]
0x18004149d  mov     rax, [rax+0A0h]
0x1800414a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800414a9  call    ?IsDesktopSpotlightAllowedByPolicy@@YA_NXZ; IsDesktopSpotlightAllowedByPolicy(void)
0x1800414ae  test    al, al
0x1800414b0  jz      loc_180041549
0x1800414b6  mov     [rsp+0CD0h+var_C90], esi
0x1800414ba  lea     r9, [rsp+0CD0h+var_C90]; unsigned int *
0x1800414bf  lea     r8, aWindowsspotlig; "WindowsSpotlight"
0x1800414c6  mov     rdx, r15; unsigned __int16 *
0x1800414c9  mov     rcx, r14; HKEY
0x1800414cc  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800414d1  test    eax, eax
0x1800414d3  js      short loc_180041549
0x1800414d5  mov     [rsp+0CD0h+var_C80], rsi
0x1800414da  mov     rax, [rsp+0CD0h+var_C88]
0x1800414df  mov     rcx, [rax]
0x1800414e2  mov     rbx, [rcx]
0x1800414e5  lea     rcx, [rsp+0CD0h+var_C80]
0x1800414ea  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800414ef  lea     r8, [rsp+0CD0h+var_C80]
0x1800414f4  lea     rdx, _GUID_6a0522b4_8e09_4aa8_985a_9e52d534977a
0x1800414fb  mov     rcx, [rsp+0CD0h+var_C88]
0x180041500  mov     rax, rbx
0x180041503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041508  mov     rcx, [rbp+0BD8h]; this
0x18004150f  test    eax, eax
0x180041511  jns     short loc_180041529
0x180041513  mov     r9d, eax; char *
0x180041516  lea     r8, aShellThemesThe_1; "shell\\themes\\themeui\\dllreg.cpp"
0x18004151d  mov     edx, 417h; void *
0x180041522  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180041527  jmp     short loc_18004153F
0x180041529  mov     rcx, [rsp+0CD0h+var_C80]
0x18004152e  mov     rax, [rcx]
0x180041531  mov     edx, [rsp+0CD0h+var_C90]
0x180041535  mov     rax, [rax+18h]
0x180041539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004153e  nop
0x18004153f  lea     rcx, [rsp+0CD0h+var_C80]
0x180041544  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180041549  lea     r8, [rbp+0BD0h+NewFileName]; unsigned __int16 *
0x180041550  mov     edx, 104h; unsigned __int64
0x180041555  mov     rcx, rdi; unsigned __int16 *
0x180041558  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004155d  mov     ebx, eax
0x18004155f  mov     rcx, [rsp+0CD0h+var_C88]
0x180041564  mov     rax, [rcx]
0x180041567  mov     rax, [rax+10h]
0x18004156b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041570  mov     eax, ebx
0x180041572  mov     rcx, [rbp+0BD0h+var_30]
0x180041579  xor     rcx, rsp; StackCookie
0x18004157c  call    __security_check_cookie
0x180041581  lea     r11, [rsp+0CD0h+var_20]
0x180041589  mov     rbx, [r11+38h]
0x18004158d  mov     rsi, [r11+40h]
0x180041591  mov     rsp, r11
0x180041594  pop     r15
0x180041596  pop     r14
0x180041598  pop     r12
0x18004159a  pop     rdi
0x18004159b  pop     rbp
0x18004159c  retn
```
