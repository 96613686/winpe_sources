# CContentFolder::GetDisplayNameOf(_ITEMIDLIST const *,ulong,_STRRET *)

- ea: `0x180007a30`
- end: `0x1800082cf`
- name: `?GetDisplayNameOf@CContentFolder@@UEAAJPEFBU_ITEMIDLIST@@KPEAU_STRRET@@@Z`
- size: `2207`
- prototype: `int(CContentFolder *__hidden this, const struct _ITEMIDLIST *, unsigned int, struct _STRRET *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x180007a30`
- `0x1800082e0`
- `0x18002ff5c`
- `0x1800339cc`
- `0x180035590`
- `0x1800361ba`
- `0x180078010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180007e25`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180007e25`
- `SHLWAPI!SHStrDupW` at `0x180007bcd`
- `SHLWAPI!SHStrDupW` at `0x180007c6e`
- `SHLWAPI!SHStrDupW` at `0x180007bcd`
- `SHLWAPI!SHStrDupW` at `0x180007c6e`
- `SHLWAPI!PathFindFileNameW` at `0x180007c4f`
- `SHLWAPI!PathFindFileNameW` at `0x180007d8d`
- `SHLWAPI!PathFindFileNameW` at `0x180007c4f`
- `SHLWAPI!PathFindFileNameW` at `0x180007d8d`
- `SHLWAPI!StrRetToBufW` at `0x180007f52`
- `SHLWAPI!StrRetToBufW` at `0x180007f52`
- `ole32!CoUninitialize` at `0x180007f9a`
- `ole32!CoUninitialize` at `0x180007f9a`
- `ole32!CoTaskMemFree` at `0x180007cce`
- `ole32!CoTaskMemFree` at `0x180007cce`
- `ole32!CoTaskMemAlloc` at `0x180007e7d`
- `ole32!CoTaskMemAlloc` at `0x180007e7d`
- `ole32!CoInitializeEx` at `0x180007eaa`
- `ole32!CoInitializeEx` at `0x1800080a5`
- `ole32!CoInitializeEx` at `0x180007eaa`
- `ole32!CoInitializeEx` at `0x1800080a5`
- `SHELL32!SHGetSettings` at `0x180007d1d`
- `SHELL32!SHGetSettings` at `0x180007d1d`
- `SHELL32!SHBindToParent` at `0x180007ee1`
- `SHELL32!SHBindToParent` at `0x180007ee1`

## pseudocode

```c
HRESULT __fastcall CContentFolder::GetDisplayNameOf(
        CContentFolder *this,
        const struct _ITEMIDLIST *a2,
        unsigned int a3,
        struct _STRRET *a4)
{
  CContentFolder *v8; // rcx
  const struct CONTENTITEM *v9; // rbx
  WCHAR *v10; // r12
  HRESULT v11; // edi
  __int64 v12; // r14
  WCHAR *v13; // r9
  __int64 v14; // rdx
  WCHAR *v15; // r8
  __int64 v16; // rbx
  WCHAR *v17; // rcx
  __int64 v18; // rcx
  WCHAR *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r15
  WCHAR *v22; // rcx
  WCHAR *v23; // rdx
  WCHAR *v24; // rcx
  struct _STRRET *v25; // rdx
  HRESULT v26; // eax
  PVOID *v27; // rcx
  unsigned int v28; // ebx
  WCHAR *v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // rbx
  WCHAR *v32; // r8
  WCHAR *v33; // rcx
  struct _STRRET *v34; // rdx
  HRESULT result; // eax
  PVOID *v36; // rcx
  unsigned int v37; // ebx
  WCHAR *v38; // rcx
  int v39; // edx
  PVOID *v40; // r10
  int v41; // esi
  const struct CONTENTITEM *v42; // rdx
  __int64 v43; // rbx
  STRRET *p_FullPath; // r8
  __int64 v45; // r9
  __int64 v46; // rcx
  _WORD *v47; // rdx
  STRRET *v48; // rcx
  __int64 v49; // rcx
  STRRET *v50; // rdx
  WCHAR *v51; // r8
  __int64 v52; // rcx
  wchar_t *v53; // rdx
  WCHAR *v54; // rax
  WCHAR *v55; // rax
  const ITEMIDLIST *v56; // rbx
  HRESULT v57; // esi
  const ITEMIDLIST *v58; // r14
  __int64 v59; // rbx
  __int64 v60; // rcx
  WCHAR *v61; // rax
  __int64 v62; // r9
  bool v63; // zf
  __int64 v64; // r8
  __int64 v65; // rcx
  WCHAR *v66; // r9
  const wchar_t *v67; // rdx
  HRESULT v68; // eax
  SHELLFLAGSTATE psfs[2]; // [rsp+50h] [rbp-B0h] BYREF
  LPCITEMIDLIST ppidlLast; // [rsp+58h] [rbp-A8h] BYREF
  const struct CONTENTITEM *v71; // [rsp+60h] [rbp-A0h]
  struct _STRRET *v72; // [rsp+68h] [rbp-98h]
  WCHAR pszPath[264]; // [rsp+70h] [rbp-90h] BYREF
  STRRET FullPath; // [rsp+280h] [rbp+180h] BYREF
  wchar_t Filename[264]; // [rsp+490h] [rbp+390h] BYREF
  wchar_t Ext[264]; // [rsp+6A0h] [rbp+5A0h] BYREF

  v72 = a4;
  memset_0(pszPath, 0, 0x208u);
  if ( !a4 )
  {
    v11 = -2147467261;
    goto LABEL_101;
  }
  v71 = CContentFolder::_IsValid(v8, a2);
  v9 = v71;
  if ( !v71 )
  {
    v11 = -2147024809;
    goto LABEL_101;
  }
  v10 = 0;
  if ( (a3 & 0xC000) == 0 || (a3 & 1) != 0 )
  {
    v11 = -2147024809;
    v12 = 2147483646;
    goto LABEL_5;
  }
  v55 = (WCHAR *)CoTaskMemAlloc(0x1040u);
  v10 = v55;
  if ( !v55 )
  {
    v11 = -2147024882;
    goto LABEL_101;
  }
  memset_0(v55, 0, 0x1040u);
  v56 = (const ITEMIDLIST *)*((_QWORD *)this + 6);
  v57 = CoInitializeEx(0, 6u);
  if ( v57 < 0 )
  {
    v68 = CoInitializeEx(0, 4u);
    v57 = v68;
    if ( v68 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        67,
        &WPP_d7637b305d8b3afba9326780f352c02a_Traceguids,
        (unsigned int)v68);
  }
  *(_QWORD *)psfs = 0;
  ppidlLast = 0;
  v11 = SHBindToParent(v56, &GUID_000214e6_0000_0000_c000_000000000046, (void **)psfs, &ppidlLast);
  if ( v11 < 0 )
    goto LABEL_85;
  v58 = ppidlLast;
  v59 = *(_QWORD *)psfs;
  *v10 = 0;
  memset_0(&FullPath, 0, sizeof(FullPath));
  v11 = (*(__int64 (__fastcall **)(__int64, const ITEMIDLIST *, _QWORD, STRRET *))(*(_QWORD *)v59 + 88LL))(
          v59,
          v58,
          a3,
          &FullPath);
  if ( v11 >= 0 )
  {
    v11 = StrRetToBufW(&FullPath, v58, v10, 0x820u);
    if ( v11 >= 0 )
      goto LABEL_82;
  }
  v40 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      &WPP_d7637b305d8b3afba9326780f352c02a_Traceguids,
      (unsigned int)v11);
LABEL_82:
    v40 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *(_QWORD *)psfs )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)psfs + 16LL))(*(_QWORD *)psfs);
    *(_QWORD *)psfs = 0;
LABEL_85:
    v40 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v57 >= 0 )
  {
    CoUninitialize();
    v40 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v11 < 0 )
  {
    if ( v40 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v40 + 28) & 2) != 0 )
      {
        WPP_SF_d(v40[2], 68, &WPP_d7637b305d8b3afba9326780f352c02a_Traceguids, (unsigned int)v11);
        v40 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v40 != &WPP_GLOBAL_Control && (*((_BYTE *)v40 + 28) & 2) != 0 )
        WPP_SF_d(v40[2], 63, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)v11);
    }
    goto LABEL_48;
  }
  v60 = 2080;
  v61 = v10;
  do
  {
    if ( !*v61 )
      break;
    ++v61;
    --v60;
  }
  while ( v60 );
  v11 = -2147024809;
  v39 = -2147024809;
  if ( v60 )
    v39 = 0;
  v62 = 2080 - v60;
  if ( !v60 )
    goto LABEL_47;
  v12 = 2147483646;
  v64 = v60;
  v63 = v62 == 2080;
  v65 = 2147483646;
  v66 = &v10[v62];
  v67 = L"\\";
  if ( !v63 )
  {
    do
    {
      if ( !v65 )
        break;
      if ( !*v67 )
        break;
      *v66++ = *v67++;
      --v65;
      --v64;
    }
    while ( v64 );
  }
  v38 = v66 - 1;
  v39 = -2147024774;
  if ( v64 )
  {
    v38 = v66;
    v39 = 0;
  }
  *v38 = 0;
  if ( !v64 )
  {
    v40 = (PVOID *)WPP_GLOBAL_Control;
LABEL_47:
    v11 = v39;
    if ( v40 != &WPP_GLOBAL_Control && (*((_BYTE *)v40 + 28) & 2) != 0 )
      WPP_SF_SSd(
        (unsigned int)v40[2],
        64,
        (unsigned int)WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
        (_DWORD)v10,
        (__int64)L"\\",
        v39);
    goto LABEL_48;
  }
  v9 = v71;
LABEL_5:
  if ( (a3 & 0x4000) != 0 )
  {
    if ( *(_DWORD *)((char *)v9 + 66) > 1u )
      v9 = (const struct CONTENTITEM *)((char *)v9 + 2 * *(unsigned int *)((char *)v9 + 62));
    v29 = (WCHAR *)((char *)v9 + 74);
    v30 = 2147483646;
    v31 = 260;
    v32 = pszPath;
    do
    {
      if ( !v30 )
        break;
      if ( !*v29 )
        break;
      *v32++ = *v29++;
      --v30;
      --v31;
    }
    while ( v31 );
    v33 = v32 - 1;
    if ( v31 )
      v33 = v32;
    *v33 = 0;
    PathFindFileNameW(pszPath);
  }
  else
  {
    if ( (a3 & 0x8000) != 0 )
    {
      v13 = pszPath;
      v14 = 2147483646;
      v15 = (WCHAR *)((char *)v9
                    + 2 * *(unsigned int *)((char *)v9 + 66)
                    + 2 * (unsigned __int64)*(unsigned int *)((char *)v9 + 62)
                    + 74);
      v16 = 260;
      do
      {
        if ( !v14 )
          break;
        if ( !*v15 )
          break;
        *v13++ = *v15++;
        --v14;
        --v16;
      }
      while ( v16 );
      v17 = v13 - 1;
      if ( v16 )
        v17 = v13;
    }
    else
    {
      psfs[0] = 0;
      SHGetSettings(psfs, 2u);
      v41 = (int)(*(_DWORD *)psfs << 30) >> 31;
      if ( *(_DWORD *)((char *)v9 + 66) <= 1u )
        v42 = v9;
      else
        v42 = (const struct CONTENTITEM *)((char *)v9 + 2 * *(unsigned int *)((char *)v9 + 62));
      v43 = 260;
      p_FullPath = &FullPath;
      v45 = 260;
      v46 = 2147483646;
      v47 = (_WORD *)((char *)v42 + 74);
      do
      {
        if ( !v46 )
          break;
        if ( !*v47 )
          break;
        LOWORD(p_FullPath->uType) = *v47++;
        p_FullPath = (STRRET *)((char *)p_FullPath + 2);
        --v46;
        --v45;
      }
      while ( v45 );
      v48 = (STRRET *)((char *)p_FullPath - 2);
      if ( v45 )
        v48 = p_FullPath;
      LOWORD(v48->uType) = 0;
      PathFindFileNameW((LPCWSTR)&FullPath);
      if ( v41 || (*((_BYTE *)v71 + 10) & 2) != 0 )
      {
        v49 = 2147483646;
        v50 = &FullPath;
        v51 = pszPath;
        do
        {
          if ( !v49 )
            break;
          if ( !LOWORD(v50->uType) )
            break;
          *v51 = v50->uType;
          v50 = (STRRET *)((char *)v50 + 2);
          ++v51;
          --v49;
          --v43;
        }
        while ( v43 );
        v17 = v51 - 1;
        if ( v43 )
          v17 = v51;
      }
      else
      {
        _wsplitpath_s((const wchar_t *)&FullPath, 0, 0, 0, 0, Filename, 0x104u, Ext, 0x104u);
        v52 = 2147483646;
        v53 = Filename;
        v54 = pszPath;
        do
        {
          if ( !v52 )
            break;
          if ( !*v53 )
            break;
          *v54++ = *v53++;
          --v52;
          --v43;
        }
        while ( v43 );
        v17 = v54 - 1;
        if ( v43 )
          v17 = v54;
      }
    }
    *v17 = 0;
  }
  if ( v10 )
  {
    v18 = 2080;
    v19 = v10;
    do
    {
      if ( !*v19 )
        break;
      ++v19;
      --v18;
    }
    while ( v18 );
    if ( v18 )
      v11 = 0;
    v20 = 2080 - v18;
    if ( !v18 )
      goto LABEL_135;
    v21 = v18;
    v22 = pszPath;
    v23 = &v10[v20];
    do
    {
      if ( !v12 )
        break;
      if ( !*v22 )
        break;
      *v23++ = *v22++;
      --v12;
      --v21;
    }
    while ( v21 );
    v24 = v23 - 1;
    v11 = -2147024774;
    if ( v21 )
    {
      v24 = v23;
      v11 = 0;
    }
    *v24 = 0;
    if ( v21 )
    {
      v25 = v72;
      v72->uType = 0;
      v26 = SHStrDupW(v10, &v25->pOleStr);
      v27 = (PVOID *)WPP_GLOBAL_Control;
      v28 = v26;
      if ( v26 >= 0 || WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
        v11 = v26;
        if ( v26 >= 0 )
          goto LABEL_48;
      }
      else
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          &WPP_d7637b305d8b3afba9326780f352c02a_Traceguids,
          (unsigned int)v26);
        v27 = (PVOID *)WPP_GLOBAL_Control;
        v11 = v28;
      }
      if ( v27 != &WPP_GLOBAL_Control && (*((_BYTE *)v27 + 28) & 2) != 0 )
        WPP_SF_d(v27[2], 67, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, v28);
    }
    else
    {
LABEL_135:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_SSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          66,
          (unsigned int)WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
          (_DWORD)v10,
          (__int64)pszPath,
          v11);
    }
LABEL_48:
    CoTaskMemFree(v10);
    if ( v11 >= 0 )
      return v11;
    goto LABEL_101;
  }
  v34 = v72;
  v72->uType = 0;
  result = SHStrDupW(pszPath, &v34->pOleStr);
  v36 = (PVOID *)WPP_GLOBAL_Control;
  v37 = result;
  if ( result < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      &WPP_d7637b305d8b3afba9326780f352c02a_Traceguids,
      (unsigned int)result);
    v36 = (PVOID *)WPP_GLOBAL_Control;
    v11 = v37;
    goto LABEL_125;
  }
  v11 = result;
  if ( result < 0 )
  {
LABEL_125:
    if ( v36 == &WPP_GLOBAL_Control )
      return v11;
    if ( (*((_BYTE *)v36 + 28) & 2) == 0 )
    {
LABEL_102:
      if ( v36 != &WPP_GLOBAL_Control && (*((_BYTE *)v36 + 28) & 2) != 0 )
        WPP_SF_d(v36[2], 68, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)v11);
      return v11;
    }
    WPP_SF_d(v36[2], 65, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, v37);
LABEL_101:
    v36 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_102;
  }
  return result;
}

```

## disassembly

```asm
0x180007a30  push    rbp
0x180007a32  push    rbx
0x180007a33  push    rsi
0x180007a34  push    rdi
0x180007a35  push    r12
0x180007a37  push    r13
0x180007a39  push    r14
0x180007a3b  push    r15
0x180007a3d  lea     rbp, [rsp-7C8h]
0x180007a45  sub     rsp, 8C8h
0x180007a4c  mov     rax, cs:__security_cookie
0x180007a53  xor     rax, rsp
0x180007a56  mov     [rbp+800h+var_50], rax
0x180007a5d  mov     r13d, r8d
0x180007a60  mov     [rsp+900h+var_898], r9
0x180007a65  mov     rbx, rdx
0x180007a68  mov     rdi, rcx
0x180007a6b  xor     edx, edx; Val
0x180007a6d  lea     rcx, [rsp+900h+pszPath]; void *
0x180007a72  mov     r8d, 208h; Size
0x180007a78  mov     rsi, r9
0x180007a7b  call    memset_0
0x180007a80  test    rsi, rsi
0x180007a83  jz      loc_18000803F
0x180007a89  mov     rdx, rbx; struct _ITEMIDLIST *
0x180007a8c  call    ?_IsValid@CContentFolder@@QEAAPEFBUCONTENTITEM@@PEFBU_ITEMIDLIST@@@Z; CContentFolder::_IsValid(_ITEMIDLIST const *)
0x180007a91  mov     [rsp+900h+var_8A0], rax
0x180007a96  mov     rbx, rax
0x180007a99  test    rax, rax
0x180007a9c  jz      loc_180008082
0x180007aa2  xor     r12d, r12d
0x180007aa5  test    r13d, 0C000h
0x180007aac  jnz     loc_180007E6E
0x180007ab2  mov     edi, 80070057h
0x180007ab7  mov     r15d, 820h
0x180007abd  mov     r14d, 7FFFFFFEh
0x180007ac3  bt      r13d, 0Eh
0x180007ac8  jb      loc_180007BFA
0x180007ace  bt      r13d, 0Fh
0x180007ad3  jnb     loc_180007D0B
0x180007ad9  mov     r8d, [rbx+3Eh]
0x180007add  lea     r9, [rsp+900h+pszPath]
0x180007ae2  mov     eax, [rbx+42h]
0x180007ae5  mov     rdx, r14
0x180007ae8  add     r8, rax
0x180007aeb  add     rbx, 4Ah ; 'J'
0x180007aef  lea     r8, [rbx+r8*2]
0x180007af3  mov     ebx, 104h
0x180007af8  test    rdx, rdx
0x180007afb  jz      short loc_180007B1B
0x180007afd  movzx   eax, word ptr [r8]
0x180007b01  test    ax, ax
0x180007b04  jz      short loc_180007B1B
0x180007b06  mov     [r9], ax
0x180007b0a  add     r8, 2
0x180007b0e  add     r9, 2
0x180007b12  dec     rdx
0x180007b15  sub     rbx, 1
0x180007b19  jnz     short loc_180007AF8
0x180007b1b  test    rbx, rbx
0x180007b1e  lea     rcx, [r9-2]
0x180007b22  cmovnz  rcx, r9
0x180007b26  xor     eax, eax
0x180007b28  mov     [rcx], ax
0x180007b2b  test    r12, r12
0x180007b2e  jz      loc_180007C5A
0x180007b34  mov     rcx, r15
0x180007b37  mov     rax, r12
0x180007b3a  nop     word ptr [rax+rax+00h]
0x180007b40  cmp     word ptr [rax], 0
0x180007b44  jz      short loc_180007B50
0x180007b46  add     rax, 2
0x180007b4a  sub     rcx, 1
0x180007b4e  jnz     short loc_180007B40
0x180007b50  xor     eax, eax
0x180007b52  mov     rdx, r15
0x180007b55  test    rcx, rcx
0x180007b58  cmovnz  edi, eax
0x180007b5b  sub     rdx, rcx
0x180007b5e  test    rcx, rcx
0x180007b61  cmovz   rdx, rax
0x180007b65  jz      loc_180008283
0x180007b6b  sub     r15, rdx
0x180007b6e  lea     rcx, [rsp+900h+pszPath]
0x180007b73  lea     rdx, [r12+rdx*2]
0x180007b77  jz      short loc_180007BA1
0x180007b79  nop     dword ptr [rax+00000000h]
0x180007b80  test    r14, r14
0x180007b83  jz      short loc_180007BA1
0x180007b85  movzx   eax, word ptr [rcx]
0x180007b88  test    ax, ax
0x180007b8b  jz      short loc_180007BA1
0x180007b8d  mov     [rdx], ax
0x180007b90  add     rcx, 2
0x180007b94  add     rdx, 2
0x180007b98  dec     r14
0x180007b9b  sub     r15, 1
0x180007b9f  jnz     short loc_180007B80
0x180007ba1  xor     eax, eax
0x180007ba3  lea     rcx, [rdx-2]
0x180007ba7  test    r15, r15
0x180007baa  mov     edi, 8007007Ah
0x180007baf  cmovnz  rcx, rdx
0x180007bb3  cmovnz  edi, eax
0x180007bb6  mov     [rcx], ax
0x180007bb9  jz      loc_180008283
0x180007bbf  mov     rdx, [rsp+900h+var_898]
0x180007bc4  mov     rcx, r12; psz
0x180007bc7  mov     [rdx], eax
0x180007bc9  add     rdx, 8; ppwsz
0x180007bcd  call    cs:__imp_SHStrDupW
0x180007bd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180007bda  mov     ebx, eax
0x180007bdc  test    eax, eax
0x180007bde  js      loc_180008218
0x180007be4  lea     r14, WPP_GLOBAL_Control
0x180007beb  mov     edi, ebx
0x180007bed  test    ebx, ebx
0x180007bef  jns     loc_180007CCB
0x180007bf5  jmp     loc_180008253
0x180007bfa  cmp     dword ptr [rbx+42h], 1
0x180007bfe  jbe     short loc_180007C07
0x180007c00  mov     eax, [rbx+3Eh]
0x180007c03  lea     rbx, [rbx+rax*2]
0x180007c07  lea     rdx, [rbx+4Ah]
0x180007c0b  mov     rcx, r14
0x180007c0e  mov     ebx, 104h
0x180007c13  lea     r8, [rsp+900h+pszPath]
0x180007c18  test    rcx, rcx
0x180007c1b  jz      short loc_180007C3A
0x180007c1d  movzx   eax, word ptr [rdx]
0x180007c20  test    ax, ax
0x180007c23  jz      short loc_180007C3A
0x180007c25  mov     [r8], ax
0x180007c29  add     rdx, 2
0x180007c2d  add     r8, 2
0x180007c31  dec     rcx
0x180007c34  sub     rbx, 1
0x180007c38  jnz     short loc_180007C18
0x180007c3a  test    rbx, rbx
0x180007c3d  lea     rcx, [r8-2]
0x180007c41  cmovnz  rcx, r8
0x180007c45  xor     eax, eax
0x180007c47  mov     [rcx], ax
0x180007c4a  lea     rcx, [rsp+900h+pszPath]; pszPath
0x180007c4f  call    cs:__imp_PathFindFileNameW
0x180007c55  jmp     loc_180007B2B
0x180007c5a  mov     rdx, [rsp+900h+var_898]
0x180007c5f  lea     rcx, [rsp+900h+pszPath]; psz
0x180007c64  mov     dword ptr [rdx], 0
0x180007c6a  add     rdx, 8; ppwsz
0x180007c6e  call    cs:__imp_SHStrDupW
0x180007c74  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c7b  mov     ebx, eax
0x180007c7d  test    eax, eax
0x180007c7f  js      loc_1800081AD
0x180007c85  lea     r14, WPP_GLOBAL_Control
0x180007c8c  mov     edi, ebx
0x180007c8e  test    ebx, ebx
0x180007c90  js      loc_1800081E8
0x180007c96  jmp     short loc_180007CDE
0x180007c98  xor     eax, eax
0x180007c9a  lea     rcx, [r9-2]
0x180007c9e  test    r8, r8
0x180007ca1  mov     edx, 8007007Ah
0x180007ca6  cmovnz  rcx, r9
0x180007caa  cmovnz  edx, eax
0x180007cad  mov     [rcx], ax
0x180007cb0  jnz     short loc_180007D01
0x180007cb2  mov     r10, cs:WPP_GLOBAL_Control
0x180007cb9  lea     r14, WPP_GLOBAL_Control
0x180007cc0  mov     edi, edx
0x180007cc2  cmp     r10, r14
0x180007cc5  jnz     loc_18000818B
0x180007ccb  mov     rcx, r12; pv
0x180007cce  call    cs:__imp_CoTaskMemFree
0x180007cd4  test    edi, edi
0x180007cd6  js      loc_18000804B
0x180007cdc  mov     eax, edi
0x180007cde  mov     rcx, [rbp+800h+var_50]
0x180007ce5  xor     rcx, rsp; StackCookie
0x180007ce8  call    __security_check_cookie
0x180007ced  add     rsp, 8C8h
0x180007cf4  pop     r15
0x180007cf6  pop     r14
0x180007cf8  pop     r13
0x180007cfa  pop     r12
0x180007cfc  pop     rdi
0x180007cfd  pop     rsi
0x180007cfe  pop     rbx
0x180007cff  pop     rbp
0x180007d00  retn
0x180007d01  mov     rbx, [rsp+900h+var_8A0]
0x180007d06  jmp     loc_180007AC3
0x180007d0b  mov     edx, 2; dwMask
0x180007d10  mov     dword ptr [rsp+900h+psfs.fShowAllObjects], 0
0x180007d18  lea     rcx, [rsp+900h+psfs]; psfs
0x180007d1d  call    cs:__imp_SHGetSettings
0x180007d23  mov     esi, dword ptr [rsp+900h+psfs.fShowAllObjects]
0x180007d27  shl     esi, 1Eh
0x180007d2a  sar     esi, 1Fh
0x180007d2d  cmp     dword ptr [rbx+42h], 1
0x180007d31  jbe     loc_180007DD8
0x180007d37  mov     eax, [rbx+3Eh]
0x180007d3a  lea     rdx, [rbx+rax*2]
0x180007d3e  mov     ebx, 104h
0x180007d43  lea     r8, [rbp+800h+FullPath]
0x180007d4a  mov     r9d, ebx
0x180007d4d  mov     rcx, r14
0x180007d50  add     rdx, 4Ah ; 'J'
0x180007d54  test    rcx, rcx
0x180007d57  jz      short loc_180007D76
0x180007d59  movzx   eax, word ptr [rdx]
0x180007d5c  test    ax, ax
0x180007d5f  jz      short loc_180007D76
0x180007d61  mov     [r8], ax
0x180007d65  add     rdx, 2
0x180007d69  add     r8, 2
0x180007d6d  dec     rcx
0x180007d70  sub     r9, 1
0x180007d74  jnz     short loc_180007D54
0x180007d76  test    r9, r9
0x180007d79  lea     rcx, [r8-2]
0x180007d7d  cmovnz  rcx, r8
0x180007d81  xor     eax, eax
0x180007d83  mov     [rcx], ax
0x180007d86  lea     rcx, [rbp+800h+FullPath]; pszPath
0x180007d8d  call    cs:__imp_PathFindFileNameW
0x180007d93  test    esi, esi
0x180007d95  jz      short loc_180007DE0
0x180007d97  mov     rcx, r14
0x180007d9a  lea     rdx, [rbp+800h+FullPath]
0x180007da1  lea     r8, [rsp+900h+pszPath]
0x180007da6  test    rcx, rcx
0x180007da9  jz      short loc_180007DC8
0x180007dab  movzx   eax, word ptr [rdx]
0x180007dae  test    ax, ax
0x180007db1  jz      short loc_180007DC8
0x180007db3  mov     [r8], ax
0x180007db7  add     rdx, 2
0x180007dbb  add     r8, 2
0x180007dbf  dec     rcx
0x180007dc2  sub     rbx, 1
0x180007dc6  jnz     short loc_180007DA6
0x180007dc8  test    rbx, rbx
0x180007dcb  lea     rcx, [r8-2]
0x180007dcf  cmovnz  rcx, r8
0x180007dd3  jmp     loc_180007B26
0x180007dd8  mov     rdx, rbx
0x180007ddb  jmp     loc_180007D3E
0x180007de0  mov     rax, [rsp+900h+var_8A0]
0x180007de5  test    byte ptr [rax+0Ah], 2
0x180007de9  jnz     short loc_180007D97
0x180007deb  mov     [rsp+900h+ExtCount], rbx; ExtCount
0x180007df0  lea     rax, [rbp+800h+var_260]
0x180007df7  mov     [rsp+900h+Ext], rax; Ext
0x180007dfc  lea     rcx, [rbp+800h+FullPath]; FullPath
0x180007e03  lea     rax, [rbp+800h+var_470]
0x180007e0a  mov     [rsp+900h+FilenameCount], rbx; FilenameCount
0x180007e0f  mov     [rsp+900h+Filename], rax; Filename
0x180007e14  xor     r9d, r9d; Dir
0x180007e17  xor     r8d, r8d; DriveCount
0x180007e1a  mov     [rsp+900h+DirCount], 0; DirCount
0x180007e23  xor     edx, edx; Drive
0x180007e25  call    cs:__imp__wsplitpath_s
0x180007e2b  mov     rcx, r14
0x180007e2e  lea     rdx, [rbp+800h+var_470]
0x180007e35  lea     rax, [rsp+900h+pszPath]
0x180007e3a  test    rcx, rcx
0x180007e3d  jz      short loc_180007E5E
0x180007e3f  movzx   r8d, word ptr [rdx]
0x180007e43  test    r8w, r8w
0x180007e47  jz      short loc_180007E5E
0x180007e49  mov     [rax], r8w
0x180007e4d  add     rdx, 2
0x180007e51  add     rax, 2
0x180007e55  dec     rcx
0x180007e58  sub     rbx, 1
0x180007e5c  jnz     short loc_180007E3A
0x180007e5e  test    rbx, rbx
0x180007e61  lea     rcx, [rax-2]
0x180007e65  cmovnz  rcx, rax
0x180007e69  jmp     loc_180007B26
0x180007e6e  test    r13b, 1
0x180007e72  jnz     loc_180007AB2
0x180007e78  mov     ecx, 1040h; cb
0x180007e7d  call    cs:__imp_CoTaskMemAlloc
0x180007e83  mov     r12, rax
0x180007e86  test    rax, rax
0x180007e89  jz      loc_180008090
0x180007e8f  xor     edx, edx; Val
0x180007e91  mov     r8d, 1040h; Size
0x180007e97  mov     rcx, rax; void *
0x180007e9a  call    memset_0
0x180007e9f  mov     rbx, [rdi+30h]
0x180007ea3  mov     edx, 6; dwCoInit
0x180007ea8  xor     ecx, ecx; pvReserved
0x180007eaa  call    cs:__imp_CoInitializeEx
0x180007eb0  lea     r14, WPP_GLOBAL_Control
0x180007eb7  mov     esi, eax
  ... truncated ...
```
