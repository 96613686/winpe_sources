# GetServerShareFromIUriPriv

- ea: `0x1800394b4`
- end: `0x180039d37`
- name: `GetServerShareFromIUriPriv`
- size: `2179`
- prototype: `__int64 __fastcall(struct IUnknown *, unsigned int, const void **, _DWORD *, _DWORD *, UINT *, _DWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180038ca0`

## callees

- `0x1800150e0`
- `0x18001b1d0`
- `0x1800215c0`
- `0x1800389c0`
- `0x1800394b4`
- `0x180039f68`
- `0x1800478b0`
- `0x18004ca90`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `msvcrt!wcschr` at `0x180039997`
- `msvcrt!wcschr` at `0x180039cdf`
- `msvcrt!wcschr` at `0x180039d07`
- `msvcrt!wcschr` at `0x180039997`
- `msvcrt!wcschr` at `0x180039cdf`
- `msvcrt!wcschr` at `0x180039d07`
- `iertutil!GetIUriPriv` at `0x180039ad0`
- `iertutil!GetIUriPriv` at `0x180039ad0`
- `iertutil!IsDriveAndNotIPv6` at `0x18003963f`
- `iertutil!IsDriveAndNotIPv6` at `0x18003963f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x180039c83`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x180039c83`
- `api-ms-win-core-stringansi-l1-1-0!CharLowerA` at `0x180039678`
- `api-ms-win-core-stringansi-l1-1-0!CharLowerA` at `0x180039678`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeA` at `0x1800396a9`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeA` at `0x1800396a9`
- `ntdll!RtlMoveMemory` at `0x180039cd0`
- `ntdll!RtlMoveMemory` at `0x180039cd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039757`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039757`
- `OLEAUT32!__imp_SysFreeString` at `0x180039b52`
- `OLEAUT32!__imp_SysFreeString` at `0x180039b6b`
- `OLEAUT32!__imp_SysFreeString` at `0x180039c6b`
- `OLEAUT32!__imp_SysFreeString` at `0x180039b52`
- `OLEAUT32!__imp_SysFreeString` at `0x180039b6b`
- `OLEAUT32!__imp_SysFreeString` at `0x180039c6b`
- `OLEAUT32!__imp_SysStringLen` at `0x180039bac`
- `OLEAUT32!__imp_SysStringLen` at `0x180039bac`
- `MPR!WNetGetConnectionW` at `0x180039bfb`
- `MPR!WNetGetConnectionW` at `0x180039bfb`

## pseudocode

```c
__int64 __fastcall GetServerShareFromIUriPriv(
        struct IUnknown *a1,
        unsigned int a2,
        const void **a3,
        _DWORD *a4,
        _DWORD *a5,
        UINT *a6,
        _DWORD *a7)
{
  struct IUnknownVtbl *lpVtbl; // rax
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rax
  signed int v10; // edi
  wchar_t *v11; // rsi
  struct IUnknownVtbl *v12; // rax
  HRESULT (__stdcall *v13)(IUnknown *, const IID *const, void **); // rax
  int v14; // r14d
  BSTR i; // rbx
  signed __int8 v16; // al
  __int64 v17; // r14
  UINT DriveTypeA; // eax
  struct IUnknown *v19; // rcx
  BOOL v20; // ebx
  int UriWithoutRedirector; // eax
  struct IUri *v23; // rbx
  unsigned __int16 *v24; // r10
  int v25; // r14d
  DWORD v26; // ecx
  unsigned __int16 v27; // r8
  unsigned __int64 v28; // rdi
  wchar_t *v29; // rax
  int v30; // eax
  int v31; // eax
  int v32; // eax
  _BOOL8 v33; // r14
  wchar_t *v34; // rax
  unsigned __int16 *v35; // r15
  unsigned int v36; // ecx
  unsigned int v37; // eax
  const unsigned __int16 *v38; // r8
  __int64 v39; // rcx
  int v40; // r15d
  int v41; // eax
  __int64 v42; // rcx
  int v43; // r15d
  int v44; // eax
  int v45; // eax
  WCHAR *v46; // rax
  signed int ConnectionW; // eax
  OLECHAR v48; // ax
  __int64 v49; // rax
  const void **v50; // r14
  _DWORD *v51; // r15
  char *v52; // rax
  wchar_t *v53; // rax
  __int64 v54; // rbx
  wchar_t *v55; // rax
  __int64 v56; // rax
  DWORD nLength; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v58; // [rsp+44h] [rbp-BCh] BYREF
  CHAR RootPathName[8]; // [rsp+48h] [rbp-B8h] BYREF
  struct IUri *v60; // [rsp+50h] [rbp-B0h] BYREF
  int v61; // [rsp+58h] [rbp-A8h] BYREF
  int v62; // [rsp+5Ch] [rbp-A4h]
  void **v63; // [rsp+60h] [rbp-A0h]
  struct IUnknown *v64; // [rsp+68h] [rbp-98h]
  unsigned int v65; // [rsp+70h] [rbp-90h]
  BSTR pbstr[2]; // [rsp+78h] [rbp-88h] BYREF
  UINT v67; // [rsp+88h] [rbp-78h] BYREF
  _DWORD *v68; // [rsp+90h] [rbp-70h]
  void **v69; // [rsp+98h] [rbp-68h] BYREF
  __int64 v70; // [rsp+A0h] [rbp-60h]
  int v71; // [rsp+A8h] [rbp-58h]
  BSTR bstrString; // [rsp+B0h] [rbp-50h]
  unsigned __int16 *v73; // [rsp+B8h] [rbp-48h]
  unsigned int v74; // [rsp+C0h] [rbp-40h]
  void **v75; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v76; // [rsp+D0h] [rbp-30h]
  int v77; // [rsp+D8h] [rbp-28h]
  BSTR v78; // [rsp+E0h] [rbp-20h]
  unsigned __int16 *v79; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v80; // [rsp+F0h] [rbp-10h]
  const void **v81; // [rsp+F8h] [rbp-8h]
  _DWORD *v82; // [rsp+100h] [rbp+0h]
  _DWORD *v83; // [rsp+108h] [rbp+8h]
  WCHAR LocalName[4]; // [rsp+110h] [rbp+10h] BYREF

  *a3 = 0;
  *a4 = 0;
  v68 = a7;
  *a5 = 0;
  *a6 = 0;
  lpVtbl = a1->lpVtbl;
  v58 = a2;
  v82 = a5;
  v83 = a4;
  QueryInterface = lpVtbl[15].QueryInterface;
  v81 = a3;
  nLength = 0;
  v61 = 0;
  v10 = ((__int64 (__fastcall *)(struct IUnknown *, int *))QueryInterface)(a1, &v61);
  if ( v10 < 0 )
    return (unsigned int)v10;
  v62 = 0;
  v11 = 0;
  if ( (v61 & 8) != 0 )
  {
    *(_DWORD *)RootPathName = 0;
    v58 = 0;
    v60 = 0;
    if ( (unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_ZONES_MUTZ_DISABLE_LANMANCHECK) )
      UriWithoutRedirector = GetUriWithoutRedirector(a1, (struct IUriPriv **)&v60);
    else
      UriWithoutRedirector = GetIUriPriv(a1, &v60);
    v10 = UriWithoutRedirector;
    if ( UriWithoutRedirector < 0 )
      return (unsigned int)v10;
    v23 = v60;
    CUString::CUString((CUString *)&v75, v60, Uri_PROPERTY_HOST, (int *)RootPathName);
    CUString::CUString((CUString *)&v69, v60, Uri_PROPERTY_PATH, (int *)&v58);
    v24 = 0;
    if ( !*(_DWORD *)RootPathName && (_DWORD)v80 )
    {
      v25 = 0;
      v26 = v80 + nLength;
      nLength += v80;
      if ( !v58 && v74 )
      {
        v27 = *v73;
        if ( *v73 != 92 )
          ++v26;
        v26 += v74;
        nLength = v26;
        LOBYTE(v25) = v27 != 92;
      }
      v28 = v26 + 1 + 2LL;
      *(_QWORD *)LocalName = v28;
      v29 = (wchar_t *)operator new(saturated_mul(v28, 2u));
      v24 = 0;
      *(_QWORD *)RootPathName = v29;
      v11 = v29;
      if ( !v29 )
      {
        v10 = -2147024882;
        goto LABEL_61;
      }
      v30 = StringCchCopyNExW(
              v29,
              v28,
              L"\\\\",
              2u,
              (unsigned __int16 **)RootPathName,
              (unsigned __int64 *)LocalName,
              0);
      v24 = 0;
      v10 = v30;
      if ( v30 < 0 )
        goto LABEL_61;
      v31 = StringCchCopyNExW(
              *(STRSAFE_LPWSTR *)RootPathName,
              *(unsigned __int64 *)LocalName,
              v79,
              (unsigned int)v80,
              (unsigned __int16 **)RootPathName,
              (unsigned __int64 *)LocalName,
              0);
      v24 = 0;
      v10 = v31;
      if ( v31 < 0 )
        goto LABEL_61;
      if ( v25 )
      {
        v32 = StringCchCopyNExW(
                *(STRSAFE_LPWSTR *)RootPathName,
                *(unsigned __int64 *)LocalName,
                L"\\",
                1u,
                (unsigned __int16 **)RootPathName,
                (unsigned __int64 *)LocalName,
                0);
        v24 = 0;
        v10 = v32;
        if ( v32 < 0 )
          goto LABEL_61;
      }
      if ( !v74 )
        goto LABEL_61;
      v58 = 0;
      v33 = *v73 == 47;
      v34 = wcschr(&v73[v33], 0x2Fu);
      v35 = v73;
      v24 = 0;
      if ( v34 )
      {
        v45 = LongLongToULong(v34 - v73, &v58);
        v24 = 0;
        v10 = v45;
        if ( v45 < 0 )
          goto LABEL_61;
        v36 = v58;
      }
      else
      {
        v36 = v74;
      }
      if ( v36 < (unsigned int)v33 )
        v37 = -1;
      else
        v37 = v36 - v33;
      v10 = v36 < (unsigned int)v33 ? 0x80070216 : 0;
      if ( v36 < (unsigned int)v33 )
        goto LABEL_61;
      v38 = &v35[v33];
      if ( v38 > v35 )
      {
        v10 = StringCchCopyNW(*(unsigned __int16 **)RootPathName, *(unsigned __int64 *)LocalName, v38, v37);
        goto LABEL_61;
      }
    }
    v10 = -2147024809;
LABEL_61:
    v39 = v70;
    v69 = &CUString::`vftable';
    v40 = (int)v24;
    LOBYTE(v40) = v70 != 0;
    v41 = (int)v24;
    if ( v40 || (LOBYTE(v41) = v71 != 11, v41) )
    {
      if ( bstrString )
      {
        SysFreeString(bstrString);
        v39 = v70;
        v24 = 0;
        bstrString = 0;
      }
      v73 = v24;
      v74 = (unsigned int)v24;
      if ( v40 && v39 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
        v24 = 0;
        v70 = 0;
      }
    }
    v42 = v76;
    v75 = &CUString::`vftable';
    v43 = (int)v24;
    v71 = 11;
    LOBYTE(v43) = v76 != 0;
    v44 = (int)v24;
    if ( v43 || (LOBYTE(v44) = v77 != 11, v44) )
    {
      if ( v78 )
      {
        SysFreeString(v78);
        v42 = v76;
        v24 = 0;
        v78 = 0;
      }
      v79 = v24;
      LODWORD(v80) = (_DWORD)v24;
      if ( v43 && v42 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
        v76 = 0;
      }
    }
    v77 = 11;
    ((void (__fastcall *)(struct IUri *))v23->lpVtbl->Release)(v23);
    goto LABEL_27;
  }
  if ( (v61 & 4) == 0 )
    return (unsigned int)-2147024809;
  v64 = 0;
  v63 = &CUString::`vftable';
  v12 = a1->lpVtbl;
  v67 = 0;
  v65 = 8;
  *(_OWORD *)pbstr = 0;
  v13 = v12->QueryInterface;
  v60 = 0;
  if ( ((int (__fastcall *)(struct IUnknown *, GUID *, struct IUri **))v13)(
         a1,
         &GUID_50295b0c_6b79_4935_aed8_05d80ec86a60,
         &v60) < 0 )
  {
    v14 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, BSTR *, _QWORD))a1->lpVtbl[1].QueryInterface)(
            a1,
            v65,
            pbstr,
            0);
    if ( v14 >= 0 )
    {
      pbstr[1] = pbstr[0];
      v67 = SysStringLen(pbstr[0]);
    }
  }
  else
  {
    v14 = ((__int64 (__fastcall *)(struct IUri *, _QWORD, BSTR *, UINT *))v60->lpVtbl[1].QueryInterface)(
            v60,
            v65,
            &pbstr[1],
            &v67);
    ((void (__fastcall *)(struct IUri *))v60->lpVtbl->Release)(v60);
  }
  if ( a1 && v14 >= 0 )
  {
    v64 = a1;
    ((void (__fastcall *)(struct IUnknown *))a1->lpVtbl->AddRef)(a1);
  }
  if ( v14 || !v67 )
    goto LABEL_37;
  for ( i = pbstr[1]; *i == 47 || *i == 92; ++i )
    ;
  if ( !IsDriveAndNotIPv6(i) )
  {
    if ( *pbstr[1] == 92 || *pbstr[1] == 47 )
    {
      v48 = pbstr[1][1];
      if ( v48 )
      {
        if ( v48 != 92 && v48 != 47 )
        {
          v62 = 1;
          *a6 = 3;
          goto LABEL_20;
        }
      }
    }
LABEL_37:
    v10 = -2147024809;
    goto LABEL_20;
  }
  *v68 = 1;
  strcpy(&RootPathName[1], ":\\");
  RootPathName[0] = *(_BYTE *)i;
  v16 = (unsigned __int8)CharLowerA((LPSTR)RootPathName[0]);
  if ( (unsigned __int8)(v16 - 97) > 0x19u )
  {
    *a6 = 0;
  }
  else
  {
    v17 = v16;
    DriveTypeA = *((_DWORD *)&rgdwDriveTypeCache + v16 - 97);
    if ( DriveTypeA == 0xFFFF )
    {
      DriveTypeA = GetDriveTypeA(RootPathName);
      *((_DWORD *)&rgdwDriveTypeCache + v17 - 97) = DriveTypeA;
    }
    *a6 = DriveTypeA;
    if ( DriveTypeA == 4 )
    {
      LocalName[0] = *i;
      wcscpy(&LocalName[1], L":");
      nLength = 261;
      v46 = (WCHAR *)operator new(0x20Au);
      v11 = v46;
      if ( v46 )
      {
        ConnectionW = WNetGetConnectionW(LocalName, v46, &nLength);
        if ( ConnectionW )
        {
          if ( !v58 )
          {
            if ( ConnectionW > 0 )
              v10 = (unsigned __int16)ConnectionW | 0x80070000;
            else
              v10 = ConnectionW;
          }
        }
        else
        {
          v11[--nLength] = 0;
          *v68 = 0;
        }
      }
      else
      {
        v10 = -2147024882;
      }
      goto LABEL_20;
    }
  }
  v62 = 1;
  v10 = 0;
LABEL_20:
  v19 = v64;
  v63 = &CUString::`vftable';
  v20 = v64 != 0;
  if ( v64 || v65 != 11 )
  {
    if ( pbstr[0] )
    {
      SysFreeString(pbstr[0]);
      v19 = v64;
      pbstr[0] = 0;
    }
    pbstr[1] = 0;
    v67 = 0;
    if ( v20 && v19 )
    {
      ((void (__fastcall *)(struct IUnknown *))v19->lpVtbl->Release)(v19);
      v64 = 0;
    }
  }
  v65 = 11;
LABEL_27:
  if ( v10 < 0 || v62 )
  {
    if ( v11 )
      CoTaskMemFree(v11);
  }
  else
  {
    PathStripToRootW(v11);
    v49 = -1;
    do
      ++v49;
    while ( v11[v49] );
    v50 = v81;
    v51 = v82;
    nLength = v49;
    *v81 = v11;
    *v51 = v49;
    while ( 1 )
    {
      v52 = (char *)*v50;
      if ( *(_WORD *)*v50 != 92 && *(_WORD *)v52 != 47 )
        break;
      *v50 = v52 + 2;
    }
    *v51 -= (v52 - (char *)v11) >> 1;
    RtlMoveMemory(v11, *v50, 2LL * (unsigned int)(*v51 + 1));
    *v50 = v11;
    v53 = wcschr(v11, 0x5Cu);
    if ( v53 )
      v54 = ((char *)v53 - (_BYTE *)*v50) >> 1;
    else
      LODWORD(v54) = *v51;
    v55 = wcschr((const wchar_t *)*v50, 0x2Fu);
    if ( v55 )
      v56 = ((char *)v55 - (_BYTE *)*v50) >> 1;
    else
      LODWORD(v56) = *v51;
    if ( (unsigned int)v54 < (unsigned int)v56 )
      LODWORD(v56) = v54;
    *v83 = v56;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800394b4  mov     [rsp-8+arg_8], rbx
0x1800394b9  push    rbp
0x1800394ba  push    rsi
0x1800394bb  push    rdi
0x1800394bc  push    r12
0x1800394be  push    r13
0x1800394c0  push    r14
0x1800394c2  push    r15
0x1800394c4  lea     rbp, [rsp-20h]
0x1800394c9  sub     rsp, 120h
0x1800394d0  mov     rax, cs:__security_cookie
0x1800394d7  xor     rax, rsp
0x1800394da  mov     [rbp+50h+var_38], rax
0x1800394de  mov     rax, [rbp+50h+arg_30]
0x1800394e5  xor     r12d, r12d
0x1800394e8  mov     r15, [rbp+50h+arg_28]
0x1800394ef  mov     rbx, rcx
0x1800394f2  mov     rcx, [rbp+50h+arg_20]
0x1800394f9  mov     [r8], r12
0x1800394fc  mov     [r9], r12d
0x1800394ff  mov     [rbp+50h+var_C0], rax
0x180039503  mov     [rcx], r12d
0x180039506  mov     [r15], r12d
0x180039509  mov     rax, [rbx]
0x18003950c  mov     [rsp+150h+var_10C], edx
0x180039510  lea     rdx, [rsp+150h+var_F8]
0x180039515  mov     [rbp+50h+var_50], rcx
0x180039519  mov     rcx, rbx
0x18003951c  mov     [rbp+50h+var_48], r9
0x180039520  mov     rax, [rax+168h]
0x180039527  mov     [rbp+50h+var_58], r8
0x18003952b  mov     [rsp+150h+nLength], r12d
0x180039530  mov     [rsp+150h+var_F8], r12d
0x180039535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003953a  mov     edi, eax
0x18003953c  test    eax, eax
0x18003953e  js      loc_18003975D
0x180039544  lea     r14d, [r12+8]
0x180039549  mov     [rsp+150h+var_F4], r12d
0x18003954e  mov     esi, r12d
0x180039551  test    byte ptr [rsp+150h+var_F8], r14b
0x180039556  jnz     loc_1800397BD
0x18003955c  test    byte ptr [rsp+150h+var_F8], 4
0x180039561  jz      loc_180039D2D
0x180039567  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x18003956e  mov     [rsp+150h+var_E8], r12
0x180039573  mov     [rsp+150h+var_F0], rax
0x180039578  lea     r8, [rsp+150h+var_100]
0x18003957d  mov     rax, [rbx]
0x180039580  lea     rdx, _GUID_50295b0c_6b79_4935_aed8_05d80ec86a60
0x180039587  xorps   xmm0, xmm0
0x18003958a  mov     [rbp+50h+var_C8], r12d
0x18003958e  mov     rcx, rbx
0x180039591  mov     [rsp+150h+var_E0], r14d
0x180039596  movdqu  xmmword ptr [rsp+150h+pbstr], xmm0
0x18003959c  mov     rax, [rax]
0x18003959f  mov     [rsp+150h+var_100], r12
0x1800395a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800395a9  mov     edx, [rsp+150h+var_E0]
0x1800395ad  test    eax, eax
0x1800395af  js      loc_180039B81
0x1800395b5  mov     rcx, [rsp+150h+var_100]
0x1800395ba  lea     r9, [rbp+50h+var_C8]
0x1800395be  lea     r8, [rbp+50h+pbstr+8]
0x1800395c2  mov     rax, [rcx]
0x1800395c5  mov     rax, [rax+0E0h]
0x1800395cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800395d1  mov     rcx, [rsp+150h+var_100]
0x1800395d6  mov     r14d, eax
0x1800395d9  mov     rdx, [rcx]
0x1800395dc  mov     rax, [rdx+10h]
0x1800395e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800395e5  test    rbx, rbx
0x1800395e8  jz      short loc_180039603
0x1800395ea  test    r14d, r14d
0x1800395ed  js      short loc_180039603
0x1800395ef  mov     [rsp+150h+var_E8], rbx
0x1800395f4  mov     rcx, rbx
0x1800395f7  mov     rax, [rbx]
0x1800395fa  mov     rax, [rax+8]
0x1800395fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039603  mov     r12d, 5Ch ; '\'
0x180039609  lea     r13d, [r12-2Dh]
0x18003960e  test    r14d, r14d
0x180039611  jnz     loc_1800397B0
0x180039617  xor     r14d, r14d
0x18003961a  cmp     [rbp+50h+var_C8], r14d
0x18003961e  jbe     loc_1800397B0
0x180039624  mov     rbx, [rbp+50h+pbstr+8]
0x180039628  cmp     [rbx], r13w
0x18003962c  jz      loc_180039786
0x180039632  cmp     [rbx], r12w
0x180039636  jz      loc_180039786
0x18003963c  mov     rcx, rbx
0x18003963f  call    cs:__imp_?IsDriveAndNotIPv6@@YAHPEBG@Z; IsDriveAndNotIPv6(ushort const *)
0x180039645  test    eax, eax
0x180039647  jz      loc_180039798
0x18003964d  mov     rax, [rbp+50h+var_C0]
0x180039651  mov     dword ptr [rax], 1
0x180039657  movzx   eax, word ptr cs:asc_18012C8C8+1; ":\\"
0x18003965e  mov     word ptr [rsp+150h+RootPathName+1], ax
0x180039663  mov     al, byte ptr cs:asc_18012C8C8+3; ""
0x180039669  mov     [rsp+150h+RootPathName+3], al
0x18003966d  movsx   rax, byte ptr [rbx]
0x180039671  mov     rcx, rax; lpsz
0x180039674  mov     [rsp+150h+RootPathName], al
0x180039678  call    cs:__imp_CharLowerA
0x18003967e  lea     ecx, [rax-61h]
0x180039681  cmp     cl, 19h
0x180039684  ja      loc_180039AC8
0x18003968a  movsx   r14, al
0x18003968e  lea     rax, ?rgdwDriveTypeCache@@3PAKA; ulong near * rgdwDriveTypeCache
0x180039695  mov     eax, [rax+r14*4-184h]
0x18003969d  cmp     eax, 0FFFFh
0x1800396a2  jnz     short loc_1800396BE
0x1800396a4  lea     rcx, [rsp+150h+RootPathName]; lpRootPathName
0x1800396a9  call    cs:__imp_GetDriveTypeA
0x1800396af  lea     rcx, ?rgdwDriveTypeCache@@3PAKA; ulong near * rgdwDriveTypeCache
0x1800396b6  mov     [rcx+r14*4-184h], eax
0x1800396be  mov     [r15], eax
0x1800396c1  cmp     eax, 4
0x1800396c4  jz      loc_180039BBA
0x1800396ca  xor     r15d, r15d
0x1800396cd  mov     [rsp+150h+var_F4], 1
0x1800396d5  mov     edi, r15d
0x1800396d8  mov     rcx, [rsp+150h+var_E8]
0x1800396dd  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x1800396e4  test    rcx, rcx
0x1800396e7  mov     [rsp+150h+var_F0], rax
0x1800396ec  mov     ebx, r15d
0x1800396ef  mov     r14d, 0Bh
0x1800396f5  setnz   bl
0x1800396f8  mov     eax, r15d
0x1800396fb  cmp     [rsp+150h+var_E0], r14d
0x180039700  setnz   al
0x180039703  test    ebx, ebx
0x180039705  jz      loc_18003978F
0x18003970b  mov     rax, [rsp+150h+pbstr]
0x180039710  test    rax, rax
0x180039713  jnz     loc_180039C68
0x180039719  mov     [rbp+50h+pbstr+8], r15
0x18003971d  mov     [rbp+50h+var_C8], r15d
0x180039721  test    ebx, ebx
0x180039723  jz      short loc_18003973B
0x180039725  test    rcx, rcx
0x180039728  jz      short loc_18003973B
0x18003972a  mov     rax, [rcx]
0x18003972d  mov     rax, [rax+10h]
0x180039731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039736  mov     [rsp+150h+var_E8], r15
0x18003973b  mov     [rsp+150h+var_E0], r14d
0x180039740  test    edi, edi
0x180039742  js      short loc_18003974F
0x180039744  cmp     [rsp+150h+var_F4], r15d
0x180039749  jz      loc_180039C80
0x18003974f  test    rsi, rsi
0x180039752  jz      short loc_18003975D
0x180039754  mov     rcx, rsi; pv
0x180039757  call    cs:__imp_CoTaskMemFree
0x18003975d  mov     eax, edi
0x18003975f  mov     rcx, [rbp+50h+var_38]
0x180039763  xor     rcx, rsp; StackCookie
0x180039766  call    __security_check_cookie
0x18003976b  mov     rbx, [rsp+150h+arg_8]
0x180039773  add     rsp, 120h
0x18003977a  pop     r15
0x18003977c  pop     r14
0x18003977e  pop     r13
0x180039780  pop     r12
0x180039782  pop     rdi
0x180039783  pop     rsi
0x180039784  pop     rbp
0x180039785  retn
0x180039786  add     rbx, 2
0x18003978a  jmp     loc_180039628
0x18003978f  test    eax, eax
0x180039791  jz      short loc_18003973B
0x180039793  jmp     loc_18003970B
0x180039798  mov     rax, [rbp+50h+pbstr+8]
0x18003979c  cmp     [rax], r12w
0x1800397a0  jz      loc_180039C33
0x1800397a6  cmp     [rax], r13w
0x1800397aa  jz      loc_180039C33
0x1800397b0  mov     edi, 80070057h
0x1800397b5  xor     r15d, r15d
0x1800397b8  jmp     loc_1800396D8
0x1800397bd  lea     rcx, ?FEATURE_ZONES_MUTZ_DISABLE_LANMANCHECK@FCK@@3VCFeatureControlKey@@A; this
0x1800397c4  mov     dword ptr [rsp+150h+RootPathName], r12d
0x1800397c9  mov     [rsp+150h+var_10C], r12d
0x1800397ce  mov     [rsp+150h+var_100], r12
0x1800397d3  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x1800397d8  lea     rdx, [rsp+150h+var_100]; struct IUriPriv **
0x1800397dd  mov     rcx, rbx; struct IUnknown *
0x1800397e0  test    eax, eax
0x1800397e2  jz      loc_180039AD0
0x1800397e8  call    ?GetUriWithoutRedirector@@YAJPEAUIUriPriv@@PEAPEAU1@@Z; GetUriWithoutRedirector(IUriPriv *,IUriPriv * *)
0x1800397ed  mov     edi, eax
0x1800397ef  test    eax, eax
0x1800397f1  js      loc_18003975D
0x1800397f7  mov     rbx, [rsp+150h+var_100]
0x1800397fc  lea     r9, [rsp+150h+RootPathName]; int *
0x180039801  mov     rdx, rbx; struct IUri *
0x180039804  lea     rcx, [rbp+50h+var_88]; this
0x180039808  mov     r8d, 6; enum __MIDL_IUri_0001
0x18003980e  call    ??0CUString@@QEAA@PEAUIUri@@W4__MIDL_IUri_0001@@PEAJ@Z; CUString::CUString(IUri *,__MIDL_IUri_0001,long *)
0x180039813  mov     rdx, [rsp+150h+var_100]; struct IUri *
0x180039818  lea     r9, [rsp+150h+var_10C]; int *
0x18003981d  mov     r8d, r14d; enum __MIDL_IUri_0001
0x180039820  lea     rcx, [rbp+50h+var_B8]; this
0x180039824  call    ??0CUString@@QEAA@PEAUIUri@@W4__MIDL_IUri_0001@@PEAJ@Z; CUString::CUString(IUri *,__MIDL_IUri_0001,long *)
0x180039829  mov     r13d, 2Fh ; '/'
0x18003982f  xor     r10d, r10d
0x180039832  lea     r12d, [r13+2Dh]
0x180039836  cmp     dword ptr [rsp+150h+RootPathName], r10d
0x18003983b  jnz     loc_180039B45
0x180039841  mov     eax, dword ptr [rbp+50h+var_60]
0x180039844  test    eax, eax
0x180039846  jz      loc_180039B45
0x18003984c  mov     ecx, [rsp+150h+nLength]
0x180039850  mov     r14d, r10d
0x180039853  add     ecx, eax
0x180039855  mov     [rsp+150h+nLength], ecx
0x180039859  cmp     [rsp+150h+var_10C], r10d
0x18003985e  jnz     short loc_180039885
0x180039860  mov     edx, [rbp+50h+var_90]
0x180039863  test    edx, edx
0x180039865  jz      short loc_180039885
0x180039867  mov     rax, [rbp+50h+var_98]
0x18003986b  movzx   r8d, word ptr [rax]
0x18003986f  cmp     r8w, r12w
0x180039873  jz      short loc_180039877
0x180039875  inc     ecx
0x180039877  add     ecx, edx
0x180039879  cmp     r8w, r12w
0x18003987d  mov     [rsp+150h+nLength], ecx
0x180039881  setnz   r14b
0x180039885  lea     edi, [rcx+1]
0x180039888  mov     eax, 2
0x18003988d  add     rdi, 2
0x180039891  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180039898  mul     rdi
0x18003989b  mov     qword ptr [rbp+50h+LocalName], rdi
0x18003989f  cmovb   rax, rcx
0x1800398a3  mov     rcx, rax; Size
0x1800398a6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800398ab  xor     r10d, r10d
0x1800398ae  mov     qword ptr [rsp+150h+RootPathName], rax
0x1800398b3  mov     rsi, rax
0x1800398b6  test    rax, rax
0x1800398b9  jz      loc_180039B12
0x1800398bf  mov     [rsp+150h+var_120], r10d; unsigned int
0x1800398c4  lea     rax, [rbp+50h+LocalName]
0x1800398c8  mov     [rsp+150h+var_128], rax; unsigned __int64 *
0x1800398cd  lea     r9d, [r10+2]; unsigned __int64
0x1800398d1  lea     rax, [rsp+150h+RootPathName]
0x1800398d6  mov     rdx, rdi; unsigned __int64
0x1800398d9  lea     r8, asc_1801335B8; "\\\\"
0x1800398e0  mov     [rsp+150h+var_130], rax; unsigned __int16 **
0x1800398e5  mov     rcx, rsi; pszDest
0x1800398e8  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x1800398ed  xor     r10d, r10d
0x1800398f0  mov     edi, eax
0x1800398f2  test    eax, eax
0x1800398f4  js      loc_1800399EE
0x1800398fa  mov     r9d, dword ptr [rbp+50h+var_60]; unsigned __int64
0x1800398fe  lea     rax, [rbp+50h+LocalName]
0x180039902  mov     r8, [rbp+50h+var_68]; unsigned __int16 *
0x180039906  mov     rdx, qword ptr [rbp+50h+LocalName]; unsigned __int64
0x18003990a  mov     rcx, qword ptr [rsp+150h+RootPathName]; pszDest
0x18003990f  mov     [rsp+150h+var_120], r10d; unsigned int
0x180039914  mov     [rsp+150h+var_128], rax; unsigned __int64 *
0x180039919  lea     rax, [rsp+150h+RootPathName]
0x18003991e  mov     [rsp+150h+var_130], rax; unsigned __int16 **
0x180039923  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x180039928  xor     r10d, r10d
0x18003992b  mov     edi, eax
0x18003992d  test    eax, eax
0x18003992f  js      loc_1800399EE
0x180039935  test    r14d, r14d
0x180039938  jz      short loc_180039974
0x18003993a  mov     rdx, qword ptr [rbp+50h+LocalName]; unsigned __int64
0x18003993e  lea     rax, [rbp+50h+LocalName]
0x180039942  mov     rcx, qword ptr [rsp+150h+RootPathName]; pszDest
0x180039947  lea     r9d, [r10+1]; unsigned __int64
0x18003994b  mov     [rsp+150h+var_120], r10d; unsigned int
0x180039950  lea     r8, SubBlock; "\\"
0x180039957  mov     [rsp+150h+var_128], rax; unsigned __int64 *
0x18003995c  lea     rax, [rsp+150h+RootPathName]
0x180039961  mov     [rsp+150h+var_130], rax; unsigned __int16 **
0x180039966  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x18003996b  xor     r10d, r10d
0x18003996e  mov     edi, eax
0x180039970  test    eax, eax
0x180039972  js      short loc_1800399EE
0x180039974  cmp     [rbp+50h+var_90], r10d
0x180039978  jbe     short loc_1800399EE
0x18003997a  mov     rcx, [rbp+50h+var_98]
0x18003997e  mov     eax, r10d
0x180039981  mov     edx, r13d; Ch
0x180039984  mov     [rsp+150h+var_10C], r10d
  ... truncated ...
```
