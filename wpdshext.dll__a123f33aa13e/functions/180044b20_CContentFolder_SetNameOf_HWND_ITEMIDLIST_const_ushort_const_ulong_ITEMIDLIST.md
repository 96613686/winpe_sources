# CContentFolder::SetNameOf(HWND__ *,_ITEMIDLIST const *,ushort const *,ulong,_ITEMIDLIST * *)

- ea: `0x180044b20`
- end: `0x180045157`
- name: `?SetNameOf@CContentFolder@@UEAAJPEAUHWND__@@PEFBU_ITEMIDLIST@@PEBGKPEAPEFAU3@@Z`
- size: `1591`
- prototype: `__int64 __fastcall(CContentFolder *__hidden this, HWND, const struct _ITEMIDLIST *, const unsigned __int16 *, unsigned int, struct _ITEMIDLIST **)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004110`
- `0x180004190`
- `0x1800050d0`
- `0x1800082e0`
- `0x18000ef50`
- `0x180019d90`
- `0x1800285c8`
- `0x1800287d0`
- `0x18002ff5c`
- `0x1800339cc`
- `0x180035590`
- `0x1800359b0`
- `0x180039654`
- `0x180039e80`
- `0x180044b20`
- `0x180048924`
- `0x18005d784`
- `0x180075530`
- `0x180078010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180044c8e`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180044d49`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180044c8e`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180044d49`
- `ADVAPI32!RegCloseKey` at `0x180044e98`
- `ADVAPI32!RegCloseKey` at `0x180044e98`
- `SHLWAPI!StrCmpIW` at `0x180044cf6`
- `SHLWAPI!StrCmpIW` at `0x180044d67`
- `SHLWAPI!StrCmpIW` at `0x180044e61`
- `SHLWAPI!StrCmpIW` at `0x180044f01`
- `SHLWAPI!StrCmpIW` at `0x180044cf6`
- `SHLWAPI!StrCmpIW` at `0x180044d67`
- `SHLWAPI!StrCmpIW` at `0x180044e61`
- `SHLWAPI!StrCmpIW` at `0x180044f01`
- `SHLWAPI!PathRemoveBlanksW` at `0x180044bfa`
- `SHLWAPI!PathRemoveBlanksW` at `0x180044bfa`
- `SHLWAPI!AssocQueryKeyW` at `0x180044e89`
- `SHLWAPI!AssocQueryKeyW` at `0x180044e89`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180044eba`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180044eba`
- `ole32!CoTaskMemFree` at `0x180044fe5`
- `ole32!CoTaskMemFree` at `0x180044fe5`
- `SHELL32!SHGetSettings` at `0x180044bae`
- `SHELL32!SHGetSettings` at `0x180044bae`
- `SHELL32!__imp_ILFree` at `0x180045121`
- `SHELL32!__imp_ILFree` at `0x180045121`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CContentFolder::SetNameOf(
        CContentFolder *this,
        HWND a2,
        const struct _ITEMIDLIST *a3,
        const unsigned __int16 *a4,
        __int16 a5,
        struct _ITEMIDLIST **a6)
{
  const struct CONTENTITEM *v10; // rdi
  int v11; // ebx
  int IDList; // eax
  PVOID *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  CContentFolder *v16; // rcx
  unsigned int v17; // r9d
  int v18; // eax
  __int64 v19; // r9
  int ObjectID; // eax
  unsigned int v21; // r8d
  LPITEMIDLIST v22; // rdi
  SHELLFLAGSTATE psfs; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  struct IPortableDevice *v26; // [rsp+60h] [rbp-A0h] BYREF
  HKEY phkeyOut; // [rsp+68h] [rbp-98h] BYREF
  LPITEMIDLIST pidl[2]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t pszPath[264]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t psz2[264]; // [rsp+290h] [rbp+190h] BYREF
  wchar_t Ext[264]; // [rsp+4A0h] [rbp+3A0h] BYREF
  wchar_t psz1[264]; // [rsp+6B0h] [rbp+5B0h] BYREF
  wchar_t FullPath[264]; // [rsp+8C0h] [rbp+7C0h] BYREF
  unsigned __int16 v34[264]; // [rsp+AD0h] [rbp+9D0h] BYREF
  unsigned __int16 v35[264]; // [rsp+CE0h] [rbp+BE0h] BYREF
  wchar_t Filename[264]; // [rsp+EF0h] [rbp+DF0h] BYREF

  pidl[0] = 0;
  phkeyOut = 0;
  v26 = 0;
  if ( a6 )
    *a6 = 0;
  v10 = CContentFolder::_IsValid(this, a3);
  if ( !v10 )
    goto LABEL_4;
  psfs = 0;
  SHGetSettings(&psfs, 2u);
  IDList = StringCchCopyW(pszPath, 0x104u, a4);
  v11 = IDList;
  if ( IDList < 0 )
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_76;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_69;
    v14 = 69;
LABEL_66:
    v19 = (unsigned int)IDList;
LABEL_67:
    WPP_SF_d(v13[2], v14, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, v19);
    goto LABEL_68;
  }
  PathRemoveBlanksW(pszPath);
  if ( (*((_BYTE *)v10 + 10) & 2) != 0 )
    goto LABEL_20;
  v15 = -1;
  do
    ++v15;
  while ( pszPath[v15] );
  while ( v15 && *((_WORD *)&pidl[1] + v15 + 3) == 46 )
  {
    --v15;
    if ( (unsigned __int64)(2 * v15) >= 0x208 )
      _report_rangecheckfailure();
    pszPath[v15] = 0;
  }
  if ( (*((_BYTE *)v10 + 10) & 2) != 0 || (*(_BYTE *)&psfs & 2) == 0 )
  {
LABEL_20:
    Ext[0] = 0;
    IDList = StringCchCopyW(psz1, 0x104u, pszPath);
    v11 = IDList;
    if ( IDList < 0 )
    {
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_76;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_69;
      v14 = 70;
      goto LABEL_66;
    }
  }
  else
  {
    _wsplitpath_s(pszPath, 0, 0, 0, 0, psz1, 0x104u, Ext, 0x104u);
  }
  if ( !StrCmpIW(psz1, &String) )
  {
LABEL_4:
    v11 = -2147024809;
LABEL_68:
    v13 = (PVOID *)WPP_GLOBAL_Control;
LABEL_69:
    if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 2) != 0 )
      WPP_SF_d(v13[2], 78, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)v11);
    goto LABEL_76;
  }
  CContentFolder::_Name(v16, v10, FullPath, v17);
  _wsplitpath_s(FullPath, 0, 0, 0, 0, Filename, 0x104u, psz2, 0x104u);
  if ( (*((_BYTE *)v10 + 10) & 2) == 0 )
  {
    if ( !StrCmpIW(Ext, &String) && (a5 & 0x8000) == 0 && (*(_BYTE *)&psfs & 2) == 0 && psz2[0] )
    {
      IDList = StringCchCopyW(Ext, 0x104u, psz2);
      v11 = IDList;
      if ( IDList < 0 )
      {
        v13 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_76;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_69;
        v14 = 71;
        goto LABEL_66;
      }
      v18 = StringCchCatW(pszPath, 0x104u, psz2);
      v11 = v18;
      if ( v18 < 0 )
      {
        v13 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_76;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_69;
        WPP_SF_SSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          72,
          (unsigned int)WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
          (unsigned int)pszPath,
          (__int64)psz2,
          v18);
        goto LABEL_68;
      }
    }
    if ( StrCmpIW(Ext, psz2) )
    {
      if ( AssocQueryKeyW(0, ASSOCKEY_SHELLEXECCLASS, psz2, 0, &phkeyOut) >= 0 )
      {
        RegCloseKey(phkeyOut);
        if ( ShellMessageBoxW(g_hInst, a2, (LPCWSTR)0x10C, (LPCWSTR)0x10B, 0x34u) == 7 )
        {
          v11 = -2147023673;
          v13 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
            goto LABEL_76;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_69;
          v14 = 73;
          v19 = 2147943623LL;
          goto LABEL_67;
        }
      }
    }
  }
  if ( !StrCmpIW(pszPath, FullPath) )
  {
    v11 = 1;
    goto LABEL_76;
  }
  StringCchCopyW(
    v34,
    0x104u,
    (const unsigned __int16 *)v10 + *(unsigned int *)((char *)v10 + 62) + *(unsigned int *)((char *)v10 + 66) + 37);
  ObjectID = CBaseFolder::_GetObjectID((CContentFolder *)((char *)this - 16), v34, v35, 0x104u);
  v11 = ObjectID;
  if ( ObjectID < 0 )
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_76;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_69;
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      74,
      (unsigned int)WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
      (unsigned int)v34,
      ObjectID);
    goto LABEL_68;
  }
  v11 = CContentFolder::_RenameElement((CContentFolder *)((char *)this - 16), a3, pszPath);
  if ( v11 == -2147286960 )
  {
    pv = 0;
    if ( (int)SHILCombine(*((_QWORD *)this + 6), a3, &pv) >= 0 )
      _DisplayApplyError((struct _ITEMIDLIST *)pv, a2, v21);
    CoTaskMemFree(pv);
    goto LABEL_55;
  }
  if ( v11 < 0 )
  {
LABEL_55:
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_76;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_69;
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      75,
      (unsigned int)WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
      (unsigned int)pszPath,
      v11);
    goto LABEL_68;
  }
  IDList = (*(__int64 (__fastcall **)(char *, _QWORD, struct IPortableDevice **))(*((_QWORD *)this - 2) + 136LL))(
             (char *)this - 16,
             *((_QWORD *)this + 6),
             &v26);
  v11 = IDList;
  if ( IDList < 0 )
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_76;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_69;
    v14 = 76;
    goto LABEL_66;
  }
  IDList = CContentFolder::_CreateIDList((CContentFolder *)((char *)this - 16), v26, v35, 0, pidl, (int *)&pv);
  v11 = IDList;
  if ( IDList < 0 )
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_76;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_69;
    v14 = 77;
    goto LABEL_66;
  }
  v22 = pidl[0];
  CBaseFolder::_ChangeNotifyItem((CContentFolder *)((char *)this - 16), 1, a3, pidl[0]);
  if ( a6 )
  {
    *a6 = v22;
  }
  else if ( v22 )
  {
    ILFree(v22);
  }
LABEL_76:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180044b20  push    rbp
0x180044b22  push    rbx
0x180044b23  push    rsi
0x180044b24  push    rdi
0x180044b25  push    r12
0x180044b27  push    r13
0x180044b29  push    r14
0x180044b2b  push    r15
0x180044b2d  lea     rbp, [rsp-1018h]
0x180044b35  mov     eax, 1118h
0x180044b3a  call    _alloca_probe
0x180044b3f  sub     rsp, rax
0x180044b42  mov     rax, cs:__security_cookie
0x180044b49  xor     rax, rsp
0x180044b4c  mov     [rbp+1050h+var_50], rax
0x180044b53  mov     rbx, r9
0x180044b56  mov     r15, r8
0x180044b59  mov     r12, rdx
0x180044b5c  mov     r13, rcx
0x180044b5f  mov     r14, [rbp+1050h+arg_28]
0x180044b66  xor     esi, esi
0x180044b68  mov     [rsp+1150h+pidl], rsi
0x180044b6d  mov     [rsp+1150h+phkeyOut], rsi
0x180044b72  mov     [rsp+1150h+var_10F0], rsi
0x180044b77  test    r14, r14
0x180044b7a  jz      short loc_180044B7F
0x180044b7c  mov     [r14], rsi
0x180044b7f  mov     rdx, r15; struct _ITEMIDLIST *
0x180044b82  call    ?_IsValid@CContentFolder@@QEAAPEFBUCONTENTITEM@@PEFBU_ITEMIDLIST@@@Z; CContentFolder::_IsValid(_ITEMIDLIST const *)
0x180044b87  mov     rdi, rax
0x180044b8a  test    rax, rax
0x180044b8d  jnz     short loc_180044BA0
0x180044b8f  mov     ebx, 80070057h
0x180044b94  lea     rdi, WPP_GLOBAL_Control
0x180044b9b  jmp     loc_1800450CB
0x180044ba0  mov     dword ptr [rsp+1150h+psfs.fShowAllObjects], esi
0x180044ba4  mov     edx, 2; dwMask
0x180044ba9  lea     rcx, [rsp+1150h+psfs]; psfs
0x180044bae  call    cs:__imp_SHGetSettings
0x180044bb4  mov     r8, rbx; unsigned __int16 *
0x180044bb7  mov     edx, 104h; unsigned __int64
0x180044bbc  lea     rcx, [rbp+1050h+pszPath]; unsigned __int16 *
0x180044bc0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180044bc5  mov     ebx, eax
0x180044bc7  test    eax, eax
0x180044bc9  jns     short loc_180044BF6
0x180044bcb  mov     rcx, cs:WPP_GLOBAL_Control
0x180044bd2  lea     rdi, WPP_GLOBAL_Control
0x180044bd9  cmp     rcx, rdi
0x180044bdc  jz      loc_180045128
0x180044be2  test    byte ptr [rcx+1Ch], 2
0x180044be6  jz      loc_1800450D2
0x180044bec  mov     edx, 45h ; 'E'
0x180044bf1  jmp     loc_1800450B8
0x180044bf6  lea     rcx, [rbp+1050h+pszPath]; pszPath
0x180044bfa  call    cs:__imp_PathRemoveBlanksW
0x180044c00  test    byte ptr [rdi+0Ah], 2
0x180044c04  jnz     loc_180044C96
0x180044c0a  lea     rax, [rbp+1050h+pszPath]
0x180044c0e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180044c12  inc     rcx
0x180044c15  cmp     [rax+rcx*2], si
0x180044c19  jnz     short loc_180044C12
0x180044c1b  test    rcx, rcx
0x180044c1e  jz      short loc_180044C49
0x180044c20  mov     eax, 2Eh ; '.'
0x180044c25  cmp     ax, [rsp+rcx*2+1150h+var_10D2]
0x180044c2a  jnz     short loc_180044C49
0x180044c2c  dec     rcx
0x180044c2f  lea     rdx, [rcx+rcx]
0x180044c33  cmp     rdx, 208h
0x180044c3a  jnb     short loc_180044C43
0x180044c3c  mov     [rbp+rdx+1050h+pszPath], si
0x180044c41  jmp     short loc_180044C1B
0x180044c43  call    __report_rangecheckfailure
0x180044c49  test    byte ptr [rdi+0Ah], 2
0x180044c4d  jnz     short loc_180044C96
0x180044c4f  test    byte ptr [rsp+1150h+psfs.fShowAllObjects], 2
0x180044c54  jz      short loc_180044C96
0x180044c56  mov     ebx, 104h
0x180044c5b  mov     [rsp+1150h+ExtCount], rbx; ExtCount
0x180044c60  lea     rax, [rbp+1050h+var_CB0]
0x180044c67  mov     [rsp+1150h+Ext], rax; Ext
0x180044c6c  mov     [rsp+1150h+FilenameCount], rbx; FilenameCount
0x180044c71  lea     rax, [rbp+1050h+psz1]
0x180044c78  mov     [rsp+1150h+Filename], rax; Filename
0x180044c7d  mov     [rsp+1150h+DirCount], rsi; DirCount
0x180044c82  xor     r9d, r9d; Dir
0x180044c85  xor     r8d, r8d; DriveCount
0x180044c88  xor     edx, edx; Drive
0x180044c8a  lea     rcx, [rbp+1050h+pszPath]; FullPath
0x180044c8e  call    cs:__imp__wsplitpath_s
0x180044c94  jmp     short loc_180044CE8
0x180044c96  mov     [rbp+1050h+var_CB0], si
0x180044c9d  lea     r8, [rbp+1050h+pszPath]; unsigned __int16 *
0x180044ca1  mov     edx, 104h; unsigned __int64
0x180044ca6  lea     rcx, [rbp+1050h+psz1]; unsigned __int16 *
0x180044cad  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180044cb2  mov     ebx, eax
0x180044cb4  test    eax, eax
0x180044cb6  jns     short loc_180044CE3
0x180044cb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180044cbf  lea     rdi, WPP_GLOBAL_Control
0x180044cc6  cmp     rcx, rdi
0x180044cc9  jz      loc_180045128
0x180044ccf  test    byte ptr [rcx+1Ch], 2
0x180044cd3  jz      loc_1800450D2
0x180044cd9  mov     edx, 46h ; 'F'
0x180044cde  jmp     loc_1800450B8
0x180044ce3  mov     ebx, 104h
0x180044ce8  lea     rdx, String; psz2
0x180044cef  lea     rcx, [rbp+1050h+psz1]; psz1
0x180044cf6  call    cs:__imp_StrCmpIW
0x180044cfc  test    eax, eax
0x180044cfe  jz      loc_180044B8F
0x180044d04  lea     r8, [rbp+1050h+FullPath]; unsigned __int16 *
0x180044d0b  mov     rdx, rdi; struct CONTENTITEM *
0x180044d0e  call    ?_Name@CContentFolder@@QEAAPEBGPEFBUCONTENTITEM@@PEAGI@Z; CContentFolder::_Name(CONTENTITEM const *,ushort *,uint)
0x180044d13  mov     [rsp+1150h+ExtCount], rbx; ExtCount
0x180044d18  lea     rax, [rbp+1050h+psz2]
0x180044d1f  mov     [rsp+1150h+Ext], rax; Ext
0x180044d24  mov     [rsp+1150h+FilenameCount], rbx; FilenameCount
0x180044d29  lea     rax, [rbp+1050h+var_260]
0x180044d30  mov     [rsp+1150h+Filename], rax; Filename
0x180044d35  mov     [rsp+1150h+DirCount], rsi; DirCount
0x180044d3a  xor     r9d, r9d; Dir
0x180044d3d  xor     r8d, r8d; DriveCount
0x180044d40  xor     edx, edx; Drive
0x180044d42  lea     rcx, [rbp+1050h+FullPath]; FullPath
0x180044d49  call    cs:__imp__wsplitpath_s
0x180044d4f  test    byte ptr [rdi+0Ah], 2
0x180044d53  jnz     loc_180044EF6
0x180044d59  lea     rdx, String; psz2
0x180044d60  lea     rcx, [rbp+1050h+var_CB0]; psz1
0x180044d67  call    cs:__imp_StrCmpIW
0x180044d6d  test    eax, eax
0x180044d6f  jnz     loc_180044E53
0x180044d75  test    dword ptr [rbp+1050h+arg_20], 8000h
0x180044d7f  jnz     loc_180044E53
0x180044d85  test    byte ptr [rsp+1150h+psfs.fShowAllObjects], 2
0x180044d8a  jnz     loc_180044E53
0x180044d90  cmp     [rbp+1050h+psz2], si
0x180044d97  jz      loc_180044E53
0x180044d9d  lea     r8, [rbp+1050h+psz2]; unsigned __int16 *
0x180044da4  mov     rdx, rbx; unsigned __int64
0x180044da7  lea     rcx, [rbp+1050h+var_CB0]; unsigned __int16 *
0x180044dae  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180044db3  mov     ebx, eax
0x180044db5  test    eax, eax
0x180044db7  jns     short loc_180044DE4
0x180044db9  mov     rcx, cs:WPP_GLOBAL_Control
0x180044dc0  lea     rdi, WPP_GLOBAL_Control
0x180044dc7  cmp     rcx, rdi
0x180044dca  jz      loc_180045128
0x180044dd0  test    byte ptr [rcx+1Ch], 2
0x180044dd4  jz      loc_1800450D2
0x180044dda  mov     edx, 47h ; 'G'
0x180044ddf  jmp     loc_1800450B8
0x180044de4  lea     r8, [rbp+1050h+psz2]; unsigned __int16 *
0x180044deb  mov     edx, 104h; unsigned __int64
0x180044df0  lea     rcx, [rbp+1050h+pszPath]; unsigned __int16 *
0x180044df4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180044df9  mov     ebx, eax
0x180044dfb  test    eax, eax
0x180044dfd  jns     short loc_180044E4E
0x180044dff  mov     rcx, cs:WPP_GLOBAL_Control
0x180044e06  lea     rdi, WPP_GLOBAL_Control
0x180044e0d  cmp     rcx, rdi
0x180044e10  jz      loc_180045128
0x180044e16  test    byte ptr [rcx+1Ch], 2
0x180044e1a  jz      loc_1800450D2
0x180044e20  mov     edx, 48h ; 'H'
0x180044e25  mov     dword ptr [rsp+1150h+Filename], eax
0x180044e29  lea     rax, [rbp+1050h+psz2]
0x180044e30  mov     [rsp+1150h+DirCount], rax
0x180044e35  lea     r9, [rbp+1050h+pszPath]
0x180044e39  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x180044e40  mov     rcx, [rcx+10h]
0x180044e44  call    WPP_SF_SSd
0x180044e49  jmp     loc_1800450CB
0x180044e4e  mov     ebx, 104h
0x180044e53  lea     rdx, [rbp+1050h+psz2]; psz2
0x180044e5a  lea     rcx, [rbp+1050h+var_CB0]; psz1
0x180044e61  call    cs:__imp_StrCmpIW
0x180044e67  test    eax, eax
0x180044e69  jz      loc_180044EF6
0x180044e6f  lea     rax, [rsp+1150h+phkeyOut]
0x180044e74  mov     [rsp+1150h+DirCount], rax; phkeyOut
0x180044e79  xor     r9d, r9d; pszExtra
0x180044e7c  lea     r8, [rbp+1050h+psz2]; pszAssoc
0x180044e83  lea     edx, [r9+1]; key
0x180044e87  xor     ecx, ecx; flags
0x180044e89  call    cs:__imp_AssocQueryKeyW
0x180044e8f  test    eax, eax
0x180044e91  js      short loc_180044EF6
0x180044e93  mov     rcx, [rsp+1150h+phkeyOut]; hKey
0x180044e98  call    cs:__imp_RegCloseKey
0x180044e9e  mov     dword ptr [rsp+1150h+DirCount], 34h ; '4'; fuStyle
0x180044ea6  mov     r9d, 10Bh; lpcTitle
0x180044eac  lea     r8d, [r9+1]; lpcText
0x180044eb0  mov     rdx, r12; hWnd
0x180044eb3  mov     rcx, cs:g_hInst; hAppInst
0x180044eba  call    cs:__imp_ShellMessageBoxW
0x180044ec0  cmp     eax, 7
0x180044ec3  jnz     short loc_180044EF6
0x180044ec5  mov     ebx, 800704C7h
0x180044eca  mov     rcx, cs:WPP_GLOBAL_Control
0x180044ed1  lea     rdi, WPP_GLOBAL_Control
0x180044ed8  cmp     rcx, rdi
0x180044edb  jz      loc_180045128
0x180044ee1  test    byte ptr [rcx+1Ch], 2
0x180044ee5  jz      loc_1800450D2
0x180044eeb  lea     edx, [rax+42h]
0x180044eee  mov     r9d, ebx
0x180044ef1  jmp     loc_1800450BB
0x180044ef6  lea     rdx, [rbp+1050h+FullPath]; psz2
0x180044efd  lea     rcx, [rbp+1050h+pszPath]; psz1
0x180044f01  call    cs:__imp_StrCmpIW
0x180044f07  test    eax, eax
0x180044f09  jnz     short loc_180044F13
0x180044f0b  lea     ebx, [rax+1]
0x180044f0e  jmp     loc_180045128
0x180044f13  mov     ecx, [rdi+42h]
0x180044f16  mov     eax, [rdi+3Eh]
0x180044f19  add     rax, 25h ; '%'
0x180044f1d  add     rcx, rax
0x180044f20  lea     r8, [rdi+rcx*2]; unsigned __int16 *
0x180044f24  mov     rdx, rbx; unsigned __int64
0x180044f27  lea     rcx, [rbp+1050h+var_680]; unsigned __int16 *
0x180044f2e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180044f33  lea     rsi, [r13-10h]
0x180044f37  mov     r9d, ebx; unsigned int
0x180044f3a  lea     r8, [rbp+1050h+var_470]; unsigned __int16 *
0x180044f41  lea     rdx, [rbp+1050h+var_680]; unsigned __int16 *
0x180044f48  mov     rcx, rsi; this
0x180044f4b  call    ?_GetObjectID@CBaseFolder@@QEAAJPEBGPEAGI@Z; CBaseFolder::_GetObjectID(ushort const *,ushort *,uint)
0x180044f50  mov     ebx, eax
0x180044f52  test    eax, eax
0x180044f54  jns     short loc_180044F9C
0x180044f56  mov     rcx, cs:WPP_GLOBAL_Control
0x180044f5d  lea     rdi, WPP_GLOBAL_Control
0x180044f64  cmp     rcx, rdi
0x180044f67  jz      loc_180045128
0x180044f6d  test    byte ptr [rcx+1Ch], 2
0x180044f71  jz      loc_1800450D2
0x180044f77  mov     edx, 4Ah ; 'J'
0x180044f7c  mov     dword ptr [rsp+1150h+DirCount], eax
0x180044f80  lea     r9, [rbp+1050h+var_680]
0x180044f87  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x180044f8e  mov     rcx, [rcx+10h]
0x180044f92  call    WPP_SF_Sd
0x180044f97  jmp     loc_1800450CB
0x180044f9c  lea     r8, [rbp+1050h+pszPath]; unsigned __int16 *
0x180044fa0  mov     rdx, r15; struct _ITEMIDLIST *
0x180044fa3  mov     rcx, rsi; this
0x180044fa6  call    ?_RenameElement@CContentFolder@@AEAAJPEFBU_ITEMIDLIST@@PEBG@Z; CContentFolder::_RenameElement(_ITEMIDLIST const *,ushort const *)
0x180044fab  mov     ebx, eax
0x180044fad  cmp     eax, 80030050h
0x180044fb2  jnz     short loc_180044FED
0x180044fb4  mov     [rsp+1150h+pv], 0
0x180044fbd  lea     r8, [rsp+1150h+pv]
0x180044fc2  mov     rdx, r15
0x180044fc5  mov     rcx, [r13+30h]
0x180044fc9  call    SHILCombine
0x180044fce  test    eax, eax
0x180044fd0  js      short loc_180044FE0
0x180044fd2  mov     rdx, r12; HWND
0x180044fd5  mov     rcx, [rsp+1150h+pv]; struct _ITEMIDLIST *
0x180044fda  call    ?_DisplayApplyError@@YAXPEFAU_ITEMIDLIST@@PEAUHWND__@@I@Z; _DisplayApplyError(_ITEMIDLIST *,HWND__ *,uint)
0x180044fdf  nop
0x180044fe0  mov     rcx, [rsp+1150h+pv]; pv
0x180044fe5  call    cs:__imp_CoTaskMemFree
0x180044feb  jmp     short loc_180044FF1
0x180044fed  test    ebx, ebx
0x180044fef  jns     short loc_180045024
0x180044ff1  mov     rcx, cs:WPP_GLOBAL_Control
0x180044ff8  lea     rdi, WPP_GLOBAL_Control
0x180044fff  cmp     rcx, rdi
0x180045002  jz      loc_180045128
0x180045008  test    byte ptr [rcx+1Ch], 2
0x18004500c  jz      loc_1800450D2
0x180045012  mov     edx, 4Bh ; 'K'
0x180045017  mov     dword ptr [rsp+1150h+DirCount], ebx
0x18004501b  lea     r9, [rbp+1050h+pszPath]
0x18004501f  jmp     loc_180044F87
0x180045024  mov     rax, [rsi]
0x180045027  lea     r8, [rsp+1150h+var_10F0]
0x18004502c  mov     rdx, [r13+30h]
0x180045030  mov     rcx, rsi
0x180045033  mov     rax, [rax+88h]
0x18004503a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004503f  mov     ebx, eax
0x180045041  test    eax, eax
0x180045043  jns     short loc_180045069
0x180045045  mov     rcx, cs:WPP_GLOBAL_Control
0x18004504c  lea     rdi, WPP_GLOBAL_Control
0x180045053  cmp     rcx, rdi
0x180045056  jz      loc_180045128
0x18004505c  test    byte ptr [rcx+1Ch], 2
0x180045060  jz      short loc_1800450D2
  ... truncated ...
```
