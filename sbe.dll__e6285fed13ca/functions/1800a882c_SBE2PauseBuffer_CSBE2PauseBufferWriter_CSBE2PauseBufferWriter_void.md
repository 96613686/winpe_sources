# SBE2PauseBuffer::CSBE2PauseBufferWriter::~CSBE2PauseBufferWriter(void)

- ea: `0x1800a882c`
- end: `0x1800a8956`
- name: `??1CSBE2PauseBufferWriter@SBE2PauseBuffer@@MEAA@XZ`
- size: `298`
- prototype: `void __fastcall(SBE2PauseBuffer::CSBE2PauseBufferWriter *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x1800a8a00`

## callees

- `0x180008330`
- `0x1800089b8`
- `0x18002573c`
- `0x1800621ec`
- `0x180062710`
- `0x1800a882c`
- `0x1800aa1b0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800a88e0`
- `KERNEL32!CloseHandle` at `0x1800a88e0`
- `KERNEL32!DeleteCriticalSection` at `0x1800a891c`
- `KERNEL32!DeleteCriticalSection` at `0x1800a8929`
- `KERNEL32!DeleteCriticalSection` at `0x1800a891c`
- `KERNEL32!DeleteCriticalSection` at `0x1800a8929`

## string_xrefs

- `0x1800a8885`: `multimedia\dshow\filters\sbe\pausebuffer\pbwriter.cpp`
- `0x1800a88a5`: `multimedia\dshow\filters\sbe\pausebuffer\pbwriter.cpp`

## pseudocode

```c
void __fastcall SBE2PauseBuffer::CSBE2PauseBufferWriter::~CSBE2PauseBufferWriter(
        SBE2PauseBuffer::CSBE2PauseBufferWriter *this)
{
  SBE2PauseBuffer::CSBE2PauseBufferWriter *v2; // rcx
  __int64 v3; // rcx

  *(_QWORD *)this = &SBE2PauseBuffer::CSBE2PauseBufferWriter::`vftable'{for `SBEBasicTracers'};
  *((_QWORD *)this + 33) = &SBE2PauseBuffer::CSBE2PauseBufferWriter::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 36) = &SBE2PauseBuffer::CSBE2PauseBufferWriter::`vftable'{for `IPauseBuffer'};
  v2 = (SBE2PauseBuffer::CSBE2PauseBufferWriter *)((char *)this + 296);
  *(_QWORD *)v2 = &SBE2PauseBuffer::CSBE2PauseBufferWriter::`vftable'{for `IPauseBufferWriter'};
  SBE2PauseBuffer::CSBE2PauseBufferWriter::Stop(v2);
  if ( *((_QWORD *)this + 113) )
    SBEBasicTracers::EtwTraceAssert(
      (SBE2PauseBuffer::CSBE2PauseBufferWriter *)((char *)this + 48),
      "multimedia\\dshow\\filters\\sbe\\pausebuffer\\pbwriter.cpp",
      0x6Eu);
  if ( *((_QWORD *)this + 114) )
    SBEBasicTracers::EtwTraceAssert(
      (SBE2PauseBuffer::CSBE2PauseBufferWriter *)((char *)this + 48),
      "multimedia\\dshow\\filters\\sbe\\pausebuffer\\pbwriter.cpp",
      0x6Fu);
  EhEtw::TPtr<IEhTraceSpan>::Release((char *)this + 848);
  SAL2::Release<SAL2::CSALResidentNVP *>((char *)this + 856);
  EhEtw::TPtr<IEhTraceSpan>::Release((char *)this + 312);
  CloseHandle(*((HANDLE *)this + 126));
  v3 = *((_QWORD *)this + 133);
  if ( v3 )
  {
    SBF2::CRefCounted::Release((SBF2::CRefCounted *)(v3 + 264));
    *((_QWORD *)this + 133) = 0;
  }
  SAL2::Release<SAL2::CSALResidentNVP *>((char *)this + 1056);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1016));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 936));
  *((_QWORD *)this + 108) = &SBECoreUtil::LISTENTRYList<SBE2PauseBuffer::CSBE2PBNodeReader>::`vftable';
  _InterlockedDecrement(&CBaseObject::m_cObjects);
  SBEBasicTracers::~SBEBasicTracers(this);
}

```

## disassembly

```asm
0x1800a882c  mov     [rsp+arg_0], rbx
0x1800a8831  push    rdi
0x1800a8832  sub     rsp, 20h
0x1800a8836  lea     rax, ??_7CSBE2PauseBufferWriter@SBE2PauseBuffer@@6BSBEBasicTracers@@@; const SBE2PauseBuffer::CSBE2PauseBufferWriter::`vftable'{for `SBEBasicTracers'}
0x1800a883d  mov     rbx, rcx
0x1800a8840  mov     [rcx], rax
0x1800a8843  lea     rax, ??_7CSBE2PauseBufferWriter@SBE2PauseBuffer@@6BCUnknown@@@; const SBE2PauseBuffer::CSBE2PauseBufferWriter::`vftable'{for `CUnknown'}
0x1800a884a  mov     [rcx+108h], rax
0x1800a8851  lea     rax, ??_7CSBE2PauseBufferWriter@SBE2PauseBuffer@@6BIPauseBuffer@@@; const SBE2PauseBuffer::CSBE2PauseBufferWriter::`vftable'{for `IPauseBuffer'}
0x1800a8858  mov     [rcx+120h], rax
0x1800a885f  add     rcx, 128h; this
0x1800a8866  lea     rax, ??_7CSBE2PauseBufferWriter@SBE2PauseBuffer@@6BIPauseBufferWriter@@@; const SBE2PauseBuffer::CSBE2PauseBufferWriter::`vftable'{for `IPauseBufferWriter'}
0x1800a886d  mov     [rcx], rax
0x1800a8870  call    ?Stop@CSBE2PauseBufferWriter@SBE2PauseBuffer@@UEAAJXZ; SBE2PauseBuffer::CSBE2PauseBufferWriter::Stop(void)
0x1800a8875  cmp     qword ptr [rbx+388h], 0
0x1800a887d  jz      short loc_1800A8895
0x1800a887f  mov     r8d, 6Eh ; 'n'; unsigned int
0x1800a8885  lea     rdx, aMultimediaDsho_27; "multimedia\\dshow\\filters\\sbe\\pauseb"...
0x1800a888c  lea     rcx, [rbx+30h]; struct CEhEventTracer *
0x1800a8890  call    ?EtwTraceAssert@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDK@Z; SBEBasicTracers::EtwTraceAssert(CEhEventTracer &,char const *,ulong)
0x1800a8895  cmp     qword ptr [rbx+390h], 0
0x1800a889d  jz      short loc_1800A88B5
0x1800a889f  mov     r8d, 6Fh ; 'o'; unsigned int
0x1800a88a5  lea     rdx, aMultimediaDsho_27; "multimedia\\dshow\\filters\\sbe\\pauseb"...
0x1800a88ac  lea     rcx, [rbx+30h]; struct CEhEventTracer *
0x1800a88b0  call    ?EtwTraceAssert@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDK@Z; SBEBasicTracers::EtwTraceAssert(CEhEventTracer &,char const *,ulong)
0x1800a88b5  lea     rcx, [rbx+350h]
0x1800a88bc  call    ?Release@?$TPtr@UIEhTraceSpan@@@EhEtw@@QEAAXXZ; EhEtw::TPtr<IEhTraceSpan>::Release(void)
0x1800a88c1  lea     rcx, [rbx+358h]
0x1800a88c8  call    ??$Release@PEAVCSALResidentNVP@SAL2@@@SAL2@@YAXAEAPEAVCSALResidentNVP@0@@Z; SAL2::Release<SAL2::CSALResidentNVP *>(SAL2::CSALResidentNVP * &)
0x1800a88cd  lea     rcx, [rbx+138h]
0x1800a88d4  call    ?Release@?$TPtr@UIEhTraceSpan@@@EhEtw@@QEAAXXZ; EhEtw::TPtr<IEhTraceSpan>::Release(void)
0x1800a88d9  mov     rcx, [rbx+3F0h]; hObject
0x1800a88e0  call    cs:__imp_CloseHandle
0x1800a88e6  mov     rcx, [rbx+428h]
0x1800a88ed  test    rcx, rcx
0x1800a88f0  jz      short loc_1800A8909
0x1800a88f2  add     rcx, 108h; this
0x1800a88f9  call    ?Release@CRefCounted@SBF2@@QEAAJXZ; SBF2::CRefCounted::Release(void)
0x1800a88fe  mov     qword ptr [rbx+428h], 0
0x1800a8909  lea     rcx, [rbx+420h]
0x1800a8910  call    ??$Release@PEAVCSALResidentNVP@SAL2@@@SAL2@@YAXAEAPEAVCSALResidentNVP@0@@Z; SAL2::Release<SAL2::CSALResidentNVP *>(SAL2::CSALResidentNVP * &)
0x1800a8915  lea     rcx, [rbx+3F8h]; lpCriticalSection
0x1800a891c  call    cs:__imp_DeleteCriticalSection
0x1800a8922  lea     rcx, [rbx+3A8h]; lpCriticalSection
0x1800a8929  call    cs:__imp_DeleteCriticalSection
0x1800a892f  lea     rax, ??_7?$LISTENTRYList@VCSBE2PBNodeReader@SBE2PauseBuffer@@@SBECoreUtil@@6B@; const SBECoreUtil::LISTENTRYList<SBE2PauseBuffer::CSBE2PBNodeReader>::`vftable'
0x1800a8936  mov     rcx, rbx; this
0x1800a8939  mov     [rbx+360h], rax
0x1800a8940  lock dec cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x1800a8947  mov     rbx, [rsp+28h+arg_0]
0x1800a894c  add     rsp, 20h
0x1800a8950  pop     rdi
0x1800a8951  jmp     ??1SBEBasicTracers@@UEAA@XZ; SBEBasicTracers::~SBEBasicTracers(void)
```
