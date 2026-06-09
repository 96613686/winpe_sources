# CASFHeaderObjectv1::FixContentDescription(void)

- ea: `0x1800111f8`
- end: `0x1800122a9`
- name: `?FixContentDescription@CASFHeaderObjectv1@@IEAAJXZ`
- size: `4273`
- prototype: `__int64 __fastcall(CASFHeaderObjectv1 *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800136d0`

## callees

- `0x1800011c0`
- `0x1800011cc`
- `0x1800015d0`
- `0x1800111f8`
- `0x180030a00`
- `0x1800310c0`
- `0x180040010`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x180011ae2`
- `KERNEL32!MultiByteToWideChar` at `0x180011bac`
- `KERNEL32!MultiByteToWideChar` at `0x180011ae2`
- `KERNEL32!MultiByteToWideChar` at `0x180011bac`

## string_xrefs

- `0x1800116a2`: `Copyright`
- `0x180011bda`: `CopyrightURL`

## pseudocode

```c
__int64 __fastcall CASFHeaderObjectv1::FixContentDescription(CASFHeaderObjectv1 *this)
{
  __int64 v2; // rcx
  int v3; // ebx
  _WORD *v4; // r8
  void *v5; // rdi
  void *v6; // rax
  void *v7; // r14
  __int64 v8; // r8
  _WORD *v9; // r8
  void *v10; // rax
  __int64 v11; // r8
  _WORD *v12; // r8
  void *v13; // rax
  __int64 v14; // r8
  _WORD *v15; // r8
  void *v16; // rax
  __int64 v17; // r8
  _WORD *v18; // r8
  void *v19; // rax
  __int64 v20; // r8
  __int64 v21; // rcx
  __int64 v22; // rcx
  WCHAR *v23; // rax
  WCHAR *v24; // rbx
  __int64 v25; // r9
  __int64 v26; // r9
  __int64 v27; // rcx
  WCHAR *v28; // rax
  WCHAR *v29; // rbx
  __int64 v30; // r9
  __int64 v31; // r9
  void *v32; // rsi
  unsigned __int16 i; // r14
  void *v34; // rax
  __int64 v35; // rcx
  unsigned __int16 j; // r14
  void *v37; // rax
  __int64 v38; // rcx
  unsigned __int16 k; // r14
  void *v40; // rax
  __int64 v41; // rcx
  int lpWideCharStr; // [rsp+20h] [rbp-B9h]
  int lpWideCharStra; // [rsp+20h] [rbp-B9h]
  int lpWideCharStrb; // [rsp+20h] [rbp-B9h]
  int lpWideCharStrc; // [rsp+20h] [rbp-B9h]
  int lpWideCharStrd; // [rsp+20h] [rbp-B9h]
  int v48; // [rsp+38h] [rbp-A1h]
  int v49; // [rsp+38h] [rbp-A1h]
  int v50; // [rsp+38h] [rbp-A1h]
  int v51; // [rsp+38h] [rbp-A1h]
  int v52; // [rsp+38h] [rbp-A1h]
  _WORD v53[2]; // [rsp+60h] [rbp-79h] BYREF
  _WORD v54[2]; // [rsp+64h] [rbp-75h] BYREF
  _WORD v55[2]; // [rsp+68h] [rbp-71h] BYREF
  _DWORD v56[3]; // [rsp+6Ch] [rbp-6Dh] BYREF
  __int64 v57; // [rsp+78h] [rbp-61h] BYREF
  LPCCH lpMultiByteStr; // [rsp+80h] [rbp-59h] BYREF
  LPCCH v59; // [rsp+88h] [rbp-51h] BYREF
  __int64 v60; // [rsp+90h] [rbp-49h] BYREF
  __int64 v61; // [rsp+98h] [rbp-41h] BYREF
  __int64 v62; // [rsp+A0h] [rbp-39h] BYREF
  __int64 v63; // [rsp+A8h] [rbp-31h] BYREF
  __int64 v64; // [rsp+B0h] [rbp-29h] BYREF
  __int64 v65; // [rsp+B8h] [rbp-21h] BYREF
  __int64 v66; // [rsp+C0h] [rbp-19h] BYREF
  __int64 v67; // [rsp+C8h] [rbp-11h] BYREF
  _WORD v68[2]; // [rsp+D0h] [rbp-9h] BYREF
  _WORD v69[2]; // [rsp+D4h] [rbp-5h] BYREF
  _WORD v70[2]; // [rsp+D8h] [rbp-1h] BYREF
  int v71; // [rsp+DCh] [rbp+3h] BYREF
  _WORD v72[2]; // [rsp+E0h] [rbp+7h] BYREF
  int v73; // [rsp+E4h] [rbp+Bh] BYREF

  v54[0] = 0;
  v2 = *((_QWORD *)this + 5);
  v53[0] = 0;
  v68[0] = -1;
  v55[0] = 0;
  memset(v56, 0, sizeof(v56));
  v69[0] = 0;
  v70[0] = 0;
  v71 = 0;
  v57 = 0;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v3 = ASFGetHeaderObject(v2, &CLSID_ASFLanguageListObject, &IID_IASFLanguageListObject, &v65);
  if ( v3 < 0 )
    goto LABEL_125;
  v72[0] = 0;
  v3 = (*(__int64 (__fastcall **)(__int64, _WORD *))(*(_QWORD *)v65 + 96LL))(v65, v72);
  if ( v65 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
    v65 = 0;
  }
  if ( v3 < 0 )
    goto LABEL_125;
  v3 = ASFGetHeaderObject(*((_QWORD *)this + 5), &CLSID_ASFMetaDataObject, &IID_IASFMetaDataObject, &v56[1]);
  if ( v3 < 0 )
    goto LABEL_125;
  if ( (int)ASFFindHeaderObject(
              *((_QWORD *)this + 5),
              &CLSID_ASFContentDescriptionObjectv1,
              &IID_IASFContentDescriptionObjectv1,
              &v57) >= 0 )
  {
    v4 = v54;
    LOBYTE(v4) = 2;
    if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, _WORD *, _QWORD, _WORD, _QWORD, _WORD *, _WORD, _QWORD, _WORD *, _QWORD))(*(_QWORD *)v57 + 104LL))(
           v57,
           0,
           v4,
           0,
           0,
           0,
           v54,
           0,
           0,
           v53,
           0) == -1072887855
      && v53[0] )
    {
      v5 = operator new[](saturated_mul(v54[0], 2u));
      v6 = operator new[](saturated_mul(v53[0], 2u));
      v7 = v6;
      if ( !v5 || !v6 )
        goto LABEL_57;
      LOWORD(v48) = v53[0];
      v8 = v54[0];
      LOWORD(lpWideCharStra) = v54[0];
      LOBYTE(v8) = 2;
      if ( (*(int (__fastcall **)(__int64, _QWORD, __int64, _QWORD, int, void *, _WORD *, int, void *, _WORD *, _QWORD))(*(_QWORD *)v57 + 104LL))(
             v57,
             0,
             v8,
             0,
             lpWideCharStra,
             v5,
             v54,
             v48,
             v6,
             v53,
             0) >= 0 )
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, const wchar_t *, int, int, void *))(**(_QWORD **)&v56[1] + 112LL))(
          *(_QWORD *)&v56[1],
          0,
          0,
          L"Title",
          1,
          2 * v53[0],
          v7);
      operator delete(v5);
      operator delete(v7);
    }
    v9 = v54;
    LOWORD(v48) = 0;
    LOBYTE(v9) = 1;
    LOWORD(lpWideCharStra) = 0;
    if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, _WORD *, _QWORD, int, _QWORD, _WORD *, int, _QWORD, _WORD *, _QWORD))(*(_QWORD *)v57 + 104LL))(
           v57,
           0,
           v9,
           0,
           lpWideCharStra,
           0,
           v54,
           v48,
           0,
           v53,
           0) == -1072887855
      && v53[0] )
    {
      v5 = operator new[](saturated_mul(v54[0], 2u));
      v10 = operator new[](saturated_mul(v53[0], 2u));
      v7 = v10;
      if ( !v5 || !v10 )
        goto LABEL_57;
      LOWORD(v49) = v53[0];
      v11 = v54[0];
      LOWORD(lpWideCharStrb) = v54[0];
      LOBYTE(v11) = 1;
      if ( (*(int (__fastcall **)(__int64, _QWORD, __int64, _QWORD, int, void *, _WORD *, int, void *, _WORD *, _QWORD))(*(_QWORD *)v57 + 104LL))(
             v57,
             0,
             v11,
             0,
             lpWideCharStrb,
             v5,
             v54,
             v49,
             v10,
             v53,
             0) >= 0 )
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, const wchar_t *, int, int, void *))(**(_QWORD **)&v56[1] + 112LL))(
          *(_QWORD *)&v56[1],
          0,
          0,
          L"Author",
          1,
          2 * v53[0],
          v7);
      operator delete(v5);
      operator delete(v7);
    }
    v12 = v54;
    LOWORD(v49) = 0;
    LOBYTE(v12) = 3;
    LOWORD(lpWideCharStrb) = 0;
    if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, _WORD *, _QWORD, int, _QWORD, _WORD *, int, _QWORD, _WORD *, _QWORD))(*(_QWORD *)v57 + 104LL))(
           v57,
           0,
           v12,
           0,
           lpWideCharStrb,
           0,
           v54,
           v49,
           0,
           v53,
           0) == -1072887855
      && v53[0] )
    {
      v5 = operator new[](saturated_mul(v54[0], 2u));
      v13 = operator new[](saturated_mul(v53[0], 2u));
      v7 = v13;
      if ( !v5 || !v13 )
        goto LABEL_57;
      LOWORD(v50) = v53[0];
      v14 = v54[0];
      LOWORD(lpWideCharStrc) = v54[0];
      LOBYTE(v14) = 3;
      if ( (*(int (__fastcall **)(__int64, _QWORD, __int64, _QWORD, int, void *, _WORD *, int, void *, _WORD *, _QWORD))(*(_QWORD *)v57 + 104LL))(
             v57,
             0,
             v14,
             0,
             lpWideCharStrc,
             v5,
             v54,
             v50,
             v13,
             v53,
             0) >= 0 )
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, const wchar_t *, int, int, void *))(**(_QWORD **)&v56[1] + 112LL))(
          *(_QWORD *)&v56[1],
          0,
          0,
          L"Copyright",
          1,
          2 * v53[0],
          v7);
      operator delete(v5);
      operator delete(v7);
    }
    v15 = v54;
    LOWORD(v50) = 0;
    LOBYTE(v15) = 4;
    LOWORD(lpWideCharStrc) = 0;
    if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, _WORD *, _QWORD, int, _QWORD, _WORD *, int, _QWORD, _WORD *, _QWORD))(*(_QWORD *)v57 + 104LL))(
           v57,
           0,
           v15,
           0,
           lpWideCharStrc,
           0,
           v54,
           v50,
           0,
           v53,
           0) == -1072887855
      && v53[0] )
    {
      v5 = operator new[](saturated_mul(v54[0], 2u));
      v16 = operator new[](saturated_mul(v53[0], 2u));
      v7 = v16;
      if ( !v5 || !v16 )
        goto LABEL_57;
      LOWORD(v51) = v53[0];
      v17 = v54[0];
      LOWORD(lpWideCharStrd) = v54[0];
      LOBYTE(v17) = 4;
      if ( (*(int (__fastcall **)(__int64, _QWORD, __int64, _QWORD, int, void *, _WORD *, int, void *, _WORD *, _QWORD))(*(_QWORD *)v57 + 104LL))(
             v57,
             0,
             v17,
             0,
             lpWideCharStrd,
             v5,
             v54,
             v51,
             v16,
             v53,
             0) >= 0 )
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, const wchar_t *, int, int, void *))(**(_QWORD **)&v56[1] + 112LL))(
          *(_QWORD *)&v56[1],
          0,
          0,
          L"Description",
          1,
          2 * v53[0],
          v7);
      operator delete(v5);
      operator delete(v7);
    }
    v18 = v54;
    LOWORD(v51) = 0;
    LOBYTE(v18) = 74;
    LOWORD(lpWideCharStrd) = 0;
    if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, _WORD *, _QWORD, int, _QWORD, _WORD *, int, _QWORD, _WORD *, _QWORD))(*(_QWORD *)v57 + 104LL))(
           v57,
           0,
           v18,
           0,
           lpWideCharStrd,
           0,
           v54,
           v51,
           0,
           v53,
           0) != -1072887855
      || !v53[0] )
    {
LABEL_42:
      v21 = *((_QWORD *)this + 11);
      v66 = 0;
      (*(void (__fastcall **)(__int64, GUID *, _QWORD, __int64 *))(*(_QWORD *)v21 + 48LL))(
        v21,
        &CLSID_ASFContentDescriptionObjectv1,
        0,
        &v66);
      if ( v66 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
        v66 = 0;
      }
      goto LABEL_44;
    }
    v5 = operator new[](saturated_mul(v54[0], 2u));
    v19 = operator new[](saturated_mul(v53[0], 2u));
    v7 = v19;
    if ( v5 && v19 )
    {
      LOWORD(v52) = v53[0];
      v20 = v54[0];
      LOWORD(lpWideCharStr) = v54[0];
      LOBYTE(v20) = 74;
      if ( (*(int (__fastcall **)(__int64, _QWORD, __int64, _QWORD, int, void *, _WORD *, int, void *, _WORD *, _QWORD))(*(_QWORD *)v57 + 104LL))(
             v57,
             0,
             v20,
             0,
             lpWideCharStr,
             v5,
             v54,
             v52,
             v19,
             v53,
             0) >= 0 )
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, const wchar_t *, int, int, void *))(**(_QWORD **)&v56[1] + 112LL))(
          *(_QWORD *)&v56[1],
          0,
          0,
          L"Rating",
          1,
          2 * v53[0],
          v7);
      operator delete(v5);
      operator delete(v7);
      goto LABEL_42;
    }
LABEL_57:
    v3 = -2147024882;
LABEL_121:
    if ( v5 )
      operator delete(v5);
    if ( v7 )
      operator delete(v7);
    goto LABEL_125;
  }
LABEL_44:
  if ( (int)ASFFindHeaderObject(
              *((_QWORD *)this + 5),
              &CLSID_ASFContentBrandingObjectv1,
              &IID_IASFContentBrandingObjectv1,
              &v64) < 0 )
    goto LABEL_73;
  v73 = 0;
  v3 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v64 + 80LL))(v64, &v73);
  if ( v3 >= 0 )
  {
    if ( v73 )
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, const wchar_t *, int, int, int *))(**(_QWORD **)&v56[1] + 112LL))(
        *(_QWORD *)&v56[1],
        0,
        0,
        L"BannerImageType",
        2,
        4,
        &v73);
    v67 = 0;
    LODWORD(v60) = 0;
    v3 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *))(*(_QWORD *)v64 + 88LL))(v64, &v60, &v67);
    if ( v3 >= 0 )
    {
      if ( v67 )
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, const wchar_t *, _DWORD, _DWORD, __int64))(**(_QWORD **)&v56[1]
                                                                                                 + 112LL))(
          *(_QWORD *)&v56[1],
          0,
          0,
          L"BannerImageData",
          0,
          (unsigned __int16)v60,
          v67);
      lpMultiByteStr = 0;
      v3 = (*(__int64 (__fastcall **)(__int64, LPCCH *))(*(_QWORD *)v64 + 96LL))(v64, &lpMultiByteStr);
      if ( v3 >= 0 )
      {
        if ( lpMultiByteStr )
        {
          v22 = -1;
          do
            ++v22;
          while ( lpMultiByteStr[v22] );
          v23 = (WCHAR *)operator new[](saturated_mul(v22 + 1, 2u));
          v24 = v23;
          if ( !v23 )
            goto LABEL_56;
          v25 = -1;
          do
            ++v25;
          while ( lpMultiByteStr[v25] );
          MultiByteToWideChar(0, 0, lpMultiByteStr, v25 + 1, v23, v25 + 1);
          v26 = -1;
          do
            ++v26;
          while ( v24[v26] );
          (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, const wchar_t *, int, _DWORD, WCHAR *))(**(_QWORD **)&v56[1]
                                                                                                + 112LL))(
            *(_QWORD *)&v56[1],
            0,
            0,
            L"BannerImageURL",
            1,
            2 * v26 + 2,
            v24);
          operator delete(v24);
        }
        v59 = 0;
        v3 = (*(__int64 (__fastcall **)(__int64, LPCCH *))(*(_QWORD *)v64 + 104LL))(v64, &v59);
        if ( v3 >= 0 )
        {
          if ( v59 )
          {
            v27 = -1;
            do
              ++v27;
            while ( v59[v27] );
            v28 = (WCHAR *)operator new[](saturated_mul(v27 + 1, 2u));
            v29 = v28;
            if ( !v28 )
            {
LABEL_56:
              v3 = -2147024882;
              goto LABEL_125;
            }
            v30 = -1;
            do
              ++v30;
            while ( v59[v30] );
            MultiByteToWideChar(0, 0, v59, v30 + 1, v28, v30 + 1);
            v31 = -1;
            do
              ++v31;
            while ( v29[v31] );
            (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, const wchar_t *, int, _DWORD, WCHAR *))(**(_QWORD **)&v56[1]
                                                                                                  + 112LL))(
              *(_QWORD *)&v56[1],
              0,
              0,
              L"CopyrightURL",
              1,
              2 * v31 + 2,
              v29);
            operator delete(v29);
          }
LABEL_73:
          v32 = 0;
          v3 = ASFFindHeaderObject(
                 *((_QWORD *)this + 5),
                 &CLSID_ASFExtendedContentDescriptionObjectv1,
                 &IID_IASFMetaDataObject,
                 &v61);
          v5 = 0;
          if ( v3 >= 0 )
          {
            v69[0] = 0;
            (*(void (__fastcall **)(__int64, _WORD *))(*(_QWORD *)v61 + 80LL))(v61, v69);
            for ( i = 0; i < v69[0]; ++i )
            {
              v68[0] = -1;
              v55[0] = 0;
              LOWORD(lpWideCharStr) = 0;
              v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, _WORD *, _WORD *, int, _QWORD, _WORD *, int *, _DWORD, _QWORD, _DWORD *))(*(_QWORD *)v61 + 96LL))(
                     v61,
                     i,
                     v68,
                     v70,
                     lpWideCharStr,
                     0,
                     v55,
                     &v71,
                     v56[0],
                     0,
                     v56);
              if ( v3 >= 0 )
              {
                v5 = operator new[](saturated_mul(v55[0], 2u));
                v34 = operator new[](v56[0]);
                v32 = v34;
                if ( !v5 || !v34 )
                {
LABEL_114:
                  v3 = -2147024882;
                  goto LABEL_119;
                }
                v68[0] = -1;
                LOWORD(lpWideCharStr) = v55[0];
                v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, _WORD *, _WORD *, int, void *, _WORD *, int *, _DWORD, void *, _DWORD *))(*(_QWORD *)v61 + 96LL))(
                       v61,
                       i,
                       v68,
                       v70,
                       lpWideCharStr,
                       v5,
                       v55,
                       &v71,
                       v56[0],
                       v34,
                       v56);
                if ( v3 >= 0 )
                  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, void *, int, _DWORD, void *))(**(_QWORD **)&v56[1]
                                                                                              + 112LL))(
                    *(_QWORD *)&v56[1],
                    v68[0],
                    0,
                    v5,
                    v71,
                    v56[0],
                    v32);
                operator delete(v5);
                operator delete(v32);
              }
              v32 = 0;
              v5 = 0;
            }
            if ( v3 < 0 )
              goto LABEL_119;
            v35 = *((_QWORD *)this + 11);
            v59 = 0;
            (*(void (__fastcall **)(__int64, GUID *, _QWORD, LPCCH *))(*(_QWORD *)v35 + 48LL))(
              v35,
              &CLSID_ASFExtendedContentDescriptionObjectv1,
              0,
              &v59);
            if ( v59 )
            {
              (*(void (__fastcall **)(LPCCH))(*(_QWORD *)v59 + 16LL))(v59);
              v59 = 0;
            }
          }
          v3 = ASFFindHeaderObject(*((_QWORD *)this + 5), &CLSID_ASFMetaDataObjectv1, &IID_IASFMetaDataObject, &v62);
          if ( v3 >= 0 )
          {
            v69[0] = 0;
            (*(void (__fastcall **)(__int64, _WORD *))(*(_QWORD *)v62 + 80LL))(v62, v69);
            for ( j = 0; j < v69[0]; ++j )
            {
              v68[0] = -1;
              v55[0] = 0;
              LOWORD(lpWideCharStr) = 0;
              v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, _WORD *, _WORD *, int, _QWORD, _WORD *, int *, _DWORD, _QWORD, _DWORD *))(*(_QWORD *)v62 + 96LL))(
                     v62,
                     j,
                     v68,
                     v70,
                     lpWideCharStr,
                     0,
                     v55,
                     &v71,
                     v56[0],
                     0,
                     v56);
              if ( v3 >= 0 )
              {
                if ( v70[0] && v70[0] >= v72[0] )
                {
LABEL_98:
                  v3 = -1072887838;
                  goto LABEL_125;
                }
                v5 = operator new[](saturated_mul(v55[0], 2u));
                v37 = operator new[](v56[0]);
                v32 = v37;
                if ( !v5 || !v37 )
                  goto LABEL_114;
                v68[0] = -1;
                LOWORD(lpWideCharStr) = v55[0];
                v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, _WORD *, _WORD *, int, void *, _WORD *, int *, _DWORD, void *, _DWORD *))(*(_QWORD *)v62 + 96LL))(
                       v62,
                       j,
                       v68,
                       v70,
                       lpWideCharStr,
                       v5,
                       v55,
                       &v71,
                       v56[0],
                       v37,
                       v56);
                if ( v3 >= 0 )
                  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, void *, int, _DWORD, void *))(**(_QWORD **)&v56[1]
                                                                                              + 112LL))(
                    *(_QWORD *)&v56[1],
                    v68[0],
                    0,
                    v5,
                    v71,
                    v56[0],
                    v32);
                operator delete(v5);
                operator delete(v32);
              }
              v5 = 0;
              v32 = 0;
            }
            if ( v3 < 0 )
              goto LABEL_119;
            v38 = *((_QWORD *)this + 11);
            lpMultiByteStr = 0;
            (*(void (__fastcall **)(__int64, GUID *, _QWORD, LPCCH *))(*(_QWORD *)v38 + 48LL))(
              v38,
              &CLSID_ASFMetaDataObjectv1,
              0,
              &lpMultiByteStr);
            if ( lpMultiByteStr )
            {
              (*(void (__fastcall **)(LPCCH))(*(_QWORD *)lpMultiByteStr + 16LL))(lpMultiByteStr);
              lpMultiByteStr = 0;
            }
          }
          v3 = ASFFindHeaderObject(
                 *((_QWORD *)this + 5),
                 &CLSID_ASFMetaDataLibraryObjectv1,
                 &IID_IASFMetaDataObject,
                 &v63);
          if ( v3 >= 0 )
          {
            v69[0] = 0;
            (*(void (__fastcall **)(__int64, _WORD *))(*(_QWORD *)v63 + 80LL))(v63, v69);
            for ( k = 0; k < v69[0]; ++k )
            {
              v68[0] = -1;
              v55[0] = 0;
              LOWORD(lpWideCharStr) = 0;
              v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, _WORD *, _WORD *, int, _QWORD, _WORD *, int *, _DWORD, _QWORD, _DWORD *))(*(_QWORD *)v63 + 136LL))(
                     v63,
                     k,
                     v68,
                     v70,
                     lpWideCharStr,
                     0,
                     v55,
                     &v71,
                     v56[0],
                     0,
                     v56);
              if ( v3 >= 0 )
              {
                if ( v70[0] && v70[0] >= v72[0] )
                  goto LABEL_98;
                v5 = operator new[](saturated_mul(v55[0], 2u));
                v40 = operator new[](v56[0]);
                v32 = v40;
                if ( !v5 || !v40 )
                  goto LABEL_114;
                v68[0] = -1;
                LOWORD(lpWideCharStr) = v55[0];
                v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, _WORD *, _WORD *, int, void *, _WORD *, int *, _DWORD, void *, _DWORD *))(*(_QWORD *)v63 + 136LL))(
                       v63,
                       k,
                       v68,
                       v70,
                       lpWideCharStr,
                       v5,
                       v55,
                       &v71,
                       v56[0],
                       v40,
                       v56);
                if ( v3 >= 0 )
                  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, void *, int, _DWORD, void *))(**(_QWORD **)&v56[1]
                                                                                              + 112LL))(
                    *(_QWORD *)&v56[1],
                    v68[0],
                    v70[0],
                    v5,
                    v71,
                    v56[0],
                    v32);
                operator delete(v5);
                operator delete(v32);
              }
              v5 = 0;
              v32 = 0;
            }
            if ( v3 < 0 )
              goto LABEL_119;
            v41 = *((_QWORD *)this + 11);
            v60 = 0;
            (*(void (__fastcall **)(__int64, GUID *, _QWORD, __int64 *))(*(_QWORD *)v41 + 48LL))(
              v41,
              &CLSID_ASFMetaDataLibraryObjectv1,
              0,
              &v60);
            if ( v60 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
              v60 = 0;
            }
          }
          v3 = 0;
LABEL_119:
          v7 = 0;
          if ( v32 )
            operator delete(v32);
          goto LABEL_121;
        }
      }
    }
  }
LABEL_125:
  if ( *(_QWORD *)&v56[1] )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v56[1] + 16LL))(*(_QWORD *)&v56[1]);
    *(_QWORD *)&v56[1] = 0;
  }
  if ( v57 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
    v57 = 0;
  }
  if ( v61 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
    v61 = 0;
  }
  if ( v62 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
    v62 = 0;
  }
  if ( v63 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
    v63 = 0;
  }
  if ( v64 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800111f8  push    rbp
0x1800111fa  push    rbx
0x1800111fb  push    rsi
0x1800111fc  push    rdi
0x1800111fd  push    r12
0x1800111ff  push    r13
0x180011201  push    r14
0x180011203  push    r15
0x180011205  lea     rbp, [rsp-1Fh]
0x18001120a  sub     rsp, 0F8h
0x180011211  mov     rax, cs:__security_cookie
0x180011218  xor     rax, rsp
0x18001121b  mov     [rbp+57h+var_48], rax
0x18001121f  xor     r12d, r12d
0x180011222  lea     r9, [rbp+57h+var_78]
0x180011226  mov     r15, rcx
0x180011229  mov     [rbp+57h+var_CC], r12w
0x18001122e  mov     rcx, [rcx+28h]
0x180011232  lea     r8, IID_IASFLanguageListObject
0x180011239  mov     eax, 0FFFFh
0x18001123e  mov     [rbp+57h+var_D0], r12w
0x180011243  lea     rdx, CLSID_ASFLanguageListObject
0x18001124a  mov     [rbp+57h+var_60], ax
0x18001124e  mov     [rbp+57h+var_C8], r12w
0x180011253  mov     dword ptr [rbp+57h+var_C4], r12d
0x180011257  mov     [rbp+57h+var_5C], r12w
0x18001125c  mov     [rbp+57h+var_58], r12w
0x180011261  mov     [rbp+57h+var_54], r12d
0x180011265  mov     qword ptr [rbp+57h+var_C4+4], r12
0x180011269  mov     [rbp+57h+var_B8], r12
0x18001126d  mov     [rbp+57h+var_98], r12
0x180011271  mov     [rbp+57h+var_90], r12
0x180011275  mov     [rbp+57h+var_88], r12
0x180011279  mov     [rbp+57h+var_80], r12
0x18001127d  mov     [rbp+57h+var_78], r12
0x180011281  call    ASFGetHeaderObject
0x180011286  mov     ebx, eax
0x180011288  test    eax, eax
0x18001128a  js      loc_1800121F5
0x180011290  mov     rcx, [rbp+57h+var_78]
0x180011294  lea     rdx, [rbp+57h+var_50]
0x180011298  mov     [rbp+57h+var_50], r12w
0x18001129d  mov     rax, [rcx]
0x1800112a0  mov     rax, [rax+60h]
0x1800112a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112a9  mov     rcx, [rbp+57h+var_78]
0x1800112ad  mov     ebx, eax
0x1800112af  test    rcx, rcx
0x1800112b2  jz      short loc_1800112C4
0x1800112b4  mov     rax, [rcx]
0x1800112b7  mov     rax, [rax+10h]
0x1800112bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112c0  mov     [rbp+57h+var_78], r12
0x1800112c4  test    ebx, ebx
0x1800112c6  js      loc_1800121F5
0x1800112cc  mov     rcx, [r15+28h]
0x1800112d0  lea     r9, [rbp+57h+var_C4+4]
0x1800112d4  lea     r8, IID_IASFMetaDataObject
0x1800112db  lea     rdx, CLSID_ASFMetaDataObject
0x1800112e2  call    ASFGetHeaderObject
0x1800112e7  mov     ebx, eax
0x1800112e9  test    eax, eax
0x1800112eb  js      loc_1800121F5
0x1800112f1  mov     rcx, [r15+28h]
0x1800112f5  lea     r9, [rbp+57h+var_B8]
0x1800112f9  lea     r8, IID_IASFContentDescriptionObjectv1
0x180011300  lea     rdx, CLSID_ASFContentDescriptionObjectv1
0x180011307  call    ASFFindHeaderObject
0x18001130c  mov     r14d, 2
0x180011312  or      r13, 0FFFFFFFFFFFFFFFFh
0x180011316  lea     esi, [r14-1]
0x18001131a  test    eax, eax
0x18001131c  js      loc_180011975
0x180011322  mov     rcx, [rbp+57h+var_B8]
0x180011326  lea     r8, [rbp+57h+var_CC]
0x18001132a  mov     [rsp+130h+var_E0], r12
0x18001132f  lea     r10, [rbp+57h+var_D0]
0x180011333  mov     [rsp+130h+var_E8], r10
0x180011338  xor     edx, edx
0x18001133a  mov     [rsp+130h+var_F0], r12
0x18001133f  xor     r9d, r9d
0x180011342  mov     rax, [rcx]
0x180011345  mov     word ptr [rsp+130h+var_F8], r12w
0x18001134b  mov     [rsp+130h+var_100], r8
0x180011350  mov     r8b, r14b
0x180011353  mov     qword ptr [rsp+130h+cchWideChar], r12
0x180011358  mov     rax, [rax+68h]
0x18001135c  mov     word ptr [rsp+130h+lpWideCharStr], r12w
0x180011362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011367  mov     ebx, 0C00D07D1h
0x18001136c  cmp     eax, ebx
0x18001136e  jnz     loc_180011461
0x180011374  cmp     r12w, [rbp+57h+var_D0]
0x180011379  jnb     loc_180011461
0x18001137f  movzx   ecx, [rbp+57h+var_CC]
0x180011383  mov     eax, r14d
0x180011386  mul     rcx
0x180011389  cmovb   rax, r13
0x18001138d  mov     rcx, rax; unsigned __int64
0x180011390  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180011395  movzx   ecx, [rbp+57h+var_D0]
0x180011399  mov     rdi, rax
0x18001139c  mov     eax, r14d
0x18001139f  mul     rcx
0x1800113a2  cmovb   rax, r13
0x1800113a6  mov     rcx, rax; unsigned __int64
0x1800113a9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800113ae  mov     r14, rax
0x1800113b1  test    rdi, rdi
0x1800113b4  jz      loc_180011AB7
0x1800113ba  test    rax, rax
0x1800113bd  jz      loc_180011AB7
0x1800113c3  mov     r10, [rbp+57h+var_B8]
0x1800113c7  xor     edx, edx
0x1800113c9  movzx   r8d, [rbp+57h+var_D0]
0x1800113ce  xor     r9d, r9d
0x1800113d1  mov     [rsp+130h+var_E0], r12
0x1800113d6  mov     rcx, [r10]
0x1800113d9  mov     rax, [rcx+68h]
0x1800113dd  lea     rcx, [rbp+57h+var_D0]
0x1800113e1  mov     [rsp+130h+var_E8], rcx
0x1800113e6  lea     rcx, [rbp+57h+var_CC]
0x1800113ea  mov     [rsp+130h+var_F0], r14
0x1800113ef  mov     word ptr [rsp+130h+var_F8], r8w
0x1800113f5  movzx   r8d, [rbp+57h+var_CC]
0x1800113fa  mov     [rsp+130h+var_100], rcx
0x1800113ff  mov     rcx, r10
0x180011402  mov     qword ptr [rsp+130h+cchWideChar], rdi
0x180011407  mov     word ptr [rsp+130h+lpWideCharStr], r8w
0x18001140d  mov     r8b, 2
0x180011410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011415  test    eax, eax
0x180011417  js      short loc_18001144B
0x180011419  movzx   r9d, [rbp+57h+var_D0]
0x18001141e  xor     r8d, r8d
0x180011421  mov     rcx, qword ptr [rbp+57h+var_C4+4]
0x180011425  add     r9d, r9d
0x180011428  mov     [rsp+130h+var_100], r14
0x18001142d  xor     edx, edx
0x18001142f  mov     [rsp+130h+cchWideChar], r9d
0x180011434  lea     r9, aTitle; "Title"
0x18001143b  mov     dword ptr [rsp+130h+lpWideCharStr], esi
0x18001143f  mov     rax, [rcx]
0x180011442  mov     rax, [rax+70h]
0x180011446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001144b  mov     rcx, rdi; Block
0x18001144e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011453  mov     rcx, r14; Block
0x180011456  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001145b  mov     r14d, 2
0x180011461  mov     rcx, [rbp+57h+var_B8]
0x180011465  lea     r8, [rbp+57h+var_CC]
0x180011469  mov     [rsp+130h+var_E0], r12
0x18001146e  lea     r10, [rbp+57h+var_D0]
0x180011472  mov     [rsp+130h+var_E8], r10
0x180011477  xor     edx, edx
0x180011479  mov     [rsp+130h+var_F0], r12
0x18001147e  xor     r9d, r9d
0x180011481  mov     rax, [rcx]
0x180011484  mov     word ptr [rsp+130h+var_F8], r12w
0x18001148a  mov     [rsp+130h+var_100], r8
0x18001148f  mov     r8b, sil
0x180011492  mov     qword ptr [rsp+130h+cchWideChar], r12
0x180011497  mov     rax, [rax+68h]
0x18001149b  mov     word ptr [rsp+130h+lpWideCharStr], r12w
0x1800114a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114a6  cmp     eax, ebx
0x1800114a8  jnz     loc_180011592
0x1800114ae  cmp     r12w, [rbp+57h+var_D0]
0x1800114b3  jnb     loc_180011592
0x1800114b9  movzx   ecx, [rbp+57h+var_CC]
0x1800114bd  mov     rax, r14
0x1800114c0  mul     rcx
0x1800114c3  cmovb   rax, r13
0x1800114c7  mov     rcx, rax; unsigned __int64
0x1800114ca  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800114cf  movzx   ecx, [rbp+57h+var_D0]
0x1800114d3  mov     rdi, rax
0x1800114d6  mov     rax, r14
0x1800114d9  mul     rcx
0x1800114dc  cmovb   rax, r13
0x1800114e0  mov     rcx, rax; unsigned __int64
0x1800114e3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800114e8  mov     r14, rax
0x1800114eb  test    rdi, rdi
0x1800114ee  jz      loc_180011AB7
0x1800114f4  test    rax, rax
0x1800114f7  jz      loc_180011AB7
0x1800114fd  mov     rcx, [rbp+57h+var_B8]
0x180011501  lea     r8, [rbp+57h+var_D0]
0x180011505  mov     [rsp+130h+var_E0], r12
0x18001150a  xor     edx, edx
0x18001150c  mov     [rsp+130h+var_E8], r8
0x180011511  xor     r9d, r9d
0x180011514  movzx   r8d, [rbp+57h+var_D0]
0x180011519  mov     rax, [rcx]
0x18001151c  mov     [rsp+130h+var_F0], r14
0x180011521  mov     word ptr [rsp+130h+var_F8], r8w
0x180011527  lea     r8, [rbp+57h+var_CC]
0x18001152b  mov     [rsp+130h+var_100], r8
0x180011530  movzx   r8d, [rbp+57h+var_CC]
0x180011535  mov     rax, [rax+68h]
0x180011539  mov     qword ptr [rsp+130h+cchWideChar], rdi
0x18001153e  mov     word ptr [rsp+130h+lpWideCharStr], r8w
0x180011544  mov     r8b, sil
0x180011547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001154c  test    eax, eax
0x18001154e  js      short loc_180011582
0x180011550  movzx   r9d, [rbp+57h+var_D0]
0x180011555  xor     r8d, r8d
0x180011558  mov     rcx, qword ptr [rbp+57h+var_C4+4]
0x18001155c  add     r9d, r9d
0x18001155f  mov     [rsp+130h+var_100], r14
0x180011564  xor     edx, edx
0x180011566  mov     [rsp+130h+cchWideChar], r9d
0x18001156b  lea     r9, aAuthor; "Author"
0x180011572  mov     dword ptr [rsp+130h+lpWideCharStr], esi
0x180011576  mov     rax, [rcx]
0x180011579  mov     rax, [rax+70h]
0x18001157d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011582  mov     rcx, rdi; Block
0x180011585  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001158a  mov     rcx, r14; Block
0x18001158d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011592  mov     rcx, [rbp+57h+var_B8]
0x180011596  lea     r8, [rbp+57h+var_CC]
0x18001159a  mov     [rsp+130h+var_E0], r12
0x18001159f  lea     r10, [rbp+57h+var_D0]
0x1800115a3  mov     [rsp+130h+var_E8], r10
0x1800115a8  xor     edx, edx
0x1800115aa  mov     [rsp+130h+var_F0], r12
0x1800115af  xor     r9d, r9d
0x1800115b2  mov     rax, [rcx]
0x1800115b5  mov     word ptr [rsp+130h+var_F8], r12w
0x1800115bb  mov     [rsp+130h+var_100], r8
0x1800115c0  mov     r8b, 3
0x1800115c3  mov     qword ptr [rsp+130h+cchWideChar], r12
0x1800115c8  mov     rax, [rax+68h]
0x1800115cc  mov     word ptr [rsp+130h+lpWideCharStr], r12w
0x1800115d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115d7  cmp     eax, ebx
0x1800115d9  jnz     loc_1800116C9
0x1800115df  cmp     r12w, [rbp+57h+var_D0]
0x1800115e4  jnb     loc_1800116C9
0x1800115ea  movzx   ecx, [rbp+57h+var_CC]
0x1800115ee  mov     r14d, 2
0x1800115f4  mov     eax, r14d
0x1800115f7  mul     rcx
0x1800115fa  cmovb   rax, r13
0x1800115fe  mov     rcx, rax; unsigned __int64
0x180011601  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180011606  movzx   ecx, [rbp+57h+var_D0]
0x18001160a  mov     rdi, rax
0x18001160d  mov     eax, r14d
0x180011610  mul     rcx
0x180011613  cmovb   rax, r13
0x180011617  mov     rcx, rax; unsigned __int64
0x18001161a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001161f  mov     r14, rax
0x180011622  test    rdi, rdi
0x180011625  jz      loc_180011AB7
0x18001162b  test    rax, rax
0x18001162e  jz      loc_180011AB7
0x180011634  mov     rcx, [rbp+57h+var_B8]
0x180011638  lea     r8, [rbp+57h+var_D0]
0x18001163c  mov     [rsp+130h+var_E0], r12
0x180011641  xor     edx, edx
0x180011643  mov     [rsp+130h+var_E8], r8
0x180011648  xor     r9d, r9d
0x18001164b  movzx   r8d, [rbp+57h+var_D0]
0x180011650  mov     rax, [rcx]
0x180011653  mov     [rsp+130h+var_F0], r14
0x180011658  mov     word ptr [rsp+130h+var_F8], r8w
0x18001165e  lea     r8, [rbp+57h+var_CC]
0x180011662  mov     [rsp+130h+var_100], r8
0x180011667  movzx   r8d, [rbp+57h+var_CC]
0x18001166c  mov     rax, [rax+68h]
0x180011670  mov     qword ptr [rsp+130h+cchWideChar], rdi
0x180011675  mov     word ptr [rsp+130h+lpWideCharStr], r8w
0x18001167b  mov     r8b, 3
0x18001167e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011683  test    eax, eax
0x180011685  js      short loc_1800116B9
0x180011687  movzx   r9d, [rbp+57h+var_D0]
0x18001168c  xor     r8d, r8d
0x18001168f  mov     rcx, qword ptr [rbp+57h+var_C4+4]
0x180011693  add     r9d, r9d
0x180011696  mov     [rsp+130h+var_100], r14
0x18001169b  xor     edx, edx
0x18001169d  mov     [rsp+130h+cchWideChar], r9d
0x1800116a2  lea     r9, aCopyright; "Copyright"
0x1800116a9  mov     dword ptr [rsp+130h+lpWideCharStr], esi
0x1800116ad  mov     rax, [rcx]
0x1800116b0  mov     rax, [rax+70h]
0x1800116b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116b9  mov     rcx, rdi; Block
0x1800116bc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800116c1  mov     rcx, r14; Block
0x1800116c4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800116c9  mov     rcx, [rbp+57h+var_B8]
  ... truncated ...
```
