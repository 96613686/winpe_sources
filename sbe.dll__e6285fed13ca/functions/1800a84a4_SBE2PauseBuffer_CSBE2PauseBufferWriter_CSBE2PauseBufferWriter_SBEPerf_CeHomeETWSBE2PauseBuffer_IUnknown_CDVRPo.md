# SBE2PauseBuffer::CSBE2PauseBufferWriter::CSBE2PauseBufferWriter(SBEPerf::CeHomeETWSBE2PauseBuffer *,IUnknown *,CDVRPolicy *,ushort *,long *)

- ea: `0x1800a84a4`
- end: `0x1800a87bc`
- name: `??0CSBE2PauseBufferWriter@SBE2PauseBuffer@@IEAA@PEAVCeHomeETWSBE2PauseBuffer@SBEPerf@@PEAUIUnknown@@PEAVCDVRPolicy@@PEAGPEAJ@Z`
- size: `792`
- prototype: `__int64 __usercall@<rax>(SBE2PauseBuffer::CSBE2PauseBufferWriter *__hidden this@<rcx>, struct SBEPerf::CeHomeETWSBE2PauseBuffer *@<rdx>, struct IUnknown *@<r8>, struct CDVRPolicy *@<r9>, unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800a8c78`

## callees

- `0x18002573c`
- `0x18002d050`
- `0x180044ec8`
- `0x180061ef0`
- `0x18006201c`
- `0x180062710`
- `0x1800627f0`
- `0x18007eac8`
- `0x1800a84a4`
- `0x1800a8ba4`
- `0x1800affd0`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x1800a8595`
- `KERNEL32!InitializeCriticalSection` at `0x1800a85c5`
- `KERNEL32!InitializeCriticalSection` at `0x1800a8595`
- `KERNEL32!InitializeCriticalSection` at `0x1800a85c5`
- `KERNEL32!GetLastError` at `0x1800a867d`
- `KERNEL32!GetLastError` at `0x1800a867d`
- `KERNEL32!CreateMutexW` at `0x1800a866b`
- `KERNEL32!CreateMutexW` at `0x1800a866b`

## string_xrefs

- `0x1800a861d`: `multimedia\dshow\filters\sbe\pausebuffer\pbwriter.cpp`
- `0x1800a877d`: `multimedia\dshow\filters\sbe\pausebuffer\pbwriter.cpp`

## pseudocode

```c
SBE2PauseBuffer::CSBE2PauseBufferWriter *__fastcall SBE2PauseBuffer::CSBE2PauseBufferWriter::CSBE2PauseBufferWriter(
        SBE2PauseBuffer::CSBE2PauseBufferWriter *this,
        struct SBEPerf::CeHomeETWSBE2PauseBuffer *a2,
        struct IUnknown *a3,
        struct CDVRPolicy *a4,
        unsigned __int16 *a5,
        int *a6)
{
  char *v10; // r14
  signed int v11; // ebx
  unsigned int v12; // r8d
  unsigned int v13; // r9d
  __int64 v14; // rax
  HANDLE MutexW; // rax
  int v16; // r8d
  signed int LastError; // eax
  int v18; // ebx
  int v19; // r8d
  unsigned __int64 v20; // rdx
  int v21; // eax
  int Instance; // eax

  SBEBasicTracers::SBEBasicTracers(this, a4);
  _InterlockedIncrement(&CBaseObject::m_cObjects);
  *((_QWORD *)this + 34) = (char *)this + 264;
  *((_DWORD *)this + 70) = 0;
  *(_QWORD *)this = &SBE2PauseBuffer::CSBE2PauseBufferWriter::`vftable'{for `SBEBasicTracers'};
  *((_QWORD *)this + 33) = &SBE2PauseBuffer::CSBE2PauseBufferWriter::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 36) = &SBE2PauseBuffer::CSBE2PauseBufferWriter::`vftable'{for `IPauseBuffer'};
  *((_DWORD *)this + 76) = 0;
  *((_QWORD *)this + 37) = &SBE2PauseBuffer::CSBE2PauseBufferWriter::`vftable'{for `IPauseBufferWriter'};
  *((_QWORD *)this + 39) = 0;
  *((_QWORD *)this + 40) = 0;
  *((_QWORD *)this + 106) = a3;
  *((_QWORD *)this + 107) = a2;
  *((_DWORD *)this + 222) = 0;
  *((_QWORD *)this + 110) = (char *)this + 872;
  *((_QWORD *)this + 109) = (char *)this + 872;
  *((_QWORD *)this + 108) = &SBECoreUtil::LISTENTRYList<SBE2PauseBuffer::CSBE2PBNodeReader>::`vftable';
  *((_DWORD *)this + 224) = 0;
  *((_QWORD *)this + 113) = 0;
  *((_QWORD *)this + 114) = 0;
  *((_DWORD *)this + 230) = 0;
  *((_WORD *)this + 462) = 0;
  *((_QWORD *)this + 116) = -1;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 936));
  *((_QWORD *)this + 122) = 0;
  *((_QWORD *)this + 123) = 0;
  *((_QWORD *)this + 124) = 0;
  *((_DWORD *)this + 250) = 0;
  *((_QWORD *)this + 126) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 1016));
  v10 = (char *)this + 1056;
  *((_QWORD *)this + 132) = 0;
  *((_QWORD *)this + 133) = a4;
  if ( a4 )
    _InterlockedIncrement((volatile signed __int32 *)a4 + 68);
  *((_WORD *)this + 164) = 0;
  v11 = *a6;
  SBF2::AddRef<ISBFEvent *>((char *)this + 848);
  SBECoreUtil::AddRef<SBEPerf::CeHomeETWSBE2PauseBuffer *>((char *)this + 856);
  if ( v11 < 0 )
  {
    v12 = 78;
LABEL_5:
    v13 = v11;
LABEL_6:
    SBEBasicTracers::EtwTraceError(
      (SBE2PauseBuffer::CSBE2PauseBufferWriter *)((char *)this + 88),
      "multimedia\\dshow\\filters\\sbe\\pausebuffer\\pbwriter.cpp",
      v12,
      v13);
    goto LABEL_21;
  }
  v14 = *((_QWORD *)this + 133);
  if ( !v14 )
  {
    v11 = -2147467261;
    v12 = 82;
    v13 = -2147467261;
    goto LABEL_6;
  }
  if ( v14 == -328 )
  {
    v11 = -2147467261;
    v12 = 83;
    v13 = -2147467261;
    goto LABEL_6;
  }
  MutexW = CreateMutexW(0, 0, 0);
  *((_QWORD *)this + 126) = MutexW;
  if ( !MutexW )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    v12 = 87;
    goto LABEL_5;
  }
  v18 = CTSDVRSettings::DVRGetVal_(
          (int)a4 + 328,
          (unsigned int)L"BackingStoreMaxNumBackingFiles",
          v16,
          8,
          4,
          256,
          (__int64)a4 + 920);
  *((_QWORD *)this + 40) = 10000000LL
                         * v18
                         * (unsigned int)CTSDVRSettings::DVRGetVal_(
                                           (int)a4 + 328,
                                           (unsigned int)L"BackingStoreEachFileDurationSeconds",
                                           v19,
                                           300,
                                           5,
                                           -1,
                                           (__int64)a4 + 928);
  v21 = SBE2PauseBuffer::CSBE2PauseBufferWriter::ConfigureTMPDirectory(this, v20);
  v11 = v21;
  if ( v21 < 0 )
  {
    v13 = v21;
    v12 = 90;
    goto LABEL_6;
  }
  SAL2::Release<SAL2::CSALResidentNVP *>((char *)this + 1056);
  Instance = SBE2PauseBuffer::Cv2StubWriter::CreateInstance(
               a2,
               a5,
               a4,
               (struct SBE2PauseBuffer::Cv2StubWriter **)this + 132);
  v11 = Instance;
  if ( Instance < 0 )
  {
    v13 = Instance;
    v12 = 91;
    goto LABEL_6;
  }
  if ( !*(_QWORD *)v10 )
    SBEBasicTracers::EtwTraceAssert(
      (SBE2PauseBuffer::CSBE2PauseBufferWriter *)((char *)this + 88),
      "multimedia\\dshow\\filters\\sbe\\pausebuffer\\pbwriter.cpp",
      0x5Cu);
LABEL_21:
  if ( *(_QWORD *)v10 )
    SBECoreUtil::CMutexLock::Unlock(*(SBECoreUtil::CMutexLock **)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v10 + 56LL) + 16LL)
                                                                + 320LL));
  *a6 = v11;
  return this;
}

```

## disassembly

```asm
0x1800a84a4  push    rbx
0x1800a84a6  push    rbp
0x1800a84a7  push    rsi
0x1800a84a8  push    rdi
0x1800a84a9  push    r12
0x1800a84ab  push    r13
0x1800a84ad  push    r14
0x1800a84af  push    r15
0x1800a84b1  sub     rsp, 48h
0x1800a84b5  mov     r13, rdx
0x1800a84b8  mov     rbp, r9
0x1800a84bb  mov     rdx, r9; struct SBEBasicTracers *
0x1800a84be  mov     rbx, r8
0x1800a84c1  mov     rsi, rcx
0x1800a84c4  call    ??0SBEBasicTracers@@QEAA@PEBV0@@Z; SBEBasicTracers::SBEBasicTracers(SBEBasicTracers const *)
0x1800a84c9  lea     rax, [rsi+108h]
0x1800a84d0  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x1800a84d7  mov     [rax+8], rax
0x1800a84db  lea     rcx, ??_7CSBE2PauseBufferWriter@SBE2PauseBuffer@@6BSBEBasicTracers@@@; const SBE2PauseBuffer::CSBE2PauseBufferWriter::`vftable'{for `SBEBasicTracers'}
0x1800a84e2  xor     r15d, r15d
0x1800a84e5  lea     rdi, [rsi+350h]
0x1800a84ec  mov     [rax+10h], r15d
0x1800a84f0  lea     r12, [rsi+358h]
0x1800a84f7  mov     [rsi], rcx
0x1800a84fa  lea     rcx, ??_7CSBE2PauseBufferWriter@SBE2PauseBuffer@@6BCUnknown@@@; const SBE2PauseBuffer::CSBE2PauseBufferWriter::`vftable'{for `CUnknown'}
0x1800a8501  mov     [rax], rcx
0x1800a8504  lea     rax, ??_7CSBE2PauseBufferWriter@SBE2PauseBuffer@@6BIPauseBuffer@@@; const SBE2PauseBuffer::CSBE2PauseBufferWriter::`vftable'{for `IPauseBuffer'}
0x1800a850b  mov     [rsi+120h], rax
0x1800a8512  lea     rcx, [rsi+3A8h]; lpCriticalSection
0x1800a8519  mov     [rsi+130h], r15d
0x1800a8520  lea     rax, ??_7CSBE2PauseBufferWriter@SBE2PauseBuffer@@6BIPauseBufferWriter@@@; const SBE2PauseBuffer::CSBE2PauseBufferWriter::`vftable'{for `IPauseBufferWriter'}
0x1800a8527  mov     [rsi+128h], rax
0x1800a852e  lea     rax, [rsi+368h]
0x1800a8535  mov     [rsi+138h], r15
0x1800a853c  mov     [rsi+140h], r15
0x1800a8543  mov     [rdi], rbx
0x1800a8546  mov     [r12], r13
0x1800a854a  mov     [rsi+378h], r15d
0x1800a8551  mov     [rax+8], rax
0x1800a8555  mov     [rax], rax
0x1800a8558  lea     rax, ??_7?$LISTENTRYList@VCSBE2PBNodeReader@SBE2PauseBuffer@@@SBECoreUtil@@6B@; const SBECoreUtil::LISTENTRYList<SBE2PauseBuffer::CSBE2PBNodeReader>::`vftable'
0x1800a855f  mov     [rsi+360h], rax
0x1800a8566  mov     [rsi+380h], r15d
0x1800a856d  mov     [rsi+388h], r15
0x1800a8574  mov     [rsi+390h], r15
0x1800a857b  mov     [rsi+398h], r15d
0x1800a8582  mov     [rsi+39Ch], r15w
0x1800a858a  mov     qword ptr [rsi+3A0h], 0FFFFFFFFFFFFFFFFh
0x1800a8595  call    cs:__imp_InitializeCriticalSection
0x1800a859b  lea     rcx, [rsi+3F8h]; lpCriticalSection
0x1800a85a2  mov     [rsi+3D0h], r15
0x1800a85a9  mov     [rsi+3D8h], r15
0x1800a85b0  mov     [rsi+3E0h], r15
0x1800a85b7  mov     [rsi+3E8h], r15d
0x1800a85be  mov     [rsi+3F0h], r15
0x1800a85c5  call    cs:__imp_InitializeCriticalSection
0x1800a85cb  lea     r14, [rsi+420h]
0x1800a85d2  mov     [r14], r15
0x1800a85d5  mov     [rsi+428h], rbp
0x1800a85dc  test    rbp, rbp
0x1800a85df  jz      short loc_1800A85E8
0x1800a85e1  lock inc dword ptr [rbp+110h]
0x1800a85e8  mov     r15, [rsp+88h+arg_28]
0x1800a85f0  xor     eax, eax
0x1800a85f2  mov     rcx, rdi
0x1800a85f5  mov     [rsi+148h], ax
0x1800a85fc  mov     ebx, [r15]
0x1800a85ff  call    ??$AddRef@PEAUISBFEvent@@@SBF2@@YAXAEAPEAUISBFEvent@@@Z; SBF2::AddRef<ISBFEvent *>(ISBFEvent * &)
0x1800a8604  mov     rcx, r12
0x1800a8607  call    ??$AddRef@PEAVCeHomeETWSBE2PauseBuffer@SBEPerf@@@SBECoreUtil@@YAXAEAPEAVCeHomeETWSBE2PauseBuffer@SBEPerf@@@Z; SBECoreUtil::AddRef<SBEPerf::CeHomeETWSBE2PauseBuffer *>(SBEPerf::CeHomeETWSBE2PauseBuffer * &)
0x1800a860c  test    ebx, ebx
0x1800a860e  jns     short loc_1800A862E
0x1800a8610  mov     r8d, 4Eh ; 'N'; unsigned int
0x1800a8616  mov     r9d, ebx; unsigned int
0x1800a8619  lea     rcx, [rsi+58h]; struct CEhEventTracer *
0x1800a861d  lea     rdx, aMultimediaDsho_27; "multimedia\\dshow\\filters\\sbe\\pauseb"...
0x1800a8624  call    ?EtwTraceError@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDKK@Z; SBEBasicTracers::EtwTraceError(CEhEventTracer &,char const *,ulong,ulong)
0x1800a8629  jmp     loc_1800A8789
0x1800a862e  mov     rax, [rsi+428h]
0x1800a8635  test    rax, rax
0x1800a8638  jnz     short loc_1800A864B
0x1800a863a  mov     ebx, 80004003h
0x1800a863f  lea     r8d, [rax+52h]
0x1800a8643  mov     r9d, 80004003h
0x1800a8649  jmp     short loc_1800A8619
0x1800a864b  add     rax, 148h
0x1800a8651  jnz     short loc_1800A8664
0x1800a8653  mov     ebx, 80004003h
0x1800a8658  lea     r8d, [rax+53h]
0x1800a865c  mov     r9d, 80004003h
0x1800a8662  jmp     short loc_1800A8619
0x1800a8664  xor     r8d, r8d; lpName
0x1800a8667  xor     edx, edx; bInitialOwner
0x1800a8669  xor     ecx, ecx; lpMutexAttributes
0x1800a866b  call    cs:__imp_CreateMutexW
0x1800a8671  mov     [rsi+3F0h], rax
0x1800a8678  test    rax, rax
0x1800a867b  jnz     short loc_1800A869D
0x1800a867d  call    cs:__imp_GetLastError
0x1800a8683  mov     ebx, eax
0x1800a8685  test    eax, eax
0x1800a8687  jle     short loc_1800A8692
0x1800a8689  movzx   ebx, ax
0x1800a868c  or      ebx, 80070000h
0x1800a8692  mov     r8d, 57h ; 'W'
0x1800a8698  jmp     loc_1800A8616
0x1800a869d  lea     rdi, [rbp+148h]
0x1800a86a4  mov     r9d, 8
0x1800a86aa  lea     rax, [rdi+250h]
0x1800a86b1  mov     rcx, rdi
0x1800a86b4  mov     [rsp+88h+var_58], rax
0x1800a86b9  lea     rdx, aBackingstorema_0; "BackingStoreMaxNumBackingFiles"
0x1800a86c0  mov     [rsp+88h+var_60], 100h
0x1800a86c8  mov     [rsp+88h+var_68], 4
0x1800a86d0  call    ?DVRGetVal_@CTSDVRSettings@@AEAAKPEBGHKKKPEAU?$CTRegVal@K@1@@Z; CTSDVRSettings::DVRGetVal_(ushort const *,int,ulong,ulong,ulong,CTSDVRSettings::CTRegVal<ulong> *)
0x1800a86d5  mov     ebx, eax
0x1800a86d7  lea     rdx, aBackingstoreea; "BackingStoreEachFileDurationSeconds"
0x1800a86de  lea     rax, [rdi+258h]
0x1800a86e5  mov     r9d, 12Ch
0x1800a86eb  mov     [rsp+88h+var_58], rax
0x1800a86f0  mov     rcx, rdi
0x1800a86f3  mov     [rsp+88h+var_60], 0FFFFFFFFh
0x1800a86fb  mov     [rsp+88h+var_68], 5
0x1800a8703  call    ?DVRGetVal_@CTSDVRSettings@@AEAAKPEBGHKKKPEAU?$CTRegVal@K@1@@Z; CTSDVRSettings::DVRGetVal_(ushort const *,int,ulong,ulong,ulong,CTSDVRSettings::CTRegVal<ulong> *)
0x1800a8708  imul    eax, ebx
0x1800a870b  imul    ecx, eax, 3E8h
0x1800a8711  imul    rax, rcx, 2710h
0x1800a8718  mov     rcx, rsi; this
0x1800a871b  mov     [rsi+140h], rax
0x1800a8722  call    ?ConfigureTMPDirectory@CSBE2PauseBufferWriter@SBE2PauseBuffer@@AEAAJXZ; SBE2PauseBuffer::CSBE2PauseBufferWriter::ConfigureTMPDirectory(void)
0x1800a8727  mov     ebx, eax
0x1800a8729  test    eax, eax
0x1800a872b  jns     short loc_1800A873B
0x1800a872d  mov     r9d, eax
0x1800a8730  mov     r8d, 5Ah ; 'Z'
0x1800a8736  jmp     loc_1800A8619
0x1800a873b  mov     rcx, r14
0x1800a873e  call    ??$Release@PEAVCSALResidentNVP@SAL2@@@SAL2@@YAXAEAPEAVCSALResidentNVP@0@@Z; SAL2::Release<SAL2::CSALResidentNVP *>(SAL2::CSALResidentNVP * &)
0x1800a8743  mov     rdx, [rsp+88h+arg_20]; unsigned __int16 *
0x1800a874b  mov     r9, r14; struct SBE2PauseBuffer::Cv2StubWriter **
0x1800a874e  mov     r8, rbp; struct CDVRPolicy *
0x1800a8751  mov     rcx, r13; struct SBEPerf::CeHomeETWSBE2PauseBuffer *
0x1800a8754  call    ?CreateInstance@Cv2StubWriter@SBE2PauseBuffer@@SAJPEAVCeHomeETWSBE2PauseBuffer@SBEPerf@@PEBGPEAVCDVRPolicy@@PEAPEAV12@@Z; SBE2PauseBuffer::Cv2StubWriter::CreateInstance(SBEPerf::CeHomeETWSBE2PauseBuffer *,ushort const *,CDVRPolicy *,SBE2PauseBuffer::Cv2StubWriter * *)
0x1800a8759  mov     ebx, eax
0x1800a875b  test    eax, eax
0x1800a875d  jns     short loc_1800A876D
0x1800a875f  mov     r9d, eax
0x1800a8762  mov     r8d, 5Bh ; '['
0x1800a8768  jmp     loc_1800A8619
0x1800a876d  cmp     qword ptr [r14], 0
0x1800a8771  jnz     short loc_1800A8789
0x1800a8773  lea     rcx, [rsi+58h]; struct CEhEventTracer *
0x1800a8777  mov     r8d, 5Ch ; '\'; unsigned int
0x1800a877d  lea     rdx, aMultimediaDsho_27; "multimedia\\dshow\\filters\\sbe\\pauseb"...
0x1800a8784  call    ?EtwTraceAssert@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDK@Z; SBEBasicTracers::EtwTraceAssert(CEhEventTracer &,char const *,ulong)
0x1800a8789  mov     rax, [r14]
0x1800a878c  test    rax, rax
0x1800a878f  jz      short loc_1800A87A5
0x1800a8791  mov     rax, [rax+38h]
0x1800a8795  mov     rcx, [rax+10h]
0x1800a8799  mov     rcx, [rcx+140h]; this
0x1800a87a0  call    ?Unlock@CMutexLock@SBECoreUtil@@QEAAXXZ; SBECoreUtil::CMutexLock::Unlock(void)
0x1800a87a5  mov     [r15], ebx
0x1800a87a8  mov     rax, rsi
0x1800a87ab  add     rsp, 48h
0x1800a87af  pop     r15
0x1800a87b1  pop     r14
0x1800a87b3  pop     r13
0x1800a87b5  pop     r12
0x1800a87b7  pop     rdi
0x1800a87b8  pop     rsi
0x1800a87b9  pop     rbp
0x1800a87ba  pop     rbx
0x1800a87bb  retn
```
