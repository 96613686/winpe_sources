# CThemeFile::get_Background(ushort * *)

- ea: `0x180009bd0`
- end: `0x180009e8d`
- name: `?get_Background@CThemeFile@@UEAAJPEAPEAG@Z`
- size: `701`
- prototype: `__int64 __fastcall(CThemeFile *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800089c0`
- `0x180009bd0`
- `0x18000a9a0`
- `0x18000d490`
- `0x18000dd60`
- `0x180015660`
- `0x1800358c0`
- `0x18003633c`
- `0x1800427dc`
- `0x18004b7e8`
- `0x18006d010`

## import_xrefs

- `SHLWAPI!StrCmpIW` at `0x180009ccf`
- `SHLWAPI!StrCmpIW` at `0x180009ccf`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x180009e36`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x180009e36`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180009c7e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180009c7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009d2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009e81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009d2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009e81`
- `OLEAUT32!__imp_SysAllocString` at `0x180009d0a`
- `OLEAUT32!__imp_SysAllocString` at `0x180009d0a`
- `OLEAUT32!__imp_SysFreeString` at `0x180009c95`
- `OLEAUT32!__imp_SysFreeString` at `0x180009c95`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CThemeFile::get_Background(const unsigned __int16 **this, unsigned __int16 **a2)
{
  __int64 result; // rax
  WCHAR *v5; // rbx
  OLECHAR *v6; // rsi
  HRESULT CachedProfile; // edi
  unsigned __int16 *v8; // rax
  int v9; // eax
  struct ICachedPrivateProfile *v10; // r15
  unsigned int v11; // edx
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // [rsp+40h] [rbp-C0h] BYREF
  PCWSTR pszSource; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR *v16; // [rsp+50h] [rbp-B0h] BYREF
  struct ICachedPrivateProfile *v17; // [rsp+58h] [rbp-A8h] BYREF
  OLECHAR *v18; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Buffer[264]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v20[264]; // [rsp+280h] [rbp+180h] BYREF

  *a2 = 0;
  v14 = 0;
  result = (*((__int64 (__fastcall **)(const unsigned __int16 **, int *))*this + 54))(this, &v14);
  if ( (int)result >= 0 )
  {
    if ( !v14 )
    {
      v5 = 0;
      v16 = 0;
      v6 = 0;
      v18 = 0;
      v17 = 0;
      CachedProfile = CThemeFile::_GetCachedProfile((CThemeFile *)(this - 2), 1, &v17);
      if ( CachedProfile >= 0 )
      {
        pszSource = 0;
        v9 = StringCchPrintfW(v20, 0x104u, L"%s.MUI", L"Wallpaper");
        v10 = v17;
        if ( v9 >= 0
          && (*(int (__fastcall **)(struct ICachedPrivateProfile *, const WCHAR *, unsigned __int16 *, _QWORD, int, PCWSTR *))(*(_QWORD *)v17 + 48LL))(
               v17,
               L"Control Panel\\Desktop",
               v20,
               0,
               1,
               &pszSource) >= 0
          || (CachedProfile = (*(__int64 (__fastcall **)(struct ICachedPrivateProfile *, const WCHAR *, const WCHAR *, _QWORD, int, PCWSTR *))(*(_QWORD *)v10 + 48LL))(
                                v10,
                                L"Control Panel\\Desktop",
                                L"Wallpaper",
                                0,
                                1,
                                &pszSource),
              CachedProfile >= 0) )
        {
          memset_0(Buffer, 0, 0x208u);
          CachedProfile = SHLoadIndirectString(pszSource, Buffer, 0x104u, 0);
          if ( CachedProfile >= 0 )
          {
            CachedProfile = ExpandResourceDir(Buffer, v11);
            if ( CachedProfile >= 0 )
            {
              CachedProfile = ExpandThemeTokens(this[4], Buffer);
              if ( CachedProfile >= 0 )
              {
                CachedProfile = _AllocString<CTCoAllocPolicy>(v13, v12, Buffer, &v18);
                v6 = v18;
              }
            }
          }
          CoTaskMemFree((LPVOID)pszSource);
        }
        (*(void (__fastcall **)(struct ICachedPrivateProfile *))(*(_QWORD *)v10 + 16LL))(v10);
        if ( CachedProfile < 0 )
          goto LABEL_7;
        CachedProfile = 0;
        v5 = SysAllocString(v6);
        v16 = v5;
        if ( v6 && !v5 )
          CachedProfile = -2147024882;
        CoTaskMemFree(v6);
      }
      if ( CachedProfile >= 0 )
      {
        if ( LoadStringW(g_hinst, 0x7E6u, Buffer, 260) )
        {
          if ( !StrCmpIW(Buffer, v5) )
          {
            ATL::CComBSTR::operator=(&v16, &Default);
            v5 = v16;
          }
        }
        v8 = v5;
        v5 = 0;
        *a2 = v8;
      }
LABEL_7:
      SysFreeString(v5);
      return (unsigned int)CachedProfile;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_f86c7d449eb73dc42ae2fc23b21f20e6_Traceguids, this[4]);
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x180009bd0  mov     [rsp-8+arg_10], rbx
0x180009bd5  push    rbp
0x180009bd6  push    rsi
0x180009bd7  push    rdi
0x180009bd8  push    r12
0x180009bda  push    r13
0x180009bdc  push    r14
0x180009bde  push    r15
0x180009be0  lea     rbp, [rsp-3A0h]
0x180009be8  sub     rsp, 4A0h
0x180009bef  mov     rax, cs:__security_cookie
0x180009bf6  xor     rax, rsp
0x180009bf9  mov     [rbp+3D0h+var_40], rax
0x180009c00  mov     r12, rdx
0x180009c03  mov     r14, rcx
0x180009c06  xor     r13d, r13d
0x180009c09  mov     [rdx], r13
0x180009c0c  mov     [rsp+4D0h+var_490], r13d
0x180009c11  mov     rax, [rcx]
0x180009c14  lea     rdx, [rsp+4D0h+var_490]
0x180009c19  mov     rax, [rax+1B0h]
0x180009c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c25  test    eax, eax
0x180009c27  js      short loc_180009C9D
0x180009c29  cmp     [rsp+4D0h+var_490], r13d
0x180009c2e  jnz     loc_180009D36
0x180009c34  mov     ebx, r13d
0x180009c37  mov     [rsp+4D0h+var_480], rbx
0x180009c3c  mov     esi, r13d
0x180009c3f  mov     [rsp+4D0h+var_470], r13
0x180009c44  mov     [rsp+4D0h+var_478], r13
0x180009c49  lea     r8, [rsp+4D0h+var_478]; struct ICachedPrivateProfile **
0x180009c4e  mov     dl, 1; bool
0x180009c50  lea     rcx, [r14-10h]; this
0x180009c54  call    ?_GetCachedProfile@CThemeFile@@AEAAJ_NPEAPEAUICachedPrivateProfile@@@Z; CThemeFile::_GetCachedProfile(bool,ICachedPrivateProfile * *)
0x180009c59  mov     edi, eax
0x180009c5b  test    eax, eax
0x180009c5d  jns     loc_180009D72
0x180009c63  test    edi, edi
0x180009c65  js      short loc_180009C92
0x180009c67  mov     r9d, 104h; cchBufferMax
0x180009c6d  lea     r8, [rsp+4D0h+Buffer]; lpBuffer
0x180009c72  mov     edx, 7E6h; uID
0x180009c77  mov     rcx, cs:g_hinst; hInstance
0x180009c7e  call    cs:__imp_LoadStringW
0x180009c84  test    eax, eax
0x180009c86  jnz     short loc_180009CC7
0x180009c88  mov     rax, rbx
0x180009c8b  mov     rbx, r13
0x180009c8e  mov     [r12], rax
0x180009c92  mov     rcx, rbx; bstrString
0x180009c95  call    cs:__imp_SysFreeString
0x180009c9b  mov     eax, edi
0x180009c9d  mov     rcx, [rbp+3D0h+var_40]
0x180009ca4  xor     rcx, rsp; StackCookie
0x180009ca7  call    __security_check_cookie
0x180009cac  mov     rbx, [rsp+4D0h+arg_10]
0x180009cb4  add     rsp, 4A0h
0x180009cbb  pop     r15
0x180009cbd  pop     r14
0x180009cbf  pop     r13
0x180009cc1  pop     r12
0x180009cc3  pop     rdi
0x180009cc4  pop     rsi
0x180009cc5  pop     rbp
0x180009cc6  retn
0x180009cc7  mov     rdx, rbx; psz2
0x180009cca  lea     rcx, [rsp+4D0h+Buffer]; psz1
0x180009ccf  call    cs:__imp_StrCmpIW
0x180009cd5  test    eax, eax
0x180009cd7  jnz     short loc_180009C88
0x180009cd9  lea     rdx, Default
0x180009ce0  lea     rcx, [rsp+4D0h+var_480]
0x180009ce5  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180009cea  mov     rbx, [rsp+4D0h+var_480]
0x180009cef  jmp     short loc_180009C88
0x180009cf1  mov     rax, [r15]
0x180009cf4  mov     rcx, r15
0x180009cf7  mov     rax, [rax+10h]
0x180009cfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d00  test    edi, edi
0x180009d02  js      short loc_180009C92
0x180009d04  mov     edi, r13d
0x180009d07  mov     rcx, rsi; psz
0x180009d0a  call    cs:__imp_SysAllocString
0x180009d10  mov     rbx, rax
0x180009d13  mov     [rsp+4D0h+var_480], rax
0x180009d18  test    rsi, rsi
0x180009d1b  jz      short loc_180009D28
0x180009d1d  mov     eax, 8007000Eh
0x180009d22  test    rbx, rbx
0x180009d25  cmovz   edi, eax
0x180009d28  mov     rcx, rsi; pv
0x180009d2b  call    cs:__imp_CoTaskMemFree
0x180009d31  jmp     loc_180009C63
0x180009d36  lea     rax, WPP_GLOBAL_Control
0x180009d3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d44  cmp     rcx, rax
0x180009d47  jz      short loc_180009D68
0x180009d49  test    byte ptr [rcx+1Ch], 8
0x180009d4d  jz      short loc_180009D68
0x180009d4f  mov     edx, 0Ah
0x180009d54  mov     r9, [r14+20h]
0x180009d58  lea     r8, WPP_f86c7d449eb73dc42ae2fc23b21f20e6_Traceguids
0x180009d5f  mov     rcx, [rcx+10h]
0x180009d63  call    WPP_SF_S
0x180009d68  mov     eax, 80004005h
0x180009d6d  jmp     loc_180009C9D
0x180009d72  mov     [rsp+4D0h+pszSource], r13
0x180009d77  lea     r9, aWallpaper; "Wallpaper"
0x180009d7e  lea     r8, aSMui; "%s.MUI"
0x180009d85  mov     edx, 104h; unsigned __int64
0x180009d8a  lea     rcx, [rbp+3D0h+var_250]; unsigned __int16 *
0x180009d91  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009d96  mov     r15, [rsp+4D0h+var_478]
0x180009d9b  test    eax, eax
0x180009d9d  js      short loc_180009DD5
0x180009d9f  mov     rax, [r15]
0x180009da2  lea     rcx, [rsp+4D0h+pszSource]
0x180009da7  mov     [rsp+4D0h+var_4A8], rcx
0x180009dac  mov     [rsp+4D0h+var_4B0], 1
0x180009db4  xor     r9d, r9d
0x180009db7  lea     r8, [rbp+3D0h+var_250]
0x180009dbe  lea     rdx, aControlPanelDe_0; "Control Panel\\Desktop"
0x180009dc5  mov     rcx, r15
0x180009dc8  mov     rax, [rax+30h]
0x180009dcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dd1  test    eax, eax
0x180009dd3  jns     short loc_180009E11
0x180009dd5  mov     rax, [r15]
0x180009dd8  lea     rcx, [rsp+4D0h+pszSource]
0x180009ddd  mov     [rsp+4D0h+var_4A8], rcx
0x180009de2  mov     [rsp+4D0h+var_4B0], 1
0x180009dea  xor     r9d, r9d
0x180009ded  lea     r8, aWallpaper; "Wallpaper"
0x180009df4  lea     rdx, aControlPanelDe_0; "Control Panel\\Desktop"
0x180009dfb  mov     rcx, r15
0x180009dfe  mov     rax, [rax+30h]
0x180009e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e07  mov     edi, eax
0x180009e09  test    eax, eax
0x180009e0b  js      loc_180009CF1
0x180009e11  xor     edx, edx; Val
0x180009e13  mov     r8d, 208h; Size
0x180009e19  lea     rcx, [rsp+4D0h+Buffer]; void *
0x180009e1e  call    memset_0
0x180009e23  xor     r9d, r9d; ppvReserved
0x180009e26  mov     r8d, 104h; cchOutBuf
0x180009e2c  lea     rdx, [rsp+4D0h+Buffer]; pszOutBuf
0x180009e31  mov     rcx, [rsp+4D0h+pszSource]; pszSource
0x180009e36  call    cs:__imp_SHLoadIndirectString
0x180009e3c  mov     edi, eax
0x180009e3e  test    eax, eax
0x180009e40  js      short loc_180009E7C
0x180009e42  lea     rcx, [rsp+4D0h+Buffer]; unsigned __int16 *
0x180009e47  call    ?ExpandResourceDir@@YAJPEAGK@Z; ExpandResourceDir(ushort *,ulong)
0x180009e4c  mov     edi, eax
0x180009e4e  test    eax, eax
0x180009e50  js      short loc_180009E7C
0x180009e52  lea     rdx, [rsp+4D0h+Buffer]; unsigned __int16 *
0x180009e57  mov     rcx, [r14+20h]; unsigned __int16 *
0x180009e5b  call    ?ExpandThemeTokens@@YAJPEBGPEAGH@Z; ExpandThemeTokens(ushort const *,ushort *,int)
0x180009e60  mov     edi, eax
0x180009e62  test    eax, eax
0x180009e64  js      short loc_180009E7C
0x180009e66  lea     r9, [rsp+4D0h+var_470]
0x180009e6b  lea     r8, [rsp+4D0h+Buffer]
0x180009e70  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180009e75  mov     edi, eax
0x180009e77  mov     rsi, [rsp+4D0h+var_470]
0x180009e7c  mov     rcx, [rsp+4D0h+pszSource]; pv
0x180009e81  call    cs:__imp_CoTaskMemFree
0x180009e87  jmp     loc_180009CF1
```
