# SBE2PauseBuffer::CSBE2PBNodeReader::~CSBE2PBNodeReader(void)

- ea: `0x1800b1538`
- end: `0x1800b16e0`
- name: `??1CSBE2PBNodeReader@SBE2PauseBuffer@@MEAA@XZ`
- size: `424`
- prototype: `void __fastcall(SBE2PauseBuffer::CSBE2PBNodeReader *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800b1750`

## callees

- `0x1800017e0`
- `0x180008ea8`
- `0x18002573c`
- `0x180057140`
- `0x1800621ec`
- `0x1800a841c`
- `0x1800a87c4`
- `0x1800add3c`
- `0x1800adf04`
- `0x1800b1538`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800b16c6`
- `KERNEL32!DeleteCriticalSection` at `0x1800b16c6`
- `KERNEL32!LeaveCriticalSection` at `0x1800b1693`
- `KERNEL32!LeaveCriticalSection` at `0x1800b1693`
- `KERNEL32!EnterCriticalSection` at `0x1800b167b`
- `KERNEL32!EnterCriticalSection` at `0x1800b167b`

## pseudocode

```c
void __fastcall SBE2PauseBuffer::CSBE2PBNodeReader::~CSBE2PBNodeReader(SBE2PauseBuffer::CSBE2PBNodeReader *this)
{
  SBE2PauseBuffer::Cv2Stub **v1; // r15
  __int64 v2; // rdx
  __int64 v4; // rcx
  __int64 v5; // rsi
  int v6; // [rsp+20h] [rbp-78h]
  _BYTE v7[72]; // [rsp+50h] [rbp-48h] BYREF
  int v8; // [rsp+A0h] [rbp+8h] BYREF

  v1 = (SBE2PauseBuffer::Cv2Stub **)((char *)this + 872);
  v8 = 0;
  v2 = *((_QWORD *)this + 109);
  *(_QWORD *)this = &SBE2PauseBuffer::CSBE2PBNodeReader::`vftable'{for `SBEBasicTracers'};
  *((_QWORD *)this + 33) = &SBE2PauseBuffer::CSBE2PBNodeReader::`vftable'{for `SBECoreUtil::CRefCounted'};
  SBECoreUtil::CTSFScopeLock<SBE2PauseBuffer::Cv2Stub>::CTSFScopeLock<SBE2PauseBuffer::Cv2Stub>(v7, v2, &v8);
  if ( v8 < 0 )
  {
    v6 = 130;
    CSbeFileLog::LogEvent(
      0x10u,
      1u,
      L"%s(%d) : ~pbnr can't lock stub.  have leaked a node ctx () %s ",
      L"multimedia\\dshow\\filters\\sbe\\pausebuffer\\pbnoder.cpp",
      v6,
      (char *)this + 320);
  }
  else
  {
    operator delete(*((void **)this + 108), 0x10u);
  }
  SBE2PauseBuffer::Cv2Stub::etwNodeExpired(
    *v1,
    (unsigned __int16 *)this + 160,
    (const struct _GUID *)((char *)this + 936),
    -1,
    -1,
    -1,
    -1,
    *((_DWORD *)this + 224) == 0,
    1);
  SBE2PauseBuffer::Cv2Stub::etwNodeClosed(
    *v1,
    (unsigned __int16 *)this + 160,
    (const struct _GUID *)((char *)this + 936),
    -1,
    -1,
    -1,
    -1,
    *((_DWORD *)this + 224) == 0,
    1);
  v4 = *((_QWORD *)this + 110);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 110) = 0;
  }
  v5 = *((_QWORD *)this + 111);
  if ( v5 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 32));
    *(_QWORD *)(v5 + 16) = 0;
    *(_WORD *)(v5 + 72) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 32));
  }
  SBECoreUtil::CTSFScopeLock<SBE2PauseBuffer::Cv2Stub>::~CTSFScopeLock<SBE2PauseBuffer::Cv2Stub>(v7);
  SAL2::Release<SAL2::CSALResidentNVP *>((char *)this + 888);
  SAL2::Release<SAL2::CSALResidentNVP *>(v1);
  QzCComPtr<IStream>::~QzCComPtr<IStream>((char *)this + 856);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 7);
  SBEBasicTracers::~SBEBasicTracers(this);
}

```

## disassembly

```asm
0x1800b1538  mov     r11, rsp
0x1800b153b  push    rbx
0x1800b153c  push    rbp
0x1800b153d  push    rsi
0x1800b153e  push    rdi
0x1800b153f  push    r14
0x1800b1541  push    r15
0x1800b1543  sub     rsp, 68h
0x1800b1547  lea     r15, [rcx+368h]
0x1800b154e  mov     dword ptr [r11+8], 0
0x1800b1556  mov     rdx, [r15]
0x1800b1559  lea     rax, ??_7CSBE2PBNodeReader@SBE2PauseBuffer@@6BSBEBasicTracers@@@; const SBE2PauseBuffer::CSBE2PBNodeReader::`vftable'{for `SBEBasicTracers'}
0x1800b1560  mov     [rcx], rax
0x1800b1563  lea     r8, [r11+8]
0x1800b1567  lea     rax, ??_7CSBE2PBNodeReader@SBE2PauseBuffer@@6BCRefCounted@SBECoreUtil@@@; const SBE2PauseBuffer::CSBE2PBNodeReader::`vftable'{for `SBECoreUtil::CRefCounted'}
0x1800b156e  mov     rdi, rcx
0x1800b1571  mov     [rcx+108h], rax
0x1800b1578  lea     rcx, [r11-48h]
0x1800b157c  call    ??0?$CTSFScopeLock@VCv2Stub@SBE2PauseBuffer@@@SBECoreUtil@@QEAA@PEAVCv2Stub@SBE2PauseBuffer@@PEAJ@Z; SBECoreUtil::CTSFScopeLock<SBE2PauseBuffer::Cv2Stub>::CTSFScopeLock<SBE2PauseBuffer::Cv2Stub>(SBE2PauseBuffer::Cv2Stub *,long *)
0x1800b1581  cmp     [rsp+98h+arg_0], 0
0x1800b1589  lea     rsi, [rdi+140h]
0x1800b1590  mov     r14d, 1
0x1800b1596  jl      short loc_1800B15AA
0x1800b1598  mov     rcx, [rdi+360h]; void *
0x1800b159f  lea     edx, [r14+0Fh]; unsigned __int64
0x1800b15a3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800b15a8  jmp     short loc_1800B15D2
0x1800b15aa  mov     [rsp+98h+var_70], rsi
0x1800b15af  lea     r9, aMultimediaDsho_15; "multimedia\\dshow\\filters\\sbe\\pauseb"...
0x1800b15b6  lea     r8, aSDPbnrCanTLock; "%s(%d) : ~pbnr can't lock stub.  have l"...
0x1800b15bd  mov     dword ptr [rsp+98h+var_78], 82h
0x1800b15c5  mov     edx, r14d; unsigned __int8
0x1800b15c8  mov     ecx, 10h; unsigned int
0x1800b15cd  call    ?LogEvent@CSbeFileLog@@SAJKEPEBGZZ; CSbeFileLog::LogEvent(ulong,uchar,ushort const *,...)
0x1800b15d2  mov     rcx, [r15]; this
0x1800b15d5  lea     rbx, [rdi+3A8h]
0x1800b15dc  xor     eax, eax
0x1800b15de  mov     [rsp+98h+var_58], r14d; int
0x1800b15e3  cmp     [rdi+380h], eax
0x1800b15e9  mov     r8, rbx; struct _GUID *
0x1800b15ec  mov     rdx, rsi; unsigned __int16 *
0x1800b15ef  setz    al
0x1800b15f2  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800b15f6  mov     [rsp+98h+var_60], eax; int
0x1800b15fa  mov     r9, rbp; __int64
0x1800b15fd  mov     [rsp+98h+var_68], rbp; __int64
0x1800b1602  mov     [rsp+98h+var_70], rbp; __int64
0x1800b1607  mov     [rsp+98h+var_78], rbp; __int64
0x1800b160c  call    ?etwNodeExpired@Cv2Stub@SBE2PauseBuffer@@IEAAXPEAGAEBU_GUID@@_J222HH@Z; SBE2PauseBuffer::Cv2Stub::etwNodeExpired(ushort *,_GUID const &,__int64,__int64,__int64,__int64,int,int)
0x1800b1611  mov     rcx, [r15]; this
0x1800b1614  xor     eax, eax
0x1800b1616  cmp     [rdi+380h], eax
0x1800b161c  mov     r9, rbp; __int64
0x1800b161f  mov     [rsp+98h+var_58], r14d; int
0x1800b1624  mov     r8, rbx; struct _GUID *
0x1800b1627  setz    al
0x1800b162a  mov     rdx, rsi; unsigned __int16 *
0x1800b162d  mov     [rsp+98h+var_60], eax; int
0x1800b1631  mov     [rsp+98h+var_68], rbp; __int64
0x1800b1636  mov     [rsp+98h+var_70], rbp; __int64
0x1800b163b  mov     [rsp+98h+var_78], rbp; __int64
0x1800b1640  call    ?etwNodeClosed@Cv2Stub@SBE2PauseBuffer@@IEAAXPEAGAEBU_GUID@@_J222HH@Z; SBE2PauseBuffer::Cv2Stub::etwNodeClosed(ushort *,_GUID const &,__int64,__int64,__int64,__int64,int,int)
0x1800b1645  mov     rcx, [rdi+370h]
0x1800b164c  test    rcx, rcx
0x1800b164f  jz      short loc_1800B1668
0x1800b1651  mov     rax, [rcx]
0x1800b1654  mov     rax, [rax+10h]
0x1800b1658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b165d  mov     qword ptr [rdi+370h], 0
0x1800b1668  lea     r14, [rdi+378h]
0x1800b166f  mov     rsi, [r14]
0x1800b1672  test    rsi, rsi
0x1800b1675  jz      short loc_1800B1699
0x1800b1677  lea     rcx, [rsi+20h]; lpCriticalSection
0x1800b167b  call    cs:__imp_EnterCriticalSection
0x1800b1681  lea     rcx, [rsi+20h]; lpCriticalSection
0x1800b1685  mov     qword ptr [rsi+10h], 0
0x1800b168d  mov     word ptr [rsi+48h], 0
0x1800b1693  call    cs:__imp_LeaveCriticalSection
0x1800b1699  lea     rcx, [rsp+98h+var_48]
0x1800b169e  call    ??1?$CTSFScopeLock@VCv2Stub@SBE2PauseBuffer@@@SBECoreUtil@@QEAA@XZ; SBECoreUtil::CTSFScopeLock<SBE2PauseBuffer::Cv2Stub>::~CTSFScopeLock<SBE2PauseBuffer::Cv2Stub>(void)
0x1800b16a3  mov     rcx, r14
0x1800b16a6  call    ??$Release@PEAVCSALResidentNVP@SAL2@@@SAL2@@YAXAEAPEAVCSALResidentNVP@0@@Z; SAL2::Release<SAL2::CSALResidentNVP *>(SAL2::CSALResidentNVP * &)
0x1800b16ab  mov     rcx, r15
0x1800b16ae  call    ??$Release@PEAVCSALResidentNVP@SAL2@@@SAL2@@YAXAEAPEAVCSALResidentNVP@0@@Z; SAL2::Release<SAL2::CSALResidentNVP *>(SAL2::CSALResidentNVP * &)
0x1800b16b3  lea     rcx, [rdi+358h]
0x1800b16ba  call    ??1?$QzCComPtr@UIStream@@@@QEAA@XZ; QzCComPtr<IStream>::~QzCComPtr<IStream>(void)
0x1800b16bf  lea     rcx, [rdi+118h]; lpCriticalSection
0x1800b16c6  call    cs:__imp_DeleteCriticalSection
0x1800b16cc  mov     rcx, rdi; this
0x1800b16cf  add     rsp, 68h
0x1800b16d3  pop     r15
0x1800b16d5  pop     r14
0x1800b16d7  pop     rdi
0x1800b16d8  pop     rsi
0x1800b16d9  pop     rbp
0x1800b16da  pop     rbx
0x1800b16db  jmp     ??1SBEBasicTracers@@UEAA@XZ; SBEBasicTracers::~SBEBasicTracers(void)
```
