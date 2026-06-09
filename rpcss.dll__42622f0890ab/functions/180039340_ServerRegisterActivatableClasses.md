# ServerRegisterActivatableClasses

- ea: `0x180039340`
- end: `0x180039a9f`
- name: `ServerRegisterActivatableClasses`
- size: `1887`
- prototype: `__int64 __fastcall(void *, struct CProcess *, unsigned int *, char **, _DWORD *)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180005c40`
- `0x180012238`
- `0x180014870`
- `0x180019a3c`
- `0x18001b670`
- `0x18002ba28`
- `0x180039340`
- `0x180039aa8`
- `0x18003a540`
- `0x18003a908`
- `0x18003aabc`
- `0x18003aba0`
- `0x18003ac10`
- `0x18003b604`
- `0x18003e9d8`
- `0x180040918`
- `0x180056d48`
- `0x1800866d4`
- `0x180098b54`
- `0x1800a20ec`
- `0x1800b27e0`
- `0x1800b3128`
- `0x18010a000`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039505`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039505`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800399d2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800399d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800395c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180039610`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003987f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003992e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800395c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180039610`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003987f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003992e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800396a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18003993c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800396a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18003993c`

## string_xrefs

- `0x1800393bf`: `onecore\com\combase\rpcss\olescm\scmif.cxx`
- `0x18003988e`: `onecore\com\combase\rpcss\olescm\scmif.cxx`

## pseudocode

```c
__int64 __fastcall ServerRegisterActivatableClasses(
        void *a1,
        struct CProcess *a2,
        unsigned int *a3,
        char **a4,
        _DWORD *a5)
{
  UINT32 *p_length; // rdi
  unsigned int *v7; // r12
  struct CProcess *v8; // rax
  struct CProcess *v9; // r13
  int ComponentProcessId; // ebx
  __int64 v11; // rdx
  unsigned __int64 v13; // rsi
  unsigned __int64 v14; // rcx
  unsigned int v15; // r15d
  size_t v16; // rbx
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // rcx
  void *v19; // rsp
  void *v20; // rsp
  UINT32 *v21; // rax
  char *v22; // rax
  unsigned int *v23; // rbx
  unsigned int v24; // r15d
  HSTRING i; // rax
  __int64 v26; // r15
  const unsigned __int16 *v27; // rcx
  const WCHAR *v28; // rcx
  unsigned __int64 v29; // rdx
  const WCHAR *v30; // rcx
  unsigned __int64 v31; // rdx
  int v32; // ebx
  char IsEnabled; // al
  struct CToken *v34; // r9
  int v35; // eax
  HSTRING *v36; // rsi
  int v37; // eax
  int v38; // r14d
  void *v39; // rbx
  __int64 v40; // rax
  HSTRING v41; // rax
  HSTRING v42; // r12
  HSTRING v43; // r13
  CServerTableEntry *v44; // r14
  __int128 v45; // xmm0
  unsigned int v46; // r15d
  unsigned int v47; // edi
  __int64 v48; // r14
  const WCHAR *v49; // rcx
  unsigned __int64 v50; // rdx
  int v51; // eax
  __int64 v52; // r10
  unsigned int v53; // esi
  unsigned __int64 v54; // rcx
  const WCHAR *v55; // r10
  void *v56; // r9
  CServerTableEntry *v57; // rsi
  unsigned int v58; // r8d
  unsigned int v59; // r13d
  __int64 v60; // rcx
  CNamedObject *v61; // rcx
  __int64 v62; // [rsp+0h] [rbp-40h] BYREF
  struct _GUID *v63; // [rsp+20h] [rbp-20h]
  char v64[4]; // [rsp+28h] [rbp-18h]
  struct CClassData **v65; // [rsp+30h] [rbp-10h]
  unsigned int *v66; // [rsp+38h] [rbp-8h]
  int v67; // [rsp+40h] [rbp+0h] BYREF
  unsigned int v68; // [rsp+44h] [rbp+4h]
  UINT32 length; // [rsp+48h] [rbp+8h] BYREF
  HSTRING v70; // [rsp+50h] [rbp+10h] BYREF
  HSTRING v71; // [rsp+58h] [rbp+18h] BYREF
  UINT32 *v72; // [rsp+60h] [rbp+20h]
  HSTRING v73[2]; // [rsp+70h] [rbp+30h] BYREF
  HSTRING string; // [rsp+80h] [rbp+40h] BYREF
  struct CProcess *v75; // [rsp+88h] [rbp+48h]
  char *v76; // [rsp+90h] [rbp+50h]
  unsigned int *v77; // [rsp+98h] [rbp+58h]
  struct _GUID v78; // [rsp+A0h] [rbp+60h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp+70h] BYREF
  HSTRING_HEADER v80; // [rsp+C8h] [rbp+88h] BYREF
  HSTRING_HEADER v81; // [rsp+E0h] [rbp+A0h] BYREF
  HSTRING_HEADER v82; // [rsp+F8h] [rbp+B8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+128h]

  p_length = 0;
  v77 = a3;
  v7 = a3;
  if ( !a5 || !a3 || !a4 )
    return 2147942487LL;
  *a5 = 0;
  *a4 = 0;
  v8 = CheckLocalSecurity(a1, a2);
  v75 = v8;
  v9 = v8;
  if ( !v8 )
  {
    ComponentProcessId = -2147024891;
    v11 = 830;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\scmif.cxx",
      (const char *)(unsigned int)ComponentProcessId,
      (int)v63);
    return (unsigned int)ComponentProcessId;
  }
  if ( !*((_QWORD *)v8 + 71) )
  {
    ComponentProcessId = -2147418113;
    v11 = 835;
    goto LABEL_6;
  }
  v78 = GUID_NULL;
  ComponentProcessId = CToken::GetComponentProcessId(*((CToken **)v8 + 3), &v78);
  if ( ComponentProcessId < 0 )
    goto LABEL_108;
  v13 = 8LL * *v7;
  if ( v13 > 0xFFFFFFFF || (v14 = 4LL * (*v7 - 1), v14 > 0xFFFFFFFF) || (v15 = v14 + 8, (unsigned int)v14 >= 0xFFFFFFF8) )
  {
    ComponentProcessId = -2147024362;
    goto LABEL_108;
  }
  v72 = 0;
  if ( !(_DWORD)v13 )
    goto LABEL_22;
  v16 = (unsigned int)v13;
  if ( (unsigned int)v13 > (unsigned __int64)g_ulMaxStackAllocSize
    || (unsigned __int64)(unsigned int)v13 + g_ulAdditionalProbeSize + 8 < (unsigned int)v13
    || !(unsigned int)VerifyStackAvailable() )
  {
    goto LABEL_22;
  }
  v17 = (unsigned int)v13 + 23LL;
  if ( v17 <= (unsigned __int64)(unsigned int)v13 + 8 )
    v17 = 0xFFFFFFFFFFFFFF0LL;
  v18 = v17 & 0xFFFFFFFFFFFFFFF0uLL;
  v19 = alloca(v18);
  v20 = alloca(v18);
  p_length = (UINT32 *)&v67;
  v72 = (UINT32 *)&v67;
  if ( &v62 == (__int64 *)-64LL || (v67 = 1801679955, p_length = &length, (v72 = &length) == 0) )
  {
LABEL_22:
    v16 = (unsigned int)v13;
    if ( (unsigned __int64)(unsigned int)v13 + 8 >= (unsigned int)v13 )
    {
      v21 = (UINT32 *)((__int64 (*)(void))g_pfnAllocate)();
      v72 = v21;
      p_length = v21;
      if ( v21 )
      {
        p_length = v21 + 2;
        *v21 = 1885431112;
        v72 = v21 + 2;
      }
    }
  }
  if ( !p_length )
  {
    ComponentProcessId = -2147024882;
    goto LABEL_108;
  }
  v22 = (char *)HeapAlloc(g_hHeap, 0, v15);
  *a4 = v22;
  if ( !v22 )
  {
    ComponentProcessId = -2147024882;
    goto LABEL_105;
  }
  memset_0(p_length, 0, v16);
  v76 = *a4;
  v23 = (unsigned int *)v76;
  memset_0(v76, 0, v15);
  *v23 = *v7;
  ComponentProcessId = 0;
  v24 = *v7;
  v68 = *v7;
  for ( i = 0; ; i = (HSTRING)(length + 1) )
  {
    length = (unsigned int)i;
    if ( (unsigned int)i >= v24 )
      break;
    string = 0;
    v26 = 6LL * (_QWORD)i;
    v71 = 0;
    v70 = i;
    memset(&hstringHeader, 0, sizeof(hstringHeader));
    v27 = *(const unsigned __int16 **)&v7[12 * (_QWORD)i + 2];
    memset(&v80, 0, sizeof(v80));
    if ( !v27 )
    {
      ComponentProcessId = -2147024809;
      break;
    }
    BreakOnDebuggedActivatableClassId(v27);
    v28 = *(const WCHAR **)&v7[2 * v26 + 2];
    v29 = -1;
    do
      ++v29;
    while ( v28[v29] );
    if ( v29 > 0xFFFFFFFF )
      ComponentProcessId = -2147024362;
    else
      ComponentProcessId = WindowsCreateStringReference(v28, v29, &hstringHeader, &string);
    if ( ComponentProcessId < 0 )
      break;
    v30 = *(const WCHAR **)&v7[2 * v26 + 4];
    if ( v30 )
    {
      v31 = -1;
      do
        ++v31;
      while ( v30[v31] );
      if ( v31 > 0xFFFFFFFF )
      {
        ComponentProcessId = -2147024362;
        break;
      }
      ComponentProcessId = WindowsCreateStringReference(v30, v31, &v80, &v71);
      if ( ComponentProcessId < 0 )
        break;
    }
    v32 = v7[2 * v26 + 12] & 0x40000000;
    v73[0] = 0;
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl);
    v34 = (struct CToken *)*((_QWORD *)v9 + 3);
    v65 = (struct CClassData **)v73;
    *(_DWORD *)v64 = (v32 | 0x20000000u) >> 7;
    v63 = 0;
    if ( IsEnabled )
      v35 = CActivatableClassData::LookupActivatableClassData(
              string,
              v71,
              0,
              v34,
              (unsigned __int64)v63,
              *(unsigned int *)v64,
              v65);
    else
      v35 = LookupActivatableClassDataOld(string, v71, 0, v34, (unsigned __int64)v63, *(unsigned int *)v64, v65);
    ComponentProcessId = v35;
    if ( v35 < 0 )
      break;
    v36 = (HSTRING *)v73[0];
    v37 = CClassData::CertifyServer((CClassData *)v73[0], v9);
    v38 = v37;
    if ( v37 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x3CA,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\scmif.cxx",
        (const char *)(unsigned int)v37,
        (int)v63);
      BreakOnServerCertificationFailureIfRequested();
      ComponentProcessId = -2147467243;
      if ( v38 == -2147024444 )
        ComponentProcessId = -2147024444;
      if ( v36 )
        (*(void (__fastcall **)(HSTRING *, __int64))*v36)(v36, 1);
      break;
    }
    v39 = 0;
    if ( !WindowsIsStringEmpty(v71) )
      v39 = (void *)(*((_QWORD *)v9 + 3) + 156LL);
    v40 = (*((__int64 (__fastcall **)(HSTRING *, void *, struct _GUID *))*v36 + 1))(v36, v39, &v78);
    *(_QWORD *)&p_length[2 * (_QWORD)v70] = v40;
    if ( !v40 )
    {
      if ( v36 )
        (*(void (__fastcall **)(HSTRING *, __int64))*v36)(v36, 1);
      ComponentProcessId = -2147024882;
      break;
    }
    v41 = v36[12];
    v42 = v71;
    v43 = string;
    v63 = &v78;
    LOBYTE(v67) = (*((_DWORD *)v41 + 30) == 1) + 2;
    v73[0] = (HSTRING)gpActivatableClassTable;
    v44 = CWinRTServerTable::Lookup(gpActivatableClassTable, string, v71, v39, &v78);
    if ( v44 || (v44 = CWinRTServerTable::Create((CWinRTServerTable *)v73[0], v43, v42, v39, &v78)) != 0 )
    {
      v7 = v77;
      v9 = v75;
      v45 = *(_OWORD *)&v77[2 * v26 + 8];
      v66 = (unsigned int *)&v76[4 * (_QWORD)v70 + 4];
      LODWORD(v65) = v77[2 * v26 + 13];
      *(_OWORD *)v73 = v45;
      ComponentProcessId = CServerTableEntry::RegisterServer(
                             v44,
                             v75,
                             (struct _GUID *)v73,
                             v36,
                             0,
                             v67,
                             (unsigned int)v65,
                             v66);
      (*(void (__fastcall **)(CServerTableEntry *))(*(_QWORD *)v44 + 8LL))(v44);
    }
    else
    {
      v9 = v75;
      ComponentProcessId = -2147024882;
      v7 = v77;
    }
    if ( v36 )
      (*(void (__fastcall **)(HSTRING *, __int64))*v36)(v36, 1);
    if ( ComponentProcessId )
      break;
    v24 = v68;
  }
  v46 = 0;
  if ( !v68 )
  {
    if ( !ComponentProcessId )
      goto LABEL_105;
LABEL_104:
    memset_0(v76 + 4, 0, 4LL * *(unsigned int *)v76);
    goto LABEL_105;
  }
  v47 = v68;
  v48 = 0;
  do
  {
    v70 = 0;
    v73[0] = 0;
    memset(&v81, 0, sizeof(v81));
    v49 = *(const WCHAR **)&v7[12 * v48 + 2];
    memset(&v82, 0, sizeof(v82));
    if ( !v49 )
      goto LABEL_89;
    v50 = -1;
    do
      ++v50;
    while ( v49[v50] );
    v51 = v50 > 0xFFFFFFFF ? -2147024362 : WindowsCreateStringReference(v49, v50, &v81, &v70);
    if ( v51 < 0 )
      goto LABEL_89;
    v52 = *(_QWORD *)&v7[12 * v48 + 4];
    v53 = 0;
    if ( !v52 )
      goto LABEL_112;
    length = 0;
    v54 = -1;
    do
      ++v54;
    while ( *(_WORD *)(v52 + 2 * v54) );
    if ( (int)ULongLongToULong(v54, &length) >= 0 && WindowsCreateStringReference(v55, length, &v82, v73) >= 0 )
    {
LABEL_112:
      if ( WindowsIsStringEmpty(v73[0]) )
        v56 = 0;
      else
        v56 = (void *)(*((_QWORD *)v9 + 3) + 156LL);
      v57 = CWinRTServerTable::Lookup(gpActivatableClassTable, v70, v73[0], v56, &v78);
      v58 = *(_DWORD *)&v76[4 * v48 + 4];
      if ( ComponentProcessId )
      {
        if ( v58 )
        {
          if ( !v57 )
            goto LABEL_89;
          CServerTableEntry::RevokeServer(v57, v9, v58, 0);
          goto LABEL_88;
        }
      }
      else
      {
        CServerTableEntry::UnsuspendServer(v57, v58);
      }
      if ( !v57 )
      {
LABEL_89:
        v53 = 0;
        goto LABEL_90;
      }
LABEL_88:
      (*(void (__fastcall **)(CServerTableEntry *))(*(_QWORD *)v57 + 8LL))(v57);
      goto LABEL_89;
    }
LABEL_90:
    ++v46;
    ++v48;
  }
  while ( v46 < v47 );
  p_length = v72;
  v59 = v68;
  if ( ComponentProcessId )
  {
    do
    {
      v61 = *(CNamedObject **)&p_length[2 * v53];
      if ( v61 )
      {
        CNamedObject::Release(v61);
        *(_QWORD *)&p_length[2 * v53] = 0;
      }
      ++v53;
    }
    while ( v53 < v59 );
    v9 = v75;
    goto LABEL_104;
  }
  do
  {
    v60 = *(_QWORD *)&p_length[2 * v53];
    if ( v60 )
    {
      SetEvent(*(HANDLE *)(v60 + 24));
      CNamedObject::Release(*(CNamedObject **)&p_length[2 * v53]);
      *(_QWORD *)&p_length[2 * v53] = 0;
    }
    ++v53;
  }
  while ( v53 < v59 );
  v9 = v75;
LABEL_105:
  if ( *(p_length - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
LABEL_108:
  ReleaseProcess(v9);
  return (unsigned int)ComponentProcessId;
}

```

## disassembly

```asm
0x180039340  push    rbp
0x180039342  push    rbx
0x180039343  push    rsi
0x180039344  push    rdi
0x180039345  push    r12
0x180039347  push    r13
0x180039349  push    r14
0x18003934b  push    r15
0x18003934d  sub     rsp, 128h
0x180039354  lea     rbp, [rsp+40h]
0x180039359  mov     rax, cs:__security_cookie
0x180039360  xor     rax, rbp
0x180039363  mov     [rbp+120h+var_50], rax
0x18003936a  mov     rax, [rbp+120h+arg_20]
0x180039371  xor     edi, edi
0x180039373  mov     [rbp+120h+var_C8], r8
0x180039377  mov     r14, r9
0x18003937a  mov     r12, r8
0x18003937d  test    rax, rax
0x180039380  jz      loc_180039A77
0x180039386  test    r8, r8
0x180039389  jz      loc_180039A77
0x18003938f  test    r9, r9
0x180039392  jz      loc_180039A77
0x180039398  mov     [rax], edi
0x18003939a  mov     [r9], rdi
0x18003939d  call    ?CheckLocalSecurity@@YAPEAVCProcess@@PEAX0@Z; CheckLocalSecurity(void *,void *)
0x1800393a2  mov     [rbp+120h+var_D8], rax
0x1800393a6  mov     r13, rax
0x1800393a9  test    rax, rax
0x1800393ac  jnz     short loc_1800393D5
0x1800393ae  mov     ebx, 80070005h
0x1800393b3  mov     edx, 33Eh; void *
0x1800393b8  mov     rcx, [rbp+128h]; this
0x1800393bf  lea     r8, aOnecoreComComb_29; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x1800393c6  mov     r9d, ebx; char *
0x1800393c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800393ce  mov     eax, ebx
0x1800393d0  jmp     loc_180039A7C
0x1800393d5  cmp     [rax+238h], rdi
0x1800393dc  jnz     short loc_1800393EA
0x1800393de  mov     ebx, 8000FFFFh
0x1800393e3  mov     edx, 343h
0x1800393e8  jmp     short loc_1800393B8
0x1800393ea  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800393f1  lea     rdx, [rbp+120h+var_C0]; struct _GUID *
0x1800393f5  movdqu  xmmword ptr [rbp+120h+var_C0.Data1], xmm0
0x1800393fa  mov     rcx, [rax+18h]; this
0x1800393fe  call    ?GetComponentProcessId@CToken@@QEAAJPEAU_GUID@@@Z; CToken::GetComponentProcessId(_GUID *)
0x180039403  mov     ebx, eax
0x180039405  test    eax, eax
0x180039407  js      loc_180039A6A
0x18003940d  mov     eax, [r12]
0x180039411  mov     edx, 0FFFFFFFFh
0x180039416  mov     esi, eax
0x180039418  shl     rsi, 3
0x18003941c  cmp     rsi, rdx
0x18003941f  ja      loc_180039A65
0x180039425  lea     ecx, [rax-1]
0x180039428  shl     rcx, 2
0x18003942c  cmp     rcx, rdx
0x18003942f  ja      loc_180039A65
0x180039435  lea     r15d, [rcx+8]
0x180039439  cmp     r15d, 8
0x18003943d  jb      loc_180039A65
0x180039443  mov     [rbp+120h+var_100], rdi
0x180039447  test    esi, esi
0x180039449  jz      short loc_1800394B6
0x18003944b  mov     ebx, esi
0x18003944d  cmp     rbx, cs:g_ulMaxStackAllocSize
0x180039454  ja      short loc_1800394B6
0x180039456  mov     rcx, cs:g_ulAdditionalProbeSize
0x18003945d  add     rcx, 8
0x180039461  add     rcx, rbx
0x180039464  cmp     rcx, rbx
0x180039467  jb      short loc_1800394B6
0x180039469  call    VerifyStackAvailable
0x18003946e  test    eax, eax
0x180039470  jz      short loc_1800394B6
0x180039472  lea     rax, [rbx+8]
0x180039476  lea     rcx, [rax+0Fh]
0x18003947a  cmp     rcx, rax
0x18003947d  ja      short loc_180039489
0x18003947f  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180039489  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18003948d  mov     rax, rcx
0x180039490  call    _alloca_probe
0x180039495  sub     rsp, rcx
0x180039498  lea     rdi, [rsp+160h+var_120]
0x18003949d  mov     [rbp+120h+var_100], rdi
0x1800394a1  test    rdi, rdi
0x1800394a4  jz      short loc_1800394B6
0x1800394a6  mov     dword ptr [rdi], 6B637453h
0x1800394ac  add     rdi, 8
0x1800394b0  mov     [rbp+120h+var_100], rdi
0x1800394b4  jnz     short loc_1800394E7
0x1800394b6  mov     ebx, esi
0x1800394b8  lea     rcx, [rbx+8]
0x1800394bc  cmp     rcx, rbx
0x1800394bf  jb      short loc_1800394E7
0x1800394c1  mov     rax, cs:g_pfnAllocate
0x1800394c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800394cd  mov     [rbp+120h+var_100], rax
0x1800394d1  mov     rdi, rax
0x1800394d4  test    rax, rax
0x1800394d7  jz      short loc_1800394E7
0x1800394d9  add     rdi, 8
0x1800394dd  mov     dword ptr [rax], 70616548h
0x1800394e3  mov     [rbp+120h+var_100], rdi
0x1800394e7  test    rdi, rdi
0x1800394ea  jnz     short loc_1800394F6
0x1800394ec  mov     ebx, 8007000Eh
0x1800394f1  jmp     loc_180039A6A
0x1800394f6  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800394fd  xor     edx, edx; dwFlags
0x1800394ff  mov     r8d, r15d; dwBytes
0x180039502  mov     esi, r15d
0x180039505  call    cs:__imp_HeapAlloc
0x18003950b  mov     [r14], rax
0x18003950e  test    rax, rax
0x180039511  jnz     short loc_18003951D
0x180039513  mov     ebx, 8007000Eh
0x180039518  jmp     loc_180039A4B
0x18003951d  mov     r8, rbx; Size
0x180039520  xor     edx, edx; Val
0x180039522  mov     rcx, rdi; void *
0x180039525  call    memset_0
0x18003952a  mov     rbx, [r14]
0x18003952d  mov     r8, rsi; Size
0x180039530  mov     rcx, rbx; void *
0x180039533  mov     [rbp+120h+var_D0], rbx
0x180039537  xor     edx, edx; Val
0x180039539  call    memset_0
0x18003953e  mov     eax, [r12]
0x180039542  xor     esi, esi
0x180039544  mov     [rbx], eax
0x180039546  mov     ebx, esi
0x180039548  mov     r15d, [r12]
0x18003954c  mov     [rbp+120h+var_11C], r15d
0x180039550  mov     eax, esi
0x180039552  mov     [rbp+120h+length], eax
0x180039555  cmp     eax, r15d
0x180039558  jnb     loc_18003980A
0x18003955e  xor     ecx, ecx
0x180039560  mov     [rbp+120h+string], rsi
0x180039564  lea     r15, [rax+rax*2]
0x180039568  mov     qword ptr [rbp+120h+hstringHeader.Reserved+10h], rcx
0x18003956f  add     r15, r15
0x180039572  mov     qword ptr [rbp+120h+var_98.Reserved+10h], rcx
0x180039579  xorps   xmm0, xmm0
0x18003957c  mov     [rbp+120h+var_108], rsi
0x180039580  xorps   xmm1, xmm1
0x180039583  mov     [rbp+120h+var_110], rax
0x180039587  movups  xmmword ptr [rbp+120h+hstringHeader.Reserved], xmm0
0x18003958b  mov     rcx, [r12+r15*8+8]; unsigned __int16 *
0x180039590  movups  xmmword ptr [rbp+120h+var_98.Reserved], xmm1
0x180039597  test    rcx, rcx
0x18003959a  jz      loc_1800398D8
0x1800395a0  call    ?BreakOnDebuggedActivatableClassId@@YAXPEBG@Z; BreakOnDebuggedActivatableClassId(ushort const *)
0x1800395a5  mov     rcx, [r12+r15*8+8]; sourceString
0x1800395aa  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800395ae  inc     rdx; length
0x1800395b1  cmp     [rcx+rdx*2], si
0x1800395b5  jnz     short loc_1800395AE
0x1800395b7  mov     eax, 0FFFFFFFFh
0x1800395bc  cmp     rdx, rax
0x1800395bf  ja      short loc_1800395D8
0x1800395c1  lea     r9, [rbp+120h+string]; string
0x1800395c5  lea     r8, [rbp+120h+hstringHeader]; hstringHeader
0x1800395c9  call    cs:__imp_WindowsCreateStringReference
0x1800395cf  mov     ebx, eax
0x1800395d1  mov     eax, 0FFFFFFFFh
0x1800395d6  jmp     short loc_1800395DD
0x1800395d8  mov     ebx, 80070216h
0x1800395dd  test    ebx, ebx
0x1800395df  js      loc_18003980A
0x1800395e5  mov     rcx, [r12+r15*8+10h]; sourceString
0x1800395ea  test    rcx, rcx
0x1800395ed  jz      short loc_180039620
0x1800395ef  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800395f3  inc     rdx; length
0x1800395f6  cmp     [rcx+rdx*2], si
0x1800395fa  jnz     short loc_1800395F3
0x1800395fc  cmp     rdx, rax
0x1800395ff  ja      loc_1800397E4
0x180039605  lea     r9, [rbp+120h+var_108]; string
0x180039609  lea     r8, [rbp+120h+var_98]; hstringHeader
0x180039610  call    cs:__imp_WindowsCreateStringReference
0x180039616  mov     ebx, eax
0x180039618  test    eax, eax
0x18003961a  js      loc_18003980A
0x180039620  mov     ebx, [r12+r15*8+30h]
0x180039625  and     ebx, 40000000h
0x18003962b  mov     [rbp+120h+var_F0], rsi
0x18003962f  bts     ebx, 1Dh
0x180039633  shr     ebx, 7
0x180039636  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x18003963d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x180039642  mov     r9, [r13+18h]; struct CToken *
0x180039646  xor     r8d, r8d; struct IComClassInfo *
0x180039649  mov     rdx, [rbp+120h+var_108]; HSTRING
0x18003964d  test    al, al
0x18003964f  mov     rcx, [rbp+120h+string]; HSTRING
0x180039653  lea     rax, [rbp+120h+var_F0]
0x180039657  mov     [rsp+160h+var_130], rax; struct CClassData **
0x18003965c  mov     dword ptr [rsp+160h+var_138], ebx; unsigned int
0x180039660  mov     [rsp+160h+var_140], rsi; int
0x180039665  jz      short loc_18003966E
0x180039667  call    ?LookupActivatableClassData@CActivatableClassData@@SAJPEAUHSTRING__@@0PEAUIComClassInfo@@PEAVCToken@@_KKPEAPEAVCClassData@@@Z; CActivatableClassData::LookupActivatableClassData(HSTRING__ *,HSTRING__ *,IComClassInfo *,CToken *,unsigned __int64,ulong,CClassData * *)
0x18003966c  jmp     short loc_180039673
0x18003966e  call    ?LookupActivatableClassDataOld@@YAJPEAUHSTRING__@@0PEAUIComClassInfo@@PEAVCToken@@_KKPEAPEAVCClassData@@@Z; LookupActivatableClassDataOld(HSTRING__ *,HSTRING__ *,IComClassInfo *,CToken *,unsigned __int64,ulong,CClassData * *)
0x180039673  mov     ebx, eax
0x180039675  test    eax, eax
0x180039677  js      loc_18003980A
0x18003967d  mov     rsi, [rbp+120h+var_F0]
0x180039681  mov     rdx, r13; struct CProcess *
0x180039684  mov     rcx, rsi; this
0x180039687  call    ?CertifyServer@CClassData@@QEAAJPEAVCProcess@@@Z; CClassData::CertifyServer(CProcess *)
0x18003968c  mov     r14d, eax
0x18003968f  test    eax, eax
0x180039691  js      loc_180039887
0x180039697  mov     rcx, [rbp+120h+var_108]; string
0x18003969b  xor     r14d, r14d
0x18003969e  mov     ebx, r14d
0x1800396a1  call    cs:__imp_WindowsIsStringEmpty
0x1800396a7  test    eax, eax
0x1800396a9  jnz     short loc_1800396B6
0x1800396ab  mov     rbx, [r13+18h]
0x1800396af  add     rbx, 9Ch
0x1800396b6  mov     rax, [rsi]
0x1800396b9  lea     r8, [rbp+120h+var_C0]
0x1800396bd  mov     rdx, rbx
0x1800396c0  mov     rcx, rsi
0x1800396c3  mov     rax, [rax+8]
0x1800396c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800396cc  mov     rcx, [rbp+120h+var_110]
0x1800396d0  mov     [rdi+rcx*8], rax
0x1800396d4  test    rax, rax
0x1800396d7  jz      loc_1800397EB
0x1800396dd  mov     rax, [rsi+60h]
0x1800396e1  lea     rcx, [rbp+120h+var_C0]
0x1800396e5  mov     r12, [rbp+120h+var_108]
0x1800396e9  mov     r9, rbx; void *
0x1800396ec  mov     r13, [rbp+120h+string]
0x1800396f0  mov     r8, r12; HSTRING
0x1800396f3  mov     [rsp+160h+var_140], rcx; struct _GUID *
0x1800396f8  mov     rdx, r13; HSTRING
0x1800396fb  cmp     dword ptr [rax+78h], 1
0x1800396ff  setz    al
0x180039702  add     al, 2
0x180039704  mov     byte ptr [rbp+120h+var_120], al
0x180039707  mov     rax, cs:?gpActivatableClassTable@@3PEAVCWinRTServerTable@@EA; CWinRTServerTable * gpActivatableClassTable
0x18003970e  mov     rcx, rax; this
0x180039711  mov     [rbp+120h+var_F0], rax
0x180039715  call    ?Lookup@CWinRTServerTable@@QEAAPEAVCWinRTServerTableEntry@@PEAUHSTRING__@@0PEAXAEBU_GUID@@@Z; CWinRTServerTable::Lookup(HSTRING__ *,HSTRING__ *,void *,_GUID const &)
0x18003971a  mov     r14, rax
0x18003971d  test    rax, rax
0x180039720  jnz     short loc_180039754
0x180039722  mov     rcx, [rbp+120h+var_F0]; this
0x180039726  lea     rax, [rbp+120h+var_C0]
0x18003972a  mov     r9, rbx; void *
0x18003972d  mov     [rsp+160h+var_140], rax; struct _GUID *
0x180039732  mov     r8, r12; HSTRING
0x180039735  mov     rdx, r13; HSTRING
0x180039738  call    ?Create@CWinRTServerTable@@QEAAPEAVCWinRTServerTableEntry@@PEAUHSTRING__@@0PEAXAEBU_GUID@@@Z; CWinRTServerTable::Create(HSTRING__ *,HSTRING__ *,void *,_GUID const &)
0x18003973d  mov     r14, rax
0x180039740  test    rax, rax
0x180039743  jnz     short loc_180039754
0x180039745  mov     r13, [rbp+120h+var_D8]
0x180039749  mov     ebx, 8007000Eh
0x18003974e  mov     r12, [rbp+120h+var_C8]
0x180039752  jmp     short loc_1800397B8
0x180039754  mov     r12, [rbp+120h+var_C8]
0x180039758  lea     r8, [rbp+120h+var_F0]; struct _GUID
0x18003975c  mov     rcx, [rbp+120h+var_D0]
0x180039760  mov     r9, rsi; struct CClassData *
0x180039763  mov     rax, [rbp+120h+var_110]
0x180039767  add     rcx, 4
0x18003976b  mov     r13, [rbp+120h+var_D8]
0x18003976f  movups  xmm0, xmmword ptr [r12+r15*8+20h]
0x180039775  mov     rdx, r13; struct CProcess *
0x180039778  lea     rax, [rcx+rax*4]
0x18003977c  mov     rcx, r14; this
0x18003977f  mov     [rsp+160h+var_128], rax; unsigned int *
0x180039784  mov     eax, [r12+r15*8+34h]
0x180039789  mov     dword ptr [rsp+160h+var_130], eax; unsigned int
0x18003978d  mov     al, byte ptr [rbp+120h+var_120]
0x180039790  mov     [rsp+160h+var_138], al; char
0x180039794  mov     [rsp+160h+var_140], 0; struct CAppidData *
0x18003979d  movdqu  xmmword ptr [rbp+120h+var_F0], xmm0
0x1800397a2  call    ?RegisterServer@CServerTableEntry@@QEAAJPEAVCProcess@@U_GUID@@PEAVCClassData@@PEAVCAppidData@@EKPEAK@Z; CServerTableEntry::RegisterServer(CProcess *,_GUID,CClassData *,CAppidData *,uchar,ulong,ulong *)
0x1800397a7  mov     ebx, eax
0x1800397a9  mov     rcx, r14
0x1800397ac  mov     rax, [r14]
0x1800397af  mov     rax, [rax+8]
0x1800397b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800397b8  test    rsi, rsi
0x1800397bb  jz      short loc_1800397D0
0x1800397bd  mov     rax, [rsi]
0x1800397c0  mov     edx, 1
  ... truncated ...
```
