# GetServerShareFromIUriPriv

- ea: `0x18003ed90`
- end: `0x18003f663`
- name: `GetServerShareFromIUriPriv`
- size: `2259`
- prototype: `__int64 __usercall@<rax>(struct IUnknown *@<rcx>, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18003e540`

## callees

- `0x18001db50`
- `0x180021650`
- `0x180028510`
- `0x18003ed90`
- `0x18003f8a0`
- `0x18003f9d4`
- `0x1800498c0`
- `0x180083b6c`
- `0x180088604`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `msvcrt!wcschr` at `0x18003f28c`
- `msvcrt!wcschr` at `0x18003f5ff`
- `msvcrt!wcschr` at `0x18003f62d`
- `msvcrt!wcschr` at `0x18003f28c`
- `msvcrt!wcschr` at `0x18003f5ff`
- `msvcrt!wcschr` at `0x18003f62d`
- `iertutil!GetIUriPriv` at `0x18003f2bc`
- `iertutil!GetIUriPriv` at `0x18003f2bc`
- `iertutil!IsDriveAndNotIPv6` at `0x18003ef1b`
- `iertutil!IsDriveAndNotIPv6` at `0x18003ef1b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x18003f597`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x18003f597`
- `api-ms-win-core-stringansi-l1-1-0!CharLowerA` at `0x18003ef5a`
- `api-ms-win-core-stringansi-l1-1-0!CharLowerA` at `0x18003ef5a`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeA` at `0x18003ef91`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeA` at `0x18003ef91`
- `ntdll!RtlMoveMemory` at `0x18003f5ea`
- `ntdll!RtlMoveMemory` at `0x18003f5ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f045`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f045`
- `OLEAUT32!__imp_SysFreeString` at `0x18003f44b`
- `OLEAUT32!__imp_SysFreeString` at `0x18003f46a`
- `OLEAUT32!__imp_SysFreeString` at `0x18003f579`
- `OLEAUT32!__imp_SysFreeString` at `0x18003f44b`
- `OLEAUT32!__imp_SysFreeString` at `0x18003f46a`
- `OLEAUT32!__imp_SysFreeString` at `0x18003f579`
- `OLEAUT32!__imp_SysStringLen` at `0x18003f4b1`
- `OLEAUT32!__imp_SysStringLen` at `0x18003f4b1`
- `MPR!WNetGetConnectionW` at `0x18003f506`
- `MPR!WNetGetConnectionW` at `0x18003f506`

## pseudocode

```c
__int64 __fastcall GetServerShareFromIUriPriv(
        struct IUnknown *a1,
        int a2,
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
  _BOOL8 v33; // r15
  wchar_t *v34; // rax
  unsigned __int16 *v35; // r14
  unsigned int v36; // ecx
  __int64 v37; // rcx
  int v38; // r15d
  int v39; // eax
  __int64 v40; // rcx
  int v41; // r15d
  int v42; // eax
  int v43; // eax
  const unsigned __int16 *v44; // r8
  WCHAR *v45; // rax
  signed int ConnectionW; // eax
  OLECHAR v47; // ax
  __int64 v48; // rax
  const void **v49; // r14
  _DWORD *v50; // r15
  char *v51; // rax
  wchar_t *v52; // rax
  __int64 v53; // rbx
  wchar_t *v54; // rax
  __int64 v55; // rax
  CHAR RootPathName[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD nLength; // [rsp+44h] [rbp-BCh] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+48h] [rbp-B8h] BYREF
  struct IUri *v59; // [rsp+50h] [rbp-B0h] BYREF
  int v60; // [rsp+58h] [rbp-A8h] BYREF
  int v61; // [rsp+5Ch] [rbp-A4h]
  void **v62; // [rsp+60h] [rbp-A0h]
  struct IUnknown *v63; // [rsp+68h] [rbp-98h]
  unsigned int v64; // [rsp+70h] [rbp-90h]
  BSTR pbstr[2]; // [rsp+78h] [rbp-88h] BYREF
  UINT v66; // [rsp+88h] [rbp-78h] BYREF
  _DWORD *v67; // [rsp+90h] [rbp-70h]
  void **v68; // [rsp+98h] [rbp-68h] BYREF
  __int64 v69; // [rsp+A0h] [rbp-60h]
  int v70; // [rsp+A8h] [rbp-58h]
  BSTR bstrString; // [rsp+B0h] [rbp-50h]
  unsigned __int16 *v72; // [rsp+B8h] [rbp-48h]
  unsigned int v73; // [rsp+C0h] [rbp-40h]
  void **v74; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v75; // [rsp+D0h] [rbp-30h]
  int v76; // [rsp+D8h] [rbp-28h]
  BSTR v77; // [rsp+E0h] [rbp-20h]
  unsigned __int16 *v78; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v79; // [rsp+F0h] [rbp-10h]
  const void **v80; // [rsp+F8h] [rbp-8h]
  _DWORD *v81; // [rsp+100h] [rbp+0h]
  _DWORD *v82; // [rsp+108h] [rbp+8h]
  WCHAR LocalName[4]; // [rsp+110h] [rbp+10h] BYREF

  *a3 = 0;
  *a4 = 0;
  v67 = a7;
  *a5 = 0;
  *a6 = 0;
  lpVtbl = a1->lpVtbl;
  LODWORD(pszDest) = a2;
  v81 = a5;
  v82 = a4;
  QueryInterface = lpVtbl[15].QueryInterface;
  v80 = a3;
  nLength = 0;
  v60 = 0;
  v10 = ((__int64 (__fastcall *)(struct IUnknown *, int *))QueryInterface)(a1, &v60);
  if ( v10 < 0 )
    return (unsigned int)v10;
  v61 = 0;
  v11 = 0;
  if ( (v60 & 8) != 0 )
  {
    *(_DWORD *)RootPathName = 0;
    LODWORD(pszDest) = 0;
    v59 = 0;
    if ( (unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_ZONES_MUTZ_DISABLE_LANMANCHECK) )
      UriWithoutRedirector = GetUriWithoutRedirector(a1, (struct IUriPriv **)&v59);
    else
      UriWithoutRedirector = GetIUriPriv(a1, &v59);
    v10 = UriWithoutRedirector;
    if ( UriWithoutRedirector < 0 )
      return (unsigned int)v10;
    v23 = v59;
    CUString::CUString((CUString *)&v74, v59, Uri_PROPERTY_HOST, (int *)RootPathName);
    CUString::CUString((CUString *)&v68, v59, Uri_PROPERTY_PATH, (int *)&pszDest);
    v24 = 0;
    if ( !*(_DWORD *)RootPathName && (_DWORD)v79 )
    {
      v25 = 0;
      v26 = v79 + nLength;
      nLength += v79;
      if ( !(_DWORD)pszDest && v73 )
      {
        v27 = *v72;
        if ( *v72 != 92 )
          ++v26;
        v26 += v73;
        nLength = v26;
        LOBYTE(v25) = v27 != 92;
      }
      v28 = v26 + 1 + 2LL;
      *(_QWORD *)LocalName = v28;
      v29 = (wchar_t *)operator new(saturated_mul(v28, 2u));
      v24 = 0;
      pszDest = v29;
      v11 = v29;
      if ( !v29 )
      {
        v10 = -2147024882;
        goto LABEL_58;
      }
      v30 = StringCchCopyNExW(v29, v28, L"\\\\", 2u, &pszDest, (unsigned __int64 *)LocalName, 0);
      v24 = 0;
      v10 = v30;
      if ( v30 < 0 )
        goto LABEL_58;
      v31 = StringCchCopyNExW(
              pszDest,
              *(unsigned __int64 *)LocalName,
              v78,
              (unsigned int)v79,
              &pszDest,
              (unsigned __int64 *)LocalName,
              0);
      v24 = 0;
      v10 = v31;
      if ( v31 < 0 )
        goto LABEL_58;
      if ( v25 )
      {
        v32 = StringCchCopyNExW(
                pszDest,
                *(unsigned __int64 *)LocalName,
                L"\\",
                1u,
                &pszDest,
                (unsigned __int64 *)LocalName,
                0);
        v24 = 0;
        v10 = v32;
        if ( v32 < 0 )
          goto LABEL_58;
      }
      if ( !v73 )
        goto LABEL_58;
      *(_DWORD *)RootPathName = 0;
      v33 = *v72 == 47;
      v34 = wcschr(&v72[v33], 0x2Fu);
      v35 = v72;
      if ( v34 )
      {
        v43 = LongLongToULong(v34 - v72, (unsigned int *)RootPathName);
        v24 = 0;
        v10 = v43;
        if ( v43 < 0 )
          goto LABEL_58;
        v36 = *(_DWORD *)RootPathName;
      }
      else
      {
        v36 = v73;
        *(_DWORD *)RootPathName = v73;
      }
      v10 = ULongSub(v36, v33, (unsigned int *)RootPathName);
      if ( v10 < 0 )
      {
LABEL_58:
        v37 = v69;
        v68 = &CUString::`vftable';
        v38 = (int)v24;
        LOBYTE(v38) = v69 != 0;
        v39 = (int)v24;
        if ( v38 || (LOBYTE(v39) = v70 != 11, v39) )
        {
          if ( bstrString )
          {
            SysFreeString(bstrString);
            v37 = v69;
            v24 = 0;
            bstrString = 0;
          }
          v72 = v24;
          v73 = (unsigned int)v24;
          if ( v38 && v37 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
            v24 = 0;
            v69 = 0;
          }
        }
        v40 = v75;
        v74 = &CUString::`vftable';
        v41 = (int)v24;
        v70 = 11;
        LOBYTE(v41) = v75 != 0;
        v42 = (int)v24;
        if ( v41 || (LOBYTE(v42) = v76 != 11, v42) )
        {
          if ( v77 )
          {
            SysFreeString(v77);
            v40 = v75;
            v24 = 0;
            v77 = 0;
          }
          v78 = v24;
          LODWORD(v79) = (_DWORD)v24;
          if ( v41 && v40 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
            v75 = 0;
          }
        }
        v76 = 11;
        ((void (__fastcall *)(struct IUri *))v23->lpVtbl->Release)(v23);
        goto LABEL_27;
      }
      v44 = &v35[v33];
      if ( v44 > v35 )
      {
        v10 = StringCchCopyNW(pszDest, *(unsigned __int64 *)LocalName, v44, *(unsigned int *)RootPathName);
        goto LABEL_58;
      }
    }
    v10 = -2147024809;
    goto LABEL_58;
  }
  if ( (v60 & 4) == 0 )
    return (unsigned int)-2147024809;
  v63 = 0;
  v62 = &CUString::`vftable';
  v12 = a1->lpVtbl;
  v66 = 0;
  v64 = 8;
  *(_OWORD *)pbstr = 0;
  v13 = v12->QueryInterface;
  v59 = 0;
  if ( ((int (__fastcall *)(struct IUnknown *, GUID *, struct IUri **))v13)(
         a1,
         &GUID_50295b0c_6b79_4935_aed8_05d80ec86a60,
         &v59) < 0 )
  {
    v14 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, BSTR *, _QWORD))a1->lpVtbl[1].QueryInterface)(
            a1,
            v64,
            pbstr,
            0);
    if ( v14 >= 0 )
    {
      pbstr[1] = pbstr[0];
      v66 = SysStringLen(pbstr[0]);
    }
  }
  else
  {
    v14 = ((__int64 (__fastcall *)(struct IUri *, _QWORD, BSTR *, UINT *))v59->lpVtbl[1].QueryInterface)(
            v59,
            v64,
            &pbstr[1],
            &v66);
    ((void (__fastcall *)(struct IUri *))v59->lpVtbl->Release)(v59);
  }
  if ( a1 && v14 >= 0 )
  {
    v63 = a1;
    ((void (__fastcall *)(struct IUnknown *))a1->lpVtbl->AddRef)(a1);
  }
  if ( v14 || !v66 )
    goto LABEL_37;
  for ( i = pbstr[1]; *i == 47 || *i == 92; ++i )
    ;
  if ( !IsDriveAndNotIPv6(i) )
  {
    if ( *pbstr[1] == 92 || *pbstr[1] == 47 )
    {
      v47 = pbstr[1][1];
      if ( v47 )
      {
        if ( v47 != 92 && v47 != 47 )
        {
          v61 = 1;
          *a6 = 3;
          goto LABEL_20;
        }
      }
    }
LABEL_37:
    v10 = -2147024809;
    goto LABEL_20;
  }
  *v67 = 1;
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
      v45 = (WCHAR *)operator new(0x20Au);
      v11 = v45;
      if ( v45 )
      {
        ConnectionW = WNetGetConnectionW(LocalName, v45, &nLength);
        if ( ConnectionW )
        {
          if ( !(_DWORD)pszDest )
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
          *v67 = 0;
        }
      }
      else
      {
        v10 = -2147024882;
      }
      goto LABEL_20;
    }
  }
  v61 = 1;
  v10 = 0;
LABEL_20:
  v19 = v63;
  v62 = &CUString::`vftable';
  v20 = v63 != 0;
  if ( v63 || v64 != 11 )
  {
    if ( pbstr[0] )
    {
      SysFreeString(pbstr[0]);
      v19 = v63;
      pbstr[0] = 0;
    }
    pbstr[1] = 0;
    v66 = 0;
    if ( v20 && v19 )
    {
      ((void (__fastcall *)(struct IUnknown *))v19->lpVtbl->Release)(v19);
      v63 = 0;
    }
  }
  v64 = 11;
LABEL_27:
  if ( v10 < 0 || v61 )
  {
    if ( v11 )
      CoTaskMemFree(v11);
  }
  else
  {
    PathStripToRootW(v11);
    v48 = -1;
    do
      ++v48;
    while ( v11[v48] );
    v49 = v80;
    v50 = v81;
    nLength = v48;
    *v80 = v11;
    *v50 = v48;
    while ( 1 )
    {
      v51 = (char *)*v49;
      if ( *(_WORD *)*v49 != 92 && *(_WORD *)v51 != 47 )
        break;
      *v49 = v51 + 2;
    }
    *v50 -= (v51 - (char *)v11) >> 1;
    RtlMoveMemory(v11, *v49, 2LL * (unsigned int)(*v50 + 1));
    *v49 = v11;
    v52 = wcschr(v11, 0x5Cu);
    if ( v52 )
      v53 = ((char *)v52 - (_BYTE *)*v49) >> 1;
    else
      LODWORD(v53) = *v50;
    v54 = wcschr((const wchar_t *)*v49, 0x2Fu);
    if ( v54 )
      v55 = ((char *)v54 - (_BYTE *)*v49) >> 1;
    else
      LODWORD(v55) = *v50;
    if ( (unsigned int)v53 < (unsigned int)v55 )
      LODWORD(v55) = v53;
    *v82 = v55;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18003ed90  mov     [rsp-8+arg_8], rbx
0x18003ed95  push    rbp
0x18003ed96  push    rsi
0x18003ed97  push    rdi
0x18003ed98  push    r12
0x18003ed9a  push    r13
0x18003ed9c  push    r14
0x18003ed9e  push    r15
0x18003eda0  lea     rbp, [rsp-20h]
0x18003eda5  sub     rsp, 120h
0x18003edac  mov     rax, cs:__security_cookie
0x18003edb3  xor     rax, rsp
0x18003edb6  mov     [rbp+50h+var_38], rax
0x18003edba  mov     rax, [rbp+50h+arg_30]
0x18003edc1  xor     r12d, r12d
0x18003edc4  mov     r15, [rbp+50h+arg_28]
0x18003edcb  mov     rbx, rcx
0x18003edce  mov     rcx, [rbp+50h+arg_20]
0x18003edd5  mov     [r8], r12
0x18003edd8  mov     [r9], r12d
0x18003eddb  mov     [rbp+50h+var_C0], rax
0x18003eddf  mov     [rcx], r12d
0x18003ede2  mov     [r15], r12d
0x18003ede5  mov     rax, [rbx]
0x18003ede8  mov     dword ptr [rsp+150h+pszDest], edx
0x18003edec  lea     rdx, [rsp+150h+var_F8]
0x18003edf1  mov     [rbp+50h+var_50], rcx
0x18003edf5  mov     rcx, rbx
0x18003edf8  mov     [rbp+50h+var_48], r9
0x18003edfc  mov     rax, [rax+168h]
0x18003ee03  mov     [rbp+50h+var_58], r8
0x18003ee07  mov     [rsp+150h+nLength], r12d
0x18003ee0c  mov     [rsp+150h+var_F8], r12d
0x18003ee11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ee16  mov     edi, eax
0x18003ee18  test    eax, eax
0x18003ee1a  js      loc_18003F051
0x18003ee20  lea     r14d, [r12+8]
0x18003ee25  mov     [rsp+150h+var_F4], r12d
0x18003ee2a  mov     esi, r12d
0x18003ee2d  test    byte ptr [rsp+150h+var_F8], r14b
0x18003ee32  jnz     loc_18003F0B2
0x18003ee38  test    byte ptr [rsp+150h+var_F8], 4
0x18003ee3d  jz      loc_18003F659
0x18003ee43  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x18003ee4a  mov     [rsp+150h+var_E8], r12
0x18003ee4f  mov     [rsp+150h+var_F0], rax
0x18003ee54  lea     r8, [rsp+150h+var_100]
0x18003ee59  mov     rax, [rbx]
0x18003ee5c  lea     rdx, _GUID_50295b0c_6b79_4935_aed8_05d80ec86a60
0x18003ee63  xorps   xmm0, xmm0
0x18003ee66  mov     [rbp+50h+var_C8], r12d
0x18003ee6a  mov     rcx, rbx
0x18003ee6d  mov     [rsp+150h+var_E0], r14d
0x18003ee72  movdqu  xmmword ptr [rsp+150h+pbstr], xmm0
0x18003ee78  mov     rax, [rax]
0x18003ee7b  mov     [rsp+150h+var_100], r12
0x18003ee80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ee85  mov     edx, [rsp+150h+var_E0]
0x18003ee89  test    eax, eax
0x18003ee8b  js      loc_18003F486
0x18003ee91  mov     rcx, [rsp+150h+var_100]
0x18003ee96  lea     r9, [rbp+50h+var_C8]
0x18003ee9a  lea     r8, [rbp+50h+pbstr+8]
0x18003ee9e  mov     rax, [rcx]
0x18003eea1  mov     rax, [rax+0E0h]
0x18003eea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eead  mov     rcx, [rsp+150h+var_100]
0x18003eeb2  mov     r14d, eax
0x18003eeb5  mov     rdx, [rcx]
0x18003eeb8  mov     rax, [rdx+10h]
0x18003eebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eec1  test    rbx, rbx
0x18003eec4  jz      short loc_18003EEDF
0x18003eec6  test    r14d, r14d
0x18003eec9  js      short loc_18003EEDF
0x18003eecb  mov     [rsp+150h+var_E8], rbx
0x18003eed0  mov     rcx, rbx
0x18003eed3  mov     rax, [rbx]
0x18003eed6  mov     rax, [rax+8]
0x18003eeda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eedf  mov     r12d, 5Ch ; '\'
0x18003eee5  lea     r13d, [r12-2Dh]
0x18003eeea  test    r14d, r14d
0x18003eeed  jnz     loc_18003F0A5
0x18003eef3  xor     r14d, r14d
0x18003eef6  cmp     [rbp+50h+var_C8], r14d
0x18003eefa  jbe     loc_18003F0A5
0x18003ef00  mov     rbx, [rbp+50h+pbstr+8]
0x18003ef04  cmp     [rbx], r13w
0x18003ef08  jz      loc_18003F07B
0x18003ef0e  cmp     [rbx], r12w
0x18003ef12  jz      loc_18003F07B
0x18003ef18  mov     rcx, rbx
0x18003ef1b  call    cs:__imp_?IsDriveAndNotIPv6@@YAHPEBG@Z; IsDriveAndNotIPv6(ushort const *)
0x18003ef22  nop     dword ptr [rax+rax+00h]
0x18003ef27  test    eax, eax
0x18003ef29  jz      loc_18003F08D
0x18003ef2f  mov     rax, [rbp+50h+var_C0]
0x18003ef33  mov     dword ptr [rax], 1
0x18003ef39  movzx   eax, word ptr cs:asc_180139730+1; ":\\"
0x18003ef40  mov     word ptr [rsp+150h+RootPathName+1], ax
0x18003ef45  mov     al, byte ptr cs:asc_180139730+3; ""
0x18003ef4b  mov     [rsp+150h+RootPathName+3], al
0x18003ef4f  movsx   rax, byte ptr [rbx]
0x18003ef53  mov     rcx, rax; lpsz
0x18003ef56  mov     [rsp+150h+RootPathName], al
0x18003ef5a  call    cs:__imp_CharLowerA
0x18003ef61  nop     dword ptr [rax+rax+00h]
0x18003ef66  lea     ecx, [rax-61h]
0x18003ef69  cmp     cl, 19h
0x18003ef6c  ja      loc_18003F2B4
0x18003ef72  movsx   r14, al
0x18003ef76  lea     rax, ?rgdwDriveTypeCache@@3PAKA; ulong near * rgdwDriveTypeCache
0x18003ef7d  mov     eax, [rax+r14*4-184h]
0x18003ef85  cmp     eax, 0FFFFh
0x18003ef8a  jnz     short loc_18003EFAC
0x18003ef8c  lea     rcx, [rsp+150h+RootPathName]; lpRootPathName
0x18003ef91  call    cs:__imp_GetDriveTypeA
0x18003ef98  nop     dword ptr [rax+rax+00h]
0x18003ef9d  lea     rcx, ?rgdwDriveTypeCache@@3PAKA; ulong near * rgdwDriveTypeCache
0x18003efa4  mov     [rcx+r14*4-184h], eax
0x18003efac  mov     [r15], eax
0x18003efaf  cmp     eax, 4
0x18003efb2  jz      loc_18003F4C5
0x18003efb8  xor     r15d, r15d
0x18003efbb  mov     [rsp+150h+var_F4], 1
0x18003efc3  mov     edi, r15d
0x18003efc6  mov     rcx, [rsp+150h+var_E8]
0x18003efcb  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x18003efd2  test    rcx, rcx
0x18003efd5  mov     [rsp+150h+var_F0], rax
0x18003efda  mov     ebx, r15d
0x18003efdd  mov     r14d, 0Bh
0x18003efe3  setnz   bl
0x18003efe6  mov     eax, r15d
0x18003efe9  cmp     [rsp+150h+var_E0], r14d
0x18003efee  setnz   al
0x18003eff1  test    ebx, ebx
0x18003eff3  jz      loc_18003F084
0x18003eff9  mov     rax, [rsp+150h+pbstr]
0x18003effe  test    rax, rax
0x18003f001  jnz     loc_18003F576
0x18003f007  mov     [rbp+50h+pbstr+8], r15
0x18003f00b  mov     [rbp+50h+var_C8], r15d
0x18003f00f  test    ebx, ebx
0x18003f011  jz      short loc_18003F029
0x18003f013  test    rcx, rcx
0x18003f016  jz      short loc_18003F029
0x18003f018  mov     rax, [rcx]
0x18003f01b  mov     rax, [rax+10h]
0x18003f01f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f024  mov     [rsp+150h+var_E8], r15
0x18003f029  mov     [rsp+150h+var_E0], r14d
0x18003f02e  test    edi, edi
0x18003f030  js      short loc_18003F03D
0x18003f032  cmp     [rsp+150h+var_F4], r15d
0x18003f037  jz      loc_18003F594
0x18003f03d  test    rsi, rsi
0x18003f040  jz      short loc_18003F051
0x18003f042  mov     rcx, rsi; pv
0x18003f045  call    cs:__imp_CoTaskMemFree
0x18003f04c  nop     dword ptr [rax+rax+00h]
0x18003f051  mov     eax, edi
0x18003f053  mov     rcx, [rbp+50h+var_38]
0x18003f057  xor     rcx, rsp; StackCookie
0x18003f05a  call    __security_check_cookie
0x18003f05f  mov     rbx, [rsp+150h+arg_8]
0x18003f067  add     rsp, 120h
0x18003f06e  pop     r15
0x18003f070  pop     r14
0x18003f072  pop     r13
0x18003f074  pop     r12
0x18003f076  pop     rdi
0x18003f077  pop     rsi
0x18003f078  pop     rbp
0x18003f079  retn
0x18003f07b  add     rbx, 2
0x18003f07f  jmp     loc_18003EF04
0x18003f084  test    eax, eax
0x18003f086  jz      short loc_18003F029
0x18003f088  jmp     loc_18003EFF9
0x18003f08d  mov     rax, [rbp+50h+pbstr+8]
0x18003f091  cmp     [rax], r12w
0x18003f095  jz      loc_18003F541
0x18003f09b  cmp     [rax], r13w
0x18003f09f  jz      loc_18003F541
0x18003f0a5  mov     edi, 80070057h
0x18003f0aa  xor     r15d, r15d
0x18003f0ad  jmp     loc_18003EFC6
0x18003f0b2  lea     rcx, ?FEATURE_ZONES_MUTZ_DISABLE_LANMANCHECK@FCK@@3VCFeatureControlKey@@A; this
0x18003f0b9  mov     dword ptr [rsp+150h+RootPathName], r12d
0x18003f0be  mov     dword ptr [rsp+150h+pszDest], r12d
0x18003f0c3  mov     [rsp+150h+var_100], r12
0x18003f0c8  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x18003f0cd  lea     rdx, [rsp+150h+var_100]; struct IUriPriv **
0x18003f0d2  mov     rcx, rbx; struct IUnknown *
0x18003f0d5  test    eax, eax
0x18003f0d7  jz      loc_18003F2BC
0x18003f0dd  call    ?GetUriWithoutRedirector@@YAJPEAUIUriPriv@@PEAPEAU1@@Z; GetUriWithoutRedirector(IUriPriv *,IUriPriv * *)
0x18003f0e2  mov     edi, eax
0x18003f0e4  test    eax, eax
0x18003f0e6  js      loc_18003F051
0x18003f0ec  mov     rbx, [rsp+150h+var_100]
0x18003f0f1  lea     r9, [rsp+150h+RootPathName]; int *
0x18003f0f6  mov     rdx, rbx; struct IUri *
0x18003f0f9  lea     rcx, [rbp+50h+var_88]; this
0x18003f0fd  mov     r8d, 6; enum __MIDL_IUri_0001
0x18003f103  call    ??0CUString@@QEAA@PEAUIUri@@W4__MIDL_IUri_0001@@PEAJ@Z; CUString::CUString(IUri *,__MIDL_IUri_0001,long *)
0x18003f108  mov     rdx, [rsp+150h+var_100]; struct IUri *
0x18003f10d  lea     r9, [rsp+150h+pszDest]; int *
0x18003f112  mov     r8d, r14d; enum __MIDL_IUri_0001
0x18003f115  lea     rcx, [rbp+50h+var_B8]; this
0x18003f119  call    ??0CUString@@QEAA@PEAUIUri@@W4__MIDL_IUri_0001@@PEAJ@Z; CUString::CUString(IUri *,__MIDL_IUri_0001,long *)
0x18003f11e  mov     r13d, 2Fh ; '/'
0x18003f124  xor     r10d, r10d
0x18003f127  lea     r12d, [r13+2Dh]
0x18003f12b  cmp     dword ptr [rsp+150h+RootPathName], r10d
0x18003f130  jnz     loc_18003F43E
0x18003f136  mov     eax, dword ptr [rbp+50h+var_60]
0x18003f139  test    eax, eax
0x18003f13b  jz      loc_18003F43E
0x18003f141  mov     ecx, [rsp+150h+nLength]
0x18003f145  mov     r14d, r10d
0x18003f148  add     ecx, eax
0x18003f14a  mov     [rsp+150h+nLength], ecx
0x18003f14e  cmp     dword ptr [rsp+150h+pszDest], r10d
0x18003f153  jnz     short loc_18003F17A
0x18003f155  mov     edx, [rbp+50h+var_90]
0x18003f158  test    edx, edx
0x18003f15a  jz      short loc_18003F17A
0x18003f15c  mov     rax, [rbp+50h+var_98]
0x18003f160  movzx   r8d, word ptr [rax]
0x18003f164  cmp     r8w, r12w
0x18003f168  jz      short loc_18003F16C
0x18003f16a  inc     ecx
0x18003f16c  add     ecx, edx
0x18003f16e  cmp     r8w, r12w
0x18003f172  mov     [rsp+150h+nLength], ecx
0x18003f176  setnz   r14b
0x18003f17a  lea     edi, [rcx+1]
0x18003f17d  mov     eax, 2
0x18003f182  add     rdi, 2
0x18003f186  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003f18d  mul     rdi
0x18003f190  mov     qword ptr [rbp+50h+LocalName], rdi
0x18003f194  cmovb   rax, rcx
0x18003f198  mov     rcx, rax; Size
0x18003f19b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003f1a0  xor     r10d, r10d
0x18003f1a3  mov     [rsp+150h+pszDest], rax
0x18003f1a8  mov     rsi, rax
0x18003f1ab  test    rax, rax
0x18003f1ae  jz      loc_18003F3D6
0x18003f1b4  mov     [rsp+150h+var_120], r10d; unsigned int
0x18003f1b9  lea     rax, [rbp+50h+LocalName]
0x18003f1bd  mov     [rsp+150h+var_128], rax; unsigned __int64 *
0x18003f1c2  lea     r9d, [r10+2]; unsigned __int64
0x18003f1c6  lea     rax, [rsp+150h+pszDest]
0x18003f1cb  mov     rdx, rdi; unsigned __int64
0x18003f1ce  lea     r8, asc_1801405A0; "\\\\"
0x18003f1d5  mov     [rsp+150h+var_130], rax; unsigned __int16 **
0x18003f1da  mov     rcx, rsi; pszDest
0x18003f1dd  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x18003f1e2  xor     r10d, r10d
0x18003f1e5  mov     edi, eax
0x18003f1e7  test    eax, eax
0x18003f1e9  js      loc_18003F2CD
0x18003f1ef  mov     r9d, dword ptr [rbp+50h+var_60]; unsigned __int64
0x18003f1f3  lea     rax, [rbp+50h+LocalName]
0x18003f1f7  mov     r8, [rbp+50h+var_68]; unsigned __int16 *
0x18003f1fb  mov     rdx, qword ptr [rbp+50h+LocalName]; unsigned __int64
0x18003f1ff  mov     rcx, [rsp+150h+pszDest]; pszDest
0x18003f204  mov     [rsp+150h+var_120], r10d; unsigned int
0x18003f209  mov     [rsp+150h+var_128], rax; unsigned __int64 *
0x18003f20e  lea     rax, [rsp+150h+pszDest]
0x18003f213  mov     [rsp+150h+var_130], rax; unsigned __int16 **
0x18003f218  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x18003f21d  xor     r10d, r10d
0x18003f220  mov     edi, eax
0x18003f222  test    eax, eax
0x18003f224  js      loc_18003F2CD
0x18003f22a  test    r14d, r14d
0x18003f22d  jz      short loc_18003F269
0x18003f22f  mov     rdx, qword ptr [rbp+50h+LocalName]; unsigned __int64
0x18003f233  lea     rax, [rbp+50h+LocalName]
0x18003f237  mov     rcx, [rsp+150h+pszDest]; pszDest
0x18003f23c  lea     r9d, [r10+1]; unsigned __int64
0x18003f240  mov     [rsp+150h+var_120], r10d; unsigned int
0x18003f245  lea     r8, SubBlock; "\\"
0x18003f24c  mov     [rsp+150h+var_128], rax; unsigned __int64 *
0x18003f251  lea     rax, [rsp+150h+pszDest]
0x18003f256  mov     [rsp+150h+var_130], rax; unsigned __int16 **
0x18003f25b  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x18003f260  xor     r10d, r10d
0x18003f263  mov     edi, eax
0x18003f265  test    eax, eax
0x18003f267  js      short loc_18003F2CD
0x18003f269  cmp     [rbp+50h+var_90], r10d
0x18003f26d  jbe     short loc_18003F2CD
  ... truncated ...
```
