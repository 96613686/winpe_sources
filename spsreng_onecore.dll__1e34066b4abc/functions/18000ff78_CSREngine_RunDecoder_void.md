# CSREngine::RunDecoder(void)

- ea: `0x18000ff78`
- end: `0x18001072a`
- name: `?RunDecoder@CSREngine@@AEAAJXZ`
- size: `1970`
- prototype: `__int64 __fastcall(CSREngine *__hidden this)`
- caller_count: `2`
- callee_count: `28`
- tags: `authz_impersonation`

## callers

- `0x18000f380`
- `0x1800131c4`

## callees

- `0x1800056fc`
- `0x180006dbc`
- `0x18000ded8`
- `0x18000f058`
- `0x18000ff78`
- `0x180010824`
- `0x180010cd4`
- `0x180013e90`
- `0x18001481c`
- `0x18004bf60`
- `0x180069aa8`
- `0x180069c20`
- `0x18006c244`
- `0x180070668`
- `0x180070784`
- `0x1800708e0`
- `0x180070cf4`
- `0x180072cc4`
- `0x180072d5c`
- `0x1800752f4`
- `0x18007e7f8`
- `0x18007f684`
- `0x180080f0c`
- `0x1800820a0`
- `0x18009b090`
- `0x1800a5394`
- `0x1800af344`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000ffd7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000ffd7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010711`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010711`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18000ffb1`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18000fffa`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18000ffb1`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18000fffa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000ffa8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000fff1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180010006`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001064b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800106db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000ffa8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000fff1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180010006`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001064b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800106db`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180010011`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180010657`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800106e7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180010011`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180010657`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800106e7`

## pseudocode

```c
__int64 __fastcall CSREngine::RunDecoder(CSREngine *this)
{
  __int64 v2; // rcx
  int AM; // esi
  HANDLE CurrentThread; // rax
  int ThreadPriority; // r12d
  void *v6; // rcx
  HANDLE v7; // rax
  int v8; // ebx
  HANDLE v9; // rax
  _BYTE *v10; // rcx
  bool v11; // r15
  CFrontEndWrapper *v12; // rcx
  int v13; // ecx
  bool v14; // dl
  __int64 v15; // rax
  CAptVTLN *v16; // rcx
  char i; // bl
  struct CMllr *MllrObject; // rax
  CDecoder *v19; // rcx
  unsigned int j; // ebx
  CSLM **Elem; // rax
  struct CSLM *v22; // r14
  __int64 v23; // rcx
  __int64 v24; // rax
  char v25; // bp
  char v26; // r14
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  char v31; // bl
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rax
  __int64 v39; // rcx
  CRecentReco *v40; // rbx
  unsigned int v41; // edx
  CRecentReco *v42; // rcx
  __int64 v43; // rcx
  CDecoder *v44; // rcx
  __int64 v45; // rcx
  int v46; // ebx
  int v47; // r14d
  __int64 v48; // rbp
  __int64 v49; // r15
  HANDLE v50; // rax
  int v51; // eax
  __int64 v52; // rcx
  HANDLE v53; // rax
  __int64 v54; // rax
  int v56; // [rsp+80h] [rbp+8h] BYREF

  v2 = *((_QWORD *)this + 17);
  AM = 0;
  v56 = 0;
  CDecoder::search_reset(*(CDecoder **)(v2 + 64));
  CurrentThread = GetCurrentThread();
  ThreadPriority = GetThreadPriority(CurrentThread);
  do
  {
    v6 = *(void **)(*(_QWORD *)(*((_QWORD *)this + 17) + 64LL) + 2296LL);
    if ( v6 && !WaitForSingleObject(v6, 0) )
      break;
    if ( *((_DWORD *)this + 233) != 0x7FFFFFFF )
    {
      v7 = GetCurrentThread();
      GetThreadPriority(v7);
      v8 = *((_DWORD *)this + 233);
      v9 = GetCurrentThread();
      SetThreadPriority(v9, v8);
    }
    v10 = *(_BYTE **)(*((_QWORD *)this + 17) + 64LL);
    v11 = v10[2548] && v10[2550] && (*((_DWORD *)this + 217) || v10[2551]);
    v12 = (CFrontEndWrapper *)*((_QWORD *)this + 101);
    if ( v11 )
    {
      v13 = CFrontEndWrapper::SetAudioRecord(v12, 1);
      v14 = 0;
      if ( v13 >= 0 )
        v14 = v11;
      v11 = v14;
    }
    else
    {
      CFrontEndWrapper::SetAudioRecord(v12, 0);
    }
    if ( *((_DWORD *)this + 217) )
    {
      v15 = *((_QWORD *)this + 17);
      *((_DWORD *)this + 217) = 0;
      *((_DWORD *)this + 221) = -1;
      v16 = *(CAptVTLN **)(v15 + 160);
      if ( *((_BYTE *)v16 + 178) )
      {
        CAptVTLN::Reset(v16, 1);
        v15 = *((_QWORD *)this + 17);
      }
      if ( *((_DWORD *)this + 219) == 1
        && *((_BYTE *)this + 786)
        && *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v15 + 144) + 16LL) + 354LL) )
      {
        CSREngine::PurgeAdaptationData(this);
        CMllr_imp::ClearAdaptationData(*(CMllr_imp **)(*(_QWORD *)(*((_QWORD *)this + 17) + 144LL) + 16LL));
        for ( i = 0; i < *(_DWORD *)(*((_QWORD *)this + 87) + 28LL); ++i )
        {
          MllrObject = CAMCollection::GetMllrObject((CAMCollection *)(*((_QWORD *)this + 17) + 96LL), i);
          CMllr_imp::ClearAdaptationData(*((CMllr_imp **)MllrObject + 2));
        }
        CDecoder::ResetFeatureTransform(*(CDecoder **)(*((_QWORD *)this + 17) + 64LL));
      }
      v19 = *(CDecoder **)(*((_QWORD *)this + 17) + 64LL);
      if ( !*((_BYTE *)v19 + 2595) && !*((_BYTE *)v19 + 2594) )
        CDecoder::search_restart_autodetect(v19);
    }
    if ( AM < 0 )
      break;
    AM = 1;
    for ( j = 0; j < *((_DWORD *)this + 84); ++j )
    {
      Elem = (CSLM **)CList::GetElem((CSREngine *)((char *)this + 336), j);
      v22 = *Elem;
      if ( *((_DWORD *)*Elem + 8) == 4 )
      {
        AM = CSLM::SynchronizeAdaptation(*Elem);
        if ( !AM )
          AM = CDecoder::FindSLMInfo(*(CDecoder **)(*((_QWORD *)this + 17) + 64LL), v22) == 0;
        if ( AM < 0 )
          break;
      }
    }
    if ( AM < 0 )
      break;
    v23 = *((_QWORD *)this + 17);
    v24 = *(_QWORD *)(v23 + 80);
    if ( !*(_BYTE *)(v24 + 24) )
    {
      v25 = 0;
      if ( *(_DWORD *)(v24 + 120) )
        goto LABEL_120;
    }
    v25 = 1;
LABEL_120:
    AM = CDecoder::search(
           *(CDecoder **)(v23 + 64),
           &v56,
           *((_DWORD *)this + 216),
           *((_DWORD *)this + 215),
           *(_DWORD *)(v23 + 792));
    if ( AM == 282709 )
    {
      if ( *((_BYTE *)this + 800) )
        break;
    }
    v26 = 0;
    CRecoLatencyMeter::Start(
      *(CRecoLatencyMeter **)(*((_QWORD *)this + 17) + 72LL),
      *((struct CRecentReco **)this + 118));
    v27 = *((_QWORD *)this + 12);
    *((_DWORD *)this + 216) = 0;
    if ( v27 && (*(_BYTE *)(*(_QWORD *)(v27 + 56) + 1LL) & 8) != 0 )
      McTemplateMofU0(v27 + 8, Generate2ndPassFeaturesStartEvent, Generate2ndPassFeaturesId);
    if ( v11 )
    {
      CFrontEndWrapper::SetAudioRecord(*((CFrontEndWrapper **)this + 101), 0);
      if ( AM >= 0 )
      {
        if ( *((_QWORD *)this + 118) )
        {
          v28 = *((_QWORD *)this + 17);
          if ( *(_BYTE *)(*(_QWORD *)(v28 + 64) + 2568LL) )
          {
            if ( CRecoLatencyMeter::LowRecoLatency(*(CRecoLatencyMeter **)(v28 + 72))
              && !(unsigned int)CDecoder::Generate2ndPassFeatures(*(CDecoder **)(*((_QWORD *)this + 17) + 64LL)) )
            {
              v26 = 1;
            }
          }
        }
      }
      if ( *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 17) + 64LL) + 2568LL) )
        CAudioBuffer::FoundSpeech(*(CAudioBuffer **)(*((_QWORD *)this + 101) + 24LL), 0);
    }
    v29 = *((_QWORD *)this + 12);
    if ( v29 && (*(_BYTE *)(*(_QWORD *)(v29 + 56) + 1LL) & 8) != 0 )
      McTemplateMofU0(v29 + 8, Generate2ndPassFeaturesEndEvent, Generate2ndPassFeaturesId);
    v30 = *((_QWORD *)this + 12);
    if ( v30 && (*(_BYTE *)(*(_QWORD *)(v30 + 56) + 1LL) & 0x20) != 0 )
      McTemplateMofU0(v30 + 8, AdaptationStartEvent, AdaptationId);
    if ( AM >= 0 )
    {
      if ( !*((_DWORD *)this + 220) )
        goto LABEL_119;
      v31 = *((_BYTE *)this + 792);
      AM = CAcousticModel::LoadAM(*((CAcousticModel **)this + 87), 0);
      if ( AM >= 0 )
      {
        if ( *((_DWORD *)this + 218) != 1
          && !*((_BYTE *)this + 787)
          && (v31
           || *((_BYTE *)this + 792)
           || *((_BYTE *)this + 786)
           && CRecoLatencyMeter::LowRecoLatency(*(CRecoLatencyMeter **)(*((_QWORD *)this + 17) + 72LL))) )
        {
          CSREngine::StartCollectingAdaptationData(this);
        }
      }
      else
      {
        v56 = 1;
      }
      v32 = *((_QWORD *)this + 17);
      *((_DWORD *)this + 220) = 0;
      *((_DWORD *)this + 221) = -1;
      CAutoDetect::ForceBaseAM(*(CAutoDetect **)(v32 + 80));
      if ( AM >= 0 )
      {
LABEL_119:
        if ( v25 )
        {
          v33 = *((_QWORD *)this + 17);
          if ( !*(_BYTE *)(*(_QWORD *)(v33 + 80) + 24LL) )
          {
            if ( *((_DWORD *)this + 219) == 1
              && *((_BYTE *)this + 786)
              && *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v33 + 144) + 16LL) + 354LL)
              && CRecoLatencyMeter::LowRecoLatency(*(CRecoLatencyMeter **)(v33 + 72)) )
            {
              CSREngine::StartCollectingAdaptationData(this);
            }
            if ( *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 17) + 80LL) + 96LL) )
              v26 = 1;
          }
        }
      }
    }
    v34 = *(_QWORD *)(*((_QWORD *)this + 17) + 64LL);
    if ( *(_BYTE *)(v34 + 3252) )
    {
      if ( !*(_BYTE *)(v34 + 2549) || (v35 = *(_QWORD *)(v34 + 3256), !*(_BYTE *)(v35 + 28)) && !*(_BYTE *)(v35 + 29) )
        v26 = 1;
    }
    v36 = *((_QWORD *)this + 12);
    if ( v36 && (*(_BYTE *)(*(_QWORD *)(v36 + 56) + 1LL) & 0x20) != 0 )
      McTemplateMofU0(v36 + 8, AdaptationEndEvent, AdaptationId);
    if ( AM >= 0 )
    {
      if ( *((_QWORD *)this + 118) )
      {
        v37 = *((_QWORD *)this + 17);
        v38 = *(_QWORD *)(v37 + 64);
        if ( *(_BYTE *)(v38 + 2568) )
        {
          if ( *(_BYTE *)(v38 + 2548) && v26 && CRecoLatencyMeter::LowRecoLatency(*(CRecoLatencyMeter **)(v37 + 72)) )
          {
            v39 = *((_QWORD *)this + 17);
            v40 = (CRecentReco *)*((_QWORD *)this + 118);
            *((_QWORD *)this + 118) = 0;
            if ( (int)CDecoder::search_2nd_pass(*(CDecoder **)(v39 + 64)) >= 0 && *((_QWORD *)this + 118) )
            {
              if ( v40 )
                CRecentReco::`scalar deleting destructor'(v40, v41);
            }
            else
            {
              v42 = (CRecentReco *)*((_QWORD *)this + 118);
              if ( v42 )
                CRecentReco::`scalar deleting destructor'(v42, v41);
              *((_QWORD *)this + 118) = v40;
            }
          }
        }
      }
    }
    v43 = *((_QWORD *)this + 17);
    if ( *(_BYTE *)(v43 + 516) )
      CDecoder::search_continue(
        *(CDecoder **)(v43 + 64),
        &v56,
        *((_DWORD *)this + 216),
        *((_DWORD *)this + 215),
        *(_DWORD *)(v43 + 792));
    v44 = *(CDecoder **)(*((_QWORD *)this + 17) + 64LL);
    *((_DWORD *)v44 + 1601) += *((_DWORD *)v44 + 750);
    *((_DWORD *)v44 + 750) = 0;
    *((_DWORD *)v44 + 1847) = 1;
    CDecoder::prune_ngt_tr_cache(v44, -1);
    AM = 0;
    if ( !*((_BYTE *)this + 800)
      && *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 17) + 64LL) + 557LL)
      && (int)CSREngine::SendRecognition(this) < 0 )
    {
      CSREngine::SendFalseRecognition(this, 0);
    }
    v45 = *(_QWORD *)(*((_QWORD *)this + 17) + 64LL);
    v46 = *(_DWORD *)(v45 + 6404);
    v47 = *(_DWORD *)(v45 + 3000);
    v48 = *(_QWORD *)(v45 + 6416);
    v49 = *(_QWORD *)(v45 + 6408);
    v50 = GetCurrentThread();
    SetThreadPriority(v50, ThreadPriority);
    if ( !v56 && !*((_BYTE *)this + 800) )
    {
      AM = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 21) + 72LL))(
             *((_QWORD *)this + 21),
             v49 + v48 * (unsigned int)(v47 + v46));
      if ( AM == 1 )
        break;
    }
    v51 = v56;
    if ( *((_BYTE *)this + 801) )
      v51 = 1;
    v56 = v51;
  }
  while ( !v51 );
  v52 = *((_QWORD *)this + 17);
  *((_BYTE *)this + 801) = 0;
  CDecoder::search_reset(*(CDecoder **)(v52 + 64));
  v53 = GetCurrentThread();
  SetThreadPriority(v53, ThreadPriority);
  if ( AM < 0 )
  {
    v54 = *((_QWORD *)this + 17);
    *((_DWORD *)this + 199) = 1;
    *((_DWORD *)this + 222) = 0;
    SetEvent(*(HANDLE *)(*(_QWORD *)(v54 + 64) + 2296LL));
  }
  return (unsigned int)AM;
}

```

## disassembly

```asm
0x18000ff78  mov     rax, rsp
0x18000ff7b  push    rbx
0x18000ff7c  push    rbp
0x18000ff7d  push    rsi
0x18000ff7e  push    rdi
0x18000ff7f  push    r12
0x18000ff81  push    r13
0x18000ff83  push    r14
0x18000ff85  push    r15
0x18000ff87  sub     rsp, 38h
0x18000ff8b  mov     rdi, rcx
0x18000ff8e  xor     r13d, r13d
0x18000ff91  mov     rcx, [rcx+88h]
0x18000ff98  mov     esi, r13d
0x18000ff9b  mov     [rax+8], r13d
0x18000ff9f  mov     rcx, [rcx+40h]; this
0x18000ffa3  call    ?search_reset@CDecoder@@QEAAXXZ; CDecoder::search_reset(void)
0x18000ffa8  call    cs:__imp_GetCurrentThread
0x18000ffae  mov     rcx, rax; hThread
0x18000ffb1  call    cs:__imp_GetThreadPriority
0x18000ffb7  mov     r12d, eax
0x18000ffba  lea     r14d, [r13+1]
0x18000ffbe  mov     rax, [rdi+88h]
0x18000ffc5  mov     rcx, [rax+40h]
0x18000ffc9  mov     rcx, [rcx+8F8h]; hHandle
0x18000ffd0  test    rcx, rcx
0x18000ffd3  jz      short loc_18000FFE5
0x18000ffd5  xor     edx, edx; dwMilliseconds
0x18000ffd7  call    cs:__imp_WaitForSingleObject
0x18000ffdd  test    eax, eax
0x18000ffdf  jz      loc_1800106C4
0x18000ffe5  cmp     dword ptr [rdi+3A4h], 7FFFFFFFh
0x18000ffef  jz      short loc_180010017
0x18000fff1  call    cs:__imp_GetCurrentThread
0x18000fff7  mov     rcx, rax; hThread
0x18000fffa  call    cs:__imp_GetThreadPriority
0x180010000  mov     ebx, [rdi+3A4h]
0x180010006  call    cs:__imp_GetCurrentThread
0x18001000c  mov     rcx, rax; hThread
0x18001000f  mov     edx, ebx; nPriority
0x180010011  call    cs:__imp_SetThreadPriority
0x180010017  mov     rax, [rdi+88h]
0x18001001e  mov     rcx, [rax+40h]
0x180010022  cmp     [rcx+9F4h], r13b
0x180010029  jz      short loc_18001004B
0x18001002b  cmp     [rcx+9F6h], r13b
0x180010032  jz      short loc_18001004B
0x180010034  cmp     [rdi+364h], r13d
0x18001003b  jnz     short loc_180010046
0x18001003d  cmp     [rcx+9F7h], r13b
0x180010044  jz      short loc_18001004B
0x180010046  mov     r15b, r14b
0x180010049  jmp     short loc_18001004E
0x18001004b  mov     r15b, r13b
0x18001004e  mov     rcx, [rdi+328h]; this
0x180010055  test    r15b, r15b
0x180010058  jz      short loc_180010075
0x18001005a  mov     dl, r14b; bool
0x18001005d  call    ?SetAudioRecord@CFrontEndWrapper@@QEAAJ_N@Z; CFrontEndWrapper::SetAudioRecord(bool)
0x180010062  mov     ecx, eax
0x180010064  mov     edx, r13d
0x180010067  movzx   eax, r15b
0x18001006b  test    ecx, ecx
0x18001006d  cmovns  edx, eax
0x180010070  mov     r15b, dl
0x180010073  jmp     short loc_18001007C
0x180010075  xor     edx, edx; bool
0x180010077  call    ?SetAudioRecord@CFrontEndWrapper@@QEAAJ_N@Z; CFrontEndWrapper::SetAudioRecord(bool)
0x18001007c  cmp     [rdi+364h], r13d
0x180010083  jz      loc_18001017D
0x180010089  mov     rax, [rdi+88h]
0x180010090  mov     [rdi+364h], r13d
0x180010097  mov     dword ptr [rdi+374h], 0FFFFFFFFh
0x1800100a1  mov     rcx, [rax+0A0h]; this
0x1800100a8  cmp     [rcx+0B2h], r13b
0x1800100af  jz      short loc_1800100C0
0x1800100b1  mov     dl, r14b; bool
0x1800100b4  call    ?Reset@CAptVTLN@@QEAAJ_N@Z; CAptVTLN::Reset(bool)
0x1800100b9  mov     rax, [rdi+88h]
0x1800100c0  cmp     [rdi+36Ch], r14d
0x1800100c7  jnz     loc_18001015B
0x1800100cd  cmp     [rdi+312h], r13b
0x1800100d4  jz      loc_18001015B
0x1800100da  mov     rax, [rax+90h]
0x1800100e1  mov     rcx, [rax+10h]
0x1800100e5  cmp     [rcx+162h], r13b
0x1800100ec  jz      short loc_18001015B
0x1800100ee  mov     rcx, rdi; this
0x1800100f1  call    ?PurgeAdaptationData@CSREngine@@AEAAXXZ; CSREngine::PurgeAdaptationData(void)
0x1800100f6  mov     rax, [rdi+88h]
0x1800100fd  mov     rcx, [rax+90h]
0x180010104  mov     rcx, [rcx+10h]; this
0x180010108  call    ?ClearAdaptationData@CMllr_imp@@QEAAXXZ; CMllr_imp::ClearAdaptationData(void)
0x18001010d  mov     rax, [rdi+2B8h]
0x180010114  mov     bl, r13b
0x180010117  cmp     [rax+1Ch], r13d
0x18001011b  jle     short loc_18001014B
0x18001011d  mov     rcx, [rdi+88h]
0x180010124  add     rcx, 60h ; '`'; this
0x180010128  movsx   edx, bl; int
0x18001012b  call    ?GetMllrObject@CAMCollection@@QEAAPEAVCMllr@@H@Z; CAMCollection::GetMllrObject(int)
0x180010130  mov     rcx, [rax+10h]; this
0x180010134  call    ?ClearAdaptationData@CMllr_imp@@QEAAXXZ; CMllr_imp::ClearAdaptationData(void)
0x180010139  mov     rcx, [rdi+2B8h]
0x180010140  add     bl, r14b
0x180010143  movsx   eax, bl
0x180010146  cmp     eax, [rcx+1Ch]
0x180010149  jl      short loc_18001011D
0x18001014b  mov     rcx, [rdi+88h]
0x180010152  mov     rcx, [rcx+40h]; this
0x180010156  call    ?ResetFeatureTransform@CDecoder@@AEAAXXZ; CDecoder::ResetFeatureTransform(void)
0x18001015b  mov     rax, [rdi+88h]
0x180010162  mov     rcx, [rax+40h]; this
0x180010166  cmp     [rcx+0A23h], r13b
0x18001016d  jnz     short loc_18001017D
0x18001016f  cmp     [rcx+0A22h], r13b
0x180010176  jnz     short loc_18001017D
0x180010178  call    ?search_restart_autodetect@CDecoder@@QEAAJXZ; CDecoder::search_restart_autodetect(void)
0x18001017d  test    esi, esi
0x18001017f  js      loc_1800106C4
0x180010185  lea     rbp, [rdi+150h]
0x18001018c  mov     esi, r14d
0x18001018f  mov     ebx, r13d
0x180010192  cmp     [rbp+0], r13d
0x180010196  jbe     short loc_1800101F1
0x180010198  mov     edx, ebx; unsigned int
0x18001019a  mov     rcx, rbp; this
0x18001019d  call    ?GetElem@CList@@QEAAPEAXK@Z; CList::GetElem(ulong)
0x1800101a2  mov     r14, [rax]
0x1800101a5  cmp     dword ptr [r14+20h], 4
0x1800101aa  jnz     short loc_1800101DB
0x1800101ac  mov     rcx, r14; this
0x1800101af  call    ?SynchronizeAdaptation@CSLM@@QEAAJXZ; CSLM::SynchronizeAdaptation(void)
0x1800101b4  mov     esi, eax
0x1800101b6  test    eax, eax
0x1800101b8  jnz     short loc_1800101D7
0x1800101ba  mov     rcx, [rdi+88h]
0x1800101c1  mov     rdx, r14; struct CSLM *
0x1800101c4  mov     rcx, [rcx+40h]; this
0x1800101c8  call    ?FindSLMInfo@CDecoder@@AEAAPEAULMINFO@@PEAVCSLM@@@Z; CDecoder::FindSLMInfo(CSLM *)
0x1800101cd  test    rax, rax
0x1800101d0  mov     esi, r13d
0x1800101d3  setz    sil
0x1800101d7  test    esi, esi
0x1800101d9  js      short loc_1800101EB
0x1800101db  mov     r14d, 1
0x1800101e1  add     ebx, r14d
0x1800101e4  cmp     ebx, [rbp+0]
0x1800101e7  jb      short loc_180010198
0x1800101e9  jmp     short loc_1800101F1
0x1800101eb  mov     r14d, 1
0x1800101f1  test    esi, esi
0x1800101f3  js      loc_1800106C4
0x1800101f9  mov     rcx, [rdi+88h]
0x180010200  mov     rax, [rcx+50h]
0x180010204  cmp     [rax+18h], r13b
0x180010208  jnz     short loc_180010213
0x18001020a  mov     bpl, r13b
0x18001020d  cmp     [rax+78h], r13d
0x180010211  jnz     short loc_180010216
0x180010213  mov     bpl, r14b
0x180010216  mov     eax, [rcx+318h]
0x18001021c  lea     rdx, [rsp+78h+arg_0]; int *
0x180010224  mov     rcx, [rcx+40h]; this
0x180010228  mov     r9d, [rdi+35Ch]; int
0x18001022f  mov     r8d, [rdi+360h]; int
0x180010236  mov     [rsp+78h+var_58], eax; unsigned int
0x18001023a  call    ?search@CDecoder@@QEAAJPEAHHHI@Z; CDecoder::search(int *,int,int,uint)
0x18001023f  mov     esi, eax
0x180010241  cmp     eax, 45055h
0x180010246  jnz     short loc_180010255
0x180010248  cmp     [rdi+320h], r13b
0x18001024f  jnz     loc_1800106C4
0x180010255  mov     rcx, [rdi+88h]
0x18001025c  mov     rdx, [rdi+3B0h]; struct CRecentReco *
0x180010263  movzx   r14d, r13b
0x180010267  mov     rcx, [rcx+48h]; this
0x18001026b  call    ?Start@CRecoLatencyMeter@@QEAAXPEAVCRecentReco@@@Z; CRecoLatencyMeter::Start(CRecentReco *)
0x180010270  mov     rcx, [rdi+60h]
0x180010274  mov     [rdi+360h], r13d
0x18001027b  test    rcx, rcx
0x18001027e  jz      short loc_1800102A1
0x180010280  mov     rax, [rcx+38h]
0x180010284  test    byte ptr [rax+1], 8
0x180010288  jz      short loc_1800102A1
0x18001028a  add     rcx, 8
0x18001028e  lea     r8, Generate2ndPassFeaturesId
0x180010295  lea     rdx, Generate2ndPassFeaturesStartEvent
0x18001029c  call    McTemplateMofU0
0x1800102a1  test    r15b, r15b
0x1800102a4  jz      loc_180010332
0x1800102aa  mov     rcx, [rdi+328h]; this
0x1800102b1  xor     edx, edx; bool
0x1800102b3  call    ?SetAudioRecord@CFrontEndWrapper@@QEAAJ_N@Z; CFrontEndWrapper::SetAudioRecord(bool)
0x1800102b8  test    esi, esi
0x1800102ba  js      short loc_180010304
0x1800102bc  cmp     [rdi+3B0h], r13
0x1800102c3  jz      short loc_180010304
0x1800102c5  mov     rcx, [rdi+88h]
0x1800102cc  mov     rax, [rcx+40h]
0x1800102d0  cmp     [rax+0A08h], r13b
0x1800102d7  jz      short loc_180010304
0x1800102d9  mov     rcx, [rcx+48h]; this
0x1800102dd  call    ?LowRecoLatency@CRecoLatencyMeter@@QEAA_NXZ; CRecoLatencyMeter::LowRecoLatency(void)
0x1800102e2  test    al, al
0x1800102e4  jz      short loc_180010304
0x1800102e6  mov     rcx, [rdi+88h]
0x1800102ed  mov     rcx, [rcx+40h]; this
0x1800102f1  call    ?Generate2ndPassFeatures@CDecoder@@QEAAJXZ; CDecoder::Generate2ndPassFeatures(void)
0x1800102f6  test    eax, eax
0x1800102f8  mov     r15d, 1
0x1800102fe  cmovz   r14d, r15d
0x180010302  jmp     short loc_18001030A
0x180010304  mov     r15d, 1
0x18001030a  mov     rax, [rdi+88h]
0x180010311  mov     rcx, [rax+40h]
0x180010315  cmp     [rcx+0A08h], r13b
0x18001031c  jz      short loc_180010338
0x18001031e  mov     rcx, [rdi+328h]
0x180010325  xor     edx, edx; bool
0x180010327  mov     rcx, [rcx+18h]; this
0x18001032b  call    ?FoundSpeech@CAudioBuffer@@QEAAJ_N@Z; CAudioBuffer::FoundSpeech(bool)
0x180010330  jmp     short loc_180010338
0x180010332  mov     r15d, 1
0x180010338  mov     rcx, [rdi+60h]
0x18001033c  test    rcx, rcx
0x18001033f  jz      short loc_180010362
0x180010341  mov     rax, [rcx+38h]
0x180010345  test    byte ptr [rax+1], 8
0x180010349  jz      short loc_180010362
0x18001034b  add     rcx, 8
0x18001034f  lea     r8, Generate2ndPassFeaturesId
0x180010356  lea     rdx, Generate2ndPassFeaturesEndEvent
0x18001035d  call    McTemplateMofU0
0x180010362  mov     rcx, [rdi+60h]
0x180010366  test    rcx, rcx
0x180010369  jz      short loc_18001038C
0x18001036b  mov     rax, [rcx+38h]
0x18001036f  test    byte ptr [rax+1], 20h
0x180010373  jz      short loc_18001038C
0x180010375  add     rcx, 8
0x180010379  lea     r8, AdaptationId
0x180010380  lea     rdx, AdaptationStartEvent
0x180010387  call    McTemplateMofU0
0x18001038c  test    esi, esi
0x18001038e  js      loc_180010496
0x180010394  cmp     [rdi+370h], r13d
0x18001039b  jz      loc_18001042E
0x1800103a1  mov     rcx, [rdi+2B8h]; this
0x1800103a8  xor     edx, edx; bool
0x1800103aa  mov     bl, [rdi+318h]
0x1800103b0  call    ?LoadAM@CAcousticModel@@QEAAJ_N@Z; CAcousticModel::LoadAM(bool)
0x1800103b5  mov     esi, eax
0x1800103b7  test    eax, eax
0x1800103b9  jns     short loc_1800103C5
0x1800103bb  mov     [rsp+78h+arg_0], r15d
0x1800103c3  jmp     short loc_180010409
0x1800103c5  cmp     [rdi+368h], r15d
0x1800103cc  jz      short loc_180010409
0x1800103ce  cmp     [rdi+313h], r13b
0x1800103d5  jnz     short loc_180010409
0x1800103d7  test    bl, bl
0x1800103d9  jnz     short loc_180010401
0x1800103db  cmp     [rdi+318h], r13b
0x1800103e2  jnz     short loc_180010401
0x1800103e4  cmp     [rdi+312h], r13b
0x1800103eb  jz      short loc_180010409
0x1800103ed  mov     rcx, [rdi+88h]
0x1800103f4  mov     rcx, [rcx+48h]; this
0x1800103f8  call    ?LowRecoLatency@CRecoLatencyMeter@@QEAA_NXZ; CRecoLatencyMeter::LowRecoLatency(void)
0x1800103fd  test    al, al
0x1800103ff  jz      short loc_180010409
0x180010401  mov     rcx, rdi; this
0x180010404  call    ?StartCollectingAdaptationData@CSREngine@@AEAAJXZ; CSREngine::StartCollectingAdaptationData(void)
0x180010409  mov     rcx, [rdi+88h]
0x180010410  mov     [rdi+370h], r13d
0x180010417  mov     dword ptr [rdi+374h], 0FFFFFFFFh
0x180010421  mov     rcx, [rcx+50h]; this
0x180010425  call    ?ForceBaseAM@CAutoDetect@@QEAAXXZ; CAutoDetect::ForceBaseAM(void)
0x18001042a  test    esi, esi
0x18001042c  js      short loc_180010496
0x18001042e  test    bpl, bpl
0x180010431  jz      short loc_180010496
0x180010433  mov     rcx, [rdi+88h]
0x18001043a  mov     rax, [rcx+50h]
0x18001043e  cmp     [rax+18h], r13b
0x180010442  jnz     short loc_180010496
0x180010444  cmp     [rdi+36Ch], r15d
0x18001044b  jnz     short loc_18001047F
0x18001044d  cmp     [rdi+312h], r13b
0x180010454  jz      short loc_18001047F
0x180010456  mov     rax, [rcx+90h]
0x18001045d  mov     rdx, [rax+10h]
0x180010461  cmp     [rdx+162h], r13b
0x180010468  jz      short loc_18001047F
0x18001046a  mov     rcx, [rcx+48h]; this
0x18001046e  call    ?LowRecoLatency@CRecoLatencyMeter@@QEAA_NXZ; CRecoLatencyMeter::LowRecoLatency(void)
0x180010473  test    al, al
0x180010475  jz      short loc_18001047F
0x180010477  mov     rcx, rdi; this
  ... truncated ...
```
