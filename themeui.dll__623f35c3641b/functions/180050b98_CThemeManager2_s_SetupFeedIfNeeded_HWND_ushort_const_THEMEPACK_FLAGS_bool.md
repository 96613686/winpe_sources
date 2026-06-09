# CThemeManager2::s_SetupFeedIfNeeded(HWND__ *,ushort const *,THEMEPACK_FLAGS,bool *)

- ea: `0x180050b98`
- end: `0x180050fd6`
- name: `?s_SetupFeedIfNeeded@CThemeManager2@@CAJPEAUHWND__@@PEBGW4THEMEPACK_FLAGS@@PEA_N@Z`
- size: `1086`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180031ee0`

## callees

- `0x18000ab10`
- `0x18001a930`
- `0x1800358c0`
- `0x18003c1f4`
- `0x180050b98`
- `0x180050fdc`
- `0x18006ab10`
- `0x18006d010`

## import_xrefs

- `SHCORE!__imp_SHQueueUserWorkItem` at `0x180050f4a`
- `SHCORE!__imp_SHQueueUserWorkItem` at `0x180050f4a`
- `SHCORE!__imp_SHCreateDirectoryExW` at `0x180050eec`
- `SHCORE!__imp_SHCreateDirectoryExW` at `0x180050eec`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180050d34`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180050d5b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180050d7c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180050d34`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180050d5b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180050d7c`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180050f6b`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180050f6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050ef7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050ef7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180050bfe`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180050bfe`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180050f13`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x180050f13`

## pseudocode

```c
__int64 __fastcall CThemeManager2::s_SetupFeedIfNeeded(HWND a1, const unsigned __int16 *a2, char a3, _BYTE *a4)
{
  HRESULT v8; // ebx
  unsigned int v9; // r9d
  unsigned int v10; // r9d
  const unsigned __int16 *v11; // rdx
  int v12; // eax
  LPUNKNOWN v13; // rcx
  LPUNKNOWN v14; // rcx
  IStream *v15; // rdi
  LPUNKNOWN v16; // rcx
  LPSTREAM ppStm; // [rsp+40h] [rbp-C0h] BYREF
  LPUNKNOWN pUnk; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR pszPath; // [rsp+50h] [rbp-B0h] BYREF
  int v21; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Buffer[128]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pszWindowTitle[128]; // [rsp+170h] [rbp+70h] BYREF
  WCHAR pszContent[256]; // [rsp+270h] [rbp+170h] BYREF

  *a4 = 0;
  v21 = 0;
  ppv = 0;
  v8 = CoCreateInstance(&CLSID_XFeedsManager, 0, 1u, &GUID_5357e238_fb12_4aca_a930_cab7832b84bf, &ppv);
  if ( v8 < 0 )
    return (unsigned int)v8;
  pUnk = 0;
  if ( (*(int (__fastcall **)(LPVOID, const unsigned __int16 *, GUID *, LPUNKNOWN *))(*(_QWORD *)ppv + 56LL))(
         ppv,
         a2,
         &GUID_a44179a4_e0f6_403b_af8d_d080f425a451,
         &pUnk) < 0 )
  {
    pUnk = 0;
  }
  else
  {
    v8 = ((__int64 (__fastcall *)(LPUNKNOWN, int *))pUnk->lpVtbl[9].AddRef)(pUnk, &v21);
    if ( v8 < 0 )
      goto LABEL_40;
  }
  if ( pUnk && v21 )
  {
    *a4 = 1;
  }
  else
  {
    LODWORD(ppStm) = 0;
    LODWORD(pszPath) = 0;
    if ( (int)SHRegGetBOOLWithREGSAM(
                HKEY_LOCAL_MACHINE,
                L"Software\\Policies\\Microsoft\\Internet Explorer\\Feeds",
                L"DisableEnclosureDownload",
                v9,
                (int *)&pszPath) >= 0
      && (_DWORD)pszPath
      || (int)SHRegGetBOOLWithREGSAM(
                HKEY_CURRENT_USER,
                L"Software\\Policies\\Microsoft\\Internet Explorer\\Feeds",
                L"DisableEnclosureDownload",
                v10,
                (int *)&pszPath) >= 0
      && (_DWORD)pszPath )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids);
      v8 = 1;
      if ( LoadStringW(g_hinst, 0xA84u, Buffer, 128)
        && LoadStringW(g_hinst, 0xA85u, pszContent, 256)
        && LoadStringW(g_hinst, 0xA86u, pszWindowTitle, 128) )
      {
        TaskDialog(a1, 0, pszWindowTitle, Buffer, pszContent, 32, (PCWSTR)0xFFFE, 0);
      }
      goto LABEL_40;
    }
    if ( (a3 & 4) != 0 )
    {
      v12 = 1;
    }
    else
    {
      v8 = CThemeManager2::s_ShowRssDownloadPrompt(a1, v11, (int *)&ppStm);
      if ( v8 < 0 )
        goto LABEL_40;
      v12 = (int)ppStm;
    }
    if ( v12 )
    {
      v13 = pUnk;
      if ( !pUnk )
      {
        ppStm = 0;
        v8 = (*(__int64 (__fastcall **)(LPVOID, GUID *, LPSTREAM *))(*(_QWORD *)ppv + 24LL))(
               ppv,
               &GUID_4c963678_3a51_4b88_8531_98b90b6508f2,
               &ppStm);
        if ( v8 < 0 )
          goto LABEL_40;
        v8 = StringCchCopyW(Buffer, 0x78u, a2);
        if ( (int)(v8 + 0x80000000) < 0 || v8 == -2147024774 )
          v8 = (*(__int64 (__fastcall **)(LPSTREAM, WCHAR *, const unsigned __int16 *, GUID *, LPUNKNOWN *))(*(_QWORD *)ppStm + 40LL))(
                 ppStm,
                 Buffer,
                 a2,
                 &GUID_a44179a4_e0f6_403b_af8d_d080f425a451,
                 &pUnk);
        (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppStm + 16LL))(ppStm);
        if ( v8 < 0 )
          goto LABEL_40;
        v13 = pUnk;
      }
      v8 = ((__int64 (__fastcall *)(LPUNKNOWN, __int64))v13->lpVtbl[9].Release)(v13, 1);
      if ( v8 >= 0 )
      {
        v14 = pUnk;
        *a4 = 1;
        pszPath = 0;
        if ( ((int (__fastcall *)(LPUNKNOWN, LPCWSTR *))v14->lpVtbl[7].AddRef)(v14, &pszPath) >= 0 )
        {
          SHCreateDirectoryExW(0, pszPath, 0);
          CoTaskMemFree((LPVOID)pszPath);
        }
        ppStm = 0;
        v8 = CoMarshalInterThreadInterfaceInStream(&GUID_a44179a4_e0f6_403b_af8d_d080f425a451, pUnk, &ppStm);
        if ( v8 >= 0 )
        {
          _InterlockedIncrement((volatile signed __int32 *)&g_cRef);
          if ( !(unsigned int)SHQueueUserWorkItem(RSSDownloadThread, ppStm, 0, 0, 0, 0, 8) )
          {
            v15 = ppStm;
            v8 = -2147467259;
            ppStm = 0;
            if ( v15 )
            {
              CoReleaseMarshalData(v15);
              (*(void (__fastcall **)(IStream *))(*(_QWORD *)v15 + 16LL))(v15);
            }
            _InterlockedDecrement((volatile signed __int32 *)&g_cRef);
          }
        }
      }
    }
  }
LABEL_40:
  v16 = pUnk;
  pUnk = 0;
  if ( v16 )
    ((void (__fastcall *)(LPUNKNOWN))v16->lpVtbl->Release)(v16);
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180050b98  push    rbp
0x180050b9a  push    rbx
0x180050b9b  push    rsi
0x180050b9c  push    rdi
0x180050b9d  push    r12
0x180050b9f  push    r14
0x180050ba1  push    r15
0x180050ba3  lea     rbp, [rsp-380h]
0x180050bab  sub     rsp, 480h
0x180050bb2  mov     rax, cs:__security_cookie
0x180050bb9  xor     rax, rsp
0x180050bbc  mov     [rbp+3B0h+var_40], rax
0x180050bc3  xor     r12d, r12d
0x180050bc6  lea     rax, [rsp+4B0h+var_450]
0x180050bcb  mov     rsi, r9
0x180050bce  mov     [r9], r12b
0x180050bd1  mov     r15d, r8d
0x180050bd4  mov     [rsp+4B0h+var_458], r12d
0x180050bd9  mov     r14, rdx
0x180050bdc  mov     [rsp+4B0h+var_450], r12
0x180050be1  mov     rdi, rcx
0x180050be4  mov     [rsp+4B0h+ppv], rax; ppv
0x180050be9  lea     r8d, [r12+1]; dwClsContext
0x180050bee  xor     edx, edx; pUnkOuter
0x180050bf0  lea     r9, _GUID_5357e238_fb12_4aca_a930_cab7832b84bf; riid
0x180050bf7  lea     rcx, CLSID_XFeedsManager; rclsid
0x180050bfe  call    cs:__imp_CoCreateInstance
0x180050c04  mov     ebx, eax
0x180050c06  test    eax, eax
0x180050c08  js      loc_180050FB3
0x180050c0e  mov     r10, [rsp+4B0h+var_450]
0x180050c13  lea     r9, [rsp+4B0h+pUnk]
0x180050c18  mov     [rsp+4B0h+pUnk], r12
0x180050c1d  lea     r8, _GUID_a44179a4_e0f6_403b_af8d_d080f425a451
0x180050c24  mov     rdx, r14
0x180050c27  mov     rcx, [r10]
0x180050c2a  mov     rax, [rcx+38h]
0x180050c2e  mov     rcx, r10
0x180050c31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050c36  test    eax, eax
0x180050c38  js      short loc_180050C5F
0x180050c3a  mov     rcx, [rsp+4B0h+pUnk]
0x180050c3f  lea     rdx, [rsp+4B0h+var_458]
0x180050c44  mov     rax, [rcx]
0x180050c47  mov     rax, [rax+0E0h]
0x180050c4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050c53  mov     ebx, eax
0x180050c55  test    eax, eax
0x180050c57  js      loc_180050F87
0x180050c5d  jmp     short loc_180050C64
0x180050c5f  mov     [rsp+4B0h+pUnk], r12
0x180050c64  cmp     [rsp+4B0h+pUnk], r12
0x180050c69  jz      short loc_180050C7A
0x180050c6b  cmp     [rsp+4B0h+var_458], r12d
0x180050c70  jz      short loc_180050C7A
0x180050c72  mov     byte ptr [rsi], 1
0x180050c75  jmp     loc_180050F87
0x180050c7a  lea     rax, [rsp+4B0h+pszPath]
0x180050c7f  mov     dword ptr [rsp+4B0h+ppStm], r12d
0x180050c84  lea     r8, aDisableenclosu; "DisableEnclosureDownload"
0x180050c8b  mov     [rsp+4B0h+ppv], rax; int *
0x180050c90  lea     rdx, aSoftwarePolici_1; "Software\\Policies\\Microsoft\\Internet"...
0x180050c97  mov     dword ptr [rsp+4B0h+pszPath], r12d
0x180050c9c  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180050ca3  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x180050ca8  test    eax, eax
0x180050caa  js      short loc_180050CB3
0x180050cac  cmp     dword ptr [rsp+4B0h+pszPath], r12d
0x180050cb1  jnz     short loc_180050CEA
0x180050cb3  lea     rax, [rsp+4B0h+pszPath]
0x180050cb8  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x180050cbf  lea     r8, aDisableenclosu; "DisableEnclosureDownload"
0x180050cc6  mov     [rsp+4B0h+ppv], rax; int *
0x180050ccb  lea     rdx, aSoftwarePolici_1; "Software\\Policies\\Microsoft\\Internet"...
0x180050cd2  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x180050cd7  test    eax, eax
0x180050cd9  js      loc_180050DC4
0x180050cdf  cmp     dword ptr [rsp+4B0h+pszPath], r12d
0x180050ce4  jz      loc_180050DC4
0x180050cea  mov     rcx, cs:WPP_GLOBAL_Control
0x180050cf1  lea     rax, WPP_GLOBAL_Control
0x180050cf8  cmp     rcx, rax
0x180050cfb  jz      short loc_180050D18
0x180050cfd  test    byte ptr [rcx+1Ch], 8
0x180050d01  jz      short loc_180050D18
0x180050d03  mov     rcx, [rcx+10h]
0x180050d07  lea     r8, WPP_2142f6b70e34304a5e651dea6bf0f6a5_Traceguids
0x180050d0e  mov     edx, 24h ; '$'
0x180050d13  call    WPP_SF_
0x180050d18  mov     rcx, cs:g_hinst; hInstance
0x180050d1f  lea     r8, [rsp+4B0h+Buffer]; lpBuffer
0x180050d24  mov     ebx, 1
0x180050d29  mov     edx, 0A84h; uID
0x180050d2e  lea     esi, [rbx+7Fh]
0x180050d31  mov     r9d, esi; cchBufferMax
0x180050d34  call    cs:__imp_LoadStringW
0x180050d3a  test    eax, eax
0x180050d3c  jz      loc_180050F87
0x180050d42  mov     rcx, cs:g_hinst; hInstance
0x180050d49  lea     r8, [rbp+3B0h+pszContent]; lpBuffer
0x180050d50  mov     r9d, 100h; cchBufferMax
0x180050d56  mov     edx, 0A85h; uID
0x180050d5b  call    cs:__imp_LoadStringW
0x180050d61  test    eax, eax
0x180050d63  jz      loc_180050F87
0x180050d69  mov     rcx, cs:g_hinst; hInstance
0x180050d70  lea     r8, [rbp+3B0h+pszWindowTitle]; lpBuffer
0x180050d74  mov     r9d, esi; cchBufferMax
0x180050d77  mov     edx, 0A86h; uID
0x180050d7c  call    cs:__imp_LoadStringW
0x180050d82  test    eax, eax
0x180050d84  jz      loc_180050F87
0x180050d8a  mov     [rsp+4B0h+pnButton], r12; pnButton
0x180050d8f  lea     rax, [rbp+3B0h+pszContent]
0x180050d96  mov     [rsp+4B0h+pszIcon], 0FFFEh; pszIcon
0x180050d9f  lea     r9, [rsp+4B0h+Buffer]; pszMainInstruction
0x180050da4  mov     [rsp+4B0h+dwCommonButtons], 20h ; ' '; dwCommonButtons
0x180050dac  lea     r8, [rbp+3B0h+pszWindowTitle]; pszWindowTitle
0x180050db0  xor     edx, edx; hInstance
0x180050db2  mov     [rsp+4B0h+ppv], rax; pszContent
0x180050db7  mov     rcx, rdi; hwndOwner
0x180050dba  call    TaskDialog
0x180050dbf  jmp     loc_180050F87
0x180050dc4  test    r15b, 4
0x180050dc8  jnz     short loc_180050DE7
0x180050dca  lea     r8, [rsp+4B0h+ppStm]; int *
0x180050dcf  mov     rcx, rdi; HWND
0x180050dd2  call    ?s_ShowRssDownloadPrompt@CThemeManager2@@CAJPEAUHWND__@@PEBGPEAH@Z; CThemeManager2::s_ShowRssDownloadPrompt(HWND__ *,ushort const *,int *)
0x180050dd7  mov     ebx, eax
0x180050dd9  test    eax, eax
0x180050ddb  js      loc_180050F87
0x180050de1  mov     eax, dword ptr [rsp+4B0h+ppStm]
0x180050de5  jmp     short loc_180050DEC
0x180050de7  mov     eax, 1
0x180050dec  test    eax, eax
0x180050dee  jz      loc_180050F87
0x180050df4  mov     rcx, [rsp+4B0h+pUnk]
0x180050df9  test    rcx, rcx
0x180050dfc  jnz     loc_180050E9F
0x180050e02  mov     rcx, [rsp+4B0h+var_450]
0x180050e07  lea     r8, [rsp+4B0h+ppStm]
0x180050e0c  mov     [rsp+4B0h+ppStm], r12
0x180050e11  lea     rdx, _GUID_4c963678_3a51_4b88_8531_98b90b6508f2
0x180050e18  mov     rax, [rcx]
0x180050e1b  mov     rax, [rax+18h]
0x180050e1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050e24  mov     ebx, eax
0x180050e26  test    eax, eax
0x180050e28  js      loc_180050F87
0x180050e2e  mov     r8, r14; unsigned __int16 *
0x180050e31  lea     rcx, [rsp+4B0h+Buffer]; unsigned __int16 *
0x180050e36  mov     edx, 78h ; 'x'; unsigned __int64
0x180050e3b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180050e40  mov     ecx, 80000000h
0x180050e45  mov     ebx, eax
0x180050e47  add     eax, ecx
0x180050e49  test    ecx, eax
0x180050e4b  jnz     short loc_180050E55
0x180050e4d  cmp     ebx, 8007007Ah
0x180050e53  jnz     short loc_180050E81
0x180050e55  mov     rcx, [rsp+4B0h+ppStm]
0x180050e5a  lea     rdx, [rsp+4B0h+pUnk]
0x180050e5f  mov     [rsp+4B0h+ppv], rdx
0x180050e64  lea     r9, _GUID_a44179a4_e0f6_403b_af8d_d080f425a451
0x180050e6b  mov     r8, r14
0x180050e6e  lea     rdx, [rsp+4B0h+Buffer]
0x180050e73  mov     rax, [rcx]
0x180050e76  mov     rax, [rax+28h]
0x180050e7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050e7f  mov     ebx, eax
0x180050e81  mov     rcx, [rsp+4B0h+ppStm]
0x180050e86  mov     rax, [rcx]
0x180050e89  mov     rax, [rax+10h]
0x180050e8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050e92  test    ebx, ebx
0x180050e94  js      loc_180050F87
0x180050e9a  mov     rcx, [rsp+4B0h+pUnk]
0x180050e9f  mov     rax, [rcx]
0x180050ea2  mov     edx, 1
0x180050ea7  mov     rax, [rax+0E8h]
0x180050eae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050eb3  mov     ebx, eax
0x180050eb5  test    eax, eax
0x180050eb7  js      loc_180050F87
0x180050ebd  mov     rcx, [rsp+4B0h+pUnk]
0x180050ec2  lea     rdx, [rsp+4B0h+pszPath]
0x180050ec7  mov     byte ptr [rsi], 1
0x180050eca  mov     [rsp+4B0h+pszPath], r12
0x180050ecf  mov     rax, [rcx]
0x180050ed2  mov     rax, [rax+0B0h]
0x180050ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ede  test    eax, eax
0x180050ee0  js      short loc_180050EFD
0x180050ee2  mov     rdx, [rsp+4B0h+pszPath]; pszPath
0x180050ee7  xor     r8d, r8d; psa
0x180050eea  xor     ecx, ecx; hwnd
0x180050eec  call    cs:__imp_SHCreateDirectoryExW
0x180050ef2  mov     rcx, [rsp+4B0h+pszPath]; pv
0x180050ef7  call    cs:__imp_CoTaskMemFree
0x180050efd  mov     rdx, [rsp+4B0h+pUnk]; pUnk
0x180050f02  lea     r8, [rsp+4B0h+ppStm]; ppStm
0x180050f07  lea     rcx, _GUID_a44179a4_e0f6_403b_af8d_d080f425a451; riid
0x180050f0e  mov     [rsp+4B0h+ppStm], r12
0x180050f13  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x180050f19  mov     ebx, eax
0x180050f1b  test    eax, eax
0x180050f1d  js      short loc_180050F87
0x180050f1f  lock inc cs:?g_cRef@@3KA; ulong g_cRef
0x180050f26  mov     rdx, [rsp+4B0h+ppStm]
0x180050f2b  lea     rcx, ?RSSDownloadThread@@YAKPEAX@Z; RSSDownloadThread(void *)
0x180050f32  mov     dword ptr [rsp+4B0h+pszIcon], 8
0x180050f3a  xor     r9d, r9d
0x180050f3d  mov     qword ptr [rsp+4B0h+dwCommonButtons], r12
0x180050f42  xor     r8d, r8d
0x180050f45  mov     [rsp+4B0h+ppv], r12
0x180050f4a  call    cs:__imp_SHQueueUserWorkItem
0x180050f50  test    eax, eax
0x180050f52  jnz     short loc_180050F87
0x180050f54  mov     rdi, [rsp+4B0h+ppStm]
0x180050f59  mov     ebx, 80004005h
0x180050f5e  mov     [rsp+4B0h+ppStm], r12
0x180050f63  test    rdi, rdi
0x180050f66  jz      short loc_180050F80
0x180050f68  mov     rcx, rdi; pStm
0x180050f6b  call    cs:__imp_CoReleaseMarshalData
0x180050f71  mov     rax, [rdi]
0x180050f74  mov     rcx, rdi
0x180050f77  mov     rax, [rax+10h]
0x180050f7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050f80  lock dec cs:?g_cRef@@3KA; ulong g_cRef
0x180050f87  mov     rcx, [rsp+4B0h+pUnk]
0x180050f8c  mov     [rsp+4B0h+pUnk], r12
0x180050f91  test    rcx, rcx
0x180050f94  jz      short loc_180050FA2
0x180050f96  mov     rax, [rcx]
0x180050f99  mov     rax, [rax+10h]
0x180050f9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050fa2  mov     rcx, [rsp+4B0h+var_450]
0x180050fa7  mov     rax, [rcx]
0x180050faa  mov     rax, [rax+10h]
0x180050fae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050fb3  mov     eax, ebx
0x180050fb5  mov     rcx, [rbp+3B0h+var_40]
0x180050fbc  xor     rcx, rsp; StackCookie
0x180050fbf  call    __security_check_cookie
0x180050fc4  add     rsp, 480h
0x180050fcb  pop     r15
0x180050fcd  pop     r14
0x180050fcf  pop     r12
0x180050fd1  pop     rdi
0x180050fd2  pop     rsi
0x180050fd3  pop     rbx
0x180050fd4  pop     rbp
0x180050fd5  retn
```
