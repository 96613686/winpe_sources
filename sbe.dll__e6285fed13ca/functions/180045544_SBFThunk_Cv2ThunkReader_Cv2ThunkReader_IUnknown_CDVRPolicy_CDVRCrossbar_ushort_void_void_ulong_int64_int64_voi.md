# SBFThunk::Cv2ThunkReader::Cv2ThunkReader(IUnknown *,CDVRPolicy *,CDVRCrossbar *,ushort *,void (*)(void *,ulong,__int64,__int64),void *,ulong,void * *,ushort *,SBFThunk::ISBE2PauseBufferExtentReporter *,long *)

- ea: `0x180045544`
- end: `0x180045ae0`
- name: `??0Cv2ThunkReader@SBFThunk@@IEAA@PEAUIUnknown@@PEAVCDVRPolicy@@PEAVCDVRCrossbar@@PEAGP6AXPEAXK_J5@Z4KPEAPEAX3PEAVISBE2PauseBufferExtentReporter@1@PEAJ@Z`
- size: `1436`
- prototype: `__int64 __usercall@<rax>(SBFThunk::Cv2ThunkReader *__hidden this@<rcx>, struct IUnknown *@<rdx>, struct CDVRPolicy *@<r8>, struct CDVRCrossbar *@<r9>, unsigned __int16 *, void (*)(void *, unsigned int, __int64, __int64), void *, unsigned int, void **, unsigned __int16 *, struct SBFThunk::ISBE2PauseBufferExtentReporter *, int *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180048248`

## callees

- `0x1800017a0`
- `0x1800017ec`
- `0x180001c00`
- `0x18000256c`
- `0x1800089b8`
- `0x18000ca14`
- `0x18000ca64`
- `0x180044eec`
- `0x180045544`
- `0x180047df0`
- `0x180048a04`
- `0x18004c8dc`
- `0x180057140`
- `0x18006201c`
- `0x1800a5210`
- `0x1800a6de4`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x1800457f5`
- `KERNEL32!CreateEventW` at `0x1800457f5`
- `KERNEL32!InitializeCriticalSection` at `0x18004568a`
- `KERNEL32!InitializeCriticalSection` at `0x18004568a`
- `KERNEL32!GetLastError` at `0x180045807`
- `KERNEL32!GetLastError` at `0x180045807`
- `ole32!CoCreateInstance` at `0x180045839`
- `ole32!CoCreateInstance` at `0x180045839`
- `WINMM!timeGetTime` at `0x180045790`
- `WINMM!timeGetTime` at `0x180045790`

## string_xrefs

- `0x180045963`: `ERROR: %s(%u); m_pISBFFile -> CreateFile () %s : error is %08xh`

## pseudocode

```c
SBFThunk::Cv2ThunkReader *__fastcall SBFThunk::Cv2ThunkReader::Cv2ThunkReader(
        SBFThunk::Cv2ThunkReader *this,
        struct IUnknown *a2,
        struct CDVRPolicy *a3,
        struct CDVRCrossbar *a4,
        unsigned __int16 *a5,
        void (*a6)(void *, unsigned int, __int64, __int64),
        void *a7,
        unsigned int a8,
        void **a9,
        unsigned __int16 *a10,
        struct SBFThunk::ISBE2PauseBufferExtentReporter *a11,
        int *a12)
{
  struct ISBFFile **v15; // r12
  char *v16; // r15
  void *v17; // rax
  int v18; // eax
  void *v19; // rax
  int v20; // eax
  __int64 *v21; // r14
  __int64 v22; // rax
  HANDLE EventW; // rax
  signed int LastError; // eax
  HRESULT Instance; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // esi
  __int64 v31; // r14
  unsigned __int64 v32; // rdx
  SBF2::CSBFDShowTimeline *v33; // rax
  void (__fastcall ***v34)(_QWORD, __int64); // rax
  int Profile; // eax
  int v36; // esi
  __int64 v37; // rdi
  unsigned __int64 v38; // rdx
  SBF2::CSBFTimeBasedIndex *v39; // rax
  unsigned int v40; // edx
  __int64 v41; // rax
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  _QWORD v46[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v47; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v48[199]; // [rsp+71h] [rbp-8Fh] BYREF
  int v49; // [rsp+138h] [rbp+38h]
  int v50; // [rsp+13Ch] [rbp+3Ch]

  SBEBasicTracers::SBEBasicTracers(this, a3);
  _InterlockedIncrement(&CBaseObject::m_cObjects);
  *((_QWORD *)this + 34) = (char *)this + 264;
  *((_DWORD *)this + 70) = 0;
  v15 = (struct ISBFFile **)((char *)this + 664);
  *(_QWORD *)this = &SBFThunk::Cv2ThunkReader::`vftable'{for `SBEBasicTracers'};
  v16 = (char *)this + 736;
  *((_DWORD *)this + 158) = 0;
  *((_QWORD *)this + 33) = &SBFThunk::Cv2ThunkReader::`vftable'{for `CUnknown'};
  *((_DWORD *)this + 162) = 2000;
  *(_QWORD *)((char *)this + 636) = 1;
  *((_DWORD *)this + 161) = 0;
  *((_QWORD *)this + 82) = 0;
  *((_QWORD *)this + 83) = 0;
  *((_QWORD *)this + 84) = 0;
  *((_QWORD *)this + 36) = &SBFThunk::Cv2ThunkReader::`vftable'{for `IDVRReader'};
  *((_QWORD *)this + 37) = &SBFThunk::Cv2ThunkReader::`vftable'{for `IDVRReaderNotify'};
  *((_QWORD *)this + 87) = 0;
  *((_QWORD *)this + 88) = 0;
  *((_DWORD *)this + 178) = 10;
  *((_QWORD *)this + 38) = &SBFThunk::Cv2ThunkReader::`vftable'{for `IPauseBufferNodeState'};
  *((_QWORD *)this + 86) = &SBF2::CTSmallVector<SBF2::CSBFEvtHolder *>::`vftable';
  *((_QWORD *)this + 85) = &SBFThunk::Cv2ThunkReader::CSBFEventVectorEx::`vftable';
  *((_QWORD *)this + 91) = a3;
  *((_QWORD *)this + 92) = 0;
  *((_QWORD *)this + 93) = 0;
  *((_QWORD *)this + 90) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 752));
  *((_DWORD *)this + 208) = -1;
  *((_QWORD *)this + 99) = -1;
  *((_QWORD *)this + 100) = -1;
  *((_QWORD *)this + 101) = &SBF2::CTSmallVector<SBF2::CSBFEvtHolder *>::`vftable';
  *((_QWORD *)this + 102) = 0;
  *((_QWORD *)this + 103) = 0;
  if ( *a12 >= 0 )
  {
    v17 = operator new[](0x100u);
    *((_QWORD *)this + 102) = v17;
    if ( v17 )
    {
      v18 = 0;
      *((_DWORD *)this + 207) = 16;
    }
    else
    {
      v18 = -2147024882;
    }
    *a12 = v18;
  }
  *((_QWORD *)this + 101) = &SBFThunk::CStreamCtxPtrMap::`vftable';
  *((_QWORD *)this + 105) = &SBF2::CTSmallVector<SBF2::CSBFEvtHolder *>::`vftable';
  *((_QWORD *)this + 106) = 0;
  *((_QWORD *)this + 107) = 0;
  *((_DWORD *)this + 216) = -1;
  if ( *a12 >= 0 )
  {
    v19 = operator new[](0x100u);
    *((_QWORD *)this + 106) = v19;
    if ( v19 )
    {
      v20 = 0;
      *((_DWORD *)this + 215) = 16;
    }
    else
    {
      v20 = -2147024882;
    }
    *a12 = v20;
  }
  *((_QWORD *)this + 105) = &SBFThunk::CPipelineCtxPtrMap::`vftable';
  v21 = (__int64 *)((char *)this + 872);
  *((_QWORD *)this + 112) = a4;
  *((_QWORD *)this + 109) = 0;
  *((_QWORD *)this + 110) = 0;
  *((_QWORD *)this + 111) = 0;
  *((_DWORD *)this + 226) = timeGetTime();
  *((_WORD *)this + 464) = 0;
  *((_QWORD *)this + 114) = -1;
  *((_QWORD *)this + 115) = -1;
  *((_QWORD *)this + 117) = a11;
  if ( a11 )
    _InterlockedIncrement((volatile signed __int32 *)a11 + 2);
  v22 = *((_QWORD *)this + 91);
  v46[0] = 0;
  _InterlockedIncrement((volatile signed __int32 *)(v22 + 272));
  if ( *a12 >= 0 )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 93) = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      *a12 = LastError;
      goto LABEL_42;
    }
    Instance = CoCreateInstance(&CLSID_SBFCore, 0, 3u, &IID_ISBFFile, (LPVOID *)this + 83);
    *a12 = Instance;
    if ( Instance < 0 )
      goto LABEL_42;
    v26 = SBF2::CSBFPolicy::CreateInstance(a3, a8, a9, (struct SBF2::CSBFPolicy **)this + 92);
    *a12 = v26;
    if ( v26 < 0 )
      goto LABEL_42;
    if ( a8 )
    {
      v27 = (**(__int64 (__fastcall ***)(struct ISBFFile *, GUID *, _QWORD *))*v15)(
              *v15,
              &IID_IStreamBufferInitialize,
              v46);
      *a12 = v27;
      if ( v27 < 0 )
        goto LABEL_42;
      v28 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)v46[0] + 32LL))(
              v46[0],
              *(unsigned int *)(*(_QWORD *)(*(_QWORD *)v16 + 280LL) + 24LL),
              *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v16 + 280LL) + 16LL));
      *a12 = v28;
      if ( v28 < 0 )
        goto LABEL_42;
    }
    v29 = (*(__int64 (__fastcall **)(struct ISBFFile *, struct IUnknown *, unsigned __int16 *, __int64, unsigned int, int))(*(_QWORD *)*v15 + 24LL))(
            *v15,
            a2,
            a5,
            3,
            0x80000000,
            7);
    *a12 = v29;
    v30 = v29;
    if ( v29 == -2147418113 )
      goto LABEL_42;
    if ( v29 < 0 )
    {
      v31 = *(_QWORD *)v16;
      v47 = 0;
      memset_0(v48, 0, 0xCFu);
      if ( (int)StringCchCopyA(&v47, v32, "multimedia\\dshow\\filters\\sbe\\dvrfilters\\shared\\v2thunk.cpp") >= 0 )
      {
        v49 = 423;
        v50 = v30;
        SBEPerf::CTeHomeETWEvent<EH_FATAL_ERROR_EVENT>::TraceEvent(v31 + 416, &v47);
      }
      LODWORD(ppv) = 423;
      CSbeFileLog::LogEvent(
        0x10u,
        1u,
        L"ERROR: %s(%u); m_pISBFFile -> CreateFile () %s : error is %08xh",
        L"multimedia\\dshow\\filters\\sbe\\dvrfilters\\shared\\v2thunk.cpp",
        ppv,
        a5,
        *a12);
      goto LABEL_42;
    }
    v33 = (SBF2::CSBFDShowTimeline *)operator new(0x2B0u);
    if ( v33 )
    {
      v34 = (void (__fastcall ***)(_QWORD, __int64))SBF2::CSBFDShowTimeline::CSBFDShowTimeline(
                                                      v33,
                                                      (__int64)this + 680,
                                                      a12);
      *((_QWORD *)this + 84) = v34;
      if ( v34 )
      {
        if ( *a12 < 0 )
        {
          (**v34)(v34, 1);
          *((_QWORD *)this + 84) = 0;
          goto LABEL_42;
        }
        Profile = SBFThunk::Cv2ThunkReader::ExtractProfile(this);
        *a12 = Profile;
        v36 = Profile;
        if ( Profile < 0 )
        {
          v37 = *(_QWORD *)v16;
          v47 = 0;
          memset_0(v48, 0, 0xCFu);
          if ( (int)StringCchCopyA(&v47, v38, "multimedia\\dshow\\filters\\sbe\\dvrfilters\\shared\\v2thunk.cpp") >= 0 )
          {
            v49 = 432;
            v50 = v36;
            SBEPerf::CTeHomeETWEvent<EH_FATAL_ERROR_EVENT>::TraceEvent(v37 + 416, &v47);
          }
          goto LABEL_42;
        }
        SBF2::CTSBFRefVector<ISBFEvent>::Reset((char *)this + 680);
        v39 = (SBF2::CSBFTimeBasedIndex *)operator new(0x48u);
        if ( v39 )
        {
          v41 = SBF2::CSBFTimeBasedIndex::CSBFTimeBasedIndex(v39, v40, *v15, a12);
          *v21 = v41;
          if ( v41 )
          {
            if ( *a12 == -2147023728 )
            {
              SBF2::Delete<SBF2::CSBFTimeBasedIndex>((char *)this + 872);
              *a12 = 0;
            }
            goto LABEL_42;
          }
        }
        else
        {
          *v21 = 0;
        }
      }
    }
    else
    {
      *((_QWORD *)this + 84) = 0;
    }
    *a12 = -2147024882;
  }
LABEL_42:
  EhEtw::TPtr<IEhTraceSpan>::Release(v46);
  return this;
}

```

## disassembly

```asm
0x180045544  mov     [rsp-8+arg_18], rbx
0x180045549  push    rbp
0x18004554a  push    rsi
0x18004554b  push    rdi
0x18004554c  push    r12
0x18004554e  push    r13
0x180045550  push    r14
0x180045552  push    r15
0x180045554  lea     rbp, [rsp-50h]
0x180045559  sub     rsp, 150h
0x180045560  mov     rax, cs:__security_cookie
0x180045567  xor     rax, rsp
0x18004556a  mov     [rbp+80h+var_40], rax
0x18004556e  mov     rax, [rbp+80h+arg_20]
0x180045575  mov     rsi, r9
0x180045578  mov     rdi, [rbp+80h+arg_58]
0x18004557f  mov     r14, r8
0x180045582  mov     [rsp+180h+var_140], rax
0x180045587  mov     rbx, rcx
0x18004558a  mov     rax, [rbp+80h+arg_40]
0x180045591  mov     [rsp+180h+var_128], rdx
0x180045596  mov     rdx, r8; struct SBEBasicTracers *
0x180045599  mov     [rsp+180h+var_138], rax
0x18004559e  mov     [rsp+180h+var_130], r8
0x1800455a3  call    ??0SBEBasicTracers@@QEAA@PEBV0@@Z; SBEBasicTracers::SBEBasicTracers(SBEBasicTracers const *)
0x1800455a8  lea     rax, [rbx+108h]
0x1800455af  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x1800455b6  mov     [rax+8], rax
0x1800455ba  lea     r13, [rbx+2A8h]
0x1800455c1  xor     edx, edx
0x1800455c3  lea     rcx, ??_7Cv2ThunkReader@SBFThunk@@6BSBEBasicTracers@@@; const SBFThunk::Cv2ThunkReader::`vftable'{for `SBEBasicTracers'}
0x1800455ca  mov     [rax+10h], edx
0x1800455cd  lea     r12, [rbx+298h]
0x1800455d4  mov     [rbx], rcx
0x1800455d7  lea     r15, [rbx+2E0h]
0x1800455de  mov     [rbx+278h], edx
0x1800455e4  lea     rcx, ??_7Cv2ThunkReader@SBFThunk@@6BCUnknown@@@; const SBFThunk::Cv2ThunkReader::`vftable'{for `CUnknown'}
0x1800455eb  mov     [rax], rcx
0x1800455ee  lea     rax, ??_7Cv2ThunkReader@SBFThunk@@6BIDVRReader@@@; const SBFThunk::Cv2ThunkReader::`vftable'{for `IDVRReader'}
0x1800455f5  mov     dword ptr [rbx+288h], 7D0h
0x1800455ff  lea     rcx, [rbx+2F0h]; lpCriticalSection
0x180045606  mov     qword ptr [rbx+27Ch], 1
0x180045611  mov     [rbx+284h], edx
0x180045617  mov     [rbx+290h], rdx
0x18004561e  mov     [r12], rdx
0x180045622  mov     [rbx+2A0h], rdx
0x180045629  mov     [rbx+120h], rax
0x180045630  lea     rax, ??_7Cv2ThunkReader@SBFThunk@@6BIDVRReaderNotify@@@; const SBFThunk::Cv2ThunkReader::`vftable'{for `IDVRReaderNotify'}
0x180045637  mov     [rbx+128h], rax
0x18004563e  lea     rax, ??_7Cv2ThunkReader@SBFThunk@@6BIPauseBufferNodeState@@@; const SBFThunk::Cv2ThunkReader::`vftable'{for `IPauseBufferNodeState'}
0x180045645  mov     [r13+10h], rdx
0x180045649  mov     [r13+18h], rdx
0x18004564d  mov     dword ptr [r13+20h], 0Ah
0x180045655  mov     [rbx+130h], rax
0x18004565c  lea     rax, ??_7?$CTSmallVector@PEAVCSBFEvtHolder@SBF2@@@SBF2@@6B@; const SBF2::CTSmallVector<SBF2::CSBFEvtHolder *>::`vftable'
0x180045663  mov     [r13+8], rax
0x180045667  lea     rax, ??_7CSBFEventVectorEx@Cv2ThunkReader@SBFThunk@@6B@; const SBFThunk::Cv2ThunkReader::CSBFEventVectorEx::`vftable'
0x18004566e  mov     [r13+0], rax
0x180045672  mov     [rbx+2D8h], r14
0x180045679  mov     [r15], rdx
0x18004567c  mov     [rbx+2E8h], rdx
0x180045683  mov     [rbx+2D0h], rdx
0x18004568a  call    cs:__imp_InitializeCriticalSection
0x180045690  or      rax, 0FFFFFFFFFFFFFFFFh
0x180045694  mov     dword ptr [rbx+340h], 0FFFFFFFFh
0x18004569e  mov     [rbx+318h], rax
0x1800456a5  xor     r14d, r14d
0x1800456a8  mov     [rbx+320h], rax
0x1800456af  lea     rax, ??_7?$CTSmallVector@PEAVCSBFEvtHolder@SBF2@@@SBF2@@6B@; const SBF2::CTSmallVector<SBF2::CSBFEvtHolder *>::`vftable'
0x1800456b6  mov     [rbx+328h], rax
0x1800456bd  mov     [rbx+330h], r14
0x1800456c4  mov     [rbx+338h], r14
0x1800456cb  cmp     [rdi], r14d
0x1800456ce  jl      short loc_1800456FC
0x1800456d0  mov     ecx, 100h; unsigned __int64
0x1800456d5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800456da  mov     [rbx+330h], rax
0x1800456e1  test    rax, rax
0x1800456e4  jnz     short loc_1800456ED
0x1800456e6  mov     eax, 8007000Eh
0x1800456eb  jmp     short loc_1800456FA
0x1800456ed  mov     eax, r14d
0x1800456f0  mov     dword ptr [rbx+33Ch], 10h
0x1800456fa  mov     [rdi], eax
0x1800456fc  lea     rax, ??_7CStreamCtxPtrMap@SBFThunk@@6B@; const SBFThunk::CStreamCtxPtrMap::`vftable'
0x180045703  mov     [rbx+328h], rax
0x18004570a  lea     rax, ??_7?$CTSmallVector@PEAVCSBFEvtHolder@SBF2@@@SBF2@@6B@; const SBF2::CTSmallVector<SBF2::CSBFEvtHolder *>::`vftable'
0x180045711  mov     [rbx+348h], rax
0x180045718  mov     [rbx+350h], r14
0x18004571f  mov     [rbx+358h], r14
0x180045726  mov     dword ptr [rbx+360h], 0FFFFFFFFh
0x180045730  cmp     [rdi], r14d
0x180045733  jl      short loc_180045761
0x180045735  mov     ecx, 100h; unsigned __int64
0x18004573a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18004573f  mov     [rbx+350h], rax
0x180045746  test    rax, rax
0x180045749  jnz     short loc_180045752
0x18004574b  mov     eax, 8007000Eh
0x180045750  jmp     short loc_18004575F
0x180045752  mov     eax, r14d
0x180045755  mov     dword ptr [rbx+35Ch], 10h
0x18004575f  mov     [rdi], eax
0x180045761  lea     rax, ??_7CPipelineCtxPtrMap@SBFThunk@@6B@; const SBFThunk::CPipelineCtxPtrMap::`vftable'
0x180045768  mov     [rbx+348h], rax
0x18004576f  lea     r14, [rbx+368h]
0x180045776  xor     eax, eax
0x180045778  mov     [rbx+380h], rsi
0x18004577f  mov     [r14], rax
0x180045782  mov     [rbx+370h], rax
0x180045789  mov     [rbx+378h], rax
0x180045790  call    cs:__imp_timeGetTime
0x180045796  mov     [rbx+388h], eax
0x18004579c  xor     esi, esi
0x18004579e  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800457a2  mov     [rbx+3A0h], si
0x1800457a9  mov     [rbx+390h], rax
0x1800457b0  mov     [rbx+398h], rax
0x1800457b7  mov     rax, [rbp+80h+arg_50]
0x1800457be  mov     [rbx+3A8h], rax
0x1800457c5  test    rax, rax
0x1800457c8  jz      short loc_1800457CE
0x1800457ca  lock inc dword ptr [rax+8]
0x1800457ce  mov     rax, [rbx+2D8h]
0x1800457d5  mov     [rsp+180h+var_120], rsi
0x1800457da  lock inc dword ptr [rax+110h]
0x1800457e1  cmp     [rdi], esi
0x1800457e3  jl      loc_180045AAC
0x1800457e9  xor     r9d, r9d; lpName
0x1800457ec  xor     r8d, r8d; bInitialState
0x1800457ef  xor     ecx, ecx; lpEventAttributes
0x1800457f1  lea     edx, [r9+1]; bManualReset
0x1800457f5  call    cs:__imp_CreateEventW
0x1800457fb  mov     [rbx+2E8h], rax
0x180045802  test    rax, rax
0x180045805  jnz     short loc_180045820
0x180045807  call    cs:__imp_GetLastError
0x18004580d  test    eax, eax
0x18004580f  jle     short loc_180045819
0x180045811  movzx   eax, ax
0x180045814  or      eax, 80070000h
0x180045819  mov     [rdi], eax
0x18004581b  jmp     loc_180045AAC
0x180045820  xor     edx, edx; pUnkOuter
0x180045822  mov     [rsp+180h+ppv], r12; ppv
0x180045827  lea     r9, IID_ISBFFile; riid
0x18004582e  lea     rcx, CLSID_SBFCore; rclsid
0x180045835  lea     r8d, [rdx+3]; dwClsContext
0x180045839  call    cs:__imp_CoCreateInstance
0x18004583f  mov     [rdi], eax
0x180045841  test    eax, eax
0x180045843  js      loc_180045AAC
0x180045849  mov     esi, [rbp+80h+arg_38]
0x18004584f  mov     r9, r15; struct SBF2::CSBFPolicy **
0x180045852  mov     r8, [rsp+180h+var_138]; void **
0x180045857  mov     edx, esi; unsigned int
0x180045859  mov     rcx, [rsp+180h+var_130]; struct SBEBasicTracers *
0x18004585e  call    ?CreateInstance@CSBFPolicy@SBF2@@SAJPEAVSBEBasicTracers@@KPEAPEAXPEAPEAV12@@Z; SBF2::CSBFPolicy::CreateInstance(SBEBasicTracers *,ulong,void * *,SBF2::CSBFPolicy * *)
0x180045863  mov     [rdi], eax
0x180045865  test    eax, eax
0x180045867  js      loc_180045AAC
0x18004586d  test    esi, esi
0x18004586f  jz      short loc_1800458C2
0x180045871  mov     rcx, [r12]
0x180045875  lea     r8, [rsp+180h+var_120]
0x18004587a  lea     rdx, IID_IStreamBufferInitialize
0x180045881  mov     rax, [rcx]
0x180045884  mov     rax, [rax]
0x180045887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004588c  mov     [rdi], eax
0x18004588e  test    eax, eax
0x180045890  js      loc_180045AAC
0x180045896  mov     rax, [r15]
0x180045899  mov     rcx, [rsp+180h+var_120]
0x18004589e  mov     rdx, [rax+118h]
0x1800458a5  mov     rax, [rcx]
0x1800458a8  mov     r8, [rdx+10h]
0x1800458ac  mov     edx, [rdx+18h]
0x1800458af  mov     rax, [rax+20h]
0x1800458b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800458b8  mov     [rdi], eax
0x1800458ba  test    eax, eax
0x1800458bc  js      loc_180045AAC
0x1800458c2  mov     rcx, [r12]
0x1800458c6  mov     r9d, 3
0x1800458cc  mov     r8, [rsp+180h+var_140]
0x1800458d1  mov     rdx, [rsp+180h+var_128]
0x1800458d6  mov     dword ptr [rsp+180h+var_158], 7
0x1800458de  mov     rax, [rcx]
0x1800458e1  mov     dword ptr [rsp+180h+ppv], 80000000h
0x1800458e9  mov     rax, [rax+18h]
0x1800458ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800458f2  mov     [rdi], eax
0x1800458f4  mov     esi, eax
0x1800458f6  cmp     eax, 8000FFFFh
0x1800458fb  jz      loc_180045AAC
0x180045901  test    eax, eax
0x180045903  jns     loc_18004598B
0x180045909  mov     r14, [r15]
0x18004590c  lea     rcx, [rsp+180h+var_10F]; void *
0x180045911  xor     edx, edx; Val
0x180045913  mov     [rsp+180h+var_110], 0
0x180045918  mov     r8d, 0CFh; Size
0x18004591e  call    memset_0
0x180045923  lea     r8, aMultimediaDsho_13; "multimedia\\dshow\\filters\\sbe\\dvrfil"...
0x18004592a  lea     rcx, [rsp+180h+var_110]; char *
0x18004592f  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180045934  mov     r15d, 1A7h
0x18004593a  test    eax, eax
0x18004593c  js      short loc_180045956
0x18004593e  lea     rcx, [r14+1A0h]
0x180045945  mov     [rbp+80h+var_48], r15d
0x180045949  lea     rdx, [rsp+180h+var_110]
0x18004594e  mov     [rbp+80h+var_44], esi
0x180045951  call    ?TraceEvent@?$CTeHomeETWEvent@UEH_FATAL_ERROR_EVENT@@@SBEPerf@@QEAAXPEAUEH_FATAL_ERROR_EVENT@@@Z; SBEPerf::CTeHomeETWEvent<EH_FATAL_ERROR_EVENT>::TraceEvent(EH_FATAL_ERROR_EVENT *)
0x180045956  mov     eax, [rdi]
0x180045958  lea     r9, aMultimediaDsho_12; "multimedia\\dshow\\filters\\sbe\\dvrfil"...
0x18004595f  mov     [rsp+180h+var_150], eax
0x180045963  lea     r8, aErrorSUMPisbff; "ERROR: %s(%u); m_pISBFFile -> CreateFil"...
0x18004596a  mov     rax, [rsp+180h+var_140]
0x18004596f  mov     edx, 1; unsigned __int8
0x180045974  mov     [rsp+180h+var_158], rax
0x180045979  mov     dword ptr [rsp+180h+ppv], r15d
0x18004597e  lea     ecx, [rdx+0Fh]; unsigned int
0x180045981  call    ?LogEvent@CSbeFileLog@@SAJKEPEBGZZ; CSbeFileLog::LogEvent(ulong,uchar,ushort const *,...)
0x180045986  jmp     loc_180045AAC
0x18004598b  mov     ecx, 2B0h; Size
0x180045990  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180045995  xor     esi, esi
0x180045997  test    rax, rax
0x18004599a  jz      loc_180045A9F
0x1800459a0  mov     r9, [r12]
0x1800459a4  mov     rcx, rax; this
0x1800459a7  mov     rdx, [r15]
0x1800459aa  mov     [rsp+180h+var_158], rdi; int *
0x1800459af  mov     [rsp+180h+ppv], r13; __int64
0x1800459b4  call    ??0CSBFDShowTimeline@SBF2@@QEAA@PEAVCSBFPolicy@1@PEAGPEAUISBFFile@@AEAV?$CTSBFRefVector@UISBFEvent@@@1@PEAJ@Z; SBF2::CSBFDShowTimeline::CSBFDShowTimeline(SBF2::CSBFPolicy *,ushort *,ISBFFile *,SBF2::CTSBFRefVector<ISBFEvent> &,long *)
0x1800459b9  mov     [rbx+2A0h], rax
0x1800459c0  mov     rcx, rax
0x1800459c3  test    rax, rax
0x1800459c6  jz      loc_180045AA6
0x1800459cc  cmp     [rdi], esi
0x1800459ce  jge     short loc_1800459EA
0x1800459d0  mov     rax, [rax]
0x1800459d3  lea     edx, [rsi+1]
0x1800459d6  mov     rax, [rax]
0x1800459d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800459de  mov     [rbx+2A0h], rsi
0x1800459e5  jmp     loc_180045AAC
0x1800459ea  lea     r8, [rbx+2D0h]
0x1800459f1  mov     rdx, r13
0x1800459f4  mov     rcx, rbx; this
0x1800459f7  call    ?ExtractProfile@Cv2ThunkReader@SBFThunk@@AEAAJAEAV?$CTSBFRefVector@UISBFEvent@@@SBF2@@PEAPEAUIWMProfile@@@Z; SBFThunk::Cv2ThunkReader::ExtractProfile(SBF2::CTSBFRefVector<ISBFEvent> &,IWMProfile * *)
0x1800459fc  mov     [rdi], eax
0x1800459fe  mov     esi, eax
0x180045a00  test    eax, eax
0x180045a02  jns     short loc_180045A50
0x180045a04  mov     rdi, [r15]
0x180045a07  lea     rcx, [rsp+180h+var_10F]; void *
0x180045a0c  xor     edx, edx; Val
0x180045a0e  mov     [rsp+180h+var_110], 0
0x180045a13  mov     r8d, 0CFh; Size
0x180045a19  call    memset_0
0x180045a1e  lea     r8, aMultimediaDsho_13; "multimedia\\dshow\\filters\\sbe\\dvrfil"...
0x180045a25  lea     rcx, [rsp+180h+var_110]; char *
0x180045a2a  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180045a2f  test    eax, eax
0x180045a31  js      short loc_180045AAC
0x180045a33  lea     rcx, [rdi+1A0h]
0x180045a3a  mov     [rbp+80h+var_48], 1B0h
0x180045a41  lea     rdx, [rsp+180h+var_110]
0x180045a46  mov     [rbp+80h+var_44], esi
0x180045a49  call    ?TraceEvent@?$CTeHomeETWEvent@UEH_FATAL_ERROR_EVENT@@@SBEPerf@@QEAAXPEAUEH_FATAL_ERROR_EVENT@@@Z; SBEPerf::CTeHomeETWEvent<EH_FATAL_ERROR_EVENT>::TraceEvent(EH_FATAL_ERROR_EVENT *)
0x180045a4e  jmp     short loc_180045AAC
0x180045a50  mov     rcx, r13
0x180045a53  call    ?Reset@?$CTSBFRefVector@UISBFEvent@@@SBF2@@QEAAXXZ; SBF2::CTSBFRefVector<ISBFEvent>::Reset(void)
0x180045a58  mov     ecx, 48h ; 'H'; Size
0x180045a5d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180045a62  test    rax, rax
0x180045a65  jz      short loc_180045A96
0x180045a67  mov     r8, [r12]; struct ISBFFile *
0x180045a6b  mov     r9, rdi; int *
0x180045a6e  mov     rcx, rax; this
0x180045a71  call    ??0CSBFTimeBasedIndex@SBF2@@QEAA@KPEAUISBFFile@@PEAJ@Z; SBF2::CSBFTimeBasedIndex::CSBFTimeBasedIndex(ulong,ISBFFile *,long *)
0x180045a76  mov     [r14], rax
0x180045a79  test    rax, rax
0x180045a7c  jz      short loc_180045AA6
0x180045a7e  cmp     dword ptr [rdi], 80070490h
0x180045a84  jnz     short loc_180045AAC
0x180045a86  mov     rcx, r14
0x180045a89  call    ??$Delete@VCSBFTimeBasedIndex@SBF2@@@SBF2@@YAXAEAPEAVCSBFTimeBasedIndex@0@@Z; SBF2::Delete<SBF2::CSBFTimeBasedIndex>(SBF2::CSBFTimeBasedIndex * &)
0x180045a8e  mov     dword ptr [rdi], 0
0x180045a94  jmp     short loc_180045AAC
0x180045a96  mov     qword ptr [r14], 0
0x180045a9d  jmp     short loc_180045AA6
0x180045a9f  mov     [rbx+2A0h], rsi
0x180045aa6  mov     dword ptr [rdi], 8007000Eh
0x180045aac  lea     rcx, [rsp+180h+var_120]
0x180045ab1  call    ?Release@?$TPtr@UIEhTraceSpan@@@EhEtw@@QEAAXXZ; EhEtw::TPtr<IEhTraceSpan>::Release(void)
0x180045ab6  mov     rax, rbx
  ... truncated ...
```
