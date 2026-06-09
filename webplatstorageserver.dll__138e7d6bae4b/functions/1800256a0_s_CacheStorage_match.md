# s_CacheStorage_match

- ea: `0x1800256a0`
- end: `0x180025b19`
- name: `s_CacheStorage_match`
- size: `1145`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int *, const struct __MIDL_RPCCacheStorage_0003 **)`
- caller_count: `0`
- callee_count: `21`
- tags: `broker_com_uri`

## callees

- `0x180024c2c`
- `0x180025560`
- `0x1800256a0`
- `0x180025b20`
- `0x180025b94`
- `0x180025bd0`
- `0x180026280`
- `0x180026290`
- `0x180027550`
- `0x1800275f0`
- `0x1800277c0`
- `0x180066010`
- `0x180070e88`
- `0x1800767cc`
- `0x1800767d8`
- `0x1800767e4`
- `0x180080fb0`
- `0x18008149c`
- `0x180083fcc`
- `0x180084034`
- `0x1800b5f04`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180025a16`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180025a16`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180025755`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180025755`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180025767`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180025767`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800257ce`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800257ce`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x180025761`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x180025761`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800256fb`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800256fb`

## string_xrefs

- `0x1800256e0`: `RPC CacheStorage_match`
- `0x18002582b`: `CS_CacheStorage_match`
- `0x180025af9`: `onecoreuap\inetcore\webplatstorageserver\cachestorage\rpcapi.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall s_CacheStorage_match(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int *a4,
        const struct __MIDL_RPCCacheStorage_0003 **a5)
{
  const WCHAR *v8; // rdi
  const wchar_t *v9; // rax
  int v10; // eax
  unsigned __int16 *v11; // rcx
  HANDLE CurrentThread; // rax
  APTTYPE v13; // r14d
  APTTYPE *v14; // rdi
  __int64 v15; // rax
  unsigned int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rcx
  const char *v20; // r9
  wil::details::in1diag3 *v21; // r10
  const char *v22; // r9
  __int64 v24; // rcx
  wil *v25; // rcx
  int v26; // [rsp+20h] [rbp-1E8h]
  _BYTE v27[8]; // [rsp+30h] [rbp-1D8h] BYREF
  APTTYPEQUALIFIER pAptQualifier[2]; // [rsp+38h] [rbp-1D0h] BYREF
  APTTYPE pAptType[2]; // [rsp+40h] [rbp-1C8h] BYREF
  __int64 v30; // [rsp+48h] [rbp-1C0h]
  _BYTE v31[48]; // [rsp+50h] [rbp-1B8h] BYREF
  unsigned __int16 v32[4]; // [rsp+80h] [rbp-188h] BYREF
  int v33; // [rsp+88h] [rbp-180h] BYREF
  char v34; // [rsp+8Ch] [rbp-17Ch]
  int v35; // [rsp+B0h] [rbp-158h] BYREF
  const char *v36; // [rsp+B8h] [rbp-150h]
  __int64 v37; // [rsp+C0h] [rbp-148h]
  char v38; // [rsp+C8h] [rbp-140h]
  int v39; // [rsp+D0h] [rbp-138h]
  __int128 v40; // [rsp+D8h] [rbp-130h]
  __int128 v41; // [rsp+E8h] [rbp-120h]
  __int128 v42; // [rsp+F8h] [rbp-110h]
  __int128 v43; // [rsp+108h] [rbp-100h]
  __int128 v44; // [rsp+118h] [rbp-F0h]
  __int128 v45; // [rsp+128h] [rbp-E0h]
  __int128 v46; // [rsp+138h] [rbp-D0h]
  __int128 v47; // [rsp+148h] [rbp-C0h]
  __int128 v48; // [rsp+158h] [rbp-B0h]
  __int64 v49; // [rsp+168h] [rbp-A0h]
  __int128 v50; // [rsp+170h] [rbp-98h]
  int v51; // [rsp+180h] [rbp-88h]
  __int64 v52; // [rsp+188h] [rbp-80h]
  int *v53; // [rsp+190h] [rbp-78h]
  __int64 v54; // [rsp+198h] [rbp-70h]
  __int64 v55; // [rsp+1A0h] [rbp-68h]
  unsigned __int16 *v56; // [rsp+1A8h] [rbp-60h]
  __int64 v57; // [rsp+1B0h] [rbp-58h]
  int v58; // [rsp+1B8h] [rbp-50h]
  int *v59; // [rsp+1C0h] [rbp-48h]
  char v60; // [rsp+1C8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h]

  v8 = L"RPC CacheStorage_match";
  pAptType[0] = APTTYPE_STA;
  pAptQualifier[0] = APTTYPEQUALIFIER_NONE;
  if ( CoGetApartmentType(pAptType, pAptQualifier) )
    goto LABEL_8;
  if ( pAptType[0] != APTTYPE_MTA )
  {
    if ( pAptType[0] )
    {
      if ( pAptType[0] == APTTYPE_NA )
      {
        switch ( pAptQualifier[0] )
        {
          case APTTYPEQUALIFIER_NA_ON_MTA:
            v9 = L"NA on MTA";
            break;
          case APTTYPEQUALIFIER_NA_ON_STA:
            v9 = L"NA on STA";
            break;
          case APTTYPEQUALIFIER_NA_ON_IMPLICIT_MTA:
            v9 = L"NA on MTA Implicit";
            break;
          case APTTYPEQUALIFIER_NA_ON_MAINSTA:
            v9 = L"NA on MAINSTA";
            break;
          default:
            v9 = L"NA";
            break;
        }
        goto LABEL_5;
      }
      if ( pAptType[0] != APTTYPE_MAINSTA )
        goto LABEL_8;
    }
    v9 = L"ASTA";
    if ( pAptQualifier[0] != APTTYPEQUALIFIER_APPLICATION_STA )
      v9 = L"STA";
    goto LABEL_5;
  }
  if ( pAptQualifier[0] == APTTYPEQUALIFIER_IMPLICIT_MTA )
    v9 = (const wchar_t *)L"MTA Implicit";
  else
    v9 = L"MTA";
LABEL_5:
  v10 = StringCchPrintfW(v32, 0x80u, L"%s %s", L"RPC CacheStorage_match", v9);
  v11 = v32;
  if ( v10 < 0 )
    v11 = L"RPC CacheStorage_match";
  v8 = v11;
LABEL_8:
  CurrentThread = GetCurrentThread();
  SetThreadDescription(CurrentThread, v8);
  if ( IsDebuggerPresent() )
    SetThreadNameViaException(v8);
  if ( dword_180114128 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 5060LL) )
    goto LABEL_21;
  while ( 1 )
  {
    *(_QWORD *)pAptQualifier = &qword_180114130;
    _InterlockedIncrement64(&qword_180114130);
    *(_QWORD *)pAptType = qword_180114140;
    SetThreadpoolTimer(pti, (PFILETIME)pAptType, 0, 0);
    *a5 = 0;
    v13 = APTTYPE_STA;
    *(_QWORD *)pAptType = 0;
    v30 = 0;
    v14 = 0;
    if ( !a4 )
      break;
    v15 = *((_QWORD *)a4 + 1);
    if ( v15 || !*a4 )
    {
      *(_QWORD *)pAptType = *a4;
      v30 = v15;
      v14 = pAptType;
      break;
    }
    _o_terminate(*a4);
LABEL_21:
    Init_thread_header(&dword_180114128);
    if ( dword_180114128 == -1 )
    {
      HangDetectionWatchDog::HangDetectionWatchDog(v24, 300000);
      atexit(HangDetectionWatchDog::s_DefaultInstance_::_2_::_dynamic_atexit_destructor_for__s_instance__);
      Init_thread_footer(&dword_180114128);
    }
  }
  try
  {
    v33 = 0;
    v34 = 0;
    v38 = 0;
    v35 = 0;
    v36 = "CS_CacheStorage_match";
    v37 = 0;
    v39 = 0;
    v50 = 0;
    v40 = 0;
    v41 = 0;
    v42 = 0;
    v43 = 0;
    v44 = 0;
    v45 = 0;
    v46 = 0;
    v47 = 0;
    v48 = 0;
    v49 = 0;
    v51 = 1;
    v52 = 0;
    v53 = &v33;
    v54 = 0;
    v55 = 0;
    v56 = v32;
    v57 = 0;
    v58 = 0;
    v59 = &v35;
    v60 = 0;
    *(_QWORD *)v32 = &CacheStorageTraceLogging::CS_CacheStorage_match::`vftable';
    CacheStorageTraceLogging::CS_CacheStorage_match::StartActivity(v32, a2, a3, v14);
    CacheStorageSession::Match(a2, v31, a3, v14);
    if ( !(unsigned __int8)std::deque<ResponseMatch>::empty(v31) )
    {
      v16 = wil::verify_hresult<long>(2147549183LL);
      LOBYTE(v19) = std::deque<ResponseMatch>::size(v31, v17, v18, v16) != 1;
      if ( (unsigned __int8)wil::verify_bool<bool,0>(v19) )
        wil::details::in1diag3::Throw_Hr(
          v21,
          (void *)0xE6,
          (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\cachestorage\\rpcapi.cxx",
          v20,
          v26);
      *a5 = (const struct __MIDL_RPCCacheStorage_0003 *)ResponseMatch::s_AllocateResponseInfosForRpc(v31);
    }
    CacheStorageTraceLogging::CS_CacheStorage_match::Stop((CacheStorageTraceLogging::CS_CacheStorage_match *)v32, *a5);
    std::deque<ResponseMatch>::~deque<ResponseMatch>(v31);
    CacheStorageTraceLogging::CS_CacheStorage_match::~CS_CacheStorage_match((CacheStorageTraceLogging::CS_CacheStorage_match *)v32);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xEE,
      (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\cachestorage\\rpcapi.cxx",
      v22);
    pAptType[0] = wil::ResultFromCaughtException(v25);
    v13 = pAptType[0];
  }
  HangDetectionWatchDog::Activity::~Activity((HangDetectionWatchDog::Activity *)pAptQualifier);
  AutoSetThreadName::~AutoSetThreadName((AutoSetThreadName *)v27);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800256a0  mov     [rsp+arg_0], rbx
0x1800256a5  mov     [rsp+arg_18], rsi
0x1800256aa  push    rdi
0x1800256ab  push    r12
0x1800256ad  push    r13
0x1800256af  push    r14
0x1800256b1  push    r15
0x1800256b3  sub     rsp, 1E0h
0x1800256ba  mov     rax, cs:__security_cookie
0x1800256c1  xor     rax, rsp
0x1800256c4  mov     [rsp+208h+var_38], rax
0x1800256cc  mov     rbx, r9
0x1800256cf  mov     r12, r8
0x1800256d2  mov     r15, rdx
0x1800256d5  mov     rsi, [rsp+208h+arg_20]
0x1800256dd  xor     r13d, r13d
0x1800256e0  lea     rdi, WideCharStr; "RPC CacheStorage_match"
0x1800256e7  mov     [rsp+208h+pAptType], r13d
0x1800256ec  mov     [rsp+208h+pAptQualifier], r13d
0x1800256f1  lea     rdx, [rsp+208h+pAptQualifier]; pAptQualifier
0x1800256f6  lea     rcx, [rsp+208h+pAptType]; pAptType
0x1800256fb  call    cs:__imp_CoGetApartmentType
0x180025701  test    eax, eax
0x180025703  jnz     short loc_180025755
0x180025705  mov     ecx, [rsp+208h+pAptType]
0x180025709  cmp     ecx, 1
0x18002570c  jnz     loc_180025A6A
0x180025712  cmp     [rsp+208h+pAptQualifier], ecx
0x180025716  jnz     loc_180025A5E
0x18002571c  lea     rax, aMtaImplicit; "MTA Implicit"
0x180025723  mov     qword ptr [rsp+208h+var_1E8], rax; int
0x180025728  mov     r9, rdi
0x18002572b  lea     r8, aSS_1; "%s %s"
0x180025732  mov     edx, 80h; unsigned __int64
0x180025737  lea     rcx, [rsp+208h+var_188]; unsigned __int16 *
0x18002573f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180025744  lea     rcx, [rsp+208h+var_188]
0x18002574c  test    eax, eax
0x18002574e  cmovs   rcx, rdi
0x180025752  mov     rdi, rcx
0x180025755  call    cs:__imp_GetCurrentThread
0x18002575b  mov     rcx, rax; hThread
0x18002575e  mov     rdx, rdi; lpThreadDescription
0x180025761  call    cs:__imp_SetThreadDescription
0x180025767  call    cs:__imp_IsDebuggerPresent
0x18002576d  test    eax, eax
0x18002576f  jnz     loc_180025AEC
0x180025775  mov     ecx, cs:_tls_index
0x18002577b  mov     rax, gs:58h
0x180025784  mov     edx, 13C4h
0x180025789  mov     rax, [rax+rcx*8]
0x18002578d  mov     ecx, [rdx+rax]
0x180025790  cmp     cs:dword_180114128, ecx
0x180025796  jg      loc_180025A1D
0x18002579c  lea     rax, qword_180114130
0x1800257a3  mov     qword ptr [rsp+208h+pAptQualifier], rax
0x1800257a8  lock inc cs:qword_180114130
0x1800257b0  mov     rax, cs:qword_180114140
0x1800257b7  mov     qword ptr [rsp+208h+pAptType], rax
0x1800257bc  xor     r9d, r9d; msWindowLength
0x1800257bf  xor     r8d, r8d; msPeriod
0x1800257c2  lea     rdx, [rsp+208h+pAptType]; pftDueTime
0x1800257c7  mov     rcx, cs:pti; pti
0x1800257ce  call    cs:__imp_SetThreadpoolTimer
0x1800257d4  nop
0x1800257d5  mov     [rsi], r13
0x1800257d8  mov     r14d, r13d
0x1800257db  mov     qword ptr [rsp+208h+pAptType], r13
0x1800257e0  mov     [rsp+208h+var_1C0], r13
0x1800257e5  mov     rdi, r13
0x1800257e8  test    rbx, rbx
0x1800257eb  jz      short loc_18002580B
0x1800257ed  mov     ecx, [rbx]
0x1800257ef  mov     rax, [rbx+8]
0x1800257f3  test    rax, rax
0x1800257f6  jz      loc_180025A0D
0x1800257fc  mov     qword ptr [rsp+208h+pAptType], rcx
0x180025801  mov     [rsp+208h+var_1C0], rax
0x180025806  lea     rdi, [rsp+208h+pAptType]
0x18002580b  mov     [rsp+208h+var_180], r13d
0x180025813  mov     [rsp+208h+var_17C], 0
0x18002581b  mov     [rsp+208h+var_140], 0
0x180025823  mov     [rsp+208h+var_158], r13d
0x18002582b  lea     rax, aCsCachestorage; "CS_CacheStorage_match"
0x180025832  mov     [rsp+208h+var_150], rax
0x18002583a  mov     [rsp+208h+var_148], r13
0x180025842  mov     [rsp+208h+var_138], r13d
0x18002584a  xorps   xmm0, xmm0
0x18002584d  movdqa  [rsp+208h+var_98], xmm0
0x180025856  xorps   xmm1, xmm1
0x180025859  xor     eax, eax
0x18002585b  movups  [rsp+208h+var_130], xmm1
0x180025863  movups  [rsp+208h+var_120], xmm1
0x18002586b  movups  [rsp+208h+var_110], xmm1
0x180025873  movups  [rsp+208h+var_100], xmm1
0x18002587b  movups  [rsp+208h+var_F0], xmm1
0x180025883  movups  [rsp+208h+var_E0], xmm1
0x18002588b  movups  [rsp+208h+var_D0], xmm1
0x180025893  movups  [rsp+208h+var_C0], xmm1
0x18002589b  movups  [rsp+208h+var_B0], xmm1
0x1800258a3  mov     [rsp+208h+var_A0], rax
0x1800258ab  mov     [rsp+208h+var_88], 1
0x1800258b6  mov     [rsp+208h+var_80], rax
0x1800258be  lea     rax, [rsp+208h+var_180]
0x1800258c6  mov     [rsp+208h+var_78], rax
0x1800258ce  mov     [rsp+208h+var_70], r13
0x1800258d6  mov     [rsp+208h+var_68], r13
0x1800258de  lea     rax, [rsp+208h+var_188]
0x1800258e6  mov     [rsp+208h+var_60], rax
0x1800258ee  mov     [rsp+208h+var_58], r13
0x1800258f6  mov     [rsp+208h+var_50], r13d
0x1800258fe  lea     rax, [rsp+208h+var_158]
0x180025906  mov     [rsp+208h+var_48], rax
0x18002590e  mov     [rsp+208h+var_40], 0
0x180025916  lea     rax, ??_7CS_CacheStorage_match@CacheStorageTraceLogging@@6B@; const CacheStorageTraceLogging::CS_CacheStorage_match::`vftable'
0x18002591d  mov     qword ptr [rsp+208h+var_188], rax
0x180025925  mov     r9, rdi
0x180025928  mov     r8, r12
0x18002592b  mov     rdx, r15
0x18002592e  lea     rcx, [rsp+208h+var_188]
0x180025936  call    ?StartActivity@CS_CacheStorage_match@CacheStorageTraceLogging@@QEAAXPEAXAEBU__MIDL_RPCCacheStorage_0002@@PEBV?$basic_string_span@$$CBG$0?0@gsl@@@Z; CacheStorageTraceLogging::CS_CacheStorage_match::StartActivity(void *,__MIDL_RPCCacheStorage_0002 const &,gsl::basic_string_span<ushort const,-1> const *)
0x18002593b  nop
0x18002593c  mov     r9, rdi
0x18002593f  mov     r8, r12
0x180025942  lea     rdx, [rsp+208h+var_1B8]
0x180025947  mov     rcx, r15
0x18002594a  call    ?Match@CacheStorageSession@@QEAA?AV?$deque@VResponseMatch@@V?$allocator@VResponseMatch@@@std@@@std@@AEBU__MIDL_RPCCacheStorage_0002@@PEAV?$basic_string_span@$$CBG$0?0@gsl@@@Z; CacheStorageSession::Match(__MIDL_RPCCacheStorage_0002 const &,gsl::basic_string_span<ushort const,-1> *)
0x18002594f  nop
0x180025950  lea     rcx, [rsp+208h+var_1B8]
0x180025955  call    ?empty@?$deque@VResponseMatch@@V?$allocator@VResponseMatch@@@std@@@std@@QEBA_NXZ; std::deque<ResponseMatch>::empty(void)
0x18002595a  test    al, al
0x18002595c  jnz     short loc_18002599E
0x18002595e  mov     ecx, 8000FFFFh
0x180025963  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180025968  mov     r9d, eax
0x18002596b  mov     r10, [rsp+208h]
0x180025973  lea     rcx, [rsp+208h+var_1B8]
0x180025978  call    ?size@?$deque@VResponseMatch@@V?$allocator@VResponseMatch@@@std@@@std@@QEBA_KXZ; std::deque<ResponseMatch>::size(void)
0x18002597d  cmp     rax, 1
0x180025981  setnz   cl
0x180025984  call    ??$verify_bool@_N$0A@@wil@@YA_N_N@Z; wil::verify_bool<bool,0>(bool)
0x180025989  test    al, al
0x18002598b  jnz     loc_180025AF9
0x180025991  lea     rcx, [rsp+208h+var_1B8]
0x180025996  call    ?s_AllocateResponseInfosForRpc@ResponseMatch@@SAPEAU__MIDL_RPCCacheStorage_0003@@AEAV?$deque@VResponseMatch@@V?$allocator@VResponseMatch@@@std@@@std@@@Z; ResponseMatch::s_AllocateResponseInfosForRpc(std::deque<ResponseMatch> &)
0x18002599b  mov     [rsi], rax
0x18002599e  mov     rdx, [rsi]; struct __MIDL_RPCCacheStorage_0003 *
0x1800259a1  lea     rcx, [rsp+208h+var_188]; this
0x1800259a9  call    ?Stop@CS_CacheStorage_match@CacheStorageTraceLogging@@QEAAXPEBU__MIDL_RPCCacheStorage_0003@@@Z; CacheStorageTraceLogging::CS_CacheStorage_match::Stop(__MIDL_RPCCacheStorage_0003 const *)
0x1800259ae  nop
0x1800259af  lea     rcx, [rsp+208h+var_1B8]
0x1800259b4  call    ??1?$deque@VResponseMatch@@V?$allocator@VResponseMatch@@@std@@@std@@QEAA@XZ; std::deque<ResponseMatch>::~deque<ResponseMatch>(void)
0x1800259b9  nop
0x1800259ba  lea     rcx, [rsp+208h+var_188]; this
0x1800259c2  call    ??1CS_CacheStorage_match@CacheStorageTraceLogging@@QEAA@XZ; CacheStorageTraceLogging::CS_CacheStorage_match::~CS_CacheStorage_match(void)
0x1800259c7  nop
0x1800259c8  lea     rcx, [rsp+208h+pAptQualifier]; this
0x1800259cd  call    ??1Activity@HangDetectionWatchDog@@QEAA@XZ; HangDetectionWatchDog::Activity::~Activity(void)
0x1800259d2  nop
0x1800259d3  lea     rcx, [rsp+208h+var_1D8]; this
0x1800259d8  call    ??1AutoSetThreadName@@QEAA@XZ; AutoSetThreadName::~AutoSetThreadName(void)
0x1800259dd  mov     eax, r14d
0x1800259e0  mov     rcx, [rsp+208h+var_38]
0x1800259e8  xor     rcx, rsp; StackCookie
0x1800259eb  call    __security_check_cookie
0x1800259f0  lea     r11, [rsp+208h+var_28]
0x1800259f8  mov     rbx, [r11+30h]
0x1800259fc  mov     rsi, [r11+48h]
0x180025a00  mov     rsp, r11
0x180025a03  pop     r15
0x180025a05  pop     r14
0x180025a07  pop     r13
0x180025a09  pop     r12
0x180025a0b  pop     rdi
0x180025a0c  retn
0x180025a0d  test    rcx, rcx
0x180025a10  jz      loc_1800257FC
0x180025a16  call    cs:__imp__o_terminate
0x180025a1c  nop
0x180025a1d  lea     rcx, dword_180114128
0x180025a24  call    _Init_thread_header
0x180025a29  cmp     cs:dword_180114128, 0FFFFFFFFh
0x180025a30  jnz     loc_18002579C
0x180025a36  mov     edx, 493E0h
0x180025a3b  call    ??0HangDetectionWatchDog@@QEAA@V?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@@Z; HangDetectionWatchDog::HangDetectionWatchDog(std::chrono::duration<__int64,std::ratio<1,1000>>)
0x180025a40  lea     rcx, _HangDetectionWatchDog__s_DefaultInstance____2____dynamic_atexit_destructor_for__s_instance__; void (__cdecl *)()
0x180025a47  call    atexit
0x180025a4c  nop
0x180025a4d  lea     rcx, dword_180114128
0x180025a54  call    _Init_thread_footer
0x180025a59  jmp     loc_18002579C
0x180025a5e  lea     rax, aMta; "MTA"
0x180025a65  jmp     loc_180025723
0x180025a6a  test    ecx, ecx
0x180025a6c  jz      short loc_180025A7C
0x180025a6e  sub     ecx, 2
0x180025a71  jz      short loc_180025A98
0x180025a73  cmp     ecx, 1
0x180025a76  jnz     loc_180025755
0x180025a7c  lea     rax, aAsta; "ASTA"
0x180025a83  lea     rcx, aSta; "STA"
0x180025a8a  cmp     [rsp+208h+pAptQualifier], 6
0x180025a8f  cmovnz  rax, rcx
0x180025a93  jmp     loc_180025723
0x180025a98  mov     ecx, [rsp+208h+pAptQualifier]
0x180025a9c  sub     ecx, 2
0x180025a9f  jz      short loc_180025AE0
0x180025aa1  sub     ecx, 1
0x180025aa4  jz      short loc_180025AD4
0x180025aa6  sub     ecx, 1
0x180025aa9  jz      short loc_180025AC8
0x180025aab  cmp     ecx, 1
0x180025aae  jz      short loc_180025ABC
0x180025ab0  lea     rax, aNa; "NA"
0x180025ab7  jmp     loc_180025723
0x180025abc  lea     rax, aNaOnMainsta; "NA on MAINSTA"
0x180025ac3  jmp     loc_180025723
0x180025ac8  lea     rax, aNaOnMtaImplici; "NA on MTA Implicit"
0x180025acf  jmp     loc_180025723
0x180025ad4  lea     rax, aNaOnSta; "NA on STA"
0x180025adb  jmp     loc_180025723
0x180025ae0  lea     rax, aNaOnMta; "NA on MTA"
0x180025ae7  jmp     loc_180025723
0x180025aec  mov     rcx, rdi; lpWideCharStr
0x180025aef  call    SetThreadNameViaException
0x180025af4  jmp     loc_180025775
0x180025af9  lea     r8, aOnecoreuapInet_4; "onecoreuap\\inetcore\\webplatstorageser"...
0x180025b00  mov     edx, 0E6h; void *
0x180025b05  mov     rcx, r10; this
0x180025b08  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180025b0e  mov     r14d, [rsp+208h+pAptType]
0x180025b13  jmp     loc_1800259C8
```
