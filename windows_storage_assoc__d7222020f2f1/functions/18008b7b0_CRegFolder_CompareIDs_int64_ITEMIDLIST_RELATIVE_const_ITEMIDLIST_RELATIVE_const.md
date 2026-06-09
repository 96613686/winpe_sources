# CRegFolder::CompareIDs(__int64,_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE const *)

- ea: `0x18008b7b0`
- end: `0x18008c737`
- name: `?CompareIDs@CRegFolder@@UEAAJ_JPEFBU_ITEMIDLIST_RELATIVE@@1@Z`
- size: `3975`
- prototype: `int(CRegFolder *__hidden this, __int64, const struct _ITEMIDLIST_RELATIVE *, const struct _ITEMIDLIST_RELATIVE *)`
- caller_count: `0`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180009fc0`
- `0x18005b730`
- `0x180062710`
- `0x180063050`
- `0x18008a190`
- `0x18008b7b0`
- `0x18008c740`
- `0x18008c830`
- `0x180091620`
- `0x180092a70`
- `0x180095130`
- `0x1800e3760`
- `0x1801b1844`
- `0x1801c0cf0`
- `0x1802292b0`
- `0x18028aaf4`
- `0x1802dae80`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x1803b69b9`
- `0x1803b69c5`
- `0x18067d010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18008c3c6`
- `OLEAUT32!__imp_VariantClear` at `0x18008c3d7`
- `OLEAUT32!__imp_VariantClear` at `0x18008c3c6`
- `OLEAUT32!__imp_VariantClear` at `0x18008c3d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008bc79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008bc79`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18008bca1`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18008bca1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008bda1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008be11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008be5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008c3e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008c3f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008c5b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008c5cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008bda1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008be11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008be5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008c3e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008c3f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008c5b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008c5cb`
- `SHCORE!__imp_IUnknown_GetClassID` at `0x18008b84c`
- `SHCORE!__imp_IUnknown_GetClassID` at `0x18008b84c`
- `PROPSYS!VariantCompare` at `0x18008c3b0`
- `PROPSYS!VariantCompare` at `0x18008c3b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CRegFolder::CompareIDs(
        CRegFolder *this,
        __int64 a2,
        ITEMIDLIST *a3,
        const struct _ITEMIDLIST_RELATIVE *a4)
{
  CRegFolder *v6; // rsi
  int v7; // r14d
  struct IUnknown *v8; // rdi
  _WORD *v9; // rax
  __int64 v10; // rcx
  unsigned __int64 cb; // rbx
  int v12; // r15d
  BYTE v13; // di
  __int64 v14; // rdx
  unsigned __int64 v15; // rax
  __int64 v16; // rdx
  ITEMIDLIST *v17; // rax
  struct _GUID *v18; // rax
  __int64 v19; // rdx
  _QWORD *v20; // r8
  __int64 v21; // rax
  unsigned __int64 v22; // rbx
  char v23; // di
  __int64 v24; // rdx
  unsigned __int64 v25; // rax
  __int64 v26; // rdx
  const struct _ITEMIDLIST_RELATIVE *v27; // rax
  struct _GUID *v28; // rax
  __int64 v29; // rdx
  _QWORD *v30; // r8
  __int64 v31; // rax
  int v32; // eax
  int v33; // r14d
  unsigned __int64 v34; // rdi
  BYTE v35; // r15
  CRegFolder *v36; // rcx
  ITEMIDLIST *v37; // r15
  unsigned __int64 v38; // rdi
  char v39; // r12
  CRegFolder *v40; // rcx
  const struct _ITEMIDLIST_RELATIVE *v41; // rdi
  int v42; // r13d
  unsigned __int64 v43; // rax
  __int64 v44; // rdx
  const struct _ITEMIDLIST_RELATIVE *v45; // rax
  const void *v46; // r14
  unsigned __int64 v47; // r12
  __int64 v48; // rdx
  ITEMIDLIST *v49; // rax
  char *v50; // rcx
  CRegFolder *v51; // rcx
  unsigned __int16 *p_cb; // rdx
  __int64 v53; // rdx
  const struct _ITEMIDLIST_RELATIVE *v54; // r15
  unsigned __int64 v55; // rax
  __int64 v56; // r9
  const struct _ITEMIDLIST_RELATIVE *v57; // r12
  int v58; // edx
  bool v59; // sf
  size_t v60; // rbx
  _WORD *v61; // rdi
  _WORD *v62; // r14
  char *v63; // r15
  size_t v64; // r12
  __int64 v65; // rdx
  BOOL v67; // r14d
  BOOL v68; // ebx
  int v69; // eax
  ITEMIDLIST *v70; // rdx
  int v71; // eax
  const struct _ITEMIDLIST_RELATIVE *v72; // rdx
  struct IShellFolder2 *v73; // rcx
  CRegFolder *v74; // rcx
  char v75; // al
  char v76; // al
  LPMALLOC v77; // rdi
  HRESULT (__stdcall *QueryInterface)(IMalloc *, const IID *const, void **); // rbx
  int v79; // r15d
  LPITEMIDLIST v80; // rbx
  struct DELEGATEITEMID *v81; // rax
  CRegFolder *v82; // rcx
  unsigned __int8 OrderPure; // r12
  struct DELEGATEITEMID *v84; // rax
  int v85; // r12d
  char v86; // al
  char v87; // al
  LPITEMIDLIST v88; // rdi
  LPVOID v89; // rcx
  char *v90; // rdx
  __int64 v91; // rax
  unsigned int v92; // eax
  char *v93; // rdx
  __int64 v94; // rax
  __int64 v95; // rax
  int v96; // r12d
  unsigned __int16 **v97; // rax
  unsigned __int16 **v98; // rax
  void *v99; // rax
  LPMALLOC v100; // rcx
  char *v101; // r14
  int v102; // eax
  void *Src; // [rsp+38h] [rbp-81h] BYREF
  __int64 v105; // [rsp+40h] [rbp-79h]
  int v106; // [rsp+48h] [rbp-71h]
  LPMALLOC ppMalloc; // [rsp+50h] [rbp-69h] BYREF
  unsigned int cb_low; // [rsp+58h] [rbp-61h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-59h] BYREF
  struct _GUID Buf1; // [rsp+68h] [rbp-51h] BYREF
  __int128 v111; // [rsp+78h] [rbp-41h] BYREF
  int v112; // [rsp+88h] [rbp-31h]
  VARIANT var2; // [rsp+90h] [rbp-29h] BYREF
  VARIANT var1; // [rsp+A8h] [rbp-11h] BYREF

  Src = a3;
  v105 = a2;
  v6 = this;
  if ( !a3 || !a4 )
    return 2147942487LL;
  Buf1 = 0;
  v7 = 0;
  if ( !*((_QWORD *)this + 17) )
  {
    v8 = (struct IUnknown *)*((_QWORD *)this + 18);
    *((_QWORD *)this + 17) = 0;
    if ( v8 )
    {
      if ( _GetIDListFromObjectWorker(v8, (struct _ITEMIDLIST_ABSOLUTE **)this + 17) < 0 )
      {
        ppMalloc = 0;
        if ( _GetItemFromObjectWorker(v8, &GUID_1079acfc_29bd_11d3_8e0d_00c04f6837d5, (void **)&ppMalloc) >= 0 )
        {
          ((void (__fastcall *)(LPMALLOC, char *))ppMalloc->lpVtbl->Free)(ppMalloc, (char *)v6 + 136);
          ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
        }
      }
    }
  }
  if ( ((v9 = (_WORD *)*((_QWORD *)v6 + 17)) != 0 && *v9
     || (v10 = *((_QWORD *)v6 + 18)) != 0
     && (int)IUnknown_GetClassID(v10, &Buf1) >= 0
     && memcmp_0(&Buf1, &CLSID_ShellDesktop, 0x10u))
    && (!a3->mkid.cb || !*(_WORD *)a4) )
  {
    return 2147942487LL;
  }
  cb = a3->mkid.cb;
  v12 = 2;
  if ( (unsigned int)cb < 3 )
    goto LABEL_119;
  v13 = a3->mkid.abID[0];
  if ( v13 != *((_BYTE *)v6 + 288) )
    goto LABEL_159;
  if ( cb >= (unsigned __int64)*((unsigned __int16 *)v6 + 158) + 20 )
    goto LABEL_15;
  v69 = IsDelegateRegId(a3);
  v70 = a3;
  if ( !v69 )
    v70 = 0;
  if ( v70 )
  {
LABEL_15:
    if ( (unsigned int)cb <= 7 )
      goto LABEL_17;
  }
  else
  {
LABEL_159:
    if ( !*((_DWORD *)v6 + 79) || (v75 = *((_BYTE *)v6 + 320)) == 0 || v13 != v75 || (unsigned int)cb < 0x14 )
    {
LABEL_119:
      v7 = *((_DWORD *)v6 + 64);
      goto LABEL_29;
    }
  }
  v14 = *(unsigned __int16 *)((char *)&a3[1].mkid.cb + 1);
  if ( cb >= v14 + 38 )
  {
    Buf1 = *(struct _GUID *)((char *)&a3[2].mkid.cb + v14);
    if ( !memcmp_0(&Buf1, qword_1807187A0, 0x10u) )
    {
      v7 = 2;
      goto LABEL_29;
    }
  }
LABEL_17:
  v15 = a3->mkid.cb;
  if ( (unsigned int)v15 > 7
    && (v16 = *(unsigned __int16 *)((char *)&a3[1].mkid.cb + 1), v15 >= v16 + 38)
    && (Buf1 = *(struct _GUID *)((char *)&a3[2].mkid.cb + v16), !memcmp_0(&Buf1, qword_1807187A0, 0x10u)) )
  {
    v18 = (struct _GUID *)((char *)&a3[7].mkid.cb + *(unsigned __int16 *)((char *)&a3[1].mkid.cb + 1) + 1);
  }
  else
  {
    if ( v13 == *((_BYTE *)v6 + 320) )
      v17 = a3;
    else
      v17 = (ITEMIDLIST *)((char *)a3 + *((unsigned int *)v6 + 79));
    v18 = (struct _GUID *)((char *)&v17[1].mkid.cb + 1);
  }
  Buf1 = *v18;
  v19 = (unsigned int)(*((_DWORD *)v6 + 74) - 1);
  if ( (int)v19 < 0 )
  {
LABEL_27:
    if ( (_DWORD)v19 == -1 )
      v7 = 1;
  }
  else
  {
    while ( 1 )
    {
      v20 = *(_QWORD **)(*((_QWORD *)v6 + 38) + 48 * v19);
      v21 = *(_QWORD *)&Buf1.Data1 - *v20;
      if ( *(_QWORD *)&Buf1.Data1 == *v20 )
        v21 = *(_QWORD *)Buf1.Data4 - v20[1];
      if ( !v21 )
        break;
      v19 = (unsigned int)(v19 - 1);
      if ( (int)v19 < 0 )
        goto LABEL_27;
    }
  }
LABEL_29:
  v22 = *(unsigned __int16 *)a4;
  if ( (unsigned int)v22 < 3 )
  {
LABEL_124:
    v12 = *((_DWORD *)v6 + 64);
    goto LABEL_46;
  }
  v23 = *((_BYTE *)a4 + 2);
  if ( v23 != *((_BYTE *)v6 + 288) )
    goto LABEL_163;
  if ( v22 < (unsigned __int64)*((unsigned __int16 *)v6 + 158) + 20 )
  {
    v71 = IsDelegateRegId(a4);
    v72 = a4;
    if ( !v71 )
      v72 = 0;
    if ( !v72 )
    {
LABEL_163:
      if ( !*((_DWORD *)v6 + 79) )
        goto LABEL_124;
      v76 = *((_BYTE *)v6 + 320);
      if ( !v76 || v23 != v76 || (unsigned int)v22 < 0x14 )
        goto LABEL_124;
LABEL_33:
      v24 = *((unsigned __int16 *)a4 + 2);
      if ( v22 >= v24 + 38 )
      {
        Buf1 = *(struct _GUID *)((char *)a4 + v24 + 6);
        if ( !memcmp_0(&Buf1, qword_1807187A0, 0x10u) )
          goto LABEL_46;
      }
      goto LABEL_34;
    }
  }
  if ( (unsigned int)v22 > 7 )
    goto LABEL_33;
LABEL_34:
  v25 = *(unsigned __int16 *)a4;
  if ( (unsigned int)v25 > 7
    && (v26 = *((unsigned __int16 *)a4 + 2), v25 >= v26 + 38)
    && (Buf1 = *(struct _GUID *)((char *)a4 + v26 + 6), !memcmp_0(&Buf1, qword_1807187A0, 0x10u)) )
  {
    v28 = (struct _GUID *)((char *)a4 + *((unsigned __int16 *)a4 + 2) + 22);
  }
  else
  {
    if ( v23 == *((_BYTE *)v6 + 320) )
      v27 = a4;
    else
      v27 = (const struct _ITEMIDLIST_RELATIVE *)((char *)a4 + *((unsigned int *)v6 + 79));
    v28 = (struct _GUID *)((char *)v27 + 4);
  }
  Buf1 = *v28;
  v29 = (unsigned int)(*((_DWORD *)v6 + 74) - 1);
  if ( (int)v29 < 0 )
  {
LABEL_44:
    if ( (_DWORD)v29 == -1 )
    {
      v12 = 1;
      goto LABEL_46;
    }
  }
  else
  {
    while ( 1 )
    {
      v30 = *(_QWORD **)(*((_QWORD *)v6 + 38) + 48 * v29);
      v31 = *(_QWORD *)&Buf1.Data1 - *v30;
      if ( *(_QWORD *)&Buf1.Data1 == *v30 )
        v31 = *(_QWORD *)Buf1.Data4 - v30[1];
      if ( !v31 )
        break;
      v29 = (unsigned int)(v29 - 1);
      if ( (int)v29 < 0 )
        goto LABEL_44;
    }
  }
  v12 = 0;
LABEL_46:
  v106 = v7 - v12;
  if ( v7 == v12 && v7 == *((_DWORD *)v6 + 64) )
    return (*(__int64 (__fastcall **)(_QWORD, __int64, ITEMIDLIST *, const struct _ITEMIDLIST_RELATIVE *))(**((_QWORD **)v6 + 18) + 56LL))(
             *((_QWORD *)v6 + 18),
             v105,
             a3,
             a4);
  v32 = *((_DWORD *)v6 + 78);
  if ( v32 == 2 )
  {
    v67 = 0;
    ppMalloc = (LPMALLOC)ILCloneFirst(a3);
    if ( ppMalloc )
    {
      cb_low = 541065216;
      if ( (int)CRegFolder::GetAttributesOf(v6, 1u, (const struct _ITEMID_CHILD *const *)&ppMalloc, &cb_low) >= 0 )
        v67 = cb_low == 0x20000000;
      CoTaskMemFree(ppMalloc);
    }
    v68 = 0;
    ppMalloc = (LPMALLOC)ILCloneFirst((LPCITEMIDLIST)a4);
    if ( ppMalloc )
    {
      cb_low = 541065216;
      if ( (int)CRegFolder::GetAttributesOf(v6, 1u, (const struct _ITEMID_CHILD *const *)&ppMalloc, &cb_low) >= 0 )
        v68 = cb_low == 0x20000000;
      CoTaskMemFree(ppMalloc);
    }
    if ( v67 )
    {
      if ( !v68 )
        goto LABEL_110;
    }
    else if ( v68 )
    {
LABEL_110:
      v33 = 2 * !v67 - 1;
      goto LABEL_111;
    }
    v73 = (struct IShellFolder2 *)v6;
    if ( v6 == (CRegFolder *)40 )
      v73 = 0;
    v33 = (__int16)CompareIDsImpl(v73, v105, (const struct _ITEMIDLIST_RELATIVE *)a3, a4);
LABEL_111:
    v59 = v33 < 0;
    if ( v33 )
    {
LABEL_112:
      if ( v59 )
        return 0xFFFF;
      else
        return v33 > 0;
    }
    goto LABEL_50;
  }
  if ( v32 == 4 )
  {
    v74 = v6;
    if ( v6 == (CRegFolder *)40 )
      v74 = 0;
    v33 = CompareIDsAlphabetical(v74, (unsigned __int16)v105, a3, a4);
    goto LABEL_111;
  }
LABEL_50:
  v33 = 0;
  v34 = a3->mkid.cb;
  if ( (unsigned int)v34 < 3 )
    goto LABEL_132;
  v35 = a3->mkid.abID[0];
  if ( v35 == *((_BYTE *)v6 + 288) )
  {
    v36 = (CRegFolder *)(*((unsigned __int16 *)v6 + 158) + 20LL);
    if ( v34 >= (unsigned __int64)v36 || CRegFolder::_IsDelegate(v36, (const struct IDLREGITEM *)a3) )
    {
      v37 = a3;
      goto LABEL_54;
    }
  }
  if ( *((_DWORD *)v6 + 79) && (v86 = *((_BYTE *)v6 + 320)) != 0 && v35 == v86 && (unsigned int)v34 >= 0x14 )
    v37 = a3;
  else
LABEL_132:
    v37 = 0;
LABEL_54:
  v38 = *(unsigned __int16 *)a4;
  if ( (unsigned int)v38 < 3 )
  {
LABEL_135:
    v41 = 0;
    goto LABEL_58;
  }
  v39 = *((_BYTE *)a4 + 2);
  if ( v39 != *((_BYTE *)v6 + 288)
    || (v40 = (CRegFolder *)(*((unsigned __int16 *)v6 + 158) + 20LL), v38 < (unsigned __int64)v40)
    && !CRegFolder::_IsDelegate(v40, a4) )
  {
    if ( *((_DWORD *)v6 + 79) )
    {
      v87 = *((_BYTE *)v6 + 320);
      if ( v87 )
      {
        if ( v39 == v87 && (unsigned int)v38 >= 0x14 )
        {
          v41 = a4;
          goto LABEL_58;
        }
      }
    }
    goto LABEL_135;
  }
  v41 = a4;
LABEL_58:
  v42 = -2147024882;
  if ( !v37 || !v41 )
    goto LABEL_80;
  v43 = *(unsigned __int16 *)v41;
  if ( (unsigned int)v43 > 7
    && (v44 = *((unsigned __int16 *)v41 + 2), v43 >= v44 + 38)
    && (v101 = (char *)v41 + v44,
        Buf1 = *(struct _GUID *)((char *)v41 + v44 + 6),
        !memcmp_0(&Buf1, qword_1807187A0, 0x10u)) )
  {
    v46 = v101 + 22;
  }
  else
  {
    if ( *((_BYTE *)v41 + 2) == *((_BYTE *)v6 + 320) )
      v45 = v41;
    else
      v45 = (const struct _ITEMIDLIST_RELATIVE *)((char *)v41 + *((unsigned int *)v6 + 79));
    v46 = (char *)v45 + 4;
  }
  v47 = v37->mkid.cb;
  if ( (unsigned int)v47 > 7
    && (v48 = *(unsigned __int16 *)((char *)&v37[1].mkid.cb + 1), v47 >= v48 + 38)
    && (ppMalloc = (LPMALLOC)((char *)v37 + v48),
        Buf1 = *(struct _GUID *)((char *)&v37[2].mkid.cb + v48),
        !memcmp_0(&Buf1, qword_1807187A0, 0x10u)) )
  {
    v50 = (char *)&ppMalloc[2].lpVtbl + 6;
  }
  else
  {
    if ( v37->mkid.abID[0] == *((_BYTE *)v6 + 320) )
      v49 = v37;
    else
      v49 = (ITEMIDLIST *)((char *)v37 + *((unsigned int *)v6 + 79));
    v50 = (char *)&v49[1].mkid.cb + 1;
  }
  v33 = memcmp_0(v50, v46, 0x10u);
  cb_low = v33;
  if ( v33 )
  {
    if ( (v105 & 0x10000000) == 0 )
    {
      v81 = CRegFolder::_IsDelegate(v51, (const struct IDLREGITEM *)v37);
      OrderPure = 0x80;
      if ( v81 )
      {
        v90 = (char *)v81 + v81->cbInner;
        v91 = *(_QWORD *)(v90 + 22) - *(_QWORD *)&CLSID_RemovableDrivesFolder.Data1;
        if ( !v91 )
          v91 = *(_QWORD *)(v90 + 30) - *(_QWORD *)CLSID_RemovableDrivesFolder.Data4;
        if ( v91 )
        {
          v82 = (CRegFolder *)(*(_QWORD *)(v90 + 22) - *(_QWORD *)&CLSID_FrequentPlacesFolder.Data1);
          if ( !v82 )
            v82 = (CRegFolder *)(*(_QWORD *)(v90 + 30) - *(_QWORD *)CLSID_FrequentPlacesFolder.Data4);
          v92 = 128;
          if ( !v82 )
            v92 = 69;
          cb_low = v92;
        }
        else
        {
          LOBYTE(cb_low) = 86;
        }
      }
      else
      {
        cb_low = LOBYTE(v37[1].mkid.cb);
        if ( (unsigned __int8)cb_low <= 0x40u )
          LOBYTE(cb_low) = CRegFolder::_GetOrderPure((CRegFolder *)((char *)v6 - 40), (const struct IDLREGITEM *)v37);
      }
      v84 = CRegFolder::_IsDelegate(v82, v41);
      if ( v84 )
      {
        v93 = (char *)v84 + v84->cbInner;
        v94 = *(_QWORD *)(v93 + 22) - *(_QWORD *)&CLSID_RemovableDrivesFolder.Data1;
        if ( !v94 )
          v94 = *(_QWORD *)(v93 + 30) - *(_QWORD *)CLSID_RemovableDrivesFolder.Data4;
        if ( v94 )
        {
          v95 = *(_QWORD *)(v93 + 22) - *(_QWORD *)&CLSID_FrequentPlacesFolder.Data1;
          if ( !v95 )
            v95 = *(_QWORD *)(v93 + 30) - *(_QWORD *)CLSID_FrequentPlacesFolder.Data4;
          if ( !v95 )
            OrderPure = 69;
        }
        else
        {
          OrderPure = 86;
        }
      }
      else
      {
        OrderPure = *((_BYTE *)v41 + 3);
        if ( OrderPure <= 0x40u )
          OrderPure = CRegFolder::_GetOrderPure((CRegFolder *)((char *)v6 - 40), v41);
      }
      v85 = (unsigned __int8)cb_low - OrderPure;
      if ( v85 )
        goto LABEL_179;
      cb_low = CRegFolder::_ReqItemIndex((CRegFolder *)((char *)v6 - 40), (const struct IDLREGITEM *)v37);
      v96 = CRegFolder::_ReqItemIndex((CRegFolder *)((char *)v6 - 40), v41);
      if ( cb_low == -1 && v96 == -1 )
      {
        ppMalloc = 0;
        pv = 0;
        v97 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&ppMalloc);
        CRegFolder::_GetDisplayName((struct IShellItem2 *)v6 - 5, (const struct IDLREGITEM *)v37, 0, v97);
        v98 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pv);
        CRegFolder::_GetDisplayName((struct IShellItem2 *)v6 - 5, v41, 0, v98);
        v99 = pv;
        v100 = ppMalloc;
        if ( ppMalloc && pv )
        {
          v85 = StrCmpLogicalRestricted((PCWSTR)ppMalloc, (PCWSTR)pv);
          v100 = ppMalloc;
          v99 = pv;
        }
        else
        {
          v85 = 0;
        }
        if ( v99 )
        {
          CoTaskMemFree(v99);
          v100 = ppMalloc;
        }
        if ( v100 )
          CoTaskMemFree(v100);
      }
      else
      {
        v85 = v96 - cb_low;
      }
      if ( v85 )
LABEL_179:
        v33 = v85;
    }
    goto LABEL_80;
  }
  p_cb = 0;
  pv = 0;
  if ( (unsigned int)v47 > 7 )
  {
    v53 = *(unsigned __int16 *)((char *)&v37[1].mkid.cb + 1);
    if ( v47 >= v53 + 38 )
    {
      Buf1 = *(struct _GUID *)((char *)&v37[2].mkid.cb + v53);
      v102 = memcmp_0(&Buf1, qword_1807187A0, 0x10u);
      p_cb = (unsigned __int16 *)pv;
      if ( !v102 )
        p_cb = &v37->mkid.cb;
      pv = p_cb;
    }
    else
    {
      p_cb = (unsigned __int16 *)pv;
    }
  }
  v54 = 0;
  v55 = *(unsigned __int16 *)v41;
  if ( (unsigned int)v55 > 7 )
  {
    v56 = *((unsigned __int16 *)v41 + 2);
    if ( v55 >= v56 + 38 )
    {
      Buf1 = *(struct _GUID *)((char *)v41 + v56 + 6);
      if ( !memcmp_0(&Buf1, qword_1807187A0, 0x10u) )
        v54 = v41;
      p_cb = (unsigned __int16 *)pv;
    }
  }
  if ( p_cb )
  {
    if ( !v54 )
    {
      v58 = 1;
      v33 = 1;
      v57 = a4;
      goto LABEL_82;
    }
    ppMalloc = 0;
    Buf1 = *(struct _GUID *)((char *)p_cb + p_cb[2] + 22);
    if ( (int)CRegFolder::_CreateCachedDelegateFolder(
                (CRegFolder *)((char *)v6 - 40),
                &Buf1,
                (struct IShellFolder **)&ppMalloc,
                0) >= 0 )
    {
      if ( (v105 & 0x90000000) != 0 )
      {
        v57 = a4;
      }
      else
      {
        v77 = ppMalloc;
        v33 = 0;
        cb_low = 0;
        pv = 0;
        QueryInterface = ppMalloc->lpVtbl->QueryInterface;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
        v79 = ((__int64 (__fastcall *)(LPMALLOC, GUID *, LPVOID *))QueryInterface)(
                v77,
                &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1,
                &pv);
        if ( v79 < 0
          || (v111 = 0,
              v112 = 0,
              v79 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int128 *))(**((_QWORD **)v6 + 18) + 152LL))(
                      *((_QWORD *)v6 + 18),
                      (unsigned __int16)v105,
                      &v111),
              v79 < 0) )
        {
          v57 = a4;
        }
        else
        {
          v80 = ILCloneFirst((LPCITEMIDLIST)Src);
          *(_QWORD *)&Buf1.Data1 = v80;
          if ( v80 )
          {
            v57 = a4;
            v88 = ILCloneFirst((LPCITEMIDLIST)a4);
            v79 = -2147024882;
            if ( v88 )
              v79 = 0;
            if ( v79 >= 0 )
            {
              memset(&var1, 0, sizeof(var1));
              (*(void (__fastcall **)(LPVOID, LPITEMIDLIST, __int128 *, VARIANT *))(*(_QWORD *)pv + 136LL))(
                pv,
                v80,
                &v111,
                &var1);
              memset(&var2, 0, sizeof(var2));
              (*(void (__fastcall **)(LPVOID, LPITEMIDLIST, __int128 *, VARIANT *))(*(_QWORD *)pv + 136LL))(
                pv,
                v88,
                &v111,
                &var2);
              v33 = VariantCompare(&var1, &var2);
              cb_low = v33;
              VariantClear(&var2);
              VariantClear(&var1);
            }
            CoTaskMemFree(v88);
          }
          else
          {
            v79 = -2147024882;
            v57 = a4;
          }
          CoTaskMemFree(v80);
        }
        v89 = pv;
        if ( pv )
        {
          pv = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v89 + 16LL))(v89);
        }
        if ( v79 >= 0 )
          goto LABEL_198;
      }
      SHCompareIDs((struct IShellFolder *)ppMalloc, v105, (const struct _ITEMIDLIST_RELATIVE *)Src, v57, (int *)&cb_low);
      v33 = cb_low;
LABEL_198:
      ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
      goto LABEL_81;
    }
LABEL_80:
    v57 = a4;
LABEL_81:
    v58 = 1;
    goto LABEL_82;
  }
  v57 = a4;
  v58 = 1;
  if ( v54 )
    v33 = -1;
LABEL_82:
  v59 = v33 < 0;
  if ( v33 )
    goto LABEL_112;
  v33 = v106;
  v59 = v106 < 0;
  if ( v106 )
    goto LABEL_112;
  if ( v6 == (CRegFolder *)40 )
    v6 = 0;
  v60 = *(unsigned __int16 *)Src;
  v61 = (char *)Src + v60;
  v62 = (_WORD *)((char *)v57 + *(unsigned __int16 *)v57);
  if ( (char *)Src + v60 && *v61 )
  {
    if ( v62 && *v62 )
    {
      if ( (int)v60 + 2 >= (unsigned int)v60 )
      {
        v63 = (char *)CoTaskMemAlloc((unsigned int)(v60 + 2));
        if ( v63 )
        {
          v64 = 0;
          ppMalloc = 0;
          if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
          {
            v64 = ((__int64 (__fastcall *)(LPMALLOC, char *))ppMalloc->lpVtbl->GetSize)(ppMalloc, v63);
            ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
          }
          memset_0(v63, 0, v64);
          memcpy_0(v63, Src, v60);
          *(_WORD *)&v63[v60] = 0;
          Src = 0;
          v42 = (*(__int64 (__fastcall **)(CRegFolder *, char *, _QWORD, GUID *, void **))(*(_QWORD *)v6 + 40LL))(
                  v6,
                  v63,
                  0,
                  &GUID_000214e6_0000_0000_c000_000000000046,
                  &Src);
          if ( v42 >= 0 )
          {
            ppMalloc = 0;
            if ( (**(int (__fastcall ***)(void *, GUID *, LPMALLOC *))Src)(
                   Src,
                   &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1,
                   &ppMalloc) < 0 )
            {
              v65 = 0;
            }
            else
            {
              ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
              v65 = v105;
            }
            v42 = (*(__int64 (__fastcall **)(void *, unsigned __int64, _WORD *, _WORD *))(*(_QWORD *)Src + 56LL))(
                    Src,
                    v65 & 0xFFFFFFFFFFFF0000uLL,
                    v61,
                    v62);
            (*(void (__fastcall **)(void *))(*(_QWORD *)Src + 16LL))(Src);
          }
          CoTaskMemFree(v63);
        }
      }
    }
    else
    {
      return 1;
    }
  }
  else
  {
    if ( v62 && *v62 )
      v58 = 0;
    v42 = 0;
    if ( !v58 )
      return 0xFFFF;
  }
  return (unsigned int)v42;
}

```

## disassembly

```asm
0x18008b7b0  push    rbp
0x18008b7b2  push    rbx
0x18008b7b3  push    rsi
0x18008b7b4  push    rdi
0x18008b7b5  push    r12
0x18008b7b7  push    r13
0x18008b7b9  push    r14
0x18008b7bb  push    r15
0x18008b7bd  lea     rbp, [rsp-1Fh]
0x18008b7c2  sub     rsp, 0D8h
0x18008b7c9  mov     rax, cs:__security_cookie
0x18008b7d0  xor     rax, rsp
0x18008b7d3  mov     [rbp+57h+var_50], rax
0x18008b7d7  mov     r13, r9
0x18008b7da  mov     [rsp+110h+pidl], r9
0x18008b7df  mov     r12, r8
0x18008b7e2  mov     [rsp+110h+Src], r8
0x18008b7e7  mov     [rbp+57h+var_D0], rdx
0x18008b7eb  mov     rsi, rcx
0x18008b7ee  test    r8, r8
0x18008b7f1  jz      loc_18008C4DF
0x18008b7f7  test    r9, r9
0x18008b7fa  jz      loc_18008C4DF
0x18008b800  xorps   xmm0, xmm0
0x18008b803  movups  [rbp+57h+Buf1], xmm0
0x18008b807  xor     r14d, r14d
0x18008b80a  cmp     [rcx+88h], r14
0x18008b811  jnz     short loc_18008B82A
0x18008b813  mov     rdi, [rcx+90h]
0x18008b81a  mov     [rcx+88h], r14
0x18008b821  test    rdi, rdi
0x18008b824  jnz     loc_18008BF41
0x18008b82a  mov     rax, [rsi+88h]
0x18008b831  test    rax, rax
0x18008b834  jz      short loc_18008B83C
0x18008b836  cmp     [rax], r14w
0x18008b83a  jnz     short loc_18008B876
0x18008b83c  mov     rcx, [rsi+90h]
0x18008b843  test    rcx, rcx
0x18008b846  jz      short loc_18008B88C
0x18008b848  lea     rdx, [rbp+57h+Buf1]
0x18008b84c  call    cs:__imp_IUnknown_GetClassID
0x18008b853  nop     dword ptr [rax+rax+00h]
0x18008b858  test    eax, eax
0x18008b85a  js      short loc_18008B88C
0x18008b85c  mov     r8d, 10h; Size
0x18008b862  lea     rdx, CLSID_ShellDesktop; Buf2
0x18008b869  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18008b86d  call    memcmp_0
0x18008b872  test    eax, eax
0x18008b874  jz      short loc_18008B88C
0x18008b876  cmp     [r12], r14w
0x18008b87b  jz      loc_18008C4DF
0x18008b881  cmp     [r13+0], r14w
0x18008b886  jz      loc_18008C4DF
0x18008b88c  movzx   ebx, word ptr [r12]
0x18008b891  mov     r15d, 2
0x18008b897  cmp     ebx, 3
0x18008b89a  jb      loc_18008BED4
0x18008b8a0  movzx   edi, byte ptr [r12+2]
0x18008b8a6  cmp     dil, [rsi+120h]
0x18008b8ad  jnz     loc_18008BEC7
0x18008b8b3  movzx   ecx, word ptr [rsi+13Ch]
0x18008b8ba  add     rcx, 14h
0x18008b8be  cmp     rbx, rcx
0x18008b8c1  jb      loc_18008BEAD
0x18008b8c7  cmp     ebx, 7
0x18008b8ca  jbe     short loc_18008B8DF
0x18008b8cc  movzx   edx, word ptr [r12+4]
0x18008b8d2  lea     rcx, [rdx+26h]
0x18008b8d6  cmp     rbx, rcx
0x18008b8d9  jnb     loc_18008C045
0x18008b8df  movzx   eax, word ptr [r12]
0x18008b8e4  cmp     eax, 7
0x18008b8e7  jbe     short loc_18008B8FC
0x18008b8e9  movzx   edx, word ptr [r12+4]
0x18008b8ef  lea     rcx, [rdx+26h]
0x18008b8f3  cmp     rax, rcx
0x18008b8f6  jnb     loc_18008C0A2
0x18008b8fc  cmp     dil, [rsi+140h]
0x18008b903  jz      loc_18008C5FF
0x18008b909  mov     eax, [rsi+13Ch]
0x18008b90f  add     rax, r12
0x18008b912  add     rax, 4
0x18008b916  movups  xmm0, xmmword ptr [rax]
0x18008b919  movups  [rbp+57h+Buf1], xmm0
0x18008b91d  mov     edx, [rsi+128h]
0x18008b923  sub     edx, 1
0x18008b926  js      short loc_18008B964
0x18008b928  mov     r10, [rsi+130h]
0x18008b92f  mov     r9, qword ptr [rbp+57h+Buf1+8]
0x18008b933  mov     r11, qword ptr [rbp+57h+Buf1]
0x18008b937  nop     word ptr [rax+rax+00000000h]
0x18008b940  lea     rcx, [rdx+rdx*2]
0x18008b944  add     rcx, rcx
0x18008b947  mov     r8, [r10+rcx*8]
0x18008b94b  mov     rax, r11
0x18008b94e  sub     rax, [r8]
0x18008b951  jnz     short loc_18008B95A
0x18008b953  mov     rax, r9
0x18008b956  sub     rax, [r8+8]
0x18008b95a  test    rax, rax
0x18008b95d  jz      short loc_18008B96F
0x18008b95f  sub     edx, 1
0x18008b962  jns     short loc_18008B940
0x18008b964  cmp     edx, 0FFFFFFFFh
0x18008b967  jnz     short loc_18008B96F
0x18008b969  mov     r14d, 1
0x18008b96f  mov     eax, 120h
0x18008b974  mov     rcx, rsi
0x18008b977  movzx   ebx, word ptr [r13+0]
0x18008b97c  cmp     ebx, 3
0x18008b97f  jb      loc_18008BF09
0x18008b985  movzx   edi, byte ptr [r13+2]
0x18008b98a  cmp     dil, [rcx+rax]
0x18008b98e  jnz     loc_18008BEFC
0x18008b994  movzx   ecx, word ptr [rsi+13Ch]
0x18008b99b  add     rcx, 14h
0x18008b99f  cmp     rbx, rcx
0x18008b9a2  jb      loc_18008BEE0
0x18008b9a8  cmp     ebx, 7
0x18008b9ab  jbe     short loc_18008B9BF
0x18008b9ad  movzx   edx, word ptr [r13+4]
0x18008b9b2  lea     rcx, [rdx+26h]
0x18008b9b6  cmp     rbx, rcx
0x18008b9b9  jnb     loc_18008C075
0x18008b9bf  movzx   eax, word ptr [r13+0]
0x18008b9c4  cmp     eax, 7
0x18008b9c7  jbe     short loc_18008B9DB
0x18008b9c9  movzx   edx, word ptr [r13+4]
0x18008b9ce  lea     rcx, [rdx+26h]
0x18008b9d2  cmp     rax, rcx
0x18008b9d5  jnb     loc_18008C0DC
0x18008b9db  cmp     dil, [rsi+140h]
0x18008b9e2  jz      loc_18008C607
0x18008b9e8  mov     eax, [rsi+13Ch]
0x18008b9ee  add     rax, r13
0x18008b9f1  add     rax, 4
0x18008b9f5  movups  xmm0, xmmword ptr [rax]
0x18008b9f8  movups  [rbp+57h+Buf1], xmm0
0x18008b9fc  mov     edx, [rsi+128h]
0x18008ba02  sub     edx, 1
0x18008ba05  js      short loc_18008BA44
0x18008ba07  mov     r10, [rsi+130h]
0x18008ba0e  mov     r9, qword ptr [rbp+57h+Buf1+8]
0x18008ba12  mov     r11, qword ptr [rbp+57h+Buf1]
0x18008ba16  nop     word ptr [rax+rax+00000000h]
0x18008ba20  lea     rcx, [rdx+rdx*2]
0x18008ba24  add     rcx, rcx
0x18008ba27  mov     r8, [r10+rcx*8]
0x18008ba2b  mov     rax, r11
0x18008ba2e  sub     rax, [r8]
0x18008ba31  jnz     short loc_18008BA3A
0x18008ba33  mov     rax, r9
0x18008ba36  sub     rax, [r8+8]
0x18008ba3a  test    rax, rax
0x18008ba3d  jz      short loc_18008BA4D
0x18008ba3f  sub     edx, 1
0x18008ba42  jns     short loc_18008BA20
0x18008ba44  cmp     edx, 0FFFFFFFFh
0x18008ba47  jz      loc_18008BEA0
0x18008ba4d  xor     r15d, r15d
0x18008ba50  mov     edi, 1
0x18008ba55  mov     eax, r14d
0x18008ba58  sub     eax, r15d
0x18008ba5b  mov     [rbp+57h+var_C8], eax
0x18008ba5e  jnz     short loc_18008BA6D
0x18008ba60  cmp     r14d, [rsi+100h]
0x18008ba67  jz      loc_18008BF15
0x18008ba6d  mov     eax, [rsi+138h]
0x18008ba73  cmp     eax, 2
0x18008ba76  jz      loc_18008BDD1
0x18008ba7c  cmp     eax, 4
0x18008ba7f  jz      loc_18008C01E
0x18008ba85  xor     r14d, r14d
0x18008ba88  movzx   edi, word ptr [r12]
0x18008ba8d  cmp     edi, 3
0x18008ba90  jb      loc_18008BFC1
0x18008ba96  movzx   r15d, byte ptr [r12+2]
0x18008ba9c  cmp     r15b, [rsi+120h]
0x18008baa3  jnz     loc_18008BFB4
0x18008baa9  movzx   ecx, word ptr [rsi+13Ch]
0x18008bab0  add     rcx, 14h; this
0x18008bab4  cmp     rdi, rcx
0x18008bab7  jb      loc_18008BFA3
0x18008babd  mov     r15, r12
0x18008bac0  movzx   edi, word ptr [r13+0]
0x18008bac5  cmp     edi, 3
0x18008bac8  jb      loc_18008BFE7
0x18008bace  movzx   r12d, byte ptr [r13+2]
0x18008bad3  cmp     r12b, [rsi+120h]
0x18008bada  jnz     loc_18008BFDA
0x18008bae0  movzx   ecx, word ptr [rsi+13Ch]
0x18008bae7  add     rcx, 14h; this
0x18008baeb  cmp     rdi, rcx
0x18008baee  jb      loc_18008BFC9
0x18008baf4  mov     rdi, r13
0x18008baf7  mov     r13d, 8007000Eh
0x18008bafd  test    r15, r15
0x18008bb00  jz      loc_18008BC04
0x18008bb06  test    rdi, rdi
0x18008bb09  jz      loc_18008BC04
0x18008bb0f  movzx   eax, word ptr [rdi]
0x18008bb12  cmp     eax, 7
0x18008bb15  jbe     short loc_18008BB28
0x18008bb17  movzx   edx, word ptr [rdi+4]
0x18008bb1b  lea     rcx, [rdx+26h]
0x18008bb1f  cmp     rax, rcx
0x18008bb22  jnb     loc_18008C624
0x18008bb28  movzx   eax, byte ptr [rsi+140h]
0x18008bb2f  cmp     [rdi+2], al
0x18008bb32  jz      loc_18008C614
0x18008bb38  mov     eax, [rsi+13Ch]
0x18008bb3e  add     rax, rdi
0x18008bb41  lea     r14, [rax+4]
0x18008bb45  movzx   r12d, word ptr [r15]
0x18008bb49  cmp     r12d, 7
0x18008bb4d  jbe     short loc_18008BB61
0x18008bb4f  movzx   edx, word ptr [r15+4]
0x18008bb54  lea     rcx, [rdx+26h]
0x18008bb58  cmp     r12, rcx
0x18008bb5b  jnb     loc_18008C658
0x18008bb61  movzx   eax, byte ptr [rsi+140h]
0x18008bb68  cmp     [r15+2], al
0x18008bb6c  jz      loc_18008C61C
0x18008bb72  mov     eax, [rsi+13Ch]
0x18008bb78  add     rax, r15
0x18008bb7b  lea     rcx, [rax+4]; Buf1
0x18008bb7f  mov     r8d, 10h; Size
0x18008bb85  mov     rdx, r14; Buf2
0x18008bb88  call    memcmp_0
0x18008bb8d  mov     r14d, eax
0x18008bb90  mov     [rbp+57h+var_B8], eax
0x18008bb93  test    eax, eax
0x18008bb95  jnz     short loc_18008BBF6
0x18008bb97  xor     edx, edx
0x18008bb99  mov     [rbp+57h+pv], rdx
0x18008bb9d  cmp     r12d, 7
0x18008bba1  jbe     short loc_18008BBB9
0x18008bba3  movzx   edx, word ptr [r15+4]
0x18008bba8  lea     rcx, [rdx+26h]
0x18008bbac  cmp     r12, rcx
0x18008bbaf  jnb     loc_18008C693
0x18008bbb5  mov     rdx, [rbp+57h+pv]
0x18008bbb9  xor     r15d, r15d
0x18008bbbc  movzx   eax, word ptr [rdi]
0x18008bbbf  cmp     eax, 7
0x18008bbc2  jbe     short loc_18008BBD6
0x18008bbc4  movzx   r9d, word ptr [rdi+4]
0x18008bbc9  lea     rcx, [r9+26h]
0x18008bbcd  cmp     rax, rcx
0x18008bbd0  jnb     loc_18008C6C6
0x18008bbd6  test    rdx, rdx
0x18008bbd9  jnz     loc_18008C182
0x18008bbdf  mov     r12, [rsp+110h+pidl]
0x18008bbe4  mov     edx, 1
0x18008bbe9  test    r15, r15
0x18008bbec  jz      short loc_18008BC0E
0x18008bbee  mov     r14d, 0FFFFFFFFh
0x18008bbf4  jmp     short loc_18008BC0E
0x18008bbf6  test    [rbp+57h+var_D0], 10000000h
0x18008bbfe  jz      loc_18008C269
0x18008bc04  mov     r12, [rsp+110h+pidl]
0x18008bc09  mov     edx, 1
0x18008bc0e  test    r14d, r14d
0x18008bc11  jnz     loc_18008BE8D
0x18008bc17  mov     r14d, [rbp+57h+var_C8]
0x18008bc1b  test    r14d, r14d
0x18008bc1e  jnz     loc_18008BE8D
0x18008bc24  lea     rcx, [rsi-28h]
0x18008bc28  xor     eax, eax
0x18008bc2a  test    rcx, rcx
0x18008bc2d  cmovz   rsi, rax
0x18008bc31  mov     rax, [rsp+110h+Src]
0x18008bc36  movzx   ebx, word ptr [rax]
0x18008bc39  lea     rdi, [rbx+rax]
0x18008bc3d  movzx   r14d, word ptr [r12]
0x18008bc42  add     r14, r12
0x18008bc45  test    rdi, rdi
0x18008bc48  jz      loc_18008C115
0x18008bc4e  cmp     word ptr [rdi], 0
0x18008bc52  jz      loc_18008C115
0x18008bc58  test    r14, r14
0x18008bc5b  jz      loc_18008C322
0x18008bc61  cmp     word ptr [r14], 0
0x18008bc66  jz      loc_18008C322
0x18008bc6c  lea     edx, [rbx+2]
0x18008bc6f  cmp     edx, ebx
0x18008bc71  jb      loc_18008BDAD
0x18008bc77  mov     ecx, edx; cb
0x18008bc79  call    cs:__imp_CoTaskMemAlloc
0x18008bc80  nop     dword ptr [rax+rax+00h]
0x18008bc85  mov     r15, rax
0x18008bc88  test    rax, rax
0x18008bc8b  jz      loc_18008BDAD
0x18008bc91  xor     r12d, r12d
0x18008bc94  mov     [rbp+57h+ppMalloc], r12
0x18008bc98  lea     rdx, [rbp+57h+ppMalloc]; ppMalloc
0x18008bc9c  mov     ecx, 1; dwMemContext
0x18008bca1  call    cs:__imp_CoGetMalloc
  ... truncated ...
```
