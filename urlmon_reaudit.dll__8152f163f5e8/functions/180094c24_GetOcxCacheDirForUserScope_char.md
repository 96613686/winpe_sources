# GetOcxCacheDirForUserScope(char *)

- ea: `0x180094c24`
- end: `0x180094ed3`
- name: `?GetOcxCacheDirForUserScope@@YAJPEAD@Z`
- size: `687`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005d404`

## callees

- `0x180028510`
- `0x180064f50`
- `0x180094c24`
- `0x1800bb724`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180094db0`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x180094db0`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180094d85`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180094d85`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180094ce9`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180094d65`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180094ce9`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180094d65`
- `api-ms-win-core-file-l1-1-0!GetShortPathNameW` at `0x180094d19`
- `api-ms-win-core-file-l1-1-0!GetShortPathNameW` at `0x180094d19`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathA` at `0x180094e7d`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathA` at `0x180094e7d`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathW` at `0x180094c81`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathW` at `0x180094c81`

## pseudocode

```c
__int64 __fastcall GetOcxCacheDirForUserScope(char *a1)
{
  int v1; // eax
  unsigned __int64 v2; // rdx
  DWORD ShortPathNameW; // eax
  DWORD v4; // ebx
  int v5; // eax
  HRESULT v6; // ebx
  int v7; // eax
  WINBOOL UsedDefaultChar[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v10; // [rsp+48h] [rbp-B8h] BYREF
  struct IEUserBroker *v11; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR WideCharStr[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR szShortPath[264]; // [rsp+270h] [rbp+170h] BYREF

  if ( (unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_USE_SHORT_NAMES_AX_CDL_KB2310253)
    || SHGetFolderPathW(0, 28, 0, 0, WideCharStr) < 0 )
  {
    goto LABEL_15;
  }
  UsedDefaultChar[0] = 1;
  v10 = 0;
  StringCchLengthW(WideCharStr, 0x104u, &v10);
  v1 = WideCharToMultiByte(0x4E9Fu, 0, WideCharStr, v10 + 1, g_szOCXCacheDirUserScope, 260, 0, UsedDefaultChar);
  if ( UsedDefaultChar[0] || (unsigned int)(v1 - 1) > 0x102 )
  {
    ShortPathNameW = GetShortPathNameW(WideCharStr, szShortPath, 0x104u);
    if ( ShortPathNameW - 1 > 0x102
      || (v4 = ShortPathNameW + 1,
          UsedDefaultChar[0] = 1,
          v5 = WideCharToMultiByte(
                 0x4E9Fu,
                 0,
                 szShortPath,
                 ShortPathNameW + 1,
                 g_szOCXCacheDirUserScope,
                 260,
                 0,
                 UsedDefaultChar),
          UsedDefaultChar[0])
      || v5 != v4 )
    {
LABEL_15:
      if ( (unsigned __int8)IEConfiguration_GetBool(536870915) )
      {
        v10 = 0;
        v11 = 0;
        v6 = CoCreateUserBroker(&v11);
        if ( v6 < 0 )
          goto LABEL_19;
        *(_QWORD *)UsedDefaultChar = 0;
        v6 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, WINBOOL *))(*(_QWORD *)v11 + 48LL))(
               v11,
               &CLSID_CShdocvwBroker,
               &IID_IUnknown,
               UsedDefaultChar);
        if ( v6 >= 0 )
        {
          v6 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, unsigned __int64 *))UsedDefaultChar)(
                 *(_QWORD *)UsedDefaultChar,
                 &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42,
                 &v10);
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)UsedDefaultChar + 16LL))(*(_QWORD *)UsedDefaultChar);
        }
        (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v11 + 16LL))(v11);
        if ( v6 < 0 )
          goto LABEL_19;
        v6 = (*(__int64 (__fastcall **)(unsigned __int64, CHAR *, __int64))(*(_QWORD *)v10 + 1192LL))(
               v10,
               g_szOCXCacheDirUserScope,
               260);
        (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v10 + 16LL))(v10);
      }
      else
      {
        v6 = SHGetFolderPathA(0, 28, 0, 0, g_szOCXCacheDirUserScope);
      }
      if ( v6 < 0 )
      {
LABEL_19:
        g_szOCXCacheDirUserScope[0] = 0;
        return (unsigned int)v6;
      }
    }
  }
  v7 = PathCchAppendA(g_szOCXCacheDirUserScope, v2, "Microsoft\\Internet Explorer\\Downloaded Program Files");
  v6 = v7;
  if ( v7 != 1 )
  {
    if ( v7 >= 0 )
      return (unsigned int)v6;
    goto LABEL_19;
  }
  return 0;
}

```

## disassembly

```asm
0x180094c24  push    rbp
0x180094c26  push    rbx
0x180094c27  push    rsi
0x180094c28  push    r14
0x180094c2a  lea     rbp, [rsp-398h]
0x180094c32  sub     rsp, 498h
0x180094c39  mov     rax, cs:__security_cookie
0x180094c40  xor     rax, rsp
0x180094c43  mov     [rbp+3B0h+var_30], rax
0x180094c4a  lea     rcx, ?FEATURE_USE_SHORT_NAMES_AX_CDL_KB2310253@FCK@@3VCFeatureControlKey@@A; this
0x180094c51  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x180094c56  lea     rsi, ?g_szOCXCacheDirUserScope@@3PADA; char near * g_szOCXCacheDirUserScope
0x180094c5d  mov     r14d, 104h
0x180094c63  test    eax, eax
0x180094c65  jnz     loc_180094D80
0x180094c6b  xor     r9d, r9d; dwFlags
0x180094c6e  lea     rax, [rsp+4B0h+WideCharStr]
0x180094c73  xor     r8d, r8d; hToken
0x180094c76  mov     [rsp+4B0h+pszPath], rax; pszPath
0x180094c7b  xor     ecx, ecx; hwnd
0x180094c7d  lea     edx, [r9+1Ch]; csidl
0x180094c81  call    cs:__imp_SHGetFolderPathW
0x180094c88  nop     dword ptr [rax+rax+00h]
0x180094c8d  test    eax, eax
0x180094c8f  js      loc_180094D80
0x180094c95  lea     r8, [rsp+4B0h+var_468]; unsigned __int64 *
0x180094c9a  mov     [rsp+4B0h+UsedDefaultChar], 1
0x180094ca2  mov     edx, r14d; unsigned __int64
0x180094ca5  mov     [rsp+4B0h+var_468], 0
0x180094cae  lea     rcx, [rsp+4B0h+WideCharStr]; unsigned __int16 *
0x180094cb3  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180094cb8  mov     r9d, dword ptr [rsp+4B0h+var_468]
0x180094cbd  lea     rax, [rsp+4B0h+UsedDefaultChar]
0x180094cc2  mov     [rsp+4B0h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x180094cc7  lea     r8, [rsp+4B0h+WideCharStr]; lpWideCharStr
0x180094ccc  mov     [rsp+4B0h+lpDefaultChar], 0; lpDefaultChar
0x180094cd5  inc     r9d; cchWideChar
0x180094cd8  mov     [rsp+4B0h+cbMultiByte], r14d; cbMultiByte
0x180094cdd  xor     edx, edx; dwFlags
0x180094cdf  mov     ecx, 4E9Fh; CodePage
0x180094ce4  mov     [rsp+4B0h+pszPath], rsi; lpMultiByteStr
0x180094ce9  call    cs:__imp_WideCharToMultiByte
0x180094cf0  nop     dword ptr [rax+rax+00h]
0x180094cf5  cmp     [rsp+4B0h+UsedDefaultChar], 0
0x180094cfa  lea     ebx, [r14-2]
0x180094cfe  jnz     short loc_180094D0A
0x180094d00  dec     eax
0x180094d02  cmp     eax, ebx
0x180094d04  jbe     loc_180094E8F
0x180094d0a  mov     r8d, r14d; cchBuffer
0x180094d0d  lea     rdx, [rbp+3B0h+szShortPath]; lpszShortPath
0x180094d14  lea     rcx, [rsp+4B0h+WideCharStr]; lpszLongPath
0x180094d19  call    cs:__imp_GetShortPathNameW
0x180094d20  nop     dword ptr [rax+rax+00h]
0x180094d25  lea     edx, [rax-1]
0x180094d28  cmp     edx, ebx
0x180094d2a  ja      short loc_180094D80
0x180094d2c  lea     ebx, [rax+1]
0x180094d2f  mov     [rsp+4B0h+UsedDefaultChar], 1
0x180094d37  lea     rax, [rsp+4B0h+UsedDefaultChar]
0x180094d3c  mov     r9d, ebx; cchWideChar
0x180094d3f  mov     [rsp+4B0h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x180094d44  lea     r8, [rbp+3B0h+szShortPath]; lpWideCharStr
0x180094d4b  mov     [rsp+4B0h+lpDefaultChar], 0; lpDefaultChar
0x180094d54  xor     edx, edx; dwFlags
0x180094d56  mov     [rsp+4B0h+cbMultiByte], r14d; cbMultiByte
0x180094d5b  mov     ecx, 4E9Fh; CodePage
0x180094d60  mov     [rsp+4B0h+pszPath], rsi; lpMultiByteStr
0x180094d65  call    cs:__imp_WideCharToMultiByte
0x180094d6c  nop     dword ptr [rax+rax+00h]
0x180094d71  cmp     [rsp+4B0h+UsedDefaultChar], 0
0x180094d76  jnz     short loc_180094D80
0x180094d78  cmp     eax, ebx
0x180094d7a  jz      loc_180094E8F
0x180094d80  mov     ecx, 20000003h
0x180094d85  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180094d8c  nop     dword ptr [rax+rax+00h]
0x180094d91  test    al, al
0x180094d93  jz      loc_180094E6C
0x180094d99  lea     rcx, [rsp+4B0h+var_460]
0x180094d9e  mov     [rsp+4B0h+var_468], 0
0x180094da7  mov     [rsp+4B0h+var_460], 0
0x180094db0  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x180094db7  nop     dword ptr [rax+rax+00h]
0x180094dbc  mov     ebx, eax
0x180094dbe  test    eax, eax
0x180094dc0  js      loc_180094EAD
0x180094dc6  mov     rcx, [rsp+4B0h+var_460]
0x180094dcb  lea     r9, [rsp+4B0h+UsedDefaultChar]
0x180094dd0  mov     qword ptr [rsp+4B0h+UsedDefaultChar], 0
0x180094dd9  lea     r8, IID_IUnknown
0x180094de0  lea     rdx, CLSID_CShdocvwBroker
0x180094de7  mov     rax, [rcx]
0x180094dea  mov     rax, [rax+30h]
0x180094dee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094df3  mov     ebx, eax
0x180094df5  test    eax, eax
0x180094df7  js      short loc_180094E28
0x180094df9  mov     rcx, qword ptr [rsp+4B0h+UsedDefaultChar]
0x180094dfe  lea     r8, [rsp+4B0h+var_468]
0x180094e03  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x180094e0a  mov     rax, [rcx]
0x180094e0d  mov     rax, [rax]
0x180094e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094e15  mov     rcx, qword ptr [rsp+4B0h+UsedDefaultChar]
0x180094e1a  mov     ebx, eax
0x180094e1c  mov     rax, [rcx]
0x180094e1f  mov     rax, [rax+10h]
0x180094e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094e28  mov     rcx, [rsp+4B0h+var_460]
0x180094e2d  mov     rax, [rcx]
0x180094e30  mov     rax, [rax+10h]
0x180094e34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094e39  test    ebx, ebx
0x180094e3b  js      short loc_180094EAD
0x180094e3d  mov     rcx, [rsp+4B0h+var_468]
0x180094e42  mov     r8d, r14d
0x180094e45  mov     rdx, rsi
0x180094e48  mov     rax, [rcx]
0x180094e4b  mov     rax, [rax+4A8h]
0x180094e52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094e57  mov     rcx, [rsp+4B0h+var_468]
0x180094e5c  mov     ebx, eax
0x180094e5e  mov     rax, [rcx]
0x180094e61  mov     rax, [rax+10h]
0x180094e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094e6a  jmp     short loc_180094E8B
0x180094e6c  xor     r9d, r9d; dwFlags
0x180094e6f  mov     [rsp+4B0h+pszPath], rsi; pszPath
0x180094e74  xor     r8d, r8d; hToken
0x180094e77  xor     ecx, ecx; hwnd
0x180094e79  lea     edx, [r9+1Ch]; csidl
0x180094e7d  call    cs:__imp_SHGetFolderPathA
0x180094e84  nop     dword ptr [rax+rax+00h]
0x180094e89  mov     ebx, eax
0x180094e8b  test    ebx, ebx
0x180094e8d  js      short loc_180094EAD
0x180094e8f  lea     r8, aMicrosoftInter; "Microsoft\\Internet Explorer\\Downloade"...
0x180094e96  mov     rcx, rsi; char *
0x180094e99  call    ?PathCchAppendA@@YAJPEAD_KPEBD@Z; PathCchAppendA(char *,unsigned __int64,char const *)
0x180094e9e  mov     ebx, eax
0x180094ea0  cmp     eax, 1
0x180094ea3  jnz     short loc_180094EA9
0x180094ea5  xor     ebx, ebx
0x180094ea7  jmp     short loc_180094EB4
0x180094ea9  test    eax, eax
0x180094eab  jns     short loc_180094EB4
0x180094ead  mov     cs:?g_szOCXCacheDirUserScope@@3PADA, 0; char near * g_szOCXCacheDirUserScope
0x180094eb4  mov     eax, ebx
0x180094eb6  mov     rcx, [rbp+3B0h+var_30]
0x180094ebd  xor     rcx, rsp; StackCookie
0x180094ec0  call    __security_check_cookie
0x180094ec5  add     rsp, 498h
0x180094ecc  pop     r14
0x180094ece  pop     rsi
0x180094ecf  pop     rbx
0x180094ed0  pop     rbp
0x180094ed1  retn
```
