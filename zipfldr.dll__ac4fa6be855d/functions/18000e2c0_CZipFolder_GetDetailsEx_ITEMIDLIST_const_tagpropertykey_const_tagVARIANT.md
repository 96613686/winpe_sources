# CZipFolder::GetDetailsEx(_ITEMIDLIST const *,_tagpropertykey const *,tagVARIANT *)

- ea: `0x18000e2c0`
- end: `0x18000e95b`
- name: `?GetDetailsEx@CZipFolder@@UEAAJPEFBU_ITEMIDLIST@@PEBU_tagpropertykey@@PEAUtagVARIANT@@@Z`
- size: `1691`
- prototype: `__int64 __fastcall(CZipFolder *__hidden this, const struct _ITEMIDLIST *, const struct _tagpropertykey *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x18000c8ec`
- `0x18000d630`
- `0x18000de14`
- `0x18000e2c0`
- `0x18000ed28`
- `0x180012238`
- `0x180014bf0`
- `0x180021218`
- `0x180022abc`
- `0x18002acd8`
- `0x180036f50`
- `0x180037958`
- `0x18003b3dc`

## import_xrefs

- `PROPSYS!InitVariantFromFileTime` at `0x18000e775`
- `PROPSYS!InitVariantFromFileTime` at `0x18000e775`
- `PROPSYS!InitVariantFromBuffer` at `0x18000e938`
- `PROPSYS!InitVariantFromBuffer` at `0x18000e938`
- `SHLWAPI!PathFindExtensionW` at `0x18000e55b`
- `SHLWAPI!PathFindExtensionW` at `0x18000e55b`
- `SHLWAPI!__imp_ualstrcpynW` at `0x18000e925`
- `SHLWAPI!__imp_ualstrcpynW` at `0x18000e925`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000e626`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000e626`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e428`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e638`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e7bd`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e428`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e638`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e7bd`
- `OLEAUT32!__imp_VariantInit` at `0x18000e2fa`
- `OLEAUT32!__imp_VariantInit` at `0x18000e653`
- `OLEAUT32!__imp_VariantInit` at `0x18000e2fa`
- `OLEAUT32!__imp_VariantInit` at `0x18000e653`

## string_xrefs

- `0x18000e84d`: `prop:System.ZipFolder.CompressedSize;System.Size;System.ZipFolder.Ratio;System.DateModified;System.ItemTypeText`

## pseudocode

```c
__int64 __fastcall CZipFolder::GetDetailsEx(
        LPCITEMIDLIST *this,
        const struct _ITEMIDLIST *a2,
        const struct _tagpropertykey *a3,
        struct tagVARIANT *a4)
{
  unsigned int FileTime; // ebx
  unsigned int v9; // r9d
  const struct CArchiveIDList *v10; // r14
  unsigned __int64 pid; // r8
  __int64 v12; // rax
  const PROPERTYKEY *v13; // rdx
  BSTR v14; // rax
  __int64 v16; // rax
  __int64 v17; // r8
  __int64 v18; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  const unsigned __int16 *ExtensionW; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  int v26; // eax
  UINT v27; // edx
  BSTR v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  OLECHAR *v34; // rcx
  BSTR v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  int v41; // eax
  PWSTR *v42; // r9
  FILETIME v43; // rcx
  unsigned int *v44; // [rsp+20h] [rbp-E0h]
  FILETIME pft; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD pv[5]; // [rsp+40h] [rbp-C0h] BYREF
  FILETIME v47; // [rsp+54h] [rbp-ACh]
  int v48; // [rsp+5Ch] [rbp-A4h]
  int v49; // [rsp+60h] [rbp-A0h]
  WCHAR pszExt[274]; // [rsp+6Ch] [rbp-94h] BYREF
  OLECHAR psz[264]; // [rsp+290h] [rbp+190h] BYREF

  VariantInit(a4);
  FileTime = -2147024809;
  v10 = CArchiveIDList::_IsValidID(a2);
  if ( !v10 )
    return FileTime;
  pid = a3->pid;
  switch ( (_DWORD)pid )
  {
    case 0xA:
      v16 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_ItemNameDisplay.fmtid.Data1;
      if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_ItemNameDisplay.fmtid.Data1 )
        v16 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_ItemNameDisplay.fmtid.Data4;
      if ( !v16 )
      {
        v17 = 0;
        goto LABEL_23;
      }
      goto LABEL_7;
    case 6:
      v18 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_ItemFolderPathDisplay.fmtid.Data1;
      if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_ItemFolderPathDisplay.fmtid.Data1 )
        v18 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_ItemFolderPathDisplay.fmtid.Data4;
      if ( !v18 )
      {
        FileTime = SHGetNameAndFlagsW(this[139], 0x8000u, psz, v9, v44);
        if ( (FileTime & 0x80000000) != 0 )
          return FileTime;
        return (unsigned int)InitVariantFromString(psz, a4);
      }
      goto LABEL_7;
    case 4:
      v20 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_ItemTypeText.fmtid.Data1;
      if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_ItemTypeText.fmtid.Data1 )
        v20 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_ItemTypeText.fmtid.Data4;
      if ( !v20 )
      {
        CArchiveIDList::CopyFileType(v10, psz, 4u);
LABEL_24:
        a4->vt = 8;
        v14 = SysAllocString(psz);
        a4->llVal = (LONGLONG)v14;
        if ( v14 )
          return 0;
LABEL_62:
        FileTime = -2147024882;
        VariantInit(a4);
        return FileTime;
      }
      goto LABEL_7;
    case 0xB:
      v21 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_ItemType.fmtid.Data1;
      if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_ItemType.fmtid.Data1 )
        v21 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_ItemType.fmtid.Data4;
      if ( !v21 )
      {
        FileTime = DisplayNameOfW(this, a2, 0x8000, psz);
        if ( (FileTime & 0x80000000) != 0 )
          return FileTime;
        ExtensionW = PathFindExtensionW(psz);
        return (unsigned int)InitVariantFromString(ExtensionW, a4);
      }
      goto LABEL_7;
  }
  if ( (_DWORD)pid != 100 )
    goto LABEL_7;
  v23 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_FileName.fmtid.Data1;
  if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_FileName.fmtid.Data1 )
    v23 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_FileName.fmtid.Data4;
  if ( v23 )
  {
LABEL_7:
    FileTime = -2147467263;
    if ( (_DWORD)pid == 6 )
    {
      v24 = *(_QWORD *)&a3->fmtid.Data1 - PKEY_ZipFolder_CompressedSize;
      if ( *(_QWORD *)&a3->fmtid.Data1 == PKEY_ZipFolder_CompressedSize )
        v24 = *(_QWORD *)a3->fmtid.Data4 - 0x31FA6000AA00F0A9LL;
      if ( !v24 )
      {
        if ( (*((_BYTE *)v10 + 32) & 0x10) == 0 )
        {
          FileTime = 0;
          a4->llVal = *((_QWORD *)v10 + 2);
          a4->vt = 21;
        }
        return FileTime;
      }
    }
    if ( (_DWORD)pid == 2 )
    {
      v25 = *(_QWORD *)&a3->fmtid.Data1 - PKEY_ZipFolder_Encrypted;
      if ( *(_QWORD *)&a3->fmtid.Data1 == PKEY_ZipFolder_Encrypted )
        v25 = *(_QWORD *)a3->fmtid.Data4 - 0x31FA6000AA00F0A9LL;
      if ( !v25 )
      {
        v26 = *((_DWORD *)v10 + 8);
        FileTime = 0;
        if ( (v26 & 0x10) != 0 )
        {
          psz[0] = 0;
        }
        else
        {
          v27 = 10080;
          if ( (v26 & 0x8000) == 0 )
            v27 = 10081;
          LoadStringW(g_hmodThisDll, v27, psz, 260);
        }
        a4->vt = 8;
        v28 = SysAllocString(psz);
        a4->llVal = (LONGLONG)v28;
        if ( !v28 )
          goto LABEL_62;
        return FileTime;
      }
    }
    if ( (_DWORD)pid == 3 )
    {
      v29 = *(_QWORD *)&a3->fmtid.Data1 - PKEY_ZipFolder_Method;
      if ( *(_QWORD *)&a3->fmtid.Data1 == PKEY_ZipFolder_Method )
        v29 = *(_QWORD *)a3->fmtid.Data4 - 0x31FA6000AA00F0A9LL;
      if ( !v29 )
      {
        CArchiveIDList::CopyCompressionMethod(v10, psz, 3u);
        return (unsigned int)InitVariantFromString(psz, a4);
      }
    }
    if ( (_DWORD)pid == 12 )
    {
      v30 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_Size.fmtid.Data1;
      if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_Size.fmtid.Data1 )
        v30 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_Size.fmtid.Data4;
      if ( !v30 )
      {
        if ( (*((_BYTE *)v10 + 32) & 0x10) != 0 )
          return FileTime;
        a4->llVal = *((_QWORD *)v10 + 1);
        a4->vt = 21;
        return 0;
      }
    }
    if ( (_DWORD)pid == 4 )
    {
      v31 = *(_QWORD *)&a3->fmtid.Data1 - PKEY_ZipFolder_Ratio;
      if ( *(_QWORD *)&a3->fmtid.Data1 == PKEY_ZipFolder_Ratio )
        v31 = *(_QWORD *)a3->fmtid.Data4 - 0x31FA6000AA00F0A9LL;
      if ( !v31 )
      {
        if ( (*((_BYTE *)v10 + 32) & 0x10) == 0 )
        {
          FileTime = 0;
          pft.dwLowDateTime = 0;
          CArchiveIDList::CopyCompressionRatioInt(v10, (unsigned int *)&pft);
          a4->lVal = pft.dwLowDateTime;
          a4->vt = 19;
        }
        return FileTime;
      }
    }
    if ( (_DWORD)pid == 14 )
    {
      v32 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_DateModified.fmtid.Data1;
      if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_DateModified.fmtid.Data1 )
        v32 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_DateModified.fmtid.Data4;
      if ( !v32 )
      {
        pft = 0;
        FileTime = CArchiveIDList::GetFileTime(v10, &pft);
        if ( (FileTime & 0x80000000) == 0 )
          return (unsigned int)InitVariantFromFileTime(&pft, a4);
        return FileTime;
      }
    }
    if ( (_DWORD)pid == 5 )
    {
      v33 = *(_QWORD *)&a3->fmtid.Data1 - PKEY_ZipFolder_CRC32;
      if ( *(_QWORD *)&a3->fmtid.Data1 == PKEY_ZipFolder_CRC32 )
        v33 = *(_QWORD *)a3->fmtid.Data4 - 0x31FA6000AA00F0A9LL;
      if ( !v33 )
      {
        CArchiveIDList::CopyCRC32(v10, psz, pid);
        v34 = psz;
        goto LABEL_87;
      }
    }
    switch ( (_DWORD)pid )
    {
      case 0:
        v36 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_FindData.fmtid.Data1;
        if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_FindData.fmtid.Data1 )
          v36 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_FindData.fmtid.Data4;
        if ( v36 )
        {
          v37 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_PropList_XPDetailsPanel.fmtid.Data1;
          if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_PropList_XPDetailsPanel.fmtid.Data1 )
            v37 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_PropList_XPDetailsPanel.fmtid.Data4;
          if ( !v37 )
            return (unsigned int)InitVariantFromString(
                                   L"prop:System.ItemNameDisplay;System.ItemTypeText;System.DateModified;System.Size;Syste"
                                    "m.FileAllocationSize",
                                   a4);
        }
        else
        {
          memset_0(pv, 0, 0x250u);
          pv[0] = *((_DWORD *)v10 + 8);
          v48 = *((_DWORD *)v10 + 3);
          v49 = *((_DWORD *)v10 + 2);
          pft = 0;
          v41 = CArchiveIDList::GetFileTime(v10, &pft);
          v43 = v47;
          if ( v41 >= 0 )
            v43 = pft;
          v47 = v43;
          ualstrcpynW(pszExt, (PERCEIVED *)v10 + 23, (PERCEIVEDFLAG *)0x104, v42);
          return (unsigned int)InitVariantFromBuffer(pv, 0x250u, a4);
        }
        return FileTime;
      case 8:
        v38 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_PropList_PreviewDetails.fmtid.Data1;
        if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_PropList_PreviewDetails.fmtid.Data1 )
          v38 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_PropList_PreviewDetails.fmtid.Data4;
        if ( v38 )
          return FileTime;
        v34 = L"prop:System.ZipFolder.CompressedSize;System.Size;System.ZipFolder.Ratio;System.DateModified;System.ItemTypeText";
LABEL_87:
        a4->vt = 8;
        v35 = SysAllocString(v34);
        a4->llVal = (LONGLONG)v35;
        if ( v35 )
          return 0;
        goto LABEL_62;
      case 0xA:
        v39 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_PropList_FileOperationPrompt.fmtid.Data1;
        if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_PropList_FileOperationPrompt.fmtid.Data1 )
          v39 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_PropList_FileOperationPrompt.fmtid.Data4;
        if ( !v39 )
          return (unsigned int)InitVariantFromString(L"prop:System.ItemTypeText;System.DateModified;System.Size", a4);
        return FileTime;
      case 0x22:
        v40 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_Security_EncryptionOwners.fmtid.Data1;
        if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_Security_EncryptionOwners.fmtid.Data1 )
          v40 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_Security_EncryptionOwners.fmtid.Data4;
        if ( v40 )
          return FileTime;
        v13 = &PKEY_Security_EncryptionOwners;
        break;
      case 0x20:
        v12 = *(_QWORD *)&a3->fmtid.Data1
            - *(_QWORD *)&PKEY_Security_AllowedEnterpriseDataProtectionIdentities.fmtid.Data1;
        if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_Security_AllowedEnterpriseDataProtectionIdentities.fmtid.Data1 )
          v12 = *(_QWORD *)a3->fmtid.Data4
              - *(_QWORD *)PKEY_Security_AllowedEnterpriseDataProtectionIdentities.fmtid.Data4;
        if ( v12 )
          return FileTime;
        v13 = &PKEY_Security_AllowedEnterpriseDataProtectionIdentities;
        break;
      default:
        return FileTime;
    }
    return (unsigned int)CZipFolder::ComputePKEYFromParent((CZipFolder *)this, v13, a4);
  }
  v17 = 32769;
LABEL_23:
  FileTime = DisplayNameOfW(this, a2, v17, psz);
  if ( (FileTime & 0x80000000) == 0 )
    goto LABEL_24;
  return FileTime;
}

```

## disassembly

```asm
0x18000e2c0  push    rbp
0x18000e2c2  push    rbx
0x18000e2c3  push    rsi
0x18000e2c4  push    rdi
0x18000e2c5  push    r13
0x18000e2c7  push    r14
0x18000e2c9  push    r15
0x18000e2cb  lea     rbp, [rsp-3B0h]
0x18000e2d3  sub     rsp, 4B0h
0x18000e2da  mov     rax, cs:__security_cookie
0x18000e2e1  xor     rax, rsp
0x18000e2e4  mov     [rbp+3E0h+var_40], rax
0x18000e2eb  mov     r13, rcx
0x18000e2ee  mov     rdi, r9
0x18000e2f1  mov     rcx, r9; pvarg
0x18000e2f4  mov     rsi, r8
0x18000e2f7  mov     r15, rdx
0x18000e2fa  call    cs:__imp_VariantInit
0x18000e300  mov     rcx, r15; struct _ITEMIDLIST *
0x18000e303  mov     ebx, 80070057h
0x18000e308  call    ?_IsValidID@CArchiveIDList@@SAPEBV1@PEFBU_ITEMIDLIST@@@Z; CArchiveIDList::_IsValidID(_ITEMIDLIST const *)
0x18000e30d  mov     r14, rax
0x18000e310  test    rax, rax
0x18000e313  jz      loc_18000E43D
0x18000e319  mov     r8d, [rsi+10h]; unsigned __int64
0x18000e31d  cmp     r8d, 0Ah
0x18000e321  jz      loc_18000E460
0x18000e327  cmp     r8d, 6
0x18000e32b  jz      loc_18000E488
0x18000e331  cmp     r8d, 4
0x18000e335  jz      loc_18000E4DE
0x18000e33b  cmp     r8d, 0Bh
0x18000e33f  jz      loc_18000E512
0x18000e345  cmp     r8d, 64h ; 'd'
0x18000e349  jz      loc_18000E571
0x18000e34f  cmp     r8d, cs:dword_180078E88
0x18000e356  mov     ebx, 80004001h
0x18000e35b  jz      loc_18000E596
0x18000e361  cmp     r8d, cs:dword_180078EA0
0x18000e368  jz      loc_18000E5D5
0x18000e36e  cmp     r8d, cs:dword_180078EB8
0x18000e375  jz      loc_18000E65E
0x18000e37b  cmp     r8d, 0Ch
0x18000e37f  jz      loc_18000E6A3
0x18000e385  cmp     r8d, cs:dword_180078ED0
0x18000e38c  jz      loc_18000E6E0
0x18000e392  cmp     r8d, 0Eh
0x18000e396  jz      loc_18000E72F
0x18000e39c  cmp     r8d, cs:dword_180078EE8
0x18000e3a3  jz      loc_18000E782
0x18000e3a9  test    r8d, r8d
0x18000e3ac  jz      loc_18000E7D7
0x18000e3b2  cmp     r8d, 8
0x18000e3b6  jz      loc_18000E82D
0x18000e3bc  cmp     r8d, 0Ah
0x18000e3c0  jz      loc_18000E859
0x18000e3c6  cmp     r8d, 22h ; '"'
0x18000e3ca  jz      loc_18000E88F
0x18000e3d0  cmp     r8d, 20h ; ' '
0x18000e3d4  jnz     short loc_18000E43D
0x18000e3d6  mov     rax, [rsi]
0x18000e3d9  sub     rax, qword ptr cs:PKEY_Security_AllowedEnterpriseDataProtectionIdentities.fmtid.Data1
0x18000e3e0  jnz     short loc_18000E3ED
0x18000e3e2  mov     rax, [rsi+8]
0x18000e3e6  sub     rax, qword ptr cs:PKEY_Security_AllowedEnterpriseDataProtectionIdentities.fmtid.Data4
0x18000e3ed  test    rax, rax
0x18000e3f0  jnz     short loc_18000E43D
0x18000e3f2  lea     rdx, PKEY_Security_AllowedEnterpriseDataProtectionIdentities
0x18000e3f9  jmp     loc_18000E8B6
0x18000e3fe  mov     r8d, 8001h
0x18000e404  lea     r9, [rbp+3E0h+psz]
0x18000e40b  mov     rdx, r15
0x18000e40e  mov     rcx, r13
0x18000e411  call    DisplayNameOfW
0x18000e416  mov     ebx, eax
0x18000e418  test    eax, eax
0x18000e41a  js      short loc_18000E43D
0x18000e41c  lea     rcx, [rbp+3E0h+psz]; psz
0x18000e423  mov     word ptr [rdi], 8
0x18000e428  call    cs:__imp_SysAllocString
0x18000e42e  mov     [rdi+8], rax
0x18000e432  test    rax, rax
0x18000e435  jz      loc_18000E64B
0x18000e43b  xor     ebx, ebx
0x18000e43d  mov     eax, ebx
0x18000e43f  mov     rcx, [rbp+3E0h+var_40]
0x18000e446  xor     rcx, rsp; StackCookie
0x18000e449  call    __security_check_cookie
0x18000e44e  add     rsp, 4B0h
0x18000e455  pop     r15
0x18000e457  pop     r14
0x18000e459  pop     r13
0x18000e45b  pop     rdi
0x18000e45c  pop     rsi
0x18000e45d  pop     rbx
0x18000e45e  pop     rbp
0x18000e45f  retn
0x18000e460  mov     rax, [rsi]
0x18000e463  sub     rax, qword ptr cs:PKEY_ItemNameDisplay.fmtid.Data1
0x18000e46a  jnz     short loc_18000E477
0x18000e46c  mov     rax, [rsi+8]
0x18000e470  sub     rax, qword ptr cs:PKEY_ItemNameDisplay.fmtid.Data4
0x18000e477  test    rax, rax
0x18000e47a  jnz     loc_18000E34F
0x18000e480  xor     r8d, r8d
0x18000e483  jmp     loc_18000E404
0x18000e488  mov     rax, [rsi]
0x18000e48b  sub     rax, qword ptr cs:PKEY_ItemFolderPathDisplay.fmtid.Data1
0x18000e492  jnz     short loc_18000E49F
0x18000e494  mov     rax, [rsi+8]
0x18000e498  sub     rax, qword ptr cs:PKEY_ItemFolderPathDisplay.fmtid.Data4
0x18000e49f  test    rax, rax
0x18000e4a2  jnz     loc_18000E34F
0x18000e4a8  mov     rcx, [r13+458h]; pidl
0x18000e4af  lea     r8, [rbp+3E0h+psz]; unsigned __int16 *
0x18000e4b6  mov     edx, 8000h; unsigned int
0x18000e4bb  call    ?SHGetNameAndFlagsW@@YAJPEFBU_ITEMIDLIST@@KPEAGIPEAK@Z; SHGetNameAndFlagsW(_ITEMIDLIST const *,ulong,ushort *,uint,ulong *)
0x18000e4c0  mov     ebx, eax
0x18000e4c2  test    eax, eax
0x18000e4c4  js      loc_18000E43D
0x18000e4ca  mov     rdx, rdi; struct tagVARIANT *
0x18000e4cd  lea     rcx, [rbp+3E0h+psz]; unsigned __int16 *
0x18000e4d4  call    ?InitVariantFromString@@YAJPEBGPEAUtagVARIANT@@@Z; InitVariantFromString(ushort const *,tagVARIANT *)
0x18000e4d9  jmp     loc_18000E69C
0x18000e4de  mov     rax, [rsi]
0x18000e4e1  sub     rax, qword ptr cs:PKEY_ItemTypeText.fmtid.Data1
0x18000e4e8  jnz     short loc_18000E4F5
0x18000e4ea  mov     rax, [rsi+8]
0x18000e4ee  sub     rax, qword ptr cs:PKEY_ItemTypeText.fmtid.Data4
0x18000e4f5  test    rax, rax
0x18000e4f8  jnz     loc_18000E34F
0x18000e4fe  lea     rdx, [rbp+3E0h+psz]; unsigned __int16 *
0x18000e505  mov     rcx, r14; this
0x18000e508  call    ?CopyFileType@CArchiveIDList@@QEBAXPEAGI@Z; CArchiveIDList::CopyFileType(ushort *,uint)
0x18000e50d  jmp     loc_18000E41C
0x18000e512  mov     rax, [rsi]
0x18000e515  sub     rax, qword ptr cs:PKEY_ItemType.fmtid.Data1
0x18000e51c  jnz     short loc_18000E529
0x18000e51e  mov     rax, [rsi+8]
0x18000e522  sub     rax, qword ptr cs:PKEY_ItemType.fmtid.Data4
0x18000e529  test    rax, rax
0x18000e52c  jnz     loc_18000E34F
0x18000e532  lea     r9, [rbp+3E0h+psz]
0x18000e539  mov     r8d, 8000h
0x18000e53f  mov     rdx, r15
0x18000e542  mov     rcx, r13
0x18000e545  call    DisplayNameOfW
0x18000e54a  mov     ebx, eax
0x18000e54c  test    eax, eax
0x18000e54e  js      loc_18000E43D
0x18000e554  lea     rcx, [rbp+3E0h+psz]; pszPath
0x18000e55b  call    cs:__imp_PathFindExtensionW
0x18000e561  mov     rcx, rax; unsigned __int16 *
0x18000e564  mov     rdx, rdi; struct tagVARIANT *
0x18000e567  call    ?InitVariantFromString@@YAJPEBGPEAUtagVARIANT@@@Z; InitVariantFromString(ushort const *,tagVARIANT *)
0x18000e56c  jmp     loc_18000E69C
0x18000e571  mov     rax, [rsi]
0x18000e574  sub     rax, qword ptr cs:PKEY_FileName.fmtid.Data1
0x18000e57b  jnz     short loc_18000E588
0x18000e57d  mov     rax, [rsi+8]
0x18000e581  sub     rax, qword ptr cs:PKEY_FileName.fmtid.Data4
0x18000e588  test    rax, rax
0x18000e58b  jnz     loc_18000E34F
0x18000e591  jmp     loc_18000E3FE
0x18000e596  mov     rax, [rsi]
0x18000e599  sub     rax, cs:PKEY_ZipFolder_CompressedSize
0x18000e5a0  jnz     short loc_18000E5AD
0x18000e5a2  mov     rax, [rsi+8]
0x18000e5a6  sub     rax, cs:qword_180078E80
0x18000e5ad  test    rax, rax
0x18000e5b0  jnz     loc_18000E361
0x18000e5b6  test    byte ptr [r14+20h], 10h
0x18000e5bb  jnz     loc_18000E43D
0x18000e5c1  mov     rax, [r14+10h]
0x18000e5c5  xor     ebx, ebx
0x18000e5c7  mov     [rdi+8], rax
0x18000e5cb  mov     word ptr [rdi], 15h
0x18000e5d0  jmp     loc_18000E43D
0x18000e5d5  mov     rax, [rsi]
0x18000e5d8  sub     rax, cs:PKEY_ZipFolder_Encrypted
0x18000e5df  jnz     short loc_18000E5EC
0x18000e5e1  mov     rax, [rsi+8]
0x18000e5e5  sub     rax, cs:qword_180078E98
0x18000e5ec  test    rax, rax
0x18000e5ef  jnz     loc_18000E36E
0x18000e5f5  mov     eax, [r14+20h]
0x18000e5f9  xor     ebx, ebx
0x18000e5fb  test    al, 10h
0x18000e5fd  jnz     loc_18000E94F
0x18000e603  mov     rcx, cs:g_hmodThisDll; hInstance
0x18000e60a  mov     r9d, 104h; cchBufferMax
0x18000e610  lea     r8, [rbp+3E0h+psz]; lpBuffer
0x18000e617  mov     edx, 2760h; uID
0x18000e61c  bt      eax, 0Fh
0x18000e620  jnb     loc_18000E945
0x18000e626  call    cs:__imp_LoadStringW
0x18000e62c  lea     rcx, [rbp+3E0h+psz]; psz
0x18000e633  mov     word ptr [rdi], 8
0x18000e638  call    cs:__imp_SysAllocString
0x18000e63e  mov     [rdi+8], rax
0x18000e642  test    rax, rax
0x18000e645  jnz     loc_18000E43D
0x18000e64b  mov     rcx, rdi; pvarg
0x18000e64e  mov     ebx, 8007000Eh
0x18000e653  call    cs:__imp_VariantInit
0x18000e659  jmp     loc_18000E43D
0x18000e65e  mov     rax, [rsi]
0x18000e661  sub     rax, cs:PKEY_ZipFolder_Method
0x18000e668  jnz     short loc_18000E675
0x18000e66a  mov     rax, [rsi+8]
0x18000e66e  sub     rax, cs:qword_180078EB0
0x18000e675  test    rax, rax
0x18000e678  jnz     loc_18000E37B
0x18000e67e  lea     rdx, [rbp+3E0h+psz]; unsigned __int16 *
0x18000e685  mov     rcx, r14; this
0x18000e688  call    ?CopyCompressionMethod@CArchiveIDList@@QEBAXPEAGI@Z; CArchiveIDList::CopyCompressionMethod(ushort *,uint)
0x18000e68d  mov     rdx, rdi; struct tagVARIANT *
0x18000e690  lea     rcx, [rbp+3E0h+psz]; unsigned __int16 *
0x18000e697  call    ?InitVariantFromString@@YAJPEBGPEAUtagVARIANT@@@Z; InitVariantFromString(ushort const *,tagVARIANT *)
0x18000e69c  mov     ebx, eax
0x18000e69e  jmp     loc_18000E43D
0x18000e6a3  mov     rax, [rsi]
0x18000e6a6  sub     rax, qword ptr cs:PKEY_Size.fmtid.Data1
0x18000e6ad  jnz     short loc_18000E6BA
0x18000e6af  mov     rax, [rsi+8]
0x18000e6b3  sub     rax, qword ptr cs:PKEY_Size.fmtid.Data4
0x18000e6ba  test    rax, rax
0x18000e6bd  jnz     loc_18000E385
0x18000e6c3  test    byte ptr [r14+20h], 10h
0x18000e6c8  jnz     loc_18000E43D
0x18000e6ce  mov     rax, [r14+8]
0x18000e6d2  mov     [rdi+8], rax
0x18000e6d6  mov     word ptr [rdi], 15h
0x18000e6db  jmp     loc_18000E43B
0x18000e6e0  mov     rax, [rsi]
0x18000e6e3  sub     rax, cs:PKEY_ZipFolder_Ratio
0x18000e6ea  jnz     short loc_18000E6F7
0x18000e6ec  mov     rax, [rsi+8]
0x18000e6f0  sub     rax, cs:qword_180078EC8
0x18000e6f7  test    rax, rax
0x18000e6fa  jnz     loc_18000E392
0x18000e700  test    byte ptr [r14+20h], 10h
0x18000e705  jnz     loc_18000E43D
0x18000e70b  xor     ebx, ebx
0x18000e70d  lea     rdx, [rsp+4E0h+pft]; unsigned int *
0x18000e712  mov     rcx, r14; this
0x18000e715  mov     [rsp+4E0h+pft.dwLowDateTime], ebx
0x18000e719  call    ?CopyCompressionRatioInt@CArchiveIDList@@QEBAXPEAI@Z; CArchiveIDList::CopyCompressionRatioInt(uint *)
0x18000e71e  mov     eax, [rsp+4E0h+pft.dwLowDateTime]
0x18000e722  mov     [rdi+8], eax
0x18000e725  mov     word ptr [rdi], 13h
0x18000e72a  jmp     loc_18000E43D
0x18000e72f  mov     rax, [rsi]
0x18000e732  sub     rax, qword ptr cs:PKEY_DateModified.fmtid.Data1
0x18000e739  jnz     short loc_18000E746
0x18000e73b  mov     rax, [rsi+8]
0x18000e73f  sub     rax, qword ptr cs:PKEY_DateModified.fmtid.Data4
0x18000e746  test    rax, rax
0x18000e749  jnz     loc_18000E39C
0x18000e74f  xor     ebx, ebx
0x18000e751  lea     rdx, [rsp+4E0h+pft]; struct _FILETIME *
0x18000e756  mov     rcx, r14; this
0x18000e759  mov     qword ptr [rsp+4E0h+pft.dwLowDateTime], rbx
0x18000e75e  call    ?GetFileTime@CArchiveIDList@@QEBAJPEAU_FILETIME@@@Z; CArchiveIDList::GetFileTime(_FILETIME *)
0x18000e763  mov     ebx, eax
0x18000e765  test    eax, eax
0x18000e767  js      loc_18000E43D
0x18000e76d  mov     rdx, rdi; pvar
0x18000e770  lea     rcx, [rsp+4E0h+pft]; pft
0x18000e775  call    cs:__imp_InitVariantFromFileTime
0x18000e77b  mov     ebx, eax
0x18000e77d  jmp     loc_18000E43D
0x18000e782  mov     rax, [rsi]
0x18000e785  sub     rax, cs:PKEY_ZipFolder_CRC32
0x18000e78c  jnz     short loc_18000E799
0x18000e78e  mov     rax, [rsi+8]
0x18000e792  sub     rax, cs:qword_180078EE0
0x18000e799  test    rax, rax
0x18000e79c  jnz     loc_18000E3A9
0x18000e7a2  lea     rdx, [rbp+3E0h+psz]; unsigned __int16 *
0x18000e7a9  mov     rcx, r14; this
0x18000e7ac  call    ?CopyCRC32@CArchiveIDList@@QEBAXPEAG_K@Z; CArchiveIDList::CopyCRC32(ushort *,unsigned __int64)
0x18000e7b1  lea     rcx, [rbp+3E0h+psz]; psz
0x18000e7b8  mov     word ptr [rdi], 8
0x18000e7bd  call    cs:__imp_SysAllocString
0x18000e7c3  mov     [rdi+8], rax
0x18000e7c7  test    rax, rax
0x18000e7ca  jz      loc_18000E64B
0x18000e7d0  xor     ebx, ebx
0x18000e7d2  jmp     loc_18000E43D
0x18000e7d7  mov     rax, [rsi]
0x18000e7da  sub     rax, qword ptr cs:PKEY_FindData.fmtid.Data1
0x18000e7e1  jnz     short loc_18000E7EE
0x18000e7e3  mov     rax, [rsi+8]
0x18000e7e7  sub     rax, qword ptr cs:PKEY_FindData.fmtid.Data4
0x18000e7ee  test    rax, rax
0x18000e7f1  jz      loc_18000E8C6
0x18000e7f7  mov     rax, [rsi]
0x18000e7fa  sub     rax, qword ptr cs:PKEY_PropList_XPDetailsPanel.fmtid.Data1
0x18000e801  jnz     short loc_18000E80E
  ... truncated ...
```
