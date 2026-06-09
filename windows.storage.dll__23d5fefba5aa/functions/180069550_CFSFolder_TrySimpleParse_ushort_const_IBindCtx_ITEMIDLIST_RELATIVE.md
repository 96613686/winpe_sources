# CFSFolder::TrySimpleParse(ushort const *,IBindCtx *,_ITEMIDLIST_RELATIVE * *)

- ea: `0x180069550`
- end: `0x18006a8ae`
- name: `?TrySimpleParse@CFSFolder@@IEAAJPEBGPEAUIBindCtx@@PEAPEAU_ITEMIDLIST_RELATIVE@@@Z`
- size: `4958`
- prototype: `int(CFSFolder *__hidden this, const unsigned __int16 *, struct IBindCtx *, struct _ITEMIDLIST_RELATIVE **)`
- caller_count: `1`
- callee_count: `20`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800f1da0`

## callees

- `0x180038f80`
- `0x180049110`
- `0x180069550`
- `0x18006a8c0`
- `0x18006d910`
- `0x18008c740`
- `0x180096e60`
- `0x1800aeb90`
- `0x180107000`
- `0x18010ce70`
- `0x1801cff34`
- `0x180202b70`
- `0x18024d704`
- `0x18034591c`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x1803b2ea5`
- `0x1803b69b9`
- `0x1803b69c5`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180069726`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180069726`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsValidCharW` at `0x1800697e5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsValidCharW` at `0x1800697e5`
- `OLEAUT32!__imp_SysFreeString` at `0x18006a082`
- `OLEAUT32!__imp_SysFreeString` at `0x18006a082`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006981f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069a23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069a32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069db6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a072`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a12c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a564`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a686`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a69e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a6ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a878`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a88f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006981f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069a23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069a32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069db6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a072`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a12c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a564`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a686`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a69e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a6ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a878`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a88f`
- `SHCORE!__imp_ualstrlenW` at `0x18006a6e3`
- `SHCORE!__imp_ualstrlenW` at `0x18006a6e3`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x18006a3e1`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x18006a478`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x18006a3e1`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x18006a478`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x180069c6a`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x180069c6a`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHAnsiToUnicode` at `0x18006a836`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHAnsiToUnicode` at `0x18006a836`

## string_xrefs

- `0x180069622`: `Folders As Read Only`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CFSFolder::TrySimpleParse(
        CFSFolder *this,
        const unsigned __int16 *a2,
        struct IBindCtx *a3,
        LPVOID *a4)
{
  LPVOID *v4; // rsi
  struct IBindCtx *v5; // r12
  struct _ITEMIDLIST_RELATIVE *v8; // r15
  int v9; // ebx
  bool v10; // r13
  int v11; // ebx
  BSTR v12; // rcx
  PWSTR v13; // rax
  PWSTR v14; // r10
  unsigned __int64 v15; // rdx
  __int64 v16; // r9
  WCHAR *v17; // r8
  WCHAR v18; // ax
  WCHAR *v19; // rcx
  __int16 v20; // cx
  int v21; // r14d
  int v22; // esi
  __int16 *v23; // rbx
  __int64 v24; // rcx
  int IsValidCharW; // eax
  bool v26; // zf
  __int64 v28; // rcx
  __int64 v29; // rdx
  WCHAR *v30; // r8
  WCHAR v31; // ax
  WCHAR *v32; // rcx
  int v33; // eax
  int v34; // ebx
  void *v35; // r12
  unsigned __int16 *v36; // rdx
  int v37; // r8d
  __int64 v38; // rcx
  __int64 v39; // r15
  void *v40; // r13
  unsigned __int16 *v41; // rdx
  unsigned int v42; // esi
  __int64 v43; // rcx
  char *v44; // rax
  char *v45; // r14
  int v46; // r13d
  __int64 v47; // rcx
  __int16 *v48; // rdx
  __int64 v49; // r9
  char *v50; // r8
  __int16 v51; // ax
  char *v52; // rcx
  int v53; // ebx
  unsigned __int64 v54; // r8
  int v55; // ebx
  HRESULT v56; // ebx
  int v57; // esi
  BSTR v58; // r15
  struct _ITEMIDLIST_RELATIVE *v59; // r12
  int v60; // r14d
  void *v61; // rcx
  IPropertyBag *v62; // rcx
  unsigned __int16 *v63; // rbx
  unsigned __int16 v64; // dx
  unsigned __int16 *v65; // rsi
  __int64 v66; // r8
  unsigned int v67; // ecx
  unsigned __int64 v68; // r14
  unsigned __int16 v69; // ax
  int *v70; // r15
  int v71; // r12d
  unsigned __int16 *v72; // rcx
  unsigned __int16 *v73; // rbx
  unsigned __int16 v74; // r8
  unsigned __int16 *v75; // rdx
  __int64 v76; // r10
  unsigned int v77; // ecx
  unsigned __int64 v78; // rcx
  unsigned __int16 *v79; // rcx
  unsigned __int16 *v80; // rdx
  _WORD *v81; // rbx
  char *v82; // rsi
  __int64 v83; // rcx
  char *v84; // r14
  struct IShellFolder *v85; // rcx
  LPITEMIDLIST v86; // rax
  const struct _HIDDENITEMID *v87; // rbx
  USHORT cb; // ax
  unsigned __int16 *v89; // rdx
  __int64 v90; // r9
  unsigned int v91; // ecx
  unsigned __int64 v92; // rcx
  char *v93; // r9
  _BYTE *v94; // rcx
  unsigned __int64 v95; // rdx
  int v96; // r8d
  unsigned __int16 *v97; // r8
  unsigned __int16 *v98; // r9
  int v99; // ebx
  HRESULT v100; // ebx
  int v101; // ebx
  HRESULT StrAlloc; // ebx
  unsigned __int16 *v103; // r9
  __int64 v104; // r8
  __int64 v105; // rax
  __int64 v106; // rax
  __int64 v107; // rcx
  __int64 v108; // rcx
  __int64 v109; // rcx
  const CHAR *v110; // rbx
  unsigned __int64 v111; // r8
  __int64 v112; // rax
  __int16 v113; // r11
  const unsigned __int16 *v114; // rax
  bool v115; // [rsp+50h] [rbp-B0h]
  LPVOID v116; // [rsp+58h] [rbp-A8h] BYREF
  int v117; // [rsp+60h] [rbp-A0h]
  struct IBindCtx *v118; // [rsp+68h] [rbp-98h]
  struct _ITEMIDLIST_RELATIVE **v119; // [rsp+70h] [rbp-90h]
  struct CFSFolder *v120; // [rsp+78h] [rbp-88h]
  __int64 v121; // [rsp+80h] [rbp-80h]
  __int64 v122; // [rsp+88h] [rbp-78h]
  __int64 v123; // [rsp+90h] [rbp-70h]
  __int64 v124; // [rsp+98h] [rbp-68h] BYREF
  void *Src; // [rsp+A0h] [rbp-60h] BYREF
  IPropertyBag *propBag; // [rsp+A8h] [rbp-58h] BYREF
  struct IShellFolder *v127; // [rsp+B0h] [rbp-50h] BYREF
  BSTR value; // [rsp+B8h] [rbp-48h] BYREF
  LPVOID pv; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v130; // [rsp+C8h] [rbp-38h] BYREF
  int v131; // [rsp+D0h] [rbp-30h] BYREF
  int v132; // [rsp+D4h] [rbp-2Ch] BYREF
  _QWORD v133[3]; // [rsp+D8h] [rbp-28h] BYREF
  int v134; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v135; // [rsp+F4h] [rbp-Ch]
  __int128 v136; // [rsp+104h] [rbp+4h]
  __int64 v137; // [rsp+114h] [rbp+14h]
  __int16 v138; // [rsp+11Ch] [rbp+1Ch] BYREF
  __int16 v139; // [rsp+11Eh] [rbp+1Eh]
  __int16 v140; // [rsp+120h] [rbp+20h]
  char v141; // [rsp+324h] [rbp+224h] BYREF
  char v142[8]; // [rsp+340h] [rbp+240h] BYREF
  __int128 Buf1; // [rsp+348h] [rbp+248h] BYREF
  _QWORD v144[2]; // [rsp+360h] [rbp+260h] BYREF
  LPVOID v145; // [rsp+370h] [rbp+270h]
  LPVOID v146; // [rsp+378h] [rbp+278h]
  LPVOID v147; // [rsp+390h] [rbp+290h]
  __int64 v148; // [rsp+398h] [rbp+298h]
  __int64 v149; // [rsp+3A0h] [rbp+2A0h]
  __int64 v150; // [rsp+3A8h] [rbp+2A8h]
  const CHAR *v151; // [rsp+3B8h] [rbp+2B8h]
  int v152; // [rsp+3E0h] [rbp+2E0h]
  WCHAR pwszDst[278]; // [rsp+3E4h] [rbp+2E4h] BYREF
  int v154; // [rsp+610h] [rbp+510h] BYREF
  __int128 v155; // [rsp+614h] [rbp+514h]
  __int128 v156; // [rsp+624h] [rbp+524h]
  __int64 v157; // [rsp+634h] [rbp+534h]
  char v158; // [rsp+844h] [rbp+744h] BYREF

  v4 = a4;
  v119 = (struct _ITEMIDLIST_RELATIVE **)a4;
  v5 = a3;
  v118 = a3;
  v120 = this;
  v8 = 0;
  *a4 = 0;
  v130 = 0;
  v127 = 0;
  if ( a3 )
  {
    if ( ((int (__fastcall *)(struct IBindCtx *, const unsigned __int16 *, struct IShellFolder **))a3->lpVtbl->GetObjectParam)(
           a3,
           L"File System Bind Data",
           &v127) >= 0 )
    {
      v9 = ((__int64 (__fastcall *)(struct IShellFolder *, GUID *, __int64 *))v127->lpVtbl->QueryInterface)(
             v127,
             &GUID_01e18d10_4d8b_11d2_855d_006008059367,
             &v130);
      ((void (__fastcall *)(struct IShellFolder *))v127->lpVtbl->Release)(v127);
      if ( v9 >= 0 )
      {
        memset_0(&v134, 0, 0x268u);
        v124 = 0;
        v10 = 0;
        if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, __int64 *))v5->lpVtbl->GetObjectParam)(
               v5,
               L"Folders As Read Only",
               &v124) >= 0 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v124 + 16LL))(v124);
          if ( !(unsigned int)CFSFolder::_IsNetFolder(this) )
            v10 = 1;
        }
        v115 = v10;
        v11 = 0;
        v117 = 0;
        v124 = 0;
        if ( ((int (__fastcall *)(struct IBindCtx *, const unsigned __int16 *, __int64 *))v5->lpVtbl->GetObjectParam)(
               v5,
               L"NoValidateFilenameChars",
               &v124) >= 0 )
        {
          v11 = 1;
          v117 = 1;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v124 + 16LL))(v124);
        }
        v132 = 0;
        value = 0;
        if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, BSTR *))v5->lpVtbl->GetObjectParam)(
               v5,
               L"Folder Enum Mode",
               &value) >= 0 )
        {
          v12 = value;
          v132 = 0;
          if ( value )
          {
            v127 = 0;
            if ( (**(int (__fastcall ***)(BSTR, GUID *, struct IShellFolder **))value)(
                   value,
                   &GUID_6a9d9026_0e6e_464c_b000_42ecc07de673,
                   &v127) >= 0 )
            {
              ((void (__fastcall *)(struct IShellFolder *, int *))v127->lpVtbl->EnumObjects)(v127, &v132);
              ((void (__fastcall *)(struct IShellFolder *))v127->lpVtbl->Release)(v127);
            }
            v12 = value;
          }
          (*(void (__fastcall **)(BSTR))(*(_QWORD *)v12 + 16LL))(v12);
        }
        while ( 1 )
        {
          v138 = 0;
          if ( !a2 )
          {
            v21 = 0;
            goto LABEL_40;
          }
          v13 = StrChrW(a2, 0x5Cu);
          v14 = v13;
          if ( v13 )
          {
            if ( v13 <= a2 )
              goto LABEL_38;
            v15 = (int)(v13 - a2);
            if ( v15 > 0x7FFFFFFE )
            {
              v20 = 0;
              v138 = 0;
            }
            else
            {
              v16 = 260;
              v17 = (WCHAR *)&v138;
              do
              {
                if ( !v15 )
                  break;
                v18 = *a2;
                if ( !*a2 )
                  break;
                ++a2;
                *v17++ = v18;
                --v15;
                --v16;
              }
              while ( v16 );
              v19 = v17 - 1;
              if ( v16 )
                v19 = v17;
              *v19 = 0;
              v20 = v138;
            }
            a2 = v14 + 1;
            if ( !v14[1] )
              a2 = 0;
            v21 = 0;
            v131 = 0;
          }
          else
          {
            v28 = 2147483646;
            v29 = 260;
            v30 = (WCHAR *)&v138;
            do
            {
              if ( !v28 )
                break;
              v31 = *a2;
              if ( !*a2 )
                break;
              ++a2;
              *v30++ = v31;
              --v28;
              --v29;
            }
            while ( v29 );
            v32 = v30 - 1;
            if ( v29 )
              v32 = v30;
            *v32 = 0;
            v21 = -2147024774;
            if ( v29 )
              v21 = 0;
            v131 = v21;
            a2 = 0;
            if ( !v29 )
              goto LABEL_52;
            v20 = v138;
          }
          if ( !v11 )
          {
            if ( !v20 || v20 == 46 && (!v139 || !v140 && v139 == 46) )
            {
LABEL_37:
              v138 = 0;
LABEL_38:
              v21 = -2147024809;
              goto LABEL_39;
            }
            v22 = 1;
            v23 = &v138;
            while ( 1 )
            {
              v24 = (unsigned __int16)*v23;
              if ( !(_WORD)v24 )
                break;
              IsValidCharW = PathIsValidCharW(v24, 484);
              if ( !IsValidCharW || *v23 == 46 )
              {
                ++v23;
                if ( !IsValidCharW )
                {
                  v4 = (LPVOID *)v119;
                  goto LABEL_37;
                }
              }
              else
              {
                v22 = 0;
                ++v23;
              }
            }
            v26 = v22 == 0;
            v4 = (LPVOID *)v119;
            if ( !v26 )
              goto LABEL_37;
          }
LABEL_52:
          if ( v21 )
            goto LABEL_39;
          Src = 0;
          v116 = 0;
          if ( !a2 )
          {
            v133[0] = 16;
            v133[1] = 0;
            if ( ((int (__fastcall *)(struct IBindCtx *, _QWORD *))v5->lpVtbl->GetBindOptions)(v5, v133) >= 0
              && HIDWORD(v133[0]) == 2 )
            {
              v46 = 0;
            }
            else
            {
              v46 = 6;
            }
            if ( v115 )
              v46 |= 1u;
            memset_0(&v154, 0, 0x250u);
            if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v130 + 32LL))(v130, &v154) >= 0 )
            {
              v134 = v154;
              v135 = v155;
              v136 = v156;
              v137 = v157;
              v47 = 2147483646;
              v48 = (__int16 *)&v158;
              v49 = 14;
              v50 = &v141;
              do
              {
                if ( !v47 )
                  break;
                v51 = *v48;
                if ( !*v48 )
                  break;
                ++v48;
                *(_WORD *)v50 = v51;
                v50 += 2;
                --v47;
                --v49;
              }
              while ( v49 );
              v52 = v50 - 2;
              if ( v49 )
                v52 = v50;
              *(_WORD *)v52 = 0;
              propBag = 0;
              if ( (**(int (__fastcall ***)(__int64, GUID *, IPropertyBag **))v130)(
                     v130,
                     &GUID_3acf075f_71db_4afa_81f0_3fc4fdf2a5b8,
                     &propBag) >= 0 )
              {
                ((void (__fastcall *)(IPropertyBag *, char *))propBag->lpVtbl[1].AddRef)(propBag, v142);
                if ( ((int (__fastcall *)(IPropertyBag *, __int128 *))propBag->lpVtbl[1].Read)(propBag, &Buf1) >= 0 )
                {
                  v46 &= ~4u;
                  if ( !memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
                    v46 &= ~2u;
                }
                ((void (__fastcall *)(IPropertyBag *))propBag->lpVtbl->Release)(propBag);
              }
            }
            v127 = 0;
            pv = 0;
            v124 = 0;
            propBag = 0;
            if ( ((int (__fastcall *)(struct IBindCtx *, const unsigned __int16 *, IPropertyBag **))v5->lpVtbl->GetObjectParam)(
                   v5,
                   L"ParseOriginalItem",
                   &propBag) >= 0 )
            {
              v53 = ((__int64 (__fastcall *)(IPropertyBag *, GUID *, __int64 *))propBag->lpVtbl->QueryInterface)(
                      propBag,
                      &GUID_b3a4b685_b685_4805_99d9_5dead2873236,
                      &v124);
              ((void (__fastcall *)(IPropertyBag *))propBag->lpVtbl->Release)(propBag);
              if ( v53 >= 0 )
              {
                (*(void (__fastcall **)(__int64, _QWORD, struct IShellFolder **, LPVOID *))(*(_QWORD *)v124 + 32LL))(
                  v124,
                  0,
                  &v127,
                  &pv);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v124 + 16LL))(v124);
              }
            }
            value = 0;
            propBag = 0;
            v124 = 0;
            if ( ((int (__fastcall *)(struct IBindCtx *, const unsigned __int16 *, __int64 *))v5->lpVtbl->GetObjectParam)(
                   v5,
                   L"SHBindCtxPropertyBag",
                   &v124) >= 0 )
            {
              v55 = (**(__int64 (__fastcall ***)(__int64, GUID *, IPropertyBag **))v124)(
                      v124,
                      &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
                      &propBag);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v124 + 16LL))(v124);
              if ( v55 >= 0 )
              {
                v56 = PSPropertyBag_ReadBSTR(propBag, L"LocalizedResourceName", &value);
                ((void (__fastcall *)(IPropertyBag *))propBag->lpVtbl->Release)(propBag);
                if ( v56 >= 0 )
                {
                  v46 |= 1u;
                  goto LABEL_95;
                }
              }
            }
            v81 = pv;
            if ( pv )
            {
              v82 = 0;
              v83 = *(unsigned __int16 *)pv;
              if ( (unsigned int)v83 > 0xB )
              {
                if ( (*((_BYTE *)pv + 2) & 0x70) == 0x30 )
                {
                  v82 = (char *)pv;
                  v84 = (char *)pv;
                  goto LABEL_171;
                }
                if ( *(_DWORD *)((char *)pv + 6) == 1179862595 )
                {
                  if ( *((unsigned __int16 *)pv + 2) > (unsigned __int64)(v83 - 4) )
                    goto LABEL_192;
                  v82 = (char *)pv + 10;
                  if ( !IDListContainerIsConsistent((LPCITEMIDLIST)((char *)pv + 10), *((unsigned __int16 *)pv + 2))
                    || v113 != *(_WORD *)v82 + 6
                    || (unsigned __int16)(*(_WORD *)v82 + 6) < *(_WORD *)v82 )
                  {
                    goto LABEL_192;
                  }
                }
              }
              if ( !v82 )
                goto LABEL_192;
              v84 = v82;
LABEL_171:
              if ( *(_WORD *)v82 < 0xEu )
                goto LABEL_192;
              if ( !v81
                || !*v81
                || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::GetImpl'::`2'::impl)
                && *v81 < 2u )
              {
                goto LABEL_290;
              }
              v89 = 0;
              v54 = (unsigned __int16)*v81;
              v90 = *(unsigned __int16 *)((char *)v81 + v54 - 2);
              if ( (_WORD)v90 )
              {
                if ( v90 + 8 < v54 )
                {
                  v89 = (_WORD *)((char *)v81 + v90);
                  v91 = *(unsigned __int16 *)((char *)v81 + v90);
                  if ( v91 < 8
                    || HIWORD(*((_DWORD *)v89 + 1)) != 0xBEEF
                    || (unsigned int)v90 + v91 > (unsigned __int16)*v81 )
                  {
                    v89 = 0;
                  }
                }
              }
              v92 = (unsigned __int64)v81 + v54;
              if ( v89 )
              {
                while ( *((_DWORD *)v89 + 1) != -1091633148 )
                {
                  v54 = 0;
                  if ( (unsigned __int64)(v89 + 4) <= v92 )
                  {
                    v103 = (unsigned __int16 *)((char *)v89 + *v89);
                    if ( v103 == (unsigned __int16 *)v92 )
                      goto LABEL_201;
                    if ( (unsigned __int64)v103 <= v92 )
                    {
                      if ( (unsigned __int64)(v103 + 4) > v92
                        || HIWORD(*((_DWORD *)v103 + 1)) != 0xBEEF
                        || (unsigned __int64)v103 + *v103 > v92
                        || v103 < v89 + 4 )
                      {
                        goto LABEL_201;
                      }
                      v54 = (unsigned __int64)v89 + *v89;
                    }
                  }
                  v89 = (unsigned __int16 *)v54;
                  if ( !v54 )
                    goto LABEL_201;
                }
                v93 = v84 + 2;
LABEL_183:
                v94 = v82 + 14;
                if ( v82 == (char *)-14LL || (v95 = *(unsigned __int16 *)v82 - 14LL, v95 > 0x7FFFFFFF) )
                {
                  v96 = -2147024809;
                }
                else
                {
                  if ( *(_WORD *)v82 != 14 )
                  {
                    do
                    {
                      if ( !*v94 )
                        break;
                      ++v94;
                      --v95;
                    }
                    while ( v95 );
                  }
                  v96 = -2147024809;
                  if ( v95 )
                    v96 = 0;
                  v93 = v84 + 2;
                }
              }
              else
              {
LABEL_290:
              {
LABEL_201:
                v93 = v82 + 2;
                if ( (v82[2] & 0x34) != 0x34 )
                  goto LABEL_183;
              }
                v96 = UnalignedStringCbLengthW(
                        (const unsigned __int16 *)v82 + 7,
                        *(unsigned __int16 *)v82 - 14LL,
                        (unsigned __int64 *)v54);
              }
              if ( v96 < 0 )
              {
LABEL_192:
                v121 = 0;
                v122 = 0;
                v123 = 0;
                if ( DisplayNameOfAsBSTR(v127, (const struct _ITEMIDLIST_RELATIVE *)pv, 0, &value) >= 0 )
                  v46 |= 1u;
                goto LABEL_95;
              }
              if ( *v93 < 0 && !memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
              {
                v112 = ILFindHiddenIDOn(pv, 3203334147LL, 1);
                if ( v112 )
                {
                  Buf1 = *(_OWORD *)(v112 + 8);
                  v46 &= ~4u;
                }
              }
              CFileSysItemString::CFileSysItemString(
                (CFileSysItemString *)v144,
                v120,
                (const struct _ITEMIDLIST_RELATIVE *)pv,
                (const struct IDFOLDER *)v82);
              if ( (v152 & 4) == 0 )
              {
                pwszDst[0] = 0;
                if ( !v151 )
                  goto LABEL_247;
                if ( *((_WORD *)v151 + 1) >= 7u && (v105 = *((unsigned __int16 *)v151 + 18), (_WORD)v105) )
                {
                  v110 = &v151[v105];
                  v111 = ualstrlenW(&v151[v105], v151, v104) + 1;
                  if ( v111 > 0x104 )
LABEL_247:
                    pwszDst[0] = 0;
                  else
                    memcpy_0(pwszDst, v110, 2 * v111);
                }
                else
                {
                  v106 = *((unsigned __int16 *)v151 + 9);
                  if ( !(_WORD)v106 )
                    goto LABEL_247;
                  SHAnsiToUnicode(&v151[v106], pwszDst, 260);
                }
              }
              v152 = 4;
              if ( pwszDst[0] )
              {
                v114 = CFileSysItemString::ResourceName((CFileSysItemString *)v144);
                v21 = SHSysAllocString(v114, &value);
                if ( v21 >= 0 )
                  v46 |= 1u;
              }
              else
              {
                v21 = v131;
              }
              v144[0] = &CFileSysItemString::`vftable';
              v107 = v150;
              v150 = 0;
              if ( v107 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v107 + 16LL))(v107);
              v108 = v148;
              v148 = 0;
              if ( v108 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v108 + 16LL))(v108);
              v109 = v149;
              v149 = 0;
              if ( v109 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v109 + 16LL))(v109);
              if ( v147 )
                CoTaskMemFree(v147);
              if ( v146 )
                CoTaskMemFree(v146);
              if ( v145 )
                CoTaskMemFree(v145);
              if ( v21 < 0 )
              {
LABEL_158:
                CoTaskMemFree(pv);
                SysFreeString(value);
                v85 = v127;
                if ( v127 )
                {
                  v127 = 0;
                  ((void (__fastcall *)(struct IShellFolder *))v85->lpVtbl->Release)(v85);
                }
                v4 = (LPVOID *)v119;
                v10 = v115;
                goto LABEL_59;
              }
            }
LABEL_95:
            v57 = v46;
            v58 = value;
            v59 = *v119;
            propBag = 0;
            v60 = -1091633152;
            if ( (v134 & 0x10) == 0 )
            {
              Src = 0;
              v124 = 0;
              if ( ((int (__fastcall *)(struct IBindCtx *, const unsigned __int16 *, __int64 *))v118->lpVtbl->GetObjectParam)(
                     v118,
                     L"SHBindCtxPropertyBag",
                     &v124) >= 0
                && (v99 = (**(__int64 (__fastcall ***)(__int64, GUID *, void **))v124)(
                            v124,
                            &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
                            &Src),
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v124 + 16LL))(v124),
                    v99 >= 0)
                && (v100 = PSPropertyBag_ReadStrAlloc((IPropertyBag *)Src, L"ExplicitProgid", (PWSTR *)&propBag),
                    (*(void (__fastcall **)(void *))(*(_QWORD *)Src + 16LL))(Src),
                    v100 >= 0) )
              {
                v60 = -1091633126;
              }
              else
              {
                propBag = 0;
                Src = 0;
                v124 = 0;
                if ( ((int (__fastcall *)(struct IBindCtx *, const unsigned __int16 *, __int64 *))v118->lpVtbl->GetObjectParam)(
                       v118,
                       L"SHBindCtxPropertyBag",
                       &v124) >= 0 )
                {
                  v101 = (**(__int64 (__fastcall ***)(__int64, GUID *, void **))v124)(
                           v124,
                           &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
                           &Src);
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v124 + 16LL))(v124);
                  if ( v101 >= 0 )
                  {
                    StrAlloc = PSPropertyBag_ReadStrAlloc(
                                 (IPropertyBag *)Src,
                                 L"ExplicitAssociationApp",
                                 (PWSTR *)&propBag);
                    (*(void (__fastcall **)(void *))(*(_QWORD *)Src + 16LL))(Src);
                    if ( StrAlloc >= 0 )
                      v60 = -1091633125;
                  }
                }
              }
            }
            v124 = 0;
            if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, __int64 *))v118->lpVtbl->GetObjectParam)(
                   v118,
                   L"Win7FileSystemIdList",
                   &v124) >= 0 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v124 + 16LL))(v124);
              v57 = v46 | 8;
            }
            v131 = 0;
            Src = 0;
            if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, void **))v118->lpVtbl->GetObjectParam)(
                   v118,
                   L"Folder Enum Mode",
                   &Src) >= 0 )
            {
              v61 = Src;
              v131 = 0;
              if ( Src )
              {
                v124 = 0;
                if ( (**(int (__fastcall ***)(void *, GUID *, __int64 *))Src)(
                       Src,
                       &GUID_6a9d9026_0e6e_464c_b000_42ecc07de673,
                       &v124) >= 0 )
                {
                  (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v124 + 32LL))(v124, &v131);
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v124 + 16LL))(v124);
                }
                v61 = Src;
              }
              (*(void (__fastcall **)(void *))(*(_QWORD *)v61 + 16LL))(v61);
            }
            v21 = CFSFolder::_CreateIDList(v120, &v134, v59, v58, propBag, v60, v57, v131, &v116);
            if ( v21 >= 0 )
            {
              v62 = propBag;
              if ( !propBag )
              {
LABEL_106:
                CoTaskMemFree(v62);
                if ( v21 < 0 || (v63 = (unsigned __int16 *)pv) == 0 )
                {
                  v8 = (struct _ITEMIDLIST_RELATIVE *)v116;
                  Src = v116;
                  goto LABEL_158;
                }
                if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::GetImpl'::`2'::impl) )
                {
                  v64 = *v63;
                  goto LABEL_110;
                }
                if ( !v63 || (v64 = *v63, *v63 < 2u) )
                {
LABEL_232:
                  v8 = (struct _ITEMIDLIST_RELATIVE *)v116;
                  Src = v116;
LABEL_140:
                  if ( v8 )
                    v21 = 0;
                  else
LABEL_162:
                    v21 = -2147024882;
                  goto LABEL_158;
                }
LABEL_110:
                v65 = 0;
                v66 = *(unsigned __int16 *)((char *)v63 + v64 - 2);
                if ( (_WORD)v66 )
                {
                  if ( v66 + 8 < (unsigned __int64)v64 )
                  {
                    v65 = (unsigned __int16 *)((char *)v63 + v66);
                    v67 = *(unsigned __int16 *)((char *)v63 + v66);
                    if ( v67 < 8 || HIWORD(*((_DWORD *)v65 + 1)) != 0xBEEF || (unsigned int)v66 + v67 > v64 )
                      v65 = 0;
                  }
                }
                v68 = (unsigned __int64)v63 + *v63;
                if ( !v65 )
                  goto LABEL_232;
                v8 = (struct _ITEMIDLIST_RELATIVE *)v116;
                Src = v116;
                while ( 2 )
                {
                  if ( !v8 )
                    goto LABEL_162;
                  v69 = *(_WORD *)v8;
                  v70 = (int *)(v65 + 2);
                  if ( !v69 )
                    goto LABEL_165;
                  v71 = *v70;
                  v72 = (unsigned __int16 *)Src;
                  do
                  {
                    v73 = v72;
                    v72 = (unsigned __int16 *)((char *)v72 + v69);
                    v69 = *v72;
                  }
                  while ( *v72 );
                  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::GetImpl'::`2'::impl) )
                  {
                    v74 = *v73;
                    goto LABEL_123;
                  }
                  if ( v73 && (v74 = *v73, *v73 >= 2u) )
                  {
LABEL_123:
                    v75 = 0;
                    v76 = *(unsigned __int16 *)((char *)v73 + v74 - 2);
                    if ( (_WORD)v76 )
                    {
                      if ( v76 + 8 < (unsigned __int64)v74 )
                      {
                        v75 = (unsigned __int16 *)((char *)v73 + v76);
                        v77 = *(unsigned __int16 *)((char *)v73 + v76);
                        if ( v77 < 8 || HIWORD(*((_DWORD *)v75 + 1)) != 0xBEEF || (unsigned int)v76 + v77 > v74 )
                          v75 = 0;
                      }
                    }
                    v78 = (unsigned __int64)v73 + *v73;
                    if ( !v75 )
                      goto LABEL_165;
                    while ( *((_DWORD *)v75 + 1) != v71 )
                    {
                      v97 = 0;
                      if ( (unsigned __int64)(v75 + 4) <= v78 )
                      {
                        v98 = (unsigned __int16 *)((char *)v75 + *v75);
                        if ( v98 == (unsigned __int16 *)v78 )
                          goto LABEL_165;
                        if ( (unsigned __int64)v98 <= v78 )
                        {
                          if ( (unsigned __int64)(v98 + 4) > v78
                            || HIWORD(*((_DWORD *)v98 + 1)) != 0xBEEF
                            || (unsigned __int64)v98 + *v98 > v78
                            || v98 < v75 + 4 )
                          {
                            goto LABEL_165;
                          }
                          v97 = (unsigned __int16 *)((char *)v75 + *v75);
                        }
                      }
                      v75 = v97;
                      if ( !v97 )
                        goto LABEL_165;
                    }
                  }
                  else
                  {
LABEL_165:
                    if ( *v70 != -1091633149 || (v46 & 2) != 0 )
                    {
                      v86 = ILCloneFirst((LPCITEMIDLIST)v65);
                      v87 = (const struct _HIDDENITEMID *)v86;
                      if ( v86 && (cb = v86->mkid.cb, cb >= 8u) )
                      {
                        *(_WORD *)v87 = cb - 2;
                        v8 = ILAppendHiddenID((struct _ITEMIDLIST_RELATIVE *)Src, v87);
                        Src = v8;
                        CoTaskMemFree(v87);
                      }
                      else
                      {
                        CoTaskMemFree(Src);
                        v8 = 0;
                        Src = 0;
                      }
LABEL_131:
                      v79 = 0;
                      if ( (unsigned __int64)(v65 + 4) <= v68 )
                      {
                        v80 = (unsigned __int16 *)((char *)v65 + *v65);
                        if ( v80 == (unsigned __int16 *)v68 )
                          goto LABEL_140;
                        if ( (unsigned __int64)v80 <= v68 )
                        {
                          if ( (unsigned __int64)(v80 + 4) > v68
                            || HIWORD(*((_DWORD *)v80 + 1)) != 0xBEEF
                            || (unsigned __int64)v80 + *v80 > v68
                            || v80 < v65 + 4 )
                          {
                            goto LABEL_140;
                          }
                          v79 = (unsigned __int16 *)((char *)v65 + *v65);
                        }
                      }
                      v65 = v79;
                      if ( !v79 )
                        goto LABEL_140;
                      continue;
                    }
                  }
                  break;
                }
                v8 = (struct _ITEMIDLIST_RELATIVE *)Src;
                goto LABEL_131;
              }
              v21 = _BindCtx_SetValue<int>(v118, L"ExplicitAssociationSuccessful", 1);
              if ( v21 < 0 )
              {
                CoTaskMemFree(v116);
                v8 = 0;
                Src = 0;
                CoTaskMemFree(propBag);
                goto LABEL_158;
              }
            }
            v62 = propBag;
            goto LABEL_106;
          }
          v33 = 16;
          if ( v10 )
            v33 = 17;
          v134 = v33;
          v34 = v10;
          v124 = 0;
          if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, __int64 *))v5->lpVtbl->GetObjectParam)(
                 v5,
                 L"Win7FileSystemIdList",
                 &v124) >= 0 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v124 + 16LL))(v124);
            v34 = v10 | 8;
          }
          v21 = CFSFolder::_CreateIDList(v120, &v134, *v4, 0, 0, -1091633152, v34, v132, &v116);
          v8 = (struct _ITEMIDLIST_RELATIVE *)v116;
          Src = v116;
LABEL_59:
          if ( v21 < 0 )
            goto LABEL_39;
          v35 = *v4;
          if ( v8 && v35 )
          {
            v36 = (unsigned __int16 *)*v4;
            v37 = 2;
            do
            {
              v38 = *v36;
              if ( !(_WORD)v38 )
                break;
              v37 += v38;
              v36 = (unsigned __int16 *)((char *)v36 + v38);
            }
            while ( v36 );
            v39 = (unsigned int)(v37 - 2);
            v40 = Src;
            v41 = (unsigned __int16 *)Src;
            v42 = 2;
            do
            {
              v43 = *v41;
              if ( !(_WORD)v43 )
                break;
              v42 += v43;
              v41 = (unsigned __int16 *)((char *)v41 + v43);
            }
            while ( v41 );
            v44 = (char *)WINRT_IMPL_CoTaskMemAlloc(v42 + (unsigned int)v39);
            v45 = v44;
            if ( v44 )
            {
              memset_0(v44, 0, v42 + (unsigned int)v39);
              memcpy_0(v45, v35, (unsigned int)v39);
              memcpy_0(&v45[v39], v40, v42);
            }
            v4 = (LPVOID *)v119;
            *v119 = (struct _ITEMIDLIST_RELATIVE *)v45;
            v8 = 0;
            v26 = v45 == 0;
            v21 = 0;
            if ( v26 )
              v21 = -2147024882;
            CoTaskMemFree(v35);
            CoTaskMemFree(v40);
LABEL_73:
            if ( v21 < 0 )
              goto LABEL_39;
            v5 = v118;
            v11 = v117;
            v10 = v115;
          }
          else
          {
            v21 = 0;
            if ( v35 )
            {
              v8 = 0;
              goto LABEL_73;
            }
            if ( !v8 )
            {
              v21 = -2147024809;
LABEL_39:
              CoTaskMemFree(*v4);
              *v4 = 0;
LABEL_40:
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v130 + 16LL))(v130);
              return (unsigned int)v21;
            }
            *v4 = v8;
            v5 = v118;
            v11 = v117;
            v8 = 0;
          }
        }
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180069550  push    rbp
0x180069552  push    rbx
0x180069553  push    rsi
0x180069554  push    rdi
0x180069555  push    r12
0x180069557  push    r13
0x180069559  push    r14
0x18006955b  push    r15
0x18006955d  lea     rbp, [rsp-778h]
0x180069565  sub     rsp, 878h
0x18006956c  mov     rax, cs:__security_cookie
0x180069573  xor     rax, rsp
0x180069576  mov     [rbp+7B0h+var_50], rax
0x18006957d  mov     rsi, r9
0x180069580  mov     [rsp+8B0h+var_840], r9
0x180069585  mov     r12, r8
0x180069588  mov     [rsp+8B0h+var_848], r8
0x18006958d  mov     rdi, rdx
0x180069590  mov     r14, rcx
0x180069593  mov     [rsp+8B0h+var_838], rcx
0x180069598  xor     r15d, r15d
0x18006959b  mov     [r9], r15
0x18006959e  mov     [rbp+7B0h+var_7E8], r15
0x1800695a2  mov     [rbp+7B0h+var_800], r15
0x1800695a6  test    r8, r8
0x1800695a9  jz      loc_18006A4D3
0x1800695af  mov     rax, [r8]
0x1800695b2  lea     r8, [rbp+7B0h+var_800]
0x1800695b6  lea     rdx, aFileSystemBind; "File System Bind Data"
0x1800695bd  mov     rcx, r12
0x1800695c0  mov     rax, [rax+50h]
0x1800695c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800695c9  test    eax, eax
0x1800695cb  js      loc_18006A4D3
0x1800695d1  mov     rcx, [rbp+7B0h+var_800]
0x1800695d5  mov     rax, [rcx]
0x1800695d8  lea     r8, [rbp+7B0h+var_7E8]
0x1800695dc  lea     rdx, _GUID_01e18d10_4d8b_11d2_855d_006008059367
0x1800695e3  mov     rax, [rax]
0x1800695e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800695eb  mov     ebx, eax
0x1800695ed  mov     rcx, [rbp+7B0h+var_800]
0x1800695f1  mov     rdx, [rcx]
0x1800695f4  mov     rax, [rdx+10h]
0x1800695f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800695fd  test    ebx, ebx
0x1800695ff  js      loc_18006A4D3
0x180069605  xor     edx, edx; Val
0x180069607  mov     r8d, 268h; Size
0x18006960d  lea     rcx, [rbp+7B0h+var_7C0]; void *
0x180069611  call    memset_0
0x180069616  mov     [rbp+7B0h+var_818], r15
0x18006961a  mov     rax, [r12]
0x18006961e  lea     r8, [rbp+7B0h+var_818]
0x180069622  lea     rdx, aFoldersAsReadO; "Folders As Read Only"
0x180069629  mov     rcx, r12
0x18006962c  mov     rax, [rax+50h]
0x180069630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069635  test    eax, eax
0x180069637  jns     loc_18006A52A
0x18006963d  xor     r13b, r13b
0x180069640  mov     [rsp+8B0h+var_860], r13b
0x180069645  mov     ebx, r15d
0x180069648  mov     [rsp+8B0h+var_850], ebx
0x18006964c  mov     [rbp+7B0h+var_818], r15
0x180069650  mov     rax, [r12]
0x180069654  lea     r8, [rbp+7B0h+var_818]
0x180069658  lea     rdx, aNovalidatefile; "NoValidateFilenameChars"
0x18006965f  mov     rcx, r12
0x180069662  mov     rax, [rax+50h]
0x180069666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006966b  test    eax, eax
0x18006966d  js      short loc_180069688
0x18006966f  mov     ebx, 1
0x180069674  mov     [rsp+8B0h+var_850], ebx
0x180069678  mov     rcx, [rbp+7B0h+var_818]
0x18006967c  mov     rax, [rcx]
0x18006967f  mov     rax, [rax+10h]
0x180069683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069688  mov     [rbp+7B0h+var_7DC], r15d
0x18006968c  mov     [rbp+7B0h+value], r15
0x180069690  mov     rax, [r12]
0x180069694  lea     r8, [rbp+7B0h+value]
0x180069698  lea     rdx, aFolderEnumMode; "Folder Enum Mode"
0x18006969f  mov     rcx, r12
0x1800696a2  mov     rax, [rax+50h]
0x1800696a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800696ab  test    eax, eax
0x1800696ad  js      short loc_180069710
0x1800696af  mov     rcx, [rbp+7B0h+value]
0x1800696b3  mov     [rbp+7B0h+var_7DC], r15d
0x1800696b7  test    rcx, rcx
0x1800696ba  jz      short loc_180069702
0x1800696bc  mov     [rbp+7B0h+var_800], r15
0x1800696c0  mov     rax, [rcx]
0x1800696c3  lea     r8, [rbp+7B0h+var_800]
0x1800696c7  lea     rdx, _GUID_6a9d9026_0e6e_464c_b000_42ecc07de673
0x1800696ce  mov     rax, [rax]
0x1800696d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800696d6  test    eax, eax
0x1800696d8  js      short loc_1800696FE
0x1800696da  mov     rcx, [rbp+7B0h+var_800]
0x1800696de  mov     rax, [rcx]
0x1800696e1  lea     rdx, [rbp+7B0h+var_7DC]
0x1800696e5  mov     rax, [rax+20h]
0x1800696e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800696ee  mov     rcx, [rbp+7B0h+var_800]
0x1800696f2  mov     rax, [rcx]
0x1800696f5  mov     rax, [rax+10h]
0x1800696f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800696fe  mov     rcx, [rbp+7B0h+value]
0x180069702  mov     rax, [rcx]
0x180069705  mov     rax, [rax+10h]
0x180069709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006970e  xchg    ax, ax
0x180069710  mov     [rbp+7B0h+var_794], r15w
0x180069715  test    rdi, rdi
0x180069718  jz      loc_180069FA8
0x18006971e  mov     edx, 5Ch ; '\'; wMatch
0x180069723  mov     rcx, rdi; pszStart
0x180069726  call    cs:__imp_StrChrW
0x18006972d  nop     dword ptr [rax+rax+00h]
0x180069732  mov     r10, rax
0x180069735  test    rax, rax
0x180069738  jz      loc_180069878
0x18006973e  cmp     rax, rdi
0x180069741  jbe     loc_180069816
0x180069747  mov     rcx, rax
0x18006974a  sub     rcx, rdi
0x18006974d  sar     rcx, 1
0x180069750  movsxd  rdx, ecx
0x180069753  cmp     rdx, 7FFFFFFEh
0x18006975a  ja      loc_18006A819
0x180069760  mov     r9d, 104h
0x180069766  lea     r8, [rbp+7B0h+var_794]
0x18006976a  nop     word ptr [rax+rax+00h]
0x180069770  test    rdx, rdx
0x180069773  jz      short loc_180069792
0x180069775  movzx   eax, word ptr [rdi]
0x180069778  test    ax, ax
0x18006977b  jz      short loc_180069792
0x18006977d  add     rdi, 2
0x180069781  mov     [r8], ax
0x180069785  add     r8, 2
0x180069789  dec     rdx
0x18006978c  sub     r9, 1
0x180069790  jnz     short loc_180069770
0x180069792  lea     rcx, [r8-2]
0x180069796  test    r9, r9
0x180069799  cmovnz  rcx, r8
0x18006979d  mov     [rcx], r15w
0x1800697a1  movzx   ecx, [rbp+7B0h+var_794]
0x1800697a5  lea     rdi, [r10+2]
0x1800697a9  cmp     word ptr [rdi], 0
0x1800697ad  cmovz   rdi, r15
0x1800697b1  mov     r14d, r15d
0x1800697b4  mov     [rbp+7B0h+var_7E0], r15d
0x1800697b8  test    ebx, ebx
0x1800697ba  jnz     loc_1800698CE
0x1800697c0  test    cx, cx
0x1800697c3  jz      short loc_180069811
0x1800697c5  cmp     cx, 2Eh ; '.'
0x1800697c9  jz      loc_18006A353
0x1800697cf  mov     esi, 1
0x1800697d4  lea     rbx, [rbp+7B0h+var_794]
0x1800697d8  movzx   ecx, word ptr [rbx]
0x1800697db  test    cx, cx
0x1800697de  jz      short loc_180069804
0x1800697e0  mov     edx, 1E4h
0x1800697e5  call    cs:__imp_PathIsValidCharW
0x1800697ec  nop     dword ptr [rax+rax+00h]
0x1800697f1  test    eax, eax
0x1800697f3  jz      short loc_180069865
0x1800697f5  cmp     word ptr [rbx], 2Eh ; '.'
0x1800697f9  jz      short loc_180069865
0x1800697fb  mov     esi, r15d
0x1800697fe  add     rbx, 2
0x180069802  jmp     short loc_1800697D8
0x180069804  test    esi, esi
0x180069806  mov     rsi, [rsp+8B0h+var_840]
0x18006980b  jz      loc_1800698CE
0x180069811  mov     [rbp+7B0h+var_794], r15w
0x180069816  mov     r14d, 80070057h
0x18006981c  mov     rcx, [rsi]; pv
0x18006981f  call    cs:__imp_CoTaskMemFree
0x180069826  nop     dword ptr [rax+rax+00h]
0x18006982b  mov     [rsi], r15
0x18006982e  mov     rcx, [rbp+7B0h+var_7E8]
0x180069832  mov     rax, [rcx]
0x180069835  mov     rax, [rax+10h]
0x180069839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006983e  mov     eax, r14d
0x180069841  mov     rcx, [rbp+7B0h+var_50]
0x180069848  xor     rcx, rsp; StackCookie
0x18006984b  call    __security_check_cookie
0x180069850  add     rsp, 878h
0x180069857  pop     r15
0x180069859  pop     r14
0x18006985b  pop     r13
0x18006985d  pop     r12
0x18006985f  pop     rdi
0x180069860  pop     rsi
0x180069861  pop     rbx
0x180069862  pop     rbp
0x180069863  retn
0x180069865  add     rbx, 2
0x180069869  test    eax, eax
0x18006986b  jnz     loc_1800697D8
0x180069871  mov     rsi, [rsp+8B0h+var_840]
0x180069876  jmp     short loc_180069811
0x180069878  mov     ecx, 7FFFFFFEh
0x18006987d  mov     edx, 104h
0x180069882  lea     r8, [rbp+7B0h+var_794]
0x180069886  test    rcx, rcx
0x180069889  jz      short loc_1800698A8
0x18006988b  movzx   eax, word ptr [rdi]
0x18006988e  test    ax, ax
0x180069891  jz      short loc_1800698A8
0x180069893  add     rdi, 2
0x180069897  mov     [r8], ax
0x18006989b  add     r8, 2
0x18006989f  dec     rcx
0x1800698a2  sub     rdx, 1
0x1800698a6  jnz     short loc_180069886
0x1800698a8  lea     rcx, [r8-2]
0x1800698ac  test    rdx, rdx
0x1800698af  cmovnz  rcx, r8
0x1800698b3  mov     [rcx], r15w
0x1800698b7  mov     r14d, 8007007Ah
0x1800698bd  cmovnz  r14d, r15d
0x1800698c1  mov     [rbp+7B0h+var_7E0], r14d
0x1800698c5  mov     rdi, r15
0x1800698c8  jnz     loc_180069FB0
0x1800698ce  test    r14d, r14d
0x1800698d1  jnz     loc_180069FA2
0x1800698d7  mov     [rbp+7B0h+Src], r15
0x1800698db  mov     [rsp+8B0h+var_858], r15
0x1800698e0  test    rdi, rdi
0x1800698e3  jz      loc_180069A5B
0x1800698e9  mov     eax, 10h
0x1800698ee  test    r13b, r13b
0x1800698f1  mov     ecx, 11h
0x1800698f6  cmovnz  eax, ecx
0x1800698f9  mov     [rbp+7B0h+var_7C0], eax
0x1800698fc  movzx   ebx, r13b
0x180069900  mov     [rbp+7B0h+var_818], 0
0x180069908  mov     rax, [r12]
0x18006990c  lea     r8, [rbp+7B0h+var_818]
0x180069910  lea     rdx, aWin7filesystem; "Win7FileSystemIdList"
0x180069917  mov     rcx, r12
0x18006991a  mov     rax, [rax+50h]
0x18006991e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069923  test    eax, eax
0x180069925  jns     loc_18006A50B
0x18006992b  lea     rax, [rsp+8B0h+var_858]
0x180069930  mov     [rsp+8B0h+var_870], rax
0x180069935  mov     eax, [rbp+7B0h+var_7DC]
0x180069938  mov     [rsp+8B0h+var_878], eax
0x18006993c  mov     [rsp+8B0h+var_880], ebx
0x180069940  mov     [rsp+8B0h+var_888], 0BEEF0000h
0x180069948  mov     [rsp+8B0h+var_890], 0
0x180069951  xor     r9d, r9d
0x180069954  mov     r8, [rsi]
0x180069957  lea     rdx, [rbp+7B0h+var_7C0]
0x18006995b  mov     rcx, [rsp+8B0h+var_838]
0x180069960  call    ?_CreateIDList@CFSFolder@@IEAAJPEBUtagWIN32_FIND_DATA_EX@@PEFBU_ITEMIDLIST_RELATIVE@@PEBG2W4IDLHID@@W4CREATE_IDLIST_FLAGS@@W4FOLDER_ENUM_MODE@@PEAPEAU_ITEMID_CHILD@@@Z; CFSFolder::_CreateIDList(tagWIN32_FIND_DATA_EX const *,_ITEMIDLIST_RELATIVE const *,ushort const *,ushort const *,IDLHID,CREATE_IDLIST_FLAGS,FOLDER_ENUM_MODE,_ITEMID_CHILD * *)
0x180069965  mov     r14d, eax
0x180069968  mov     r15, [rsp+8B0h+var_858]
0x18006996d  mov     [rbp+7B0h+Src], r15
0x180069971  test    r14d, r14d
0x180069974  js      loc_18006A8A6
0x18006997a  mov     r12, [rsi]
0x18006997d  test    r15, r15
0x180069980  jz      loc_180069F79
0x180069986  test    r12, r12
0x180069989  jz      loc_180069F79
0x18006998f  mov     rdx, r12
0x180069992  mov     r8d, 2
0x180069998  movzx   ecx, word ptr [rdx]
0x18006999b  test    cx, cx
0x18006999e  jz      short loc_1800699A8
0x1800699a0  add     r8d, ecx
0x1800699a3  add     rdx, rcx
0x1800699a6  jnz     short loc_180069998
0x1800699a8  lea     r15d, [r8-2]
0x1800699ac  mov     r13, [rbp+7B0h+Src]
0x1800699b0  mov     rdx, r13
0x1800699b3  mov     esi, 2
0x1800699b8  movzx   ecx, word ptr [rdx]
0x1800699bb  test    cx, cx
0x1800699be  jz      short loc_1800699C7
0x1800699c0  add     esi, ecx
0x1800699c2  add     rdx, rcx
0x1800699c5  jnz     short loc_1800699B8
0x1800699c7  lea     eax, [rsi+r15]
0x1800699cb  mov     ebx, eax
0x1800699cd  mov     ecx, eax; cb
0x1800699cf  call    WINRT_IMPL_CoTaskMemAlloc
0x1800699d4  mov     r14, rax
0x1800699d7  test    rax, rax
  ... truncated ...
```
