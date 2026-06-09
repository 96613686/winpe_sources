# CThemeManager2::CloneAndSetCurrentTheme(HWND__ *,ushort const *,ushort * *)

- ea: `0x180053890`
- end: `0x180053d42`
- name: `?CloneAndSetCurrentTheme@CThemeManager2@@UEAAJPEAUHWND__@@PEBGPEAPEAG@Z`
- size: `1202`
- prototype: `__int64 __fastcall(CThemeManager2 *__hidden this, HWND, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800089c0`
- `0x180008dd8`
- `0x18000b5ec`
- `0x18000dd60`
- `0x1800104c0`
- `0x18001e1ec`
- `0x18001ed40`
- `0x18001fd60`
- `0x180020250`
- `0x180030f64`
- `0x1800358c0`
- `0x180042664`
- `0x180053890`
- `0x180055f00`
- `0x18006d010`

## import_xrefs

- `SHLWAPI!PathFileExistsW` at `0x1800539f9`
- `SHLWAPI!PathFileExistsW` at `0x1800539f9`
- `SHLWAPI!PathIsFileSpecW` at `0x180053971`
- `SHLWAPI!PathIsFileSpecW` at `0x180053971`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180053cb2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180053cb2`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180053a78`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180053a78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053c18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053c18`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180053cdf`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180053cdf`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180053a3c`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180053a3c`
- `ntdll!WinSqmIncrementDWORD` at `0x1800538d2`
- `ntdll!WinSqmIncrementDWORD` at `0x1800538d2`
- `USER32!SendNotifyMessageW` at `0x180053d19`
- `USER32!SendNotifyMessageW` at `0x180053d19`
- `OLEAUT32!__imp_SysFreeString` at `0x180053c6d`
- `OLEAUT32!__imp_SysFreeString` at `0x180053cfc`
- `OLEAUT32!__imp_SysFreeString` at `0x180053c6d`
- `OLEAUT32!__imp_SysFreeString` at `0x180053cfc`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CThemeManager2::CloneAndSetCurrentTheme(
        CThemeManager2 *this,
        HWND a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  int ThemeFolder; // edi
  CThemeManager2 *v9; // rcx
  unsigned int v10; // r8d
  int v11; // ebx
  OLECHAR *v12; // rbx
  __int64 (__fastcall *v13)(struct ITheme *, GUID *, __int64 *); // rdi
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  _BOOL8 IsDesktopSpotlightEnabled; // rdi
  int v18; // r8d
  int v19; // r9d
  void *v20; // r14
  unsigned int inserted; // eax
  __int64 v22; // rdx
  __int64 v23; // rcx
  int v24; // eax
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  int v27; // [rsp+28h] [rbp-D8h]
  struct ITheme *v28; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v29; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v30; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v32; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp-90h] BYREF
  GUID pguid; // [rsp+78h] [rbp-88h] BYREF
  WCHAR pszPath[264]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v37[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v38[264]; // [rsp+4B0h] [rbp+3B0h] BYREF
  CThemeManager2 *retaddr; // [rsp+708h] [rbp+608h]

  WinSqmIncrementDWORD(0, 3897, 1);
  v29 = 0;
  ThemeFolder = (*(__int64 (__fastcall **)(CThemeManager2 *, unsigned int *))(*(_QWORD *)this + 88LL))(this, &v29);
  if ( ThemeFolder < 0 )
    return (unsigned int)ThemeFolder;
  v32 = 0;
  ThemeFolder = (*(__int64 (__fastcall **)(CThemeManager2 *, _QWORD, __int64 *))(*(_QWORD *)this + 72LL))(
                  this,
                  v29,
                  &v32);
  if ( ThemeFolder < 0 )
    return (unsigned int)ThemeFolder;
  lpExistingFileName = 0;
  ThemeFolder = (*(__int64 (__fastcall **)(__int64, __int64, LPCWSTR *))(*(_QWORD *)v32 + 288LL))(
                  v32,
                  0xFFFFFFFFLL,
                  &lpExistingFileName);
  if ( ThemeFolder >= 0 )
  {
    ThemeFolder = CThemeManager2::_GetThemeFolder(v9, v38, v10);
    if ( ThemeFolder >= 0 )
    {
      if ( PathIsFileSpecW(a3) && (bIgnoreCase = (int)a3, (int)StringCchPrintfW(v37, 0x104u, L"%s\\%s", v38) >= 0)
        || (ThemeFolder = StringCchPrintfW(v37, 0x104u, L"%s\\Theme", v38), ThemeFolder >= 0) )
      {
        ThemeFolder = StringCchPrintfW(pszPath, 0x104u, L"%s.theme", v37);
        if ( ThemeFolder >= 0 )
        {
          v11 = 2;
          while ( PathFileExistsW(pszPath) )
          {
            bIgnoreCase = v11;
            ThemeFolder = StringCchPrintfW(pszPath, 0x104u, L"%s (%d).theme", v37);
            ++v11;
            if ( ThemeFolder < 0 )
              goto LABEL_42;
          }
          if ( !CopyFileW(lpExistingFileName, pszPath, 0) )
          {
            ThemeFolder = ResultFromKnownLastError();
LABEL_37:
            if ( ThemeFolder >= 0 && CompareStringOrdinal(lpExistingFileName, -1, (LPCWCH)this + 266, -1, 1) == 2 )
            {
              v24 = CThemeManager2::_SearchThemeFilePaths(this, (const unsigned __int16 *)this + 266);
              if ( v24 != -1 )
                g_pfn_DPA_DeletePtr(*((HDPA *)this + 264), v24);
              DeleteFileW((LPCWSTR)this + 266);
            }
            goto LABEL_42;
          }
          v28 = 0;
          ThemeFolder = CThemeFile_CreateInstance(pszPath, &v28);
          if ( ThemeFolder >= 0 )
          {
            pguid = 0;
            if ( CoCreateGuid(&pguid) >= 0 )
              (*(void (__fastcall **)(struct ITheme *, GUID *))(*(_QWORD *)v28 + 128LL))(v28, &pguid);
            ThemeFolder = (*(__int64 (__fastcall **)(struct ITheme *))(*(_QWORD *)v28 + 408LL))(v28);
            if ( ThemeFolder >= 0 )
            {
              ThemeFolder = (*(__int64 (__fastcall **)(struct ITheme *))(*(_QWORD *)v28 + 552LL))(v28);
              if ( ThemeFolder >= 0 )
              {
                ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, a3);
                v12 = bstrString;
                if ( bstrString )
                {
                  ThemeFolder = (*(__int64 (__fastcall **)(struct ITheme *, BSTR))(*(_QWORD *)v28 + 32LL))(
                                  v28,
                                  bstrString);
                  if ( ThemeFolder >= 0 )
                  {
                    v30 = 0;
                    v13 = **(__int64 (__fastcall ***)(struct ITheme *, GUID *, __int64 *))v28;
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
                    v14 = v13(v28, &GUID_6a0522b4_8e09_4aa8_985a_9e52d534977a, &v30);
                    if ( v14 >= 0 )
                    {
                      IsDesktopSpotlightEnabled = CThemeManager2::_IsDesktopSpotlightEnabled(retaddr);
                      if ( (*(int (__fastcall **)(__int64, _BOOL8))(*(_QWORD *)v30 + 24LL))(
                             v30,
                             IsDesktopSpotlightEnabled) >= 0
                        && IsDesktopSpotlightEnabled )
                      {
                        (*(void (__fastcall **)(struct ITheme *, _QWORD))(*(_QWORD *)v28 + 440LL))(v28, 0);
                        (*(void (__fastcall **)(struct ITheme *, __int64))(*(_QWORD *)v28 + 192LL))(v28, 4);
                      }
                      else
                      {
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 40LL))(v30);
                      }
                    }
                    else
                    {
                      wil::details::in1diag3::_Log_Hr(
                        retaddr,
                        (void *)0x369,
                        (unsigned int)"shell\\themes\\themeui\\thememanager.cpp",
                        (const char *)(unsigned int)v14,
                        bIgnoreCase);
                    }
                    pv = 0;
                    ThemeFolder = _AllocString<CTCoAllocPolicy>(v16, v15, pszPath, &pv);
                    if ( ThemeFolder >= 0 )
                    {
                      v20 = pv;
                      inserted = CDPA<unsigned short,CTContainer_PolicyUnOwned<unsigned short>>::SortedInsertPtr(
                                   (int)this + 2112,
                                   (int)pv,
                                   v18,
                                   v19,
                                   bIgnoreCase,
                                   v27,
                                   pv);
                      if ( inserted == -1 )
                      {
                        ThemeFolder = -2147467259;
                        CoTaskMemFree(v20);
                      }
                      else
                      {
                        ThemeFolder = (*(__int64 (__fastcall **)(CThemeManager2 *, HWND, _QWORD, _QWORD, _DWORD, _DWORD))(*(_QWORD *)this + 96LL))(
                                        this,
                                        a2,
                                        inserted,
                                        0,
                                        0,
                                        0);
                        if ( ThemeFolder >= 0 )
                          ThemeFolder = _AllocString<CTCoAllocPolicy>(v23, v22, pszPath, a4);
                      }
                    }
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
                  }
                }
                else
                {
                  ThemeFolder = -2147024882;
                }
                SysFreeString(v12);
              }
            }
            (*(void (__fastcall **)(struct ITheme *))(*(_QWORD *)v28 + 16LL))(v28);
            goto LABEL_37;
          }
        }
      }
    }
  }
LABEL_42:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  SysFreeString((BSTR)lpExistingFileName);
  if ( ThemeFolder >= 0 )
    SendNotifyMessageW(HWND_BROADCAST, 0x1Au, 0, (LPARAM)L"WindowsThemeElement");
  return (unsigned int)ThemeFolder;
}

```

## disassembly

```asm
0x180053890  push    rbp
0x180053892  push    rbx
0x180053893  push    rsi
0x180053894  push    rdi
0x180053895  push    r12
0x180053897  push    r14
0x180053899  push    r15
0x18005389b  lea     rbp, [rsp-5D0h]
0x1800538a3  sub     rsp, 6D0h
0x1800538aa  mov     rax, cs:__security_cookie
0x1800538b1  xor     rax, rsp
0x1800538b4  mov     [rbp+600h+var_40], rax
0x1800538bb  mov     r15, r9
0x1800538be  mov     r14, r8
0x1800538c1  mov     r12, rdx
0x1800538c4  mov     rsi, rcx
0x1800538c7  mov     edx, 0F39h
0x1800538cc  xor     ecx, ecx
0x1800538ce  lea     r8d, [rcx+1]
0x1800538d2  call    cs:__imp_WinSqmIncrementDWORD
0x1800538d8  mov     [rsp+700h+var_6B8], 0
0x1800538e0  mov     rax, [rsi]
0x1800538e3  lea     rdx, [rsp+700h+var_6B8]
0x1800538e8  mov     rcx, rsi
0x1800538eb  mov     rax, [rax+58h]
0x1800538ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800538f4  mov     edi, eax
0x1800538f6  test    eax, eax
0x1800538f8  js      loc_180053D1F
0x1800538fe  mov     [rsp+700h+var_6A0], 0
0x180053907  mov     rax, [rsi]
0x18005390a  lea     r8, [rsp+700h+var_6A0]
0x18005390f  mov     edx, [rsp+700h+var_6B8]
0x180053913  mov     rcx, rsi
0x180053916  mov     rax, [rax+48h]
0x18005391a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005391f  mov     edi, eax
0x180053921  test    eax, eax
0x180053923  js      loc_180053D1F
0x180053929  mov     [rsp+700h+lpExistingFileName], 0
0x180053932  mov     rcx, [rsp+700h+var_6A0]
0x180053937  mov     rax, [rcx]
0x18005393a  or      edx, 0FFFFFFFFh
0x18005393d  lea     r8, [rsp+700h+lpExistingFileName]
0x180053942  mov     rax, [rax+120h]
0x180053949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005394e  mov     edi, eax
0x180053950  test    eax, eax
0x180053952  js      loc_180053CE5
0x180053958  lea     rdx, [rbp+600h+var_250]; unsigned __int16 *
0x18005395f  call    ?_GetThemeFolder@CThemeManager2@@AEAAJPEAGI@Z; CThemeManager2::_GetThemeFolder(ushort *,uint)
0x180053964  mov     edi, eax
0x180053966  test    eax, eax
0x180053968  js      loc_180053CE5
0x18005396e  mov     rcx, r14; pszPath
0x180053971  call    cs:__imp_PathIsFileSpecW
0x180053977  mov     ebx, 104h
0x18005397c  test    eax, eax
0x18005397e  jz      short loc_1800539A5
0x180053980  mov     qword ptr [rsp+700h+bIgnoreCase], r14; int
0x180053985  lea     r9, [rbp+600h+var_250]
0x18005398c  lea     r8, aSS; "%s\\%s"
0x180053993  mov     edx, ebx; unsigned __int64
0x180053995  lea     rcx, [rbp+600h+var_460]; unsigned __int16 *
0x18005399c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800539a1  test    eax, eax
0x1800539a3  jns     short loc_1800539CC
0x1800539a5  lea     r9, [rbp+600h+var_250]
0x1800539ac  lea     r8, aSTheme_0; "%s\\Theme"
0x1800539b3  mov     rdx, rbx; unsigned __int64
0x1800539b6  lea     rcx, [rbp+600h+var_460]; unsigned __int16 *
0x1800539bd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800539c2  mov     edi, eax
0x1800539c4  test    eax, eax
0x1800539c6  js      loc_180053CE5
0x1800539cc  lea     r9, [rbp+600h+var_460]
0x1800539d3  lea     r8, aSTheme_1; "%s.theme"
0x1800539da  mov     rdx, rbx; unsigned __int64
0x1800539dd  lea     rcx, [rbp+600h+pszPath]; unsigned __int16 *
0x1800539e1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800539e6  mov     edi, eax
0x1800539e8  test    eax, eax
0x1800539ea  js      loc_180053CE5
0x1800539f0  mov     ebx, 2
0x1800539f5  lea     rcx, [rbp+600h+pszPath]; pszPath
0x1800539f9  call    cs:__imp_PathFileExistsW
0x1800539ff  test    eax, eax
0x180053a01  jz      short loc_180053A30
0x180053a03  mov     [rsp+700h+bIgnoreCase], ebx
0x180053a07  lea     r9, [rbp+600h+var_460]
0x180053a0e  lea     r8, aSDTheme; "%s (%d).theme"
0x180053a15  mov     edx, 104h; unsigned __int64
0x180053a1a  lea     rcx, [rbp+600h+pszPath]; unsigned __int16 *
0x180053a1e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180053a23  mov     edi, eax
0x180053a25  inc     ebx
0x180053a27  test    eax, eax
0x180053a29  jns     short loc_1800539F5
0x180053a2b  jmp     loc_180053CE5
0x180053a30  xor     r8d, r8d; bFailIfExists
0x180053a33  lea     rdx, [rbp+600h+pszPath]; lpNewFileName
0x180053a37  mov     rcx, [rsp+700h+lpExistingFileName]; lpExistingFileName
0x180053a3c  call    cs:__imp_CopyFileW
0x180053a42  test    eax, eax
0x180053a44  jz      loc_180053C86
0x180053a4a  mov     [rsp+700h+var_6C0], 0
0x180053a53  lea     rdx, [rsp+700h+var_6C0]; struct ITheme **
0x180053a58  lea     rcx, [rbp+600h+pszPath]; unsigned __int16 *
0x180053a5c  call    ?CThemeFile_CreateInstance@@YAJPEBGPEAPEAUITheme@@@Z; CThemeFile_CreateInstance(ushort const *,ITheme * *)
0x180053a61  mov     edi, eax
0x180053a63  test    eax, eax
0x180053a65  js      loc_180053CE5
0x180053a6b  xorps   xmm0, xmm0
0x180053a6e  movups  xmmword ptr [rsp+700h+pguid.Data1], xmm0
0x180053a73  lea     rcx, [rsp+700h+pguid]; pguid
0x180053a78  call    cs:__imp_CoCreateGuid
0x180053a7e  test    eax, eax
0x180053a80  js      short loc_180053A9B
0x180053a82  mov     rcx, [rsp+700h+var_6C0]
0x180053a87  mov     rax, [rcx]
0x180053a8a  lea     rdx, [rsp+700h+pguid]
0x180053a8f  mov     rax, [rax+80h]
0x180053a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053a9b  mov     rcx, [rsp+700h+var_6C0]
0x180053aa0  mov     rax, [rcx]
0x180053aa3  mov     rax, [rax+198h]
0x180053aaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053aaf  mov     edi, eax
0x180053ab1  test    eax, eax
0x180053ab3  js      loc_180053C73
0x180053ab9  mov     rcx, [rsp+700h+var_6C0]
0x180053abe  mov     rax, [rcx]
0x180053ac1  mov     rax, [rax+228h]
0x180053ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053acd  mov     edi, eax
0x180053acf  test    eax, eax
0x180053ad1  js      loc_180053C73
0x180053ad7  mov     rdx, r14; unsigned __int16 *
0x180053ada  lea     rcx, [rsp+700h+bstrString]; this
0x180053adf  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180053ae4  nop
0x180053ae5  mov     rbx, [rsp+700h+bstrString]
0x180053aea  test    rbx, rbx
0x180053aed  jz      loc_180053C65
0x180053af3  mov     rcx, [rsp+700h+var_6C0]
0x180053af8  mov     rax, [rcx]
0x180053afb  mov     rdx, rbx
0x180053afe  mov     rax, [rax+20h]
0x180053b02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053b07  mov     edi, eax
0x180053b09  test    eax, eax
0x180053b0b  js      loc_180053C6A
0x180053b11  mov     [rsp+700h+var_6B0], 0
0x180053b1a  mov     rax, [rsp+700h+var_6C0]
0x180053b1f  mov     rcx, [rax]
0x180053b22  mov     rdi, [rcx]
0x180053b25  lea     rcx, [rsp+700h+var_6B0]
0x180053b2a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180053b2f  lea     r8, [rsp+700h+var_6B0]
0x180053b34  lea     rdx, _GUID_6a0522b4_8e09_4aa8_985a_9e52d534977a
0x180053b3b  mov     rcx, [rsp+700h+var_6C0]
0x180053b40  mov     rax, rdi
0x180053b43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053b48  mov     rcx, [rbp+608h]; this
0x180053b4f  test    eax, eax
0x180053b51  jns     short loc_180053B69
0x180053b53  mov     r9d, eax; char *
0x180053b56  lea     r8, aShellThemesThe_6; "shell\\themes\\themeui\\thememanager.cp"...
0x180053b5d  mov     edx, 369h; void *
0x180053b62  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180053b67  jmp     short loc_180053BD2
0x180053b69  call    ?_IsDesktopSpotlightEnabled@CThemeManager2@@AEAA_NXZ; CThemeManager2::_IsDesktopSpotlightEnabled(void)
0x180053b6e  movzx   edi, al
0x180053b71  mov     r8, [rsp+700h+var_6B0]
0x180053b76  mov     rcx, [r8]
0x180053b79  mov     edx, edi
0x180053b7b  mov     rax, [rcx+18h]
0x180053b7f  mov     rcx, r8
0x180053b82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053b87  test    eax, eax
0x180053b89  js      short loc_180053BC1
0x180053b8b  test    dil, dil
0x180053b8e  jz      short loc_180053BC1
0x180053b90  mov     rcx, [rsp+700h+var_6C0]
0x180053b95  mov     rax, [rcx]
0x180053b98  xor     edx, edx
0x180053b9a  mov     rax, [rax+1B8h]
0x180053ba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053ba6  mov     rcx, [rsp+700h+var_6C0]
0x180053bab  mov     rax, [rcx]
0x180053bae  mov     edx, 4
0x180053bb3  mov     rax, [rax+0C0h]
0x180053bba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053bbf  jmp     short loc_180053BD2
0x180053bc1  mov     rcx, [rsp+700h+var_6B0]
0x180053bc6  mov     rax, [rcx]
0x180053bc9  mov     rax, [rax+28h]
0x180053bcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053bd2  mov     [rsp+700h+pv], 0
0x180053bdb  lea     r9, [rsp+700h+pv]
0x180053be0  lea     r8, [rbp+600h+pszPath]
0x180053be4  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180053be9  mov     edi, eax
0x180053beb  test    eax, eax
0x180053bed  js      short loc_180053C59
0x180053bef  lea     rcx, [rsi+840h]; int
0x180053bf6  mov     r14, [rsp+700h+pv]
0x180053bfb  mov     [rsp+700h+p], r14; p
0x180053c00  mov     rdx, r14; int
0x180053c03  call    ?SortedInsertPtr@?$CDPA@GV?$CTContainer_PolicyUnOwned@G@@@@QEAAHPEBGHP6AH00_J@Z1I0@Z; CDPA<ushort,CTContainer_PolicyUnOwned<ushort>>::SortedInsertPtr(ushort const *,int,int (*)(ushort const *,ushort const *,__int64),__int64,uint,ushort const *)
0x180053c08  mov     r8d, eax
0x180053c0b  cmp     eax, 0FFFFFFFFh
0x180053c0e  jnz     short loc_180053C20
0x180053c10  mov     edi, 80004005h
0x180053c15  mov     rcx, r14; pv
0x180053c18  call    cs:__imp_CoTaskMemFree
0x180053c1e  jmp     short loc_180053C59
0x180053c20  mov     rax, [rsi]
0x180053c23  mov     [rsp+700h+var_6D8], 0
0x180053c2b  mov     [rsp+700h+bIgnoreCase], 0
0x180053c33  xor     r9d, r9d
0x180053c36  mov     rdx, r12
0x180053c39  mov     rcx, rsi
0x180053c3c  mov     rax, [rax+60h]
0x180053c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053c45  mov     edi, eax
0x180053c47  test    eax, eax
0x180053c49  js      short loc_180053C59
0x180053c4b  mov     r9, r15
0x180053c4e  lea     r8, [rbp+600h+pszPath]
0x180053c52  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180053c57  mov     edi, eax
0x180053c59  lea     rcx, [rsp+700h+var_6B0]
0x180053c5e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180053c63  jmp     short loc_180053C6A
0x180053c65  mov     edi, 8007000Eh
0x180053c6a  mov     rcx, rbx; bstrString
0x180053c6d  call    cs:__imp_SysFreeString
0x180053c73  mov     rcx, [rsp+700h+var_6C0]
0x180053c78  mov     rax, [rcx]
0x180053c7b  mov     rax, [rax+10h]
0x180053c7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053c84  jmp     short loc_180053C8D
0x180053c86  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180053c8b  mov     edi, eax
0x180053c8d  test    edi, edi
0x180053c8f  js      short loc_180053CE5
0x180053c91  lea     rbx, [rsi+214h]
0x180053c98  mov     [rsp+700h+bIgnoreCase], 1; bIgnoreCase
0x180053ca0  or      r14d, 0FFFFFFFFh
0x180053ca4  mov     r9d, r14d; cchCount2
0x180053ca7  mov     r8, rbx; lpString2
0x180053caa  mov     edx, r14d; cchCount1
0x180053cad  mov     rcx, [rsp+700h+lpExistingFileName]; lpString1
0x180053cb2  call    cs:__imp_CompareStringOrdinal
0x180053cb8  cmp     eax, 2
0x180053cbb  jnz     short loc_180053CE5
0x180053cbd  mov     rdx, rbx; unsigned __int16 *
0x180053cc0  mov     rcx, rsi; this
0x180053cc3  call    ?_SearchThemeFilePaths@CThemeManager2@@AEAAHPEBG@Z; CThemeManager2::_SearchThemeFilePaths(ushort const *)
0x180053cc8  cmp     eax, r14d
0x180053ccb  jz      short loc_180053CDC
0x180053ccd  mov     edx, eax; i
0x180053ccf  mov     rcx, [rsi+840h]; hdpa
0x180053cd6  call    cs:g_pfn_DPA_DeletePtr
0x180053cdc  mov     rcx, rbx; lpFileName
0x180053cdf  call    cs:__imp_DeleteFileW
0x180053ce5  mov     rcx, [rsp+700h+var_6A0]
0x180053cea  mov     rax, [rcx]
0x180053ced  mov     rax, [rax+10h]
0x180053cf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053cf6  nop
0x180053cf7  mov     rcx, [rsp+700h+lpExistingFileName]; bstrString
0x180053cfc  call    cs:__imp_SysFreeString
0x180053d02  test    edi, edi
0x180053d04  js      short loc_180053D1F
0x180053d06  lea     r9, lParam; "WindowsThemeElement"
0x180053d0d  xor     r8d, r8d; wParam
0x180053d10  lea     edx, [r8+1Ah]; Msg
0x180053d14  mov     ecx, 0FFFFh; hWnd
0x180053d19  call    cs:__imp_SendNotifyMessageW
0x180053d1f  mov     eax, edi
0x180053d21  mov     rcx, [rbp+600h+var_40]
0x180053d28  xor     rcx, rsp; StackCookie
0x180053d2b  call    __security_check_cookie
0x180053d30  add     rsp, 6D0h
0x180053d37  pop     r15
0x180053d39  pop     r14
0x180053d3b  pop     r12
0x180053d3d  pop     rdi
0x180053d3e  pop     rsi
0x180053d3f  pop     rbx
0x180053d40  pop     rbp
0x180053d41  retn
```
