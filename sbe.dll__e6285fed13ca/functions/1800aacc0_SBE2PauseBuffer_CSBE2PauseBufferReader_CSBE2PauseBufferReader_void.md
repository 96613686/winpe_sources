# SBE2PauseBuffer::CSBE2PauseBufferReader::~CSBE2PauseBufferReader(void)

- ea: `0x1800aacc0`
- end: `0x1800aae82`
- name: `??1CSBE2PauseBufferReader@SBE2PauseBuffer@@MEAA@XZ`
- size: `450`
- prototype: `void __fastcall(SBE2PauseBuffer::CSBE2PauseBufferReader *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800aaf30`

## callees

- `0x18000716c`
- `0x1800072c4`
- `0x180008330`
- `0x1800089b8`
- `0x180008ea8`
- `0x18002573c`
- `0x1800558dc`
- `0x1800605d0`
- `0x1800621ec`
- `0x1800aacc0`
- `0x1800aae88`
- `0x1800ac688`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1800aad36`
- `KERNEL32!WaitForSingleObject` at `0x1800aad36`
- `KERNEL32!SetEvent` at `0x1800aad2a`
- `KERNEL32!SetEvent` at `0x1800aad2a`
- `KERNEL32!DeleteCriticalSection` at `0x1800aae16`
- `KERNEL32!DeleteCriticalSection` at `0x1800aae16`
- `KERNEL32!LeaveCriticalSection` at `0x1800aade1`
- `KERNEL32!LeaveCriticalSection` at `0x1800aade1`
- `KERNEL32!EnterCriticalSection` at `0x1800aadcf`
- `KERNEL32!EnterCriticalSection` at `0x1800aadcf`

## pseudocode

```c
void __fastcall SBE2PauseBuffer::CSBE2PauseBufferReader::~CSBE2PauseBufferReader(
        SBE2PauseBuffer::CSBE2PauseBufferReader *this,
        void **a2,
        void *a3)
{
  HANDLE *v4; // rbx
  bool v5; // zf
  HANDLE *v6; // rsi
  void **v7; // rdx
  void *v8; // r8
  __int64 v9; // rax
  __int64 v10; // rsi
  __int64 v11; // rcx
  __int64 v12; // [rsp+40h] [rbp+8h] BYREF
  char v13; // [rsp+48h] [rbp+10h] BYREF

  *(_QWORD *)this = &SBE2PauseBuffer::CSBE2PauseBufferReader::`vftable'{for `SBEBasicTracers'};
  v4 = (HANDLE *)((char *)this + 416);
  v5 = *((_QWORD *)this + 52) == 0;
  *((_QWORD *)this + 33) = &SBE2PauseBuffer::CSBE2PauseBufferReader::`vftable'{for `CUnknown'};
  v6 = (HANDLE *)((char *)this + 424);
  *((_QWORD *)this + 36) = &SBE2PauseBuffer::CSBE2PauseBufferReader::`vftable'{for `IDVRReader'};
  *((_QWORD *)this + 37) = &SBE2PauseBuffer::CSBE2PauseBufferReader::`vftable'{for `IDVRReaderNotify'};
  if ( !v5 )
  {
    *((_DWORD *)this + 102) = 1;
    SetEvent(*v6);
    WaitForSingleObject(*v4, 0xFFFFFFFF);
    SBECoreUtil::CloseHandle((SBECoreUtil *)v4, v7, v8);
  }
  SBECoreUtil::CloseHandle((SBECoreUtil *)v6, a2, a3);
  if ( *((_QWORD *)this + 38) )
  {
    v12 = 0;
    do
    {
      v9 = SBE2PauseBuffer::CSBE2PauseBufferReader::fifoPop(this, &v13);
      SBECoreUtil::autoref<SBE2PauseBuffer::CSBE2PBNodeReader>::operator=(&v12, v9);
      SAL2::Release<SAL2::CSALPoolGrow *>(&v13);
    }
    while ( v12 );
    SAL2::Release<SAL2::CSALPoolGrow *>(&v12);
  }
  SBEPerf::CeHomeETWProvider::Unload(*((SBEPerf::CeHomeETWProvider **)this + 50));
  SAL2::Release<SAL2::CSALResidentNVP *>((char *)this + 400);
  EhEtw::TPtr<IEhTraceSpan>::Release((char *)this + 464);
  v10 = *((_QWORD *)this + 60);
  if ( v10 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v10 + 24));
    *(_QWORD *)(v10 + 16) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 24));
  }
  SAL2::Release<SAL2::CSALResidentNVP *>((char *)this + 480);
  SAL2::Release<SAL2::CSALResidentNVP *>((char *)this + 480);
  SAL2::Release<SAL2::CSALPoolGrow *>((char *)this + 440);
  QzCComPtr<IStream>::~QzCComPtr<IStream>((char *)this + 432);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 9);
  *((_QWORD *)this + 41) = &SBECoreUtil::LISTENTRYList<SBE2PauseBuffer::CSBE2PBNodeReader>::`vftable';
  v11 = *((_QWORD *)this + 40);
  if ( v11 )
  {
    SBF2::CRefCounted::Release((SBF2::CRefCounted *)(v11 + 264));
    *((_QWORD *)this + 40) = 0;
  }
  CAMEvent::~CAMEvent((SBE2PauseBuffer::CSBE2PauseBufferReader *)((char *)this + 312));
  SAL2::Release<SAL2::CSALResidentNVP *>((char *)this + 304);
  _InterlockedDecrement(&CBaseObject::m_cObjects);
  SBEBasicTracers::~SBEBasicTracers(this);
}

```

## disassembly

```asm
0x1800aacc0  mov     [rsp+arg_10], rbx
0x1800aacc5  mov     [rsp+arg_18], rbp
0x1800aacca  push    rsi
0x1800aaccb  push    rdi
0x1800aaccc  push    r14
0x1800aacce  sub     rsp, 20h
0x1800aacd2  lea     rax, ??_7CSBE2PauseBufferReader@SBE2PauseBuffer@@6BSBEBasicTracers@@@; const SBE2PauseBuffer::CSBE2PauseBufferReader::`vftable'{for `SBEBasicTracers'}
0x1800aacd9  mov     rdi, rcx
0x1800aacdc  mov     [rcx], rax
0x1800aacdf  lea     rbx, [rcx+1A0h]
0x1800aace6  cmp     qword ptr [rbx], 0
0x1800aacea  lea     rax, ??_7CSBE2PauseBufferReader@SBE2PauseBuffer@@6BCUnknown@@@; const SBE2PauseBuffer::CSBE2PauseBufferReader::`vftable'{for `CUnknown'}
0x1800aacf1  mov     [rcx+108h], rax
0x1800aacf8  lea     rsi, [rcx+1A8h]
0x1800aacff  lea     rax, ??_7CSBE2PauseBufferReader@SBE2PauseBuffer@@6BIDVRReader@@@; const SBE2PauseBuffer::CSBE2PauseBufferReader::`vftable'{for `IDVRReader'}
0x1800aad06  mov     [rcx+120h], rax
0x1800aad0d  lea     rax, ??_7CSBE2PauseBufferReader@SBE2PauseBuffer@@6BIDVRReaderNotify@@@; const SBE2PauseBuffer::CSBE2PauseBufferReader::`vftable'{for `IDVRReaderNotify'}
0x1800aad14  mov     [rcx+128h], rax
0x1800aad1b  jz      short loc_1800AAD44
0x1800aad1d  mov     dword ptr [rcx+198h], 1
0x1800aad27  mov     rcx, [rsi]; hEvent
0x1800aad2a  call    cs:__imp_SetEvent
0x1800aad30  mov     rcx, [rbx]; hHandle
0x1800aad33  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800aad36  call    cs:__imp_WaitForSingleObject
0x1800aad3c  mov     rcx, rbx; this
0x1800aad3f  call    ?CloseHandle@SBECoreUtil@@YAXAEAPEAXPEAX@Z; SBECoreUtil::CloseHandle(void * &,void *)
0x1800aad44  mov     rcx, rsi; this
0x1800aad47  call    ?CloseHandle@SBECoreUtil@@YAXAEAPEAXPEAX@Z; SBECoreUtil::CloseHandle(void * &,void *)
0x1800aad4c  lea     rbp, [rdi+130h]
0x1800aad53  cmp     qword ptr [rbp+0], 0
0x1800aad58  jz      short loc_1800AAD99
0x1800aad5a  mov     [rsp+38h+arg_0], 0
0x1800aad63  lea     rdx, [rsp+38h+arg_8]
0x1800aad68  mov     rcx, rdi
0x1800aad6b  call    ?fifoPop@CSBE2PauseBufferReader@SBE2PauseBuffer@@AEAA?AV?$autoref@VCSBE2PBNodeReader@SBE2PauseBuffer@@@SBECoreUtil@@XZ; SBE2PauseBuffer::CSBE2PauseBufferReader::fifoPop(void)
0x1800aad70  mov     rdx, rax
0x1800aad73  lea     rcx, [rsp+38h+arg_0]
0x1800aad78  call    ??4?$autoref@VCSBE2PBNodeReader@SBE2PauseBuffer@@@SBECoreUtil@@QEAAAEAV01@AEBV01@@Z; SBECoreUtil::autoref<SBE2PauseBuffer::CSBE2PBNodeReader>::operator=(SBECoreUtil::autoref<SBE2PauseBuffer::CSBE2PBNodeReader> const &)
0x1800aad7d  lea     rcx, [rsp+38h+arg_8]
0x1800aad82  call    ??$Release@PEAVCSALPoolGrow@SAL2@@@SAL2@@YAXAEAPEAVCSALPoolGrow@0@@Z; SAL2::Release<SAL2::CSALPoolGrow *>(SAL2::CSALPoolGrow * &)
0x1800aad87  cmp     [rsp+38h+arg_0], 0
0x1800aad8d  jnz     short loc_1800AAD63
0x1800aad8f  lea     rcx, [rsp+38h+arg_0]
0x1800aad94  call    ??$Release@PEAVCSALPoolGrow@SAL2@@@SAL2@@YAXAEAPEAVCSALPoolGrow@0@@Z; SAL2::Release<SAL2::CSALPoolGrow *>(SAL2::CSALPoolGrow * &)
0x1800aad99  lea     rbx, [rdi+190h]
0x1800aada0  mov     rcx, [rbx]; this
0x1800aada3  call    ?Unload@CeHomeETWProvider@SBEPerf@@QEAAXXZ; SBEPerf::CeHomeETWProvider::Unload(void)
0x1800aada8  mov     rcx, rbx
0x1800aadab  call    ??$Release@PEAVCSALResidentNVP@SAL2@@@SAL2@@YAXAEAPEAVCSALResidentNVP@0@@Z; SAL2::Release<SAL2::CSALResidentNVP *>(SAL2::CSALResidentNVP * &)
0x1800aadb0  lea     rcx, [rdi+1D0h]
0x1800aadb7  call    ?Release@?$TPtr@UIEhTraceSpan@@@EhEtw@@QEAAXXZ; EhEtw::TPtr<IEhTraceSpan>::Release(void)
0x1800aadbc  lea     r14, [rdi+1E0h]
0x1800aadc3  mov     rsi, [r14]
0x1800aadc6  test    rsi, rsi
0x1800aadc9  jz      short loc_1800AADE7
0x1800aadcb  lea     rcx, [rsi+18h]; lpCriticalSection
0x1800aadcf  call    cs:__imp_EnterCriticalSection
0x1800aadd5  lea     rcx, [rsi+18h]; lpCriticalSection
0x1800aadd9  mov     qword ptr [rsi+10h], 0
0x1800aade1  call    cs:__imp_LeaveCriticalSection
0x1800aade7  mov     rcx, r14
0x1800aadea  call    ??$Release@PEAVCSALResidentNVP@SAL2@@@SAL2@@YAXAEAPEAVCSALResidentNVP@0@@Z; SAL2::Release<SAL2::CSALResidentNVP *>(SAL2::CSALResidentNVP * &)
0x1800aadef  mov     rcx, r14
0x1800aadf2  call    ??$Release@PEAVCSALResidentNVP@SAL2@@@SAL2@@YAXAEAPEAVCSALResidentNVP@0@@Z; SAL2::Release<SAL2::CSALResidentNVP *>(SAL2::CSALResidentNVP * &)
0x1800aadf7  lea     rcx, [rdi+1B8h]
0x1800aadfe  call    ??$Release@PEAVCSALPoolGrow@SAL2@@@SAL2@@YAXAEAPEAVCSALPoolGrow@0@@Z; SAL2::Release<SAL2::CSALPoolGrow *>(SAL2::CSALPoolGrow * &)
0x1800aae03  lea     rcx, [rdi+1B0h]
0x1800aae0a  call    ??1?$QzCComPtr@UIStream@@@@QEAA@XZ; QzCComPtr<IStream>::~QzCComPtr<IStream>(void)
0x1800aae0f  lea     rcx, [rdi+168h]; lpCriticalSection
0x1800aae16  call    cs:__imp_DeleteCriticalSection
0x1800aae1c  lea     rax, ??_7?$LISTENTRYList@VCSBE2PBNodeReader@SBE2PauseBuffer@@@SBECoreUtil@@6B@; const SBECoreUtil::LISTENTRYList<SBE2PauseBuffer::CSBE2PBNodeReader>::`vftable'
0x1800aae23  mov     [rdi+148h], rax
0x1800aae2a  mov     rcx, [rdi+140h]
0x1800aae31  test    rcx, rcx
0x1800aae34  jz      short loc_1800AAE4D
0x1800aae36  add     rcx, 108h; this
0x1800aae3d  call    ?Release@CRefCounted@SBF2@@QEAAJXZ; SBF2::CRefCounted::Release(void)
0x1800aae42  mov     qword ptr [rdi+140h], 0
0x1800aae4d  lea     rcx, [rdi+138h]; this
0x1800aae54  call    ??1CAMEvent@@QEAA@XZ; CAMEvent::~CAMEvent(void)
0x1800aae59  mov     rcx, rbp
0x1800aae5c  call    ??$Release@PEAVCSALResidentNVP@SAL2@@@SAL2@@YAXAEAPEAVCSALResidentNVP@0@@Z; SAL2::Release<SAL2::CSALResidentNVP *>(SAL2::CSALResidentNVP * &)
0x1800aae61  lock dec cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x1800aae68  mov     rcx, rdi; this
0x1800aae6b  mov     rbx, [rsp+38h+arg_10]
0x1800aae70  mov     rbp, [rsp+38h+arg_18]
0x1800aae75  add     rsp, 20h
0x1800aae79  pop     r14
0x1800aae7b  pop     rdi
0x1800aae7c  pop     rsi
0x1800aae7d  jmp     ??1SBEBasicTracers@@UEAA@XZ; SBEBasicTracers::~SBEBasicTracers(void)
```
