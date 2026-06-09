# CRecoMaster::StartStreamExecute(CRecoInst *)

- ea: `0x1800765e8`
- end: `0x180076ca7`
- name: `?StartStreamExecute@CRecoMaster@@AEAAJPEAVCRecoInst@@@Z`
- size: `1727`
- prototype: `__int64 __fastcall(CRecoMaster *__hidden this, struct CRecoInst *)`
- caller_count: `1`
- callee_count: `32`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180076468`

## callees

- `0x180013ec0`
- `0x18002637c`
- `0x180026508`
- `0x1800316e0`
- `0x18003b79c`
- `0x180050b64`
- `0x180050d0c`
- `0x1800510d4`
- `0x180055c44`
- `0x180055c5c`
- `0x1800765e8`
- `0x180076d80`
- `0x1800771cc`
- `0x18007aae4`
- `0x1800b6dc8`
- `0x18012ad44`
- `0x18012ada4`
- `0x18012d708`
- `0x18012d7c8`
- `0x18012e34c`
- `0x1801305ac`
- `0x180133710`
- `0x180133cd4`
- `0x180133d7c`
- `0x180133f04`
- `0x180133f98`
- `0x180134c68`
- `0x180138008`
- `0x180138234`
- `0x18018b93c`
- `0x18027b320`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180076662`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180076662`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800769e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800769e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800769be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800769be`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800769d7`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800769d7`

## string_xrefs

- `0x18007681c`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sr\srrecomaster.cpp`
- `0x180076c22`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sr\srrecomaster.cpp`
- `0x180076646`: `CRecoMaster`
- `0x180076712`: `CRecoMaster`
- `0x1800768dd`: `CRecoMaster`
- `0x180076c7c`: `CRecoMaster`
- `0x180076622`: `StartStreamExecute skipped because reco already started`
- `0x18007698c`: `CRecoMaster: Start availability assurance window loop`
- `0x1800768b5`: `CRecoMaster: failed read HR of 0x%08x after RecognizeStream()`
- `0x180076a88`: `Engine forcibly exited, doing an arbitration update on all reco instances`
- `0x1800769fe`: `CRecoMaster: Availability assurance window ended due to %d`
- `0x180076b98`: `ReaderCloseStream`
- `0x180076830`: `ReaderGetDataAvailableEvent`

## pseudocode

```c
__int64 __fastcall CRecoMaster::StartStreamExecute(CRecoMaster *this, struct CRecoInst *a2)
{
  int CoordinatingInstCtxts; // r14d
  unsigned __int16 *v4; // rax
  CSpEngineProxy *v5; // rcx
  unsigned __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 v8; // r8
  char v9; // al
  char *v10; // r12
  int v11; // eax
  HANDLE *v12; // rbx
  __int64 v13; // r13
  int IsRealTime; // eax
  unsigned int *v15; // rdx
  __int64 *v16; // rcx
  __int64 v17; // r8
  __int64 v18; // rdx
  int v19; // eax
  int v20; // ebx
  int v21; // r8d
  __int64 v22; // rcx
  DWORD v23; // ebx
  __int64 i; // rbx
  __int64 v25; // rax
  __int64 j; // rbx
  __int64 v27; // rax
  enum _SPAUDIOSTATE AudioState; // r13d
  int v29; // edx
  int v30; // ebx
  int v31; // eax
  int v32; // eax
  __int64 v33; // rcx
  int v34; // eax
  CSpEngineProxy *v35; // rcx
  unsigned int StreamNumber; // eax
  __int64 v37; // rdx
  unsigned __int64 v38; // rdx
  unsigned __int16 *v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  int *v42; // [rsp+20h] [rbp-E0h]
  char v43; // [rsp+28h] [rbp-D8h]
  DWORD v44; // [rsp+50h] [rbp-B0h] BYREF
  int v45; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v46; // [rsp+58h] [rbp-A8h] BYREF
  int v47; // [rsp+60h] [rbp-A0h]
  HANDLE Handles[3]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v49; // [rsp+80h] [rbp-80h]
  _DWORD v50[10]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v51; // [rsp+B8h] [rbp-48h]
  int v52; // [rsp+CCh] [rbp-34h]
  wil::details::in1diag3 *retaddr; // [rsp+3648h] [rbp+3548h]
  int v54; // [rsp+3650h] [rbp+3550h] BYREF
  struct CRecoInst *v55; // [rsp+3658h] [rbp+3558h] BYREF
  unsigned int v56; // [rsp+3660h] [rbp+3560h] BYREF
  int v57; // [rsp+3668h] [rbp+3568h] BYREF

  v55 = a2;
  CoordinatingInstCtxts = 0;
  if ( *((_BYTE *)this + 182) )
  {
    v4 = L"StartStreamExecute skipped because reco already started";
LABEL_5:
    RecoInstTraceEx_0(16, v4, v43);
    return (unsigned int)CoordinatingInstCtxts;
  }
  if ( *((_BYTE *)this + 183) )
  {
    v4 = L"StartStreamExecute skipped because m_fPreBuffering is set";
    goto LABEL_5;
  }
  ResetEvent(*((HANDLE *)this + 43));
  v5 = (CSpEngineProxy *)*((_QWORD *)this + 99);
  *((_QWORD *)this + 46) = 0;
  CSpEngineProxy::Set_RecognitionStreamPos(v5, 0);
  CSpEngineProxy::Set_RecognitionStreamTime(*((CSpEngineProxy **)this + 99), v6);
  *((_BYTE *)this + 182) = 1;
  if ( !*((_BYTE *)this + 1980) && CRecoMaster::UseCoordinator(this) && !CRecoMaster::CoordinatorCurrentlyActive(this) )
  {
    std::vector<std::unique_ptr<DGGInfo::SPDGGITEM>>::vector<std::unique_ptr<DGGInfo::SPDGGITEM>>(Handles, v7, v8);
    CoordinatingInstCtxts = CRecoMaster::GetCoordinatingInstCtxts(this, Handles);
    if ( CoordinatingInstCtxts >= 0 )
      CoordinatingInstCtxts = CloudCoordinator::OnLocalAudioStart(*((CloudCoordinator **)this + 114));
    if ( Handles[0] )
      std::_Deallocate<16>(Handles[0], ((char *)Handles[2] - (char *)Handles[0]) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  RecoInstTraceEx_0(16, L"StartStreamExecute Reco starting -- entering RecognizeStream()", v43);
  SpPerfTelemetry::SapiEvent_StartStream_Server();
  v56 = 0;
  if ( !(unsigned int)RemoteControlHelpers::QueryRegistryKey(
                        L"GrammarDumpEnabled",
                        (unsigned __int16 *)4,
                        (unsigned int)&v56,
                        (unsigned __int8 *)4,
                        (unsigned __int64)v40)
    && v56 == 1 )
  {
    (*(void (__fastcall **)(_QWORD, const wchar_t *))(**((_QWORD **)this + 97) + 184LL))(
      *((_QWORD *)this + 97),
      L"sync");
  }
  v9 = *((_BYTE *)this + 1980);
  v10 = (char *)this + 1632;
  v54 = 0;
  if ( v9 )
  {
    v11 = CRecoMaster::StreamRetainedAudio(this);
    v54 = v11;
    v12 = (HANDLE *)((char *)this + 728);
  }
  else
  {
    *((_BYTE *)this + 1981) = 1;
    v13 = *((_QWORD *)this + 205);
    Handles[0] = *(HANDLE *)(*(_QWORD *)this + 40LL);
    IsRealTime = CRecoMaster::ReaderInputIsRealTime(this);
    v46 = -1;
    v15 = (unsigned int *)*((_QWORD *)this + 214);
    v16 = (__int64 *)(*(_QWORD *)v10 + 40LL);
    v47 = IsRealTime;
    v44 = *((_DWORD *)this + 46);
    v17 = *v16;
    v18 = *v15;
    v49 = *((_QWORD *)this + 43);
    v19 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v17 + 112))(v16, v18, &v46);
    v20 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x192E,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\srrecomaster.cpp",
        (const char *)(unsigned int)v19,
        v41);
      CRecoMaster::AoTrace(this, v20, L"ReaderGetDataAvailableEvent");
    }
    v12 = (HANDLE *)((char *)this + 728);
    v54 = ((__int64 (__fastcall *)(CRecoMaster *, char *, _QWORD, _QWORD, __int64, __int64, DWORD, int, __int64))Handles[0])(
            this,
            (char *)this + 1680,
            *((_QWORD *)this + 212),
            *((_QWORD *)this + 91),
            v46,
            v49,
            v44,
            v47,
            v13);
    *((_BYTE *)this + 1981) = 0;
    v11 = v54;
  }
  if ( v11 >= 0 )
  {
    v21 = *((_DWORD *)this + 490);
    if ( v21 < 0 )
    {
      DoTraceMessage(2, "CRecoMaster: failed read HR of 0x%08x after RecognizeStream()", v21);
      v11 = *((_DWORD *)this + 490);
      v54 = v11;
      *((_DWORD *)this + 490) = 0;
    }
  }
  RecoInstTraceEx_0(16, L"StartStreamExecute Reco finished -- leaving RecognizeStream() (hr=0x%08x)", v11);
  if ( v54 < 0 )
  {
    v22 = *(_QWORD *)v10 + 32LL;
    v46 = -1;
    LODWORD(v42) = 0;
    if ( (*(int (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v22 + 40LL))(v22, 0, 0, 0) >= 0 )
    {
      v42 = &v54;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)(*(_QWORD *)v10 + 32LL) + 32LL))(
        *(_QWORD *)v10 + 32LL,
        111,
        v46);
    }
  }
  if ( *((_BYTE *)this + 199) )
  {
    DoTraceMessage(8, "CRecoMaster: Start availability assurance window loop");
    Handles[0] = *v12;
    Handles[1] = *((HANDLE *)this + 45);
    while ( *((_BYTE *)this + 199) )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
      v44 = WaitForMultipleObjects(2u, Handles, 0, *((_DWORD *)this + 243));
      v23 = v44;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
      if ( v23 )
      {
        SPTelemetry::AvailabilityAssuranceWindowEnded<unsigned long &>(&v44);
        DoTraceMessage(8, "CRecoMaster: Availability assurance window ended due to %d", v23);
        *((_BYTE *)this + 199) = 0;
      }
      else
      {
        CRecoMaster::ProcessPendingTasks(this);
      }
    }
    for ( i = *((_QWORD *)this + 102); i; i = *(_QWORD *)(i + 8) )
    {
      memset_0(v50, 0, 0x3580u);
      v50[0] = 80;
      v52 = -1;
      v25 = *(_QWORD *)this;
      v51 = -1;
      (*(void (__fastcall **)(CRecoMaster *, __int64, _DWORD *))(v25 + 264))(this, i, v50);
    }
  }
  if ( *((_BYTE *)this + 198) )
  {
    DoTraceMessage(16, "Engine forcibly exited, doing an arbitration update on all reco instances");
    for ( j = *((_QWORD *)this + 102); j; j = *(_QWORD *)(j + 8) )
    {
      memset_0(v50, 0, 0x3580u);
      v27 = *(_QWORD *)this;
      v52 = -1;
      v50[0] = 80;
      v51 = -1;
      (*(void (__fastcall **)(CRecoMaster *, __int64, _DWORD *))(v27 + 264))(this, j, v50);
    }
  }
  CRecoMaster::CleanUpPairedEvents(this);
  CRecoMaster::UpdateRecoPosEx(this, 0, 0);
  CSpBasicQueue<CSRTask,1,0>::FindAndDeleteAll<CRecoInst *>((char *)this + 736, &v55);
  AudioState = CRecoMaster::ReaderGetAudioState(this);
  CRecoMaster::ReaderLastReadPos(this, v29);
  v57 = 0;
  v45 = 0;
  CRecoMaster::ReaderEndStream(this, &v57, &v45);
  v30 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*(_QWORD *)v10 + 40LL) + 136LL))(
          *(_QWORD *)v10 + 40LL,
          **((unsigned int **)this + 214));
  v31 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*(_QWORD *)v10 + 40LL) + 136LL))(
          *(_QWORD *)v10 + 40LL,
          **((unsigned int **)this + 215));
  CRecoMaster::AoTrace(this, v30, v31, L"ReaderCloseStream");
  *((_QWORD *)this + 32) = 0xFFFFFFFFLL;
  v32 = v54;
  *(_WORD *)((char *)this + 181) = 0;
  if ( v32 < 0 || v57 < 0 || !v45 && AudioState == SPAS_RUN )
  {
    v33 = *((_QWORD *)this + 111);
    CoordinatingInstCtxts = v32;
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 24LL))(v33);
    if ( CRecoMaster::CoordinatorCurrentlyActive(this) )
    {
      v34 = CloudCoordinator::OnSessionCancel(*((_QWORD *)this + 114), 2);
      if ( v34 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xB49,
          (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sr\\srrecomaster.cpp",
          (const char *)(unsigned int)v34,
          (int)v42);
    }
  }
  v35 = (CSpEngineProxy *)*((_QWORD *)this + 99);
  if ( *((_QWORD *)v35 + 12) )
  {
    StreamNumber = CSpEngineProxy::Get_StreamNumber(v35);
    *(_DWORD *)(v37 + 48) = StreamNumber + 1;
  }
  CSpEngineProxy::Set_RecognitionStreamPos(*((CSpEngineProxy **)this + 99), 0);
  CSpEngineProxy::Set_RecognitionStreamTime(*((CSpEngineProxy **)this + 99), v38);
  RecoInstTraceEx_0(16, L"End of StartStreamExecute, hr=0x%08x", CoordinatingInstCtxts);
  return (unsigned int)CoordinatingInstCtxts;
}

```

## disassembly

```asm
0x1800765e8  mov     [rsp-8+arg_8], rdx
0x1800765ed  push    rbp
0x1800765ee  push    rbx
0x1800765ef  push    rdi
0x1800765f0  push    r12
0x1800765f2  push    r13
0x1800765f4  push    r14
0x1800765f6  push    r15
0x1800765f8  lea     rbp, [rsp-3510h]
0x180076600  mov     eax, 3610h
0x180076605  call    _alloca_probe
0x18007660a  sub     rsp, rax
0x18007660d  xor     r13d, r13d
0x180076610  mov     r15, rdx
0x180076613  mov     rdi, rcx
0x180076616  mov     r14d, r13d
0x180076619  cmp     [rcx+0B6h], r13b
0x180076620  jz      short loc_18007662B
0x180076622  lea     rax, aStartstreamexe_0; "StartStreamExecute skipped because reco"...
0x180076629  jmp     short loc_18007663B
0x18007662b  cmp     [rcx+0B7h], r13b
0x180076632  jz      short loc_18007665B
0x180076634  lea     rax, aStartstreamexe; "StartStreamExecute skipped because m_fP"...
0x18007663b  xor     r9d, r9d
0x18007663e  mov     [rsp+3640h+var_3620], rax; unsigned __int16 *
0x180076643  mov     r8, r15
0x180076646  lea     rdx, aCrecomaster; "CRecoMaster"
0x18007664d  lea     ecx, [r9+10h]; int
0x180076651  call    RecoInstTraceEx_0
0x180076656  jmp     loc_180076C91
0x18007665b  mov     rcx, [rcx+158h]; hEvent
0x180076662  call    cs:__imp_ResetEvent
0x180076668  mov     rcx, [rdi+318h]; this
0x18007666f  xor     edx, edx; unsigned __int64
0x180076671  mov     [rdi+170h], r13
0x180076678  call    ?Set_RecognitionStreamPos@CSpEngineProxy@@QEAAX_K@Z; CSpEngineProxy::Set_RecognitionStreamPos(unsigned __int64)
0x18007667d  mov     rcx, [rdi+318h]; this
0x180076684  call    ?Set_RecognitionStreamTime@CSpEngineProxy@@QEAAX_K@Z; CSpEngineProxy::Set_RecognitionStreamTime(unsigned __int64)
0x180076689  mov     byte ptr [rdi+0B6h], 1
0x180076690  mov     al, [rdi+7BCh]
0x180076696  nop
0x180076697  test    al, al
0x180076699  jnz     short loc_180076700
0x18007669b  mov     rcx, rdi; this
0x18007669e  call    ?UseCoordinator@CRecoMaster@@QEAA_NXZ; CRecoMaster::UseCoordinator(void)
0x1800766a3  test    al, al
0x1800766a5  jz      short loc_180076700
0x1800766a7  mov     rcx, rdi; this
0x1800766aa  call    ?CoordinatorCurrentlyActive@CRecoMaster@@QEAA_NXZ; CRecoMaster::CoordinatorCurrentlyActive(void)
0x1800766af  test    al, al
0x1800766b1  jnz     short loc_180076700
0x1800766b3  lea     rcx, [rsp+3640h+Handles]
0x1800766b8  call    ??0?$vector@V?$unique_ptr@USPDGGITEM@DGGInfo@@U?$default_delete@USPDGGITEM@DGGInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@USPDGGITEM@DGGInfo@@U?$default_delete@USPDGGITEM@DGGInfo@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<DGGInfo::SPDGGITEM>>::vector<std::unique_ptr<DGGInfo::SPDGGITEM>>(void)
0x1800766bd  lea     rdx, [rsp+3640h+Handles]
0x1800766c2  mov     rcx, rdi
0x1800766c5  call    ?GetCoordinatingInstCtxts@CRecoMaster@@QEAAJAEAV?$vector@PEAVCRecoInstCtxt@@V?$allocator@PEAVCRecoInstCtxt@@@std@@@std@@@Z; CRecoMaster::GetCoordinatingInstCtxts(std::vector<CRecoInstCtxt *> &)
0x1800766ca  mov     r14d, eax
0x1800766cd  test    eax, eax
0x1800766cf  js      short loc_1800766E5
0x1800766d1  mov     rcx, [rdi+390h]; this
0x1800766d8  lea     rdx, [rsp+3640h+Handles]
0x1800766dd  call    ?OnLocalAudioStart@CloudCoordinator@@QEAAJAEAV?$vector@PEAVCRecoInstCtxt@@V?$allocator@PEAVCRecoInstCtxt@@@std@@@std@@@Z; CloudCoordinator::OnLocalAudioStart(std::vector<CRecoInstCtxt *> &)
0x1800766e2  mov     r14d, eax
0x1800766e5  mov     rcx, [rsp+3640h+Handles]
0x1800766ea  test    rcx, rcx
0x1800766ed  jz      short loc_180076700
0x1800766ef  mov     rdx, [rsp+3640h+var_35C8]
0x1800766f4  sub     rdx, rcx
0x1800766f7  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800766fb  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180076700  xor     r9d, r9d
0x180076703  lea     rax, aStartstreamexe_1; "StartStreamExecute Reco starting -- ent"...
0x18007670a  mov     r8, r15
0x18007670d  mov     [rsp+3640h+var_3620], rax; int
0x180076712  lea     rdx, aCrecomaster; "CRecoMaster"
0x180076719  lea     ecx, [r9+10h]; int
0x18007671d  call    RecoInstTraceEx_0
0x180076722  call    ?SapiEvent_StartStream_Server@SpPerfTelemetry@@SAXXZ; SpPerfTelemetry::SapiEvent_StartStream_Server(void)
0x180076727  mov     eax, 4
0x18007672c  mov     [rbp+3540h+arg_10], r13d
0x180076733  mov     r9d, eax; unsigned __int8 *
0x180076736  lea     r8, [rbp+3540h+arg_10]; unsigned int
0x18007673d  mov     edx, eax; unsigned __int16 *
0x18007673f  lea     rcx, aGrammardumpena; "GrammarDumpEnabled"
0x180076746  call    ?QueryRegistryKey@RemoteControlHelpers@@YAJPEAGKPEAE_K@Z; RemoteControlHelpers::QueryRegistryKey(ushort *,ulong,uchar *,unsigned __int64)
0x18007674b  test    eax, eax
0x18007674d  jnz     short loc_180076775
0x18007674f  cmp     [rbp+3540h+arg_10], 1
0x180076756  jnz     short loc_180076775
0x180076758  mov     rcx, [rdi+308h]
0x18007675f  lea     rdx, aSync; "sync"
0x180076766  mov     rax, [rcx]
0x180076769  mov     rax, [rax+0B8h]
0x180076770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076775  mov     al, [rdi+7BCh]
0x18007677b  lea     r12, [rdi+660h]
0x180076782  mov     [rbp+3540h+arg_0], r13d
0x180076789  nop
0x18007678a  mov     rcx, rdi; this
0x18007678d  test    al, al
0x18007678f  jz      short loc_1800767A8
0x180076791  call    ?StreamRetainedAudio@CRecoMaster@@AEAAJXZ; CRecoMaster::StreamRetainedAudio(void)
0x180076796  mov     [rbp+3540h+arg_0], eax
0x18007679c  lea     rbx, [rdi+2D8h]
0x1800767a3  jmp     loc_1800768A5
0x1800767a8  mov     eax, 1
0x1800767ad  xchg    al, [rdi+7BDh]
0x1800767b3  mov     rax, [rdi]
0x1800767b6  mov     r13, [rdi+668h]
0x1800767bd  mov     rax, [rax+28h]
0x1800767c1  mov     [rsp+3640h+Handles], rax
0x1800767c6  call    ?ReaderInputIsRealTime@CRecoMaster@@AEAAHXZ; CRecoMaster::ReaderInputIsRealTime(void)
0x1800767cb  mov     [rsp+3640h+var_35E8], 0FFFFFFFFFFFFFFFFh
0x1800767d4  mov     rcx, [r12]
0x1800767d8  mov     rdx, [rdi+6B0h]
0x1800767df  add     rcx, 28h ; '('
0x1800767e3  mov     [rsp+3640h+var_35E0], eax
0x1800767e7  mov     eax, [rdi+0B8h]
0x1800767ed  mov     [rsp+3640h+var_35F0], eax
0x1800767f1  mov     r8, [rcx]
0x1800767f4  mov     rax, [rdi+158h]
0x1800767fb  mov     edx, [rdx]
0x1800767fd  mov     [rbp+3540h+var_35C0], rax
0x180076801  mov     rax, [r8+70h]
0x180076805  lea     r8, [rsp+3640h+var_35E8]
0x18007680a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007680f  mov     ebx, eax
0x180076811  test    eax, eax
0x180076813  jns     short loc_180076841
0x180076815  mov     rcx, [rbp+3548h]; this
0x18007681c  lea     r8, aOnecoreuapEndu_215; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180076823  mov     r9d, eax; char *
0x180076826  mov     edx, 192Eh; void *
0x18007682b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076830  lea     r8, aReadergetdataa; "ReaderGetDataAvailableEvent"
0x180076837  mov     edx, ebx; int
0x180076839  mov     rcx, rdi; this
0x18007683c  call    ?AoTrace@CRecoMaster@@AEAAXJPEBGZZ; CRecoMaster::AoTrace(long,ushort const *,...)
0x180076841  mov     rcx, [rsp+3640h+var_35E8]
0x180076846  lea     rdx, [rdi+690h]
0x18007684d  mov     eax, [rsp+3640h+var_35E0]
0x180076851  lea     rbx, [rdi+2D8h]
0x180076858  mov     r8d, [rsp+3640h+var_35F0]
0x18007685d  mov     r9, [rbx]
0x180076860  mov     [rsp+3640h+var_3600], r13
0x180076865  mov     [rsp+3640h+var_3608], eax
0x180076869  mov     rax, [rsp+3640h+Handles]
0x18007686e  mov     dword ptr [rsp+3640h+var_3610], r8d
0x180076873  mov     r8, [rbp+3540h+var_35C0]
0x180076877  mov     qword ptr [rsp+3640h+var_3618], r8
0x18007687c  mov     r8, [rdx+10h]
0x180076880  mov     [rsp+3640h+var_3620], rcx
0x180076885  mov     rcx, rdi
0x180076888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007688d  mov     [rbp+3540h+arg_0], eax
0x180076893  xor     r13d, r13d
0x180076896  mov     eax, r13d
0x180076899  xchg    al, [rdi+7BDh]
0x18007689f  mov     eax, [rbp+3540h+arg_0]
0x1800768a5  test    eax, eax
0x1800768a7  js      short loc_1800768D9
0x1800768a9  mov     r8d, [rdi+7A8h]
0x1800768b0  test    r8d, r8d
0x1800768b3  jns     short loc_1800768D9
0x1800768b5  lea     rdx, aCrecomasterFai; "CRecoMaster: failed read HR of 0x%08x a"...
0x1800768bc  mov     ecx, 2; int
0x1800768c1  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800768c6  mov     eax, [rdi+7A8h]
0x1800768cc  mov     [rbp+3540h+arg_0], eax
0x1800768d2  mov     [rdi+7A8h], r13d
0x1800768d9  mov     dword ptr [rsp+3640h+var_3618], eax; char
0x1800768dd  lea     rdx, aCrecomaster; "CRecoMaster"
0x1800768e4  xor     r9d, r9d
0x1800768e7  lea     rax, aStartstreamexe_2; "StartStreamExecute Reco finished -- lea"...
0x1800768ee  mov     r8, r15
0x1800768f1  mov     [rsp+3640h+var_3620], rax; unsigned __int16 *
0x1800768f6  lea     ecx, [r9+10h]; int
0x1800768fa  call    RecoInstTraceEx_0
0x1800768ff  cmp     [rbp+3540h+arg_0], r13d
0x180076906  jge     short loc_18007697F
0x180076908  mov     rcx, [r12]
0x18007690c  lea     rdx, [rsp+3640h+var_35E8]
0x180076911  mov     [rsp+3640h+var_3610], rdx
0x180076916  add     rcx, 20h ; ' '
0x18007691a  mov     [rsp+3640h+var_35E8], 0FFFFFFFFFFFFFFFFh
0x180076923  xor     r9d, r9d
0x180076926  mov     dword ptr [rsp+3640h+var_3618], 1
0x18007692e  xor     r8d, r8d
0x180076931  xor     edx, edx
0x180076933  mov     dword ptr [rsp+3640h+var_3620], r13d
0x180076938  mov     rax, [rcx]
0x18007693b  mov     rax, [rax+28h]
0x18007693f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076944  test    eax, eax
0x180076946  js      short loc_18007697F
0x180076948  mov     rcx, [r12]
0x18007694c  lea     rdx, [rbp+3540h+arg_0]
0x180076953  mov     r8, [rsp+3640h+var_35E8]
0x180076958  add     rcx, 20h ; ' '
0x18007695c  mov     r9d, 3
0x180076962  mov     dword ptr [rsp+3640h+var_3618], 4
0x18007696a  mov     [rsp+3640h+var_3620], rdx; int
0x18007696f  mov     rax, [rcx]
0x180076972  lea     edx, [r9+6Ch]
0x180076976  mov     rax, [rax+20h]
0x18007697a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007697f  cmp     [rdi+0C7h], r13b
0x180076986  jz      loc_180076A7F
0x18007698c  lea     rdx, aCrecomasterSta_1; "CRecoMaster: Start availability assuran"...
0x180076993  mov     ecx, 8; int
0x180076998  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x18007699d  mov     rax, [rbx]
0x1800769a0  mov     [rsp+3640h+Handles], rax
0x1800769a5  mov     rax, [rdi+168h]
0x1800769ac  mov     [rsp+3640h+var_35D0], rax
0x1800769b1  cmp     [rdi+0C7h], r13b
0x1800769b8  jz      short loc_180076A2C
0x1800769ba  lea     rcx, [rdi+38h]; lpCriticalSection
0x1800769be  call    cs:__imp_LeaveCriticalSection
0x1800769c4  mov     r9d, [rdi+3CCh]; dwMilliseconds
0x1800769cb  lea     rdx, [rsp+3640h+Handles]; lpHandles
0x1800769d0  xor     r8d, r8d; bWaitAll
0x1800769d3  lea     ecx, [r8+2]; nCount
0x1800769d7  call    cs:__imp_WaitForMultipleObjects
0x1800769dd  lea     rcx, [rdi+38h]; lpCriticalSection
0x1800769e1  mov     [rsp+3640h+var_35F0], eax
0x1800769e5  mov     ebx, eax
0x1800769e7  call    cs:__imp_EnterCriticalSection
0x1800769ed  test    ebx, ebx
0x1800769ef  jz      short loc_180076A18
0x1800769f1  lea     rcx, [rsp+3640h+var_35F0]
0x1800769f6  call    ??$AvailabilityAssuranceWindowEnded@AEAK@SPTelemetry@@SAXAEAK@Z; SPTelemetry::AvailabilityAssuranceWindowEnded<ulong &>(ulong &)
0x1800769fb  mov     r8d, ebx
0x1800769fe  lea     rdx, aCrecomasterAva_0; "CRecoMaster: Availability assurance win"...
0x180076a05  mov     ecx, 8; int
0x180076a0a  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x180076a0f  mov     byte ptr [rdi+0C7h], 0
0x180076a16  jmp     short loc_180076A20
0x180076a18  mov     rcx, rdi; this
0x180076a1b  call    ?ProcessPendingTasks@CRecoMaster@@QEAAXXZ; CRecoMaster::ProcessPendingTasks(void)
0x180076a20  cmp     byte ptr [rdi+0C7h], 0
0x180076a27  jnz     short loc_1800769BA
0x180076a29  xor     r13d, r13d
0x180076a2c  mov     rbx, [rdi+330h]
0x180076a33  test    rbx, rbx
0x180076a36  jz      short loc_180076A7F
0x180076a38  xor     edx, edx; Val
0x180076a3a  lea     rcx, [rbp+3540h+var_35B0]; void *
0x180076a3e  mov     r8d, 3580h; Size
0x180076a44  call    memset_0
0x180076a49  mov     eax, 0FFFFFFFFh
0x180076a4e  mov     [rbp+3540h+var_35B0], 50h ; 'P'
0x180076a55  mov     [rbp+3540h+var_3574], eax
0x180076a58  lea     r8, [rbp+3540h+var_35B0]
0x180076a5c  mov     rax, [rdi]
0x180076a5f  mov     rdx, rbx
0x180076a62  mov     rcx, rdi
0x180076a65  mov     [rbp+3540h+var_3588], 0FFFFFFFFFFFFFFFFh
0x180076a6d  mov     rax, [rax+108h]
0x180076a74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076a79  mov     rbx, [rbx+8]
0x180076a7d  jmp     short loc_180076A33
0x180076a7f  cmp     [rdi+0C6h], r13b
0x180076a86  jz      short loc_180076AF5
0x180076a88  lea     rdx, aEngineForcibly; "Engine forcibly exited, doing an arbitr"...
0x180076a8f  mov     ecx, 10h; int
0x180076a94  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x180076a99  mov     rbx, [rdi+330h]
0x180076aa0  mov     r15d, 0FFFFFFFFh
0x180076aa6  test    rbx, rbx
0x180076aa9  jz      short loc_180076AEE
0x180076aab  xor     edx, edx; Val
0x180076aad  lea     rcx, [rbp+3540h+var_35B0]; void *
0x180076ab1  mov     r8d, 3580h; Size
0x180076ab7  call    memset_0
0x180076abc  mov     rax, [rdi]
0x180076abf  lea     r8, [rbp+3540h+var_35B0]
0x180076ac3  mov     rdx, rbx
0x180076ac6  mov     [rbp+3540h+var_3574], r15d
0x180076aca  mov     rcx, rdi
0x180076acd  mov     [rbp+3540h+var_35B0], 50h ; 'P'
0x180076ad4  mov     [rbp+3540h+var_3588], 0FFFFFFFFFFFFFFFFh
0x180076adc  mov     rax, [rax+108h]
0x180076ae3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076ae8  mov     rbx, [rbx+8]
0x180076aec  jmp     short loc_180076AA6
0x180076aee  mov     r15, [rbp+3540h+arg_8]
0x180076af5  mov     rcx, rdi; this
0x180076af8  call    ?CleanUpPairedEvents@CRecoMaster@@QEAAJXZ; CRecoMaster::CleanUpPairedEvents(void)
0x180076afd  xor     r8d, r8d; unsigned __int64
0x180076b00  xor     edx, edx; unsigned __int64
0x180076b02  mov     rcx, rdi; this
0x180076b05  call    ?UpdateRecoPosEx@CRecoMaster@@QEAAJ_K0@Z; CRecoMaster::UpdateRecoPosEx(unsigned __int64,unsigned __int64)
0x180076b0a  lea     rcx, [rdi+2E0h]
0x180076b11  lea     rdx, [rbp+3540h+arg_8]
0x180076b18  call    ??$FindAndDeleteAll@PEAVCRecoInst@@@?$CSpBasicQueue@VCSRTask@@$00$0A@@@QEAAXAEAPEAVCRecoInst@@@Z; CSpBasicQueue<CSRTask,1,0>::FindAndDeleteAll<CRecoInst *>(CRecoInst * &)
0x180076b1d  mov     rcx, rdi; this
0x180076b20  call    ?ReaderGetAudioState@CRecoMaster@@AEAA?AW4_SPAUDIOSTATE@@XZ; CRecoMaster::ReaderGetAudioState(void)
0x180076b25  mov     rcx, rdi; this
0x180076b28  mov     r13d, eax
  ... truncated ...
```
