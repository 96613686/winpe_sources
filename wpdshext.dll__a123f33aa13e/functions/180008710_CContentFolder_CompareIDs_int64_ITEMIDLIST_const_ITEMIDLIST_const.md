# CContentFolder::CompareIDs(__int64,_ITEMIDLIST const *,_ITEMIDLIST const *)

- ea: `0x180008710`
- end: `0x180009149`
- name: `?CompareIDs@CContentFolder@@UEAAJ_JPEFBU_ITEMIDLIST@@1@Z`
- size: `2617`
- prototype: `__int64 __fastcall(CContentFolder *__hidden this, __int64, const struct _ITEMIDLIST *, const struct _ITEMIDLIST *)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004190`
- `0x1800082e0`
- `0x180008710`
- `0x180014b60`
- `0x18001ef50`
- `0x18002ab58`
- `0x18002e224`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x180039dd4`
- `0x18006d9ec`
- `0x180075530`
- `0x18007559c`
- `0x180078010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180008c7d`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180008d0d`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180008c7d`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180008d0d`
- `KERNEL32!CompareFileTime` at `0x180009039`
- `KERNEL32!CompareFileTime` at `0x180009049`
- `KERNEL32!CompareFileTime` at `0x180009039`
- `KERNEL32!CompareFileTime` at `0x180009049`
- `KERNEL32!QueryPerformanceCounter` at `0x180008e81`
- `KERNEL32!QueryPerformanceCounter` at `0x180008e81`
- `SHLWAPI!PathFindFileNameW` at `0x180008986`
- `SHLWAPI!PathFindFileNameW` at `0x180008a4c`
- `SHLWAPI!PathFindFileNameW` at `0x180008986`
- `SHLWAPI!PathFindFileNameW` at `0x180008a4c`
- `SHLWAPI!StrCmpW` at `0x18000907d`
- `SHLWAPI!StrCmpW` at `0x18000907d`
- `SHLWAPI!StrCmpLogicalW` at `0x180008bdc`
- `SHLWAPI!StrCmpLogicalW` at `0x180008c1f`
- `SHLWAPI!StrCmpLogicalW` at `0x180008bdc`
- `SHLWAPI!StrCmpLogicalW` at `0x180008c1f`
- `ole32!PropVariantClear` at `0x180008883`
- `ole32!PropVariantClear` at `0x18000888e`
- `ole32!PropVariantClear` at `0x180008883`
- `ole32!PropVariantClear` at `0x18000888e`
- `SHELL32!SHGetSettings` at `0x18000890f`
- `SHELL32!SHGetSettings` at `0x1800089e5`
- `SHELL32!SHGetSettings` at `0x18000890f`
- `SHELL32!SHGetSettings` at `0x1800089e5`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CContentFolder::CompareIDs(
        CContentFolder *this,
        __int64 a2,
        const struct _ITEMIDLIST *a3,
        const struct _ITEMIDLIST *a4)
{
  const struct CONTENTITEM *v7; // r14
  CContentFolder *v8; // rcx
  const struct CONTENTITEM *v9; // r15
  int v10; // ebx
  int v12; // esi
  const struct CONTENTITEM *v13; // rdx
  __int64 v14; // rbx
  __int64 v15; // rcx
  WCHAR *v16; // rdx
  __int64 v17; // rdi
  __int64 v18; // r9
  WCHAR *v19; // r8
  WCHAR v20; // ax
  WCHAR *v21; // rcx
  __int64 v22; // rcx
  WCHAR *v23; // rdx
  __int64 v24; // r9
  WCHAR *v25; // r8
  WCHAR v26; // ax
  WCHAR *v27; // rcx
  int v28; // esi
  const struct CONTENTITEM *v29; // rdx
  __int64 v30; // rcx
  WCHAR *v31; // rdx
  __int64 v32; // r9
  WCHAR *v33; // r8
  WCHAR v34; // ax
  WCHAR *v35; // rcx
  __int64 v36; // rcx
  WCHAR *v37; // rdx
  __int64 v38; // r9
  WCHAR *v39; // r8
  WCHAR v40; // ax
  WCHAR *v41; // rcx
  __int64 v42; // rdx
  WCHAR *v43; // r8
  __int64 v44; // r10
  WCHAR *v45; // r9
  WCHAR v46; // ax
  WCHAR *v47; // rcx
  WCHAR *v48; // rdx
  WCHAR *v49; // r8
  WCHAR v50; // ax
  WCHAR *v51; // rcx
  __int64 v52; // rdi
  CContentFolder *v53; // r12
  unsigned __int64 vt; // rcx
  wchar_t *v55; // rdx
  WCHAR *v56; // rcx
  int v57; // eax
  __int64 v58; // rax
  wchar_t *v59; // rcx
  __int64 v60; // r8
  WCHAR *v61; // rdx
  wchar_t v62; // r9
  __int64 v63; // rax
  wchar_t *v64; // rcx
  __int64 v65; // r8
  WCHAR *v66; // rdx
  wchar_t v67; // r9
  CContentFolder *v68; // rcx
  int v69; // ecx
  int v70; // ebx
  int v71; // eax
  _QWORD *v72; // rcx
  __int64 v73; // rdx
  __int64 v74; // r9
  CContentFolder *v75; // rcx
  unsigned int v76; // r9d
  unsigned __int64 v77; // rax
  CContentFolder *v78; // rcx
  unsigned int v79; // r9d
  unsigned __int16 v80; // ax
  int v81; // eax
  SHELLFLAGSTATE psfs; // [rsp+50h] [rbp-B0h] BYREF
  int v83; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v84; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v85; // [rsp+60h] [rbp-A0h] BYREF
  PROPVARIANT v86; // [rsp+68h] [rbp-98h] BYREF
  PROPVARIANT pvar; // [rsp+80h] [rbp-80h] BYREF
  CContentFolder *v88; // [rsp+98h] [rbp-68h]
  const struct _ITEMIDLIST *v89; // [rsp+A0h] [rbp-60h]
  const struct _ITEMIDLIST *v90; // [rsp+A8h] [rbp-58h]
  __int64 v91; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v92; // [rsp+B8h] [rbp-48h]
  LARGE_INTEGER PerformanceCount[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v94; // [rsp+D0h] [rbp-30h]
  __int64 v95; // [rsp+E0h] [rbp-20h]
  char v96; // [rsp+E8h] [rbp-18h]
  WCHAR pszPath[264]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR psz2[264]; // [rsp+300h] [rbp+200h] BYREF
  WCHAR psz1[264]; // [rsp+510h] [rbp+410h] BYREF
  WCHAR v100[264]; // [rsp+720h] [rbp+620h] BYREF
  WCHAR v101[264]; // [rsp+930h] [rbp+830h] BYREF
  wchar_t Filename[264]; // [rsp+B40h] [rbp+A40h] BYREF
  WCHAR v103[264]; // [rsp+D50h] [rbp+C50h] BYREF
  WCHAR v104[264]; // [rsp+F60h] [rbp+E60h] BYREF
  wchar_t Ext[520]; // [rsp+1170h] [rbp+1070h] BYREF

  v89 = a4;
  v90 = a3;
  v88 = this;
  v91 = 0;
  v92 = 0;
  v96 = 0;
  *(_OWORD *)&PerformanceCount[0].LowPart = 0;
  v94 = 0;
  v95 = 0;
  v83 = 0;
  v7 = CContentFolder::_IsValid(0, a3);
  v9 = CContentFolder::_IsValid(v8, a4);
  memset_0(v101, 0, 0x208u);
  memset_0(v100, 0, 0x208u);
  memset_0(psz1, 0, 0x208u);
  memset_0(psz2, 0, 0x208u);
  memset_0(v104, 0, 0x208u);
  memset_0(v103, 0, 0x208u);
  v85 = 0;
  v84 = 0;
  memset(&pvar, 0, sizeof(pvar));
  memset(&v86, 0, sizeof(v86));
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
  {
    QueryPerformanceCounter(PerformanceCount);
    v91 = 3;
    v92 = 0;
    v94 = 0;
    v96 = 1;
  }
  if ( !v7 )
  {
    v10 = -2147024809;
    goto LABEL_5;
  }
  if ( !v9 )
  {
    v10 = -2147024809;
    goto LABEL_5;
  }
  if ( (unsigned __int16)a2 >= (unsigned __int64)*((unsigned int *)this + 16) )
  {
    v10 = -2147024809;
    goto LABEL_5;
  }
  psfs = 0;
  SHGetSettings(&psfs, 2u);
  v12 = (int)(*(_DWORD *)&psfs << 30) >> 31;
  if ( *(_DWORD *)((char *)v7 + 66) <= 1u )
    v13 = v7;
  else
    v13 = (const struct CONTENTITEM *)((char *)v7 + 2 * *(unsigned int *)((char *)v7 + 62));
  v14 = 2147483646;
  v15 = 2147483646;
  v16 = (WCHAR *)((char *)v13 + 74);
  v17 = 260;
  v18 = 260;
  v19 = pszPath;
  do
  {
    if ( !v15 )
      break;
    v20 = *v16;
    if ( !*v16 )
      break;
    ++v16;
    *v19++ = v20;
    --v15;
    --v18;
  }
  while ( v18 );
  v21 = v19 - 1;
  if ( v18 )
    v21 = v19;
  *v21 = 0;
  PathFindFileNameW(pszPath);
  if ( v12 || (*((_BYTE *)v7 + 10) & 2) != 0 )
  {
    v22 = 2147483646;
    v23 = pszPath;
    v24 = 260;
    v25 = v101;
    do
    {
      if ( !v22 )
        break;
      v26 = *v23;
      if ( !*v23 )
        break;
      ++v23;
      *v25++ = v26;
      --v22;
      --v24;
    }
    while ( v24 );
    v27 = v25 - 1;
    if ( v24 )
      v27 = v25;
  }
  else
  {
    _wsplitpath_s(pszPath, 0, 0, 0, 0, Filename, 0x104u, Ext, 0x104u);
    v58 = 2147483646;
    v59 = Filename;
    v60 = 260;
    v61 = v101;
    do
    {
      if ( !v58 )
        break;
      v62 = *v59;
      if ( !*v59 )
        break;
      ++v59;
      *v61++ = v62;
      --v58;
      --v60;
    }
    while ( v60 );
    v27 = v61 - 1;
    if ( v60 )
      v27 = v61;
  }
  *v27 = 0;
  psfs = 0;
  SHGetSettings(&psfs, 2u);
  v28 = (int)(*(_DWORD *)&psfs << 30) >> 31;
  if ( *(_DWORD *)((char *)v9 + 66) <= 1u )
    v29 = v9;
  else
    v29 = (const struct CONTENTITEM *)((char *)v9 + 2 * *(unsigned int *)((char *)v9 + 62));
  v30 = 2147483646;
  v31 = (WCHAR *)((char *)v29 + 74);
  v32 = 260;
  v33 = pszPath;
  do
  {
    if ( !v30 )
      break;
    v34 = *v31;
    if ( !*v31 )
      break;
    ++v31;
    *v33++ = v34;
    --v30;
    --v32;
  }
  while ( v32 );
  v35 = v33 - 1;
  if ( v32 )
    v35 = v33;
  *v35 = 0;
  PathFindFileNameW(pszPath);
  if ( v28 || (*((_BYTE *)v9 + 10) & 2) != 0 )
  {
    v36 = 2147483646;
    v37 = pszPath;
    v38 = 260;
    v39 = v100;
    do
    {
      if ( !v36 )
        break;
      v40 = *v37;
      if ( !*v37 )
        break;
      ++v37;
      *v39++ = v40;
      --v36;
      --v38;
    }
    while ( v38 );
    v41 = v39 - 1;
    if ( v38 )
      v41 = v39;
  }
  else
  {
    _wsplitpath_s(pszPath, 0, 0, 0, 0, Filename, 0x104u, Ext, 0x104u);
    v63 = 2147483646;
    v64 = Filename;
    v65 = 260;
    v66 = v100;
    do
    {
      if ( !v63 )
        break;
      v67 = *v64;
      if ( !*v64 )
        break;
      ++v64;
      *v66++ = v67;
      --v63;
      --v65;
    }
    while ( v65 );
    v41 = v66 - 1;
    if ( v65 )
      v41 = v66;
  }
  *v41 = 0;
  v42 = 2147483646;
  v43 = (WCHAR *)((char *)v7 + 2 * *(unsigned int *)((char *)v7 + 66) + 2 * *(unsigned int *)((char *)v7 + 62) + 74);
  v44 = 260;
  v45 = psz1;
  do
  {
    if ( !v42 )
      break;
    v46 = *v43;
    if ( !*v43 )
      break;
    ++v43;
    *v45++ = v46;
    --v42;
    --v44;
  }
  while ( v44 );
  v47 = v45 - 1;
  if ( v44 )
    v47 = v45;
  *v47 = 0;
  v48 = (WCHAR *)((char *)v9 + 2 * *(unsigned int *)((char *)v9 + 66) + 2 * *(unsigned int *)((char *)v9 + 62) + 74);
  v49 = psz2;
  do
  {
    if ( !v14 )
      break;
    v50 = *v48;
    if ( !*v48 )
      break;
    ++v48;
    *v49++ = v50;
    --v14;
    --v17;
  }
  while ( v17 );
  v51 = v49 - 1;
  if ( v17 )
    v51 = v49;
  *v51 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        (unsigned int)WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
        (unsigned int)v101,
        (__int64)psz1);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        (unsigned int)WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
        (unsigned int)v100,
        (__int64)psz2);
  }
  if ( (*((_BYTE *)v7 + 10) & 2) != 0 )
  {
    if ( (*((_BYTE *)v9 + 10) & 2) == 0 )
      goto LABEL_73;
  }
  else if ( (*((_BYTE *)v9 + 10) & 2) != 0 )
  {
    goto LABEL_134;
  }
  v52 = 24LL * (unsigned __int16)a2;
  v53 = v88;
  vt = *(unsigned int *)(v52 + *((_QWORD *)v88 + 9));
  if ( (_DWORD)vt == 8976 )
    goto LABEL_65;
  vt = (unsigned int)(vt - 8978);
  if ( !(_DWORD)vt )
  {
    v77 = *(_QWORD *)((char *)v9 + 18);
    if ( *(_QWORD *)((char *)v7 + 18) < v77 )
      goto LABEL_73;
    if ( *(_QWORD *)((char *)v7 + 18) <= v77 )
      goto LABEL_65;
LABEL_134:
    LOWORD(v57) = 1;
    goto LABEL_71;
  }
  v68 = (CContentFolder *)(unsigned int)(vt - 1);
  if ( !(_DWORD)v68 )
  {
    CContentFolder::_Type(v68, v7, v104, (unsigned int)v45);
    CContentFolder::_Type(v75, v9, v103, v76);
    v57 = StrCmpW(v104, v103);
LABEL_130:
    if ( v57 )
      goto LABEL_71;
    goto LABEL_65;
  }
  v69 = (_DWORD)v68 - 1;
  if ( !v69 )
  {
    v57 = CompareFileTime((const FILETIME *)((char *)v7 + 26), (const FILETIME *)((char *)v9 + 26));
    goto LABEL_130;
  }
  if ( v69 == 1 )
  {
    v57 = CompareFileTime((const FILETIME *)((char *)v7 + 34), (const FILETIME *)((char *)v9 + 34));
    goto LABEL_130;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, const struct CONTENTITEM *, __int64 *, __int64))(*((_QWORD *)v88 - 2) + 32LL))(
          (__int64)v88 - 16,
          v7,
          &v85,
          1);
  if ( v10 < 0 )
  {
    v72 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_5;
    v73 = 30;
LABEL_109:
    v74 = (unsigned int)v10;
LABEL_110:
    WPP_SF_d(v72[2], v73, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, v74);
    goto LABEL_5;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, const struct CONTENTITEM *, __int64 *, __int64))(*((_QWORD *)v53 - 2) + 32LL))(
          (__int64)v53 - 16,
          v9,
          &v84,
          1);
  if ( v10 < 0 )
  {
    v72 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_5;
    v73 = 31;
    goto LABEL_109;
  }
  v70 = (*(__int64 (__fastcall **)(__int64, _QWORD, PROPVARIANT *))(*(_QWORD *)v85 + 40LL))(
          v85,
          *(_QWORD *)(v52 + *((_QWORD *)v53 + 9) + 16),
          &pvar);
  v71 = (*(__int64 (__fastcall **)(__int64, _QWORD, PROPVARIANT *))(*(_QWORD *)v84 + 40LL))(
          v84,
          *(_QWORD *)(v52 + *((_QWORD *)v53 + 9) + 16),
          &v86);
  if ( v70 >= 0 )
  {
    vt = pvar.vt;
    if ( pvar.vt != 10 )
    {
      if ( pvar.vt )
      {
        if ( v71 < 0 || v86.vt == 10 || !v86.vt )
          goto LABEL_134;
        v10 = PropVariantCompare(&pvar, &v86, &v83, 0);
        if ( v10 < 0 )
        {
          v72 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_5;
          v73 = 32;
          goto LABEL_109;
        }
        v57 = v83;
        goto LABEL_130;
      }
    }
  }
  if ( v71 >= 0 && v86.vt != 10 && v86.vt )
  {
    LOWORD(v57) = -1;
    goto LABEL_71;
  }
LABEL_65:
  if ( (a2 & 0x10000000) != 0 )
  {
    if ( !psz1[0] || !psz2[0] )
    {
      CContentFolder::_Name((CContentFolder *)vt, v7, pszPath, (unsigned int)v45);
      CContentFolder::_Name(v78, v9, Filename, v79);
      v55 = Filename;
      v56 = pszPath;
      goto LABEL_69;
    }
LABEL_68:
    v55 = psz2;
    v56 = psz1;
LABEL_69:
    v57 = StrCmpLogicalW(v56, v55);
    goto LABEL_70;
  }
  if ( (a2 & 0x80000000) == 0 )
  {
    v57 = StrCmpLogicalW(v101, v100);
    if ( v57 )
      goto LABEL_71;
    goto LABEL_68;
  }
  v80 = *((_WORD *)v7 + 2);
  if ( v80 < *((_WORD *)v9 + 2) )
  {
LABEL_73:
    v10 = 0xFFFF;
    goto LABEL_5;
  }
  if ( v80 > *((_WORD *)v9 + 2) )
    goto LABEL_134;
  v57 = memcmp_0(v7, v9, *((unsigned __int16 *)v7 + 2));
LABEL_70:
  if ( v57 )
  {
LABEL_71:
    v10 = (unsigned __int16)v57;
    goto LABEL_5;
  }
  if ( v53 == (CContentFolder *)16 )
    v53 = 0;
  v81 = ILCompareRelIDs(v53, v90, v89, a2);
  v10 = v81;
  if ( v81 < 0 )
  {
    v72 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v73 = 33;
      v74 = (unsigned int)v81;
      goto LABEL_110;
    }
  }
LABEL_5:
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
  {
    StringCchPrintfW(Ext, 0x208u, L"1=%s/2=%s", v101, v100);
    CPerfTraceHelper::ProcessPerformanceData((CPerfTraceHelper *)&v91, 3u, v10, Ext);
  }
  PropVariantClear(&pvar);
  PropVariantClear(&v86);
  if ( v84 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
  if ( v85 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180008710  push    rbp
0x180008712  push    rbx
0x180008713  push    rsi
0x180008714  push    rdi
0x180008715  push    r12
0x180008717  push    r13
0x180008719  push    r14
0x18000871b  push    r15
0x18000871d  lea     rbp, [rsp-1498h]
0x180008725  mov     eax, 1598h
0x18000872a  call    _alloca_probe
0x18000872f  sub     rsp, rax
0x180008732  mov     rax, cs:__security_cookie
0x180008739  xor     rax, rsp
0x18000873c  mov     [rbp+14D0h+var_50], rax
0x180008743  mov     rdi, r9
0x180008746  mov     [rbp+14D0h+var_1530], r9
0x18000874a  mov     [rbp+14D0h+var_1528], r8
0x18000874e  mov     r13, rdx
0x180008751  mov     rbx, rcx
0x180008754  mov     [rbp+14D0h+var_1538], rcx
0x180008758  xor     esi, esi
0x18000875a  mov     [rbp+14D0h+var_1520], rsi
0x18000875e  mov     [rbp+14D0h+var_1518], rsi
0x180008762  mov     [rbp+14D0h+var_14E8], sil
0x180008766  xorps   xmm0, xmm0
0x180008769  movdqa  xmmword ptr [rbp+14D0h+PerformanceCount], xmm0
0x18000876e  xorps   xmm1, xmm1
0x180008771  movdqa  [rbp+14D0h+var_1500], xmm1
0x180008776  mov     [rbp+14D0h+var_14F0], rsi
0x18000877a  mov     [rsp+15D0h+var_157C], esi
0x18000877e  xor     ecx, ecx; this
0x180008780  movups  xmmword ptr [rbp+14D0h+pvar], xmm0
0x180008784  mov     qword ptr [rbp+14D0h+pvar+10h], rcx
0x180008788  movups  xmmword ptr [rsp+15D0h+var_1568], xmm1
0x18000878d  mov     qword ptr [rsp+15D0h+var_1568+10h], rcx
0x180008792  mov     rdx, r8; struct _ITEMIDLIST *
0x180008795  call    ?_IsValid@CContentFolder@@QEAAPEFBUCONTENTITEM@@PEFBU_ITEMIDLIST@@@Z; CContentFolder::_IsValid(_ITEMIDLIST const *)
0x18000879a  mov     r14, rax
0x18000879d  mov     rdx, rdi; struct _ITEMIDLIST *
0x1800087a0  call    ?_IsValid@CContentFolder@@QEAAPEFBUCONTENTITEM@@PEFBU_ITEMIDLIST@@@Z; CContentFolder::_IsValid(_ITEMIDLIST const *)
0x1800087a5  mov     r15, rax
0x1800087a8  xor     edx, edx; Val
0x1800087aa  mov     r8d, 208h; Size
0x1800087b0  lea     rcx, [rbp+14D0h+var_CA0]; void *
0x1800087b7  call    memset_0
0x1800087bc  xor     edx, edx; Val
0x1800087be  mov     r8d, 208h; Size
0x1800087c4  lea     rcx, [rbp+14D0h+var_EB0]; void *
0x1800087cb  call    memset_0
0x1800087d0  xor     edx, edx; Val
0x1800087d2  mov     r8d, 208h; Size
0x1800087d8  lea     rcx, [rbp+14D0h+psz1]; void *
0x1800087df  call    memset_0
0x1800087e4  xor     edx, edx; Val
0x1800087e6  mov     r8d, 208h; Size
0x1800087ec  lea     rcx, [rbp+14D0h+psz2]; void *
0x1800087f3  call    memset_0
0x1800087f8  xor     edx, edx; Val
0x1800087fa  mov     r8d, 208h; Size
0x180008800  lea     rcx, [rbp+14D0h+var_670]; void *
0x180008807  call    memset_0
0x18000880c  xor     edx, edx; Val
0x18000880e  mov     r8d, 208h; Size
0x180008814  lea     rcx, [rbp+14D0h+var_880]; void *
0x18000881b  call    memset_0
0x180008820  mov     [rsp+15D0h+var_1570], rsi
0x180008825  mov     [rsp+15D0h+var_1578], rsi
0x18000882a  xorps   xmm0, xmm0
0x18000882d  xor     eax, eax
0x18000882f  movups  xmmword ptr [rbp+14D0h+pvar], xmm0
0x180008833  mov     qword ptr [rbp+14D0h+pvar+10h], rax
0x180008837  xorps   xmm1, xmm1
0x18000883a  movups  xmmword ptr [rsp+15D0h+var_1568], xmm1
0x18000883f  mov     qword ptr [rsp+15D0h+var_1568+10h], rax
0x180008844  cmp     [rbp+14D0h+var_14E8], al
0x180008847  jnz     short loc_18000885D
0x180008849  mov     rax, cs:WPP_GLOBAL_Control
0x180008850  test    dword ptr [rax+1Ch], 800h
0x180008857  jnz     loc_180008E7D
0x18000885d  test    r14, r14
0x180008860  jnz     loc_1800088E8
0x180008866  mov     ebx, 80070057h
0x18000886b  mov     rax, cs:WPP_GLOBAL_Control
0x180008872  test    dword ptr [rax+1Ch], 800h
0x180008879  jnz     loc_180008E35
0x18000887f  lea     rcx, [rbp+14D0h+pvar]; pvar
0x180008883  call    cs:__imp_PropVariantClear
0x180008889  lea     rcx, [rsp+15D0h+var_1568]; pvar
0x18000888e  call    cs:__imp_PropVariantClear
0x180008894  nop
0x180008895  mov     rcx, [rsp+15D0h+var_1578]
0x18000889a  test    rcx, rcx
0x18000889d  jz      short loc_1800088AC
0x18000889f  mov     rax, [rcx]
0x1800088a2  mov     rax, [rax+10h]
0x1800088a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088ab  nop
0x1800088ac  mov     rcx, [rsp+15D0h+var_1570]
0x1800088b1  test    rcx, rcx
0x1800088b4  jz      short loc_1800088C3
0x1800088b6  mov     rax, [rcx]
0x1800088b9  mov     rax, [rax+10h]
0x1800088bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088c2  nop
0x1800088c3  mov     eax, ebx
0x1800088c5  mov     rcx, [rbp+14D0h+var_50]
0x1800088cc  xor     rcx, rsp; StackCookie
0x1800088cf  call    __security_check_cookie
0x1800088d4  add     rsp, 1598h
0x1800088db  pop     r15
0x1800088dd  pop     r14
0x1800088df  pop     r13
0x1800088e1  pop     r12
0x1800088e3  pop     rdi
0x1800088e4  pop     rsi
0x1800088e5  pop     rbx
0x1800088e6  pop     rbp
0x1800088e7  retn
0x1800088e8  test    r15, r15
0x1800088eb  jz      loc_180008EA4
0x1800088f1  movzx   r12d, r13w
0x1800088f5  mov     eax, [rbx+40h]
0x1800088f8  cmp     r12, rax
0x1800088fb  jnb     loc_180008EAE
0x180008901  mov     dword ptr [rsp+15D0h+psfs.fShowAllObjects], esi
0x180008905  mov     edx, 2; dwMask
0x18000890a  lea     rcx, [rsp+15D0h+psfs]; psfs
0x18000890f  call    cs:__imp_SHGetSettings
0x180008915  mov     esi, dword ptr [rsp+15D0h+psfs.fShowAllObjects]
0x180008919  shl     esi, 1Eh
0x18000891c  sar     esi, 1Fh
0x18000891f  cmp     dword ptr [r14+42h], 1
0x180008924  jbe     loc_180008C2B
0x18000892a  mov     eax, [r14+3Eh]
0x18000892e  lea     rdx, [r14+rax*2]
0x180008932  mov     ebx, 7FFFFFFEh
0x180008937  mov     ecx, ebx
0x180008939  add     rdx, 4Ah ; 'J'
0x18000893d  mov     edi, 104h
0x180008942  mov     r9d, edi
0x180008945  lea     r8, [rbp+14D0h+pszPath]
0x180008949  nop     dword ptr [rax+00000000h]
0x180008950  test    rcx, rcx
0x180008953  jz      short loc_180008972
0x180008955  movzx   eax, word ptr [rdx]
0x180008958  test    ax, ax
0x18000895b  jz      short loc_180008972
0x18000895d  add     rdx, 2
0x180008961  mov     [r8], ax
0x180008965  add     r8, 2
0x180008969  dec     rcx
0x18000896c  sub     r9, 1
0x180008970  jnz     short loc_180008950
0x180008972  lea     rcx, [r8-2]
0x180008976  test    r9, r9
0x180008979  cmovnz  rcx, r8
0x18000897d  xor     eax, eax
0x18000897f  mov     [rcx], ax
0x180008982  lea     rcx, [rbp+14D0h+pszPath]; pszPath
0x180008986  call    cs:__imp_PathFindFileNameW
0x18000898c  test    esi, esi
0x18000898e  jz      loc_180008C3B
0x180008994  mov     rcx, rbx
0x180008997  lea     rdx, [rbp+14D0h+pszPath]
0x18000899b  mov     r9, rdi
0x18000899e  lea     r8, [rbp+14D0h+var_CA0]
0x1800089a5  test    rcx, rcx
0x1800089a8  jz      short loc_1800089C7
0x1800089aa  movzx   eax, word ptr [rdx]
0x1800089ad  test    ax, ax
0x1800089b0  jz      short loc_1800089C7
0x1800089b2  add     rdx, 2
0x1800089b6  mov     [r8], ax
0x1800089ba  add     r8, 2
0x1800089be  dec     rcx
0x1800089c1  sub     r9, 1
0x1800089c5  jnz     short loc_1800089A5
0x1800089c7  lea     rcx, [r8-2]
0x1800089cb  test    r9, r9
0x1800089ce  cmovnz  rcx, r8
0x1800089d2  xor     eax, eax
0x1800089d4  mov     [rcx], ax
0x1800089d7  mov     dword ptr [rsp+15D0h+psfs.fShowAllObjects], eax
0x1800089db  mov     edx, 2; dwMask
0x1800089e0  lea     rcx, [rsp+15D0h+psfs]; psfs
0x1800089e5  call    cs:__imp_SHGetSettings
0x1800089eb  mov     esi, dword ptr [rsp+15D0h+psfs.fShowAllObjects]
0x1800089ef  shl     esi, 1Eh
0x1800089f2  sar     esi, 1Fh
0x1800089f5  cmp     dword ptr [r15+42h], 1
0x1800089fa  jbe     loc_180008C33
0x180008a00  mov     eax, [r15+3Eh]
0x180008a04  lea     rdx, [r15+rax*2]
0x180008a08  mov     rcx, rbx
0x180008a0b  add     rdx, 4Ah ; 'J'
0x180008a0f  mov     r9, rdi
0x180008a12  lea     r8, [rbp+14D0h+pszPath]
0x180008a16  test    rcx, rcx
0x180008a19  jz      short loc_180008A38
0x180008a1b  movzx   eax, word ptr [rdx]
0x180008a1e  test    ax, ax
0x180008a21  jz      short loc_180008A38
0x180008a23  add     rdx, 2
0x180008a27  mov     [r8], ax
0x180008a2b  add     r8, 2
0x180008a2f  dec     rcx
0x180008a32  sub     r9, 1
0x180008a36  jnz     short loc_180008A16
0x180008a38  lea     rcx, [r8-2]
0x180008a3c  test    r9, r9
0x180008a3f  cmovnz  rcx, r8
0x180008a43  xor     eax, eax
0x180008a45  mov     [rcx], ax
0x180008a48  lea     rcx, [rbp+14D0h+pszPath]; pszPath
0x180008a4c  call    cs:__imp_PathFindFileNameW
0x180008a52  test    esi, esi
0x180008a54  jz      loc_180008CCB
0x180008a5a  mov     rcx, rbx
0x180008a5d  lea     rdx, [rbp+14D0h+pszPath]
0x180008a61  mov     r9, rdi
0x180008a64  lea     r8, [rbp+14D0h+var_EB0]
0x180008a6b  nop     dword ptr [rax+rax+00h]
0x180008a70  test    rcx, rcx
0x180008a73  jz      short loc_180008A92
0x180008a75  movzx   eax, word ptr [rdx]
0x180008a78  test    ax, ax
0x180008a7b  jz      short loc_180008A92
0x180008a7d  add     rdx, 2
0x180008a81  mov     [r8], ax
0x180008a85  add     r8, 2
0x180008a89  dec     rcx
0x180008a8c  sub     r9, 1
0x180008a90  jnz     short loc_180008A70
0x180008a92  lea     rcx, [r8-2]
0x180008a96  test    r9, r9
0x180008a99  cmovnz  rcx, r8
0x180008a9d  xor     eax, eax
0x180008a9f  mov     [rcx], ax
0x180008aa2  mov     rdx, rbx
0x180008aa5  mov     r8d, [r14+3Eh]
0x180008aa9  mov     eax, [r14+42h]
0x180008aad  add     r8, 25h ; '%'
0x180008ab1  add     r8, rax
0x180008ab4  lea     r8, [r14+r8*2]
0x180008ab8  mov     r10, rdi
0x180008abb  lea     r9, [rbp+14D0h+psz1]
0x180008ac2  test    rdx, rdx
0x180008ac5  jz      short loc_180008AE5
0x180008ac7  movzx   eax, word ptr [r8]
0x180008acb  test    ax, ax
0x180008ace  jz      short loc_180008AE5
0x180008ad0  add     r8, 2
0x180008ad4  mov     [r9], ax
0x180008ad8  add     r9, 2; unsigned int
0x180008adc  dec     rdx
0x180008adf  sub     r10, 1
0x180008ae3  jnz     short loc_180008AC2
0x180008ae5  lea     rcx, [r9-2]
0x180008ae9  test    r10, r10
0x180008aec  cmovnz  rcx, r9
0x180008af0  xor     eax, eax
0x180008af2  mov     [rcx], ax
0x180008af5  mov     edx, [r15+3Eh]
0x180008af9  mov     eax, [r15+42h]
0x180008afd  add     rdx, 25h ; '%'
0x180008b01  add     rdx, rax
0x180008b04  lea     rdx, [r15+rdx*2]
0x180008b08  lea     r8, [rbp+14D0h+psz2]
0x180008b0f  nop
0x180008b10  test    rbx, rbx
0x180008b13  jz      short loc_180008B32
0x180008b15  movzx   eax, word ptr [rdx]
0x180008b18  test    ax, ax
0x180008b1b  jz      short loc_180008B32
0x180008b1d  add     rdx, 2
0x180008b21  mov     [r8], ax
0x180008b25  add     r8, 2
0x180008b29  dec     rbx
0x180008b2c  sub     rdi, 1
0x180008b30  jnz     short loc_180008B10
0x180008b32  lea     rcx, [r8-2]
0x180008b36  test    rdi, rdi
0x180008b39  cmovnz  rcx, r8
0x180008b3d  xor     eax, eax
0x180008b3f  mov     [rcx], ax
0x180008b42  lea     rsi, WPP_GLOBAL_Control
0x180008b49  mov     rcx, cs:WPP_GLOBAL_Control
0x180008b50  cmp     rcx, rsi
0x180008b53  jz      short loc_180008B75
0x180008b55  test    byte ptr [rcx+1Ch], 40h
0x180008b59  jnz     loc_180008EB8
0x180008b5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008b66  cmp     rcx, rsi
0x180008b69  jz      short loc_180008B75
0x180008b6b  test    byte ptr [rcx+1Ch], 40h
0x180008b6f  jnz     loc_180008EE5
0x180008b75  test    byte ptr [r14+0Ah], 2
0x180008b7a  jnz     short loc_180008BF2
0x180008b7c  test    byte ptr [r15+0Ah], 2
  ... truncated ...
```
