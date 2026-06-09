# CFSFolder::GetAttributesOf(uint,_ITEMID_CHILD const * const *,ulong *)

- ea: `0x18032c640`
- end: `0x18032ce72`
- name: `?GetAttributesOf@CFSFolder@@UEAAJIPEBQEFBU_ITEMID_CHILD@@PEAK@Z`
- size: `2098`
- prototype: `__int64 __fastcall(CFSFolder *__hidden this, unsigned int, const struct _ITEMID_CHILD *const *, unsigned int *)`
- caller_count: `0`
- callee_count: `26`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180035d30`
- `0x180038f50`
- `0x180038f80`
- `0x1800441c0`
- `0x180045390`
- `0x180045520`
- `0x180047f00`
- `0x180048ad0`
- `0x180049b60`
- `0x18004a9e0`
- `0x180056670`
- `0x1800572c0`
- `0x180058560`
- `0x18005a2d0`
- `0x18008cd40`
- `0x18008d3e0`
- `0x1800ab340`
- `0x1800aba40`
- `0x1800b85f0`
- `0x180180ba0`
- `0x18023498c`
- `0x18032c640`
- `0x1803b1f60`
- `0x1803b69b9`
- `0x1805d9b94`
- `0x18067d010`

## import_xrefs

- `ntdll!RtlIsPartialPlaceholder` at `0x18032c861`
- `ntdll!RtlIsPartialPlaceholder` at `0x18032c861`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18032c936`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18032c936`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032c734`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032c783`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032c9e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032cd62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032ce0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032c734`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032c783`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032c9e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032cd62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18032ce0c`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x18032cb19`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x18032cb7d`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x18032cbd6`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x18032cb19`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x18032cb7d`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x18032cbd6`
- `SHCORE!__imp_SHGetObjectCompatFlags` at `0x18032cbff`
- `SHCORE!__imp_SHGetObjectCompatFlags` at `0x18032cbff`
- `api-ms-win-shlwapi-ie-l1-1-0!PathFileExistsAndAttributesW` at `0x18032c769`
- `api-ms-win-shlwapi-ie-l1-1-0!PathFileExistsAndAttributesW` at `0x18032c769`
- `ext-ms-win-shell-ntshrui-l1-1-0!IsPathSharedW` at `0x18032caa3`
- `ext-ms-win-shell-ntshrui-l1-1-0!IsPathSharedW` at `0x18032caa3`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CFSFolder::GetAttributesOf(
        CFSFolder *this,
        int a2,
        const struct _ITEMID_CHILD **a3,
        unsigned int *a4)
{
  const struct IDFOLDER *v7; // rax
  const struct IDFOLDER *v8; // r12
  int v9; // edi
  __int16 FullFileAttributes; // r15
  CFSFolder *v11; // r13
  int v12; // eax
  unsigned int v13; // ebx
  int v15; // eax
  int v17; // eax
  unsigned int ReparsePointTag; // ebx
  unsigned int v19; // eax
  int v20; // eax
  bool v21; // bl
  __int16 v22; // r12
  CMountPoint *v23; // r14
  CFSFolder *v24; // rcx
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // edi
  CCLSIDInfoCache *v28; // rcx
  unsigned int v29; // ebx
  CCLSIDInfoCache *v30; // rcx
  unsigned int RestrictedAttributes; // eax
  int v32; // eax
  int (__fastcall **v33)(LPCWSTR, GUID *, struct _GUID *); // rax
  int (__fastcall **v34)(LPCWSTR, GUID *, struct _GUID *); // rax
  char v35; // bl
  int v36; // [rsp+20h] [rbp-E0h]
  LPCWSTR pszPath; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v38; // [rsp+38h] [rbp-C8h] BYREF
  const struct IDFOLDER *v39; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  struct _GUID Buf1; // [rsp+50h] [rbp-B0h] BYREF
  struct $D321FDA48A4D82B6F6ABB6499405B63E v42; // [rsp+60h] [rbp-A0h] BYREF
  struct $D321FDA48A4D82B6F6ABB6499405B63E v43; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v44[80]; // [rsp+A0h] [rbp-60h] BYREF
  struct IDFOLDER *v45; // [rsp+F0h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+398h] [rbp+298h]

  v38 = a3;
  if ( !a2 )
  {
    v9 = 1073742149;
    goto LABEL_142;
  }
  v7 = CFSFolder::_IsValidID(this, *a3);
  v8 = v7;
  v39 = v7;
  v9 = 1073742149;
  if ( a2 != 1 || !v7 )
  {
LABEL_142:
    if ( (*(_BYTE *)a4 & 0x32) != 0
      && (CFSFolder::_GetVolumeInformationFlags((CFSFolder *)((char *)this - 48)) & 0x80000) == 0 )
    {
      v9 = 1073742199;
    }
    goto LABEL_145;
  }
  FullFileAttributes = GetFullFileAttributes(v7);
  v11 = (CFSFolder *)((char *)this - 48);
  CFileSysItemString::CFileSysItemString(
    (CFileSysItemString *)v44,
    (CFSFolder *)((char *)this - 48),
    *(const struct _ITEMIDLIST_RELATIVE **)v38,
    v8);
  pv = 0;
  if ( (*a4 & 0x3020010) != 0 )
  {
    pv = 0;
    v12 = (*(__int64 (__fastcall **)(char *, _QWORD, __int64, LPVOID *))(*((_QWORD *)this + 33) + 112LL))(
            (char *)this + 264,
            *(_QWORD *)v38,
            1,
            &pv);
    v13 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE03,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
        (const char *)(unsigned int)v12,
        v36);
      if ( pv )
        CoTaskMemFree(pv);
      CFileSysItemString::~CFileSysItemString((CFileSysItemString *)v44);
      return v13;
    }
  }
  if ( (*a4 & 0x1000000) == 0 || (LODWORD(pszPath) = 0, (unsigned int)PathFileExistsAndAttributesW(pv, &pszPath)) )
  {
    v15 = *a4;
    if ( (*a4 & 0x4000000) != 0 && (FullFileAttributes & 0x800) != 0 )
      v9 = 1140851013;
    if ( (v15 & 0x2000) != 0 && (FullFileAttributes & 0x4000) != 0 )
      v9 |= 0x2000u;
    if ( (*((_BYTE *)this + 488) & 0x40) != 0 )
      goto LABEL_29;
    if ( (v15 & 0x40000) != 0
      && !((FullFileAttributes & 0x10) != 0
         ? (CFSFolder::_GetVolumeInformationFlags((CFSFolder *)((char *)this - 48)) & 0x80000) == 0
         : (FullFileAttributes & 1) == 0) )
    {
      v9 |= 0x40000u;
    }
    if ( (*(_BYTE *)a4 & 0x22) != 0
      && (CFSFolder::_GetVolumeInformationFlags((CFSFolder *)((char *)this - 48)) & 0x80000) == 0 )
    {
LABEL_29:
      v9 |= 0x22u;
    }
    v17 = *a4;
    if ( (*a4 & 0x80000) != 0 && (FullFileAttributes & 2) != 0 )
      v9 |= 0x80000u;
    if ( (v17 & 0x1000) != 0
      && (FullFileAttributes & 4) != 0
      && ((FullFileAttributes & 0x10) == 0 || (FullFileAttributes & 2) != 0) )
    {
      v9 |= 0x1000u;
    }
    if ( (v17 & 0x800) != 0 )
    {
      if ( v45 )
      {
        ReparsePointTag = CFileSysItemString::GetReparsePointTag((CFileSysItemString *)v44);
        v19 = GetFullFileAttributes(v45);
        if ( (unsigned __int8)RtlIsPartialPlaceholder(v19, ReparsePointTag) )
          v9 |= 0x800u;
      }
    }
    if ( (*a4 & 0x100000) != 0 )
    {
      if ( !(unsigned int)ShowSuperHidden() && (FullFileAttributes & 6) == 6
        || (FullFileAttributes & 2) != 0
        && (memset(&v42, 0, sizeof(v42)), SHGetSetSettings(&v42, 1u, 0), (*(_BYTE *)&v42 & 1) == 0) )
      {
        v9 |= 0x100000u;
      }
    }
    if ( (*a4 & 0x4000) != 0 )
    {
      if ( (*(unsigned int (__fastcall **)(char *, const struct IDFOLDER *))(*((_QWORD *)this + 33) + 104LL))(
             (char *)this + 264,
             v8) )
      {
        goto LABEL_70;
      }
      v20 = *((_DWORD *)v11 + 141);
      if ( !v20 )
      {
        v21 = 0;
        if ( *((_DWORD *)v11 + 148) != 2 )
        {
          pszPath = 0;
          if ( CFSFolder::GetFolderPath(v11, (unsigned __int16 **)&pszPath) >= 0 )
          {
            v22 = CFSFolder::_Attributes(v11);
            if ( PathIsUNCW(pszPath) )
            {
              v21 = (v22 & 0x1000) != 0 || GetUNCPathSpeed(pszPath) - 1 <= 0x18F;
            }
            else
            {
              *(_QWORD *)&Buf1.Data1 = 0;
              if ( (int)CMountPoint::GetMountPoint(pszPath, 1, &Buf1) >= 0 )
              {
                v23 = *(CMountPoint **)&Buf1.Data1;
                if ( *((_DWORD *)v11 + 148) == 1
                  || (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)&Buf1.Data1 + 360LL))(*(_QWORD *)&Buf1.Data1) )
                {
                  v21 = (v22 & 0x1000) != 0
                     || (*(unsigned int (__fastcall **)(CMountPoint *))(*(_QWORD *)v23 + 512LL))(v23);
                }
                CMountPoint::Release(v23);
              }
            }
            v8 = v39;
          }
          if ( pszPath )
            CoTaskMemFree((LPVOID)pszPath);
        }
        v20 = 2 - v21;
        *((_DWORD *)v11 + 141) = v20;
      }
      if ( v20 == 1 )
LABEL_70:
        v9 |= 0x4000u;
    }
    if ( (((*((_BYTE *)v8 + 2) & 0x37) - 49) & 0xFB) != 0 )
    {
      if ( (*a4 & 0x400000) != 0
        && ((FullFileAttributes & 0x400) == 0
         || CFileSysItemString::GetReparsePointTag((CFileSysItemString *)v44) != -1610612724) )
      {
        v9 |= 0x400000u;
      }
      if ( (*(_BYTE *)a4 & 0x10) != 0 && (CFSFolder::_GetVolumeInformationFlags(v11) & 0x80000) == 0 )
        v9 |= 0x10u;
    }
    else
    {
      v9 |= 0x30800008u;
      if ( (*(_BYTE *)a4 & 0x10) != 0
        && (CFSFolder::_GetVolumeInformationFlags(v11) & 0x80000) == 0
        && (unsigned int)CFSFolder::_CanRenameFolder(v24, (const unsigned __int16 *)pv) )
      {
        v9 |= 0x10u;
      }
      if ( (*a4 & 0x2000000) != 0 && CFSFolder::IsOnRemovableVolume(v11) )
        v9 |= 0x2000000u;
      if ( (*a4 & 0x20000) != 0 && (unsigned int)IsPathSharedW(pv, 0) )
        v9 |= 0x20000u;
    }
    if ( (*a4 & 0x10000) != 0 )
    {
      if ( (CFileSysItemString::ClassFlags((CFileSysItemString *)v44) & 0x1000000) != 0
        || (FullFileAttributes & 0x400) != 0
        && ((v25 = CFileSysItemString::GetReparsePointTag((CFileSysItemString *)v44), v25 == -2147483638)
         || v25 == -1610612733
         || v25 == -1610612724) )
      {
        v9 |= 0x10000u;
      }
    }
    v26 = v9 & *a4;
    if ( (v26 & 0xB080013F) != 0 || (*a4 & 0xB0C50108) != 0 )
    {
      Buf1 = 0;
      if ( (unsigned int)CFileSysItemString::GetJunctionClsid(v44, 3, &Buf1) )
      {
        v27 = v9 & 0xEF7FFEF7;
        if ( !memcmp_0(&Buf1, &CLSID_FolderShortcut, 0x10u) && (unsigned int)IsAppCompatModeEnabled(9) )
          v27 &= ~0x20000000u;
        v29 = v27 | CCLSIDInfoCache::GetAttribute(v28, &Buf1, 0x80000000, 0xB0C50108) & 0xB0C50108;
        RestrictedAttributes = CCLSIDInfoCache::GetRestrictedAttributes(v30, &Buf1);
        if ( RestrictedAttributes )
        {
          v32 = ~RestrictedAttributes;
          v9 = v29 & v32;
          *a4 &= v32;
        }
        else
        {
          v9 = v29;
        }
        if ( (FullFileAttributes & 0x10) == 0 && (unsigned int)IsAppCompatModeEnabled(9) )
          v9 &= ~0x20000000u;
        if ( (v9 & 0x30000000) == 0x20000000 && (SHGetObjectCompatFlags(0, &Buf1) & 0x10) != 0 )
          v9 |= 0x10000000u;
      }
    }
    else if ( !v26 && !(unsigned int)IsAppCompatModeEnabled(21) )
    {
      v9 = 0;
LABEL_131:
      if ( (*a4 & 0x8000) != 0 )
      {
        v35 = GetFullFileAttributes(v8);
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudFileStateIcon>::__private_IsEnabledPreCheck(
          `wil::Feature<__WilFeatureTraits_Feature_CloudFileStateIcon>::GetImpl'::`2'::impl,
          0);
        if ( (v35 & 2) != 0 )
          v9 |= 0x8000u;
      }
      if ( (*a4 & 0x8000000) != 0
        && (((*((_BYTE *)v8 + 2) & 0x37) - 50) & 0xFB) == 0
        && (CFileSysItemString::ClassFlags((CFileSysItemString *)v44) & 0x500000) != 0 )
      {
        v9 |= 0x8000000u;
      }
      if ( pv )
        CoTaskMemFree(pv);
      CFileSysItemString::~CFileSysItemString((CFileSysItemString *)v44);
LABEL_145:
      *a4 = v9;
      return 0;
    }
    if ( (v9 & 0x20000000) != 0 && (*a4 & 0x80000000) != 0 )
    {
      if ( (FullFileAttributes & 0x400) != 0 )
      {
        v9 |= 0x80000000;
      }
      else if ( v9 >= 0 )
      {
        pszPath = 0;
        if ( (int)CFSFolder::_Bind(
                    v11,
                    0,
                    *(const struct _ITEMIDLIST_RELATIVE **)v38,
                    &GUID_000214e6_0000_0000_c000_000000000046,
                    (void **)&pszPath) >= 0 )
        {
          *(_QWORD *)&Buf1.Data1 = 0;
          *(GUID *)&v42 = GUID_NULL;
          v33 = *(int (__fastcall ***)(LPCWSTR, GUID *, struct _GUID *))pszPath;
          *(_QWORD *)&Buf1.Data1 = 0;
          if ( (*v33)(pszPath, &GUID_053b4a86_0dc9_40a3_b7ed_bc6a2e951f48, &Buf1) >= 0 )
            (*(void (__fastcall **)(_QWORD, struct $D321FDA48A4D82B6F6ABB6499405B63E *))(**(_QWORD **)&Buf1.Data1 + 24LL))(
              *(_QWORD *)&Buf1.Data1,
              &v42);
          if ( !memcmp_0(&v42, &FOLDERTYPEID_CompressedFolder, 0x10u) )
          {
            v9 |= 0x80000000;
          }
          else
          {
            memset(&v43, 0, sizeof(v43));
            SHGetSetSettings(&v43, 1u, 0);
            v39 = 0;
            v34 = *(int (__fastcall ***)(LPCWSTR, GUID *, struct _GUID *))pszPath;
            v39 = 0;
            if ( !((unsigned int (__fastcall *)(LPCWSTR, _QWORD, _QWORD, const struct IDFOLDER **))v34[4])(
                    pszPath,
                    0,
                    ((*(_BYTE *)&v43 & 1) << 7) | 0x30u,
                    &v39) )
            {
              v38 = 0;
              if ( !(*(unsigned int (__fastcall **)(const struct IDFOLDER *, __int64, LPVOID *, _QWORD))(*(_QWORD *)v39 + 24LL))(
                      v39,
                      1,
                      &v38,
                      0) )
              {
                v9 |= 0x80000000;
                CoTaskMemFree(v38);
              }
            }
            if ( v39 )
              (*(void (__fastcall **)(const struct IDFOLDER *))(*(_QWORD *)v39 + 16LL))(v39);
          }
          (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)pszPath + 16LL))(pszPath);
          if ( *(_QWORD *)&Buf1.Data1 )
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&Buf1.Data1 + 16LL))(*(_QWORD *)&Buf1.Data1);
        }
      }
    }
    goto LABEL_131;
  }
  if ( pv )
    CoTaskMemFree(pv);
  CFileSysItemString::~CFileSysItemString((CFileSysItemString *)v44);
  return 2147500037LL;
}

```

## disassembly

```asm
0x18032c640  mov     [rsp-8+arg_8], rbx
0x18032c645  push    rbp
0x18032c646  push    rsi
0x18032c647  push    rdi
0x18032c648  push    r12
0x18032c64a  push    r13
0x18032c64c  push    r14
0x18032c64e  push    r15
0x18032c650  lea     rbp, [rsp-260h]
0x18032c658  sub     rsp, 360h
0x18032c65f  mov     rax, cs:__security_cookie
0x18032c666  xor     rax, rsp
0x18032c669  mov     [rbp+290h+var_40], rax
0x18032c670  mov     rsi, r9
0x18032c673  mov     [rsp+390h+var_358], r8
0x18032c678  mov     ebx, edx
0x18032c67a  mov     r14, rcx
0x18032c67d  test    edx, edx
0x18032c67f  jz      loc_18032CE24
0x18032c685  mov     rdx, [r8]; struct _ITEMIDLIST_RELATIVE *
0x18032c688  call    ?_IsValidID@CFSFolder@@IEAAPEFBUIDFOLDER@@PEFBU_ITEMIDLIST_RELATIVE@@@Z; CFSFolder::_IsValidID(_ITEMIDLIST_RELATIVE const *)
0x18032c68d  mov     r12, rax
0x18032c690  mov     [rsp+390h+var_350], rax
0x18032c695  mov     edi, 40000145h
0x18032c69a  cmp     ebx, 1
0x18032c69d  jnz     loc_18032CE29
0x18032c6a3  test    rax, rax
0x18032c6a6  jz      loc_18032CE29
0x18032c6ac  mov     rcx, rax; struct IDFOLDER *
0x18032c6af  call    ?GetFullFileAttributes@@YAKPEFBUIDFOLDER@@@Z; GetFullFileAttributes(IDFOLDER const *)
0x18032c6b4  mov     r15d, eax
0x18032c6b7  lea     r13, [r14-30h]
0x18032c6bb  mov     r9, r12; struct IDFOLDER *
0x18032c6be  mov     rbx, [rsp+390h+var_358]
0x18032c6c3  mov     r8, [rbx]; struct _ITEMIDLIST_RELATIVE *
0x18032c6c6  mov     rdx, r13; struct CFSFolder *
0x18032c6c9  lea     rcx, [rbp+290h+var_2F0]; this
0x18032c6cd  call    ??0CFileSysItemString@@QEAA@PEAVCFSFolder@@PEFBU_ITEMIDLIST_RELATIVE@@PEFBUIDFOLDER@@@Z; CFileSysItemString::CFileSysItemString(CFSFolder *,_ITEMIDLIST_RELATIVE const *,IDFOLDER const *)
0x18032c6d2  nop
0x18032c6d3  xor     eax, eax
0x18032c6d5  mov     [rsp+390h+pv], rax
0x18032c6da  test    dword ptr [rsi], 3020010h
0x18032c6e0  jz      short loc_18032C753
0x18032c6e2  lea     rcx, [r14+108h]
0x18032c6e9  mov     [rsp+390h+pv], rax
0x18032c6ee  mov     rax, [rcx]
0x18032c6f1  lea     r9, [rsp+390h+pv]
0x18032c6f6  mov     r8d, 1
0x18032c6fc  mov     rdx, [rbx]
0x18032c6ff  mov     rax, [rax+70h]
0x18032c703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032c708  mov     ebx, eax
0x18032c70a  test    eax, eax
0x18032c70c  jns     short loc_18032C751
0x18032c70e  mov     rcx, [rbp+298h]; this
0x18032c715  mov     r9d, eax; char *
0x18032c718  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x18032c71f  mov     edx, 0E03h; void *
0x18032c724  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18032c729  nop
0x18032c72a  mov     rcx, [rsp+390h+pv]; pv
0x18032c72f  test    rcx, rcx
0x18032c732  jz      short loc_18032C741
0x18032c734  call    cs:__imp_CoTaskMemFree
0x18032c73b  nop     dword ptr [rax+rax+00h]
0x18032c740  nop
0x18032c741  lea     rcx, [rbp+290h+var_2F0]; this
0x18032c745  call    ??1CFileSysItemString@@UEAA@XZ; CFileSysItemString::~CFileSysItemString(void)
0x18032c74a  mov     eax, ebx
0x18032c74c  jmp     loc_18032CE47
0x18032c751  xor     eax, eax
0x18032c753  test    dword ptr [rsi], 1000000h
0x18032c759  jz      short loc_18032C7A3
0x18032c75b  mov     dword ptr [rsp+390h+pszPath], eax
0x18032c75f  lea     rdx, [rsp+390h+pszPath]
0x18032c764  mov     rcx, [rsp+390h+pv]
0x18032c769  call    cs:__imp_PathFileExistsAndAttributesW
0x18032c770  nop     dword ptr [rax+rax+00h]
0x18032c775  test    eax, eax
0x18032c777  jnz     short loc_18032C7A3
0x18032c779  mov     rcx, [rsp+390h+pv]; pv
0x18032c77e  test    rcx, rcx
0x18032c781  jz      short loc_18032C790
0x18032c783  call    cs:__imp_CoTaskMemFree
0x18032c78a  nop     dword ptr [rax+rax+00h]
0x18032c78f  nop
0x18032c790  lea     rcx, [rbp+290h+var_2F0]; this
0x18032c794  call    ??1CFileSysItemString@@UEAA@XZ; CFileSysItemString::~CFileSysItemString(void)
0x18032c799  mov     eax, 80004005h
0x18032c79e  jmp     loc_18032CE47
0x18032c7a3  mov     eax, [rsi]
0x18032c7a5  bt      eax, 1Ah
0x18032c7a9  jnb     short loc_18032C7B8
0x18032c7ab  bt      r15d, 0Bh
0x18032c7b0  mov     ecx, 44000145h
0x18032c7b5  cmovb   edi, ecx
0x18032c7b8  bt      eax, 0Dh
0x18032c7bc  jnb     short loc_18032C7C9
0x18032c7be  bt      r15d, 0Eh
0x18032c7c3  jnb     short loc_18032C7C9
0x18032c7c5  bts     edi, 0Dh
0x18032c7c9  test    byte ptr [r14+1E8h], 40h
0x18032c7d1  jnz     short loc_18032C80B
0x18032c7d3  bt      eax, 12h
0x18032c7d7  jnb     short loc_18032C7F8
0x18032c7d9  test    r15b, 10h
0x18032c7dd  jz      short loc_18032C7EE
0x18032c7df  mov     rcx, r13; this
0x18032c7e2  call    ?_GetVolumeInformationFlags@CFSFolder@@IEAAKXZ; CFSFolder::_GetVolumeInformationFlags(void)
0x18032c7e7  test    eax, 80000h
0x18032c7ec  jmp     short loc_18032C7F2
0x18032c7ee  test    r15b, 1
0x18032c7f2  jz      short loc_18032C7F8
0x18032c7f4  bts     edi, 12h
0x18032c7f8  test    byte ptr [rsi], 22h
0x18032c7fb  jz      short loc_18032C80E
0x18032c7fd  mov     rcx, r13; this
0x18032c800  call    ?_GetVolumeInformationFlags@CFSFolder@@IEAAKXZ; CFSFolder::_GetVolumeInformationFlags(void)
0x18032c805  bt      eax, 13h
0x18032c809  jb      short loc_18032C80E
0x18032c80b  or      edi, 22h
0x18032c80e  mov     eax, [rsi]
0x18032c810  bt      eax, 13h
0x18032c814  jnb     short loc_18032C820
0x18032c816  test    r15b, 2
0x18032c81a  jz      short loc_18032C820
0x18032c81c  bts     edi, 13h
0x18032c820  bt      eax, 0Ch
0x18032c824  jnb     short loc_18032C83C
0x18032c826  test    r15b, 4
0x18032c82a  jz      short loc_18032C83C
0x18032c82c  test    r15b, 10h
0x18032c830  jz      short loc_18032C838
0x18032c832  test    r15b, 2
0x18032c836  jz      short loc_18032C83C
0x18032c838  bts     edi, 0Ch
0x18032c83c  bt      eax, 0Bh
0x18032c840  jnb     short loc_18032C875
0x18032c842  cmp     [rbp+290h+var_2A0], 0
0x18032c847  jz      short loc_18032C875
0x18032c849  lea     rcx, [rbp+290h+var_2F0]; this
0x18032c84d  call    ?GetReparsePointTag@CFileSysItemString@@QEBAKXZ; CFileSysItemString::GetReparsePointTag(void)
0x18032c852  mov     ebx, eax
0x18032c854  mov     rcx, [rbp+290h+var_2A0]; struct IDFOLDER *
0x18032c858  call    ?GetFullFileAttributes@@YAKPEFBUIDFOLDER@@@Z; GetFullFileAttributes(IDFOLDER const *)
0x18032c85d  mov     edx, ebx
0x18032c85f  mov     ecx, eax
0x18032c861  call    cs:__imp_RtlIsPartialPlaceholder
0x18032c868  nop     dword ptr [rax+rax+00h]
0x18032c86d  test    al, al
0x18032c86f  jz      short loc_18032C875
0x18032c871  bts     edi, 0Bh
0x18032c875  test    dword ptr [rsi], 100000h
0x18032c87b  jz      short loc_18032C8C0
0x18032c87d  call    ShowSuperHidden
0x18032c882  test    eax, eax
0x18032c884  jnz     short loc_18032C890
0x18032c886  mov     eax, r15d
0x18032c889  and     eax, 6
0x18032c88c  cmp     al, 6
0x18032c88e  jz      short loc_18032C8BC
0x18032c890  test    r15b, 2
0x18032c894  jz      short loc_18032C8C0
0x18032c896  xorps   xmm0, xmm0
0x18032c899  movups  xmmword ptr [rsp+390h+var_330.fShowAllObjects], xmm0
0x18032c89e  movups  xmmword ptr [rsp+390h+var_330.iSortDirection], xmm0
0x18032c8a3  xor     r8d, r8d; bSet
0x18032c8a6  mov     edx, 1; dwMask
0x18032c8ab  lea     rcx, [rsp+390h+var_330]; lpss
0x18032c8b0  call    SHGetSetSettings
0x18032c8b5  test    byte ptr [rsp+390h+var_330.fShowAllObjects], 1
0x18032c8ba  jnz     short loc_18032C8C0
0x18032c8bc  bts     edi, 14h
0x18032c8c0  test    dword ptr [rsi], 4000h
0x18032c8c6  jz      loc_18032CA09
0x18032c8cc  lea     rcx, [r14+108h]
0x18032c8d3  mov     rax, [rcx]
0x18032c8d6  mov     rdx, r12
0x18032c8d9  mov     rax, [rax+68h]
0x18032c8dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032c8e2  test    eax, eax
0x18032c8e4  jnz     loc_18032CA05
0x18032c8ea  mov     eax, [r13+234h]
0x18032c8f1  test    eax, eax
0x18032c8f3  jnz     loc_18032CA00
0x18032c8f9  xor     bl, bl
0x18032c8fb  cmp     dword ptr [r13+250h], 2
0x18032c903  jz      loc_18032C9F2
0x18032c909  xor     r14d, r14d
0x18032c90c  mov     [rsp+390h+pszPath], r14
0x18032c911  lea     rdx, [rsp+390h+pszPath]; unsigned __int16 **
0x18032c916  mov     rcx, r13; this
0x18032c919  call    ?GetFolderPath@CFSFolder@@QEAAJPEAPEAG@Z; CFSFolder::GetFolderPath(ushort * *)
0x18032c91e  test    eax, eax
0x18032c920  js      loc_18032C9DC
0x18032c926  mov     rcx, r13; this
0x18032c929  call    ?_Attributes@CFSFolder@@IEAAKXZ; CFSFolder::_Attributes(void)
0x18032c92e  mov     r12d, eax
0x18032c931  mov     rcx, [rsp+390h+pszPath]; pszPath
0x18032c936  call    cs:__imp_PathIsUNCW
0x18032c93d  nop     dword ptr [rax+rax+00h]
0x18032c942  test    eax, eax
0x18032c944  jz      short loc_18032C96A
0x18032c946  bt      r12d, 0Ch
0x18032c94b  jnb     short loc_18032C954
0x18032c94d  mov     bl, 1
0x18032c94f  jmp     loc_18032C9D7
0x18032c954  mov     rcx, [rsp+390h+pszPath]; unsigned __int16 *
0x18032c959  call    ?GetUNCPathSpeed@@YAKPEBG@Z; GetUNCPathSpeed(ushort const *)
0x18032c95e  dec     eax
0x18032c960  cmp     eax, 18Fh
0x18032c965  setbe   bl
0x18032c968  jmp     short loc_18032C9D7
0x18032c96a  mov     qword ptr [rsp+390h+Buf1], r14
0x18032c96f  lea     r8, [rsp+390h+Buf1]
0x18032c974  mov     edx, 1
0x18032c979  mov     rcx, [rsp+390h+pszPath]
0x18032c97e  call    ?GetMountPoint@CMountPoint@@SAJPEBGW4AddToDriveLetterCache@@PEAPEAV1@@Z; CMountPoint::GetMountPoint(ushort const *,AddToDriveLetterCache,CMountPoint * *)
0x18032c983  test    eax, eax
0x18032c985  js      short loc_18032C9D7
0x18032c987  mov     r14, qword ptr [rsp+390h+Buf1]
0x18032c98c  cmp     dword ptr [r13+250h], 1
0x18032c994  jz      short loc_18032C9AC
0x18032c996  mov     rax, [r14]
0x18032c999  mov     rcx, r14
0x18032c99c  mov     rax, [rax+168h]
0x18032c9a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032c9a8  test    eax, eax
0x18032c9aa  jz      short loc_18032C9CF
0x18032c9ac  bt      r12d, 0Ch
0x18032c9b1  jb      short loc_18032C9CD
0x18032c9b3  mov     rax, [r14]
0x18032c9b6  mov     rcx, r14
0x18032c9b9  mov     rax, [rax+200h]
0x18032c9c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032c9c5  test    eax, eax
0x18032c9c7  jnz     short loc_18032C9CD
0x18032c9c9  xor     bl, bl
0x18032c9cb  jmp     short loc_18032C9CF
0x18032c9cd  mov     bl, 1
0x18032c9cf  mov     rcx, r14; this
0x18032c9d2  call    ?Release@CMountPoint@@QEAAKXZ; CMountPoint::Release(void)
0x18032c9d7  mov     r12, [rsp+390h+var_350]
0x18032c9dc  mov     rcx, [rsp+390h+pszPath]; pv
0x18032c9e1  test    rcx, rcx
0x18032c9e4  jz      short loc_18032C9F2
0x18032c9e6  call    cs:__imp_CoTaskMemFree
0x18032c9ed  nop     dword ptr [rax+rax+00h]
0x18032c9f2  neg     bl
0x18032c9f4  sbb     eax, eax
0x18032c9f6  add     eax, 2
0x18032c9f9  mov     [r13+234h], eax
0x18032ca00  cmp     eax, 1
0x18032ca03  jnz     short loc_18032CA09
0x18032ca05  bts     edi, 0Eh
0x18032ca09  movzx   eax, byte ptr [r12+2]
0x18032ca0f  and     al, 37h
0x18032ca11  sub     al, 31h ; '1'
0x18032ca13  test    al, 0FBh
0x18032ca15  jz      short loc_18032CA52
0x18032ca17  test    dword ptr [rsi], 400000h
0x18032ca1d  jz      short loc_18032CA3A
0x18032ca1f  bt      r15d, 0Ah
0x18032ca24  jnb     short loc_18032CA36
0x18032ca26  lea     rcx, [rbp+290h+var_2F0]; this
0x18032ca2a  call    ?GetReparsePointTag@CFileSysItemString@@QEBAKXZ; CFileSysItemString::GetReparsePointTag(void)
0x18032ca2f  cmp     eax, 0A000000Ch
0x18032ca34  jz      short loc_18032CA3A
0x18032ca36  bts     edi, 16h
0x18032ca3a  test    byte ptr [rsi], 10h
0x18032ca3d  jz      short loc_18032CAB7
0x18032ca3f  mov     rcx, r13; this
0x18032ca42  call    ?_GetVolumeInformationFlags@CFSFolder@@IEAAKXZ; CFSFolder::_GetVolumeInformationFlags(void)
0x18032ca47  bt      eax, 13h
0x18032ca4b  jb      short loc_18032CAB7
0x18032ca4d  or      edi, 10h
0x18032ca50  jmp     short loc_18032CAB7
0x18032ca52  or      edi, 30800008h
0x18032ca58  test    byte ptr [rsi], 10h
0x18032ca5b  jz      short loc_18032CA7C
0x18032ca5d  mov     rcx, r13; this
0x18032ca60  call    ?_GetVolumeInformationFlags@CFSFolder@@IEAAKXZ; CFSFolder::_GetVolumeInformationFlags(void)
0x18032ca65  bt      eax, 13h
0x18032ca69  jb      short loc_18032CA7C
0x18032ca6b  mov     rdx, [rsp+390h+pv]; unsigned __int16 *
0x18032ca70  call    ?_CanRenameFolder@CFSFolder@@IEAAHPEBG@Z; CFSFolder::_CanRenameFolder(ushort const *)
0x18032ca75  test    eax, eax
0x18032ca77  jz      short loc_18032CA7C
0x18032ca79  or      edi, 10h
0x18032ca7c  test    dword ptr [rsi], 2000000h
0x18032ca82  jz      short loc_18032CA94
0x18032ca84  mov     rcx, r13; this
0x18032ca87  call    ?IsOnRemovableVolume@CFSFolder@@IEAA_NXZ; CFSFolder::IsOnRemovableVolume(void)
0x18032ca8c  test    al, al
0x18032ca8e  jz      short loc_18032CA94
0x18032ca90  bts     edi, 19h
0x18032ca94  test    dword ptr [rsi], 20000h
0x18032ca9a  jz      short loc_18032CAB7
0x18032ca9c  xor     edx, edx
0x18032ca9e  mov     rcx, [rsp+390h+pv]
  ... truncated ...
```
