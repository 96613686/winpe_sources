# CThemeManager2::InstallThemePack(HWND__ *,ushort const *,int,THEMEPACK_FLAGS,ushort * *,ITheme * *)

- ea: `0x1800547c0`
- end: `0x180054a74`
- name: `?InstallThemePack@CThemeManager2@@UEAAJPEAUHWND__@@PEBGHW4THEMEPACK_FLAGS@@PEAPEAGPEAPEAUITheme@@@Z`
- size: `692`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000dd60`
- `0x18000ed70`
- `0x1800104c0`
- `0x180017a10`
- `0x1800358c0`
- `0x18003633c`
- `0x1800547c0`
- `0x180055e38`
- `0x180056538`
- `0x1800628c4`
- `0x180062a50`
- `0x180062f3c`
- `0x18006ad80`
- `0x18006d010`

## import_xrefs

- `SHELL32!SHGetFolderPathEx` at `0x180054897`
- `SHELL32!SHGetFolderPathEx` at `0x180054897`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180054978`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180054978`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180054a11`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180054a11`
- `OLEAUT32!__imp_SysFreeString` at `0x180054a08`
- `OLEAUT32!__imp_SysFreeString` at `0x180054a08`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CThemeManager2::InstallThemePack(
        void **a1,
        __int64 a2,
        OLECHAR *a3,
        int a4,
        unsigned int a5,
        __int64 a6,
        struct ITheme **a7)
{
  int InstallThemeMutex; // ebx
  CThemeManager2 *v11; // rcx
  HWND v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r9
  int v15; // eax
  BSTR bstrString; // [rsp+30h] [rbp-D0h] BYREF
  struct ITheme *v18; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v19; // [rsp+40h] [rbp-C0h]
  _QWORD v20[622]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[64]; // [rsp+13C0h] [rbp+12C0h] BYREF
  unsigned __int16 v22[264]; // [rsp+1440h] [rbp+1340h] BYREF

  bstrString = a3;
  v19 = a2;
  if ( a7 )
    *a7 = 0;
  CThemePackManager::CThemePackManager((CThemePackManager *)v20);
  v20[0] = a2;
  v20[1] = g_hinst;
  if ( !g_hinst )
  {
    InstallThemeMutex = -2147467259;
    goto LABEL_29;
  }
  v18 = 0;
  InstallThemeMutex = CThemeFile_CreateInstance(0, &v18);
  if ( InstallThemeMutex >= 0 )
  {
    memset_0(v22, 0, 0x208u);
    InstallThemeMutex = SHGetFolderPathEx(&FOLDERID_LocalAppData, 0, 0, v22, 260);
    if ( InstallThemeMutex < 0 )
      goto LABEL_25;
    InstallThemeMutex = StringCchCatW(v22, 0x104u, L"\\Microsoft\\Windows\\Themes");
    if ( InstallThemeMutex < 0 )
      goto LABEL_25;
    InstallThemeMutex = CThemeManager2::_GetInstallThemeMutex(v11, a1 + 263);
    if ( InstallThemeMutex < 0 )
      goto LABEL_25;
    InstallThemeMutex = CThemePackManager::InstallThemePack((__int64)v20, (__int64)bstrString, v22, a5, v18);
    if ( InstallThemeMutex < 0 )
    {
LABEL_24:
      ReleaseMutex(a1[263]);
LABEL_25:
      if ( a7 )
        *a7 = v18;
      else
        (*(void (__fastcall **)(struct ITheme *))(*(_QWORD *)v18 + 16LL))(v18);
      goto LABEL_29;
    }
    bstrString = 0;
    InstallThemeMutex = (*(__int64 (__fastcall **)(struct ITheme *, __int64, BSTR *))(*(_QWORD *)v18 + 288LL))(
                          v18,
                          0xFFFFFFFFLL,
                          &bstrString);
    if ( InstallThemeMutex >= 0 )
    {
      if ( !a4 )
        goto LABEL_21;
      if ( (a5 & 3) != 0 )
      {
        if ( (a5 & 8) != 0 )
        {
          if ( LoadStringW(g_hinst, 0x80Bu, Buffer, 64) )
          {
            InstallThemeMutex = (*(__int64 (__fastcall **)(struct ITheme *, WCHAR *))(*(_QWORD *)v18 + 32LL))(
                                  v18,
                                  Buffer);
            if ( InstallThemeMutex < 0 )
              goto LABEL_23;
            InstallThemeMutex = CThemeManager2::_Refresh((CThemeManager2 *)a1, 1, 1);
            if ( InstallThemeMutex < 0 )
              goto LABEL_23;
          }
          v14 = 128;
        }
        else
        {
          v14 = 0;
        }
        v15 = (*((__int64 (__fastcall **)(void **, __int64, BSTR, __int64, unsigned int))*a1 + 20))(
                a1,
                v19,
                bstrString,
                v14,
                a5);
      }
      else
      {
        v15 = CThemeManager2::_OpenTheme((const WCHAR *)a1, v12, bstrString);
      }
      InstallThemeMutex = v15;
      if ( v15 >= 0 )
      {
LABEL_21:
        if ( a6 )
          InstallThemeMutex = _AllocString<CTCoAllocPolicy>(v13, v12, bstrString, a6);
      }
    }
LABEL_23:
    SysFreeString(bstrString);
    goto LABEL_24;
  }
LABEL_29:
  CThemePackManager::~CThemePackManager((CThemePackManager *)v20);
  return (unsigned int)InstallThemeMutex;
}

```

## disassembly

```asm
0x1800547c0  mov     [rsp-8+arg_18], rbx
0x1800547c5  push    rbp
0x1800547c6  push    rsi
0x1800547c7  push    rdi
0x1800547c8  push    r12
0x1800547ca  push    r13
0x1800547cc  push    r14
0x1800547ce  push    r15
0x1800547d0  lea     rbp, [rsp-1560h]
0x1800547d8  mov     eax, 1660h
0x1800547dd  call    _alloca_probe
0x1800547e2  sub     rsp, rax
0x1800547e5  mov     rax, cs:__security_cookie
0x1800547ec  xor     rax, rsp
0x1800547ef  mov     [rbp+1590h+var_40], rax
0x1800547f6  mov     r13d, r9d
0x1800547f9  mov     [rsp+1690h+bstrString], r8
0x1800547fe  mov     rbx, rdx
0x180054801  mov     [rsp+1690h+var_1650], rdx
0x180054806  mov     r14, rcx
0x180054809  mov     r12, [rbp+1590h+arg_28]
0x180054810  mov     rdi, [rbp+1590h+arg_30]
0x180054817  test    rdi, rdi
0x18005481a  jz      short loc_180054823
0x18005481c  mov     qword ptr [rdi], 0
0x180054823  lea     rcx, [rsp+1690h+var_1640]; this
0x180054828  call    ??0CThemePackManager@@QEAA@XZ; CThemePackManager::CThemePackManager(void)
0x18005482d  nop
0x18005482e  mov     [rsp+1690h+var_1640], rbx
0x180054833  mov     rax, cs:g_hinst
0x18005483a  mov     [rsp+1690h+var_1638], rax
0x18005483f  test    rax, rax
0x180054842  jz      loc_180054A39
0x180054848  mov     [rsp+1690h+var_1658], 0
0x180054851  lea     rdx, [rsp+1690h+var_1658]; struct ITheme **
0x180054856  xor     ecx, ecx; unsigned __int16 *
0x180054858  call    ?CThemeFile_CreateInstance@@YAJPEBGPEAPEAUITheme@@@Z; CThemeFile_CreateInstance(ushort const *,ITheme * *)
0x18005485d  mov     ebx, eax
0x18005485f  test    eax, eax
0x180054861  js      loc_180054A3E
0x180054867  xor     edx, edx; Val
0x180054869  mov     r8d, 208h; Size
0x18005486f  lea     rcx, [rbp+1590h+var_250]; void *
0x180054876  call    memset_0
0x18005487b  mov     esi, 104h
0x180054880  mov     dword ptr [rsp+1690h+var_1670], esi
0x180054884  lea     r9, [rbp+1590h+var_250]
0x18005488b  xor     r8d, r8d
0x18005488e  xor     edx, edx
0x180054890  lea     rcx, FOLDERID_LocalAppData
0x180054897  call    cs:__imp_SHGetFolderPathEx
0x18005489d  mov     ebx, eax
0x18005489f  test    eax, eax
0x1800548a1  js      loc_180054A17
0x1800548a7  lea     r8, aMicrosoftWindo_2; "\\Microsoft\\Windows\\Themes"
0x1800548ae  mov     edx, esi; unsigned __int64
0x1800548b0  lea     rcx, [rbp+1590h+var_250]; unsigned __int16 *
0x1800548b7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800548bc  mov     ebx, eax
0x1800548be  test    eax, eax
0x1800548c0  js      loc_180054A17
0x1800548c6  lea     r15, [r14+838h]
0x1800548cd  mov     rdx, r15; void **
0x1800548d0  call    ?_GetInstallThemeMutex@CThemeManager2@@AEAAJPEAPEAX@Z; CThemeManager2::_GetInstallThemeMutex(void * *)
0x1800548d5  mov     ebx, eax
0x1800548d7  test    eax, eax
0x1800548d9  js      loc_180054A17
0x1800548df  mov     rax, [rsp+1690h+var_1658]
0x1800548e4  mov     [rsp+1690h+var_1670], rax
0x1800548e9  mov     esi, [rbp+1590h+arg_20]
0x1800548ef  mov     r9d, esi
0x1800548f2  lea     r8, [rbp+1590h+var_250]
0x1800548f9  mov     rdx, [rsp+1690h+bstrString]
0x1800548fe  lea     rcx, [rsp+1690h+var_1640]
0x180054903  call    ?InstallThemePack@CThemePackManager@@QEAAJPEBG0W4THEMEPACK_FLAGS@@PEAUITheme@@@Z; CThemePackManager::InstallThemePack(ushort const *,ushort const *,THEMEPACK_FLAGS,ITheme *)
0x180054908  mov     ebx, eax
0x18005490a  test    eax, eax
0x18005490c  js      loc_180054A0E
0x180054912  mov     [rsp+1690h+bstrString], 0
0x18005491b  mov     rcx, [rsp+1690h+var_1658]
0x180054920  mov     rax, [rcx]
0x180054923  or      edx, 0FFFFFFFFh
0x180054926  lea     r8, [rsp+1690h+bstrString]
0x18005492b  mov     rax, [rax+120h]
0x180054932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054937  mov     ebx, eax
0x180054939  test    eax, eax
0x18005493b  js      loc_180054A03
0x180054941  test    r13d, r13d
0x180054944  jz      loc_1800549EF
0x18005494a  test    sil, 3
0x18005494e  jz      loc_1800549DC
0x180054954  test    sil, 8
0x180054958  jnz     short loc_18005495F
0x18005495a  xor     r9d, r9d
0x18005495d  jmp     short loc_1800549BA
0x18005495f  mov     r9d, 40h ; '@'; cchBufferMax
0x180054965  lea     r8, [rbp+1590h+Buffer]; lpBuffer
0x18005496c  mov     edx, 80Bh; uID
0x180054971  mov     rcx, cs:g_hinst; hInstance
0x180054978  call    cs:__imp_LoadStringW
0x18005497e  test    eax, eax
0x180054980  jz      short loc_1800549B4
0x180054982  mov     rcx, [rsp+1690h+var_1658]
0x180054987  mov     rax, [rcx]
0x18005498a  lea     rdx, [rbp+1590h+Buffer]
0x180054991  mov     rax, [rax+20h]
0x180054995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005499a  mov     ebx, eax
0x18005499c  test    eax, eax
0x18005499e  js      short loc_180054A03
0x1800549a0  mov     r8b, 1; bool
0x1800549a3  mov     dl, r8b; bool
0x1800549a6  mov     rcx, r14; this
0x1800549a9  call    ?_Refresh@CThemeManager2@@AEAAJ_N0@Z; CThemeManager2::_Refresh(bool,bool)
0x1800549ae  mov     ebx, eax
0x1800549b0  test    eax, eax
0x1800549b2  js      short loc_180054A03
0x1800549b4  mov     r9d, 80h
0x1800549ba  mov     rax, [r14]
0x1800549bd  mov     dword ptr [rsp+1690h+var_1670], esi
0x1800549c1  mov     r8, [rsp+1690h+bstrString]
0x1800549c6  mov     rdx, [rsp+1690h+var_1650]
0x1800549cb  mov     rcx, r14
0x1800549ce  mov     rax, [rax+0A0h]
0x1800549d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800549da  jmp     short loc_1800549E9
0x1800549dc  mov     r8, [rsp+1690h+bstrString]; unsigned __int16 *
0x1800549e1  mov     rcx, r14; this
0x1800549e4  call    ?_OpenTheme@CThemeManager2@@AEAAJPEAUHWND__@@PEBG@Z; CThemeManager2::_OpenTheme(HWND__ *,ushort const *)
0x1800549e9  mov     ebx, eax
0x1800549eb  test    eax, eax
0x1800549ed  js      short loc_180054A03
0x1800549ef  test    r12, r12
0x1800549f2  jz      short loc_180054A03
0x1800549f4  mov     r9, r12
0x1800549f7  mov     r8, [rsp+1690h+bstrString]
0x1800549fc  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180054a01  mov     ebx, eax
0x180054a03  mov     rcx, [rsp+1690h+bstrString]; bstrString
0x180054a08  call    cs:__imp_SysFreeString
0x180054a0e  mov     rcx, [r15]; hMutex
0x180054a11  call    cs:__imp_ReleaseMutex
0x180054a17  test    rdi, rdi
0x180054a1a  jnz     short loc_180054A2F
0x180054a1c  mov     rcx, [rsp+1690h+var_1658]
0x180054a21  mov     rax, [rcx]
0x180054a24  mov     rax, [rax+10h]
0x180054a28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054a2d  jmp     short loc_180054A3E
0x180054a2f  mov     rax, [rsp+1690h+var_1658]
0x180054a34  mov     [rdi], rax
0x180054a37  jmp     short loc_180054A3E
0x180054a39  mov     ebx, 80004005h
0x180054a3e  lea     rcx, [rsp+1690h+var_1640]; this
0x180054a43  call    ??1CThemePackManager@@QEAA@XZ; CThemePackManager::~CThemePackManager(void)
0x180054a48  mov     eax, ebx
0x180054a4a  mov     rcx, [rbp+1590h+var_40]
0x180054a51  xor     rcx, rsp; StackCookie
0x180054a54  call    __security_check_cookie
0x180054a59  mov     rbx, [rsp+1690h+arg_18]
0x180054a61  add     rsp, 1660h
0x180054a68  pop     r15
0x180054a6a  pop     r14
0x180054a6c  pop     r13
0x180054a6e  pop     r12
0x180054a70  pop     rdi
0x180054a71  pop     rsi
0x180054a72  pop     rbp
0x180054a73  retn
```
