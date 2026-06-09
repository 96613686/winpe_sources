# CThemeFile::GetCategory(tagTHEMECAT *)

- ea: `0x180007f20`
- end: `0x1800082e4`
- name: `?GetCategory@CThemeFile@@UEAAJPEAW4tagTHEMECAT@@@Z`
- size: `964`
- prototype: `__int64 __fastcall(CThemeFile *__hidden this, enum tagTHEMECAT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180007f20`
- `0x1800089c0`
- `0x1800358c0`
- `0x18003633c`
- `0x1800524fc`
- `0x18006d010`

## import_xrefs

- `SHELL32!SHGetFolderPathEx` at `0x180007f9c`
- `SHELL32!SHGetFolderPathEx` at `0x180008228`
- `SHELL32!SHGetFolderPathEx` at `0x180008265`
- `SHELL32!SHGetFolderPathEx` at `0x180007f9c`
- `SHELL32!SHGetFolderPathEx` at `0x180008228`
- `SHELL32!SHGetFolderPathEx` at `0x180008265`
- `SHLWAPI!PathFindFileNameW` at `0x1800081df`
- `SHLWAPI!PathFindFileNameW` at `0x1800081df`
- `SHLWAPI!PathIsPrefixW` at `0x18000815b`
- `SHLWAPI!PathIsPrefixW` at `0x180008242`
- `SHLWAPI!PathIsPrefixW` at `0x18000827f`
- `SHLWAPI!PathIsPrefixW` at `0x18000815b`
- `SHLWAPI!PathIsPrefixW` at `0x180008242`
- `SHLWAPI!PathIsPrefixW` at `0x18000827f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008082`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008200`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008082`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008200`
- `OLEAUT32!__imp_SysFreeString` at `0x180007fcf`
- `OLEAUT32!__imp_SysFreeString` at `0x180007fcf`
- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_GetPolicy` at `0x18000819a`
- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_GetPolicy` at `0x18000819a`
- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_FreeGetPolicyData` at `0x1800081b2`
- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_FreeGetPolicyData` at `0x1800081b2`

## string_xrefs

- `0x1800080f7`: `\Ease of Access Themes`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CThemeFile::GetCategory(CThemeFile *this, enum tagTHEMECAT *a2)
{
  int v4; // ebx
  unsigned int i; // edi
  __int64 v7; // rcx
  WCHAR *v8; // rax
  __int64 v9; // r8
  __int64 v10; // rax
  const wchar_t *v11; // r9
  bool v12; // zf
  __int64 v13; // rdx
  WCHAR *v14; // r8
  wchar_t v15; // cx
  WCHAR *v16; // rcx
  bool v17; // di
  const WCHAR *FileNameW; // rax
  const struct _GUID *v19; // rdx
  BSTR bstrString; // [rsp+30h] [rbp-D0h] BYREF
  __m128i si128; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v22; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR pszPrefix[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR String2[264]; // [rsp+270h] [rbp+170h] BYREF

  *(_DWORD *)a2 = -1;
  bstrString = 0;
  v4 = (*(__int64 (__fastcall **)(CThemeFile *, __int64, BSTR *))(*(_QWORD *)this + 288LL))(
         this,
         0xFFFFFFFFLL,
         &bstrString);
  if ( v4 < 0 )
    goto LABEL_7;
  v4 = SHGetFolderPathEx(&FOLDERID_ResourceDir, 0, 0, pszPrefix, 260);
  if ( v4 >= 0 )
  {
    for ( i = 0; i < 7; ++i )
    {
      if ( v4 < 0 )
        goto LABEL_3;
      if ( *(_DWORD *)a2 != -1 )
        goto LABEL_32;
      memset_0(String2, 0, 0x208u);
      v4 = StringCchPrintfW(String2, 0x104u, L"%s\\Themes\\%s.theme", pszPrefix, off_18006E080[i]);
      if ( v4 >= 0 && CompareStringOrdinal(bstrString, -1, String2, -1, 1) == 2 )
        *(_DWORD *)a2 = 1;
    }
    if ( v4 < 0 )
      goto LABEL_3;
    if ( *(_DWORD *)a2 == -1 )
    {
      v7 = 260;
      v8 = pszPrefix;
      do
      {
        if ( !*v8 )
          break;
        ++v8;
        --v7;
      }
      while ( v7 );
      v4 = -2147024809;
      if ( v7 )
        v4 = 0;
      v9 = 260 - v7;
      if ( !v7 )
        goto LABEL_3;
      v10 = 2147483646;
      v11 = L"\\Ease of Access Themes";
      v13 = v7;
      v12 = v9 == 260;
      v14 = &pszPrefix[v9];
      if ( !v12 )
      {
        do
        {
          if ( !v10 )
            break;
          v15 = *v11;
          if ( !*v11 )
            break;
          ++v11;
          *v14++ = v15;
          --v10;
          --v13;
        }
        while ( v13 );
      }
      v16 = v14 - 1;
      if ( v13 )
        v16 = v14;
      *v16 = 0;
      v4 = -2147024774;
      if ( !v13 )
        goto LABEL_3;
      v4 = 0;
      if ( PathIsPrefixW(pszPrefix, bstrString) )
        *(_DWORD *)a2 = 3;
    }
LABEL_32:
    v17 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    *(_QWORD *)&v22 = 0;
    if ( (int)PolicyManager_GetPolicy(L"Education", L"EnableEduThemes", &si128, &v22) >= 0 && *(_DWORD *)(v22 + 8) == 1 )
      v17 = *(_DWORD *)(v22 + 16) == 1;
    if ( (_QWORD)v22 )
      PolicyManager_FreeGetPolicyData(v22);
    if ( v17 )
    {
      if ( *(_DWORD *)a2 != -1 )
        goto LABEL_7;
      v22 = 0;
      v4 = (*(__int64 (__fastcall **)(CThemeFile *, __int128 *))(*(_QWORD *)this + 120LL))(this, &v22);
      if ( v4 < 0 )
        goto LABEL_3;
      if ( EduThemeHelpers::IsEduTheme((EduThemeHelpers *)&v22, v19) )
        *(_DWORD *)a2 = 1;
    }
    if ( *(_DWORD *)a2 != -1 )
      goto LABEL_7;
    FileNameW = PathFindFileNameW(bstrString);
    if ( CompareStringOrdinal(FileNameW, -1, L"oem.theme", -1, 1) != 2 )
    {
      v4 = SHGetFolderPathEx(&FOLDERID_Profile, 0, 0, pszPrefix, 260);
      if ( v4 >= 0 )
      {
        if ( PathIsPrefixW(pszPrefix, bstrString)
          || (v4 = SHGetFolderPathEx(&FOLDERID_Documents, 0, 0, pszPrefix, 260), v4 >= 0)
          && PathIsPrefixW(pszPrefix, bstrString) )
        {
          *(_DWORD *)a2 = 0;
        }
      }
    }
  }
LABEL_3:
  if ( *(_DWORD *)a2 == -1 )
    *(_DWORD *)a2 = 2;
LABEL_7:
  SysFreeString(bstrString);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180007f20  mov     [rsp-8+arg_10], rbx
0x180007f25  push    rbp
0x180007f26  push    rsi
0x180007f27  push    rdi
0x180007f28  push    r12
0x180007f2a  push    r13
0x180007f2c  push    r14
0x180007f2e  push    r15
0x180007f30  lea     rbp, [rsp-390h]
0x180007f38  sub     rsp, 490h
0x180007f3f  mov     rax, cs:__security_cookie
0x180007f46  xor     rax, rsp
0x180007f49  mov     [rbp+3C0h+var_40], rax
0x180007f50  mov     r14, rdx
0x180007f53  mov     r15, rcx
0x180007f56  mov     dword ptr [rdx], 0FFFFFFFFh
0x180007f5c  xor     r13d, r13d
0x180007f5f  mov     [rsp+4C0h+bstrString], r13
0x180007f64  mov     rax, [rcx]
0x180007f67  mov     edx, 0FFFFFFFFh
0x180007f6c  lea     r8, [rsp+4C0h+bstrString]
0x180007f71  mov     rax, [rax+120h]
0x180007f78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f7d  mov     ebx, eax
0x180007f7f  test    eax, eax
0x180007f81  js      short loc_180007FCA
0x180007f83  mov     [rsp+4C0h+bIgnoreCase], 104h
0x180007f8b  lea     r9, [rsp+4C0h+pszPrefix]
0x180007f90  xor     r8d, r8d
0x180007f93  xor     edx, edx
0x180007f95  lea     rcx, FOLDERID_ResourceDir
0x180007f9c  call    cs:__imp_SHGetFolderPathEx
0x180007fa2  mov     ebx, eax
0x180007fa4  test    eax, eax
0x180007fa6  jns     short loc_180008001
0x180007fa8  cmp     dword ptr [r14], 0FFFFFFFFh
0x180007fac  jnz     short loc_180007FCA
0x180007fae  mov     dword ptr [r14], 2
0x180007fb5  jmp     short loc_180007FCA
0x180007fb7  test    dil, dil
0x180007fba  jnz     loc_180008295
0x180007fc0  cmp     dword ptr [r14], 0FFFFFFFFh
0x180007fc4  jz      loc_1800081DA
0x180007fca  mov     rcx, [rsp+4C0h+bstrString]; bstrString
0x180007fcf  call    cs:__imp_SysFreeString
0x180007fd5  mov     eax, ebx
0x180007fd7  mov     rcx, [rbp+3C0h+var_40]
0x180007fde  xor     rcx, rsp; StackCookie
0x180007fe1  call    __security_check_cookie
0x180007fe6  mov     rbx, [rsp+4C0h+arg_10]
0x180007fee  add     rsp, 490h
0x180007ff5  pop     r15
0x180007ff7  pop     r14
0x180007ff9  pop     r13
0x180007ffb  pop     r12
0x180007ffd  pop     rdi
0x180007ffe  pop     rsi
0x180007fff  pop     rbp
0x180008000  retn
0x180008001  mov     edi, r13d
0x180008004  lea     r12, off_18006E080; "aero"
0x18000800b  nop     dword ptr [rax+rax+00h]
0x180008010  test    ebx, ebx
0x180008012  js      short loc_180007FA8
0x180008014  mov     eax, [r14]
0x180008017  cmp     eax, 0FFFFFFFFh
0x18000801a  jnz     loc_18000816C
0x180008020  xor     edx, edx; Val
0x180008022  mov     r8d, 208h; Size
0x180008028  lea     rcx, [rbp+3C0h+String2]; void *
0x18000802f  call    memset_0
0x180008034  movsxd  rax, edi
0x180008037  mov     rax, [r12+rax*8]
0x18000803b  mov     qword ptr [rsp+4C0h+bIgnoreCase], rax
0x180008040  lea     r9, [rsp+4C0h+pszPrefix]
0x180008045  lea     r8, aSThemesSTheme; "%s\\Themes\\%s.theme"
0x18000804c  mov     edx, 104h; unsigned __int64
0x180008051  lea     rcx, [rbp+3C0h+String2]; unsigned __int16 *
0x180008058  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000805d  mov     ebx, eax
0x18000805f  mov     esi, eax
0x180008061  test    eax, eax
0x180008063  js      short loc_180008091
0x180008065  mov     [rsp+4C0h+bIgnoreCase], 1; bIgnoreCase
0x18000806d  mov     r9d, 0FFFFFFFFh; cchCount2
0x180008073  lea     r8, [rbp+3C0h+String2]; lpString2
0x18000807a  mov     edx, r9d; cchCount1
0x18000807d  mov     rcx, [rsp+4C0h+bstrString]; lpString1
0x180008082  call    cs:__imp_CompareStringOrdinal
0x180008088  cmp     eax, 2
0x18000808b  jz      loc_1800081BD
0x180008091  inc     edi
0x180008093  cmp     edi, 7
0x180008096  jb      loc_180008010
0x18000809c  mov     eax, [r14]
0x18000809f  test    esi, esi
0x1800080a1  js      loc_180007FA8
0x1800080a7  cmp     eax, 0FFFFFFFFh
0x1800080aa  jnz     loc_18000816C
0x1800080b0  mov     ecx, 104h
0x1800080b5  lea     rax, [rsp+4C0h+pszPrefix]
0x1800080ba  nop     word ptr [rax+rax+00h]
0x1800080c0  cmp     word ptr [rax], 0
0x1800080c4  jz      short loc_1800080D0
0x1800080c6  add     rax, 2
0x1800080ca  sub     rcx, 1
0x1800080ce  jnz     short loc_1800080C0
0x1800080d0  mov     ebx, 80070057h
0x1800080d5  test    rcx, rcx
0x1800080d8  cmovnz  ebx, r13d
0x1800080dc  mov     r8d, 104h
0x1800080e2  sub     r8, rcx
0x1800080e5  test    rcx, rcx
0x1800080e8  cmovz   r8, r13
0x1800080ec  jz      loc_180007FA8
0x1800080f2  mov     eax, 7FFFFFFEh
0x1800080f7  lea     r9, aEaseOfAccessTh; "\\Ease of Access Themes"
0x1800080fe  mov     edx, 104h
0x180008103  sub     rdx, r8
0x180008106  lea     r8, [rsp+r8*2+4C0h+pszPrefix]
0x18000810b  jz      short loc_180008133
0x18000810d  nop     dword ptr [rax]
0x180008110  test    rax, rax
0x180008113  jz      short loc_180008133
0x180008115  movzx   ecx, word ptr [r9]
0x180008119  test    cx, cx
0x18000811c  jz      short loc_180008133
0x18000811e  add     r9, 2
0x180008122  mov     [r8], cx
0x180008126  add     r8, 2
0x18000812a  dec     rax
0x18000812d  sub     rdx, 1
0x180008131  jnz     short loc_180008110
0x180008133  lea     rcx, [r8-2]
0x180008137  test    rdx, rdx
0x18000813a  cmovnz  rcx, r8
0x18000813e  mov     [rcx], r13w
0x180008142  mov     ebx, 8007007Ah
0x180008147  cmovnz  ebx, r13d
0x18000814b  jz      loc_180007FA8
0x180008151  mov     rdx, [rsp+4C0h+bstrString]; pszPath
0x180008156  lea     rcx, [rsp+4C0h+pszPrefix]; pszPrefix
0x18000815b  call    cs:__imp_PathIsPrefixW
0x180008161  test    eax, eax
0x180008163  jz      short loc_18000816C
0x180008165  mov     dword ptr [r14], 3
0x18000816c  xor     dil, dil
0x18000816f  movdqa  xmm0, cs:__xmm@00000000000000000000000200000001
0x180008177  movdqu  [rsp+4C0h+var_488], xmm0
0x18000817d  mov     qword ptr [rsp+4C0h+var_478], r13
0x180008182  lea     r9, [rsp+4C0h+var_478]
0x180008187  lea     r8, [rsp+4C0h+var_488]
0x18000818c  lea     rdx, aEnableedutheme; "EnableEduThemes"
0x180008193  lea     rcx, aEducation; "Education"
0x18000819a  call    cs:__imp_PolicyManager_GetPolicy
0x1800081a0  mov     rcx, qword ptr [rsp+4C0h+var_478]
0x1800081a5  test    eax, eax
0x1800081a7  jns     short loc_1800081C9
0x1800081a9  test    rcx, rcx
0x1800081ac  jz      loc_180007FB7
0x1800081b2  call    cs:__imp_PolicyManager_FreeGetPolicyData
0x1800081b8  jmp     loc_180007FB7
0x1800081bd  mov     dword ptr [r14], 1
0x1800081c4  jmp     loc_180008091
0x1800081c9  cmp     dword ptr [rcx+8], 1
0x1800081cd  jnz     short loc_1800081A9
0x1800081cf  cmp     dword ptr [rcx+10h], 1
0x1800081d3  jnz     short loc_1800081A9
0x1800081d5  mov     dil, 1
0x1800081d8  jmp     short loc_1800081A9
0x1800081da  mov     rcx, [rsp+4C0h+bstrString]; pszPath
0x1800081df  call    cs:__imp_PathFindFileNameW
0x1800081e5  mov     [rsp+4C0h+bIgnoreCase], 1; bIgnoreCase
0x1800081ed  mov     r9d, 0FFFFFFFFh; cchCount2
0x1800081f3  lea     r8, aOemTheme_0; "oem.theme"
0x1800081fa  mov     edx, r9d; cchCount1
0x1800081fd  mov     rcx, rax; lpString1
0x180008200  call    cs:__imp_CompareStringOrdinal
0x180008206  cmp     eax, 2
0x180008209  jz      loc_180007FA8
0x18000820f  mov     [rsp+4C0h+bIgnoreCase], 104h
0x180008217  lea     r9, [rsp+4C0h+pszPrefix]
0x18000821c  xor     r8d, r8d
0x18000821f  xor     edx, edx
0x180008221  lea     rcx, FOLDERID_Profile
0x180008228  call    cs:__imp_SHGetFolderPathEx
0x18000822e  mov     ebx, eax
0x180008230  test    eax, eax
0x180008232  js      loc_180007FA8
0x180008238  mov     rdx, [rsp+4C0h+bstrString]; pszPath
0x18000823d  lea     rcx, [rsp+4C0h+pszPrefix]; pszPrefix
0x180008242  call    cs:__imp_PathIsPrefixW
0x180008248  test    eax, eax
0x18000824a  jnz     short loc_18000828D
0x18000824c  mov     [rsp+4C0h+bIgnoreCase], 104h
0x180008254  lea     r9, [rsp+4C0h+pszPrefix]
0x180008259  xor     r8d, r8d
0x18000825c  xor     edx, edx
0x18000825e  lea     rcx, FOLDERID_Documents
0x180008265  call    cs:__imp_SHGetFolderPathEx
0x18000826b  mov     ebx, eax
0x18000826d  test    eax, eax
0x18000826f  js      loc_180007FA8
0x180008275  mov     rdx, [rsp+4C0h+bstrString]; pszPath
0x18000827a  lea     rcx, [rsp+4C0h+pszPrefix]; pszPrefix
0x18000827f  call    cs:__imp_PathIsPrefixW
0x180008285  test    eax, eax
0x180008287  jz      loc_180007FA8
0x18000828d  mov     [r14], r13d
0x180008290  jmp     loc_180007FA8
0x180008295  cmp     dword ptr [r14], 0FFFFFFFFh
0x180008299  jnz     loc_180007FCA
0x18000829f  xorps   xmm0, xmm0
0x1800082a2  movups  [rsp+4C0h+var_478], xmm0
0x1800082a7  mov     rax, [r15]
0x1800082aa  lea     rdx, [rsp+4C0h+var_478]
0x1800082af  mov     rcx, r15
0x1800082b2  mov     rax, [rax+78h]
0x1800082b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082bb  mov     ebx, eax
0x1800082bd  test    eax, eax
0x1800082bf  js      loc_180007FA8
0x1800082c5  lea     rcx, [rsp+4C0h+var_478]; this
0x1800082ca  call    ?IsEduTheme@EduThemeHelpers@@YA_NAEBU_GUID@@@Z; EduThemeHelpers::IsEduTheme(_GUID const &)
0x1800082cf  test    al, al
0x1800082d1  jz      loc_180007FC0
0x1800082d7  mov     dword ptr [r14], 1
0x1800082de  jmp     loc_180007FC0
```
