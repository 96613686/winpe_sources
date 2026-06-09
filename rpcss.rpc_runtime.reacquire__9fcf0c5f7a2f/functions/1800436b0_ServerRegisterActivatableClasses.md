# ServerRegisterActivatableClasses

- ea: `0x1800436b0`
- end: `0x180043e40`
- name: `ServerRegisterActivatableClasses`
- size: `1936`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800065a4`
- `0x18001627c`
- `0x1800189d0`
- `0x18001ee90`
- `0x1800210f8`
- `0x180030ed0`
- `0x18004335c`
- `0x1800436b0`
- `0x180043e48`
- `0x180044940`
- `0x180044d70`
- `0x180044f2c`
- `0x180045010`
- `0x180045084`
- `0x1800465b0`
- `0x18004a3f4`
- `0x18005bb8c`
- `0x18008b6b0`
- `0x18009e160`
- `0x1800a7580`
- `0x1800b7ac0`
- `0x1800b8428`
- `0x180112d00`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180043875`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180043875`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180043d6c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180043d6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004393f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004398c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180043c07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180043cbc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004393f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004398c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180043c07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180043cbc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180043a23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180043cd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180043a23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180043cd0`

## string_xrefs

- `0x18004372f`: `onecore\com\combase\rpcss\olescm\scmif.cxx`
- `0x180043c1c`: `onecore\com\combase\rpcss\olescm\scmif.cxx`

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
  unsigned __int64 v19; // rcx
  void *v20; // rsp
  void *v21; // rsp
  UINT32 *v22; // rax
  char *v23; // rax
  unsigned int *v24; // rbx
  unsigned int v25; // r15d
  HSTRING i; // rax
  __int64 v27; // r15
  const unsigned __int16 *v28; // rcx
  const WCHAR *v29; // rcx
  unsigned __int64 v30; // rdx
  const WCHAR *v31; // rcx
  unsigned __int64 v32; // rdx
  int v33; // ebx
  char IsEnabled; // al
  struct CToken *v35; // r9
  int v36; // eax
  HSTRING *v37; // rsi
  int v38; // eax
  int v39; // r14d
  void *v40; // rbx
  __int64 v41; // rax
  HSTRING v42; // rax
  HSTRING v43; // r12
  HSTRING v44; // r13
  CServerTableEntry *v45; // r14
  __int128 v46; // xmm0
  unsigned int v47; // r15d
  unsigned int v48; // edi
  __int64 v49; // r14
  const WCHAR *v50; // rcx
  unsigned __int64 v51; // rdx
  int v52; // eax
  __int64 v53; // r10
  unsigned int v54; // esi
  unsigned __int64 v55; // rcx
  const WCHAR *v56; // r10
  void *v57; // r9
  CServerTableEntry *v58; // rsi
  unsigned int v59; // r8d
  unsigned int v60; // r13d
  __int64 v61; // rcx
  CNamedObject *v62; // rcx
  __int64 v63; // [rsp+0h] [rbp-40h] BYREF
  struct _GUID *v64; // [rsp+20h] [rbp-20h]
  char v65[4]; // [rsp+28h] [rbp-18h]
  struct CClassData **v66; // [rsp+30h] [rbp-10h]
  unsigned int *v67; // [rsp+38h] [rbp-8h]
  int v68; // [rsp+40h] [rbp+0h] BYREF
  unsigned int v69; // [rsp+44h] [rbp+4h]
  UINT32 length; // [rsp+48h] [rbp+8h] BYREF
  HSTRING v71; // [rsp+50h] [rbp+10h] BYREF
  HSTRING v72; // [rsp+58h] [rbp+18h] BYREF
  UINT32 *v73; // [rsp+60h] [rbp+20h]
  HSTRING v74[2]; // [rsp+70h] [rbp+30h] BYREF
  HSTRING string; // [rsp+80h] [rbp+40h] BYREF
  struct CProcess *v76; // [rsp+88h] [rbp+48h]
  char *v77; // [rsp+90h] [rbp+50h]
  unsigned int *v78; // [rsp+98h] [rbp+58h]
  struct _GUID v79; // [rsp+A0h] [rbp+60h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp+70h] BYREF
  HSTRING_HEADER v81; // [rsp+C8h] [rbp+88h] BYREF
  HSTRING_HEADER v82; // [rsp+E0h] [rbp+A0h] BYREF
  HSTRING_HEADER v83; // [rsp+F8h] [rbp+B8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+128h]

  p_length = 0;
  v78 = a3;
  v7 = a3;
  if ( !a5 || !a3 || !a4 )
    return 2147942487LL;
  *a5 = 0;
  *a4 = 0;
  v8 = CheckLocalSecurity(a1, a2);
  v76 = v8;
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
      (int)v64);
    return (unsigned int)ComponentProcessId;
  }
  if ( !*((_QWORD *)v8 + 71) )
  {
    ComponentProcessId = -2147418113;
    v11 = 835;
    goto LABEL_6;
  }
  v79 = GUID_NULL;
  ComponentProcessId = CToken::GetComponentProcessId(*((CToken **)v8 + 3), &v79);
  if ( ComponentProcessId < 0 )
    goto LABEL_108;
  v13 = 8LL * *v7;
  if ( v13 > 0xFFFFFFFF || (v14 = 4LL * (*v7 - 1), v14 > 0xFFFFFFFF) || (v15 = v14 + 8, (unsigned int)v14 >= 0xFFFFFFF8) )
  {
    ComponentProcessId = -2147024362;
    goto LABEL_108;
  }
  v73 = 0;
  if ( !(_DWORD)v13 )
    goto LABEL_22;
  v16 = (unsigned int)v13;
  if ( (unsigned int)v13 > (unsigned __int64)g_ulMaxStackAllocSize )
    goto LABEL_22;
  v17 = (unsigned int)v13 + g_ulAdditionalProbeSize + 8;
  if ( v17 < (unsigned int)v13 || !(unsigned int)VerifyStackAvailable(v17, 0xFFFFFFFFLL) )
    goto LABEL_22;
  v18 = (unsigned int)v13 + 23LL;
  if ( v18 <= (unsigned __int64)(unsigned int)v13 + 8 )
    v18 = 0xFFFFFFFFFFFFFF0LL;
  v19 = v18 & 0xFFFFFFFFFFFFFFF0uLL;
  v20 = alloca(v19);
  v21 = alloca(v19);
  p_length = (UINT32 *)&v68;
  v73 = (UINT32 *)&v68;
  if ( &v63 == (__int64 *)-64LL || (v68 = 1801679955, p_length = &length, (v73 = &length) == 0) )
  {
LABEL_22:
    v16 = (unsigned int)v13;
    if ( (unsigned __int64)(unsigned int)v13 + 8 >= (unsigned int)v13 )
    {
      v22 = (UINT32 *)((__int64 (*)(void))g_pfnAllocate)();
      v73 = v22;
      p_length = v22;
      if ( v22 )
      {
        p_length = v22 + 2;
        *v22 = 1885431112;
        v73 = v22 + 2;
      }
    }
  }
  if ( !p_length )
  {
    ComponentProcessId = -2147024882;
    goto LABEL_108;
  }
  v23 = (char *)HeapAlloc(g_hHeap, 0, v15);
  *a4 = v23;
  if ( !v23 )
  {
    ComponentProcessId = -2147024882;
    goto LABEL_105;
  }
  memset_0(p_length, 0, v16);
  v77 = *a4;
  v24 = (unsigned int *)v77;
  memset_0(v77, 0, v15);
  *v24 = *v7;
  ComponentProcessId = 0;
  v25 = *v7;
  v69 = *v7;
  for ( i = 0; ; i = (HSTRING)(length + 1) )
  {
    length = (unsigned int)i;
    if ( (unsigned int)i >= v25 )
      break;
    string = 0;
    v27 = 6LL * (_QWORD)i;
    v72 = 0;
    v71 = i;
    memset(&hstringHeader, 0, sizeof(hstringHeader));
    v28 = *(const unsigned __int16 **)&v7[12 * (_QWORD)i + 2];
    memset(&v81, 0, sizeof(v81));
    if ( !v28 )
    {
      ComponentProcessId = -2147024809;
      break;
    }
    BreakOnDebuggedActivatableClassId(v28);
    v29 = *(const WCHAR **)&v7[2 * v27 + 2];
    v30 = -1;
    do
      ++v30;
    while ( v29[v30] );
    if ( v30 > 0xFFFFFFFF )
      ComponentProcessId = -2147024362;
    else
      ComponentProcessId = WindowsCreateStringReference(v29, v30, &hstringHeader, &string);
    if ( ComponentProcessId < 0 )
      break;
    v31 = *(const WCHAR **)&v7[2 * v27 + 4];
    if ( v31 )
    {
      v32 = -1;
      do
        ++v32;
      while ( v31[v32] );
      if ( v32 > 0xFFFFFFFF )
      {
        ComponentProcessId = -2147024362;
        break;
      }
      ComponentProcessId = WindowsCreateStringReference(v31, v32, &v81, &v72);
      if ( ComponentProcessId < 0 )
        break;
    }
    v33 = v7[2 * v27 + 12] & 0x40000000;
    v74[0] = 0;
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl);
    v35 = (struct CToken *)*((_QWORD *)v9 + 3);
    v66 = (struct CClassData **)v74;
    *(_DWORD *)v65 = (v33 | 0x20000000u) >> 7;
    v64 = 0;
    if ( IsEnabled )
      v36 = CActivatableClassData::LookupActivatableClassData(
              string,
              v72,
              0,
              v35,
              (unsigned __int64)v64,
              *(unsigned int *)v65,
              v66);
    else
      v36 = LookupActivatableClassDataOld(string, v72, 0, v35, (unsigned __int64)v64, *(unsigned int *)v65, v66);
    ComponentProcessId = v36;
    if ( v36 < 0 )
      break;
    v37 = (HSTRING *)v74[0];
    v38 = CClassData::CertifyServer((CClassData *)v74[0], v9);
    v39 = v38;
    if ( v38 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x3CA,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\scmif.cxx",
        (const char *)(unsigned int)v38,
        (int)v64);
      BreakOnServerCertificationFailureIfRequested();
      ComponentProcessId = -2147467243;
      if ( v39 == -2147024444 )
        ComponentProcessId = -2147024444;
      if ( v37 )
        (*(void (__fastcall **)(HSTRING *, __int64))*v37)(v37, 1);
      break;
    }
    v40 = 0;
    if ( !WindowsIsStringEmpty(v72) )
      v40 = (void *)(*((_QWORD *)v9 + 3) + 156LL);
    v41 = (*((__int64 (__fastcall **)(HSTRING *, void *, struct _GUID *))*v37 + 1))(v37, v40, &v79);
    *(_QWORD *)&p_length[2 * (_QWORD)v71] = v41;
    if ( !v41 )
    {
      if ( v37 )
        (*(void (__fastcall **)(HSTRING *, __int64))*v37)(v37, 1);
      ComponentProcessId = -2147024882;
      break;
    }
    v42 = v37[12];
    v43 = v72;
    v44 = string;
    v64 = &v79;
    LOBYTE(v68) = (*((_DWORD *)v42 + 30) == 1) + 2;
    v74[0] = (HSTRING)gpActivatableClassTable;
    v45 = CWinRTServerTable::Lookup(gpActivatableClassTable, string, v72, v40, &v79);
    if ( v45 || (v45 = CWinRTServerTable::Create((CWinRTServerTable *)v74[0], v44, v43, v40, &v79)) != 0 )
    {
      v7 = v78;
      v9 = v76;
      v46 = *(_OWORD *)&v78[2 * v27 + 8];
      v67 = (unsigned int *)&v77[4 * (_QWORD)v71 + 4];
      LODWORD(v66) = v78[2 * v27 + 13];
      *(_OWORD *)v74 = v46;
      ComponentProcessId = CServerTableEntry::RegisterServer(
                             v45,
                             v76,
                             (struct _GUID *)v74,
                             v37,
                             0,
                             v68,
                             (unsigned int)v66,
                             v67);
      (*(void (__fastcall **)(CServerTableEntry *))(*(_QWORD *)v45 + 8LL))(v45);
    }
    else
    {
      v9 = v76;
      ComponentProcessId = -2147024882;
      v7 = v78;
    }
    if ( v37 )
      (*(void (__fastcall **)(HSTRING *, __int64))*v37)(v37, 1);
    if ( ComponentProcessId )
      break;
    v25 = v69;
  }
  v47 = 0;
  if ( !v69 )
  {
    if ( !ComponentProcessId )
      goto LABEL_105;
LABEL_104:
    memset_0(v77 + 4, 0, 4LL * *(unsigned int *)v77);
    goto LABEL_105;
  }
  v48 = v69;
  v49 = 0;
  do
  {
    v71 = 0;
    v74[0] = 0;
    memset(&v82, 0, sizeof(v82));
    v50 = *(const WCHAR **)&v7[12 * v49 + 2];
    memset(&v83, 0, sizeof(v83));
    if ( !v50 )
      goto LABEL_89;
    v51 = -1;
    do
      ++v51;
    while ( v50[v51] );
    v52 = v51 > 0xFFFFFFFF ? -2147024362 : WindowsCreateStringReference(v50, v51, &v82, &v71);
    if ( v52 < 0 )
      goto LABEL_89;
    v53 = *(_QWORD *)&v7[12 * v49 + 4];
    v54 = 0;
    if ( !v53 )
      goto LABEL_112;
    length = 0;
    v55 = -1;
    do
      ++v55;
    while ( *(_WORD *)(v53 + 2 * v55) );
    if ( (int)ULongLongToULong(v55, &length) >= 0 && WindowsCreateStringReference(v56, length, &v83, v74) >= 0 )
    {
LABEL_112:
      if ( WindowsIsStringEmpty(v74[0]) )
        v57 = 0;
      else
        v57 = (void *)(*((_QWORD *)v9 + 3) + 156LL);
      v58 = CWinRTServerTable::Lookup(gpActivatableClassTable, v71, v74[0], v57, &v79);
      v59 = *(_DWORD *)&v77[4 * v49 + 4];
      if ( ComponentProcessId )
      {
        if ( v59 )
        {
          if ( !v58 )
            goto LABEL_89;
          CServerTableEntry::RevokeServer(v58, v9, v59, 0);
          goto LABEL_88;
        }
      }
      else
      {
        CServerTableEntry::UnsuspendServer(v58, v59);
      }
      if ( !v58 )
      {
LABEL_89:
        v54 = 0;
        goto LABEL_90;
      }
LABEL_88:
      (*(void (__fastcall **)(CServerTableEntry *))(*(_QWORD *)v58 + 8LL))(v58);
      goto LABEL_89;
    }
LABEL_90:
    ++v47;
    ++v49;
  }
  while ( v47 < v48 );
  p_length = v73;
  v60 = v69;
  if ( ComponentProcessId )
  {
    do
    {
      v62 = *(CNamedObject **)&p_length[2 * v54];
      if ( v62 )
      {
        CNamedObject::Release(v62);
        *(_QWORD *)&p_length[2 * v54] = 0;
      }
      ++v54;
    }
    while ( v54 < v60 );
    v9 = v76;
    goto LABEL_104;
  }
  do
  {
    v61 = *(_QWORD *)&p_length[2 * v54];
    if ( v61 )
    {
      SetEvent(*(HANDLE *)(v61 + 24));
      CNamedObject::Release(*(CNamedObject **)&p_length[2 * v54]);
      *(_QWORD *)&p_length[2 * v54] = 0;
    }
    ++v54;
  }
  while ( v54 < v60 );
  v9 = v76;
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
0x1800436b0  push    rbp
0x1800436b2  push    rbx
0x1800436b3  push    rsi
0x1800436b4  push    rdi
0x1800436b5  push    r12
0x1800436b7  push    r13
0x1800436b9  push    r14
0x1800436bb  push    r15
0x1800436bd  sub     rsp, 128h
0x1800436c4  lea     rbp, [rsp+40h]
0x1800436c9  mov     rax, cs:__security_cookie
0x1800436d0  xor     rax, rbp
0x1800436d3  mov     [rbp+120h+var_50], rax
0x1800436da  mov     rax, [rbp+120h+arg_20]
0x1800436e1  xor     edi, edi
0x1800436e3  mov     [rbp+120h+var_C8], r8
0x1800436e7  mov     r14, r9
0x1800436ea  mov     r12, r8
0x1800436ed  test    rax, rax
0x1800436f0  jz      loc_180043E17
0x1800436f6  test    r8, r8
0x1800436f9  jz      loc_180043E17
0x1800436ff  test    r9, r9
0x180043702  jz      loc_180043E17
0x180043708  mov     [rax], edi
0x18004370a  mov     [r9], rdi
0x18004370d  call    ?CheckLocalSecurity@@YAPEAVCProcess@@PEAX0@Z; CheckLocalSecurity(void *,void *)
0x180043712  mov     [rbp+120h+var_D8], rax
0x180043716  mov     r13, rax
0x180043719  test    rax, rax
0x18004371c  jnz     short loc_180043745
0x18004371e  mov     ebx, 80070005h
0x180043723  mov     edx, 33Eh; void *
0x180043728  mov     rcx, [rbp+128h]; this
0x18004372f  lea     r8, aOnecoreComComb_29; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x180043736  mov     r9d, ebx; char *
0x180043739  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004373e  mov     eax, ebx
0x180043740  jmp     loc_180043E1C
0x180043745  cmp     [rax+238h], rdi
0x18004374c  jnz     short loc_18004375A
0x18004374e  mov     ebx, 8000FFFFh
0x180043753  mov     edx, 343h
0x180043758  jmp     short loc_180043728
0x18004375a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180043761  lea     rdx, [rbp+120h+var_C0]; struct _GUID *
0x180043765  movdqu  xmmword ptr [rbp+120h+var_C0.Data1], xmm0
0x18004376a  mov     rcx, [rax+18h]; this
0x18004376e  call    ?GetComponentProcessId@CToken@@QEAAJPEAU_GUID@@@Z; CToken::GetComponentProcessId(_GUID *)
0x180043773  mov     ebx, eax
0x180043775  test    eax, eax
0x180043777  js      loc_180043E0A
0x18004377d  mov     eax, [r12]
0x180043781  mov     edx, 0FFFFFFFFh
0x180043786  mov     esi, eax
0x180043788  shl     rsi, 3
0x18004378c  cmp     rsi, rdx
0x18004378f  ja      loc_180043E05
0x180043795  lea     ecx, [rax-1]
0x180043798  shl     rcx, 2
0x18004379c  cmp     rcx, rdx
0x18004379f  ja      loc_180043E05
0x1800437a5  lea     r15d, [rcx+8]
0x1800437a9  cmp     r15d, 8
0x1800437ad  jb      loc_180043E05
0x1800437b3  mov     [rbp+120h+var_100], rdi
0x1800437b7  test    esi, esi
0x1800437b9  jz      short loc_180043826
0x1800437bb  mov     ebx, esi
0x1800437bd  cmp     rbx, cs:g_ulMaxStackAllocSize
0x1800437c4  ja      short loc_180043826
0x1800437c6  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800437cd  add     rcx, 8
0x1800437d1  add     rcx, rbx
0x1800437d4  cmp     rcx, rbx
0x1800437d7  jb      short loc_180043826
0x1800437d9  call    VerifyStackAvailable
0x1800437de  test    eax, eax
0x1800437e0  jz      short loc_180043826
0x1800437e2  lea     rax, [rbx+8]
0x1800437e6  lea     rcx, [rax+0Fh]
0x1800437ea  cmp     rcx, rax
0x1800437ed  ja      short loc_1800437F9
0x1800437ef  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800437f9  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800437fd  mov     rax, rcx
0x180043800  call    _alloca_probe
0x180043805  sub     rsp, rcx
0x180043808  lea     rdi, [rsp+160h+var_120]
0x18004380d  mov     [rbp+120h+var_100], rdi
0x180043811  test    rdi, rdi
0x180043814  jz      short loc_180043826
0x180043816  mov     dword ptr [rdi], 6B637453h
0x18004381c  add     rdi, 8
0x180043820  mov     [rbp+120h+var_100], rdi
0x180043824  jnz     short loc_180043857
0x180043826  mov     ebx, esi
0x180043828  lea     rcx, [rbx+8]
0x18004382c  cmp     rcx, rbx
0x18004382f  jb      short loc_180043857
0x180043831  mov     rax, cs:g_pfnAllocate
0x180043838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004383d  mov     [rbp+120h+var_100], rax
0x180043841  mov     rdi, rax
0x180043844  test    rax, rax
0x180043847  jz      short loc_180043857
0x180043849  add     rdi, 8
0x18004384d  mov     dword ptr [rax], 70616548h
0x180043853  mov     [rbp+120h+var_100], rdi
0x180043857  test    rdi, rdi
0x18004385a  jnz     short loc_180043866
0x18004385c  mov     ebx, 8007000Eh
0x180043861  jmp     loc_180043E0A
0x180043866  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18004386d  xor     edx, edx; dwFlags
0x18004386f  mov     r8d, r15d; dwBytes
0x180043872  mov     esi, r15d
0x180043875  call    cs:__imp_HeapAlloc
0x18004387c  nop     dword ptr [rax+rax+00h]
0x180043881  mov     [r14], rax
0x180043884  test    rax, rax
0x180043887  jnz     short loc_180043893
0x180043889  mov     ebx, 8007000Eh
0x18004388e  jmp     loc_180043DEB
0x180043893  mov     r8, rbx; Size
0x180043896  xor     edx, edx; Val
0x180043898  mov     rcx, rdi; void *
0x18004389b  call    memset_0
0x1800438a0  mov     rbx, [r14]
0x1800438a3  mov     r8, rsi; Size
0x1800438a6  mov     rcx, rbx; void *
0x1800438a9  mov     [rbp+120h+var_D0], rbx
0x1800438ad  xor     edx, edx; Val
0x1800438af  call    memset_0
0x1800438b4  mov     eax, [r12]
0x1800438b8  xor     esi, esi
0x1800438ba  mov     [rbx], eax
0x1800438bc  mov     ebx, esi
0x1800438be  mov     r15d, [r12]
0x1800438c2  mov     [rbp+120h+var_11C], r15d
0x1800438c6  mov     eax, esi
0x1800438c8  mov     [rbp+120h+length], eax
0x1800438cb  cmp     eax, r15d
0x1800438ce  jnb     loc_180043B92
0x1800438d4  xor     ecx, ecx
0x1800438d6  mov     [rbp+120h+string], rsi
0x1800438da  lea     r15, [rax+rax*2]
0x1800438de  mov     qword ptr [rbp+120h+hstringHeader.Reserved+10h], rcx
0x1800438e5  add     r15, r15
0x1800438e8  mov     qword ptr [rbp+120h+var_98.Reserved+10h], rcx
0x1800438ef  xorps   xmm0, xmm0
0x1800438f2  mov     [rbp+120h+var_108], rsi
0x1800438f6  xorps   xmm1, xmm1
0x1800438f9  mov     [rbp+120h+var_110], rax
0x1800438fd  movups  xmmword ptr [rbp+120h+hstringHeader.Reserved], xmm0
0x180043901  mov     rcx, [r12+r15*8+8]; unsigned __int16 *
0x180043906  movups  xmmword ptr [rbp+120h+var_98.Reserved], xmm1
0x18004390d  test    rcx, rcx
0x180043910  jz      loc_180043C66
0x180043916  call    ?BreakOnDebuggedActivatableClassId@@YAXPEBG@Z; BreakOnDebuggedActivatableClassId(ushort const *)
0x18004391b  mov     rcx, [r12+r15*8+8]; sourceString
0x180043920  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180043924  inc     rdx; length
0x180043927  cmp     [rcx+rdx*2], si
0x18004392b  jnz     short loc_180043924
0x18004392d  mov     eax, 0FFFFFFFFh
0x180043932  cmp     rdx, rax
0x180043935  ja      short loc_180043954
0x180043937  lea     r9, [rbp+120h+string]; string
0x18004393b  lea     r8, [rbp+120h+hstringHeader]; hstringHeader
0x18004393f  call    cs:__imp_WindowsCreateStringReference
0x180043946  nop     dword ptr [rax+rax+00h]
0x18004394b  mov     ebx, eax
0x18004394d  mov     eax, 0FFFFFFFFh
0x180043952  jmp     short loc_180043959
0x180043954  mov     ebx, 80070216h
0x180043959  test    ebx, ebx
0x18004395b  js      loc_180043B92
0x180043961  mov     rcx, [r12+r15*8+10h]; sourceString
0x180043966  test    rcx, rcx
0x180043969  jz      short loc_1800439A2
0x18004396b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004396f  inc     rdx; length
0x180043972  cmp     [rcx+rdx*2], si
0x180043976  jnz     short loc_18004396F
0x180043978  cmp     rdx, rax
0x18004397b  ja      loc_180043B6C
0x180043981  lea     r9, [rbp+120h+var_108]; string
0x180043985  lea     r8, [rbp+120h+var_98]; hstringHeader
0x18004398c  call    cs:__imp_WindowsCreateStringReference
0x180043993  nop     dword ptr [rax+rax+00h]
0x180043998  mov     ebx, eax
0x18004399a  test    eax, eax
0x18004399c  js      loc_180043B92
0x1800439a2  mov     ebx, [r12+r15*8+30h]
0x1800439a7  and     ebx, 40000000h
0x1800439ad  mov     [rbp+120h+var_F0], rsi
0x1800439b1  bts     ebx, 1Dh
0x1800439b5  shr     ebx, 7
0x1800439b8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800439bf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800439c4  mov     r9, [r13+18h]; struct CToken *
0x1800439c8  xor     r8d, r8d; struct IComClassInfo *
0x1800439cb  mov     rdx, [rbp+120h+var_108]; HSTRING
0x1800439cf  test    al, al
0x1800439d1  mov     rcx, [rbp+120h+string]; HSTRING
0x1800439d5  lea     rax, [rbp+120h+var_F0]
0x1800439d9  mov     [rsp+160h+var_130], rax; struct CClassData **
0x1800439de  mov     dword ptr [rsp+160h+var_138], ebx; unsigned int
0x1800439e2  mov     [rsp+160h+var_140], rsi; int
0x1800439e7  jz      short loc_1800439F0
0x1800439e9  call    ?LookupActivatableClassData@CActivatableClassData@@SAJPEAUHSTRING__@@0PEAUIComClassInfo@@PEAVCToken@@_KKPEAPEAVCClassData@@@Z; CActivatableClassData::LookupActivatableClassData(HSTRING__ *,HSTRING__ *,IComClassInfo *,CToken *,unsigned __int64,ulong,CClassData * *)
0x1800439ee  jmp     short loc_1800439F5
0x1800439f0  call    ?LookupActivatableClassDataOld@@YAJPEAUHSTRING__@@0PEAUIComClassInfo@@PEAVCToken@@_KKPEAPEAVCClassData@@@Z; LookupActivatableClassDataOld(HSTRING__ *,HSTRING__ *,IComClassInfo *,CToken *,unsigned __int64,ulong,CClassData * *)
0x1800439f5  mov     ebx, eax
0x1800439f7  test    eax, eax
0x1800439f9  js      loc_180043B92
0x1800439ff  mov     rsi, [rbp+120h+var_F0]
0x180043a03  mov     rdx, r13; struct CProcess *
0x180043a06  mov     rcx, rsi; this
0x180043a09  call    ?CertifyServer@CClassData@@QEAAJPEAVCProcess@@@Z; CClassData::CertifyServer(CProcess *)
0x180043a0e  mov     r14d, eax
0x180043a11  test    eax, eax
0x180043a13  js      loc_180043C15
0x180043a19  mov     rcx, [rbp+120h+var_108]; string
0x180043a1d  xor     r14d, r14d
0x180043a20  mov     ebx, r14d
0x180043a23  call    cs:__imp_WindowsIsStringEmpty
0x180043a2a  nop     dword ptr [rax+rax+00h]
0x180043a2f  test    eax, eax
0x180043a31  jnz     short loc_180043A3E
0x180043a33  mov     rbx, [r13+18h]
0x180043a37  add     rbx, 9Ch
0x180043a3e  mov     rax, [rsi]
0x180043a41  lea     r8, [rbp+120h+var_C0]
0x180043a45  mov     rdx, rbx
0x180043a48  mov     rcx, rsi
0x180043a4b  mov     rax, [rax+8]
0x180043a4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043a54  mov     rcx, [rbp+120h+var_110]
0x180043a58  mov     [rdi+rcx*8], rax
0x180043a5c  test    rax, rax
0x180043a5f  jz      loc_180043B73
0x180043a65  mov     rax, [rsi+60h]
0x180043a69  lea     rcx, [rbp+120h+var_C0]
0x180043a6d  mov     r12, [rbp+120h+var_108]
0x180043a71  mov     r9, rbx; void *
0x180043a74  mov     r13, [rbp+120h+string]
0x180043a78  mov     r8, r12; HSTRING
0x180043a7b  mov     [rsp+160h+var_140], rcx; struct _GUID *
0x180043a80  mov     rdx, r13; HSTRING
0x180043a83  cmp     dword ptr [rax+78h], 1
0x180043a87  setz    al
0x180043a8a  add     al, 2
0x180043a8c  mov     byte ptr [rbp+120h+var_120], al
0x180043a8f  mov     rax, cs:?gpActivatableClassTable@@3PEAVCWinRTServerTable@@EA; CWinRTServerTable * gpActivatableClassTable
0x180043a96  mov     rcx, rax; this
0x180043a99  mov     [rbp+120h+var_F0], rax
0x180043a9d  call    ?Lookup@CWinRTServerTable@@QEAAPEAVCWinRTServerTableEntry@@PEAUHSTRING__@@0PEAXAEBU_GUID@@@Z; CWinRTServerTable::Lookup(HSTRING__ *,HSTRING__ *,void *,_GUID const &)
0x180043aa2  mov     r14, rax
0x180043aa5  test    rax, rax
0x180043aa8  jnz     short loc_180043ADC
0x180043aaa  mov     rcx, [rbp+120h+var_F0]; this
0x180043aae  lea     rax, [rbp+120h+var_C0]
0x180043ab2  mov     r9, rbx; void *
0x180043ab5  mov     [rsp+160h+var_140], rax; struct _GUID *
0x180043aba  mov     r8, r12; HSTRING
0x180043abd  mov     rdx, r13; HSTRING
0x180043ac0  call    ?Create@CWinRTServerTable@@QEAAPEAVCWinRTServerTableEntry@@PEAUHSTRING__@@0PEAXAEBU_GUID@@@Z; CWinRTServerTable::Create(HSTRING__ *,HSTRING__ *,void *,_GUID const &)
0x180043ac5  mov     r14, rax
0x180043ac8  test    rax, rax
0x180043acb  jnz     short loc_180043ADC
0x180043acd  mov     r13, [rbp+120h+var_D8]
0x180043ad1  mov     ebx, 8007000Eh
0x180043ad6  mov     r12, [rbp+120h+var_C8]
0x180043ada  jmp     short loc_180043B40
0x180043adc  mov     r12, [rbp+120h+var_C8]
0x180043ae0  lea     r8, [rbp+120h+var_F0]; struct _GUID
0x180043ae4  mov     rcx, [rbp+120h+var_D0]
0x180043ae8  mov     r9, rsi; struct CClassData *
0x180043aeb  mov     rax, [rbp+120h+var_110]
0x180043aef  add     rcx, 4
0x180043af3  mov     r13, [rbp+120h+var_D8]
0x180043af7  movups  xmm0, xmmword ptr [r12+r15*8+20h]
0x180043afd  mov     rdx, r13; struct CProcess *
0x180043b00  lea     rax, [rcx+rax*4]
0x180043b04  mov     rcx, r14; this
0x180043b07  mov     [rsp+160h+var_128], rax; unsigned int *
0x180043b0c  mov     eax, [r12+r15*8+34h]
0x180043b11  mov     dword ptr [rsp+160h+var_130], eax; unsigned int
0x180043b15  mov     al, byte ptr [rbp+120h+var_120]
0x180043b18  mov     [rsp+160h+var_138], al; char
0x180043b1c  mov     [rsp+160h+var_140], 0; struct CAppidData *
0x180043b25  movdqu  xmmword ptr [rbp+120h+var_F0], xmm0
0x180043b2a  call    ?RegisterServer@CServerTableEntry@@QEAAJPEAVCProcess@@U_GUID@@PEAVCClassData@@PEAVCAppidData@@EKPEAK@Z; CServerTableEntry::RegisterServer(CProcess *,_GUID,CClassData *,CAppidData *,uchar,ulong,ulong *)
0x180043b2f  mov     ebx, eax
0x180043b31  mov     rcx, r14
0x180043b34  mov     rax, [r14]
0x180043b37  mov     rax, [rax+8]
0x180043b3b  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
