# OpenThemeActionW(HWND__ *,HINSTANCE__ *,ushort const *,int)

- ea: `0x18001c2a0`
- end: `0x18001c57e`
- name: `?OpenThemeActionW@@YAXPEAUHWND__@@PEAUHINSTANCE__@@PEBGH@Z`
- size: `734`
- prototype: `void __fastcall(HWND hWnd, HINSTANCE, WCHAR *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002280`
- `0x180011c5c`
- `0x18001c2a0`
- `0x18001e02c`
- `0x18001e458`
- `0x18001ef54`
- `0x180057010`

## import_xrefs

- `SHELL32!__imp_SHRestricted` at `0x18001c2df`
- `SHELL32!__imp_SHRestricted` at `0x18001c2df`
- `SHLWAPI!PathFindExtensionW` at `0x18001c442`
- `SHLWAPI!PathFindExtensionW` at `0x18001c482`
- `SHLWAPI!PathFindExtensionW` at `0x18001c4bb`
- `SHLWAPI!PathFindExtensionW` at `0x18001c442`
- `SHLWAPI!PathFindExtensionW` at `0x18001c482`
- `SHLWAPI!PathFindExtensionW` at `0x18001c4bb`
- `SHLWAPI!PathRemoveBlanksW` at `0x18001c356`
- `SHLWAPI!PathRemoveBlanksW` at `0x18001c356`
- `SHLWAPI!__imp_SHWindowsPolicy` at `0x18001c39d`
- `SHLWAPI!__imp_SHWindowsPolicy` at `0x18001c39d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001c468`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001c4a5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001c4de`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001c468`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001c4a5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001c4de`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001c40e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001c40e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001c556`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001c556`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18001c372`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x18001c372`
- `ole32!CoInitialize` at `0x18001c3d7`
- `ole32!CoInitialize` at `0x18001c3d7`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
void __fastcall OpenThemeActionW(HWND hWnd, HINSTANCE a2, WCHAR *a3)
{
  unsigned int v5; // r8d
  UINT v6; // ecx
  __int64 v7; // rcx
  __int64 v8; // rdx
  WCHAR *v9; // rax
  WCHAR v10; // r8
  WCHAR *v11; // rcx
  const CHAR *v12; // rdx
  struct IUnknown *v13; // rdx
  unsigned int v14; // r8d
  const WCHAR *ExtensionW; // rax
  const WCHAR *v16; // rax
  const WCHAR *v17; // rax
  LPVOID ppv[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszPath[264]; // [rsp+50h] [rbp-B0h] BYREF

  if ( (unsigned int)CheckIfPersonalizationFeatureIsEnabled() )
  {
    if ( SHRestricted(REST_NOTHEMESTAB) )
    {
      v6 = 703;
LABEL_4:
      ShowMessage(v6, hWnd, v5);
      return;
    }
    if ( a3 )
    {
      v7 = 2147483646;
      v8 = 260;
      v9 = pszPath;
      do
      {
        if ( !v7 )
          break;
        v10 = *a3;
        if ( !*a3 )
          break;
        ++a3;
        *v9++ = v10;
        --v7;
        --v8;
      }
      while ( v8 );
      v11 = v9 - 1;
      if ( v8 )
        v11 = v9;
      *v11 = 0;
      if ( v8 )
      {
        PathRemoveBlanksW(pszPath);
        if ( GetLongPathNameW(pszPath, pszPath, 0x104u) )
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ThemeFileRemoteResource>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ThemeFileRemoteResource>::GetImpl'::`2'::impl) )
          {
            if ( !SHWindowsPolicy(&POLID_EnableThemeFileRemoteResource, v12) )
            {
              LODWORD(ppv[0]) = -1;
              SHMapUrlToZoneEx(pszPath, v13, v14, (unsigned int *)ppv);
              if ( LODWORD(ppv[0]) > 2 )
              {
                v6 = 720;
                goto LABEL_4;
              }
            }
          }
          if ( CoInitialize(0) >= 0 )
          {
            ppv[0] = 0;
            if ( CoCreateInstance(&CLSID_ThemeManager2, 0, 1u, &GUID_c1e8c83e_845d_4d95_81db_e283fdffc000, ppv) >= 0
              && (*(int (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv[0] + 24LL))(ppv[0], 0) >= 0 )
            {
              ExtensionW = PathFindExtensionW(pszPath);
              if ( CompareStringOrdinal(ExtensionW, -1, L".themepack", -1, 1) == 2
                || (v16 = PathFindExtensionW(pszPath), CompareStringOrdinal(v16, -1, L".deskthemepack", -1, 1) == 2) )
              {
                (*(void (__fastcall **)(LPVOID, _QWORD, WCHAR *, __int64, _DWORD, _QWORD, _QWORD))(*(_QWORD *)ppv[0]
                                                                                                 + 136LL))(
                  ppv[0],
                  0,
                  pszPath,
                  1,
                  0,
                  0,
                  0);
              }
              else
              {
                v17 = PathFindExtensionW(pszPath);
                if ( CompareStringOrdinal(v17, -1, L".theme", -1, 1) == 2 )
                  (*(void (__fastcall **)(LPVOID, _QWORD, WCHAR *, _QWORD))(*(_QWORD *)ppv[0] + 152LL))(
                    ppv[0],
                    0,
                    pszPath,
                    0);
              }
            }
            if ( ppv[0] )
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv[0] + 16LL))(ppv[0]);
            CoUninitialize();
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18001c2a0  push    rbp
0x18001c2a2  push    rbx
0x18001c2a3  push    rsi
0x18001c2a4  push    rdi
0x18001c2a5  lea     rbp, [rsp-178h]
0x18001c2ad  sub     rsp, 278h
0x18001c2b4  mov     rax, cs:__security_cookie
0x18001c2bb  xor     rax, rsp
0x18001c2be  mov     [rbp+190h+var_30], rax
0x18001c2c5  mov     rbx, r8
0x18001c2c8  mov     rdi, rcx
0x18001c2cb  call    ?CheckIfPersonalizationFeatureIsEnabled@@YAHXZ; CheckIfPersonalizationFeatureIsEnabled(void)
0x18001c2d0  xor     esi, esi
0x18001c2d2  test    eax, eax
0x18001c2d4  jz      loc_18001C562
0x18001c2da  mov     ecx, 4000005Ch; rest
0x18001c2df  call    cs:__imp_SHRestricted
0x18001c2e6  nop     dword ptr [rax+rax+00h]
0x18001c2eb  test    eax, eax
0x18001c2ed  jz      short loc_18001C301
0x18001c2ef  mov     ecx, 2BFh; uID
0x18001c2f4  mov     rdx, rdi; hWnd
0x18001c2f7  call    ?ShowMessage@@YAXIPEAUHWND__@@I@Z; ShowMessage(uint,HWND__ *,uint)
0x18001c2fc  jmp     loc_18001C562
0x18001c301  test    rbx, rbx
0x18001c304  jz      loc_18001C562
0x18001c30a  mov     ecx, 7FFFFFFEh
0x18001c30f  mov     edx, 104h
0x18001c314  lea     rax, [rsp+290h+pszPath]
0x18001c319  test    rcx, rcx
0x18001c31c  jz      short loc_18001C33D
0x18001c31e  movzx   r8d, word ptr [rbx]
0x18001c322  test    r8w, r8w
0x18001c326  jz      short loc_18001C33D
0x18001c328  add     rbx, 2
0x18001c32c  mov     [rax], r8w
0x18001c330  add     rax, 2
0x18001c334  dec     rcx
0x18001c337  sub     rdx, 1
0x18001c33b  jnz     short loc_18001C319
0x18001c33d  lea     rcx, [rax-2]
0x18001c341  test    rdx, rdx
0x18001c344  cmovnz  rcx, rax
0x18001c348  mov     [rcx], si
0x18001c34b  jz      loc_18001C562
0x18001c351  lea     rcx, [rsp+290h+pszPath]; pszPath
0x18001c356  call    cs:__imp_PathRemoveBlanksW
0x18001c35d  nop     dword ptr [rax+rax+00h]
0x18001c362  mov     r8d, 104h; cchBuffer
0x18001c368  lea     rdx, [rsp+290h+pszPath]; lpszLongPath
0x18001c36d  lea     rcx, [rsp+290h+pszPath]; lpszShortPath
0x18001c372  call    cs:__imp_GetLongPathNameW
0x18001c379  nop     dword ptr [rax+rax+00h]
0x18001c37e  test    eax, eax
0x18001c380  jz      loc_18001C562
0x18001c386  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ThemeFileRemoteResource@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ThemeFileRemoteResource@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ThemeFileRemoteResource> `wil::Feature<__WilFeatureTraits_Feature_ThemeFileRemoteResource>::GetImpl(void)'::`2'::impl
0x18001c38d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ThemeFileRemoteResource@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ThemeFileRemoteResource>::__private_IsEnabled(void)
0x18001c392  test    al, al
0x18001c394  jz      short loc_18001C3D5
0x18001c396  lea     rcx, POLID_EnableThemeFileRemoteResource; pszPath
0x18001c39d  call    cs:__imp_SHWindowsPolicy
0x18001c3a4  nop     dword ptr [rax+rax+00h]
0x18001c3a9  test    eax, eax
0x18001c3ab  jnz     short loc_18001C3D5
0x18001c3ad  mov     dword ptr [rsp+290h+var_250], 0FFFFFFFFh
0x18001c3b5  lea     r9, [rsp+290h+var_250]; unsigned int *
0x18001c3ba  lea     rcx, [rsp+290h+pszPath]; unsigned __int16 *
0x18001c3bf  call    ?SHMapUrlToZoneEx@@YAJPEBGPEAUIUnknown@@KPEAK@Z; SHMapUrlToZoneEx(ushort const *,IUnknown *,ulong,ulong *)
0x18001c3c4  cmp     dword ptr [rsp+290h+var_250], 2
0x18001c3c9  jbe     short loc_18001C3D5
0x18001c3cb  mov     ecx, 2D0h
0x18001c3d0  jmp     loc_18001C2F4
0x18001c3d5  xor     ecx, ecx; pvReserved
0x18001c3d7  call    cs:__imp_CoInitialize
0x18001c3de  nop     dword ptr [rax+rax+00h]
0x18001c3e3  test    eax, eax
0x18001c3e5  js      loc_18001C562
0x18001c3eb  mov     [rsp+290h+var_250], rsi
0x18001c3f0  lea     rax, [rsp+290h+var_250]
0x18001c3f5  mov     [rsp+290h+ppv], rax; ppv
0x18001c3fa  lea     r9, _GUID_c1e8c83e_845d_4d95_81db_e283fdffc000; riid
0x18001c401  xor     edx, edx; pUnkOuter
0x18001c403  lea     r8d, [rdx+1]; dwClsContext
0x18001c407  lea     rcx, CLSID_ThemeManager2; rclsid
0x18001c40e  call    cs:__imp_CoCreateInstance
0x18001c415  nop     dword ptr [rax+rax+00h]
0x18001c41a  test    eax, eax
0x18001c41c  js      loc_18001C53F
0x18001c422  mov     rcx, [rsp+290h+var_250]
0x18001c427  mov     rax, [rcx]
0x18001c42a  xor     edx, edx
0x18001c42c  mov     rax, [rax+18h]
0x18001c430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c435  test    eax, eax
0x18001c437  js      loc_18001C53F
0x18001c43d  lea     rcx, [rsp+290h+pszPath]; pszPath
0x18001c442  call    cs:__imp_PathFindExtensionW
0x18001c449  nop     dword ptr [rax+rax+00h]
0x18001c44e  mov     dword ptr [rsp+290h+ppv], 1; bIgnoreCase
0x18001c456  or      ebx, 0FFFFFFFFh
0x18001c459  mov     r9d, ebx; cchCount2
0x18001c45c  lea     r8, aThemepack; ".themepack"
0x18001c463  mov     edx, ebx; cchCount1
0x18001c465  mov     rcx, rax; lpString1
0x18001c468  call    cs:__imp_CompareStringOrdinal
0x18001c46f  nop     dword ptr [rax+rax+00h]
0x18001c474  cmp     eax, 2
0x18001c477  jz      loc_18001C50F
0x18001c47d  lea     rcx, [rsp+290h+pszPath]; pszPath
0x18001c482  call    cs:__imp_PathFindExtensionW
0x18001c489  nop     dword ptr [rax+rax+00h]
0x18001c48e  mov     dword ptr [rsp+290h+ppv], 1; bIgnoreCase
0x18001c496  mov     r9d, ebx; cchCount2
0x18001c499  lea     r8, aDeskthemepack_0; ".deskthemepack"
0x18001c4a0  mov     edx, ebx; cchCount1
0x18001c4a2  mov     rcx, rax; lpString1
0x18001c4a5  call    cs:__imp_CompareStringOrdinal
0x18001c4ac  nop     dword ptr [rax+rax+00h]
0x18001c4b1  cmp     eax, 2
0x18001c4b4  jz      short loc_18001C50F
0x18001c4b6  lea     rcx, [rsp+290h+pszPath]; pszPath
0x18001c4bb  call    cs:__imp_PathFindExtensionW
0x18001c4c2  nop     dword ptr [rax+rax+00h]
0x18001c4c7  mov     dword ptr [rsp+290h+ppv], 1; bIgnoreCase
0x18001c4cf  mov     r9d, ebx; cchCount2
0x18001c4d2  lea     r8, aTheme; ".theme"
0x18001c4d9  mov     edx, ebx; cchCount1
0x18001c4db  mov     rcx, rax; lpString1
0x18001c4de  call    cs:__imp_CompareStringOrdinal
0x18001c4e5  nop     dword ptr [rax+rax+00h]
0x18001c4ea  cmp     eax, 2
0x18001c4ed  jnz     short loc_18001C53F
0x18001c4ef  mov     rcx, [rsp+290h+var_250]
0x18001c4f4  mov     rax, [rcx]
0x18001c4f7  xor     r9d, r9d
0x18001c4fa  lea     r8, [rsp+290h+pszPath]
0x18001c4ff  xor     edx, edx
0x18001c501  mov     rax, [rax+98h]
0x18001c508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c50d  jmp     short loc_18001C53F
0x18001c50f  mov     rcx, [rsp+290h+var_250]
0x18001c514  mov     rax, [rcx]
0x18001c517  mov     [rsp+290h+var_260], rsi
0x18001c51c  mov     [rsp+290h+var_268], rsi
0x18001c521  mov     dword ptr [rsp+290h+ppv], esi
0x18001c525  mov     r9d, 1
0x18001c52b  lea     r8, [rsp+290h+pszPath]
0x18001c530  xor     edx, edx
0x18001c532  mov     rax, [rax+88h]
0x18001c539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c53e  nop
0x18001c53f  mov     rcx, [rsp+290h+var_250]
0x18001c544  test    rcx, rcx
0x18001c547  jz      short loc_18001C556
0x18001c549  mov     rax, [rcx]
0x18001c54c  mov     rax, [rax+10h]
0x18001c550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c555  nop
0x18001c556  call    cs:__imp_CoUninitialize
0x18001c55d  nop     dword ptr [rax+rax+00h]
0x18001c562  mov     rcx, [rbp+190h+var_30]
0x18001c569  xor     rcx, rsp; StackCookie
0x18001c56c  call    __security_check_cookie
0x18001c571  add     rsp, 278h
0x18001c578  pop     rdi
0x18001c579  pop     rsi
0x18001c57a  pop     rbx
0x18001c57b  pop     rbp
0x18001c57c  retn
```
