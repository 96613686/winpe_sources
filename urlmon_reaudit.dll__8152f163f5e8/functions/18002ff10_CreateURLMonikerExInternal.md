# CreateURLMonikerExInternal

- ea: `0x18002ff10`
- end: `0x1800304e6`
- name: `CreateURLMonikerExInternal`
- size: `1494`
- prototype: ``
- caller_count: `12`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002faf0`
- `0x18002fb10`
- `0x180063ea0`
- `0x180091e60`
- `0x1800c2964`
- `0x1800c812c`
- `0x1800d6c38`
- `0x1800d7ab0`
- `0x1800f1c90`
- `0x1800f36d0`
- `0x1800f4450`
- `0x1800f9f24`

## callees

- `0x18001db50`
- `0x180028410`
- `0x180028510`
- `0x18002ff10`
- `0x1800304f0`
- `0x1800309f0`
- `0x180033858`
- `0x18003e100`
- `0x18007ec4c`
- `0x180088604`
- `0x180089924`
- `0x1800940e4`
- `0x1800af5b0`
- `0x1800f35e4`
- `0x1800ff2b0`
- `0x180129010`

## import_xrefs

- `iertutil!CreateUri` at `0x18003005f`
- `iertutil!CreateUri` at `0x18003005f`
- `iertutil!__imp_?IECompatLogURICreationFailure@@YAXPEBGJ@Z` at `0x1800301e4`
- `iertutil!__imp_?IECompatLogURICreationFailure@@YAXPEBGJ@Z` at `0x1800301e4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18002ffac`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18002ffac`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18002ffc4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18002ffc4`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNW` at `0x180030343`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNW` at `0x180030343`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800300df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800300df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800303a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800304d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800303a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800304d5`

## string_xrefs

- `0x180030369`: `OldUri`
- `0x180030353`: `NewUri`
- `0x180030362`: `CreateURLMonikerDifference`

## pseudocode

```c
__int64 __fastcall CreateURLMonikerExInternal(
        struct IMoniker *a1,
        const WCHAR *a2,
        CUrlMon **a3,
        int a4,
        unsigned int a5)
{
  int v7; // esi
  unsigned int v8; // r14d
  int v9; // r12d
  __int64 v10; // rbx
  unsigned int v11; // r13d
  const WCHAR *v12; // rcx
  unsigned int v13; // ebx
  DWORD v14; // edx
  HRESULT v15; // r13d
  struct IUri *v16; // r9
  int v17; // ebx
  CUrlMon *v18; // rax
  CUrlMon *v19; // rax
  const unsigned __int16 *v21; // rdi
  int v22; // eax
  const WCHAR *v23; // rbx
  int v24; // eax
  HRESULT IsFeatureEnabledInternal; // eax
  unsigned __int16 **v26; // r9
  unsigned __int16 *v27; // r13
  unsigned int v28; // eax
  CUrlMon *v29; // r9
  CUrlMon *v30; // rax
  unsigned __int64 *v31; // [rsp+20h] [rbp-81h]
  int v32; // [rsp+20h] [rbp-81h]
  const WCHAR *psz2; // [rsp+40h] [rbp-61h]
  int v34; // [rsp+4Ch] [rbp-55h] BYREF
  int v35; // [rsp+50h] [rbp-51h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-49h]
  IUri *ppURI; // [rsp+60h] [rbp-41h] BYREF
  unsigned __int64 v38[2]; // [rsp+68h] [rbp-39h] BYREF
  unsigned int v39; // [rsp+78h] [rbp-29h]
  void **v40; // [rsp+80h] [rbp-21h] BYREF
  LPVOID v41; // [rsp+88h] [rbp-19h]
  __int64 v42; // [rsp+90h] [rbp-11h]
  void *v43; // [rsp+98h] [rbp-9h]
  __int64 v44; // [rsp+A0h] [rbp-1h]
  _QWORD v45[9]; // [rsp+A8h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+57h]
  struct IUri *nChar; // [rsp+110h] [rbp+6Fh] BYREF
  int v49; // [rsp+118h] [rbp+77h]

  v49 = a4;
  ppURI = 0;
  _InterlockedIncrement((volatile signed __int32 *)&g_cRef);
  if ( !a3 )
  {
    v17 = -2147024809;
    goto LABEL_39;
  }
  *a3 = 0;
  if ( !a2 )
  {
    v17 = -2147024809;
    goto LABEL_39;
  }
  v7 = a4 & 1;
  v8 = 50342549;
  v9 = a4 & 2;
  if ( (a4 & 2) != 0 )
  {
    a5 = 50342549;
  }
  else
  {
    a5 = 50342789;
    if ( (a4 & 1) == 0 )
    {
      v10 = -1;
      a5 = 50375589;
      do
        ++v10;
      while ( a2[v10] );
      pv = 0;
      v11 = v10;
      LODWORD(nChar) = v10;
      psz2 = a2;
      goto LABEL_8;
    }
  }
  v12 = a2;
  pv = 0;
  psz2 = a2;
  v10 = -1;
  do
    ++v10;
  while ( a2[v10] );
  LODWORD(nChar) = v10;
  v11 = v10;
  if ( (a4 & 1) != 0 )
    goto LABEL_16;
LABEL_8:
  if ( PathGetDriveNumberW(a2) == -1 && !PathIsUNCW(a2) && !IsLegacyFileURI(a2) )
    goto LABEL_11;
  v39 = v10;
  IsFeatureEnabledInternal = CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_CREATE_URL_MONIKER_DISABLE_LEGACY_COMPAT);
  v12 = a2;
  if ( IsFeatureEnabledInternal == 1 )
  {
    pv = OLESTRDuplicate(a2);
    if ( pv )
    {
      v42 = v11;
      v38[0] = v11 + 1;
      v40 = &CPercentDecodeList::`vftable';
      v35 = -1;
      v43 = &unk_18013CF20;
      v34 = -1;
      v41 = pv;
      v44 = 1;
      CPercentDecodeString::Decode(
        (CPercentDecodeString *)&v40,
        (unsigned __int16 *)pv,
        v38,
        (unsigned __int16 **)pv,
        v31,
        7u);
      v22 = LongLongToULong(v38[0], (unsigned int *)&nChar);
      if ( v22 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x114,
          (unsigned int)"onecoreuap\\inetcore\\urlmon\\utils\\urlfile.cxx",
          (const char *)(unsigned int)v22,
          (int)v31);
      if ( (int)EnsureSecurityManager() < 0
        || ((int (__fastcall *)(IInternetSecurityManager *, const WCHAR *, int *, _QWORD))g_pInternetSecurityManager->lpVtbl->MapUrlToZone)(
             g_pInternetSecurityManager,
             a2,
             &v35,
             0) < 0
        || (v23 = (const WCHAR *)pv,
            ((int (__fastcall *)(IInternetSecurityManager *, LPVOID, int *, _QWORD))g_pInternetSecurityManager->lpVtbl->MapUrlToZone)(
              g_pInternetSecurityManager,
              pv,
              &v34,
              0) < 0) )
      {
        LODWORD(v10) = (_DWORD)nChar;
        v12 = a2;
        v15 = 1;
      }
      else
      {
        v12 = a2;
        v15 = 1;
        if ( v35 == v34 )
          v12 = v23;
        LODWORD(v10) = (_DWORD)nChar;
        psz2 = v12;
      }
    }
    else
    {
      v15 = -2147024882;
      v12 = a2;
    }
  }
  else
  {
    v15 = IsFeatureEnabledInternal;
  }
  if ( g_cmptlgs == 1 )
  {
LABEL_48:
    if ( v15 >= 0 )
      goto LABEL_16;
LABEL_49:
    v13 = a5;
    goto LABEL_50;
  }
  if ( !(unsigned int)IECompatLoggingEnabled() )
  {
    v12 = psz2;
    goto LABEL_48;
  }
  if ( v15 < 0 )
    goto LABEL_49;
  v27 = OLESTRDuplicate(a2);
  if ( !v27 )
  {
LABEL_11:
    v12 = psz2;
    goto LABEL_16;
  }
  v40 = &CPercentDecodeList::`vftable';
  v42 = v39;
  v41 = v27;
  v43 = &unk_18013D094;
  v38[0] = v39 + 1;
  v44 = 0;
  CPercentDecodeString::Decode((CPercentDecodeString *)&v40, v27, v38, v26, v31, 7u);
  v24 = LongLongToULong(v38[0], (unsigned int *)&nChar);
  if ( v24 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0xE4,
      (unsigned int)"onecoreuap\\inetcore\\urlmon\\utils\\urlfile.cxx",
      (const char *)(unsigned int)v24,
      v32);
  if ( StrCmpNW(v27, psz2, v10) )
  {
    v38[0] = (unsigned __int64)psz2;
    v45[0] = L"NewUri";
    v38[1] = (unsigned __int64)v27;
    v45[1] = L"OldUri";
    IECompatLogEventWithUrl(
      -1073740785,
      (unsigned int)L"CreateURLMonikerDifference",
      (_DWORD)a2,
      0,
      2,
      (__int64)v45,
      (__int64)v38);
  }
  CoTaskMemFree(v27);
  v12 = psz2;
LABEL_16:
  v13 = a5;
  v14 = a5;
  if ( (a5 & 0x110) == 0 )
    v14 = a5 | 0x100;
  if ( (v14 & 0x1800) == 0 )
    v14 |= 0x800u;
  if ( (v14 & 0x6000) == 0 )
    v14 |= 0x2000u;
  if ( (v14 & 0x2000000) == 0 )
    v14 |= 0x2000000u;
  if ( (v14 & 0x1000000) == 0 )
    v14 |= 0x1000000u;
  v15 = CreateUri(v12, v14, 0, &ppURI);
  if ( v15 >= 0 && ppURI )
  {
    nChar = 0;
    if ( (v49 & 0xFFFFFFFC) == 0 )
    {
      if ( !v9 )
      {
        v8 = 50342789;
        if ( !v7 )
          v8 = 50375589;
      }
      v16 = ppURI;
      *a3 = 0;
      v17 = CombineIMonikerAndIUri(0, a1, 0, v16, &nChar, v8, 0);
      if ( v17 < 0 )
        goto LABEL_35;
      v18 = (CUrlMon *)CoTaskMemAlloc(0x70u);
      if ( v18 )
      {
        *(_OWORD *)v18 = 0;
        *((_OWORD *)v18 + 1) = 0;
        *((_OWORD *)v18 + 2) = 0;
        *((_OWORD *)v18 + 3) = 0;
        *((_OWORD *)v18 + 4) = 0;
        *((_OWORD *)v18 + 5) = 0;
        *((_OWORD *)v18 + 6) = 0;
        v19 = CUrlMon::CUrlMon(v18, nChar, v8);
        *a3 = v19;
        if ( v19 )
          goto LABEL_35;
      }
      else
      {
        *a3 = 0;
      }
      v17 = -2147024882;
LABEL_35:
      if ( nChar )
        ((void (__fastcall *)(struct IUri *))nChar->lpVtbl->Release)(nChar);
      goto LABEL_37;
    }
    v17 = -2147024809;
    goto LABEL_37;
  }
LABEL_50:
  if ( g_cmptlgs == 1 )
  {
    v21 = psz2;
  }
  else
  {
    v21 = psz2;
    if ( (unsigned int)IECompatLoggingEnabled() )
      IECompatLogURICreationFailure(psz2, v15);
  }
  if ( operator new(0x70u) )
  {
    v28 = HelperAddUriDefaultFlags(0x3002B80u, v13);
    v30 = CUrlMon::CUrlMon(v29, v21, v28);
    *a3 = v30;
    if ( v30 )
    {
      v17 = 0;
      goto LABEL_37;
    }
  }
  else
  {
    *a3 = 0;
  }
  v17 = -2147024882;
LABEL_37:
  if ( pv )
    CoTaskMemFree(pv);
LABEL_39:
  if ( ppURI )
  {
    ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
    ppURI = 0;
  }
  if ( g_cRef > 0 )
    _InterlockedDecrement((volatile signed __int32 *)&g_cRef);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18002ff10  mov     [rsp-8+arg_8], rbx
0x18002ff15  mov     [rsp-8+arg_18], r9d
0x18002ff1a  mov     [rsp-8+arg_0], rcx
0x18002ff1f  push    rbp
0x18002ff20  push    rsi
0x18002ff21  push    rdi
0x18002ff22  push    r12
0x18002ff24  push    r13
0x18002ff26  push    r14
0x18002ff28  push    r15
0x18002ff2a  lea     rbp, [rsp-1Fh]
0x18002ff2f  sub     rsp, 0C0h
0x18002ff36  xor     r13d, r13d
0x18002ff39  mov     eax, r9d
0x18002ff3c  mov     [rbp+4Fh+ppURI], r13
0x18002ff40  mov     r15, r8
0x18002ff43  mov     rdi, rdx
0x18002ff46  lock inc cs:?g_cRef@@3VCRefCount@@A; CRefCount g_cRef
0x18002ff4d  test    r8, r8
0x18002ff50  jz      loc_180030199
0x18002ff56  mov     [r8], r13
0x18002ff59  test    rdx, rdx
0x18002ff5c  jz      loc_1800301A0
0x18002ff62  mov     esi, eax
0x18002ff64  mov     r12d, eax
0x18002ff67  and     esi, 1
0x18002ff6a  mov     r14d, 3002A95h
0x18002ff70  and     r12d, 2
0x18002ff74  jnz     short loc_18002FFEE
0x18002ff76  mov     eax, 3002B85h
0x18002ff7b  mov     [rbp+4Fh+arg_20], eax
0x18002ff7e  test    esi, esi
0x18002ff80  jnz     short loc_18002FFF2
0x18002ff82  mov     eax, 300ABA5h
0x18002ff87  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18002ff8e  mov     [rbp+4Fh+arg_20], eax
0x18002ff91  inc     rbx
0x18002ff94  cmp     [rdx+rbx*2], r13w
0x18002ff99  jnz     short loc_18002FF91
0x18002ff9b  mov     [rbp+4Fh+pv], r13
0x18002ff9f  mov     r13d, ebx
0x18002ffa2  mov     dword ptr [rbp+4Fh+nChar], ebx
0x18002ffa5  mov     [rbp+4Fh+psz2], rdi
0x18002ffa9  mov     rcx, rdi; pszPath
0x18002ffac  call    cs:__imp_PathGetDriveNumberW
0x18002ffb3  nop     dword ptr [rax+rax+00h]
0x18002ffb8  cmp     eax, 0FFFFFFFFh
0x18002ffbb  jnz     loc_1800303B9
0x18002ffc1  mov     rcx, rdi; pszPath
0x18002ffc4  call    cs:__imp_PathIsUNCW
0x18002ffcb  nop     dword ptr [rax+rax+00h]
0x18002ffd0  test    eax, eax
0x18002ffd2  jnz     loc_1800303B9
0x18002ffd8  mov     rcx, rdi; unsigned __int16 *
0x18002ffdb  call    ?IsLegacyFileURI@@YA_NPEBG@Z; IsLegacyFileURI(ushort const *)
0x18002ffe0  test    al, al
0x18002ffe2  jnz     loc_1800303B9
0x18002ffe8  mov     rcx, [rbp+4Fh+psz2]
0x18002ffec  jmp     short loc_180030018
0x18002ffee  mov     [rbp+4Fh+arg_20], r14d
0x18002fff2  mov     rcx, rdi; pwzURI
0x18002fff5  mov     [rbp+4Fh+pv], r13
0x18002fff9  mov     [rbp+4Fh+psz2], rcx
0x18002fffd  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180030004  inc     rbx
0x180030007  cmp     [rdx+rbx*2], r13w
0x18003000c  jnz     short loc_180030004
0x18003000e  mov     dword ptr [rbp+4Fh+nChar], ebx
0x180030011  mov     r13, rbx
0x180030014  test    esi, esi
0x180030016  jz      short loc_18002FFA9
0x180030018  mov     ebx, [rbp+4Fh+arg_20]
0x18003001b  mov     eax, ebx
0x18003001d  bts     eax, 8
0x180030021  mov     edx, ebx
0x180030023  test    ebx, 110h
0x180030029  cmovz   edx, eax
0x18003002c  test    edx, 1800h
0x180030032  jnz     short loc_180030038
0x180030034  bts     edx, 0Bh
0x180030038  test    edx, 6000h
0x18003003e  jnz     short loc_180030044
0x180030040  bts     edx, 0Dh
0x180030044  bt      edx, 19h
0x180030048  jb      short loc_18003004E
0x18003004a  bts     edx, 19h
0x18003004e  bt      edx, 18h
0x180030052  jb      short loc_180030058
0x180030054  bts     edx, 18h; dwFlags
0x180030058  lea     r9, [rbp+4Fh+ppURI]; ppURI
0x18003005c  xor     r8d, r8d; dwReserved
0x18003005f  call    cs:__imp_CreateUri
0x180030066  nop     dword ptr [rax+rax+00h]
0x18003006b  mov     r13d, eax
0x18003006e  test    eax, eax
0x180030070  js      loc_1800301C0
0x180030076  mov     rdx, [rbp+4Fh+ppURI]
0x18003007a  test    rdx, rdx
0x18003007d  jz      loc_1800301C0
0x180030083  xor     r13d, r13d
0x180030086  test    [rbp+4Fh+arg_18], 0FFFFFFFCh
0x18003008d  mov     [rbp+4Fh+nChar], r13
0x180030091  jnz     loc_180030475
0x180030097  test    r12d, r12d
0x18003009a  jnz     short loc_1800300AD
0x18003009c  test    esi, esi
0x18003009e  mov     r14d, 3002B85h
0x1800300a4  mov     eax, 300ABA5h
0x1800300a9  cmovz   r14d, eax
0x1800300ad  mov     [rsp+0F0h+var_C0], r13d; unsigned int
0x1800300b2  lea     rax, [rbp+4Fh+nChar]
0x1800300b6  mov     r9, rdx; struct IUri *
0x1800300b9  mov     [rsp+0F0h+var_C8], r14d; unsigned int
0x1800300be  mov     rdx, [rbp+4Fh+arg_0]; struct IMoniker *
0x1800300c2  xor     r8d, r8d; struct IMoniker *
0x1800300c5  xor     ecx, ecx; struct IBindCtx *
0x1800300c7  mov     [rsp+0F0h+var_D0], rax; struct IUri **
0x1800300cc  mov     [r15], r13
0x1800300cf  call    ?CombineIMonikerAndIUri@@YAJPEAUIBindCtx@@PEAUIMoniker@@1PEAUIUri@@PEAPEAU3@KK@Z; CombineIMonikerAndIUri(IBindCtx *,IMoniker *,IMoniker *,IUri *,IUri * *,ulong,ulong)
0x1800300d4  mov     ebx, eax
0x1800300d6  test    eax, eax
0x1800300d8  js      short loc_18003012D
0x1800300da  mov     ecx, 70h ; 'p'; cb
0x1800300df  call    cs:__imp_CoTaskMemAlloc
0x1800300e6  nop     dword ptr [rax+rax+00h]
0x1800300eb  test    rax, rax
0x1800300ee  jz      loc_1800301A7
0x1800300f4  xorps   xmm0, xmm0
0x1800300f7  mov     r8d, r14d; unsigned int
0x1800300fa  movups  xmmword ptr [rax], xmm0
0x1800300fd  mov     rcx, rax; this
0x180030100  movups  xmmword ptr [rax+10h], xmm0
0x180030104  movups  xmmword ptr [rax+20h], xmm0
0x180030108  movups  xmmword ptr [rax+30h], xmm0
0x18003010c  movups  xmmword ptr [rax+40h], xmm0
0x180030110  movups  xmmword ptr [rax+50h], xmm0
0x180030114  movups  xmmword ptr [rax+60h], xmm0
0x180030118  mov     rdx, [rbp+4Fh+nChar]; struct IUri *
0x18003011c  call    ??0CUrlMon@@QEAA@PEAUIUri@@K@Z; CUrlMon::CUrlMon(IUri *,ulong)
0x180030121  mov     [r15], rax
0x180030124  test    rax, rax
0x180030127  jz      loc_1800301AA
0x18003012d  mov     rcx, [rbp+4Fh+nChar]
0x180030131  test    rcx, rcx
0x180030134  jz      short loc_180030142
0x180030136  mov     rax, [rcx]
0x180030139  mov     rax, [rax+10h]
0x18003013d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030142  mov     rax, [rbp+4Fh+pv]
0x180030146  test    rax, rax
0x180030149  jnz     loc_1800304D2
0x18003014f  mov     rdx, [rbp+4Fh+ppURI]
0x180030153  test    rdx, rdx
0x180030156  jz      short loc_18003016B
0x180030158  mov     rcx, [rdx]
0x18003015b  mov     rax, [rcx+10h]
0x18003015f  mov     rcx, rdx
0x180030162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030167  mov     [rbp+4Fh+ppURI], r13
0x18003016b  cmp     cs:?g_cRef@@3VCRefCount@@A, 0; CRefCount g_cRef
0x180030172  jle     short loc_18003017B
0x180030174  lock dec cs:?g_cRef@@3VCRefCount@@A; CRefCount g_cRef
0x18003017b  mov     eax, ebx
0x18003017d  mov     rbx, [rsp+0F0h+arg_8]
0x180030185  add     rsp, 0C0h
0x18003018c  pop     r15
0x18003018e  pop     r14
0x180030190  pop     r13
0x180030192  pop     r12
0x180030194  pop     rdi
0x180030195  pop     rsi
0x180030196  pop     rbp
0x180030197  retn
0x180030199  mov     ebx, 80070057h
0x18003019e  jmp     short loc_18003014F
0x1800301a0  mov     ebx, 80070057h
0x1800301a5  jmp     short loc_18003014F
0x1800301a7  mov     [r15], r13
0x1800301aa  mov     ebx, 8007000Eh
0x1800301af  jmp     loc_18003012D
0x1800301b4  test    r13d, r13d
0x1800301b7  jns     loc_180030018
0x1800301bd  mov     ebx, [rbp+4Fh+arg_20]
0x1800301c0  cmp     cs:?g_cmptlgs@@3W4CMPTLGS@@A, 1; CMPTLGS g_cmptlgs
0x1800301c7  jz      loc_18003047F
0x1800301cd  call    ?IECompatLoggingEnabled@@YAHXZ; IECompatLoggingEnabled(void)
0x1800301d2  mov     rdi, [rbp+4Fh+psz2]
0x1800301d6  test    eax, eax
0x1800301d8  jz      loc_180030483
0x1800301de  mov     edx, r13d
0x1800301e1  mov     rcx, rdi
0x1800301e4  call    cs:__imp_?IECompatLogURICreationFailure@@YAXPEBGJ@Z; IECompatLogURICreationFailure(ushort const *,long)
0x1800301eb  nop     dword ptr [rax+rax+00h]
0x1800301f0  jmp     loc_180030483
0x1800301f5  mov     eax, r13d
0x1800301f8  lea     ecx, [r13+1]
0x1800301fc  mov     [rbp+4Fh+var_60], rax
0x180030200  lea     r8, [rbp+4Fh+var_88]; unsigned __int64 *
0x180030204  lea     rax, ??_7CPercentDecodeList@@6B@; const CPercentDecodeList::`vftable'
0x18003020b  mov     [rbp+4Fh+var_88], rcx
0x18003020f  mov     [rbp+4Fh+var_70], rax
0x180030213  lea     rcx, [rbp+4Fh+var_70]; this
0x180030217  lea     rax, unk_18013CF20
0x18003021e  mov     [rbp+4Fh+var_A0], 0FFFFFFFFh
0x180030225  mov     rdx, r9; unsigned __int16 *
0x180030228  mov     [rbp+4Fh+var_58], rax
0x18003022c  mov     [rbp+4Fh+var_A4], 0FFFFFFFFh
0x180030233  mov     [rbp+4Fh+var_68], r9
0x180030237  mov     [rbp+4Fh+var_50], 1
0x18003023f  mov     [rsp+0F0h+var_C8], 7; unsigned int
0x180030247  call    ?Decode@CPercentDecodeString@@QEAAJPEAGPEA_KPEAPEAG1K@Z; CPercentDecodeString::Decode(ushort *,unsigned __int64 *,ushort * *,unsigned __int64 *,ulong)
0x18003024c  mov     rcx, [rbp+4Fh+var_88]; __int64
0x180030250  lea     rdx, [rbp+4Fh+nChar]; unsigned int *
0x180030254  call    ?LongLongToULong@@YAJ_JPEAK@Z; LongLongToULong(__int64,ulong *)
0x180030259  test    eax, eax
0x18003025b  js      loc_1800303F3
0x180030261  call    ?EnsureSecurityManager@@YAJXZ; EnsureSecurityManager(void)
0x180030266  test    eax, eax
0x180030268  js      loc_18003040C
0x18003026e  mov     rcx, cs:?g_pInternetSecurityManager@@3PEAUIInternetSecurityManager@@EA; IInternetSecurityManager * g_pInternetSecurityManager
0x180030275  lea     r8, [rbp+4Fh+var_A0]
0x180030279  xor     r9d, r9d
0x18003027c  mov     rdx, rdi
0x18003027f  mov     rax, [rcx]
0x180030282  mov     rax, [rax+28h]
0x180030286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003028b  test    eax, eax
0x18003028d  js      loc_18003040C
0x180030293  mov     rcx, cs:?g_pInternetSecurityManager@@3PEAUIInternetSecurityManager@@EA; IInternetSecurityManager * g_pInternetSecurityManager
0x18003029a  lea     r8, [rbp+4Fh+var_A4]
0x18003029e  mov     rbx, [rbp+4Fh+pv]
0x1800302a2  xor     r9d, r9d
0x1800302a5  mov     rdx, rbx
0x1800302a8  mov     rax, [rcx]
0x1800302ab  mov     rax, [rax+28h]
0x1800302af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800302b4  test    eax, eax
0x1800302b6  js      loc_18003040C
0x1800302bc  mov     eax, [rbp+4Fh+var_A4]
0x1800302bf  mov     rcx, rdi
0x1800302c2  cmp     [rbp+4Fh+var_A0], eax
0x1800302c5  mov     r13d, [rbp+4Fh+var_A8]
0x1800302c9  cmovz   rcx, rbx
0x1800302cd  mov     ebx, dword ptr [rbp+4Fh+nChar]
0x1800302d0  mov     [rbp+4Fh+psz2], rcx
0x1800302d4  jmp     loc_18003041B
0x1800302d9  mov     edx, [rbp+4Fh+var_78]
0x1800302dc  lea     rax, ??_7CPercentDecodeList@@6B@; const CPercentDecodeList::`vftable'
0x1800302e3  mov     [rbp+4Fh+var_70], rax
0x1800302e7  lea     r8, [rbp+4Fh+var_88]; unsigned __int64 *
0x1800302eb  mov     [rbp+4Fh+var_60], rdx
0x1800302ef  lea     rax, unk_18013D094
0x1800302f6  mov     [rbp+4Fh+var_68], r13
0x1800302fa  lea     ecx, [rdx+1]
0x1800302fd  mov     [rbp+4Fh+var_58], rax
0x180030301  mov     [rbp+4Fh+var_88], rcx
0x180030305  mov     rdx, r13; unsigned __int16 *
0x180030308  lea     rcx, [rbp+4Fh+var_70]; this
0x18003030c  mov     [rbp+4Fh+var_50], 0
0x180030314  mov     [rsp+0F0h+var_C8], 7; unsigned int
0x18003031c  call    ?Decode@CPercentDecodeString@@QEAAJPEAGPEA_KPEAPEAG1K@Z; CPercentDecodeString::Decode(ushort *,unsigned __int64 *,ushort * *,unsigned __int64 *,ulong)
0x180030321  mov     rcx, [rbp+4Fh+var_88]; __int64
0x180030325  lea     rdx, [rbp+4Fh+nChar]; unsigned int *
0x180030329  call    ?LongLongToULong@@YAJ_JPEAK@Z; LongLongToULong(__int64,ulong *)
0x18003032e  test    eax, eax
0x180030330  js      loc_180030453
0x180030336  mov     r8d, ebx; nChar
0x180030339  mov     rcx, r13; psz1
0x18003033c  mov     rbx, [rbp+4Fh+psz2]
0x180030340  mov     rdx, rbx; psz2
0x180030343  call    cs:__imp_StrCmpNW
0x18003034a  nop     dword ptr [rax+rax+00h]
0x18003034f  test    eax, eax
0x180030351  jz      short loc_1800303A2
0x180030353  lea     rax, aNewuri; "NewUri"
0x18003035a  mov     [rbp+4Fh+var_88], rbx
0x18003035e  mov     [rbp+4Fh+var_48], rax
0x180030362  lea     rdx, aCreateurlmonik_2; "CreateURLMonikerDifference"
0x180030369  lea     rax, aOlduri; "OldUri"
0x180030370  mov     [rbp+4Fh+var_80], r13
0x180030374  mov     [rbp+4Fh+var_40], rax
0x180030378  xor     r9d, r9d
0x18003037b  lea     rax, [rbp+4Fh+var_88]
0x18003037f  mov     r8, rdi
0x180030382  mov     qword ptr [rsp+0F0h+var_C0], rax
0x180030387  mov     ecx, 0C000040Fh
0x18003038c  lea     rax, [rbp+4Fh+var_48]
0x180030390  mov     qword ptr [rsp+0F0h+var_C8], rax
0x180030395  mov     dword ptr [rsp+0F0h+var_D0], 2
0x18003039d  call    IECompatLogEventWithUrl
0x1800303a2  mov     rcx, r13; pv
0x1800303a5  call    cs:__imp_CoTaskMemFree
0x1800303ac  nop     dword ptr [rax+rax+00h]
0x1800303b1  mov     rcx, rbx
0x1800303b4  jmp     loc_180030018
0x1800303b9  lea     rcx, ?FEATURE_CREATE_URL_MONIKER_DISABLE_LEGACY_COMPAT@FCK@@3VCFeatureControlKey@@A; this
0x1800303c0  mov     [rbp+4Fh+var_78], ebx
0x1800303c3  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x1800303c8  mov     [rbp+4Fh+var_A8], eax
0x1800303cb  mov     rcx, rdi; unsigned __int16 *
  ... truncated ...
```
