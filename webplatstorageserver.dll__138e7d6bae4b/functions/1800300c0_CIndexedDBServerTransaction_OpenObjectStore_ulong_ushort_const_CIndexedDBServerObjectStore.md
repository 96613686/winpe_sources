# CIndexedDBServerTransaction::OpenObjectStore(ulong,ushort const *,CIndexedDBServerObjectStore * *)

- ea: `0x1800300c0`
- end: `0x1800309c5`
- name: `?OpenObjectStore@CIndexedDBServerTransaction@@QEAAJKPEBGPEAPEAVCIndexedDBServerObjectStore@@@Z`
- size: `2309`
- prototype: `__int64 __fastcall(CIndexedDBServerTransaction *__hidden this, unsigned int, const unsigned __int16 *, struct CIndexedDBServerObjectStore **)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180027970`

## callees

- `0x18000d440`
- `0x18000d5a0`
- `0x18000dd40`
- `0x18000f630`
- `0x18000f810`
- `0x18000f9d0`
- `0x180012680`
- `0x180015a40`
- `0x180015bb0`
- `0x180016b40`
- `0x180017c20`
- `0x180024650`
- `0x180024720`
- `0x18002491c`
- `0x1800300c0`
- `0x180030a1c`
- `0x1800314c4`
- `0x1800315f0`
- `0x18003166c`
- `0x180031890`
- `0x1800766b8`
- `0x180080fb0`
- `0x1800814bc`
- `0x180081b10`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030236`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030260`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030792`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030236`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030260`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030792`
- `OLEAUT32!__imp_SysStringLen` at `0x180030179`
- `OLEAUT32!__imp_SysStringLen` at `0x180030179`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030124`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800301ff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003067e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030124`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800301ff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003067e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800306ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800306ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030739`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800306ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800306ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030739`
- `ESENT!JetCloseTable` at `0x18003087a`
- `ESENT!JetCloseTable` at `0x18003088d`
- `ESENT!JetCloseTable` at `0x1800308a0`
- `ESENT!JetCloseTable` at `0x18003087a`
- `ESENT!JetCloseTable` at `0x18003088d`
- `ESENT!JetCloseTable` at `0x1800308a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CIndexedDBServerTransaction::OpenObjectStore(
        CIndexedDBServerTransaction *this,
        unsigned int a2,
        __m128i *a3,
        struct CIndexedDBServerObjectStore **a4)
{
  unsigned __int64 v5; // r14
  struct _RTL_CRITICAL_SECTION *v7; // rbx
  int v8; // r13d
  char v9; // r15
  __int64 v10; // rbx
  OLECHAR *v11; // rdi
  unsigned __int64 v12; // rdx
  const __m128i *v14; // r10
  int v15; // eax
  __int64 v16; // rbx
  __int64 v17; // r13
  const char *v18; // r9
  wchar_t *v19; // r15
  unsigned __int64 v20; // r12
  HRESULT Key; // ebx
  const void *v22; // r9
  unsigned int v23; // edx
  CEseLayerIndexSchema *v24; // rbx
  unsigned int v25; // edx
  unsigned int v26; // edx
  unsigned int v27; // edx
  char v28; // r13
  CIndexedDBServerObjectStore *v29; // rax
  unsigned int v30; // edx
  CIndexedDBServerObjectStore *v31; // rbx
  int v32; // eax
  void (__fastcall ***v33)(_QWORD); // rcx
  void *v34; // rax
  char *v35; // rsi
  JET_SESID v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // rax
  const char *v40; // r9
  JET_SESID v41; // r13
  const void *v42; // r9
  const void *v43; // r9
  unsigned __int64 v47; // rax
  unsigned int v48; // [rsp+20h] [rbp-168h]
  unsigned int v49; // [rsp+20h] [rbp-168h]
  unsigned int v50; // [rsp+20h] [rbp-168h]
  unsigned int v51; // [rsp+20h] [rbp-168h]
  bool v52; // [rsp+40h] [rbp-148h] BYREF
  int v53; // [rsp+44h] [rbp-144h]
  JET_TABLEID tableid; // [rsp+48h] [rbp-140h] BYREF
  unsigned int v55[2]; // [rsp+50h] [rbp-138h] BYREF
  JET_SESID sesid; // [rsp+58h] [rbp-130h] BYREF
  JET_TABLEID v57; // [rsp+60h] [rbp-128h] BYREF
  JET_TABLEID v58; // [rsp+68h] [rbp-120h] BYREF
  JET_TABLEID v59; // [rsp+70h] [rbp-118h] BYREF
  JET_TABLEID v60; // [rsp+78h] [rbp-110h] BYREF
  void *Source; // [rsp+80h] [rbp-108h]
  CEseLayerIndexSchema *v62; // [rsp+88h] [rbp-100h]
  struct _RTL_CRITICAL_SECTION *v63; // [rsp+90h] [rbp-F8h]
  int v64; // [rsp+98h] [rbp-F0h]
  struct CIndexedDBServerObjectStore **v65; // [rsp+A0h] [rbp-E8h]
  char v66[8]; // [rsp+A8h] [rbp-E0h] BYREF
  CIndexedDBServerTransaction *v67; // [rsp+B0h] [rbp-D8h]
  struct JET_RETRIEVECOLUMN pszDest; // [rsp+C0h] [rbp-C8h] BYREF
  int v69; // [rsp+F0h] [rbp-98h]
  JET_TABLEID *v70; // [rsp+F8h] [rbp-90h]
  __int64 v71; // [rsp+100h] [rbp-88h]
  __int64 v72; // [rsp+108h] [rbp-80h]
  __int64 v73; // [rsp+110h] [rbp-78h]
  int v74; // [rsp+118h] [rbp-70h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  v65 = a4;
  Source = a3;
  v5 = a2;
  *a4 = 0;
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  v63 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  v64 = 0;
  if ( this != (CIndexedDBServerTransaction *)-16LL )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    v64 = 1;
  }
  v8 = -2147024891;
  if ( *((_BYTE *)this + 56) )
  {
    if ( *((_DWORD *)this + 40) != 2 )
    {
      v9 = 0;
      v10 = 0;
      if ( !*((_DWORD *)this + 32) )
      {
LABEL_44:
        v8 = -2140143605;
LABEL_56:
        v7 = v63;
        goto LABEL_57;
      }
      while ( !v9 )
      {
        v11 = *(OLECHAR **)(*((_QWORD *)this + 17) + 8 * v10);
        if ( SysStringLen(v11) == (_DWORD)v5 )
        {
          v12 = 0;
          _R9 = a3;
          v14 = (const __m128i *)v11;
          if ( !Avx2WmemEnabledWeakValue )
            goto LABEL_9;
          while ( v12 + 16 <= v5 )
          {
            __asm
            {
              vmovdqu ymm1, ymmword ptr [r9]
              vpcmpeqw ymm1, ymm1, ymmword ptr [r10]
              vpmovmskb eax, ymm1
            }
            if ( _EAX != -1 )
            {
              _BitScanForward((unsigned int *)&_EAX, ~_EAX);
              v53 = _EAX;
              __asm { vzeroupper }
              goto LABEL_12;
            }
            v12 += 16LL;
            _R9 += 2;
            v14 += 2;
            __asm { vzeroupper }
          }
LABEL_9:
          while ( v12 + 8 <= v5 )
          {
            LOWORD(v15) = _mm_movemask_epi8(_mm_cmpeq_epi16(_mm_loadu_si128(v14), _mm_loadu_si128(_R9)));
            if ( (_WORD)v15 != 0xFFFF )
            {
              _BitScanForward((unsigned int *)&v15, ~(unsigned __int16)v15);
              v53 = v15;
              goto LABEL_12;
            }
            v12 += 8LL;
            ++_R9;
            ++v14;
          }
          if ( v12 + 4 > v5 )
            goto LABEL_90;
          if ( _R9->m128i_i64[0] == v14->m128i_i64[0] )
          {
            v12 += 4LL;
LABEL_90:
            while ( v12 < v5 )
            {
              if ( a3->m128i_i16[v12] != v11[v12] )
                goto LABEL_12;
              ++v12;
            }
            v9 = 1;
          }
          else
          {
            _BitScanForward64(&v47, _R9->m128i_i64[0] ^ v14->m128i_i64[0]);
            v53 = v47;
          }
        }
LABEL_12:
        v10 = (unsigned int)(v10 + 1);
        if ( (unsigned int)v10 >= *((_DWORD *)this + 32) )
        {
          if ( !v9 )
            goto LABEL_44;
          break;
        }
      }
    }
    v66[0] = 0;
    v67 = this;
    _InterlockedIncrement((volatile signed __int32 *)this + 22);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
    if ( !*((_BYTE *)this + 56)
      || (v16 = *((_QWORD *)this + 21), !*(_BYTE *)(v16 + 8))
      || (v8 = HrJetSetSessionContext(*(_QWORD *)(v16 + 24), *((_QWORD *)this + 21)), v8 < 0) )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
      goto LABEL_55;
    }
    *(_DWORD *)(v16 + 12) = GetCurrentThreadId();
    v66[0] = 1;
    v17 = *((_QWORD *)this + 21);
    sesid = *(_QWORD *)(v17 + 16);
    if ( *(_DWORD *)(v17 + 12) != GetCurrentThreadId() )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xB5,
        (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\indexeddbv1\\ese\\transaction.cxx",
        v18);
    v19 = 0;
    v20 = *(_QWORD *)(v17 + 24);
    v55[0] = *(_DWORD *)(v17 + 32);
    Key = HrJetBeginTransaction(v20);
    v53 = -2147024882;
    if ( Key < 0 )
    {
LABEL_37:
      if ( Key >= 0 )
      {
        v29 = (CIndexedDBServerObjectStore *)operator new(0x118u);
        v31 = CIndexedDBServerObjectStore::CIndexedDBServerObjectStore(v29);
        v8 = v53;
        if ( v31 )
        {
          v32 = 0;
        }
        else
        {
          v31 = 0;
          v32 = v53;
        }
        if ( v32 < 0 )
        {
          v8 = v32;
LABEL_53:
          if ( v19 )
            CEseLayerObjectStore::`scalar deleting destructor'((CEseLayerObjectStore *)v19, v30);
          goto LABEL_55;
        }
        v33 = (void (__fastcall ***)(_QWORD))*((_QWORD *)this + 1);
        *((_BYTE *)v31 + 56) = 1;
        *((_QWORD *)v31 + 1) = v33;
        (**v33)(v33);
        if ( (_DWORD)v5 )
        {
          if ( 2 * v5 <= 0xFFFFFFFF )
          {
            v34 = MIDL_user_allocate((unsigned int)(2 * v5));
            if ( v34 )
            {
              *((_DWORD *)v31 + 26) = v5;
              *((_QWORD *)v31 + 14) = v34;
              v8 = 0;
            }
          }
          else
          {
            v8 = -2147024362;
          }
          if ( v8 < 0 )
          {
            CIndexedDBServerObjectStore::Close(v31);
LABEL_52:
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v31 + 20, 0xFFFFFFFF) == 1 && v31 )
              (**(void (__fastcall ***)(CIndexedDBServerObjectStore *, __int64))v31)(v31, 1);
            goto LABEL_53;
          }
        }
        else
        {
          *(_OWORD *)((char *)v31 + 104) = 0;
          v8 = 0;
        }
        memcpy_s_4(*((void *const *)v31 + 14), 2LL * *((unsigned int *)v31 + 26), Source, 2 * v5);
        *((_QWORD *)v31 + 15) = this;
        _InterlockedIncrement((volatile signed __int32 *)this + 22);
        *((_QWORD *)v31 + 16) = v19;
        v19 = 0;
        *v65 = v31;
        _InterlockedIncrement((volatile signed __int32 *)v31 + 20);
        v35 = (char *)this + 232;
        if ( *((_DWORD *)v35 + 6) )
          EnterCriticalSection((LPCRITICAL_SECTION)(v35 + 32));
        _InterlockedIncrement((volatile signed __int32 *)v31 + 20);
        v30 = (_DWORD)v31 + 88;
        *((_QWORD *)v31 + 11) = v35;
        *((_QWORD *)v31 + 12) = *((_QWORD *)v35 + 1);
        *((_QWORD *)v35 + 1) = (char *)v31 + 88;
        **((_QWORD **)v31 + 12) = (char *)v31 + 88;
        if ( *((_DWORD *)v35 + 6) )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v35 + 32));
        goto LABEL_52;
      }
      v8 = Key;
LABEL_55:
      CIndexedDBServerTransaction::CTransactionThreadScope::~CTransactionThreadScope((CIndexedDBServerTransaction::CTransactionThreadScope *)v66);
      goto LABEL_56;
    }
    v58 = -1;
    Key = HrJetOpenTable(v20, v55[0], L"DatabaseAndObjectStoreCatalog", v22, v48, 0, &v58);
    if ( Key < 0 )
    {
LABEL_99:
      HrJetRollback(v20, v23);
      goto LABEL_37;
    }
    v55[0] = *(_DWORD *)(sesid + 24);
    v57 = *(_QWORD *)(sesid + 8);
    tableid = v58;
    v60 = 0;
    v59 = 0;
    Key = HrJetSetCurrentIndex(v20, v58, L"objectStoreFinder");
    if ( Key >= 0 )
    {
      Key = HrJetMakeKey(v20, tableid, v55, 4u, 1u);
      if ( Key >= 0 )
      {
        Key = HrJetMakeKey(v20, tableid, Source, 2 * (int)v5, 0);
        if ( Key >= 0 )
        {
          Key = HrJetSeek(v20, tableid, 1u);
          if ( Key >= 0 )
          {
            pszDest.columnid = *(_DWORD *)(v57 + 200);
            pszDest.pvData = &v60;
            *(_QWORD *)&pszDest.cbData = 8;
            *(_QWORD *)&pszDest.grbit = 0;
            *(_QWORD *)&pszDest.itagSequence = 1;
            pszDest.err = 0;
            v69 = *(_DWORD *)(v57 + 452);
            v70 = &v59;
            v71 = 8;
            v72 = 0;
            v73 = 1;
            v74 = 0;
            v52 = 0;
            Key = HrJetRetrieveColumns(v20, tableid, &pszDest, 2u, &v52);
          }
        }
      }
    }
    if ( Key >= 0 )
    {
      v57 = v59;
      tableid = v60;
      Key = StringCchPrintfW((STRSAFE_LPWSTR)&pszDest, 0x40u, L"T-%I64x", v60);
      if ( Key >= 0 )
      {
        v62 = (CEseLayerIndexSchema *)operator new(0x400u);
        v24 = CEseLayerIndexSchema::CEseLayerIndexSchema(v62);
        v62 = v24;
        if ( v24 )
        {
          v19 = (wchar_t *)operator new(0xC0u);
          *(_QWORD *)v55 = v19;
          *(_QWORD *)v19 = 0;
          *((_QWORD *)v19 + 1) = 0;
          *((_QWORD *)v19 + 2) = 0;
          *((_QWORD *)v19 + 3) = v19 + 12;
          *((_QWORD *)v19 + 4) = v19 + 12;
          *((_DWORD *)v19 + 10) = 0;
          *((_QWORD *)v19 + 6) = 0;
          *((_QWORD *)v19 + 23) = 0;
          v19[28] = 0;
          Key = CEseLayerIndexSchema::OpenAllIndicesByPseudoPrimaryIndexId(
                  *(_QWORD *)(v17 + 24),
                  *(_DWORD *)(v17 + 32),
                  tableid,
                  v57,
                  (__int64)(v19 + 12),
                  (__int64)v24);
          if ( Key < 0 )
            goto LABEL_29;
          v37 = sesid;
          v38 = *(_QWORD *)(sesid + 8);
          v39 = *(_QWORD *)sesid;
          *((_QWORD *)v19 + 6) = v17;
          *(_QWORD *)v19 = v39;
          *((_QWORD *)v19 + 1) = v37;
          *((_QWORD *)v19 + 2) = v38;
          *((_QWORD *)v19 + 23) = tableid;
          if ( *(_DWORD *)(v17 + 12) != GetCurrentThreadId() )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0xB5,
              (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\indexeddbv1\\ese\\transaction.cxx",
              v40);
          sesid = *(_QWORD *)(v17 + 24);
          v55[0] = *(_DWORD *)(v17 + 32);
          v57 = -1;
          v41 = sesid;
          Key = HrJetOpenTable(sesid, v55[0], L"HeaderTable", v40, v49, 0, &v57);
          if ( Key >= 0 )
          {
            tableid = -1;
            Key = HrJetOpenTable(v41, v55[0], L"DatabaseAndObjectStoreCatalog", v42, v50, 0, &tableid);
            if ( Key >= 0 )
            {
              Key = StringCchPrintfW(v19 + 28, 0x40u, L"T-%I64x", *((_QWORD *)v19 + 23));
              if ( Key >= 0 )
              {
                sesid = -1;
                Key = HrJetOpenTable(v41, v55[0], v19 + 28, v43, v51, 0, &sesid);
                if ( sesid != -1 )
                  JetCloseTable(v41, sesid);
              }
            }
            if ( tableid != -1 )
              JetCloseTable(v41, tableid);
          }
          v25 = v57;
          if ( v57 != -1 )
            JetCloseTable(v41, v57);
          if ( Key >= 0 )
          {
            Key = HrJetCommitTransaction(v20, 1u);
            if ( Key >= 0 )
            {
              v28 = 0;
LABEL_33:
              v23 = v58;
              if ( v58 != -1 && (int)HrJetCloseTable(v20, v58) >= 0 )
                v58 = -1;
              if ( !v28 )
                goto LABEL_37;
              goto LABEL_99;
            }
            if ( v19 )
              CEseLayerObjectStore::`scalar deleting destructor'((CEseLayerObjectStore *)v19, v27);
          }
          else
          {
LABEL_29:
            CEseLayerObjectStore::`scalar deleting destructor'((CEseLayerObjectStore *)v19, v25);
            CEseLayerIndexSchema::`scalar deleting destructor'(v62, v26);
          }
        }
        else
        {
          Key = v53;
        }
      }
      v19 = 0;
    }
    v28 = 1;
    goto LABEL_33;
  }
LABEL_57:
  if ( v64 && v7 )
    LeaveCriticalSection(v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800300c0  push    rbx
0x1800300c2  push    rsi
0x1800300c3  push    rdi
0x1800300c4  push    r12
0x1800300c6  push    r13
0x1800300c8  push    r14
0x1800300ca  push    r15
0x1800300cc  sub     rsp, 150h
0x1800300d3  mov     rax, cs:__security_cookie
0x1800300da  xor     rax, rsp
0x1800300dd  mov     [rsp+188h+var_48], rax
0x1800300e5  mov     [rsp+188h+var_E8], r9
0x1800300ed  mov     r12, r8
0x1800300f0  mov     [rsp+188h+Source], r8
0x1800300f8  mov     r14d, edx
0x1800300fb  mov     rsi, rcx
0x1800300fe  mov     qword ptr [r9], 0
0x180030105  lea     rbx, [rcx+10h]
0x180030109  mov     [rsp+188h+var_F8], rbx
0x180030111  mov     [rsp+188h+var_F0], 0
0x18003011c  test    rbx, rbx
0x18003011f  jz      short loc_180030135
0x180030121  mov     rcx, rbx; lpCriticalSection
0x180030124  call    cs:__imp_EnterCriticalSection
0x18003012a  mov     [rsp+188h+var_F0], 1
0x180030135  mov     r13d, 80070005h
0x18003013b  movzx   eax, byte ptr [rsi+38h]
0x18003013f  nop
0x180030140  test    al, al
0x180030142  jz      loc_1800306DA
0x180030148  cmp     dword ptr [rsi+0A0h], 2
0x18003014f  jz      loc_1800301E4
0x180030155  xor     r15b, r15b
0x180030158  xor     ebx, ebx
0x18003015a  cmp     [rsi+80h], ebx
0x180030160  jbe     loc_180030606
0x180030166  test    r15b, r15b
0x180030169  jnz     short loc_1800301E4
0x18003016b  mov     rax, [rsi+88h]
0x180030172  mov     rdi, [rax+rbx*8]
0x180030176  mov     rcx, rdi; pbstr
0x180030179  call    cs:__imp_SysStringLen
0x18003017f  cmp     eax, r14d
0x180030182  jnz     short loc_1800301D1
0x180030184  xor     edx, edx
0x180030186  mov     r9, r12
0x180030189  mov     r10, rdi
0x18003018c  cmp     cs:_Avx2WmemEnabledWeakValue, edx
0x180030192  jnz     loc_1800308B3
0x180030198  lea     rcx, [rdx+8]
0x18003019c  cmp     rcx, r14
0x18003019f  ja      loc_180030908
0x1800301a5  movdqu  xmm1, xmmword ptr [r10]
0x1800301aa  movdqu  xmm0, xmmword ptr [r9]
0x1800301af  pcmpeqw xmm1, xmm0
0x1800301b3  pmovmskb eax, xmm1
0x1800301b7  mov     edx, 0FFFFh
0x1800301bc  cmp     ax, dx
0x1800301bf  jz      loc_1800308F8
0x1800301c5  movzx   eax, ax
0x1800301c8  not     eax
0x1800301ca  bsf     eax, eax
0x1800301cd  mov     [rsp+188h+var_144], eax
0x1800301d1  inc     ebx
0x1800301d3  cmp     ebx, [rsi+80h]
0x1800301d9  jb      short loc_180030166
0x1800301db  test    r15b, r15b
0x1800301de  jz      loc_180030606
0x1800301e4  mov     [rsp+188h+var_E0], 0
0x1800301ec  mov     [rsp+188h+var_D8], rsi
0x1800301f4  lock inc dword ptr [rsi+58h]
0x1800301f8  lea     rcx, [rsi+0C0h]; lpCriticalSection
0x1800301ff  call    cs:__imp_EnterCriticalSection
0x180030205  movzx   eax, byte ptr [rsi+38h]
0x180030209  nop
0x18003020a  test    al, al
0x18003020c  jz      loc_180030732
0x180030212  mov     rbx, [rsi+0A8h]
0x180030219  cmp     byte ptr [rbx+8], 0
0x18003021d  jz      loc_180030732
0x180030223  mov     rdx, rbx; unsigned __int64
0x180030226  mov     rcx, [rbx+18h]; unsigned __int64
0x18003022a  call    ?HrJetSetSessionContext@@YAJ_K0@Z; HrJetSetSessionContext(unsigned __int64,unsigned __int64)
0x18003022f  mov     r13d, eax
0x180030232  test    eax, eax
0x180030234  js      short loc_18003023F
0x180030236  call    cs:__imp_GetCurrentThreadId
0x18003023c  mov     [rbx+0Ch], eax
0x18003023f  test    r13d, r13d
0x180030242  js      loc_180030732
0x180030248  mov     [rsp+188h+var_E0], 1
0x180030250  mov     r13, [rsi+0A8h]
0x180030257  mov     rax, [r13+10h]
0x18003025b  mov     [rsp+188h+sesid], rax
0x180030260  call    cs:__imp_GetCurrentThreadId
0x180030266  mov     rcx, [rsp+188h]; this
0x18003026e  cmp     [r13+0Ch], eax
0x180030272  jnz     loc_180030950
0x180030278  xor     r15d, r15d
0x18003027b  mov     r12, [r13+18h]
0x18003027f  mov     eax, [r13+20h]
0x180030283  mov     [rsp+188h+var_138], eax
0x180030287  mov     rcx, r12; unsigned __int64
0x18003028a  call    ?HrJetBeginTransaction@@YAJ_K@Z; HrJetBeginTransaction(unsigned __int64)
0x18003028f  mov     ebx, eax
0x180030291  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180030298  mov     [rsp+188h+var_144], 8007000Eh
0x1800302a0  test    eax, eax
0x1800302a2  js      loc_180030594
0x1800302a8  mov     [rsp+188h+var_120], rdi
0x1800302ad  lea     rax, [rsp+188h+var_120]
0x1800302b2  mov     [rsp+188h+var_158], rax; JET_TABLEID *
0x1800302b7  mov     [rsp+188h+var_160], r15d; JET_GRBIT
0x1800302bc  lea     r8, aDatabaseandobj; "DatabaseAndObjectStoreCatalog"
0x1800302c3  mov     edx, [rsp+188h+var_138]; unsigned int
0x1800302c7  mov     rcx, r12; unsigned __int64
0x1800302ca  call    ?HrJetOpenTable@@YAJ_KKPEBGPEBXKKPEA_K@Z; HrJetOpenTable(unsigned __int64,ulong,ushort const *,void const *,ulong,ulong,unsigned __int64 *)
0x1800302cf  mov     ebx, eax
0x1800302d1  test    eax, eax
0x1800302d3  js      loc_180030993
0x1800302d9  mov     rcx, [rsp+188h+sesid]
0x1800302de  mov     eax, [rcx+18h]
0x1800302e1  mov     [rsp+188h+var_138], eax
0x1800302e5  mov     rax, [rcx+8]
0x1800302e9  mov     [rsp+188h+var_128], rax
0x1800302ee  mov     rax, [rsp+188h+var_120]
0x1800302f3  mov     [rsp+188h+tableid], rax
0x1800302f8  xor     ecx, ecx
0x1800302fa  mov     [rsp+188h+var_110], rcx
0x1800302ff  mov     [rsp+188h+var_118], rcx
0x180030304  lea     r8, aObjectstorefin; "objectStoreFinder"
0x18003030b  mov     rdx, rax; unsigned __int64
0x18003030e  mov     rcx, r12; unsigned __int64
0x180030311  call    ?HrJetSetCurrentIndex@@YAJ_K0PEBG@Z; HrJetSetCurrentIndex(unsigned __int64,unsigned __int64,ushort const *)
0x180030316  mov     ebx, eax
0x180030318  test    eax, eax
0x18003031a  js      loc_180030443
0x180030320  mov     [rsp+188h+var_168], 1; JET_GRBIT
0x180030328  mov     r9d, 4; unsigned int
0x18003032e  lea     r8, [rsp+188h+var_138]; void *
0x180030333  mov     rdx, [rsp+188h+tableid]; unsigned __int64
0x180030338  mov     rcx, r12; unsigned __int64
0x18003033b  call    ?HrJetMakeKey@@YAJ_K0PEBXKK@Z; HrJetMakeKey(unsigned __int64,unsigned __int64,void const *,ulong,ulong)
0x180030340  mov     ebx, eax
0x180030342  test    eax, eax
0x180030344  js      loc_180030443
0x18003034a  lea     r9d, [r14+r14]; unsigned int
0x18003034e  mov     [rsp+188h+var_168], r15d; JET_GRBIT
0x180030353  mov     r8, [rsp+188h+Source]; void *
0x18003035b  mov     rdx, [rsp+188h+tableid]; unsigned __int64
0x180030360  mov     rcx, r12; unsigned __int64
0x180030363  call    ?HrJetMakeKey@@YAJ_K0PEBXKK@Z; HrJetMakeKey(unsigned __int64,unsigned __int64,void const *,ulong,ulong)
0x180030368  mov     ebx, eax
0x18003036a  test    eax, eax
0x18003036c  js      loc_180030443
0x180030372  mov     r8d, 1; unsigned int
0x180030378  mov     rdx, [rsp+188h+tableid]; unsigned __int64
0x18003037d  mov     rcx, r12; unsigned __int64
0x180030380  call    ?HrJetSeek@@YAJ_K0K@Z; HrJetSeek(unsigned __int64,unsigned __int64,ulong)
0x180030385  mov     ebx, eax
0x180030387  test    eax, eax
0x180030389  js      loc_180030443
0x18003038f  mov     rcx, [rsp+188h+var_128]
0x180030394  mov     eax, [rcx+0C8h]
0x18003039a  mov     dword ptr [rsp+188h+pszDest], eax
0x1800303a1  lea     rax, [rsp+188h+var_110]
0x1800303a6  mov     [rsp+188h+var_C0], rax
0x1800303ae  mov     [rsp+188h+var_B8], 8
0x1800303ba  xor     edx, edx
0x1800303bc  mov     [rsp+188h+var_B0], rdx
0x1800303c4  mov     [rsp+188h+var_A8], 1
0x1800303d0  mov     [rsp+188h+var_A0], edx
0x1800303d7  mov     eax, [rcx+1C4h]
0x1800303dd  mov     [rsp+188h+var_98], eax
0x1800303e4  lea     rax, [rsp+188h+var_118]
0x1800303e9  mov     [rsp+188h+var_90], rax
0x1800303f1  mov     [rsp+188h+var_88], 8
0x1800303fd  mov     [rsp+188h+var_80], rdx
0x180030405  mov     [rsp+188h+var_78], 1
0x180030411  mov     [rsp+188h+var_70], edx
0x180030418  mov     [rsp+188h+var_148], dl
0x18003041c  lea     rax, [rsp+188h+var_148]
0x180030421  mov     qword ptr [rsp+188h+var_168], rax; bool *
0x180030426  mov     r9d, 2; unsigned int
0x18003042c  lea     r8, [rsp+188h+pszDest]; struct JET_RETRIEVECOLUMN *
0x180030434  mov     rdx, [rsp+188h+tableid]; unsigned __int64
0x180030439  mov     rcx, r12; unsigned __int64
0x18003043c  call    ?HrJetRetrieveColumns@@YAJ_K0PEAUJET_RETRIEVECOLUMN@@KPEA_N@Z; HrJetRetrieveColumns(unsigned __int64,unsigned __int64,JET_RETRIEVECOLUMN *,ulong,bool *)
0x180030441  mov     ebx, eax
0x180030443  test    ebx, ebx
0x180030445  js      loc_180030753
0x18003044b  mov     rax, [rsp+188h+var_118]
0x180030450  mov     [rsp+188h+var_128], rax
0x180030455  mov     rax, [rsp+188h+var_110]
0x18003045a  mov     [rsp+188h+tableid], rax
0x18003045f  mov     r9, rax
0x180030462  lea     r8, aTI64x; "T-%I64x"
0x180030469  mov     edx, 40h ; '@'; cchDest
0x18003046e  lea     rcx, [rsp+188h+pszDest]; pszDest
0x180030476  call    StringCchPrintfW
0x18003047b  mov     ebx, eax
0x18003047d  test    eax, eax
0x18003047f  js      loc_18003054E
0x180030485  mov     ecx, 400h; Size
0x18003048a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003048f  mov     [rsp+188h+var_100], rax
0x180030497  mov     rcx, rax; this
0x18003049a  call    ??0CEseLayerIndexSchema@@QEAA@XZ; CEseLayerIndexSchema::CEseLayerIndexSchema(void)
0x18003049f  mov     rbx, rax
0x1800304a2  mov     [rsp+188h+var_100], rax
0x1800304aa  test    rax, rax
0x1800304ad  jz      loc_180030962
0x1800304b3  mov     ecx, 0C0h; Size
0x1800304b8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800304bd  mov     r15, rax
0x1800304c0  mov     qword ptr [rsp+188h+var_138], rax
0x1800304c5  xor     eax, eax
0x1800304c7  mov     [r15], rax
0x1800304ca  mov     [r15+8], rax
0x1800304ce  mov     [r15+10h], rax
0x1800304d2  lea     rcx, [r15+18h]
0x1800304d6  mov     [rcx], rcx
0x1800304d9  mov     [rcx+8], rcx
0x1800304dd  mov     [rcx+10h], eax
0x1800304e0  mov     [r15+30h], rax
0x1800304e4  mov     [r15+0B8h], rax
0x1800304eb  mov     [r15+38h], ax
0x1800304f0  mov     [rsp+188h+var_150], rbx; __int64
0x1800304f5  mov     [rsp+188h+var_158], rcx; __int64
0x1800304fa  mov     rax, [rsp+188h+var_128]
0x1800304ff  mov     qword ptr [rsp+188h+var_160], rax; __int64
0x180030504  mov     rax, [rsp+188h+tableid]
0x180030509  mov     qword ptr [rsp+188h+var_168], rax; unsigned int
0x18003050e  lea     r9, [rsp+188h+pszDest]
0x180030516  mov     r8, [rsp+188h+sesid]
0x18003051b  mov     r8, [r8+8]
0x18003051f  mov     edx, [r13+20h]; unsigned int
0x180030523  mov     rcx, [r13+18h]; unsigned __int64
0x180030527  call    ?OpenAllIndicesByPseudoPrimaryIndexId@CEseLayerIndexSchema@@SAJ_KKPEBVCEseLayerDatabaseSchema@@PEBG_J3PEAVCList@?$CDoubleLink@VCEseLayerIndexSchema@@$1?CEseLayerIndexSchema_GetCIndexSchemaLink_lnkOffset@@YAHXZ@@PEAV1@@Z; CEseLayerIndexSchema::OpenAllIndicesByPseudoPrimaryIndexId(unsigned __int64,ulong,CEseLayerDatabaseSchema const *,ushort const *,__int64,__int64,CDoubleLink<CEseLayerIndexSchema,&CEseLayerIndexSchema_GetCIndexSchemaLink_lnkOffset(void)>::CList *,CEseLayerIndexSchema *)
0x18003052c  mov     ebx, eax
0x18003052e  test    eax, eax
0x180030530  jns     loc_18003076B
0x180030536  mov     rcx, r15; this
0x180030539  call    ??_GCEseLayerObjectStore@@QEAAPEAXI@Z; CEseLayerObjectStore::`scalar deleting destructor'(uint)
0x18003053e  mov     rcx, [rsp+188h+var_100]; this
0x180030546  call    ??_GCEseLayerIndexSchema@@QEAAPEAXI@Z; CEseLayerIndexSchema::`scalar deleting destructor'(uint)
0x18003054b  xor     r15d, r15d
0x18003054e  test    ebx, ebx
0x180030550  js      loc_180030750
0x180030556  mov     edx, 1; unsigned int
0x18003055b  mov     rcx, r12; unsigned __int64
0x18003055e  call    ?HrJetCommitTransaction@@YAJ_KK@Z; HrJetCommitTransaction(unsigned __int64,ulong)
0x180030563  mov     ebx, eax
0x180030565  test    eax, eax
0x180030567  js      loc_18003097D
0x18003056d  xor     r13b, r13b
0x180030570  mov     rdx, [rsp+188h+var_120]; unsigned __int64
0x180030575  cmp     rdx, rdi
0x180030578  jz      short loc_18003058B
0x18003057a  mov     rcx, r12; unsigned __int64
0x18003057d  call    ?HrJetCloseTable@@YAJ_K0@Z; HrJetCloseTable(unsigned __int64,unsigned __int64)
0x180030582  test    eax, eax
0x180030584  js      short loc_18003058B
0x180030586  mov     [rsp+188h+var_120], rdi
0x18003058b  test    r13b, r13b
0x18003058e  jnz     loc_180030993
0x180030594  test    ebx, ebx
0x180030596  js      loc_180030763
0x18003059c  mov     ecx, 118h; Size
0x1800305a1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800305a6  mov     rcx, rax; this
0x1800305a9  call    ??0CIndexedDBServerObjectStore@@AEAA@XZ; CIndexedDBServerObjectStore::CIndexedDBServerObjectStore(void)
0x1800305ae  mov     rbx, rax
0x1800305b1  mov     r13d, [rsp+188h+var_144]
0x1800305b6  test    rax, rax
0x1800305b9  jz      loc_1800309A0
0x1800305bf  xor     eax, eax
0x1800305c1  test    eax, eax
0x1800305c3  js      loc_18003075B
0x1800305c9  mov     rcx, [rsi+8]
0x1800305cd  mov     eax, 1
0x1800305d2  xchg    al, [rbx+38h]
0x1800305d5  mov     [rbx+8], rcx
0x1800305d9  mov     rax, [rcx]
0x1800305dc  mov     rax, [rax]
0x1800305df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800305e4  mov     r12, r14
0x1800305e7  test    r14d, r14d
0x1800305ea  jz      loc_180030741
0x1800305f0  lea     rax, [r14+r14]
0x1800305f4  mov     ecx, 0FFFFFFFFh
0x1800305f9  cmp     rax, rcx
0x1800305fc  jbe     short loc_180030611
0x1800305fe  mov     r13d, 80070216h
0x180030604  jmp     short loc_180030628
0x180030606  mov     r13d, 8070000Bh
0x18003060c  jmp     loc_1800306D2
0x180030611  mov     ecx, eax; size
0x180030613  call    MIDL_user_allocate
0x180030618  test    rax, rax
  ... truncated ...
```
