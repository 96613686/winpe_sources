# _ApplyRename(_ITEMIDLIST *,HWND__ *,int,ushort const *,int,CContentFolder *)

- ea: `0x18005d2a4`
- end: `0x18005d77c`
- name: `?_ApplyRename@@YAHPEFAU_ITEMIDLIST@@PEAUHWND__@@HPEBGHPEAVCContentFolder@@@Z`
- size: `1240`
- prototype: `__int64 __fastcall(struct _ITEMIDLIST *, HWND, int nIDDlgItem, LPCWSTR lpString, int, struct CContentFolder *)`
- caller_count: `4`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004ac30`
- `0x18004bee4`
- `0x18005a1f0`
- `0x1800688e0`

## callees

- `0x180004110`
- `0x180004a80`
- `0x180019d90`
- `0x1800285c8`
- `0x18002ff5c`
- `0x1800339cc`
- `0x180035590`
- `0x1800361ba`
- `0x18005d2a4`
- `0x18005d784`
- `0x18006260c`
- `0x180078010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18005d60f`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18005d60f`
- `KERNEL32!lstrcmpiW` at `0x18005d35d`
- `KERNEL32!lstrcmpiW` at `0x18005d35d`
- `SHLWAPI!__imp_StrCmpCW` at `0x18005d348`
- `SHLWAPI!__imp_StrCmpCW` at `0x18005d348`
- `USER32!SendMessageW` at `0x18005d724`
- `USER32!SendMessageW` at `0x18005d724`
- `USER32!SetDlgItemTextW` at `0x18005d702`
- `USER32!SetDlgItemTextW` at `0x18005d702`
- `USER32!GetDlgItem` at `0x18005d328`
- `USER32!GetDlgItem` at `0x18005d710`
- `USER32!GetDlgItem` at `0x18005d328`
- `USER32!GetDlgItem` at `0x18005d710`
- `USER32!GetWindowTextW` at `0x18005d33b`
- `USER32!GetWindowTextW` at `0x18005d33b`
- `SHELL32!SHGetSettings` at `0x18005d50c`
- `SHELL32!SHGetSettings` at `0x18005d50c`
- `SHELL32!SHBindToParent` at `0x18005d383`
- `SHELL32!SHBindToParent` at `0x18005d44b`
- `SHELL32!SHBindToParent` at `0x18005d383`
- `SHELL32!SHBindToParent` at `0x18005d44b`
- `SHELL32!__imp_ILFree` at `0x18005d73e`
- `SHELL32!__imp_ILFree` at `0x18005d73e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall _ApplyRename(
        struct _ITEMIDLIST *a1,
        HWND a2,
        int nIDDlgItem,
        LPCWSTR lpString,
        int a5,
        struct CContentFolder *a6)
{
  unsigned int v10; // edi
  HWND DlgItem; // rax
  int v12; // eax
  HRESULT v13; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  int StringProperty; // eax
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  int v19; // eax
  int ObjectIDFromDisplayName; // eax
  unsigned int v21; // r8d
  HWND v22; // rax
  wchar_t *Filename; // [rsp+28h] [rbp-D8h]
  void *ppv; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v26; // [rsp+58h] [rbp-A8h] BYREF
  int v27; // [rsp+60h] [rbp-A0h] BYREF
  SHELLFLAGSTATE psfs; // [rsp+64h] [rbp-9Ch] BYREF
  LPCITEMIDLIST ppidlLast; // [rsp+68h] [rbp-98h] BYREF
  LPITEMIDLIST pidl[2]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR String[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR psz1[264]; // [rsp+290h] [rbp+190h] BYREF
  wchar_t Ext[264]; // [rsp+4A0h] [rbp+3A0h] BYREF
  wchar_t FullPath[264]; // [rsp+6B0h] [rbp+5B0h] BYREF
  unsigned __int16 v35[264]; // [rsp+8C0h] [rbp+7C0h] BYREF
  wchar_t v36[264]; // [rsp+AD0h] [rbp+9D0h] BYREF

  v10 = 0;
  ppv = 0;
  ppidlLast = 0;
  pidl[0] = 0;
  memset_0(String, 0, 0x208u);
  memset_0(v35, 0, 0x208u);
  if ( !a1 )
    goto LABEL_50;
  DlgItem = GetDlgItem(a2, nIDDlgItem);
  GetWindowTextW(DlgItem, String, 260);
  if ( !StrCmpCW(lpString, String) )
    goto LABEL_15;
  v12 = lstrcmpiW(lpString, String);
  if ( !a5 )
  {
    if ( !v12 )
    {
LABEL_15:
      v10 = 1;
      goto LABEL_48;
    }
    v13 = SHBindToParent(a1, &GUID_000214e6_0000_0000_c000_000000000046, &ppv, &ppidlLast);
    if ( v13 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v15 = 12;
        goto LABEL_8;
      }
      goto LABEL_48;
    }
    v27 = 0x20000000;
    (*(void (__fastcall **)(void *, __int64, LPCITEMIDLIST *, int *))(*(_QWORD *)ppv + 72LL))(ppv, 1, &ppidlLast, &v27);
    v13 = StringCchCopyW(psz1, 0x104u, String);
    if ( v13 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v15 = 13;
        goto LABEL_8;
      }
      goto LABEL_48;
    }
    if ( (v27 & 0x20000000) == 0 )
    {
      psfs = 0;
      SHGetSettings(&psfs, 2u);
      if ( (*(_BYTE *)&psfs & 2) == 0 )
      {
        v26 = 0;
        StringProperty = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))ppv)(
                           ppv,
                           &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1,
                           &v26);
        if ( StringProperty < 0 )
        {
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_31;
          v18 = 14;
LABEL_30:
          WPP_SF_d(v17[2], v18, WPP_d6eb988fd8b53d28659d82e20842895c_Traceguids, (unsigned int)StringProperty);
LABEL_31:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
          goto LABEL_48;
        }
        StringProperty = GetStringProperty(v26, ppidlLast, &PKEY_WPDNSE_Name, FullPath, 260);
        if ( StringProperty < 0 )
        {
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_31;
          v18 = 15;
          goto LABEL_30;
        }
        _wsplitpath_s(FullPath, 0, 0, 0, 0, v36, 0x104u, Ext, 0x104u);
        v19 = StringCchCatW(psz1, 0x104u, Ext);
        if ( v19 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            LODWORD(Filename) = v19;
            WPP_SF_SSd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              16,
              (unsigned int)WPP_d6eb988fd8b53d28659d82e20842895c_Traceguids,
              (unsigned int)psz1,
              (__int64)Ext,
              Filename);
          }
          goto LABEL_31;
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
      }
    }
    if ( a6 )
      ObjectIDFromDisplayName = CContentFolder::_GetObjectIDFromDisplayName(a6, psz1, v35);
    else
      ObjectIDFromDisplayName = (*(__int64 (__fastcall **)(void *, HWND, _QWORD, WCHAR *, _QWORD, LPITEMIDLIST *, _QWORD))(*(_QWORD *)ppv + 24LL))(
                                  ppv,
                                  a2,
                                  0,
                                  psz1,
                                  0,
                                  pidl,
                                  0);
    if ( ObjectIDFromDisplayName < 0 )
    {
      if ( ObjectIDFromDisplayName == -2147024894 )
        v10 = 1;
    }
    else
    {
      _DisplayApplyError(a1, a2, v21);
      SetDlgItemTextW(a2, nIDDlgItem, lpString);
      v22 = GetDlgItem(a2, 312);
      SendMessageW(v22, 0xB1u, 0, 0);
    }
    goto LABEL_48;
  }
  v13 = SHBindToParent(a1, &GUID_000214e6_0000_0000_c000_000000000046, &ppv, &ppidlLast);
  if ( v13 >= 0 )
  {
    v13 = (*(__int64 (__fastcall **)(void *, HWND, LPCITEMIDLIST, WCHAR *, int, _QWORD))(*(_QWORD *)ppv + 96LL))(
            ppv,
            a2,
            ppidlLast,
            String,
            1,
            0);
    if ( v13 >= 0 )
    {
      v10 = 1;
    }
    else
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v15 = 11;
        goto LABEL_8;
      }
    }
  }
  else
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v15 = 10;
LABEL_8:
      WPP_SF_d(v14[2], v15, WPP_d6eb988fd8b53d28659d82e20842895c_Traceguids, (unsigned int)v13);
    }
  }
LABEL_48:
  if ( pidl[0] )
  {
    ILFree(pidl[0]);
    pidl[0] = 0;
  }
LABEL_50:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return v10;
}

```

## disassembly

```asm
0x18005d2a4  push    rbp
0x18005d2a6  push    rbx
0x18005d2a7  push    rsi
0x18005d2a8  push    rdi
0x18005d2a9  push    r12
0x18005d2ab  push    r13
0x18005d2ad  push    r14
0x18005d2af  push    r15
0x18005d2b1  lea     rbp, [rsp-0BF8h]
0x18005d2b9  sub     rsp, 0CF8h
0x18005d2c0  mov     rax, cs:__security_cookie
0x18005d2c7  xor     rax, rsp
0x18005d2ca  mov     [rbp+0C30h+var_50], rax
0x18005d2d1  mov     r15, r9
0x18005d2d4  mov     r13d, r8d
0x18005d2d7  mov     rsi, rdx
0x18005d2da  mov     r14, rcx
0x18005d2dd  mov     r12, [rbp+0C30h+arg_28]
0x18005d2e4  xor     edi, edi
0x18005d2e6  mov     [rsp+0D30h+ppv], rdi
0x18005d2eb  mov     [rsp+0D30h+ppidlLast], rdi
0x18005d2f0  mov     [rsp+0D30h+pidl], rdi
0x18005d2f5  mov     ebx, 208h
0x18005d2fa  mov     r8d, ebx; Size
0x18005d2fd  xor     edx, edx; Val
0x18005d2ff  lea     rcx, [rbp+0C30h+String]; void *
0x18005d303  call    memset_0
0x18005d308  mov     r8d, ebx; Size
0x18005d30b  xor     edx, edx; Val
0x18005d30d  lea     rcx, [rbp+0C30h+var_470]; void *
0x18005d314  call    memset_0
0x18005d319  test    r14, r14
0x18005d31c  jz      loc_18005D74D
0x18005d322  mov     edx, r13d; nIDDlgItem
0x18005d325  mov     rcx, rsi; hDlg
0x18005d328  call    cs:__imp_GetDlgItem
0x18005d32e  mov     rcx, rax; hWnd
0x18005d331  mov     r8d, 104h; nMaxCount
0x18005d337  lea     rdx, [rbp+0C30h+String]; lpString
0x18005d33b  call    cs:__imp_GetWindowTextW
0x18005d341  lea     rdx, [rbp+0C30h+String]; pszStr2
0x18005d345  mov     rcx, r15; pszStr1
0x18005d348  call    cs:__imp_StrCmpCW
0x18005d34e  test    eax, eax
0x18005d350  jz      loc_18005D42D
0x18005d356  lea     rdx, [rbp+0C30h+String]; lpString2
0x18005d35a  mov     rcx, r15; lpString1
0x18005d35d  call    cs:__imp_lstrcmpiW
0x18005d363  cmp     [rbp+0C30h+arg_20], edi
0x18005d369  jz      loc_18005D429
0x18005d36f  lea     r9, [rsp+0D30h+ppidlLast]; ppidlLast
0x18005d374  lea     r8, [rsp+0D30h+ppv]; ppv
0x18005d379  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x18005d380  mov     rcx, r14; pidl
0x18005d383  call    cs:__imp_SHBindToParent
0x18005d389  test    eax, eax
0x18005d38b  jns     short loc_18005D3C9
0x18005d38d  lea     rdx, WPP_GLOBAL_Control
0x18005d394  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d39b  cmp     rcx, rdx
0x18005d39e  jz      loc_18005D734
0x18005d3a4  test    byte ptr [rcx+1Ch], 2
0x18005d3a8  jz      loc_18005D734
0x18005d3ae  lea     edx, [rdi+0Ah]
0x18005d3b1  mov     r9d, eax
0x18005d3b4  lea     r8, WPP_d6eb988fd8b53d28659d82e20842895c_Traceguids
0x18005d3bb  mov     rcx, [rcx+10h]
0x18005d3bf  call    WPP_SF_d
0x18005d3c4  jmp     loc_18005D734
0x18005d3c9  mov     rcx, [rsp+0D30h+ppv]
0x18005d3ce  mov     rax, [rcx]
0x18005d3d1  mov     [rsp+0D30h+Filename], 0
0x18005d3da  mov     ebx, 1
0x18005d3df  mov     dword ptr [rsp+0D30h+DirCount], ebx
0x18005d3e3  lea     r9, [rbp+0C30h+String]
0x18005d3e7  mov     r8, [rsp+0D30h+ppidlLast]
0x18005d3ec  mov     rdx, rsi
0x18005d3ef  mov     rax, [rax+60h]
0x18005d3f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d3f8  test    eax, eax
0x18005d3fa  jns     short loc_18005D422
0x18005d3fc  lea     rdx, WPP_GLOBAL_Control
0x18005d403  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d40a  cmp     rcx, rdx
0x18005d40d  jz      loc_18005D734
0x18005d413  test    byte ptr [rcx+1Ch], 2
0x18005d417  jz      loc_18005D734
0x18005d41d  lea     edx, [rbx+0Ah]
0x18005d420  jmp     short loc_18005D3B1
0x18005d422  mov     edi, ebx
0x18005d424  jmp     loc_18005D734
0x18005d429  test    eax, eax
0x18005d42b  jnz     short loc_18005D437
0x18005d42d  mov     edi, 1
0x18005d432  jmp     loc_18005D734
0x18005d437  lea     r9, [rsp+0D30h+ppidlLast]; ppidlLast
0x18005d43c  lea     r8, [rsp+0D30h+ppv]; ppv
0x18005d441  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x18005d448  mov     rcx, r14; pidl
0x18005d44b  call    cs:__imp_SHBindToParent
0x18005d451  test    eax, eax
0x18005d453  jns     short loc_18005D480
0x18005d455  lea     rdx, WPP_GLOBAL_Control
0x18005d45c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d463  cmp     rcx, rdx
0x18005d466  jz      loc_18005D734
0x18005d46c  test    byte ptr [rcx+1Ch], 2
0x18005d470  jz      loc_18005D734
0x18005d476  mov     edx, 0Ch
0x18005d47b  jmp     loc_18005D3B1
0x18005d480  mov     [rsp+0D30h+var_CD0], 20000000h
0x18005d488  mov     rcx, [rsp+0D30h+ppv]
0x18005d48d  mov     rax, [rcx]
0x18005d490  lea     r9, [rsp+0D30h+var_CD0]
0x18005d495  lea     r8, [rsp+0D30h+ppidlLast]
0x18005d49a  mov     ebx, 1
0x18005d49f  mov     edx, ebx
0x18005d4a1  mov     rax, [rax+48h]
0x18005d4a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d4aa  lea     r8, [rbp+0C30h+String]; unsigned __int16 *
0x18005d4ae  mov     edx, 104h; unsigned __int64
0x18005d4b3  lea     rcx, [rbp+0C30h+psz1]; unsigned __int16 *
0x18005d4ba  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005d4bf  test    eax, eax
0x18005d4c1  jns     short loc_18005D4EC
0x18005d4c3  lea     rdx, WPP_GLOBAL_Control
0x18005d4ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d4d1  cmp     rcx, rdx
0x18005d4d4  jz      loc_18005D734
0x18005d4da  test    byte ptr [rcx+1Ch], 2
0x18005d4de  jz      loc_18005D734
0x18005d4e4  lea     edx, [rbx+0Ch]
0x18005d4e7  jmp     loc_18005D3B1
0x18005d4ec  test    [rsp+0D30h+var_CD0], 20000000h
0x18005d4f4  jnz     loc_18005D68D
0x18005d4fa  mov     dword ptr [rsp+0D30h+psfs.fShowAllObjects], 0
0x18005d502  mov     edx, 2; dwMask
0x18005d507  lea     rcx, [rsp+0D30h+psfs]; psfs
0x18005d50c  call    cs:__imp_SHGetSettings
0x18005d512  test    byte ptr [rsp+0D30h+psfs.fShowAllObjects], 2
0x18005d517  jnz     loc_18005D68D
0x18005d51d  mov     [rsp+0D30h+var_CD8], 0
0x18005d526  mov     rcx, [rsp+0D30h+ppv]
0x18005d52b  mov     rax, [rcx]
0x18005d52e  lea     r8, [rsp+0D30h+var_CD8]
0x18005d533  lea     rdx, _GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1
0x18005d53a  mov     rax, [rax]
0x18005d53d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d542  test    eax, eax
0x18005d544  jns     short loc_18005D587
0x18005d546  lea     rdx, WPP_GLOBAL_Control
0x18005d54d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d554  cmp     rcx, rdx
0x18005d557  jz      short loc_18005D578
0x18005d559  test    byte ptr [rcx+1Ch], 2
0x18005d55d  jz      short loc_18005D578
0x18005d55f  mov     edx, 0Eh
0x18005d564  mov     r9d, eax
0x18005d567  lea     r8, WPP_d6eb988fd8b53d28659d82e20842895c_Traceguids
0x18005d56e  mov     rcx, [rcx+10h]
0x18005d572  call    WPP_SF_d
0x18005d577  nop
0x18005d578  lea     rcx, [rsp+0D30h+var_CD8]
0x18005d57d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005d582  jmp     loc_18005D734
0x18005d587  mov     dword ptr [rsp+0D30h+DirCount], 104h
0x18005d58f  lea     r9, [rbp+0C30h+FullPath]
0x18005d596  lea     r8, PKEY_WPDNSE_Name
0x18005d59d  mov     rdx, [rsp+0D30h+ppidlLast]
0x18005d5a2  mov     rcx, [rsp+0D30h+var_CD8]
0x18005d5a7  call    GetStringProperty
0x18005d5ac  test    eax, eax
0x18005d5ae  jns     short loc_18005D5D0
0x18005d5b0  lea     rdx, WPP_GLOBAL_Control
0x18005d5b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d5be  cmp     rcx, rdx
0x18005d5c1  jz      short loc_18005D578
0x18005d5c3  test    byte ptr [rcx+1Ch], 2
0x18005d5c7  jz      short loc_18005D578
0x18005d5c9  mov     edx, 0Fh
0x18005d5ce  jmp     short loc_18005D564
0x18005d5d0  mov     ecx, 104h
0x18005d5d5  mov     [rsp+0D30h+ExtCount], rcx; ExtCount
0x18005d5da  lea     rax, [rbp+0C30h+var_890]
0x18005d5e1  mov     [rsp+0D30h+Ext], rax; Ext
0x18005d5e6  mov     [rsp+0D30h+FilenameCount], rcx; FilenameCount
0x18005d5eb  lea     rax, [rbp+0C30h+var_260]
0x18005d5f2  mov     [rsp+0D30h+Filename], rax; Filename
0x18005d5f7  mov     [rsp+0D30h+DirCount], 0; DirCount
0x18005d600  xor     r9d, r9d; Dir
0x18005d603  xor     r8d, r8d; DriveCount
0x18005d606  xor     edx, edx; Drive
0x18005d608  lea     rcx, [rbp+0C30h+FullPath]; FullPath
0x18005d60f  call    cs:__imp__wsplitpath_s
0x18005d615  lea     r8, [rbp+0C30h+var_890]; unsigned __int16 *
0x18005d61c  mov     edx, 104h; unsigned __int64
0x18005d621  lea     rcx, [rbp+0C30h+psz1]; unsigned __int16 *
0x18005d628  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005d62d  test    eax, eax
0x18005d62f  jns     short loc_18005D683
0x18005d631  lea     rdx, WPP_GLOBAL_Control
0x18005d638  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d63f  cmp     rcx, rdx
0x18005d642  jz      loc_18005D578
0x18005d648  test    byte ptr [rcx+1Ch], 2
0x18005d64c  jz      loc_18005D578
0x18005d652  mov     edx, 10h
0x18005d657  mov     dword ptr [rsp+0D30h+Filename], eax
0x18005d65b  lea     rax, [rbp+0C30h+var_890]
0x18005d662  mov     [rsp+0D30h+DirCount], rax
0x18005d667  lea     r9, [rbp+0C30h+psz1]
0x18005d66e  lea     r8, WPP_d6eb988fd8b53d28659d82e20842895c_Traceguids
0x18005d675  mov     rcx, [rcx+10h]
0x18005d679  call    WPP_SF_SSd
0x18005d67e  jmp     loc_18005D578
0x18005d683  lea     rcx, [rsp+0D30h+var_CD8]
0x18005d688  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005d68d  test    r12, r12
0x18005d690  jz      short loc_18005D6B0
0x18005d692  mov     r9d, 104h; unsigned int
0x18005d698  lea     r8, [rbp+0C30h+var_470]; unsigned __int16 *
0x18005d69f  lea     rdx, [rbp+0C30h+psz1]; psz1
0x18005d6a6  mov     rcx, r12; this
0x18005d6a9  call    ?_GetObjectIDFromDisplayName@CContentFolder@@QEAAJPEAG0I@Z; CContentFolder::_GetObjectIDFromDisplayName(ushort *,ushort *,uint)
0x18005d6ae  jmp     short loc_18005D6EA
0x18005d6b0  mov     rcx, [rsp+0D30h+ppv]
0x18005d6b5  mov     rax, [rcx]
0x18005d6b8  mov     [rsp+0D30h+FilenameCount], 0
0x18005d6c1  lea     rdx, [rsp+0D30h+pidl]
0x18005d6c6  mov     [rsp+0D30h+Filename], rdx
0x18005d6cb  mov     [rsp+0D30h+DirCount], 0
0x18005d6d4  lea     r9, [rbp+0C30h+psz1]
0x18005d6db  xor     r8d, r8d
0x18005d6de  mov     rdx, rsi
0x18005d6e1  mov     rax, [rax+18h]
0x18005d6e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d6ea  test    eax, eax
0x18005d6ec  js      short loc_18005D72C
0x18005d6ee  mov     rdx, rsi; HWND
0x18005d6f1  mov     rcx, r14; struct _ITEMIDLIST *
0x18005d6f4  call    ?_DisplayApplyError@@YAXPEFAU_ITEMIDLIST@@PEAUHWND__@@I@Z; _DisplayApplyError(_ITEMIDLIST *,HWND__ *,uint)
0x18005d6f9  mov     r8, r15; lpString
0x18005d6fc  mov     edx, r13d; nIDDlgItem
0x18005d6ff  mov     rcx, rsi; hDlg
0x18005d702  call    cs:__imp_SetDlgItemTextW
0x18005d708  mov     edx, 138h; nIDDlgItem
0x18005d70d  mov     rcx, rsi; hDlg
0x18005d710  call    cs:__imp_GetDlgItem
0x18005d716  mov     rcx, rax; hWnd
0x18005d719  xor     r9d, r9d; lParam
0x18005d71c  xor     r8d, r8d; wParam
0x18005d71f  mov     edx, 0B1h; Msg
0x18005d724  call    cs:__imp_SendMessageW
0x18005d72a  jmp     short loc_18005D734
0x18005d72c  cmp     eax, 80070002h
0x18005d731  cmovz   edi, ebx
0x18005d734  mov     rcx, [rsp+0D30h+pidl]; pidl
0x18005d739  test    rcx, rcx
0x18005d73c  jz      short loc_18005D74D
0x18005d73e  call    cs:__imp_ILFree
0x18005d744  mov     [rsp+0D30h+pidl], 0
0x18005d74d  lea     rcx, [rsp+0D30h+ppv]
0x18005d752  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005d757  mov     eax, edi
0x18005d759  mov     rcx, [rbp+0C30h+var_50]
0x18005d760  xor     rcx, rsp; StackCookie
0x18005d763  call    __security_check_cookie
0x18005d768  add     rsp, 0CF8h
0x18005d76f  pop     r15
0x18005d771  pop     r14
0x18005d773  pop     r13
0x18005d775  pop     r12
0x18005d777  pop     rdi
0x18005d778  pop     rsi
0x18005d779  pop     rbx
0x18005d77a  pop     rbp
0x18005d77b  retn
```
