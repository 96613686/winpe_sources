# CFSFolder::TrySimpleParse(ushort const *,IBindCtx *,_ITEMIDLIST_RELATIVE * *)

- ea: `0x1800d7800`
- end: `0x1800d8add`
- name: `?TrySimpleParse@CFSFolder@@IEAAJPEBGPEAUIBindCtx@@PEAPEAU_ITEMIDLIST_RELATIVE@@@Z`
- size: `4829`
- prototype: `__int64 __fastcall(CFSFolder *__hidden this, PCWSTR pszStart, struct IBindCtx *, struct _ITEMIDLIST_RELATIVE **)`
- caller_count: `1`
- callee_count: `20`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18001d330`

## callees

- `0x180043320`
- `0x180059700`
- `0x18008e240`
- `0x180097ff0`
- `0x1800a08d0`
- `0x1800d7800`
- `0x1800d8af0`
- `0x1800dfcf0`
- `0x1801464f8`
- `0x180155330`
- `0x1801f7b10`
- `0x1801f86f0`
- `0x18023af4c`
- `0x180333018`
- `0x1803a4cb0`
- `0x1803a57e0`
- `0x1803a5bc5`
- `0x1803a96d9`
- `0x1803a96e5`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1800d79d6`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1800d79d6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsValidCharW` at `0x1800d7a8d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsValidCharW` at `0x1800d7a8d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d82fc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d82fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d7ac1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d7cbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d7cc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d803f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d82f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d83a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d87c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d88e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d88f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d890a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d8ab3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d8ac4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d7ac1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d7cbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d7cc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d803f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d82f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d83a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d87c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d88e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d88f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d890a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d8ab3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d8ac4`
- `SHCORE!__imp_ualstrlenW` at `0x1800d892a`
- `SHCORE!__imp_ualstrlenW` at `0x1800d892a`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1800d864f`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1800d86e0`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1800d864f`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1800d86e0`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x1800d7ef9`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x1800d7ef9`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHAnsiToUnicode` at `0x1800d8a77`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHAnsiToUnicode` at `0x1800d8a77`

## string_xrefs

- `0x1800d78d2`: `Folders As Read Only`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CFSFolder::TrySimpleParse(
        CFSFolder *this,
        PCWSTR pszStart,
        struct IBindCtx *a3,
        struct _ITEMIDLIST_RELATIVE **a4)
{
  void **v4; // rsi
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
  char v34; // bl
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
  char v46; // r13
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
  char v57; // si
  unsigned __int16 *v58; // r15
  void *v59; // r12
  unsigned int v60; // r14d
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
  __int64 v105; // r9
  __int64 v106; // rax
  __int64 v107; // rax
  __int64 v108; // rcx
  __int64 v109; // rcx
  __int64 v110; // rcx
  const CHAR *v111; // rbx
  unsigned __int64 v112; // r8
  __int64 v113; // rax
  __int16 v114; // r11
  const unsigned __int16 *v115; // rax
  bool v116; // [rsp+50h] [rbp-B0h]
  LPVOID v117; // [rsp+58h] [rbp-A8h] BYREF
  int v118; // [rsp+60h] [rbp-A0h]
  struct IBindCtx *v119; // [rsp+68h] [rbp-98h]
  void **v120; // [rsp+70h] [rbp-90h]
  struct CFSFolder *v121; // [rsp+78h] [rbp-88h]
  __int64 v122; // [rsp+80h] [rbp-80h]
  __int64 v123; // [rsp+88h] [rbp-78h]
  __int64 v124; // [rsp+90h] [rbp-70h]
  __int64 v125; // [rsp+98h] [rbp-68h] BYREF
  void *Src; // [rsp+A0h] [rbp-60h] BYREF
  IPropertyBag *propBag; // [rsp+A8h] [rbp-58h] BYREF
  struct IShellFolder *v128; // [rsp+B0h] [rbp-50h] BYREF
  BSTR value; // [rsp+B8h] [rbp-48h] BYREF
  LPVOID pv; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v131; // [rsp+C8h] [rbp-38h] BYREF
  enum FOLDER_ENUM_MODE v132; // [rsp+D0h] [rbp-30h] BYREF
  enum FOLDER_ENUM_MODE v133; // [rsp+D4h] [rbp-2Ch] BYREF
  _QWORD v134[3]; // [rsp+D8h] [rbp-28h] BYREF
  int v135; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v136; // [rsp+F4h] [rbp-Ch]
  __int128 v137; // [rsp+104h] [rbp+4h]
  __int64 v138; // [rsp+114h] [rbp+14h]
  __int16 v139; // [rsp+11Ch] [rbp+1Ch] BYREF
  __int16 v140; // [rsp+11Eh] [rbp+1Eh]
  __int16 v141; // [rsp+120h] [rbp+20h]
  char v142; // [rsp+324h] [rbp+224h] BYREF
  char v143[8]; // [rsp+340h] [rbp+240h] BYREF
  __int128 Buf1; // [rsp+348h] [rbp+248h] BYREF
  _QWORD v145[2]; // [rsp+360h] [rbp+260h] BYREF
  LPVOID v146; // [rsp+370h] [rbp+270h]
  LPVOID v147; // [rsp+378h] [rbp+278h]
  LPVOID v148; // [rsp+390h] [rbp+290h]
  __int64 v149; // [rsp+398h] [rbp+298h]
  __int64 v150; // [rsp+3A0h] [rbp+2A0h]
  __int64 v151; // [rsp+3A8h] [rbp+2A8h]
  const CHAR *v152; // [rsp+3B8h] [rbp+2B8h]
  int v153; // [rsp+3E0h] [rbp+2E0h]
  WCHAR pwszDst[278]; // [rsp+3E4h] [rbp+2E4h] BYREF
  int v155; // [rsp+610h] [rbp+510h] BYREF
  __int128 v156; // [rsp+614h] [rbp+514h]
  __int128 v157; // [rsp+624h] [rbp+524h]
  __int64 v158; // [rsp+634h] [rbp+534h]
  char v159; // [rsp+844h] [rbp+744h] BYREF

  v4 = (void **)a4;
  v120 = (void **)a4;
  v5 = a3;
  v119 = a3;
  v121 = this;
  v8 = 0;
  *a4 = 0;
  v131 = 0;
  v128 = 0;
  if ( a3 )
  {
    if ( ((int (__fastcall *)(struct IBindCtx *, const unsigned __int16 *, struct IShellFolder **))a3->lpVtbl->GetObjectParam)(
           a3,
           L"File System Bind Data",
           &v128) >= 0 )
    {
      v9 = ((__int64 (__fastcall *)(struct IShellFolder *, GUID *, __int64 *))v128->lpVtbl->QueryInterface)(
             v128,
             &GUID_01e18d10_4d8b_11d2_855d_006008059367,
             &v131);
      ((void (__fastcall *)(struct IShellFolder *))v128->lpVtbl->Release)(v128);
      if ( v9 >= 0 )
      {
        memset_0(&v135, 0, 0x268u);
        v125 = 0;
        v10 = 0;
        if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, __int64 *))v5->lpVtbl->GetObjectParam)(
               v5,
               L"Folders As Read Only",
               &v125) >= 0 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v125 + 16LL))(v125);
          if ( !(unsigned int)CFSFolder::_IsNetFolder(this) )
            v10 = 1;
        }
        v116 = v10;
        v11 = 0;
        v118 = 0;
        v125 = 0;
        if ( ((int (__fastcall *)(struct IBindCtx *, const unsigned __int16 *, __int64 *))v5->lpVtbl->GetObjectParam)(
               v5,
               L"NoValidateFilenameChars",
               &v125) >= 0 )
        {
          v11 = 1;
          v118 = 1;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v125 + 16LL))(v125);
        }
        v133 = FEM_VIEWRESULT;
        value = 0;
        if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, BSTR *))v5->lpVtbl->GetObjectParam)(
               v5,
               L"Folder Enum Mode",
               &value) >= 0 )
        {
          v12 = value;
          v133 = FEM_VIEWRESULT;
          if ( value )
          {
            v128 = 0;
            if ( (**(int (__fastcall ***)(BSTR, GUID *, struct IShellFolder **))value)(
                   value,
                   &GUID_6a9d9026_0e6e_464c_b000_42ecc07de673,
                   &v128) >= 0 )
            {
              ((void (__fastcall *)(struct IShellFolder *, enum FOLDER_ENUM_MODE *))v128->lpVtbl->EnumObjects)(
                v128,
                &v133);
              ((void (__fastcall *)(struct IShellFolder *))v128->lpVtbl->Release)(v128);
            }
            v12 = value;
          }
          (*(void (__fastcall **)(BSTR))(*(_QWORD *)v12 + 16LL))(v12);
        }
        while ( 1 )
        {
          v139 = 0;
          if ( !pszStart )
          {
            v21 = 0;
            goto LABEL_40;
          }
          v13 = StrChrW(pszStart, 0x5Cu);
          v14 = v13;
          if ( v13 )
          {
            if ( v13 <= pszStart )
              goto LABEL_38;
            v15 = (int)(v13 - pszStart);
            if ( v15 > 0x7FFFFFFE )
            {
              v20 = 0;
              v139 = 0;
            }
            else
            {
              v16 = 260;
              v17 = (WCHAR *)&v139;
              do
              {
                if ( !v15 )
                  break;
                v18 = *pszStart;
                if ( !*pszStart )
                  break;
                ++pszStart;
                *v17++ = v18;
                --v15;
                --v16;
              }
              while ( v16 );
              v19 = v17 - 1;
              if ( v16 )
                v19 = v17;
              *v19 = 0;
              v20 = v139;
            }
            pszStart = v14 + 1;
            if ( !v14[1] )
              pszStart = 0;
            v21 = 0;
            v132 = FEM_VIEWRESULT;
          }
          else
          {
            v28 = 2147483646;
            v29 = 260;
            v30 = (WCHAR *)&v139;
            do
            {
              if ( !v28 )
                break;
              v31 = *pszStart;
              if ( !*pszStart )
                break;
              ++pszStart;
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
            v132 = v21;
            pszStart = 0;
            if ( !v29 )
              goto LABEL_52;
            v20 = v139;
          }
          if ( !v11 )
          {
            if ( !v20 || v20 == 46 && (!v140 || !v141 && v140 == 46) )
            {
LABEL_37:
              v139 = 0;
LABEL_38:
              v21 = -2147024809;
              goto LABEL_39;
            }
            v22 = 1;
            v23 = &v139;
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
                  v4 = v120;
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
            v4 = v120;
            if ( !v26 )
              goto LABEL_37;
          }
LABEL_52:
          if ( v21 )
            goto LABEL_39;
          Src = 0;
          v117 = 0;
          if ( !pszStart )
          {
            v134[0] = 16;
            v134[1] = 0;
            if ( ((int (__fastcall *)(struct IBindCtx *, _QWORD *))v5->lpVtbl->GetBindOptions)(v5, v134) >= 0
              && HIDWORD(v134[0]) == 2 )
            {
              v46 = 0;
            }
            else
            {
              v46 = 6;
            }
            if ( v116 )
              v46 |= 1u;
            memset_0(&v155, 0, 0x250u);
            if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v131 + 32LL))(v131, &v155) >= 0 )
            {
              v135 = v155;
              v136 = v156;
              v137 = v157;
              v138 = v158;
              v47 = 2147483646;
              v48 = (__int16 *)&v159;
              v49 = 14;
              v50 = &v142;
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
              if ( (**(int (__fastcall ***)(__int64, GUID *, IPropertyBag **))v131)(
                     v131,
                     &GUID_3acf075f_71db_4afa_81f0_3fc4fdf2a5b8,
                     &propBag) >= 0 )
              {
                ((void (__fastcall *)(IPropertyBag *, char *))propBag->lpVtbl[1].AddRef)(propBag, v143);
                if ( ((int (__fastcall *)(IPropertyBag *, __int128 *))propBag->lpVtbl[1].Read)(propBag, &Buf1) >= 0 )
                {
                  v46 &= ~4u;
                  if ( !memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
                    v46 &= ~2u;
                }
                ((void (__fastcall *)(IPropertyBag *))propBag->lpVtbl->Release)(propBag);
              }
            }
            v128 = 0;
            pv = 0;
            v125 = 0;
            propBag = 0;
            if ( ((int (__fastcall *)(struct IBindCtx *, const unsigned __int16 *, IPropertyBag **))v5->lpVtbl->GetObjectParam)(
                   v5,
                   L"ParseOriginalItem",
                   &propBag) >= 0 )
            {
              v53 = ((__int64 (__fastcall *)(IPropertyBag *, GUID *, __int64 *))propBag->lpVtbl->QueryInterface)(
                      propBag,
                      &GUID_b3a4b685_b685_4805_99d9_5dead2873236,
                      &v125);
              ((void (__fastcall *)(IPropertyBag *))propBag->lpVtbl->Release)(propBag);
              if ( v53 >= 0 )
              {
                (*(void (__fastcall **)(__int64, _QWORD, struct IShellFolder **, LPVOID *))(*(_QWORD *)v125 + 32LL))(
                  v125,
                  0,
                  &v128,
                  &pv);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v125 + 16LL))(v125);
              }
            }
            value = 0;
            propBag = 0;
            v125 = 0;
            if ( ((int (__fastcall *)(struct IBindCtx *, const unsigned __int16 *, __int64 *))v5->lpVtbl->GetObjectParam)(
                   v5,
                   L"SHBindCtxPropertyBag",
                   &v125) >= 0 )
            {
              v55 = (**(__int64 (__fastcall ***)(__int64, GUID *, IPropertyBag **))v125)(
                      v125,
                      &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
                      &propBag);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v125 + 16LL))(v125);
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
                    || v114 != *(_WORD *)v82 + 6
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
                v122 = 0;
                v123 = 0;
                v124 = 0;
                if ( DisplayNameOfAsBSTR(v128, (const struct _ITEMIDLIST_RELATIVE *)pv, 0, &value) >= 0 )
                  v46 |= 1u;
                goto LABEL_95;
              }
              if ( *v93 < 0 && !memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
              {
                v113 = ILFindHiddenIDOn(pv, 3203334147LL, 1);
                if ( v113 )
                {
                  Buf1 = *(_OWORD *)(v113 + 8);
                  v46 &= ~4u;
                }
              }
              CFileSysItemString::CFileSysItemString(
                (CFileSysItemString *)v145,
                v121,
                (const struct _ITEMIDLIST_RELATIVE *)pv,
                (const struct IDFOLDER *)v82);
              if ( (v153 & 4) == 0 )
              {
                pwszDst[0] = 0;
                if ( !v152 )
                  goto LABEL_247;
                if ( *((_WORD *)v152 + 1) >= 7u && (v106 = *((unsigned __int16 *)v152 + 18), (_WORD)v106) )
                {
                  v111 = &v152[v106];
                  v112 = ualstrlenW(&v152[v106], v152, v104, v105) + 1;
                  if ( v112 > 0x104 )
LABEL_247:
                    pwszDst[0] = 0;
                  else
                    memcpy_0(pwszDst, v111, 2 * v112);
                }
                else
                {
                  v107 = *((unsigned __int16 *)v152 + 9);
                  if ( !(_WORD)v107 )
                    goto LABEL_247;
                  SHAnsiToUnicode(&v152[v107], pwszDst, 260);
                }
              }
              v153 = 4;
              if ( pwszDst[0] )
              {
                v115 = CFileSysItemString::ResourceName((CFileSysItemString *)v145);
                v21 = SHSysAllocString(v115, &value);
                if ( v21 >= 0 )
                  v46 |= 1u;
              }
              else
              {
                v21 = v132;
              }
              v145[0] = &CFileSysItemString::`vftable';
              v108 = v151;
              v151 = 0;
              if ( v108 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v108 + 16LL))(v108);
              v109 = v149;
              v149 = 0;
              if ( v109 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v109 + 16LL))(v109);
              v110 = v150;
              v150 = 0;
              if ( v110 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v110 + 16LL))(v110);
              if ( v148 )
                CoTaskMemFree(v148);
              if ( v147 )
                CoTaskMemFree(v147);
              if ( v146 )
                CoTaskMemFree(v146);
              if ( v21 < 0 )
              {
LABEL_158:
                CoTaskMemFree(pv);
                SysFreeString(value);
                v85 = v128;
                if ( v128 )
                {
                  v128 = 0;
                  ((void (__fastcall *)(struct IShellFolder *))v85->lpVtbl->Release)(v85);
                }
                v4 = v120;
                v10 = v116;
                goto LABEL_59;
              }
            }
LABEL_95:
            v57 = v46;
            v58 = value;
            v59 = *v120;
            propBag = 0;
            v60 = -1091633152;
            if ( (v135 & 0x10) == 0 )
            {
              Src = 0;
              v125 = 0;
              if ( ((int (__fastcall *)(struct IBindCtx *, const unsigned __int16 *, __int64 *))v119->lpVtbl->GetObjectParam)(
                     v119,
                     L"SHBindCtxPropertyBag",
                     &v125) >= 0
                && (v99 = (**(__int64 (__fastcall ***)(__int64, GUID *, void **))v125)(
                            v125,
                            &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
                            &Src),
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v125 + 16LL))(v125),
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
                v125 = 0;
                if ( ((int (__fastcall *)(struct IBindCtx *, const unsigned __int16 *, __int64 *))v119->lpVtbl->GetObjectParam)(
                       v119,
                       L"SHBindCtxPropertyBag",
                       &v125) >= 0 )
                {
                  v101 = (**(__int64 (__fastcall ***)(__int64, GUID *, void **))v125)(
                           v125,
                           &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
                           &Src);
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v125 + 16LL))(v125);
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
            v125 = 0;
            if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, __int64 *))v119->lpVtbl->GetObjectParam)(
                   v119,
                   L"Win7FileSystemIdList",
                   &v125) >= 0 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v125 + 16LL))(v125);
              v57 = v46 | 8;
            }
            v132 = FEM_VIEWRESULT;
            Src = 0;
            if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, void **))v119->lpVtbl->GetObjectParam)(
                   v119,
                   L"Folder Enum Mode",
                   &Src) >= 0 )
            {
              v61 = Src;
              v132 = FEM_VIEWRESULT;
              if ( Src )
              {
                v125 = 0;
                if ( (**(int (__fastcall ***)(void *, GUID *, __int64 *))Src)(
                       Src,
                       &GUID_6a9d9026_0e6e_464c_b000_42ecc07de673,
                       &v125) >= 0 )
                {
                  (*(void (__fastcall **)(__int64, enum FOLDER_ENUM_MODE *))(*(_QWORD *)v125 + 32LL))(v125, &v132);
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v125 + 16LL))(v125);
                }
                v61 = Src;
              }
              (*(void (__fastcall **)(void *))(*(_QWORD *)v61 + 16LL))(v61);
            }
            v21 = CFSFolder::_CreateIDList(v121, (__int64)&v135, v59, v58, (__int64)propBag, v60, v57, v132, &v117);
            if ( v21 >= 0 )
            {
              v62 = propBag;
              if ( !propBag )
              {
LABEL_106:
                CoTaskMemFree(v62);
                if ( v21 < 0 || (v63 = (unsigned __int16 *)pv) == 0 )
                {
                  v8 = (struct _ITEMIDLIST_RELATIVE *)v117;
                  Src = v117;
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
                  v8 = (struct _ITEMIDLIST_RELATIVE *)v117;
                  Src = v117;
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
                v8 = (struct _ITEMIDLIST_RELATIVE *)v117;
                Src = v117;
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
              v21 = _BindCtx_SetValue<int>(v119, L"ExplicitAssociationSuccessful", 1);
              if ( v21 < 0 )
              {
                CoTaskMemFree(v117);
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
          v135 = v33;
          v34 = v10;
          v125 = 0;
          if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, __int64 *))v5->lpVtbl->GetObjectParam)(
                 v5,
                 L"Win7FileSystemIdList",
                 &v125) >= 0 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v125 + 16LL))(v125);
            v34 = v10 | 8;
          }
          v21 = CFSFolder::_CreateIDList(v121, (__int64)&v135, *v4, 0, 0, 0xBEEF0000, v34, v133, &v117);
          v8 = (struct _ITEMIDLIST_RELATIVE *)v117;
          Src = v117;
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
            v4 = v120;
            *v120 = v45;
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
            v5 = v119;
            v11 = v118;
            v10 = v116;
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
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v131 + 16LL))(v131);
              return (unsigned int)v21;
            }
            *v4 = v8;
            v5 = v119;
            v11 = v118;
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
0x1800d7800  push    rbp
0x1800d7802  push    rbx
0x1800d7803  push    rsi
0x1800d7804  push    rdi
0x1800d7805  push    r12
0x1800d7807  push    r13
0x1800d7809  push    r14
0x1800d780b  push    r15
0x1800d780d  lea     rbp, [rsp-778h]
0x1800d7815  sub     rsp, 878h
0x1800d781c  mov     rax, cs:__security_cookie
0x1800d7823  xor     rax, rsp
0x1800d7826  mov     [rbp+7B0h+var_50], rax
0x1800d782d  mov     rsi, r9
0x1800d7830  mov     [rsp+8B0h+var_840], r9
0x1800d7835  mov     r12, r8
0x1800d7838  mov     [rsp+8B0h+var_848], r8
0x1800d783d  mov     rdi, rdx
0x1800d7840  mov     r14, rcx
0x1800d7843  mov     [rsp+8B0h+var_838], rcx
0x1800d7848  xor     r15d, r15d
0x1800d784b  mov     [r9], r15
0x1800d784e  mov     [rbp+7B0h+var_7E8], r15
0x1800d7852  mov     [rbp+7B0h+var_800], r15
0x1800d7856  test    r8, r8
0x1800d7859  jz      loc_1800D8735
0x1800d785f  mov     rax, [r8]
0x1800d7862  lea     r8, [rbp+7B0h+var_800]
0x1800d7866  lea     rdx, aFileSystemBind; "File System Bind Data"
0x1800d786d  mov     rcx, r12
0x1800d7870  mov     rax, [rax+50h]
0x1800d7874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7879  test    eax, eax
0x1800d787b  js      loc_1800D8735
0x1800d7881  mov     rcx, [rbp+7B0h+var_800]
0x1800d7885  mov     rax, [rcx]
0x1800d7888  lea     r8, [rbp+7B0h+var_7E8]
0x1800d788c  lea     rdx, _GUID_01e18d10_4d8b_11d2_855d_006008059367
0x1800d7893  mov     rax, [rax]
0x1800d7896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d789b  mov     ebx, eax
0x1800d789d  mov     rcx, [rbp+7B0h+var_800]
0x1800d78a1  mov     rdx, [rcx]
0x1800d78a4  mov     rax, [rdx+10h]
0x1800d78a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d78ad  test    ebx, ebx
0x1800d78af  js      loc_1800D8735
0x1800d78b5  xor     edx, edx; Val
0x1800d78b7  mov     r8d, 268h; Size
0x1800d78bd  lea     rcx, [rbp+7B0h+var_7C0]; void *
0x1800d78c1  call    memset_0
0x1800d78c6  mov     [rbp+7B0h+var_818], r15
0x1800d78ca  mov     rax, [r12]
0x1800d78ce  lea     r8, [rbp+7B0h+var_818]
0x1800d78d2  lea     rdx, aFoldersAsReadO; "Folders As Read Only"
0x1800d78d9  mov     rcx, r12
0x1800d78dc  mov     rax, [rax+50h]
0x1800d78e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d78e5  test    eax, eax
0x1800d78e7  jns     loc_1800D878C
0x1800d78ed  xor     r13b, r13b
0x1800d78f0  mov     [rsp+8B0h+var_860], r13b
0x1800d78f5  mov     ebx, r15d
0x1800d78f8  mov     [rsp+8B0h+var_850], ebx
0x1800d78fc  mov     [rbp+7B0h+var_818], r15
0x1800d7900  mov     rax, [r12]
0x1800d7904  lea     r8, [rbp+7B0h+var_818]
0x1800d7908  lea     rdx, aNovalidatefile; "NoValidateFilenameChars"
0x1800d790f  mov     rcx, r12
0x1800d7912  mov     rax, [rax+50h]
0x1800d7916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d791b  test    eax, eax
0x1800d791d  js      short loc_1800D7938
0x1800d791f  mov     ebx, 1
0x1800d7924  mov     [rsp+8B0h+var_850], ebx
0x1800d7928  mov     rcx, [rbp+7B0h+var_818]
0x1800d792c  mov     rax, [rcx]
0x1800d792f  mov     rax, [rax+10h]
0x1800d7933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7938  mov     [rbp+7B0h+var_7DC], r15d
0x1800d793c  mov     [rbp+7B0h+value], r15
0x1800d7940  mov     rax, [r12]
0x1800d7944  lea     r8, [rbp+7B0h+value]
0x1800d7948  lea     rdx, aFolderEnumMode; "Folder Enum Mode"
0x1800d794f  mov     rcx, r12
0x1800d7952  mov     rax, [rax+50h]
0x1800d7956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d795b  test    eax, eax
0x1800d795d  js      short loc_1800D79C0
0x1800d795f  mov     rcx, [rbp+7B0h+value]
0x1800d7963  mov     [rbp+7B0h+var_7DC], r15d
0x1800d7967  test    rcx, rcx
0x1800d796a  jz      short loc_1800D79B2
0x1800d796c  mov     [rbp+7B0h+var_800], r15
0x1800d7970  mov     rax, [rcx]
0x1800d7973  lea     r8, [rbp+7B0h+var_800]
0x1800d7977  lea     rdx, _GUID_6a9d9026_0e6e_464c_b000_42ecc07de673
0x1800d797e  mov     rax, [rax]
0x1800d7981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7986  test    eax, eax
0x1800d7988  js      short loc_1800D79AE
0x1800d798a  mov     rcx, [rbp+7B0h+var_800]
0x1800d798e  mov     rax, [rcx]
0x1800d7991  lea     rdx, [rbp+7B0h+var_7DC]
0x1800d7995  mov     rax, [rax+20h]
0x1800d7999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d799e  mov     rcx, [rbp+7B0h+var_800]
0x1800d79a2  mov     rax, [rcx]
0x1800d79a5  mov     rax, [rax+10h]
0x1800d79a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d79ae  mov     rcx, [rbp+7B0h+value]
0x1800d79b2  mov     rax, [rcx]
0x1800d79b5  mov     rax, [rax+10h]
0x1800d79b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d79be  xchg    ax, ax
0x1800d79c0  mov     [rbp+7B0h+var_794], r15w
0x1800d79c5  test    rdi, rdi
0x1800d79c8  jz      loc_1800D8228
0x1800d79ce  mov     edx, 5Ch ; '\'; wMatch
0x1800d79d3  mov     rcx, rdi; pszStart
0x1800d79d6  call    cs:__imp_StrChrW
0x1800d79dc  mov     r10, rax
0x1800d79df  test    rax, rax
0x1800d79e2  jz      loc_1800D7B13
0x1800d79e8  cmp     rax, rdi
0x1800d79eb  jbe     loc_1800D7AB8
0x1800d79f1  mov     rcx, rax
0x1800d79f4  sub     rcx, rdi
0x1800d79f7  sar     rcx, 1
0x1800d79fa  movsxd  rdx, ecx
0x1800d79fd  cmp     rdx, 7FFFFFFEh
0x1800d7a04  ja      loc_1800D8A5A
0x1800d7a0a  mov     r9d, 104h
0x1800d7a10  lea     r8, [rbp+7B0h+var_794]
0x1800d7a14  test    rdx, rdx
0x1800d7a17  jz      short loc_1800D7A36
0x1800d7a19  movzx   eax, word ptr [rdi]
0x1800d7a1c  test    ax, ax
0x1800d7a1f  jz      short loc_1800D7A36
0x1800d7a21  add     rdi, 2
0x1800d7a25  mov     [r8], ax
0x1800d7a29  add     r8, 2
0x1800d7a2d  dec     rdx
0x1800d7a30  sub     r9, 1
0x1800d7a34  jnz     short loc_1800D7A14
0x1800d7a36  lea     rcx, [r8-2]
0x1800d7a3a  test    r9, r9
0x1800d7a3d  cmovnz  rcx, r8
0x1800d7a41  mov     [rcx], r15w
0x1800d7a45  movzx   ecx, [rbp+7B0h+var_794]
0x1800d7a49  lea     rdi, [r10+2]
0x1800d7a4d  cmp     word ptr [rdi], 0
0x1800d7a51  cmovz   rdi, r15
0x1800d7a55  mov     r14d, r15d
0x1800d7a58  mov     [rbp+7B0h+var_7E0], r15d
0x1800d7a5c  test    ebx, ebx
0x1800d7a5e  jnz     loc_1800D7B69
0x1800d7a64  test    cx, cx
0x1800d7a67  jz      short loc_1800D7AB3
0x1800d7a69  cmp     cx, 2Eh ; '.'
0x1800d7a6d  jz      loc_1800D85C1
0x1800d7a73  mov     esi, 1
0x1800d7a78  lea     rbx, [rbp+7B0h+var_794]
0x1800d7a7c  nop     dword ptr [rax+00h]
0x1800d7a80  movzx   ecx, word ptr [rbx]
0x1800d7a83  test    cx, cx
0x1800d7a86  jz      short loc_1800D7AA6
0x1800d7a88  mov     edx, 1E4h
0x1800d7a8d  call    cs:__imp_PathIsValidCharW
0x1800d7a93  test    eax, eax
0x1800d7a95  jz      short loc_1800D7B00
0x1800d7a97  cmp     word ptr [rbx], 2Eh ; '.'
0x1800d7a9b  jz      short loc_1800D7B00
0x1800d7a9d  mov     esi, r15d
0x1800d7aa0  add     rbx, 2
0x1800d7aa4  jmp     short loc_1800D7A80
0x1800d7aa6  test    esi, esi
0x1800d7aa8  mov     rsi, [rsp+8B0h+var_840]
0x1800d7aad  jz      loc_1800D7B69
0x1800d7ab3  mov     [rbp+7B0h+var_794], r15w
0x1800d7ab8  mov     r14d, 80070057h
0x1800d7abe  mov     rcx, [rsi]; pv
0x1800d7ac1  call    cs:__imp_CoTaskMemFree
0x1800d7ac7  mov     [rsi], r15
0x1800d7aca  mov     rcx, [rbp+7B0h+var_7E8]
0x1800d7ace  mov     rax, [rcx]
0x1800d7ad1  mov     rax, [rax+10h]
0x1800d7ad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7ada  mov     eax, r14d
0x1800d7add  mov     rcx, [rbp+7B0h+var_50]
0x1800d7ae4  xor     rcx, rsp; StackCookie
0x1800d7ae7  call    __security_check_cookie
0x1800d7aec  add     rsp, 878h
0x1800d7af3  pop     r15
0x1800d7af5  pop     r14
0x1800d7af7  pop     r13
0x1800d7af9  pop     r12
0x1800d7afb  pop     rdi
0x1800d7afc  pop     rsi
0x1800d7afd  pop     rbx
0x1800d7afe  pop     rbp
0x1800d7aff  retn
0x1800d7b00  add     rbx, 2
0x1800d7b04  test    eax, eax
0x1800d7b06  jnz     loc_1800D7A80
0x1800d7b0c  mov     rsi, [rsp+8B0h+var_840]
0x1800d7b11  jmp     short loc_1800D7AB3
0x1800d7b13  mov     ecx, 7FFFFFFEh
0x1800d7b18  mov     edx, 104h
0x1800d7b1d  lea     r8, [rbp+7B0h+var_794]
0x1800d7b21  test    rcx, rcx
0x1800d7b24  jz      short loc_1800D7B43
0x1800d7b26  movzx   eax, word ptr [rdi]
0x1800d7b29  test    ax, ax
0x1800d7b2c  jz      short loc_1800D7B43
0x1800d7b2e  add     rdi, 2
0x1800d7b32  mov     [r8], ax
0x1800d7b36  add     r8, 2
0x1800d7b3a  dec     rcx
0x1800d7b3d  sub     rdx, 1
0x1800d7b41  jnz     short loc_1800D7B21
0x1800d7b43  lea     rcx, [r8-2]
0x1800d7b47  test    rdx, rdx
0x1800d7b4a  cmovnz  rcx, r8
0x1800d7b4e  mov     [rcx], r15w
0x1800d7b52  mov     r14d, 8007007Ah
0x1800d7b58  cmovnz  r14d, r15d
0x1800d7b5c  mov     [rbp+7B0h+var_7E0], r14d
0x1800d7b60  mov     rdi, r15
0x1800d7b63  jnz     loc_1800D8230
0x1800d7b69  test    r14d, r14d
0x1800d7b6c  jnz     loc_1800D8222
0x1800d7b72  mov     [rbp+7B0h+Src], r15
0x1800d7b76  mov     [rsp+8B0h+var_858], r15
0x1800d7b7b  test    rdi, rdi
0x1800d7b7e  jz      loc_1800D7CEA
0x1800d7b84  mov     eax, 10h
0x1800d7b89  test    r13b, r13b
0x1800d7b8c  mov     ecx, 11h
0x1800d7b91  cmovnz  eax, ecx
0x1800d7b94  mov     [rbp+7B0h+var_7C0], eax
0x1800d7b97  movzx   ebx, r13b
0x1800d7b9b  mov     [rbp+7B0h+var_818], 0
0x1800d7ba3  mov     rax, [r12]
0x1800d7ba7  lea     r8, [rbp+7B0h+var_818]
0x1800d7bab  lea     rdx, aWin7filesystem; "Win7FileSystemIdList"
0x1800d7bb2  mov     rcx, r12
0x1800d7bb5  mov     rax, [rax+50h]
0x1800d7bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7bbe  test    eax, eax
0x1800d7bc0  jns     loc_1800D876D
0x1800d7bc6  lea     rax, [rsp+8B0h+var_858]
0x1800d7bcb  mov     [rsp+8B0h+var_870], rax
0x1800d7bd0  mov     eax, [rbp+7B0h+var_7DC]
0x1800d7bd3  mov     [rsp+8B0h+var_878], eax
0x1800d7bd7  mov     [rsp+8B0h+var_880], ebx
0x1800d7bdb  mov     [rsp+8B0h+var_888], 0BEEF0000h
0x1800d7be3  mov     [rsp+8B0h+var_890], 0
0x1800d7bec  xor     r9d, r9d
0x1800d7bef  mov     r8, [rsi]
0x1800d7bf2  lea     rdx, [rbp+7B0h+var_7C0]
0x1800d7bf6  mov     rcx, [rsp+8B0h+var_838]
0x1800d7bfb  call    ?_CreateIDList@CFSFolder@@IEAAJPEBUtagWIN32_FIND_DATA_EX@@PEFBU_ITEMIDLIST_RELATIVE@@PEBG2W4IDLHID@@W4CREATE_IDLIST_FLAGS@@W4FOLDER_ENUM_MODE@@PEAPEAU_ITEMID_CHILD@@@Z; CFSFolder::_CreateIDList(tagWIN32_FIND_DATA_EX const *,_ITEMIDLIST_RELATIVE const *,ushort const *,ushort const *,IDLHID,CREATE_IDLIST_FLAGS,FOLDER_ENUM_MODE,_ITEMID_CHILD * *)
0x1800d7c00  mov     r14d, eax
0x1800d7c03  mov     r15, [rsp+8B0h+var_858]
0x1800d7c08  mov     [rbp+7B0h+Src], r15
0x1800d7c0c  test    r14d, r14d
0x1800d7c0f  js      loc_1800D8AD5
0x1800d7c15  mov     r12, [rsi]
0x1800d7c18  test    r15, r15
0x1800d7c1b  jz      loc_1800D81F9
0x1800d7c21  test    r12, r12
0x1800d7c24  jz      loc_1800D81F9
0x1800d7c2a  mov     rdx, r12
0x1800d7c2d  mov     r8d, 2
0x1800d7c33  movzx   ecx, word ptr [rdx]
0x1800d7c36  test    cx, cx
0x1800d7c39  jz      short loc_1800D7C43
0x1800d7c3b  add     r8d, ecx
0x1800d7c3e  add     rdx, rcx
0x1800d7c41  jnz     short loc_1800D7C33
0x1800d7c43  lea     r15d, [r8-2]
0x1800d7c47  mov     r13, [rbp+7B0h+Src]
0x1800d7c4b  mov     rdx, r13
0x1800d7c4e  mov     esi, 2
0x1800d7c53  movzx   ecx, word ptr [rdx]
0x1800d7c56  test    cx, cx
0x1800d7c59  jz      short loc_1800D7C62
0x1800d7c5b  add     esi, ecx
0x1800d7c5d  add     rdx, rcx
0x1800d7c60  jnz     short loc_1800D7C53
0x1800d7c62  lea     eax, [rsi+r15]
0x1800d7c66  mov     ebx, eax
0x1800d7c68  mov     ecx, eax; cb
0x1800d7c6a  call    WINRT_IMPL_CoTaskMemAlloc
0x1800d7c6f  mov     r14, rax
0x1800d7c72  test    rax, rax
0x1800d7c75  jz      short loc_1800D7CA1
0x1800d7c77  mov     r8d, ebx; Size
0x1800d7c7a  xor     edx, edx; Val
  ... truncated ...
```
