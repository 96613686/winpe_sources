# CRecoMaster::SendResultToCtxt(SPEVENTENUM,SPRECORESULTINFOEX const *,CRecoInstCtxt *,unsigned __int64,unsigned __int64,bool)

- ea: `0x1800510e8`
- end: `0x180051c39`
- name: `?SendResultToCtxt@CRecoMaster@@QEAAJW4SPEVENTENUM@@PEBUSPRECORESULTINFOEX@@PEAVCRecoInstCtxt@@_K3_N@Z`
- size: `2897`
- prototype: `__int64(CRecoMaster *this, enum SPEVENTENUM, const struct SPRECORESULTINFOEX *, struct CRecoInstCtxt *, unsigned __int64, unsigned __int64, ...)`
- caller_count: `3`
- callee_count: `35`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003af70`
- `0x1801315c4`
- `0x180135100`

## callees

- `0x180013ec0`
- `0x180022044`
- `0x180026508`
- `0x18002895c`
- `0x1800316ac`
- `0x180038d18`
- `0x180038fac`
- `0x180039c98`
- `0x18003a84c`
- `0x18003b79c`
- `0x1800510d4`
- `0x1800510e8`
- `0x180051c40`
- `0x180051cd8`
- `0x1800771cc`
- `0x18007a2dc`
- `0x18007a350`
- `0x18007aae4`
- `0x18007d31c`
- `0x18007d7b1`
- `0x180088688`
- `0x18012b88c`
- `0x18012b920`
- `0x18012c0c4`
- `0x18012cecc`
- `0x18013432c`
- `0x180137398`
- `0x1801377e0`
- `0x180165324`
- `0x18017e4b0`
- `0x18017e790`
- `0x18018b340`
- `0x18018bc98`
- `0x180195864`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800517df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800519e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051ae3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051bb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051bcd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051bfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800517df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800519e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051ae3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051bb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051bcd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051bfc`

## string_xrefs

- `0x180051a8b`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sr\srrecomaster.cpp`
- `0x180051411`: `CRecoMaster`
- `0x1800519c5`: `CRecoMaster`
- `0x1800513fe`: `FAILED getting serialized audio data for RecoResult; requested data from %I64u to %I64u from CAudioOrchestrator::ReaderGetSerializedAudioSize; continuing without audio data...`
- `0x1800512c2`: `CRecoMaster: %S (#%u) reco event %s sent to cloud and %s be intercepted for coordination for inst 0x%08p`
- `0x180051b6a`: `CRecoMaster: Reco (%S) without CloudCoordinator interception`
- `0x180051b32`: `CRecoMaster: OnLocalResultEvent failed with 0x%08x`

## pseudocode

```c
__int64 CRecoMaster::SendResultToCtxt(
        CRecoMaster *this,
        enum SPEVENTENUM a2,
        const struct SPRECORESULTINFOEX *a3,
        struct CRecoInstCtxt *a4,
        unsigned __int64 a5,
        unsigned __int64 a6,
        ...)
{
  struct CRecoInstCtxt *v6; // rsi
  int CUOutputJSONString; // edi
  __int64 v11; // rax
  SPPHRASEALT *aPhraseAlts; // rcx
  ISpPhraseBuilder *pPhrase; // rax
  ULONGLONG v14; // rdx
  __int64 v15; // rbx
  int v16; // r11d
  unsigned int v17; // r10d
  __int64 v18; // r8
  __int64 v19; // rax
  bool v20; // al
  bool v21; // r13
  bool v22; // dl
  int v23; // edx
  bool v24; // al
  bool v25; // bl
  bool v26; // r13
  const wchar_t *v27; // rax
  const char *v28; // rdx
  const char *v29; // r9
  int v30; // eax
  _DWORD **v31; // r12
  unsigned int v32; // ebx
  unsigned __int64 v33; // rax
  _DWORD **v34; // rax
  unsigned int v35; // ebx
  unsigned int v36; // esi
  __int64 v37; // rcx
  unsigned int pvEngineData; // eax
  double v39; // xmm7_8
  char *v40; // r13
  double v41; // xmm1_8
  unsigned __int64 v42; // rcx
  double v43; // xmm0_8
  unsigned __int64 v44; // rcx
  __int64 v45; // rax
  GUID *v46; // rcx
  GUID *v47; // rax
  __int64 v48; // rdx
  double v49; // xmm0_8
  unsigned __int64 v50; // rax
  __int64 v51; // rcx
  float v52; // xmm0_4
  char *v53; // rbx
  unsigned int ullStreamTimeStart; // eax
  unsigned int i; // r13d
  char *v56; // rbx
  __int64 v57; // rcx
  char *v58; // rdi
  size_t v59; // rbx
  char *v60; // rbx
  _DWORD *v61; // rax
  char *v62; // rdi
  size_t v63; // rbx
  const unsigned __int16 *v64; // rax
  size_t v65; // r8
  _QWORD *v66; // rsi
  __int64 v67; // rax
  _QWORD *v68; // rsi
  SPPHRASEALT *v69; // rcx
  ISpPhraseBuilder *v70; // rax
  void *v71; // rcx
  __int64 v72; // rbx
  unsigned int v73; // edx
  int updated; // eax
  unsigned int v75; // ebx
  void *v76; // rcx
  int v78; // eax
  unsigned int v79; // edx
  char v80; // bl
  const wchar_t *v81; // rax
  unsigned int j; // ebx
  void *v83; // rcx
  int v84; // [rsp+28h] [rbp-E0h]
  unsigned int v85[2]; // [rsp+48h] [rbp-C0h] BYREF
  LPVOID v86; // [rsp+50h] [rbp-B8h] BYREF
  void *v87; // [rsp+58h] [rbp-B0h] BYREF
  void *Src; // [rsp+60h] [rbp-A8h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-A0h] BYREF
  std::_Ref_count_base *v90; // [rsp+70h] [rbp-98h] BYREF
  char v91; // [rsp+78h] [rbp-90h]
  __int128 v92; // [rsp+80h] [rbp-88h] BYREF
  void *v93[2]; // [rsp+90h] [rbp-78h] BYREF
  __int128 v94; // [rsp+A0h] [rbp-68h]
  void *v95[2]; // [rsp+B0h] [rbp-58h]
  void *v96; // [rsp+C0h] [rbp-48h]
  LPVOID *p_pv; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v98; // [rsp+D0h] [rbp-38h] BYREF
  char v99; // [rsp+D8h] [rbp-30h]
  _BYTE v100[64]; // [rsp+E8h] [rbp-20h] BYREF
  char v101[112]; // [rsp+128h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D0h] [rbp+C8h]
  __int64 v105; // [rsp+208h] [rbp+100h] BYREF
  va_list va; // [rsp+208h] [rbp+100h]
  va_list va1; // [rsp+210h] [rbp+108h] BYREF

  va_start(va1, a6);
  va_start(va, a6);
  v105 = va_arg(va1, _QWORD);
  v6 = a4;
  CUOutputJSONString = 0;
  v11 = *((_QWORD *)a4 + 3);
  if ( !_bittest64(&v11, (unsigned int)a2) )
    return (unsigned int)CUOutputJSONString;
  LOBYTE(v105) = 0;
  v86 = 0;
  aPhraseAlts = a3->aPhraseAlts;
  pPhrase = aPhraseAlts->pPhrase;
  pv = &v86;
  v90 = 0;
  v91 = 1;
  CUOutputJSONString = ((__int64 (__fastcall *)(SPPHRASEALT *, std::_Ref_count_base **))pPhrase[3].lpVtbl)(
                         aPhraseAlts,
                         &v90);
  wil::details::out_param_t<wistd::unique_ptr<SPPHRASE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<SPPHRASE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&pv);
  if ( CUOutputJSONString >= 0 )
  {
    v14 = *((_QWORD *)v86 + 3);
    v15 = *((unsigned int *)v86 + 8);
    if ( v14 && (v14 < a3->ullStreamPosEnd || (SPGRAMMARHANDLE)(v14 + v15) > a3->hGrammar) )
    {
      CUOutputJSONString = -2147200947;
    }
    else
    {
      v16 = 0;
      v17 = 0;
      do
      {
        if ( v17 >= *((_DWORD *)v86 + 16) )
          break;
        v18 = 56LL * v17;
        v19 = *((_QWORD *)v86 + 13);
        if ( *(_DWORD *)(v18 + v19 + 8) < v16 )
          CUOutputJSONString = -2147200947;
        v16 = *(_DWORD *)(v18 + v19 + 8) + *(_DWORD *)(v18 + v19 + 12);
        ++v17;
      }
      while ( CUOutputJSONString >= 0 );
      if ( v16 > (unsigned int)v15 )
        CUOutputJSONString = -2147200947;
    }
    v20 = CRecoMaster::CoordinatorCurrentlyActive(this);
    v21 = v20;
    v22 = (a3->eResultType & 0x28) == 0
       || v20 && CloudCoordinator::IsAwaitingHybridResult(*((CloudCoordinator **)this + 114));
    v23 = (a2 == SPEI_RECOGNITION || a2 == SPEI_FALSE_RECOGNITION) && v22;
    v24 = v21 || (*((_QWORD *)v6 + 3) & *((_QWORD *)this + 200)) == *((_QWORD *)this + 200);
    v25 = *((_DWORD *)this + 42) && v23 && v24;
    v26 = v21 && v23;
    LOBYTE(v105) = v26;
    v27 = (const wchar_t *)SpEventIdToString((unsigned int)a2);
    DoTraceMessage(
      16,
      "CRecoMaster: %S (#%u) reco event %s sent to cloud and %s be intercepted for coordination for inst 0x%08p",
      v27,
      a2,
      v29,
      v28,
      *((const void **)v6 + 1));
    if ( v25 )
    {
      *((_DWORD *)this + 239) = *((_DWORD *)this + 238);
      (*(void (__fastcall **)(_QWORD, LPVOID))(**((_QWORD **)this + 111) + 16LL))(*((_QWORD *)this + 111), v86);
    }
  }
  v85[1] = 0;
  Src = 0;
  *(_OWORD *)v93 = 0;
  v94 = 0;
  *(_OWORD *)v95 = 0;
  v96 = 0;
  v30 = LODWORD(a3->hGrammar) - LODWORD(a3->ullStreamPosEnd);
  LODWORD(pv) = v30;
  if ( CUOutputJSONString < 0 )
    goto LABEL_40;
  if ( v30 && !a3->fHypothesis && *((_DWORD *)v6 + 10) )
  {
    CUOutputJSONString = (*(__int64 (__fastcall **)(__int64, _QWORD, ULONGLONG, SPGRAMMARHANDLE, unsigned int *))(*(_QWORD *)(*((_QWORD *)this + 204) + 40LL) + 176LL))(
                           *((_QWORD *)this + 204) + 40LL,
                           **((unsigned int **)this + 214),
                           a3->ullStreamPosEnd,
                           a3->hGrammar,
                           &v85[1]);
    if ( (unsigned int)(CUOutputJSONString + 2147200871) <= 1 )
    {
      RecoInstTraceEx_0(
        4,
        L"FAILED getting serialized audio data for RecoResult; requested data from %I64u to %I64u from CAudioOrchestrator:"
         ":ReaderGetSerializedAudioSize; continuing without audio data...",
        a3->ullStreamPosEnd);
      v85[1] = 0;
    }
    else if ( CUOutputJSONString < 0 )
    {
LABEL_40:
      v31 = 0;
      v32 = 0;
      v85[0] = 0;
      goto LABEL_54;
    }
  }
  CUOutputJSONString = ((__int64 (__fastcall *)(SPPHRASEALT *, void **))a3->aPhraseAlts->SPRECORESULTINFO::pPhrase[4].lpVtbl)(
                         a3->aPhraseAlts,
                         &Src);
  if ( CUOutputJSONString < 0 )
    goto LABEL_40;
  *((_QWORD *)Src + 2) = a5;
  v31 = 0;
  v32 = 0;
  v85[0] = 0;
  if ( LODWORD(a3->ullStreamTimeStart) )
  {
    v33 = 8LL * LODWORD(a3->ullStreamTimeStart);
    if ( !is_mul_ok(LODWORD(a3->ullStreamTimeStart), 8u) )
      v33 = -1;
    v34 = (_DWORD **)operator new[](v33, (const struct std::nothrow_t *)&std::nothrow);
    v31 = v34;
    if ( v34 )
    {
      memset_0(v34, 0, 8LL * LODWORD(a3->ullStreamTimeStart));
      v35 = 0;
      v36 = v85[0];
      while ( v35 < LODWORD(a3->ullStreamTimeStart) )
      {
        v37 = *(_QWORD *)(*(_QWORD *)&a3->ulNumAlts + 40LL * v35);
        CUOutputJSONString = (*(__int64 (__fastcall **)(__int64, _DWORD **))(*(_QWORD *)v37 + 32LL))(v37, &v31[v35]);
        if ( CUOutputJSONString < 0 )
          break;
        v36 += ((*(_DWORD *)(*(_QWORD *)&a3->ulNumAlts + 40LL * v35 + 32) + 7) & 0xFFFFFFF8)
             + ((*v31[v35] + 7) & 0xFFFFFFF8)
             + 16;
        ++v35;
      }
      v85[0] = v36;
      v6 = a4;
      v32 = v85[0];
    }
    else
    {
      CUOutputJSONString = -2147024882;
    }
  }
LABEL_54:
  v92 = 0;
  std::shared_ptr<Bing::Speech::IConnection>::reset(&v92);
  v85[0] = 0;
  if ( CUOutputJSONString < 0 )
    goto LABEL_119;
  CUOutputJSONString = CRecoMaster::GetCUOutputJSONString(this, (struct Halsey::swstring *)&v92, v85);
  if ( CUOutputJSONString < 0 )
    goto LABEL_119;
  pvEngineData = 0;
  if ( !a3->fHypothesis )
    pvEngineData = (unsigned int)a3->pvEngineData;
  CUOutputJSONString = CResultHeader::InitFromSizes(
                         (CResultHeader *)v93,
                         *(_DWORD *)Src,
                         v32,
                         v85[1],
                         pvEngineData,
                         0,
                         v85[0]);
  if ( CUOutputJSONString < 0 )
    goto LABEL_119;
  v39 = CRecoMaster::ReaderStreamPositionToSeconds(this, a3->ullStreamPosEnd);
  v40 = (char *)v93[0];
  v41 = v39 * 10000000.0;
  v42 = 0;
  if ( v39 * 10000000.0 >= 9.223372036854776e18 )
  {
    v41 = v41 - 9.223372036854776e18;
    if ( v41 < 9.223372036854776e18 )
      v42 = 0x8000000000000000uLL;
  }
  *((_QWORD *)v93[0] + 17) = v42 + (unsigned int)(int)v41;
  v43 = CRecoMaster::ReaderStreamPositionToSeconds(this, (unsigned __int64)a3->hGrammar - a3->ullStreamPosEnd)
      * 10000000.0;
  v44 = 0;
  if ( v43 >= 9.223372036854776e18 )
  {
    v43 = v43 - 9.223372036854776e18;
    if ( v43 < 9.223372036854776e18 )
      v44 = 0x8000000000000000uLL;
  }
  *((_QWORD *)v40 + 15) = v44 + (unsigned int)(int)v43;
  *((_QWORD *)v40 + 14) = *((_QWORD *)v40 + 17) + *((_QWORD *)this + 226);
  *((_DWORD *)v40 + 32) = *((_DWORD *)this + 456) - (int)(v39 * -1000.0);
  v45 = *(_QWORD *)(*((_QWORD *)this + 99) + 96LL);
  v46 = &GUID_NULL;
  if ( v45 )
    v47 = (GUID *)(v45 + 56);
  else
    v47 = &GUID_NULL;
  *(GUID *)(v40 + 8) = *v47;
  v48 = *(_QWORD *)(*((_QWORD *)this + 99) + 96LL);
  if ( v48 )
    v46 = (GUID *)(v48 + 72);
  *(GUID *)(v40 + 24) = *v46;
  *((_DWORD *)v40 + 10) = CSpEngineProxy::Get_StreamNumber(*((CSpEngineProxy **)this + 99));
  *((_QWORD *)v40 + 6) = a3->ullStreamPosEnd;
  *((_QWORD *)v40 + 7) = a3->hGrammar;
  v49 = CRecoMaster::ReaderStreamPositionToSeconds(this, 1u) * 10000000.0;
  v50 = 0;
  if ( v49 >= 9.223372036854776e18 )
  {
    v49 = v49 - 9.223372036854776e18;
    if ( v49 < 9.223372036854776e18 )
      v50 = 0x8000000000000000uLL;
  }
  v51 = v50 + (unsigned int)(int)v49;
  if ( v51 < 0 )
    v52 = (float)(v51 & 1 | (unsigned int)((unsigned __int64)v51 >> 1))
        + (float)(v51 & 1 | (unsigned int)((unsigned __int64)v51 >> 1));
  else
    v52 = (float)(int)v51;
  *((float *)v40 + 25) = v52;
  *((_DWORD *)v40 + 26) = *((_DWORD *)this + 439);
  memcpy_0(v93[1], Src, *(unsigned int *)Src);
  if ( v32 )
  {
    v53 = (char *)v94;
    LODWORD(v87) = 0;
    ullStreamTimeStart = a3->ullStreamTimeStart;
    if ( ullStreamTimeStart )
    {
      for ( i = (unsigned int)v87; i < ullStreamTimeStart; ++i )
      {
        *(_DWORD *)v53 = *(_DWORD *)(*(_QWORD *)&a3->ulNumAlts + 40LL * i + 8);
        *((_DWORD *)v53 + 1) = *(_DWORD *)(*(_QWORD *)&a3->ulNumAlts + 40LL * i + 12);
        *((_DWORD *)v53 + 2) = *(_DWORD *)(*(_QWORD *)&a3->ulNumAlts + 40LL * i + 16);
        *((_DWORD *)v53 + 3) = *(_DWORD *)(*(_QWORD *)&a3->ulNumAlts + 40LL * i + 32);
        v56 = v53 + 16;
        memcpy_0(
          v56,
          *(const void **)(*(_QWORD *)&a3->ulNumAlts + 40LL * i + 24),
          *(unsigned int *)(*(_QWORD *)&a3->ulNumAlts + 40LL * i + 32));
        v57 = *(unsigned int *)(*(_QWORD *)&a3->ulNumAlts + 40LL * i + 32);
        v58 = &v56[v57];
        v59 = -(int)v57 & 7;
        memset_0(v58, 0, v59);
        v60 = &v58[v59];
        memcpy_0(v60, v31[i], (unsigned int)*v31[i]);
        v61 = v31[i];
        v62 = &v60[*v61];
        v63 = -*v61 & 7;
        memset_0(v62, 0, v63);
        v53 = &v62[v63];
        CoTaskMemFree(v31[i]);
        v31[i] = 0;
        ullStreamTimeStart = a3->ullStreamTimeStart;
      }
      v40 = (char *)v93[0];
      v6 = a4;
    }
    *((_DWORD *)v40 + 20) = ullStreamTimeStart;
  }
  if ( v85[1] )
  {
    LODWORD(v87) = 0;
    CUOutputJSONString = (*(__int64 (__fastcall **)(__int64, _QWORD, ULONGLONG, SPGRAMMARHANDLE, _QWORD, unsigned int, void **))(*(_QWORD *)(*((_QWORD *)this + 204) + 40LL) + 184LL))(
                           *((_QWORD *)this + 204) + 40LL,
                           **((unsigned int **)this + 214),
                           a3->ullStreamPosEnd,
                           a3->hGrammar,
                           *((_QWORD *)&v94 + 1),
                           v85[1],
                           &v87);
    if ( CUOutputJSONString < 0 )
      goto LABEL_119;
  }
  if ( v95[0] )
    memcpy_0(v95[0], a3->pPhrase, LODWORD(a3->pvEngineData));
  CUOutputJSONString = CResultHeader::StreamOffsetsToTime((CResultHeader *)v93);
  if ( CUOutputJSONString < 0 )
    goto LABEL_119;
  if ( (_DWORD)pv )
  {
    CUOutputJSONString = CRecoMaster::AddAudioOrchestratorAnchorPair(
                           this,
                           a2,
                           a3->ullStreamPosEnd,
                           (unsigned __int64)a3->hGrammar,
                           a3,
                           *((struct CRecoInst **)v6 + 1));
    if ( CUOutputJSONString < 0 )
      goto LABEL_119;
  }
  if ( (_QWORD)v92 )
  {
    v64 = Halsey::swstring::c_strsafe((Halsey::swstring *)&v92);
    memcpy_0(v96, v64, v65);
  }
  std::unordered_map<CRecoInst *,CRecoInstState>::unordered_map<CRecoInst *,CRecoInstState>(v100);
  v66 = operator new(0x80u, (const struct std::nothrow_t *)&std::nothrow);
  pv = v66;
  if ( v66 )
  {
    v67 = std::unordered_map<CRecoInst *,CRecoInstState>::unordered_map<CRecoInst *,CRecoInstState>(v101, v100);
    v68 = CSREvent::CSREvent(v66, v67, 0);
  }
  else
  {
    v68 = 0;
  }
  if ( !v68 )
  {
    CUOutputJSONString = -2147024882;
    goto LABEL_118;
  }
  pv = 0;
  v69 = a3->aPhraseAlts;
  v70 = v69->pPhrase;
  p_pv = &pv;
  v98 = 0;
  v99 = 1;
  ((void (__fastcall *)(SPPHRASEALT *, __int64, __int64, __int64, __int64 *, _QWORD))v70[5].lpVtbl)(
    v69,
    0xFFFFFFFFLL,
    0xFFFFFFFFLL,
    1,
    &v98,
    0);
  wil::details::out_param_t<wistd::unique_ptr<SPPHRASE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<SPPHRASE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  v87 = v93[0];
  RecoInstTraceEx_0(16, L"Adding recognition to event queue: eEventid: %u, end time:%I64u, text %s", a2);
  v71 = pv;
  pv = 0;
  if ( v71 )
    CoTaskMemFree(v71);
  v72 = *((_QWORD *)a4 + 6);
  v93[0] = 0;
  CResultHeader::Clear((CResultHeader *)v93);
  v68[14] = v87;
  *((_DWORD *)v68 + 26) = a2;
  v68[15] = a6;
  v68[1] = v72;
  if ( !(_BYTE)v105 )
    goto LABEL_116;
  std::shared_ptr<Bing::Speech::IJsonValue>::shared_ptr<Bing::Speech::IJsonValue>(&pv, *((_QWORD *)this + 114) + 16LL);
  if ( !pv )
    goto LABEL_109;
  v73 = *((_DWORD *)this + 239);
  if ( !v73 )
    v73 = *((_DWORD *)this + 238);
  updated = UnifiedSession::UpdateEnginesMediaTime(
              (UnifiedSession *)pv,
              v73,
              *((_DWORD *)this + 240),
              *((_DWORD *)this + 236));
  v75 = updated;
  if ( updated >= 0 )
  {
LABEL_109:
    LOBYTE(v105) = 0;
    v78 = CloudCoordinator::OnLocalResultEvent(
            *((CloudCoordinator **)this + 114),
            (struct CSREvent *)v68,
            a4,
            (bool *)va);
    if ( v78 < 0 )
    {
      v80 = 1;
      DoTraceMessage(4, "CRecoMaster: OnLocalResultEvent failed with 0x%08x", v78);
    }
    else
    {
      v80 = 0;
      if ( (_BYTE)v105 )
        CSREvent::`scalar deleting destructor'((CSREvent *)v68, v79);
    }
    if ( v90 )
      std::_Ref_count_base::_Decref(v90);
    if ( v80 )
    {
LABEL_116:
      v81 = (const wchar_t *)SpEventIdToString((unsigned int)a2);
      DoTraceMessage(16, "CRecoMaster: Reco (%S) without CloudCoordinator interception", v81);
      CSpProducerConsumerIOCompletionQueue<CSREvent,1>::InsertTail((char *)this + 464, v68);
    }
LABEL_118:
    std::_Hash<std::_Umap_traits<CRecoInst *,CRecoInstState,std::_Uhash_compare<CRecoInst *,std::hash<CRecoInst *>,std::equal_to<CRecoInst *>>,std::allocator<std::pair<CRecoInst * const,CRecoInstState>>,0>>::~_Hash<std::_Umap_traits<CRecoInst *,CRecoInstState,std::_Uhash_compare<CRecoInst *,std::hash<CRecoInst *>,std::equal_to<CRecoInst *>>,std::allocator<std::pair<CRecoInst * const,CRecoInstState>>,0>>(v100);
    if ( CUOutputJSONString >= 0 )
    {
LABEL_122:
      operator delete(v31);
      CoTaskMemFree(Src);
      if ( *((_QWORD *)&v92 + 1) )
        std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&v92 + 1));
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v93);
      v83 = v86;
      v86 = 0;
      if ( v83 )
        CoTaskMemFree(v83);
      if ( CUOutputJSONString < 0 )
        SPTelemetry::SrSendResultToCtxtFailed(CUOutputJSONString);
      return (unsigned int)CUOutputJSONString;
    }
LABEL_119:
    if ( v31 )
    {
      for ( j = 0; j < LODWORD(a3->ullStreamTimeStart); ++j )
        CoTaskMemFree(v31[j]);
    }
    goto LABEL_122;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xD32,
    (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\srrecomaster.cpp",
    (const char *)(unsigned int)updated,
    v84);
  if ( v90 )
    std::_Ref_count_base::_Decref(v90);
  std::_Hash<std::_Umap_traits<CRecoInst *,CRecoInstState,std::_Uhash_compare<CRecoInst *,std::hash<CRecoInst *>,std::equal_to<CRecoInst *>>,std::allocator<std::pair<CRecoInst * const,CRecoInstState>>,0>>::~_Hash<std::_Umap_traits<CRecoInst *,CRecoInstState,std::_Uhash_compare<CRecoInst *,std::hash<CRecoInst *>,std::equal_to<CRecoInst *>>,std::allocator<std::pair<CRecoInst * const,CRecoInstState>>,0>>(v100);
  if ( *((_QWORD *)&v92 + 1) )
    std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&v92 + 1));
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v93);
  v76 = v86;
  v86 = 0;
  if ( v76 )
    CoTaskMemFree(v76);
  return v75;
}

```

## disassembly

```asm
0x1800510e8  mov     rax, rsp
0x1800510eb  mov     [rax+8], rbx
0x1800510ef  mov     [rax+20h], r9
0x1800510f3  mov     [rax+10h], edx
0x1800510f6  push    rbp
0x1800510f7  push    rsi
0x1800510f8  push    rdi
0x1800510f9  push    r12
0x1800510fb  push    r13
0x1800510fd  push    r14
0x1800510ff  push    r15
0x180051101  lea     rbp, [rax-0C8h]
0x180051108  sub     rsp, 190h
0x18005110f  movaps  xmmword ptr [rax-48h], xmm6
0x180051113  movaps  xmmword ptr [rax-58h], xmm7
0x180051117  movaps  xmmword ptr [rax-68h], xmm8
0x18005111c  mov     rsi, r9
0x18005111f  mov     r14, r8
0x180051122  mov     r12d, edx
0x180051125  mov     r15, rcx
0x180051128  xor     edi, edi
0x18005112a  mov     rax, [r9+18h]
0x18005112e  bt      rax, r12
0x180051132  jnb     loc_180051C0D
0x180051138  xor     r13b, r13b
0x18005113b  mov     byte ptr [rbp+0C0h+arg_30], r13b
0x180051142  xor     r13d, r13d
0x180051145  mov     [rsp+1C0h+var_178], r13
0x18005114a  mov     rcx, [r8+40h]
0x18005114e  mov     rax, [rcx]
0x180051151  lea     rdx, [rsp+1C0h+var_178]
0x180051156  mov     [rsp+1C0h+pv], rdx
0x18005115b  mov     [rsp+1C0h+var_158], r13
0x180051160  mov     byte ptr [rsp+1C0h+var_150], 1
0x180051165  lea     rdx, [rsp+1C0h+var_158]
0x18005116a  mov     rax, [rax+18h]
0x18005116e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051173  mov     edi, eax
0x180051175  lea     rcx, [rsp+1C0h+pv]
0x18005117a  call    ??1?$out_param_t@V?$unique_ptr@USPPHRASE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SPPHRASE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<SPPHRASE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18005117f  test    edi, edi
0x180051181  js      loc_1800512FC
0x180051187  mov     rcx, [rsp+1C0h+var_178]
0x18005118c  mov     rdx, [rcx+18h]
0x180051190  mov     ebx, [rcx+20h]
0x180051193  test    rdx, rdx
0x180051196  jz      short loc_1800511AF
0x180051198  cmp     rdx, [r14+18h]
0x18005119c  jb      short loc_1800511A8
0x18005119e  lea     rax, [rdx+rbx]
0x1800511a2  cmp     rax, [r14+20h]
0x1800511a6  jbe     short loc_1800511AF
0x1800511a8  mov     edi, 8004504Dh
0x1800511ad  jmp     short loc_1800511ED
0x1800511af  mov     r11d, r13d
0x1800511b2  mov     r10d, r13d
0x1800511b5  mov     r9d, 8004504Dh
0x1800511bb  cmp     r10d, [rcx+40h]
0x1800511bf  jnb     short loc_1800511E6
0x1800511c1  mov     eax, r10d
0x1800511c4  imul    r8, rax, 38h ; '8'
0x1800511c8  mov     rax, [rcx+68h]
0x1800511cc  cmp     [r8+rax+8], r11d
0x1800511d1  cmovl   edi, r9d
0x1800511d5  mov     r11d, [r8+rax+0Ch]
0x1800511da  add     r11d, [r8+rax+8]
0x1800511df  inc     r10d
0x1800511e2  test    edi, edi
0x1800511e4  jns     short loc_1800511BB
0x1800511e6  cmp     r11d, ebx
0x1800511e9  cmova   edi, r9d
0x1800511ed  mov     rcx, r15; this
0x1800511f0  call    ?CoordinatorCurrentlyActive@CRecoMaster@@QEAA_NXZ; CRecoMaster::CoordinatorCurrentlyActive(void)
0x1800511f5  mov     r13b, al
0x1800511f8  xor     ebx, ebx
0x1800511fa  cmp     r12d, 2Bh ; '+'
0x1800511fe  setz    bl
0x180051201  xor     ecx, ecx
0x180051203  cmp     r12d, 26h ; '&'
0x180051207  setz    cl
0x18005120a  or      ebx, ecx
0x18005120c  test    byte ptr [r14+4], 28h
0x180051211  jz      short loc_18005122B
0x180051213  test    al, al
0x180051215  jz      short loc_180051227
0x180051217  mov     rcx, [r15+390h]; this
0x18005121e  call    ?IsAwaitingHybridResult@CloudCoordinator@@QEAA_NXZ; CloudCoordinator::IsAwaitingHybridResult(void)
0x180051223  test    al, al
0x180051225  jnz     short loc_18005122B
0x180051227  xor     edx, edx
0x180051229  jmp     short loc_180051230
0x18005122b  mov     edx, 1
0x180051230  and     edx, ebx
0x180051232  test    r13b, r13b
0x180051235  jnz     short loc_18005124E
0x180051237  mov     rcx, [r15+640h]
0x18005123e  mov     rax, rcx
0x180051241  and     rax, [rsi+18h]
0x180051245  cmp     rax, rcx
0x180051248  jz      short loc_18005124E
0x18005124a  xor     al, al
0x18005124c  jmp     short loc_180051250
0x18005124e  mov     al, 1
0x180051250  cmp     dword ptr [r15+0A8h], 0
0x180051258  jz      short loc_180051266
0x18005125a  test    edx, edx
0x18005125c  jz      short loc_180051266
0x18005125e  test    al, al
0x180051260  jz      short loc_180051266
0x180051262  mov     bl, 1
0x180051264  jmp     short loc_180051268
0x180051266  xor     bl, bl
0x180051268  test    r13b, r13b
0x18005126b  jz      short loc_180051276
0x18005126d  test    edx, edx
0x18005126f  jz      short loc_180051276
0x180051271  mov     r13b, 1
0x180051274  jmp     short loc_180051279
0x180051276  xor     r13b, r13b
0x180051279  mov     byte ptr [rbp+0C0h+arg_30], r13b
0x180051280  lea     rax, aWillNotBe; "will NOT be"
0x180051287  lea     r9, aWillBe; "WILL be"
0x18005128e  mov     rdx, r9
0x180051291  test    r13b, r13b
0x180051294  cmovz   rdx, rax
0x180051298  xor     r13d, r13d
0x18005129b  test    bl, bl
0x18005129d  cmovz   r9, rax
0x1800512a1  mov     ecx, r12d
0x1800512a4  call    SpEventIdToString
0x1800512a9  mov     r8, rax
0x1800512ac  mov     rax, [rsi+8]
0x1800512b0  mov     qword ptr [rsp+1C0h+var_190], rax
0x1800512b5  mov     [rsp+1C0h+var_198], rdx
0x1800512ba  mov     [rsp+1C0h+var_1A0], r9
0x1800512bf  mov     r9d, r12d
0x1800512c2  lea     rdx, aCrecomasterSUR; "CRecoMaster: %S (#%u) reco event %s sen"...
0x1800512c9  lea     ecx, [r13+10h]; int
0x1800512cd  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800512d2  test    bl, bl
0x1800512d4  jz      short loc_1800512FC
0x1800512d6  mov     eax, [r15+3B8h]
0x1800512dd  mov     [r15+3BCh], eax
0x1800512e4  mov     rcx, [r15+378h]
0x1800512eb  mov     rax, [rcx]
0x1800512ee  mov     rdx, [rsp+1C0h+var_178]
0x1800512f3  mov     rax, [rax+10h]
0x1800512f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800512fc  mov     [rsp+1C0h+var_180+4], r13d
0x180051301  mov     [rsp+1C0h+Src], r13
0x180051306  xorps   xmm0, xmm0
0x180051309  movdqu  xmmword ptr [rbp+0C0h+var_138], xmm0
0x18005130e  xorps   xmm1, xmm1
0x180051311  movdqu  [rbp+0C0h+var_128], xmm1
0x180051316  movdqu  xmmword ptr [rbp+0C0h+var_118], xmm0
0x18005131b  mov     [rbp+0C0h+var_108], r13
0x18005131f  mov     eax, [r14+20h]
0x180051323  sub     eax, [r14+18h]
0x180051327  mov     dword ptr [rsp+1C0h+pv], eax
0x18005132b  test    edi, edi
0x18005132d  js      short loc_180051394
0x18005132f  test    eax, eax
0x180051331  jz      loc_180051426
0x180051337  cmp     [r14+8], r13d
0x18005133b  jnz     loc_180051426
0x180051341  cmp     [rsi+28h], r13d
0x180051345  jz      loc_180051426
0x18005134b  mov     rcx, [r15+660h]
0x180051352  add     rcx, 28h ; '('
0x180051356  mov     rax, [rcx]
0x180051359  mov     rdx, [r15+6B0h]
0x180051360  lea     r8, [rsp+1C0h+var_180+4]
0x180051365  mov     [rsp+1C0h+var_1A0], r8
0x18005136a  mov     r9, [r14+20h]
0x18005136e  mov     r8, [r14+18h]
0x180051372  mov     edx, [rdx]
0x180051374  mov     rax, [rax+0B0h]
0x18005137b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051380  mov     edi, eax
0x180051382  add     eax, 7FFBAF67h
0x180051387  cmp     eax, 1
0x18005138a  jbe     short loc_1800513EC
0x18005138c  test    edi, edi
0x18005138e  jns     loc_180051426
0x180051394  mov     r12, r13
0x180051397  mov     ebx, r13d
0x18005139a  mov     [rsp+1C0h+var_180], ebx
0x18005139e  test    edi, edi
0x1800513a0  js      loc_180051504
0x1800513a6  cmp     [r14+50h], r13d
0x1800513aa  jz      loc_180051504
0x1800513b0  mov     ecx, [r14+50h]
0x1800513b4  mov     eax, 8
0x1800513b9  mul     rcx
0x1800513bc  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800513c3  cmovb   rax, rcx
0x1800513c7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800513ce  mov     rcx, rax; unsigned __int64
0x1800513d1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800513d6  mov     r12, rax
0x1800513d9  test    rax, rax
0x1800513dc  jnz     loc_180051464
0x1800513e2  mov     edi, 8007000Eh
0x1800513e7  jmp     loc_180051504
0x1800513ec  mov     rax, [r14+20h]
0x1800513f0  mov     qword ptr [rsp+1C0h+var_190], rax
0x1800513f5  mov     rax, [r14+18h]
0x1800513f9  mov     [rsp+1C0h+var_198], rax; char
0x1800513fe  lea     rax, aFailedGettingS; "FAILED getting serialized audio data fo"...
0x180051405  mov     [rsp+1C0h+var_1A0], rax; unsigned __int16 *
0x18005140a  xor     r9d, r9d
0x18005140d  mov     r8, [rsi+8]
0x180051411  lea     rdx, aCrecomaster; "CRecoMaster"
0x180051418  lea     ecx, [r9+4]; int
0x18005141c  call    RecoInstTraceEx_0
0x180051421  mov     [rsp+1C0h+var_180+4], r13d
0x180051426  mov     rcx, [r14+40h]
0x18005142a  mov     rax, [rcx]
0x18005142d  lea     rdx, [rsp+1C0h+Src]
0x180051432  mov     rax, [rax+20h]
0x180051436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005143b  mov     edi, eax
0x18005143d  test    eax, eax
0x18005143f  js      loc_180051394
0x180051445  mov     rcx, [rbp+0C0h+arg_20]
0x18005144c  mov     rax, [rsp+1C0h+Src]
0x180051451  mov     [rax+10h], rcx
0x180051455  mov     r12, r13
0x180051458  mov     ebx, r13d
0x18005145b  mov     [rsp+1C0h+var_180], ebx
0x18005145f  jmp     loc_1800513A6
0x180051464  mov     r8d, [r14+50h]
0x180051468  shl     r8, 3; Size
0x18005146c  xor     edx, edx; Val
0x18005146e  mov     rcx, r12; void *
0x180051471  call    memset_0
0x180051476  mov     ebx, r13d
0x180051479  mov     esi, [rsp+1C0h+var_180]
0x18005147d  cmp     ebx, [r14+50h]
0x180051481  jnb     short loc_1800514F5
0x180051483  test    edi, edi
0x180051485  js      short loc_1800514EF
0x180051487  mov     r13d, ebx
0x18005148a  lea     rcx, ds:0[r13*4]
0x180051492  add     rcx, r13
0x180051495  mov     rax, [r14+48h]
0x180051499  mov     rcx, [rax+rcx*8]
0x18005149d  mov     rax, [rcx]
0x1800514a0  lea     rdx, [r12+r13*8]
0x1800514a4  mov     rax, [rax+20h]
0x1800514a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800514ad  mov     edi, eax
0x1800514af  test    eax, eax
0x1800514b1  js      short loc_1800514EC
0x1800514b3  mov     rax, [r12+r13*8]
0x1800514b7  mov     edx, [rax]
0x1800514b9  add     edx, 7
0x1800514bc  mov     r8d, 0FFFFFFF8h
0x1800514c2  and     edx, r8d
0x1800514c5  mov     rax, [r14+48h]
0x1800514c9  lea     rcx, ds:0[r13*4]
0x1800514d1  add     rcx, r13
0x1800514d4  mov     ecx, [rax+rcx*8+20h]
0x1800514d8  add     ecx, 7
0x1800514db  and     ecx, r8d
0x1800514de  add     ecx, esi
0x1800514e0  lea     esi, [rdx+10h]
0x1800514e3  add     esi, ecx
0x1800514e5  inc     ebx
0x1800514e7  xor     r13d, r13d
0x1800514ea  jmp     short loc_18005147D
0x1800514ec  xor     r13d, r13d
0x1800514ef  inc     ebx
0x1800514f1  test    edi, edi
0x1800514f3  jns     short loc_18005147D
0x1800514f5  mov     [rsp+1C0h+var_180], esi
0x1800514f9  mov     rsi, [rbp+0C0h+arg_18]
0x180051500  mov     ebx, [rsp+1C0h+var_180]
0x180051504  xorps   xmm0, xmm0
0x180051507  movdqu  [rsp+1C0h+var_150+8], xmm0
0x18005150d  lea     rcx, [rsp+1C0h+var_150+8]
0x180051512  call    ?reset@?$shared_ptr@VIConnection@Speech@Bing@@@std@@QEAAXXZ; std::shared_ptr<Bing::Speech::IConnection>::reset(void)
0x180051517  nop
0x180051518  mov     [rsp+1C0h+var_180], r13d
0x18005151d  test    edi, edi
0x18005151f  js      loc_180051B9E
0x180051525  lea     r8, [rsp+1C0h+var_180]; unsigned int *
0x18005152a  lea     rdx, [rsp+1C0h+var_150+8]; struct Halsey::swstring *
0x18005152f  mov     rcx, r15; this
0x180051532  call    ?GetCUOutputJSONString@CRecoMaster@@QEBAJAEAVswstring@Halsey@@AEAK@Z; CRecoMaster::GetCUOutputJSONString(Halsey::swstring &,ulong &)
0x180051537  mov     edi, eax
0x180051539  test    eax, eax
0x18005153b  js      loc_180051B9E
0x180051541  cmp     [r14+8], r13d
0x180051545  mov     eax, r13d
0x180051548  jnz     short loc_18005154E
0x18005154a  mov     eax, [r14+30h]
0x18005154e  mov     ecx, [rsp+1C0h+var_180]
0x180051552  mov     [rsp+1C0h+var_190], ecx; unsigned int
0x180051556  mov     dword ptr [rsp+1C0h+var_198], r13d; unsigned int
  ... truncated ...
```
