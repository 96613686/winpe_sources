# SBE2PauseBuffer::CSBE2PauseBufferReader::CSBE2PauseBufferReader(SBEPerf::CeHomeETWSBE2PauseBuffer *,IUnknown *,CDVRPolicy *,CDVRCrossbar *,IFilterGraph *,SBE2PauseBuffer::Cv2StubMM *,long *)

- ea: `0x1800aa9c8`
- end: `0x1800aac8c`
- name: `??0CSBE2PauseBufferReader@SBE2PauseBuffer@@IEAA@PEAVCeHomeETWSBE2PauseBuffer@SBEPerf@@PEAUIUnknown@@PEAVCDVRPolicy@@PEAVCDVRCrossbar@@PEAUIFilterGraph@@PEAVCv2StubMM@1@PEAJ@Z`
- size: `708`
- prototype: `__int64 __usercall@<rax>(SBE2PauseBuffer::CSBE2PauseBufferReader *__hidden this@<rcx>, struct SBEPerf::CeHomeETWSBE2PauseBuffer *@<rdx>, struct IUnknown *@<r8>, struct CDVRPolicy *@<r9>, struct CDVRCrossbar *, struct IFilterGraph *, struct SBE2PauseBuffer::Cv2StubMM *, int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800ab2d4`

## callees

- `0x180007120`
- `0x1800072c4`
- `0x18002573c`
- `0x180044ec8`
- `0x18006201c`
- `0x1800627f0`
- `0x18007eac8`
- `0x1800aa9c8`
- `0x1800aae88`
- `0x1800ab23c`
- `0x1800abf60`
- `0x1800ac228`
- `0x1800aff04`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!CreateThread` at `0x1800aab91`
- `KERNEL32!CreateThread` at `0x1800aab91`
- `KERNEL32!CreateEventW` at `0x1800aab31`
- `KERNEL32!CreateEventW` at `0x1800aab31`
- `KERNEL32!InitializeCriticalSection` at `0x1800aaa93`
- `KERNEL32!InitializeCriticalSection` at `0x1800aaa93`
- `KERNEL32!GetLastError` at `0x1800aab43`
- `KERNEL32!GetLastError` at `0x1800aaba3`
- `KERNEL32!GetLastError` at `0x1800aab43`
- `KERNEL32!GetLastError` at `0x1800aaba3`

## string_xrefs

- `0x1800aab65`: `multimedia\dshow\filters\sbe\pausebuffer\pbreader.cpp`

## pseudocode

```c
SBE2PauseBuffer::CSBE2PauseBufferReader *__fastcall SBE2PauseBuffer::CSBE2PauseBufferReader::CSBE2PauseBufferReader(
        SBE2PauseBuffer::CSBE2PauseBufferReader *this,
        struct SBEPerf::CeHomeETWSBE2PauseBuffer *a2,
        struct IUnknown *a3,
        struct CDVRPolicy *a4,
        struct CDVRCrossbar *a5,
        struct IFilterGraph *a6,
        struct SBE2PauseBuffer::Cv2StubMM *a7,
        int *a8)
{
  struct IFilterGraph *v12; // rax
  struct CDVRCrossbar *v13; // rax
  int *v14; // r13
  int Instance; // ebx
  __int64 v16; // rdx
  HANDLE EventW; // rax
  signed int LastError; // eax
  unsigned int v19; // r8d
  HANDLE Thread; // rax
  signed int v21; // eax
  __int64 v22; // rax
  struct SBEPerf::CeHomeETWSBE2PauseBuffer *v24; // [rsp+88h] [rbp+10h] BYREF

  v24 = a2;
  SBEBasicTracers::SBEBasicTracers(this, a4);
  _InterlockedIncrement(&CBaseObject::m_cObjects);
  *((_QWORD *)this + 34) = (char *)this + 264;
  *((_DWORD *)this + 70) = 0;
  *(_QWORD *)this = &SBE2PauseBuffer::CSBE2PauseBufferReader::`vftable'{for `SBEBasicTracers'};
  *((_QWORD *)this + 33) = &SBE2PauseBuffer::CSBE2PauseBufferReader::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 36) = &SBE2PauseBuffer::CSBE2PauseBufferReader::`vftable'{for `IDVRReader'};
  *((_QWORD *)this + 37) = &SBE2PauseBuffer::CSBE2PauseBufferReader::`vftable'{for `IDVRReaderNotify'};
  *((_QWORD *)this + 38) = 0;
  CAMEvent::CAMEvent((SBE2PauseBuffer::CSBE2PauseBufferReader *)((char *)this + 312), 0, 0);
  *((_QWORD *)this + 40) = a4;
  if ( a4 )
    _InterlockedIncrement((volatile signed __int32 *)a4 + 68);
  *((_DWORD *)this + 88) = 0;
  *((_QWORD *)this + 43) = (char *)this + 336;
  *((_QWORD *)this + 42) = (char *)this + 336;
  *((_QWORD *)this + 41) = &SBECoreUtil::LISTENTRYList<SBE2PauseBuffer::CSBE2PBNodeReader>::`vftable';
  InitializeCriticalSection((LPCRITICAL_SECTION)this + 9);
  v12 = a6;
  *((_QWORD *)this + 50) = a2;
  *((_DWORD *)this + 102) = 0;
  *((_DWORD *)this + 103) = 0;
  *((_QWORD *)this + 52) = 0;
  *((_QWORD *)this + 53) = 0;
  *((_QWORD *)this + 54) = 0;
  *((_QWORD *)this + 55) = 0;
  *((_QWORD *)this + 56) = v12;
  v13 = a5;
  *((_QWORD *)this + 58) = a3;
  *((_QWORD *)this + 59) = v13;
  *((_QWORD *)this + 60) = 0;
  v14 = a8;
  Instance = *a8;
  SBECoreUtil::AddRef<SBEPerf::CeHomeETWSBE2PauseBuffer *>();
  SBF2::AddRef<ISBFEvent *>(v16);
  if ( Instance >= 0 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 53) = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      Instance = LastError;
      if ( LastError > 0 )
        Instance = (unsigned __int16)LastError | 0x80070000;
      v19 = 144;
LABEL_8:
      SBEBasicTracers::EtwTraceError(
        (SBE2PauseBuffer::CSBE2PauseBufferReader *)((char *)this + 48),
        "multimedia\\dshow\\filters\\sbe\\pausebuffer\\pbreader.cpp",
        v19,
        Instance);
      goto LABEL_18;
    }
    Thread = CreateThread(
               0,
               0,
               SBE2PauseBuffer::CSBE2PauseBufferReader::WorkerThreadThunk,
               this,
               0,
               (LPDWORD)this + 103);
    *((_QWORD *)this + 52) = Thread;
    if ( !Thread )
    {
      v21 = GetLastError();
      Instance = v21;
      if ( v21 > 0 )
        Instance = (unsigned __int16)v21 | 0x80070000;
      v19 = 147;
      goto LABEL_8;
    }
    Instance = (***((__int64 (__fastcall ****)(_QWORD, GUID *, char *))this + 56))(
                 *((_QWORD *)this + 56),
                 &GUID_56a868a2_0ad4_11ce_b03a_0020af0ba770,
                 (char *)this + 456);
    if ( Instance >= 0 )
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 57) + 16LL))(*((_QWORD *)this + 57));
      SAL2::Release<SAL2::CSALResidentNVP *>((char *)this + 304);
      Instance = SBE2PauseBuffer::Cv2StubReader::CreateInstance(v24, a7, a4, (struct Cv2StubReader **)this + 38);
      if ( Instance >= 0 )
      {
        SAL2::Release<SAL2::CSALResidentNVP *>((char *)this + 480);
        Instance = SBE2PauseBuffer::CSBE2PauseBufferExtentReporter::CreateInstance(
                     this,
                     (struct SBE2PauseBuffer::CSBE2PauseBufferExtentReporter **)this + 60);
        if ( Instance >= 0 )
        {
          Instance = SBE2PauseBuffer::CSBE2PauseBufferReader::SyncFifoToStub(this);
          if ( Instance >= 0 )
          {
            v22 = SBE2PauseBuffer::CSBE2PauseBufferReader::OldestFifo(this, &v24);
            SBECoreUtil::autoref<SBE2PauseBuffer::CSBE2PBNodeReader>::operator=((char *)this + 440, v22);
            SAL2::Release<SAL2::CSALPoolGrow *>(&v24);
          }
        }
      }
    }
  }
LABEL_18:
  *v14 = Instance;
  return this;
}

```

## disassembly

```asm
0x1800aa9c8  mov     [rsp+arg_8], rdx
0x1800aa9cd  push    rbx
0x1800aa9ce  push    rbp
0x1800aa9cf  push    rsi
0x1800aa9d0  push    rdi
0x1800aa9d1  push    r12
0x1800aa9d3  push    r13
0x1800aa9d5  push    r14
0x1800aa9d7  push    r15
0x1800aa9d9  sub     rsp, 38h
0x1800aa9dd  mov     r14, rdx
0x1800aa9e0  mov     rsi, r9
0x1800aa9e3  mov     rdx, r9; struct SBEBasicTracers *
0x1800aa9e6  mov     rbx, r8
0x1800aa9e9  mov     rdi, rcx
0x1800aa9ec  call    ??0SBEBasicTracers@@QEAA@PEBV0@@Z; SBEBasicTracers::SBEBasicTracers(SBEBasicTracers const *)
0x1800aa9f1  lea     rax, [rdi+108h]
0x1800aa9f8  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x1800aa9ff  mov     [rax+8], rax
0x1800aaa03  lea     rcx, ??_7CSBE2PauseBufferReader@SBE2PauseBuffer@@6BSBEBasicTracers@@@; const SBE2PauseBuffer::CSBE2PauseBufferReader::`vftable'{for `SBEBasicTracers'}
0x1800aaa0a  xor     r13d, r13d
0x1800aaa0d  lea     rbp, [rdi+130h]
0x1800aaa14  mov     [rax+10h], r13d
0x1800aaa18  xor     r8d, r8d; int *
0x1800aaa1b  mov     [rdi], rcx
0x1800aaa1e  xor     edx, edx; int
0x1800aaa20  lea     rcx, ??_7CSBE2PauseBufferReader@SBE2PauseBuffer@@6BCUnknown@@@; const SBE2PauseBuffer::CSBE2PauseBufferReader::`vftable'{for `CUnknown'}
0x1800aaa27  mov     [rax], rcx
0x1800aaa2a  lea     rax, ??_7CSBE2PauseBufferReader@SBE2PauseBuffer@@6BIDVRReader@@@; const SBE2PauseBuffer::CSBE2PauseBufferReader::`vftable'{for `IDVRReader'}
0x1800aaa31  mov     [rdi+120h], rax
0x1800aaa38  lea     rcx, [rdi+138h]; this
0x1800aaa3f  lea     rax, ??_7CSBE2PauseBufferReader@SBE2PauseBuffer@@6BIDVRReaderNotify@@@; const SBE2PauseBuffer::CSBE2PauseBufferReader::`vftable'{for `IDVRReaderNotify'}
0x1800aaa46  mov     [rdi+128h], rax
0x1800aaa4d  mov     [rbp+0], r13
0x1800aaa51  call    ??0CAMEvent@@QEAA@HPEAJ@Z; CAMEvent::CAMEvent(int,long *)
0x1800aaa56  mov     [rdi+140h], rsi
0x1800aaa5d  test    rsi, rsi
0x1800aaa60  jz      short loc_1800AAA69
0x1800aaa62  lock inc dword ptr [rsi+110h]
0x1800aaa69  lea     rax, [rdi+150h]
0x1800aaa70  mov     [rdi+160h], r13d
0x1800aaa77  mov     [rax+8], rax
0x1800aaa7b  lea     rcx, [rdi+168h]; lpCriticalSection
0x1800aaa82  mov     [rax], rax
0x1800aaa85  lea     rax, ??_7?$LISTENTRYList@VCSBE2PBNodeReader@SBE2PauseBuffer@@@SBECoreUtil@@6B@; const SBECoreUtil::LISTENTRYList<SBE2PauseBuffer::CSBE2PBNodeReader>::`vftable'
0x1800aaa8c  mov     [rdi+148h], rax
0x1800aaa93  call    cs:__imp_InitializeCriticalSection
0x1800aaa99  mov     rax, [rsp+78h+arg_28]
0x1800aaaa1  lea     rcx, [rdi+190h]
0x1800aaaa8  mov     [rcx], r14
0x1800aaaab  lea     r15, [rdi+19Ch]
0x1800aaab2  mov     [rdi+198h], r13d
0x1800aaab9  lea     r12, [rdi+1B8h]
0x1800aaac0  mov     [r15], r13d
0x1800aaac3  lea     rdx, [rdi+1D0h]
0x1800aaaca  mov     [rdi+1A0h], r13
0x1800aaad1  lea     r14, [rdi+1E0h]
0x1800aaad8  mov     [rdi+1A8h], r13
0x1800aaadf  mov     [rdi+1B0h], r13
0x1800aaae6  mov     [r12], r13
0x1800aaaea  mov     [rdi+1C0h], rax
0x1800aaaf1  mov     rax, [rsp+78h+arg_20]
0x1800aaaf9  mov     [rdx], rbx
0x1800aaafc  mov     [rdi+1D8h], rax
0x1800aab03  mov     [r14], r13
0x1800aab06  mov     r13, [rsp+78h+arg_38]
0x1800aab0e  mov     ebx, [r13+0]
0x1800aab12  call    ??$AddRef@PEAVCeHomeETWSBE2PauseBuffer@SBEPerf@@@SBECoreUtil@@YAXAEAPEAVCeHomeETWSBE2PauseBuffer@SBEPerf@@@Z; SBECoreUtil::AddRef<SBEPerf::CeHomeETWSBE2PauseBuffer *>(SBEPerf::CeHomeETWSBE2PauseBuffer * &)
0x1800aab17  mov     rcx, rdx
0x1800aab1a  call    ??$AddRef@PEAUISBFEvent@@@SBF2@@YAXAEAPEAUISBFEvent@@@Z; SBF2::AddRef<ISBFEvent *>(ISBFEvent * &)
0x1800aab1f  test    ebx, ebx
0x1800aab21  js      loc_1800AAC74
0x1800aab27  xor     r9d, r9d; lpName
0x1800aab2a  xor     r8d, r8d; bInitialState
0x1800aab2d  xor     edx, edx; bManualReset
0x1800aab2f  xor     ecx, ecx; lpEventAttributes
0x1800aab31  call    cs:__imp_CreateEventW
0x1800aab37  mov     [rdi+1A8h], rax
0x1800aab3e  test    rax, rax
0x1800aab41  jnz     short loc_1800AAB76
0x1800aab43  call    cs:__imp_GetLastError
0x1800aab49  mov     ebx, eax
0x1800aab4b  test    eax, eax
0x1800aab4d  jle     short loc_1800AAB58
0x1800aab4f  movzx   ebx, ax
0x1800aab52  or      ebx, 80070000h
0x1800aab58  mov     r8d, 90h; unsigned int
0x1800aab5e  mov     r9d, ebx; unsigned int
0x1800aab61  lea     rcx, [rdi+30h]; struct CEhEventTracer *
0x1800aab65  lea     rdx, aMultimediaDsho_3; "multimedia\\dshow\\filters\\sbe\\pauseb"...
0x1800aab6c  call    ?EtwTraceError@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDKK@Z; SBEBasicTracers::EtwTraceError(CEhEventTracer &,char const *,ulong,ulong)
0x1800aab71  jmp     loc_1800AAC74
0x1800aab76  mov     [rsp+78h+lpThreadId], r15; lpThreadId
0x1800aab7b  lea     r8, ?WorkerThreadThunk@CSBE2PauseBufferReader@SBE2PauseBuffer@@CAKPEAX@Z; lpStartAddress
0x1800aab82  mov     r9, rdi; lpParameter
0x1800aab85  mov     [rsp+78h+dwCreationFlags], 0; dwCreationFlags
0x1800aab8d  xor     edx, edx; dwStackSize
0x1800aab8f  xor     ecx, ecx; lpThreadAttributes
0x1800aab91  call    cs:__imp_CreateThread
0x1800aab97  mov     [rdi+1A0h], rax
0x1800aab9e  test    rax, rax
0x1800aaba1  jnz     short loc_1800AABC0
0x1800aaba3  call    cs:__imp_GetLastError
0x1800aaba9  mov     ebx, eax
0x1800aabab  test    eax, eax
0x1800aabad  jle     short loc_1800AABB8
0x1800aabaf  movzx   ebx, ax
0x1800aabb2  or      ebx, 80070000h
0x1800aabb8  mov     r8d, 93h
0x1800aabbe  jmp     short loc_1800AAB5E
0x1800aabc0  mov     rcx, [rdi+1C0h]
0x1800aabc7  lea     r15, [rdi+1C8h]
0x1800aabce  mov     r8, r15
0x1800aabd1  lea     rdx, _GUID_56a868a2_0ad4_11ce_b03a_0020af0ba770
0x1800aabd8  mov     rax, [rcx]
0x1800aabdb  mov     rax, [rax]
0x1800aabde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aabe3  mov     ebx, eax
0x1800aabe5  test    eax, eax
0x1800aabe7  js      loc_1800AAC74
0x1800aabed  mov     rcx, [r15]
0x1800aabf0  mov     rax, [rcx]
0x1800aabf3  mov     rax, [rax+10h]
0x1800aabf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aabfc  mov     rcx, rbp
0x1800aabff  call    ??$Release@PEAVCSALResidentNVP@SAL2@@@SAL2@@YAXAEAPEAVCSALResidentNVP@0@@Z; SAL2::Release<SAL2::CSALResidentNVP *>(SAL2::CSALResidentNVP * &)
0x1800aac04  mov     rdx, [rsp+78h+arg_30]; struct SBE2PauseBuffer::Cv2StubMM *
0x1800aac0c  mov     r9, rbp; struct Cv2StubReader **
0x1800aac0f  mov     rcx, [rsp+78h+arg_8]; struct SBEPerf::CeHomeETWSBE2PauseBuffer *
0x1800aac17  mov     r8, rsi; struct CDVRPolicy *
0x1800aac1a  call    ?CreateInstance@Cv2StubReader@SBE2PauseBuffer@@SAJPEAVCeHomeETWSBE2PauseBuffer@SBEPerf@@PEAVCv2StubMM@2@PEAVCDVRPolicy@@PEAPEAV12@@Z; SBE2PauseBuffer::Cv2StubReader::CreateInstance(SBEPerf::CeHomeETWSBE2PauseBuffer *,SBE2PauseBuffer::Cv2StubMM *,CDVRPolicy *,SBE2PauseBuffer::Cv2StubReader * *)
0x1800aac1f  mov     ebx, eax
0x1800aac21  test    eax, eax
0x1800aac23  js      short loc_1800AAC74
0x1800aac25  mov     rcx, r14
0x1800aac28  call    ??$Release@PEAVCSALResidentNVP@SAL2@@@SAL2@@YAXAEAPEAVCSALResidentNVP@0@@Z; SAL2::Release<SAL2::CSALResidentNVP *>(SAL2::CSALResidentNVP * &)
0x1800aac2d  mov     rdx, r14; struct SBE2PauseBuffer::CSBE2PauseBufferExtentReporter **
0x1800aac30  mov     rcx, rdi; struct SBE2PauseBuffer::CSBE2PauseBufferReader *
0x1800aac33  call    ?CreateInstance@CSBE2PauseBufferExtentReporter@SBE2PauseBuffer@@SAJPEAVCSBE2PauseBufferReader@2@PEAPEAV12@@Z; SBE2PauseBuffer::CSBE2PauseBufferExtentReporter::CreateInstance(SBE2PauseBuffer::CSBE2PauseBufferReader *,SBE2PauseBuffer::CSBE2PauseBufferExtentReporter * *)
0x1800aac38  mov     ebx, eax
0x1800aac3a  test    eax, eax
0x1800aac3c  js      short loc_1800AAC74
0x1800aac3e  mov     rcx, rdi; this
0x1800aac41  call    ?SyncFifoToStub@CSBE2PauseBufferReader@SBE2PauseBuffer@@AEAAJXZ; SBE2PauseBuffer::CSBE2PauseBufferReader::SyncFifoToStub(void)
0x1800aac46  mov     ebx, eax
0x1800aac48  test    eax, eax
0x1800aac4a  js      short loc_1800AAC74
0x1800aac4c  lea     rdx, [rsp+78h+arg_8]
0x1800aac54  mov     rcx, rdi
0x1800aac57  call    ?OldestFifo@CSBE2PauseBufferReader@SBE2PauseBuffer@@AEAA?AV?$autoref@VCSBE2PBNodeReader@SBE2PauseBuffer@@@SBECoreUtil@@XZ; SBE2PauseBuffer::CSBE2PauseBufferReader::OldestFifo(void)
0x1800aac5c  mov     rdx, rax
0x1800aac5f  mov     rcx, r12
0x1800aac62  call    ??4?$autoref@VCSBE2PBNodeReader@SBE2PauseBuffer@@@SBECoreUtil@@QEAAAEAV01@AEBV01@@Z; SBECoreUtil::autoref<SBE2PauseBuffer::CSBE2PBNodeReader>::operator=(SBECoreUtil::autoref<SBE2PauseBuffer::CSBE2PBNodeReader> const &)
0x1800aac67  lea     rcx, [rsp+78h+arg_8]
0x1800aac6f  call    ??$Release@PEAVCSALPoolGrow@SAL2@@@SAL2@@YAXAEAPEAVCSALPoolGrow@0@@Z; SAL2::Release<SAL2::CSALPoolGrow *>(SAL2::CSALPoolGrow * &)
0x1800aac74  mov     [r13+0], ebx
0x1800aac78  mov     rax, rdi
0x1800aac7b  add     rsp, 38h
0x1800aac7f  pop     r15
0x1800aac81  pop     r14
0x1800aac83  pop     r13
0x1800aac85  pop     r12
0x1800aac87  pop     rdi
0x1800aac88  pop     rsi
0x1800aac89  pop     rbp
0x1800aac8a  pop     rbx
0x1800aac8b  retn
```
