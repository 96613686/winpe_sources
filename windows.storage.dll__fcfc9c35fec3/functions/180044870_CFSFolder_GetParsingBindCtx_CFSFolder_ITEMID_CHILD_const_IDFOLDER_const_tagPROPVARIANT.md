# CFSFolder::_GetParsingBindCtx(CFSFolder *,_ITEMID_CHILD const *,IDFOLDER const *,tagPROPVARIANT *)

- ea: `0x180044870`
- end: `0x18004521f`
- name: `?_GetParsingBindCtx@CFSFolder@@KAJPEAV1@PEFBU_ITEMID_CHILD@@PEFBUIDFOLDER@@PEAUtagPROPVARIANT@@@Z`
- size: `2479`
- prototype: `__int64 __fastcall(struct CFSFolder *, const struct _ITEMID_CHILD *, const struct IDFOLDER *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `19`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000b1a0`
- `0x1800376a0`
- `0x180038f80`
- `0x18003df10`
- `0x18003e730`
- `0x180043400`
- `0x180044870`
- `0x180045230`
- `0x180045520`
- `0x180048ad0`
- `0x18004e06c`
- `0x18006b770`
- `0x1800995d0`
- `0x180107000`
- `0x1803b1f60`
- `0x1803b243c`
- `0x1803b2ac0`
- `0x1803b69c5`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180045007`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180045183`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180045007`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180045183`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x1800448eb`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x18004505a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x180045079`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x1800448eb`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x18004505a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x180045079`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044ebb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044f6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044f85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044f9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044ebb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044f6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044f85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044f9b`
- `SHCORE!__imp_ualstrcpynW` at `0x180044a1a`
- `SHCORE!__imp_ualstrcpynW` at `0x1800450e5`
- `SHCORE!__imp_ualstrcpynW` at `0x180044a1a`
- `SHCORE!__imp_ualstrcpynW` at `0x1800450e5`
- `SHCORE!__imp_ualstrlenW` at `0x18004511a`
- `SHCORE!__imp_ualstrlenW` at `0x1806609d2`
- `SHCORE!__imp_ualstrlenW` at `0x18004511a`
- `SHCORE!__imp_ualstrlenW` at `0x1806609d2`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x180044cca`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x180044cca`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180044c5d`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180044c5d`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHAnsiToUnicode` at `0x180045204`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHAnsiToUnicode` at `0x180045204`
- `api-ms-win-ole32-ie-l1-1-0!CreateBindCtx` at `0x180044b2f`
- `api-ms-win-ole32-ie-l1-1-0!CreateBindCtx` at `0x180044b2f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CFSFolder::_GetParsingBindCtx(
        struct _GUID *a1,
        const struct _ITEMID_CHILD *a2,
        const struct IDFOLDER *a3,
        struct tagPROPVARIANT *a4)
{
  __int64 v8; // rbx
  __int64 v9; // rax
  unsigned __int64 v10; // rcx
  struct IDFOLDER *v11; // r10
  WCHAR *v12; // rdx
  WCHAR *v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r9
  WCHAR *v16; // r8
  WCHAR v17; // ax
  WCHAR *v18; // rcx
  LPITEMIDLIST v19; // rsi
  unsigned int v20; // r8d
  HRESULT inited; // ebx
  char *v22; // rdi
  __int64 v23; // r8
  __int64 v24; // rax
  __int64 v25; // rax
  LPBC v26; // rdi
  int v27; // ebx
  __int64 v28; // rax
  const ITEMIDLIST *v29; // rcx
  int v30; // eax
  const ITEMIDLIST *v31; // rcx
  CShellItem *v32; // rax
  CShellItem *v33; // rax
  CShellItem *v34; // rdi
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  const void *v39; // rbx
  unsigned __int64 v40; // r8
  __int64 v41; // r8
  unsigned __int64 *v42; // r8
  unsigned int v43; // ecx
  int v44; // eax
  int v45; // eax
  unsigned int v46; // ecx
  int v47; // eax
  void *ppv; // [rsp+30h] [rbp-D0h] BYREF
  LPBC ppbc; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v50; // [rsp+40h] [rbp-C0h] BYREF
  struct IShellItem *v51[3]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v52[2]; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v53; // [rsp+70h] [rbp-90h]
  LPVOID v54; // [rsp+78h] [rbp-88h]
  LPVOID pv; // [rsp+90h] [rbp-70h]
  __int64 v56; // [rsp+98h] [rbp-68h]
  __int64 v57; // [rsp+A0h] [rbp-60h]
  __int64 v58; // [rsp+A8h] [rbp-58h]
  struct IDFOLDER *v59; // [rsp+B0h] [rbp-50h]
  __int64 v60; // [rsp+B8h] [rbp-48h]
  WCHAR *v61; // [rsp+C8h] [rbp-38h]
  int v62; // [rsp+E0h] [rbp-20h]
  WCHAR value[278]; // [rsp+E4h] [rbp-1Ch] BYREF
  unsigned int FullFileAttributes; // [rsp+310h] [rbp+210h] BYREF
  struct _FILETIME v65; // [rsp+314h] [rbp+214h] BYREF
  struct _FILETIME v66; // [rsp+31Ch] [rbp+21Ch] BYREF
  struct _FILETIME FileTime; // [rsp+324h] [rbp+224h] BYREF
  int v68; // [rsp+32Ch] [rbp+22Ch]
  int v69; // [rsp+330h] [rbp+230h]
  int v70; // [rsp+334h] [rbp+234h]
  char v71; // [rsp+33Ch] [rbp+23Ch] BYREF
  WCHAR WideCharStr[14]; // [rsp+544h] [rbp+444h] BYREF
  __int64 v73; // [rsp+560h] [rbp+460h]
  _BYTE v74[24]; // [rsp+568h] [rbp+468h] BYREF
  __int128 v75; // [rsp+580h] [rbp+480h] BYREF
  _OWORD v76[2]; // [rsp+590h] [rbp+490h]

  CFileSysItemString::CFileSysItemString((CFileSysItemString *)v52, (struct CFSFolder *)a1, a2, a3);
  memset_0(&FullFileAttributes, 0, 0x268u);
  v8 = v60;
  if ( DosDateTimeToFileTime(*((_WORD *)v59 + 4), *((_WORD *)v59 + 5), &FileTime)
    || (int)ResultFromKnownLastError() >= 0 )
  {
    if ( v8 )
    {
      if ( *(_WORD *)(v8 + 2) >= 9u )
      {
        v9 = *(unsigned int *)(v8 + 42);
        if ( (_DWORD)v9 )
        {
          v10 = FileTime.dwLowDateTime + ((unsigned __int64)FileTime.dwHighDateTime << 32) - v9;
          FileTime.dwLowDateTime -= v9;
          FileTime.dwHighDateTime = HIDWORD(v10);
        }
      }
    }
  }
  FullFileAttributes = GetFullFileAttributes(v59);
  v11 = v59;
  v69 = *((_DWORD *)v59 + 1);
  if ( v61 )
    goto LABEL_92;
  if ( (v62 & 1) == 0 )
  {
    if ( v60 )
    {
      v12 = (WCHAR *)(v60 + *(unsigned __int16 *)(v60 + 16));
      if ( ((unsigned __int8)v12 & 1) == 0 )
      {
        if ( v12 != value )
        {
          v61 = (WCHAR *)(v60 + *(unsigned __int16 *)(v60 + 16));
          goto LABEL_12;
        }
LABEL_99:
        v62 = 1;
LABEL_12:
        if ( !v61 )
          goto LABEL_13;
LABEL_92:
        v13 = v61;
        goto LABEL_14;
      }
    }
    else
    {
      if ( (*((_BYTE *)v59 + 2) & 0x34) != 0x34 )
      {
        MultiByteToWideChar(0, 0, (LPCCH)v59 + 14, -1, value, 260);
        goto LABEL_98;
      }
      v12 = (WCHAR *)((char *)v59 + 14);
    }
    ualstrcpynW(value, v12, 260);
LABEL_98:
    v11 = v59;
    goto LABEL_99;
  }
LABEL_13:
  v13 = value;
LABEL_14:
  v14 = 2147483646;
  v15 = 260;
  v16 = (WCHAR *)&v71;
  do
  {
    if ( !v14 )
      break;
    v17 = *v13;
    if ( !*v13 )
      break;
    ++v13;
    *v16++ = v17;
    --v14;
    --v15;
  }
  while ( v15 );
  v18 = v16 - 1;
  if ( v15 )
    v18 = v16;
  v19 = 0;
  *v18 = 0;
  v20 = 0;
  if ( (*((_BYTE *)v11 + 2) & 0x34) == 0x34 )
  {
    if ( !v60 )
    {
      v45 = ualstrlenW((char *)v11 + 14, v13, 0);
      v11 = v59;
      v46 = *(unsigned __int16 *)v59;
      if ( v46 <= 2 * v45 + 16
        || (v47 = UnalignedStringCbLengthW(
                    (const unsigned __int16 *)((char *)v59 + (unsigned int)(2 * v45 + 2) + 14),
                    v46 - (2 * v45 + 2) - 14,
                    (unsigned __int64 *)(unsigned int)(2 * v45 + 2)),
            v11 = v59,
            v47 < 0) )
      {
        v20 = 0;
      }
    }
    ualstrcpynW(WideCharStr, (char *)v11 + v20 + 14, 14);
  }
  else
  {
    if ( !v60 )
    {
      v41 = -1;
      do
        ++v41;
      while ( *((_BYTE *)v11 + v41 + 14) );
      v42 = (unsigned __int64 *)(unsigned int)(v41 + 1);
      v43 = *(unsigned __int16 *)v11;
      if ( v43 <= (int)v42 + 14
        || (v44 = StringCbLengthA((const char *)v11 + (unsigned int)v42 + 14, v43 - (unsigned int)v42 - 14, v42),
            v11 = v59,
            v44 < 0) )
      {
        v20 = 0;
      }
    }
    if ( !MultiByteToWideChar(0, 0, (LPCCH)v11 + v20 + 14, -1, WideCharStr, 14) )
      memset(WideCharStr, 0, sizeof(WideCharStr));
  }
  if ( v60 )
  {
    DosDateTimeToFileTime(*(_WORD *)(v60 + 8), *(_WORD *)(v60 + 10), &v65);
    DosDateTimeToFileTime(*(_WORD *)(v60 + 12), *(_WORD *)(v60 + 14), &v66);
    if ( *(_WORD *)(v60 + 2) >= 7u )
    {
      v73 = *(_QWORD *)(v60 + 20);
      v70 = *(_DWORD *)(v60 + 32);
      v68 = *(_DWORD *)(v60 + 28);
    }
  }
  v50 = 0;
  inited = -2147024882;
  v22 = (char *)operator new(0x278u, (const struct std::nothrow_t *)&std::nothrow);
  v51[0] = (struct IShellItem *)v22;
  if ( v22 )
  {
    *(_QWORD *)v22 = &CFileSysBindData::`vftable';
    *((_DWORD *)v22 + 2) = 1;
    memset_0(v22 + 40, 0, 0x250u);
    *((_QWORD *)v22 + 2) = 0;
    *(_OWORD *)(v22 + 24) = xmmword_180727030;
    inited = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))v22)(
               v22,
               &GUID_3acf075f_71db_4afa_81f0_3fc4fdf2a5b8,
               &v50);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v22 + 16LL))(v22);
    if ( inited >= 0 )
    {
      (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v50 + 24LL))(v50, &FullFileAttributes);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v50 + 40LL))(v50, v73);
      CFileSysItemString::GetJunctionClsid(v52, 1, v74);
      (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v50 + 56LL))(v50, v74);
      ppbc = 0;
      inited = CreateBindCtx(0, &ppbc);
      if ( inited < 0 )
      {
LABEL_75:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
        goto LABEL_76;
      }
      v51[0] = (struct IShellItem *)16;
      v51[1] = (struct IShellItem *)4096;
      inited = ((__int64 (__fastcall *)(LPBC, struct IShellItem **))ppbc->lpVtbl->SetBindOptions)(ppbc, v51);
      if ( inited < 0 )
      {
        SafeRelease<IFilterCreationCallback>(&ppbc);
        goto LABEL_75;
      }
      inited = ((__int64 (__fastcall *)(LPBC, const unsigned __int16 *, __int64))ppbc->lpVtbl->RegisterObjectParam)(
                 ppbc,
                 L"File System Bind Data",
                 v50);
      if ( inited < 0 )
        goto LABEL_74;
      if ( (v62 & 4) == 0 )
      {
        value[0] = 0;
        if ( v60 )
        {
          if ( *(_WORD *)(v60 + 2) >= 7u && (v24 = *(unsigned __int16 *)(v60 + 36), (_WORD)v24) )
          {
            v39 = (const void *)(v60 + v24);
            v40 = ualstrlenW(v60 + v24, v60, v23) + 1;
            if ( v40 <= 0x104 )
            {
              memcpy_0(value, v39, 2 * v40);
              goto LABEL_35;
            }
          }
          else
          {
            v25 = *(unsigned __int16 *)(v60 + 18);
            if ( (_WORD)v25 )
            {
              SHAnsiToUnicode((PCSTR)(v60 + v25), value, 260);
              goto LABEL_35;
            }
          }
        }
        value[0] = 0;
      }
LABEL_35:
      v62 = 4;
      if ( value[0] )
      {
        v26 = ppbc;
        if ( ppbc )
        {
          ppv = 0;
          v51[0] = 0;
          if ( ((int (__fastcall *)(LPBC, const unsigned __int16 *, struct IShellItem **))ppbc->lpVtbl->GetObjectParam)(
                 ppbc,
                 L"SHBindCtxPropertyBag",
                 v51) >= 0
            && (v27 = ((__int64 (__fastcall *)(struct IShellItem *, GUID *, void **))v51[0]->lpVtbl->QueryInterface)(
                        v51[0],
                        &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
                        &ppv),
                ((void (__fastcall *)(struct IShellItem *))v51[0]->lpVtbl->Release)(v51[0]),
                v27 >= 0)
            || (inited = PSCreateMemoryPropertyStore(&GUID_55272a00_42cb_11ce_8135_00aa004bb851, &ppv), inited >= 0)
            && (v75 = *(_OWORD *)L"SHBindCtxPropertyBag",
                v76[0] = *(_OWORD *)L"xPropertyBag",
                *(_OWORD *)((char *)v76 + 10) = *(_OWORD *)L"ertyBag",
                inited = ((__int64 (__fastcall *)(LPBC, __int128 *, void *))v26->lpVtbl->RegisterObjectParam)(
                           v26,
                           &v75,
                           ppv),
                inited >= 0) )
          {
            inited = PSPropertyBag_WriteStr((IPropertyBag *)ppv, L"LocalizedResourceName", value);
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
          }
        }
        else
        {
          inited = -2147024809;
        }
        if ( inited < 0 )
          goto LABEL_74;
      }
      if ( !ILFindFirstHiddenID(a2) )
        goto LABEL_72;
      v51[0] = 0;
      v28 = *(_QWORD *)&a1[31].Data1 - *(_QWORD *)&GUID_NULL.Data1;
      if ( !v28 )
        v28 = *(_QWORD *)a1[31].Data4 - *(_QWORD *)GUID_NULL.Data4;
      if ( v28 )
      {
        v30 = SHGetKnownFolderIDList_Internal(a1 + 31, 0x1000u, 0, (struct _ITEMIDLIST_ABSOLUTE **)v51);
        v19 = (LPITEMIDLIST)v51[0];
      }
      else
      {
        v29 = *(const ITEMIDLIST **)a1[27].Data4;
        if ( !v29 )
          goto LABEL_52;
        v19 = ILClone(v29);
        v30 = 0;
        if ( !v19 )
          v30 = -2147024882;
      }
      if ( v30 >= 0 )
        goto LABEL_56;
      v19 = 0;
LABEL_52:
      v31 = *(const ITEMIDLIST **)&a1[27].Data1;
      if ( v31 )
      {
        v19 = ILClone(v31);
        inited = 0;
        if ( !v19 )
          inited = -2147024882;
      }
      else
      {
        inited = -2147024809;
      }
      if ( inited < 0 )
        goto LABEL_74;
LABEL_56:
      v51[0] = 0;
      ppv = 0;
      inited = -2147024882;
      v32 = (CShellItem *)operator new(0xD8u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v32 )
      {
        v33 = CShellItem::CShellItem(v32);
        v34 = v33;
        if ( v33 )
        {
          inited = CObjectWithThreadUseDetection::InitApartmentId((CShellItem *)((char *)v33 + 80));
          if ( inited >= 0 )
            inited = (**(__int64 (__fastcall ***)(CShellItem *, GUID *, void **))v34)(
                       v34,
                       &GUID_b3a4b685_b685_4805_99d9_5dead2873236,
                       &ppv);
          (*(void (__fastcall **)(CShellItem *))(*(_QWORD *)v34 + 16LL))(v34);
          if ( inited < 0 )
          {
LABEL_71:
            CoTaskMemFree(v19);
            if ( inited >= 0 )
            {
LABEL_72:
              inited = ((__int64 (__fastcall *)(LPBC, GUID *, ULONG *))ppbc->lpVtbl->QueryInterface)(
                         ppbc,
                         &GUID_00000000_0000_0000_c000_000000000046,
                         &a4->decVal.Lo32);
              if ( inited >= 0 )
                a4->vt = 13;
            }
LABEL_74:
            ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
            goto LABEL_75;
          }
          inited = (*(__int64 (__fastcall **)(void *, LPITEMIDLIST, _QWORD, const struct _ITEMID_CHILD *))(*(_QWORD *)ppv + 24LL))(
                     ppv,
                     v19,
                     0,
                     a2);
          if ( inited >= 0 )
            inited = (**(__int64 (__fastcall ***)(void *, GUID *, struct IShellItem **))ppv)(
                       ppv,
                       &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                       v51);
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
        }
      }
      if ( inited >= 0 )
      {
        if ( ((((*((_BYTE *)a3 + 2) & 0x37) - 50) & 0xFB) != 0 || (unsigned int)(*((_DWORD *)a3 + 1) - 1) <= 0xFFFFFFFD)
          && *((_WORD *)a3 + 4)
          || (inited = MarkItemAsSimple(v51[0]), inited >= 0) )
        {
          inited = ((__int64 (__fastcall *)(LPBC, const unsigned __int16 *, struct IShellItem *))ppbc->lpVtbl->RegisterObjectParam)(
                     ppbc,
                     L"ParseOriginalItem",
                     v51[0]);
        }
        ((void (__fastcall *)(struct IShellItem *))v51[0]->lpVtbl->Release)(v51[0]);
      }
      goto LABEL_71;
    }
  }
LABEL_76:
  v52[0] = &CFileSysItemString::`vftable';
  v35 = v58;
  v58 = 0;
  if ( v35 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  v36 = v56;
  v56 = 0;
  if ( v36 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  v37 = v57;
  v57 = 0;
  if ( v37 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v54 )
    CoTaskMemFree(v54);
  if ( v53 )
    CoTaskMemFree(v53);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180044870  mov     [rsp-8+arg_10], rbx
0x180044875  push    rbp
0x180044876  push    rsi
0x180044877  push    rdi
0x180044878  push    r12
0x18004487a  push    r13
0x18004487c  push    r14
0x18004487e  push    r15
0x180044880  lea     rbp, [rsp-4C0h]
0x180044888  sub     rsp, 5C0h
0x18004488f  mov     rax, cs:__security_cookie
0x180044896  xor     rax, rsp
0x180044899  mov     [rbp+4F0h+var_40], rax
0x1800448a0  mov     r13, r9
0x1800448a3  mov     r15, r8
0x1800448a6  mov     r12, rdx
0x1800448a9  mov     r14, rcx
0x1800448ac  mov     r9, r8; struct IDFOLDER *
0x1800448af  mov     r8, rdx; struct _ITEMIDLIST_RELATIVE *
0x1800448b2  mov     rdx, rcx; struct CFSFolder *
0x1800448b5  lea     rcx, [rsp+5F0h+var_590]; this
0x1800448ba  call    ??0CFileSysItemString@@QEAA@PEAVCFSFolder@@PEFBU_ITEMIDLIST_RELATIVE@@PEFBUIDFOLDER@@@Z; CFileSysItemString::CFileSysItemString(CFSFolder *,_ITEMIDLIST_RELATIVE const *,IDFOLDER const *)
0x1800448bf  nop
0x1800448c0  xor     edx, edx; Val
0x1800448c2  mov     r8d, 268h; Size
0x1800448c8  lea     rcx, [rbp+4F0h+var_2E0]; void *
0x1800448cf  call    memset_0
0x1800448d4  mov     rbx, [rbp+4F0h+var_538]
0x1800448d8  mov     rcx, [rbp+4F0h+var_540]
0x1800448dc  lea     r8, [rbp+4F0h+FileTime]; lpFileTime
0x1800448e3  movzx   edx, word ptr [rcx+0Ah]; wFatTime
0x1800448e7  movzx   ecx, word ptr [rcx+8]; wFatDate
0x1800448eb  call    cs:__imp_DosDateTimeToFileTime
0x1800448f2  nop     dword ptr [rax+rax+00h]
0x1800448f7  test    eax, eax
0x1800448f9  jz      loc_180045101
0x1800448ff  test    rbx, rbx
0x180044902  jz      short loc_180044938
0x180044904  cmp     word ptr [rbx+2], 9
0x180044909  jb      short loc_180044938
0x18004490b  mov     eax, [rbx+2Ah]
0x18004490e  test    eax, eax
0x180044910  jz      short loc_180044938
0x180044912  mov     ecx, [rbp+4F0h+FileTime.dwHighDateTime]
0x180044918  shl     rcx, 20h
0x18004491c  sub     rcx, rax
0x18004491f  mov     eax, [rbp+4F0h+FileTime.dwLowDateTime]
0x180044925  add     rcx, rax
0x180044928  mov     [rbp+4F0h+FileTime.dwLowDateTime], ecx
0x18004492e  shr     rcx, 20h
0x180044932  mov     [rbp+4F0h+FileTime.dwHighDateTime], ecx
0x180044938  mov     rcx, [rbp+4F0h+var_540]; struct IDFOLDER *
0x18004493c  call    ?GetFullFileAttributes@@YAKPEFBUIDFOLDER@@@Z; GetFullFileAttributes(IDFOLDER const *)
0x180044941  mov     [rbp+4F0h+var_2E0], eax
0x180044947  mov     r10, [rbp+4F0h+var_540]
0x18004494b  mov     eax, [r10+4]
0x18004494f  mov     [rbp+4F0h+var_2C0], eax
0x180044955  cmp     [rbp+4F0h+var_528], 0
0x18004495a  jnz     loc_180045031
0x180044960  test    byte ptr [rbp+4F0h+var_510], 1
0x180044964  jnz     short loc_18004499F
0x180044966  mov     rcx, [rbp+4F0h+var_538]
0x18004496a  test    rcx, rcx
0x18004496d  jz      loc_180045155
0x180044973  movzx   edx, word ptr [rcx+10h]
0x180044977  add     rdx, rcx
0x18004497a  test    dl, 1
0x18004497d  jnz     loc_1800450DB
0x180044983  lea     rax, [rbp+4F0h+value]
0x180044987  cmp     rdx, rax
0x18004498a  jz      loc_1800450F5
0x180044990  mov     [rbp+4F0h+var_528], rdx
0x180044994  cmp     [rbp+4F0h+var_528], 0
0x180044999  jnz     loc_180045031
0x18004499f  lea     rdx, [rbp+4F0h+value]
0x1800449a3  mov     ecx, 7FFFFFFEh
0x1800449a8  mov     r9d, 104h
0x1800449ae  lea     r8, [rbp+4F0h+var_2B4]
0x1800449b5  test    rcx, rcx
0x1800449b8  jz      short loc_1800449D7
0x1800449ba  movzx   eax, word ptr [rdx]
0x1800449bd  test    ax, ax
0x1800449c0  jz      short loc_1800449D7
0x1800449c2  add     rdx, 2
0x1800449c6  mov     [r8], ax
0x1800449ca  add     r8, 2
0x1800449ce  dec     rcx
0x1800449d1  sub     r9, 1
0x1800449d5  jnz     short loc_1800449B5
0x1800449d7  lea     rcx, [r8-2]
0x1800449db  test    r9, r9
0x1800449de  cmovnz  rcx, r8
0x1800449e2  xor     esi, esi
0x1800449e4  mov     [rcx], si
0x1800449e7  movzx   eax, byte ptr [r10+2]
0x1800449ec  and     al, 34h
0x1800449ee  mov     r8d, esi
0x1800449f1  cmp     al, 34h ; '4'
0x1800449f3  jnz     loc_180044FD5
0x1800449f9  cmp     [rbp+4F0h+var_538], rsi
0x1800449fd  jz      loc_1806609CE
0x180044a03  mov     eax, r8d
0x180044a06  lea     rdx, [r10+0Eh]
0x180044a0a  add     rdx, rax
0x180044a0d  mov     r8d, 0Eh
0x180044a13  lea     rcx, [rbp+4F0h+WideCharStr]
0x180044a1a  call    cs:__imp_ualstrcpynW
0x180044a21  nop     dword ptr [rax+rax+00h]
0x180044a26  mov     rcx, [rbp+4F0h+var_538]
0x180044a2a  test    rcx, rcx
0x180044a2d  jnz     loc_18004504B
0x180044a33  mov     [rsp+5F0h+var_5B0], rsi
0x180044a38  mov     ebx, 8007000Eh
0x180044a3d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180044a44  mov     ecx, 278h; unsigned __int64
0x180044a49  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180044a4e  mov     rdi, rax
0x180044a51  mov     [rsp+5F0h+var_5A8], rax
0x180044a56  test    rax, rax
0x180044a59  jz      loc_180044F17
0x180044a5f  lea     rax, ??_7CFileSysBindData@@6B@; const CFileSysBindData::`vftable'
0x180044a66  mov     [rdi], rax
0x180044a69  mov     dword ptr [rdi+8], 1
0x180044a70  lea     rcx, [rdi+28h]; void *
0x180044a74  xor     edx, edx; Val
0x180044a76  mov     r8d, 250h; Size
0x180044a7c  call    memset_0
0x180044a81  xor     eax, eax
0x180044a83  mov     [rdi+10h], rax
0x180044a87  movups  xmm0, cs:xmmword_180727030
0x180044a8e  movups  xmmword ptr [rdi+18h], xmm0
0x180044a92  mov     rax, [rdi]
0x180044a95  lea     r8, [rsp+5F0h+var_5B0]
0x180044a9a  lea     rdx, _GUID_3acf075f_71db_4afa_81f0_3fc4fdf2a5b8
0x180044aa1  mov     rcx, rdi
0x180044aa4  mov     rax, [rax]
0x180044aa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044aac  mov     ebx, eax
0x180044aae  mov     rax, [rdi]
0x180044ab1  mov     rcx, rdi
0x180044ab4  mov     rax, [rax+10h]
0x180044ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044abd  test    ebx, ebx
0x180044abf  js      loc_180044F17
0x180044ac5  mov     rcx, [rsp+5F0h+var_5B0]
0x180044aca  mov     rax, [rcx]
0x180044acd  lea     rdx, [rbp+4F0h+var_2E0]
0x180044ad4  mov     rax, [rax+18h]
0x180044ad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044add  mov     rcx, [rsp+5F0h+var_5B0]
0x180044ae2  mov     rax, [rcx]
0x180044ae5  mov     rdx, [rbp+4F0h+var_90]
0x180044aec  mov     rax, [rax+28h]
0x180044af0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044af5  lea     r8, [rbp+4F0h+var_88]
0x180044afc  mov     edx, 1
0x180044b01  lea     rcx, [rsp+5F0h+var_590]
0x180044b06  call    ?GetJunctionClsid@CFileSysItemString@@QEAAHW4FSIS_JUNCTION_FLAGS@@PEAU_GUID@@@Z; CFileSysItemString::GetJunctionClsid(FSIS_JUNCTION_FLAGS,_GUID *)
0x180044b0b  mov     rcx, [rsp+5F0h+var_5B0]
0x180044b10  mov     rax, [rcx]
0x180044b13  lea     rdx, [rbp+4F0h+var_88]
0x180044b1a  mov     rax, [rax+38h]
0x180044b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044b23  mov     [rsp+5F0h+ppbc], rsi
0x180044b28  lea     rdx, [rsp+5F0h+ppbc]; ppbc
0x180044b2d  xor     ecx, ecx; reserved
0x180044b2f  call    cs:__imp_CreateBindCtx
0x180044b36  nop     dword ptr [rax+rax+00h]
0x180044b3b  mov     ebx, eax
0x180044b3d  test    eax, eax
0x180044b3f  js      loc_180044F04
0x180044b45  mov     [rsp+5F0h+var_5A8], 10h
0x180044b4e  mov     [rsp+5F0h+var_5A0], 1000h
0x180044b57  mov     rcx, [rsp+5F0h+ppbc]
0x180044b5c  mov     rax, [rcx]
0x180044b5f  lea     rdx, [rsp+5F0h+var_5A8]
0x180044b64  mov     rax, [rax+30h]
0x180044b68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044b6d  mov     ebx, eax
0x180044b6f  test    eax, eax
0x180044b71  js      loc_1800451E7
0x180044b77  mov     rcx, [rsp+5F0h+ppbc]
0x180044b7c  mov     rax, [rcx]
0x180044b7f  mov     r8, [rsp+5F0h+var_5B0]
0x180044b84  lea     rdx, aFileSystemBind; "File System Bind Data"
0x180044b8b  mov     rax, [rax+48h]
0x180044b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044b94  mov     ebx, eax
0x180044b96  test    eax, eax
0x180044b98  js      loc_180044EF3
0x180044b9e  test    byte ptr [rbp+4F0h+var_510], 4
0x180044ba2  jnz     short loc_180044BD6
0x180044ba4  mov     [rbp+4F0h+value], si
0x180044ba8  mov     rdx, [rbp+4F0h+var_538]
0x180044bac  test    rdx, rdx
0x180044baf  jz      short loc_180044BD2
0x180044bb1  cmp     word ptr [rdx+2], 7
0x180044bb6  jb      short loc_180044BC5
0x180044bb8  movzx   eax, word ptr [rdx+24h]
0x180044bbc  test    ax, ax
0x180044bbf  jnz     loc_180045113
0x180044bc5  movzx   eax, word ptr [rdx+12h]
0x180044bc9  test    ax, ax
0x180044bcc  jnz     loc_1800451F6
0x180044bd2  mov     [rbp+4F0h+value], si
0x180044bd6  mov     [rbp+4F0h+var_510], 4
0x180044bdd  cmp     [rbp+4F0h+value], si
0x180044be1  jz      loc_180044CF1
0x180044be7  mov     rdi, [rsp+5F0h+ppbc]
0x180044bec  test    rdi, rdi
0x180044bef  jz      loc_180045215
0x180044bf5  mov     [rsp+5F0h+ppv], rsi
0x180044bfa  mov     [rsp+5F0h+var_5A8], rsi
0x180044bff  mov     rax, [rdi]
0x180044c02  lea     r8, [rsp+5F0h+var_5A8]
0x180044c07  lea     rdx, aShbindctxprope; "SHBindCtxPropertyBag"
0x180044c0e  mov     rcx, rdi
0x180044c11  mov     rax, [rax+50h]
0x180044c15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044c1a  test    eax, eax
0x180044c1c  js      short loc_180044C51
0x180044c1e  mov     rcx, [rsp+5F0h+var_5A8]
0x180044c23  mov     rax, [rcx]
0x180044c26  lea     r8, [rsp+5F0h+ppv]
0x180044c2b  lea     rdx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851
0x180044c32  mov     rax, [rax]
0x180044c35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044c3a  mov     ebx, eax
0x180044c3c  mov     rcx, [rsp+5F0h+var_5A8]
0x180044c41  mov     rdx, [rcx]
0x180044c44  mov     rax, [rdx+10h]
0x180044c48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044c4d  test    ebx, ebx
0x180044c4f  jns     short loc_180044CBA
0x180044c51  lea     rdx, [rsp+5F0h+ppv]; ppv
0x180044c56  lea     rcx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x180044c5d  call    cs:__imp_PSCreateMemoryPropertyStore
0x180044c64  nop     dword ptr [rax+rax+00h]
0x180044c69  mov     ebx, eax
0x180044c6b  test    eax, eax
0x180044c6d  js      short loc_180044CE9
0x180044c6f  movups  xmm0, xmmword ptr cs:aShbindctxprope; "SHBindCtxPropertyBag"
0x180044c76  movups  [rbp+4F0h+var_70], xmm0
0x180044c7d  movups  xmm1, xmmword ptr cs:aShbindctxprope+10h; "xPropertyBag"
0x180044c84  movups  xmmword ptr [rbp+4F0h+var_60], xmm1
0x180044c8b  movups  xmm0, xmmword ptr cs:aShbindctxprope+1Ah; "ertyBag"
0x180044c92  movups  xmmword ptr [rbp+4F0h+var_60+0Ah], xmm0
0x180044c99  mov     rax, [rdi]
0x180044c9c  mov     r8, [rsp+5F0h+ppv]
0x180044ca1  lea     rdx, [rbp+4F0h+var_70]
0x180044ca8  mov     rcx, rdi
0x180044cab  mov     rax, [rax+48h]
0x180044caf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044cb4  mov     ebx, eax
0x180044cb6  test    eax, eax
0x180044cb8  js      short loc_180044CE9
0x180044cba  lea     r8, [rbp+4F0h+value]; value
0x180044cbe  lea     rdx, propName; "LocalizedResourceName"
0x180044cc5  mov     rcx, [rsp+5F0h+ppv]; propBag
0x180044cca  call    cs:__imp_PSPropertyBag_WriteStr
0x180044cd1  nop     dword ptr [rax+rax+00h]
0x180044cd6  mov     ebx, eax
0x180044cd8  mov     rcx, [rsp+5F0h+ppv]
0x180044cdd  mov     rax, [rcx]
0x180044ce0  mov     rax, [rax+10h]
0x180044ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044ce9  test    ebx, ebx
0x180044ceb  js      loc_180044EF3
0x180044cf1  mov     rcx, r12; struct _ITEMIDLIST_RELATIVE *
0x180044cf4  call    ?ILFindFirstHiddenID@@YAPEFBU_HIDDENITEMID@@PEFBU_ITEMIDLIST_RELATIVE@@@Z; ILFindFirstHiddenID(_ITEMIDLIST_RELATIVE const *)
0x180044cf9  test    rax, rax
0x180044cfc  jz      loc_180044ECB
0x180044d02  mov     [rsp+5F0h+var_5A8], rsi
0x180044d07  lea     rcx, [r14+1F0h]; struct _GUID *
0x180044d0e  mov     rax, [rcx]
0x180044d11  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180044d18  jnz     short loc_180044D25
0x180044d1a  mov     rax, [rcx+8]
0x180044d1e  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180044d25  test    rax, rax
0x180044d28  jnz     loc_1800450B6
0x180044d2e  mov     rcx, [r14+1B8h]; pidl
0x180044d35  test    rcx, rcx
0x180044d38  jz      loc_18004514B
0x180044d3e  call    ILClone
0x180044d43  mov     rsi, rax
0x180044d46  xor     eax, eax
0x180044d48  test    rsi, rsi
0x180044d4b  mov     edi, 8007000Eh
0x180044d50  cmovz   eax, edi
0x180044d53  test    eax, eax
0x180044d55  jns     short loc_180044D81
0x180044d57  xor     esi, esi
0x180044d59  mov     rcx, [r14+1B0h]; pidl
0x180044d60  test    rcx, rcx
0x180044d63  jz      loc_180045194
0x180044d69  call    ILClone
0x180044d6e  mov     rsi, rax
0x180044d71  xor     ebx, ebx
0x180044d73  test    rax, rax
  ... truncated ...
```
