# CSREngine::SetPropertyNum(SPPROPSRC,void *,ushort const *,long)

- ea: `0x180012000`
- end: `0x1800127c8`
- name: `?SetPropertyNum@CSREngine@@UEAAJW4SPPROPSRC@@PEAXPEBGJ@Z`
- size: `1992`
- prototype: `__int64 __usercall@<rax>(CSREngine *__hidden this@<rcx>, enum SPPROPSRC@<edx>, void *@<r8>, const unsigned __int16 *@<r9>, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, installer_update, broker_com_uri`

## callees

- `0x180004306`
- `0x180011538`
- `0x180011e44`
- `0x180012000`
- `0x18006cb1c`
- `0x18006cb5c`
- `0x1800854dc`
- `0x180085524`
- `0x180102010`

## string_xrefs

- `0x18001210c`: `ComplexResponseSpeed`
- `0x180012189`: `IncompleteRecognitionResponseSpeed`
- `0x180012444`: `AccuracyUpdatePeriod`
- `0x18001245b`: `AccuracyUpdateIncrement`
- `0x1800124f2`: `EngineThreadPriority`

## pseudocode

```c
__int64 __fastcall CSREngine::SetPropertyNum(
        CSREngine *this,
        enum SPPROPSRC a2,
        void *a3,
        const unsigned __int16 *a4,
        unsigned int a5)
{
  __int64 v7; // rbp
  __int64 v8; // rdi
  unsigned int v9; // r15d
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  bool v15; // zf
  unsigned int v16; // edx
  unsigned int v17; // ebx
  unsigned int v18; // ecx
  __int64 v19; // rdx
  __int64 v20; // rcx
  unsigned int v21; // ecx

  if ( !a4 )
    return (unsigned int)-2147024809;
  v7 = *((_QWORD *)this + 17);
  if ( !v7 )
    return (unsigned int)-2147024809;
  v8 = *(_QWORD *)(v7 + 64);
  if ( !v8 )
    return (unsigned int)-2147024809;
  v9 = 0;
  if ( !wcscmp_0(a4, L"HighConfidenceThreshold") )
  {
    v10 = a5;
    if ( (a5 & 0x80000000) == 0 )
    {
      if ( (int)a5 > 100 )
        v10 = 100;
    }
    else
    {
      v10 = 0;
    }
    *(_DWORD *)(v8 + 7644) = v10;
    return v9;
  }
  if ( !wcscmp_0(a4, L"NormalConfidenceThreshold") )
  {
    v11 = a5;
    if ( (a5 & 0x80000000) == 0 )
    {
      if ( (int)a5 > 100 )
        v11 = 100;
    }
    else
    {
      v11 = 0;
    }
    *(_DWORD *)(v8 + 7648) = v11;
    return v9;
  }
  if ( !wcscmp_0(a4, L"LowConfidenceThreshold") )
  {
    v12 = a5;
    if ( (a5 & 0x80000000) == 0 )
    {
      if ( (int)a5 > 100 )
        v12 = 100;
    }
    else
    {
      v12 = 0;
    }
    *(_DWORD *)(v8 + 7652) = v12;
    return v9;
  }
  if ( !wcscmp_0(a4, L"ResponseSpeed") )
  {
    CSegmentation::SetCompleteUnambiguousPhraseTimeout((CSegmentation *)(v7 + 264), a5);
    return v9;
  }
  if ( !wcscmp_0(a4, L"ComplexResponseSpeed") )
  {
    CSegmentation::SetCompleteAmbiguousPhraseTimeout((CSegmentation *)(v7 + 264), a5);
    return v9;
  }
  if ( !wcscmp_0(a4, L"NoRecognitionResponseSpeed") )
  {
    *(_DWORD *)(v7 + 340) = 0;
    if ( a5 )
    {
      v13 = 100;
      if ( a5 >= 0x64 )
        v13 = a5;
      if ( v13 > 0x3A98 )
        v13 = 15000;
      *(_DWORD *)(v7 + 340) = v13 / 0xA;
    }
    return v9;
  }
  if ( !wcscmp_0(a4, L"IncompleteRecognitionResponseSpeed") )
  {
    *(_DWORD *)(v7 + 344) = 0;
    if ( a5 )
    {
      v14 = 50;
      if ( a5 >= 0x32 )
        v14 = a5;
      if ( v14 > 0x2710 )
        v14 = 10000;
      *(_DWORD *)(v7 + 344) = v14 / 0xA;
    }
    return v9;
  }
  if ( !wcscmp_0(a4, L"AdaptationOn") )
  {
    v15 = a5 == 0;
LABEL_44:
    *((_BYTE *)this + 786) = !v15;
    return v9;
  }
  if ( !wcscmp_0(a4, L"PersistedBackgroundAdaptation") )
  {
    CSREngine::SetProfileParameter(this, 3, a5 != 0);
    v15 = a5 == 0;
    goto LABEL_44;
  }
  if ( !wcscmp_0(a4, L"PersistedLanguageModelAdaptation") )
  {
    CSREngine::SetProfileParameter(this, 98, a5 != 0);
    *((_BYTE *)this + 424) = a5 != 0;
    return v9;
  }
  if ( !wcscmp_0(a4, L"UserLMWeight") )
  {
    if ( a5 <= 0xFFFF )
      *(double *)(v7 + 504) = (double)(int)a5 * 0.0000152587890625;
    return v9;
  }
  if ( !wcscmp_0(a4, L"CFGConfidenceRejectionThreshold") )
  {
    if ( a5 > 0x64 )
    {
      if ( a5 == -1 )
        *(_DWORD *)(v8 + 7656) = *(_DWORD *)(v8 + 7660);
    }
    else
    {
      *(float *)(v8 + 7656) = (double)(int)a5 / 100.0;
    }
    return v9;
  }
  if ( !wcscmp_0(a4, L"SLMSpeechFrameThreshold") )
  {
    if ( (a5 & 0x80000000) != 0 )
    {
      if ( a5 == -1 )
        *(_DWORD *)(v8 + 7664) = *(_DWORD *)(v8 + 7668);
    }
    else
    {
      *(float *)(v8 + 7664) = (float)(int)a5;
    }
    return v9;
  }
  if ( !wcscmp_0(a4, L"AccuracyOverride") )
  {
    v16 = a5;
    if ( a5 > 0x64 )
      v16 = -1;
    if ( v16 != *(_DWORD *)(v8 + 60) )
      *(_DWORD *)(v8 + 60) = v16;
    return v9;
  }
  if ( !wcscmp_0(a4, L"loggingverbositythreshold") )
  {
    CDecoder::SetLoggingVerbosityThreshold((CDecoder *)v8, a5);
    return v9;
  }
  if ( !wcscmp_0(a4, L"AttachLattice") )
  {
    *(_DWORD *)(v8 + 536) = a5 != 0;
    return v9;
  }
  if ( !wcscmp_0(a4, L"AttachPhraseLevelPredictors") )
  {
    *(_BYTE *)(v8 + 540) = a5 != 0;
    return v9;
  }
  if ( wcscmp_0(a4, L"SmallLatency")
    && wcscmp_0(a4, L"LargeLatency")
    && wcscmp_0(a4, L"AccuracyUpdatePeriod")
    && wcscmp_0(a4, L"AccuracyUpdateIncrement") )
  {
    if ( !wcscmp_0(a4, L"NormalizeCFGTransitions") )
    {
      *(_DWORD *)(v7 + 824) = a5 != 0;
      return v9;
    }
    if ( !wcscmp_0(a4, L"AssumeCFGFromTrustedSource") )
    {
      *(_BYTE *)(v7 + 808) = a5 != 0;
      return v9;
    }
    v17 = a5;
    if ( !wcscmp_0(a4, L"TrumpingMethod") )
    {
      if ( a5 > 2 )
        v17 = 2;
      *(_DWORD *)(v8 + 3560) = v17;
      return v9;
    }
    if ( !wcscmp_0(a4, L"EngineThreadPriority") )
    {
      if ( a5 + 15 <= 0x11 )
      {
        *((_DWORD *)this + 233) = a5;
        return v9;
      }
      return (unsigned int)-2147024809;
    }
    if ( !wcscmp_0(a4, L"AllowSecondPass") )
    {
      *(_BYTE *)(v8 + 2548) = a5 != 0;
    }
    else if ( !wcscmp_0(a4, L"ConstrainedSecondPass") )
    {
      *(_BYTE *)(v8 + 2549) = a5 != 0;
    }
    else if ( !wcscmp_0(a4, L"AllowSecondPassFrontEnd") )
    {
      *(_BYTE *)(v8 + 2550) = a5 != 0;
    }
    else if ( !wcscmp_0(a4, L"AllowSecondPassFrontEnd2") )
    {
      *(_BYTE *)(v8 + 2551) = a5 != 0;
    }
    else if ( !wcscmp_0(a4, L"DisableHypotheses") )
    {
      *(_BYTE *)(v8 + 3296) = a5 != 0;
    }
    else if ( !wcscmp_0(a4, L"DisableTentative") )
    {
      *(_BYTE *)(v8 + 3297) = a5 != 0;
    }
    else if ( !wcscmp_0(a4, L"TentativeTimeout") )
    {
      if ( *(_BYTE *)(v7 + 516) && a5 > *(_DWORD *)(v7 + 304) )
        v17 = *(_DWORD *)(v7 + 304);
      v18 = 50;
      if ( v17 >= 0x32 )
      {
        v18 = v17;
        if ( v17 > 0x2710 )
          v18 = 10000;
      }
      *(_DWORD *)(v7 + 328) = v18;
      *(_DWORD *)(v7 + 332) = v18 / 0xA;
    }
    else if ( !wcscmp_0(a4, L"GarbageFramePenalty") )
    {
      *(_DWORD *)(v8 + 3032) = a5;
    }
    else if ( !wcscmp_0(a4, L"GarbageWordPenalty") )
    {
      *(_DWORD *)(v8 + 7212) = a5;
    }
    else if ( !wcscmp_0(a4, L"LogCFGInsertionPenalty") )
    {
      *(_DWORD *)(v8 + 7216) = a5;
    }
    else if ( !wcscmp_0(a4, L"DisableResultPronunciation") )
    {
      *(_BYTE *)(v8 + 7684) = a5 != 0;
    }
    else if ( !wcscmp_0(a4, L"WFSTDecoder") )
    {
      *(_BYTE *)(v8 + 6832) = a5 != 0;
    }
    else if ( !wcscmp_0(a4, L"AddTTSPronunciation") && *(_BYTE *)(v7 + 617) )
    {
      *(_BYTE *)(v7 + 618) = a5 != 0;
      v19 = *((_QWORD *)this + 17);
      v20 = *(_QWORD *)(v19 + 456);
      if ( v20 )
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v20 + 296LL))(v20, *(unsigned __int8 *)(v19 + 618));
    }
    else if ( !wcscmp_0(a4, L"MaxRecoLatency") )
    {
      v21 = 0x7FFFFFFF;
      if ( (a5 & 0x80000000) == 0 )
        v21 = a5;
      *(_DWORD *)(*(_QWORD *)(v7 + 72) + 8LL) = v21;
    }
    else if ( !wcscmp_0(a4, L"StreamLagEventFrequency") )
    {
      return (unsigned int)CDecoder::SetStreamLagEventFrequency((CDecoder *)v8, a5);
    }
    else if ( !wcscmp_0(a4, L"DeepNeuralNetworksFrameSkip") )
    {
      CDecoder::SetDNNFrameSkip((CDecoder *)v8, a5);
    }
    else
    {
      return 1;
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180012000  push    rbx
0x180012002  push    rbp
0x180012003  push    rsi
0x180012004  push    rdi
0x180012005  push    r14
0x180012007  push    r15
0x180012009  sub     rsp, 28h
0x18001200d  mov     rsi, r9
0x180012010  mov     r14, rcx
0x180012013  test    r9, r9
0x180012016  jz      loc_1800127B2
0x18001201c  mov     rbp, [rcx+88h]
0x180012023  test    rbp, rbp
0x180012026  jz      loc_1800127B2
0x18001202c  mov     rdi, [rbp+40h]
0x180012030  test    rdi, rdi
0x180012033  jz      loc_1800127B2
0x180012039  lea     rdx, aHighconfidence; "HighConfidenceThreshold"
0x180012040  mov     rcx, r9; String1
0x180012043  xor     r15d, r15d
0x180012046  call    wcscmp_0
0x18001204b  test    eax, eax
0x18001204d  jnz     short loc_180012073
0x18001204f  mov     eax, [rsp+58h+arg_20]
0x180012056  test    eax, eax
0x180012058  jns     short loc_18001205E
0x18001205a  xor     eax, eax
0x18001205c  jmp     short loc_180012068
0x18001205e  mov     ecx, 64h ; 'd'
0x180012063  cmp     eax, ecx
0x180012065  cmovg   eax, ecx
0x180012068  mov     [rdi+1DDCh], eax
0x18001206e  jmp     loc_1800127B8
0x180012073  lea     rdx, aNormalconfiden; "NormalConfidenceThreshold"
0x18001207a  mov     rcx, rsi; String1
0x18001207d  call    wcscmp_0
0x180012082  test    eax, eax
0x180012084  jnz     short loc_1800120AA
0x180012086  mov     eax, [rsp+58h+arg_20]
0x18001208d  test    eax, eax
0x18001208f  jns     short loc_180012095
0x180012091  xor     eax, eax
0x180012093  jmp     short loc_18001209F
0x180012095  mov     ecx, 64h ; 'd'
0x18001209a  cmp     eax, ecx
0x18001209c  cmovg   eax, ecx
0x18001209f  mov     [rdi+1DE0h], eax
0x1800120a5  jmp     loc_1800127B8
0x1800120aa  lea     rdx, aLowconfidencet; "LowConfidenceThreshold"
0x1800120b1  mov     rcx, rsi; String1
0x1800120b4  call    wcscmp_0
0x1800120b9  test    eax, eax
0x1800120bb  jnz     short loc_1800120E1
0x1800120bd  mov     eax, [rsp+58h+arg_20]
0x1800120c4  test    eax, eax
0x1800120c6  jns     short loc_1800120CC
0x1800120c8  xor     eax, eax
0x1800120ca  jmp     short loc_1800120D6
0x1800120cc  mov     ecx, 64h ; 'd'
0x1800120d1  cmp     eax, ecx
0x1800120d3  cmovg   eax, ecx
0x1800120d6  mov     [rdi+1DE4h], eax
0x1800120dc  jmp     loc_1800127B8
0x1800120e1  lea     rdx, aResponsespeed_0; "ResponseSpeed"
0x1800120e8  mov     rcx, rsi; String1
0x1800120eb  call    wcscmp_0
0x1800120f0  test    eax, eax
0x1800120f2  jnz     short loc_18001210C
0x1800120f4  mov     edx, [rsp+58h+arg_20]; unsigned int
0x1800120fb  lea     rcx, [rbp+108h]; this
0x180012102  call    ?SetCompleteUnambiguousPhraseTimeout@CSegmentation@@QEAAXK@Z; CSegmentation::SetCompleteUnambiguousPhraseTimeout(ulong)
0x180012107  jmp     loc_1800127B8
0x18001210c  lea     rdx, aComplexrespons; "ComplexResponseSpeed"
0x180012113  mov     rcx, rsi; String1
0x180012116  call    wcscmp_0
0x18001211b  test    eax, eax
0x18001211d  jnz     short loc_180012137
0x18001211f  mov     edx, [rsp+58h+arg_20]; unsigned int
0x180012126  lea     rcx, [rbp+108h]; this
0x18001212d  call    ?SetCompleteAmbiguousPhraseTimeout@CSegmentation@@QEAAXK@Z; CSegmentation::SetCompleteAmbiguousPhraseTimeout(ulong)
0x180012132  jmp     loc_1800127B8
0x180012137  lea     rdx, aNorecognitionr; "NoRecognitionResponseSpeed"
0x18001213e  mov     rcx, rsi; String1
0x180012141  call    wcscmp_0
0x180012146  test    eax, eax
0x180012148  jnz     short loc_180012189
0x18001214a  mov     eax, [rsp+58h+arg_20]
0x180012151  mov     [rbp+154h], r15d
0x180012158  test    eax, eax
0x18001215a  jz      loc_1800127B8
0x180012160  mov     ecx, 64h ; 'd'
0x180012165  cmp     eax, ecx
0x180012167  cmovnb  ecx, eax
0x18001216a  mov     eax, 3A98h
0x18001216f  cmp     ecx, eax
0x180012171  cmova   ecx, eax
0x180012174  mov     eax, 0CCCCCCCDh
0x180012179  mul     ecx
0x18001217b  shr     edx, 3
0x18001217e  mov     [rbp+154h], edx
0x180012184  jmp     loc_1800127B8
0x180012189  lea     rdx, aIncompletereco; "IncompleteRecognitionResponseSpeed"
0x180012190  mov     rcx, rsi; String1
0x180012193  call    wcscmp_0
0x180012198  test    eax, eax
0x18001219a  jnz     short loc_1800121DB
0x18001219c  mov     eax, [rsp+58h+arg_20]
0x1800121a3  mov     [rbp+158h], r15d
0x1800121aa  test    eax, eax
0x1800121ac  jz      loc_1800127B8
0x1800121b2  mov     ecx, 32h ; '2'
0x1800121b7  cmp     eax, ecx
0x1800121b9  cmovnb  ecx, eax
0x1800121bc  mov     eax, 2710h
0x1800121c1  cmp     ecx, eax
0x1800121c3  cmova   ecx, eax
0x1800121c6  mov     eax, 0CCCCCCCDh
0x1800121cb  mul     ecx
0x1800121cd  shr     edx, 3
0x1800121d0  mov     [rbp+158h], edx
0x1800121d6  jmp     loc_1800127B8
0x1800121db  lea     rdx, aAdaptationon; "AdaptationOn"
0x1800121e2  mov     rcx, rsi; String1
0x1800121e5  call    wcscmp_0
0x1800121ea  test    eax, eax
0x1800121ec  jnz     short loc_1800121F8
0x1800121ee  cmp     [rsp+58h+arg_20], r15d
0x1800121f6  jmp     short loc_180012228
0x1800121f8  lea     rdx, aPersistedbackg; "PersistedBackgroundAdaptation"
0x1800121ff  mov     rcx, rsi; String1
0x180012202  call    wcscmp_0
0x180012207  test    eax, eax
0x180012209  jnz     short loc_180012237
0x18001220b  mov     ebx, [rsp+58h+arg_20]
0x180012212  lea     edx, [rax+3]; int
0x180012215  xor     r8d, r8d
0x180012218  mov     rcx, r14; this
0x18001221b  test    ebx, ebx
0x18001221d  setnz   r8b; unsigned int
0x180012221  call    ?SetProfileParameter@CSREngine@@AEAAJHK@Z; CSREngine::SetProfileParameter(int,ulong)
0x180012226  test    ebx, ebx
0x180012228  setnz   al
0x18001222b  mov     [r14+312h], al
0x180012232  jmp     loc_1800127B8
0x180012237  lea     rdx, aPersistedlangu; "PersistedLanguageModelAdaptation"
0x18001223e  mov     rcx, rsi; String1
0x180012241  call    wcscmp_0
0x180012246  test    eax, eax
0x180012248  jnz     short loc_180012276
0x18001224a  mov     ebx, [rsp+58h+arg_20]
0x180012251  lea     edx, [rax+62h]; int
0x180012254  xor     r8d, r8d
0x180012257  mov     rcx, r14; this
0x18001225a  test    ebx, ebx
0x18001225c  setnz   r8b; unsigned int
0x180012260  call    ?SetProfileParameter@CSREngine@@AEAAJHK@Z; CSREngine::SetProfileParameter(int,ulong)
0x180012265  test    ebx, ebx
0x180012267  setnz   al
0x18001226a  mov     [r14+1A8h], al
0x180012271  jmp     loc_1800127B8
0x180012276  lea     rdx, aUserlmweight; "UserLMWeight"
0x18001227d  mov     rcx, rsi; String1
0x180012280  call    wcscmp_0
0x180012285  test    eax, eax
0x180012287  jnz     short loc_1800122BC
0x180012289  cmp     [rsp+58h+arg_20], 0FFFFh
0x180012294  ja      loc_1800127B8
0x18001229a  movd    xmm0, [rsp+58h+arg_20]
0x1800122a3  cvtdq2pd xmm0, xmm0
0x1800122a7  mulsd   xmm0, cs:__real@3ef0000000000000
0x1800122af  movsd   qword ptr [rbp+1F8h], xmm0
0x1800122b7  jmp     loc_1800127B8
0x1800122bc  lea     rdx, aCfgconfidencer; "CFGConfidenceRejectionThreshold"
0x1800122c3  mov     rcx, rsi; String1
0x1800122c6  call    wcscmp_0
0x1800122cb  test    eax, eax
0x1800122cd  jnz     short loc_18001231A
0x1800122cf  mov     edx, [rsp+58h+arg_20]
0x1800122d6  lea     ecx, [rax+64h]
0x1800122d9  cmp     edx, ecx
0x1800122db  ja      short loc_1800122FE
0x1800122dd  movd    xmm0, edx
0x1800122e1  cvtdq2pd xmm0, xmm0
0x1800122e5  divsd   xmm0, cs:__real@4059000000000000
0x1800122ed  cvtpd2ps xmm0, xmm0
0x1800122f1  movss   dword ptr [rdi+1DE8h], xmm0
0x1800122f9  jmp     loc_1800127B8
0x1800122fe  or      eax, 0FFFFFFFFh
0x180012301  cmp     edx, eax
0x180012303  jnz     loc_1800127B8
0x180012309  mov     eax, [rdi+1DECh]
0x18001230f  mov     [rdi+1DE8h], eax
0x180012315  jmp     loc_1800127B8
0x18001231a  lea     rdx, aSlmspeechframe_0; "SLMSpeechFrameThreshold"
0x180012321  mov     rcx, rsi; String1
0x180012324  call    wcscmp_0
0x180012329  test    eax, eax
0x18001232b  jnz     short loc_180012368
0x18001232d  mov     ecx, [rsp+58h+arg_20]
0x180012334  test    ecx, ecx
0x180012336  js      short loc_18001234C
0x180012338  movd    xmm0, ecx
0x18001233c  cvtdq2ps xmm0, xmm0
0x18001233f  movss   dword ptr [rdi+1DF0h], xmm0
0x180012347  jmp     loc_1800127B8
0x18001234c  or      eax, 0FFFFFFFFh
0x18001234f  cmp     ecx, eax
0x180012351  jnz     loc_1800127B8
0x180012357  mov     eax, [rdi+1DF4h]
0x18001235d  mov     [rdi+1DF0h], eax
0x180012363  jmp     loc_1800127B8
0x180012368  lea     rdx, aAccuracyoverri; "AccuracyOverride"
0x18001236f  mov     rcx, rsi; String1
0x180012372  call    wcscmp_0
0x180012377  test    eax, eax
0x180012379  jnz     short loc_18001239E
0x18001237b  mov     edx, [rsp+58h+arg_20]
0x180012382  or      eax, 0FFFFFFFFh
0x180012385  lea     ecx, [rax+65h]
0x180012388  cmp     edx, ecx
0x18001238a  cmova   edx, eax
0x18001238d  cmp     edx, [rdi+3Ch]
0x180012390  jz      loc_1800127B8
0x180012396  mov     [rdi+3Ch], edx
0x180012399  jmp     loc_1800127B8
0x18001239e  lea     rdx, aLoggingverbosi; "loggingverbositythreshold"
0x1800123a5  mov     rcx, rsi; String1
0x1800123a8  call    wcscmp_0
0x1800123ad  test    eax, eax
0x1800123af  jnz     short loc_1800123C5
0x1800123b1  mov     edx, [rsp+58h+arg_20]; unsigned int
0x1800123b8  mov     rcx, rdi; this
0x1800123bb  call    ?SetLoggingVerbosityThreshold@CDecoder@@AEAAXK@Z; CDecoder::SetLoggingVerbosityThreshold(ulong)
0x1800123c0  jmp     loc_1800127B8
0x1800123c5  lea     rdx, aAttachlattice; "AttachLattice"
0x1800123cc  mov     rcx, rsi; String1
0x1800123cf  call    wcscmp_0
0x1800123d4  test    eax, eax
0x1800123d6  jnz     short loc_1800123ED
0x1800123d8  cmp     [rsp+58h+arg_20], eax
0x1800123df  setnz   al
0x1800123e2  mov     [rdi+218h], eax
0x1800123e8  jmp     loc_1800127B8
0x1800123ed  lea     rdx, aAttachphrasele_0; "AttachPhraseLevelPredictors"
0x1800123f4  mov     rcx, rsi; String1
0x1800123f7  call    wcscmp_0
0x1800123fc  test    eax, eax
0x1800123fe  jnz     short loc_180012416
0x180012400  cmp     [rsp+58h+arg_20], r15d
0x180012408  setnz   al
0x18001240b  mov     [rdi+21Ch], al
0x180012411  jmp     loc_1800127B8
0x180012416  lea     rdx, aSmalllatency; "SmallLatency"
0x18001241d  mov     rcx, rsi; String1
0x180012420  call    wcscmp_0
0x180012425  test    eax, eax
0x180012427  jz      loc_1800127B8
0x18001242d  lea     rdx, aLargelatency; "LargeLatency"
0x180012434  mov     rcx, rsi; String1
0x180012437  call    wcscmp_0
0x18001243c  test    eax, eax
0x18001243e  jz      loc_1800127B8
0x180012444  lea     rdx, aAccuracyupdate_0; "AccuracyUpdatePeriod"
0x18001244b  mov     rcx, rsi; String1
0x18001244e  call    wcscmp_0
0x180012453  test    eax, eax
0x180012455  jz      loc_1800127B8
0x18001245b  lea     rdx, aAccuracyupdate; "AccuracyUpdateIncrement"
0x180012462  mov     rcx, rsi; String1
0x180012465  call    wcscmp_0
0x18001246a  test    eax, eax
0x18001246c  jz      loc_1800127B8
0x180012472  lea     rdx, aNormalizecfgtr_0; "NormalizeCFGTransitions"
0x180012479  mov     rcx, rsi; String1
0x18001247c  call    wcscmp_0
0x180012481  test    eax, eax
0x180012483  jnz     short loc_18001249A
0x180012485  cmp     [rsp+58h+arg_20], eax
0x18001248c  setnz   al
0x18001248f  mov     [rbp+338h], eax
0x180012495  jmp     loc_1800127B8
0x18001249a  lea     rdx, aAssumecfgfromt; "AssumeCFGFromTrustedSource"
0x1800124a1  mov     rcx, rsi; String1
0x1800124a4  call    wcscmp_0
0x1800124a9  test    eax, eax
0x1800124ab  jnz     short loc_1800124C3
0x1800124ad  cmp     [rsp+58h+arg_20], r15d
0x1800124b5  setnz   al
0x1800124b8  mov     [rbp+328h], al
0x1800124be  jmp     loc_1800127B8
0x1800124c3  mov     ebx, [rsp+58h+arg_20]
0x1800124ca  lea     rdx, aTrumpingmethod; "TrumpingMethod"
0x1800124d1  mov     rcx, rsi; String1
0x1800124d4  call    wcscmp_0
0x1800124d9  test    eax, eax
0x1800124db  jnz     short loc_1800124F2
0x1800124dd  mov     eax, 2
0x1800124e2  cmp     ebx, eax
0x1800124e4  cmova   ebx, eax
0x1800124e7  mov     [rdi+0DE8h], ebx
  ... truncated ...
```
