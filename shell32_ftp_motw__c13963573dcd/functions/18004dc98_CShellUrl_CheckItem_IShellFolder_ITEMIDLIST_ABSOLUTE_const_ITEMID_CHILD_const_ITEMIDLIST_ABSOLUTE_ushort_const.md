# CShellUrl::_CheckItem(IShellFolder *,_ITEMIDLIST_ABSOLUTE const *,_ITEMID_CHILD const *,_ITEMIDLIST_ABSOLUTE * *,ushort const *,ushort const * *,ulong)

- ea: `0x18004dc98`
- end: `0x18004dfac`
- name: `?_CheckItem@CShellUrl@@AEAAJPEAUIShellFolder@@PEBU_ITEMIDLIST_ABSOLUTE@@PEFBU_ITEMID_CHILD@@PEAPEAU3@PEBGPEAPEBGK@Z`
- size: `788`
- prototype: `__int64 __fastcall(CShellUrl *__hidden this, struct IShellFolder *, const struct _ITEMIDLIST_ABSOLUTE *, const struct _ITEMID_CHILD *, struct _ITEMIDLIST_ABSOLUTE **, LPCWSTR lpString, const unsigned __int16 **, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004d7b4`

## callees

- `0x18004dc98`
- `0x18004dfb4`
- `0x180050970`
- `0x180249490`
- `0x180425758`
- `0x1805a3840`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004dd98`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004de70`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004dd98`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004de70`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x18004de93`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x18004df4c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x18004de93`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x18004df4c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18004dd44`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18004dd55`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18004de35`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18004df23`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18004dd44`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18004dd55`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18004de35`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18004df23`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18004ddee`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18004dee4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18004ddee`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18004dee4`
- `api-ms-win-shell-shellfolders-l1-1-0!PathIsExe` at `0x18004de02`
- `api-ms-win-shell-shellfolders-l1-1-0!PathIsExe` at `0x18004def8`
- `api-ms-win-shell-shellfolders-l1-1-0!PathIsExe` at `0x18004de02`
- `api-ms-win-shell-shellfolders-l1-1-0!PathIsExe` at `0x18004def8`
- `Windows.Storage!ILCombine` at `0x18004df75`
- `Windows.Storage!ILCombine` at `0x18004df75`

## pseudocode

```c
__int64 __fastcall CShellUrl::_CheckItem(
        CShellUrl *this,
        struct IShellFolder *a2,
        const ITEMIDLIST *a3,
        const ITEMIDLIST *a4,
        struct _ITEMIDLIST_ABSOLUTE **a5,
        LPCWSTR lpString,
        const unsigned __int16 **a7,
        unsigned int a8)
{
  unsigned int CanContinue; // r15d
  __int64 v11; // rbx
  unsigned int v12; // esi
  WCHAR v13; // cx
  LPWSTR v14; // rbx
  bool v15; // zf
  WCHAR v16; // cx
  LPWSTR ExtensionW; // rbx
  WCHAR String; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v21; // [rsp+42h] [rbp-BEh]
  __int16 v22; // [rsp+44h] [rbp-BCh]

  *a5 = 0;
  *a7 = 0;
  CanContinue = CShellUrl::_CanContinue(this);
  if ( (CanContinue & 0x80000000) != 0 )
    return CanContinue;
  CanContinue = -2147467259;
  if ( (int)DisplayNameOfW(a2, a4, a8, &String, 2084) < 0 )
    return CanContinue;
  v11 = (unsigned int)lstrlenW(&String);
  v12 = lstrlenW(lpString);
  if ( !(_DWORD)v11 )
    return CanContinue;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55524821>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55524821>::GetImpl'::`2'::impl) )
  {
    if ( v12 >= (unsigned int)v11 && !StrCmpNIW(&String, lpString, v11) )
    {
      if ( v12 == (_DWORD)v11 )
        goto LABEL_33;
      v16 = lpString[v11];
      if ( v16 == 47 || v16 == 92 || (_DWORD)v11 == 3 && v21 == 58 && v22 == 92 )
        goto LABEL_33;
    }
    ExtensionW = PathFindExtensionW(&String);
    if ( !PathIsExe(&String) || (a8 & 1) != 0 && (a8 & 0x8000) == 0 )
      return CanContinue;
    v11 = ExtensionW - &String;
    if ( lstrlenW(lpString) < (int)v11 || (lpString[(int)v11] & 0xFFDF) != 0 )
      return CanContinue;
    v15 = StrCmpNIW(&String, lpString, v11) == 0;
    goto LABEL_32;
  }
  if ( v12 >= (unsigned int)v11 && CompareStringOrdinal(&String, v11, lpString, v11, 1) == 2 )
  {
    if ( v12 == (_DWORD)v11 )
      goto LABEL_33;
    v13 = lpString[v11];
    if ( v13 == 47 || v13 == 92 || (_DWORD)v11 == 3 && v21 == 58 && v22 == 92 )
      goto LABEL_33;
  }
  v14 = PathFindExtensionW(&String);
  if ( PathIsExe(&String) )
  {
    if ( (a8 & 0x8001) != 1 )
    {
      v11 = v14 - &String;
      if ( lstrlenW(lpString) >= (int)v11 && (lpString[(int)v11] & 0xFFDF) == 0 )
      {
        v15 = CompareStringOrdinal(&String, v11, lpString, v11, 1) == 2;
LABEL_32:
        if ( v15 )
        {
LABEL_33:
          CanContinue = 0;
          *a7 = &lpString[(unsigned int)v11];
          *a5 = (struct _ITEMIDLIST_ABSOLUTE *)ILCombine(a3, a4);
        }
      }
    }
  }
  return CanContinue;
}

```

## disassembly

```asm
0x18004dc98  push    rbp
0x18004dc9a  push    rbx
0x18004dc9b  push    rsi
0x18004dc9c  push    rdi
0x18004dc9d  push    r12
0x18004dc9f  push    r13
0x18004dca1  push    r14
0x18004dca3  push    r15
0x18004dca5  lea     rbp, [rsp-0FA8h]
0x18004dcad  mov     eax, 10A8h
0x18004dcb2  call    _alloca_probe
0x18004dcb7  sub     rsp, rax
0x18004dcba  mov     rax, cs:__security_cookie
0x18004dcc1  xor     rax, rsp
0x18004dcc4  mov     [rbp+0FE0h+var_50], rax
0x18004dccb  mov     rax, [rbp+0FE0h+arg_30]
0x18004dcd2  mov     r12, r9
0x18004dcd5  mov     r13, [rbp+0FE0h+arg_20]
0x18004dcdc  mov     rbx, rdx
0x18004dcdf  mov     rdi, [rbp+0FE0h+lpString]
0x18004dce6  mov     [rsp+10E0h+pidl1], r8
0x18004dceb  mov     [rsp+10E0h+var_10B0], rax
0x18004dcf0  mov     qword ptr [r13+0], 0
0x18004dcf8  mov     qword ptr [rax], 0
0x18004dcff  call    ?_CanContinue@CShellUrl@@AEAAJXZ; CShellUrl::_CanContinue(void)
0x18004dd04  mov     r15d, eax
0x18004dd07  test    eax, eax
0x18004dd09  js      loc_18004DF85
0x18004dd0f  mov     r14d, [rbp+0FE0h+arg_38]
0x18004dd16  lea     r9, [rsp+10E0h+String]
0x18004dd1b  mov     r8d, r14d
0x18004dd1e  mov     [rsp+10E0h+bIgnoreCase], 824h
0x18004dd26  mov     rdx, r12
0x18004dd29  mov     rcx, rbx
0x18004dd2c  mov     r15d, 80004005h
0x18004dd32  call    DisplayNameOfW
0x18004dd37  test    eax, eax
0x18004dd39  js      loc_18004DF85
0x18004dd3f  lea     rcx, [rsp+10E0h+String]; lpString
0x18004dd44  call    cs:__imp_lstrlenW
0x18004dd4b  nop     dword ptr [rax+rax+00h]
0x18004dd50  mov     rcx, rdi; lpString
0x18004dd53  mov     ebx, eax
0x18004dd55  call    cs:__imp_lstrlenW
0x18004dd5c  nop     dword ptr [rax+rax+00h]
0x18004dd61  mov     esi, eax
0x18004dd63  test    ebx, ebx
0x18004dd65  jz      loc_18004DF85
0x18004dd6b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55524821@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55524821@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55524821> `wil::Feature<__WilFeatureTraits_Feature_55524821>::GetImpl(void)'::`2'::impl
0x18004dd72  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55524821@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55524821>::__private_IsEnabled(wil::ReportingKind)
0x18004dd77  test    al, al
0x18004dd79  jz      loc_18004DE84
0x18004dd7f  cmp     esi, ebx
0x18004dd81  jb      short loc_18004DDE9
0x18004dd83  mov     r9d, ebx; cchCount2
0x18004dd86  mov     [rsp+10E0h+bIgnoreCase], 1; bIgnoreCase
0x18004dd8e  mov     r8, rdi; lpString2
0x18004dd91  lea     rcx, [rsp+10E0h+String]; lpString1
0x18004dd96  mov     edx, ebx; cchCount1
0x18004dd98  call    cs:__imp_CompareStringOrdinal
0x18004dd9f  nop     dword ptr [rax+rax+00h]
0x18004dda4  cmp     eax, 2
0x18004dda7  jnz     short loc_18004DDE9
0x18004dda9  cmp     esi, ebx
0x18004ddab  jz      loc_18004DF5C
0x18004ddb1  movzx   ecx, word ptr [rdi+rbx*2]
0x18004ddb5  mov     eax, 2Fh ; '/'
0x18004ddba  cmp     ax, cx
0x18004ddbd  jz      loc_18004DF5C
0x18004ddc3  mov     eax, 5Ch ; '\'
0x18004ddc8  cmp     ax, cx
0x18004ddcb  jz      loc_18004DF5C
0x18004ddd1  cmp     ebx, 3
0x18004ddd4  jnz     short loc_18004DDE9
0x18004ddd6  cmp     [rsp+10E0h+var_109E], 3Ah ; ':'
0x18004dddc  jnz     short loc_18004DDE9
0x18004ddde  cmp     [rsp+10E0h+var_109C], ax
0x18004dde3  jz      loc_18004DF5C
0x18004dde9  lea     rcx, [rsp+10E0h+String]; pszPath
0x18004ddee  call    cs:__imp_PathFindExtensionW
0x18004ddf5  nop     dword ptr [rax+rax+00h]
0x18004ddfa  lea     rcx, [rsp+10E0h+String]; pszPath
0x18004ddff  mov     rbx, rax
0x18004de02  call    cs:__imp_PathIsExe
0x18004de09  nop     dword ptr [rax+rax+00h]
0x18004de0e  test    eax, eax
0x18004de10  jz      loc_18004DF85
0x18004de16  and     r14d, 8001h
0x18004de1d  cmp     r14d, 1
0x18004de21  jz      loc_18004DF85
0x18004de27  lea     rax, [rsp+10E0h+String]
0x18004de2c  mov     rcx, rdi; lpString
0x18004de2f  sub     rbx, rax
0x18004de32  sar     rbx, 1
0x18004de35  call    cs:__imp_lstrlenW
0x18004de3c  nop     dword ptr [rax+rax+00h]
0x18004de41  cmp     eax, ebx
0x18004de43  jl      loc_18004DF85
0x18004de49  movsxd  rax, ebx
0x18004de4c  mov     ecx, 0FFDFh
0x18004de51  test    [rdi+rax*2], cx
0x18004de55  jnz     loc_18004DF85
0x18004de5b  mov     r9d, ebx; cchCount2
0x18004de5e  mov     [rsp+10E0h+bIgnoreCase], 1; bIgnoreCase
0x18004de66  mov     r8, rdi; lpString2
0x18004de69  lea     rcx, [rsp+10E0h+String]; lpString1
0x18004de6e  mov     edx, ebx; cchCount1
0x18004de70  call    cs:__imp_CompareStringOrdinal
0x18004de77  nop     dword ptr [rax+rax+00h]
0x18004de7c  cmp     eax, 2
0x18004de7f  jmp     loc_18004DF5A
0x18004de84  cmp     esi, ebx
0x18004de86  jb      short loc_18004DEDF
0x18004de88  mov     r8d, ebx; nChar
0x18004de8b  lea     rcx, [rsp+10E0h+String]; psz1
0x18004de90  mov     rdx, rdi; psz2
0x18004de93  call    cs:__imp_StrCmpNIW
0x18004de9a  nop     dword ptr [rax+rax+00h]
0x18004de9f  test    eax, eax
0x18004dea1  jnz     short loc_18004DEDF
0x18004dea3  cmp     esi, ebx
0x18004dea5  jz      loc_18004DF5C
0x18004deab  movzx   ecx, word ptr [rdi+rbx*2]
0x18004deaf  mov     eax, 2Fh ; '/'
0x18004deb4  cmp     ax, cx
0x18004deb7  jz      loc_18004DF5C
0x18004debd  mov     eax, 5Ch ; '\'
0x18004dec2  cmp     ax, cx
0x18004dec5  jz      loc_18004DF5C
0x18004decb  cmp     ebx, 3
0x18004dece  jnz     short loc_18004DEDF
0x18004ded0  cmp     [rsp+10E0h+var_109E], 3Ah ; ':'
0x18004ded6  jnz     short loc_18004DEDF
0x18004ded8  cmp     [rsp+10E0h+var_109C], ax
0x18004dedd  jz      short loc_18004DF5C
0x18004dedf  lea     rcx, [rsp+10E0h+String]; pszPath
0x18004dee4  call    cs:__imp_PathFindExtensionW
0x18004deeb  nop     dword ptr [rax+rax+00h]
0x18004def0  lea     rcx, [rsp+10E0h+String]; pszPath
0x18004def5  mov     rbx, rax
0x18004def8  call    cs:__imp_PathIsExe
0x18004deff  nop     dword ptr [rax+rax+00h]
0x18004df04  test    eax, eax
0x18004df06  jz      short loc_18004DF85
0x18004df08  test    r14b, 1
0x18004df0c  jz      short loc_18004DF15
0x18004df0e  bt      r14d, 0Fh
0x18004df13  jnb     short loc_18004DF85
0x18004df15  lea     rax, [rsp+10E0h+String]
0x18004df1a  mov     rcx, rdi; lpString
0x18004df1d  sub     rbx, rax
0x18004df20  sar     rbx, 1
0x18004df23  call    cs:__imp_lstrlenW
0x18004df2a  nop     dword ptr [rax+rax+00h]
0x18004df2f  cmp     eax, ebx
0x18004df31  jl      short loc_18004DF85
0x18004df33  movsxd  rax, ebx
0x18004df36  mov     ecx, 0FFDFh
0x18004df3b  test    [rdi+rax*2], cx
0x18004df3f  jnz     short loc_18004DF85
0x18004df41  mov     r8d, ebx; nChar
0x18004df44  lea     rcx, [rsp+10E0h+String]; psz1
0x18004df49  mov     rdx, rdi; psz2
0x18004df4c  call    cs:__imp_StrCmpNIW
0x18004df53  nop     dword ptr [rax+rax+00h]
0x18004df58  test    eax, eax
0x18004df5a  jnz     short loc_18004DF85
0x18004df5c  mov     rcx, [rsp+10E0h+pidl1]; pidl1
0x18004df61  xor     r15d, r15d
0x18004df64  mov     eax, ebx
0x18004df66  mov     rdx, r12; pidl2
0x18004df69  lea     r8, [rdi+rax*2]
0x18004df6d  mov     rax, [rsp+10E0h+var_10B0]
0x18004df72  mov     [rax], r8
0x18004df75  call    cs:__imp_ILCombine
0x18004df7c  nop     dword ptr [rax+rax+00h]
0x18004df81  mov     [r13+0], rax
0x18004df85  mov     eax, r15d
0x18004df88  mov     rcx, [rbp+0FE0h+var_50]
0x18004df8f  xor     rcx, rsp; StackCookie
0x18004df92  call    __security_check_cookie
0x18004df97  add     rsp, 10A8h
0x18004df9e  pop     r15
0x18004dfa0  pop     r14
0x18004dfa2  pop     r13
0x18004dfa4  pop     r12
0x18004dfa6  pop     rdi
0x18004dfa7  pop     rsi
0x18004dfa8  pop     rbx
0x18004dfa9  pop     rbp
0x18004dfaa  retn
```
