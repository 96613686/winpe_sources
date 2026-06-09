# SBE2PauseBuffer::CSBE2PauseBufferNode::~CSBE2PauseBufferNode(void)

- ea: `0x1800acbc8`
- end: `0x1800acd62`
- name: `??1CSBE2PauseBufferNode@SBE2PauseBuffer@@MEAA@XZ`
- size: `410`
- prototype: `void __fastcall(SBE2PauseBuffer::CSBE2PauseBufferNode *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800acdd0`

## callees

- `0x180001c00`
- `0x180008330`
- `0x180008ea8`
- `0x18002573c`
- `0x18005fd98`
- `0x1800605d0`
- `0x1800621ec`
- `0x1800acbc8`
- `0x1800ad0dc`
- `0x1800adbf0`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800acd0d`
- `KERNEL32!DeleteCriticalSection` at `0x1800acd0d`
- `KERNEL32!LeaveCriticalSection` at `0x1800acc40`
- `KERNEL32!LeaveCriticalSection` at `0x1800acce5`
- `KERNEL32!LeaveCriticalSection` at `0x1800acc40`
- `KERNEL32!LeaveCriticalSection` at `0x1800acce5`
- `KERNEL32!EnterCriticalSection` at `0x1800acc31`
- `KERNEL32!EnterCriticalSection` at `0x1800accb2`
- `KERNEL32!EnterCriticalSection` at `0x1800acc31`
- `KERNEL32!EnterCriticalSection` at `0x1800accb2`

## pseudocode

```c
void __fastcall SBE2PauseBuffer::CSBE2PauseBufferNode::~CSBE2PauseBufferNode(
        SBE2PauseBuffer::CSBE2PauseBufferNode *this)
{
  SBE2PauseBuffer::CSBE2PauseBufferNode *v1; // r14
  char *v3; // r15
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  int v5; // ebx
  unsigned int v6; // r9d
  void **v7; // rdx
  void *v8; // r8
  __int64 v9; // rcx
  __int64 v10; // rcx
  int v11[4]; // [rsp+40h] [rbp-268h] BYREF
  _BYTE v12[528]; // [rsp+50h] [rbp-258h] BYREF

  v1 = (SBE2PauseBuffer::CSBE2PauseBufferNode *)((char *)this + 288);
  v3 = (char *)this + 296;
  *(_QWORD *)this = &SBE2PauseBuffer::CSBE2PauseBufferNode::`vftable'{for `SBEBasicTracers'};
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 336);
  *((_QWORD *)this + 33) = &SBE2PauseBuffer::CSBE2PauseBufferNode::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 36) = &SBE2PauseBuffer::CSBE2PauseBufferNode::`vftable'{for `IPauseBufferNode'};
  *((_QWORD *)this + 37) = &SBE2PauseBuffer::CSBE2PauseBufferNode::`vftable'{for `IPauseBufferNodeWriter'};
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 336));
  v5 = *((_DWORD *)this + 82);
  LeaveCriticalSection(v4);
  if ( v5 == 1 )
    SBE2PauseBuffer::CSBE2PauseBufferNode::Stop(v1);
  if ( *((_WORD *)this + 192) && (*(unsigned int (__fastcall **)(char *))(*(_QWORD *)v3 + 96LL))(v3) )
  {
    v11[0] = 0;
    SBECoreUtil::CFile::CFile(
      (SBECoreUtil::CFile *)v12,
      (const unsigned __int16 *)this + 192,
      0x80000000,
      v6,
      3u,
      0x4000000u,
      v11);
    SBECoreUtil::CFile::Close((SBECoreUtil::CFile *)v12);
  }
  EnterCriticalSection(v4);
  v9 = *((_QWORD *)this + 40);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  *((_QWORD *)this + 40) = 0;
  SBECoreUtil::CloseHandle((SBE2PauseBuffer::CSBE2PauseBufferNode *)((char *)this + 928), v7, v8);
  LeaveCriticalSection(v4);
  v10 = *((_QWORD *)this + 113);
  if ( v10 )
  {
    SBF2::CRefCounted::Release((SBF2::CRefCounted *)(v10 + 264));
    *((_QWORD *)this + 113) = 0;
  }
  DeleteCriticalSection(v4);
  QzCComPtr<IStream>::~QzCComPtr<IStream>((char *)this + 320);
  SAL2::Release<SAL2::CSALResidentNVP *>((char *)this + 312);
  SAL2::Release<SAL2::CSALResidentNVP *>((char *)this + 304);
  _InterlockedDecrement(&CBaseObject::m_cObjects);
  SBEBasicTracers::~SBEBasicTracers(this);
}

```

## disassembly

```asm
0x1800acbc8  push    rbx
0x1800acbca  push    rbp
0x1800acbcb  push    rsi
0x1800acbcc  push    rdi
0x1800acbcd  push    r14
0x1800acbcf  push    r15
0x1800acbd1  sub     rsp, 278h
0x1800acbd8  mov     rax, cs:__security_cookie
0x1800acbdf  xor     rax, rsp
0x1800acbe2  mov     [rsp+2A8h+var_48], rax
0x1800acbea  lea     r14, [rcx+120h]
0x1800acbf1  mov     rdi, rcx
0x1800acbf4  lea     r15, [rcx+128h]
0x1800acbfb  lea     rax, ??_7CSBE2PauseBufferNode@SBE2PauseBuffer@@6BSBEBasicTracers@@@; const SBE2PauseBuffer::CSBE2PauseBufferNode::`vftable'{for `SBEBasicTracers'}
0x1800acc02  mov     [rcx], rax
0x1800acc05  lea     rsi, [rcx+150h]
0x1800acc0c  lea     rax, ??_7CSBE2PauseBufferNode@SBE2PauseBuffer@@6BCUnknown@@@; const SBE2PauseBuffer::CSBE2PauseBufferNode::`vftable'{for `CUnknown'}
0x1800acc13  mov     [rcx+108h], rax
0x1800acc1a  lea     rax, ??_7CSBE2PauseBufferNode@SBE2PauseBuffer@@6BIPauseBufferNode@@@; const SBE2PauseBuffer::CSBE2PauseBufferNode::`vftable'{for `IPauseBufferNode'}
0x1800acc21  mov     [r14], rax
0x1800acc24  mov     rcx, rsi; lpCriticalSection
0x1800acc27  lea     rax, ??_7CSBE2PauseBufferNode@SBE2PauseBuffer@@6BIPauseBufferNodeWriter@@@; const SBE2PauseBuffer::CSBE2PauseBufferNode::`vftable'{for `IPauseBufferNodeWriter'}
0x1800acc2e  mov     [r15], rax
0x1800acc31  call    cs:__imp_EnterCriticalSection
0x1800acc37  mov     ebx, [rdi+148h]
0x1800acc3d  mov     rcx, rsi; lpCriticalSection
0x1800acc40  call    cs:__imp_LeaveCriticalSection
0x1800acc46  cmp     ebx, 1
0x1800acc49  jnz     short loc_1800ACC53
0x1800acc4b  mov     rcx, r14; this
0x1800acc4e  call    ?Stop@CSBE2PauseBufferNode@SBE2PauseBuffer@@UEAAJXZ; SBE2PauseBuffer::CSBE2PauseBufferNode::Stop(void)
0x1800acc53  lea     rbx, [rdi+180h]
0x1800acc5a  xor     ebp, ebp
0x1800acc5c  cmp     [rbx], bp
0x1800acc5f  jz      short loc_1800ACCAF
0x1800acc61  mov     rax, [r15]
0x1800acc64  mov     rcx, r15
0x1800acc67  mov     rax, [rax+60h]
0x1800acc6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acc70  test    eax, eax
0x1800acc72  jz      short loc_1800ACCAF
0x1800acc74  lea     rax, [rsp+2A8h+var_268]
0x1800acc79  mov     [rsp+2A8h+var_268], ebp
0x1800acc7d  mov     [rsp+2A8h+var_278], rax; int *
0x1800acc82  lea     rcx, [rsp+2A8h+var_258]; this
0x1800acc87  mov     [rsp+2A8h+var_280], 4000000h; unsigned int
0x1800acc8f  mov     r8d, 80000000h; unsigned int
0x1800acc95  mov     rdx, rbx; unsigned __int16 *
0x1800acc98  mov     [rsp+2A8h+var_288], 3; unsigned int
0x1800acca0  call    ??0CFile@SBECoreUtil@@QEAA@PEBGKKKKPEAJ@Z; SBECoreUtil::CFile::CFile(ushort const *,ulong,ulong,ulong,ulong,long *)
0x1800acca5  lea     rcx, [rsp+2A8h+var_258]; this
0x1800accaa  call    ?Close@CFile@SBECoreUtil@@QEAAXXZ; SBECoreUtil::CFile::Close(void)
0x1800accaf  mov     rcx, rsi; lpCriticalSection
0x1800accb2  call    cs:__imp_EnterCriticalSection
0x1800accb8  lea     rbx, [rdi+140h]
0x1800accbf  mov     rcx, [rbx]
0x1800accc2  test    rcx, rcx
0x1800accc5  jz      short loc_1800ACCD3
0x1800accc7  mov     rax, [rcx]
0x1800accca  mov     rax, [rax+10h]
0x1800accce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800accd3  lea     rcx, [rdi+3A0h]; this
0x1800accda  mov     [rbx], rbp
0x1800accdd  call    ?CloseHandle@SBECoreUtil@@YAXAEAPEAXPEAX@Z; SBECoreUtil::CloseHandle(void * &,void *)
0x1800acce2  mov     rcx, rsi; lpCriticalSection
0x1800acce5  call    cs:__imp_LeaveCriticalSection
0x1800acceb  mov     rcx, [rdi+388h]
0x1800accf2  test    rcx, rcx
0x1800accf5  jz      short loc_1800ACD0A
0x1800accf7  add     rcx, 108h; this
0x1800accfe  call    ?Release@CRefCounted@SBF2@@QEAAJXZ; SBF2::CRefCounted::Release(void)
0x1800acd03  mov     [rdi+388h], rbp
0x1800acd0a  mov     rcx, rsi; lpCriticalSection
0x1800acd0d  call    cs:__imp_DeleteCriticalSection
0x1800acd13  mov     rcx, rbx
0x1800acd16  call    ??1?$QzCComPtr@UIStream@@@@QEAA@XZ; QzCComPtr<IStream>::~QzCComPtr<IStream>(void)
0x1800acd1b  lea     rcx, [rdi+138h]
0x1800acd22  call    ??$Release@PEAVCSALResidentNVP@SAL2@@@SAL2@@YAXAEAPEAVCSALResidentNVP@0@@Z; SAL2::Release<SAL2::CSALResidentNVP *>(SAL2::CSALResidentNVP * &)
0x1800acd27  lea     rcx, [rdi+130h]
0x1800acd2e  call    ??$Release@PEAVCSALResidentNVP@SAL2@@@SAL2@@YAXAEAPEAVCSALResidentNVP@0@@Z; SAL2::Release<SAL2::CSALResidentNVP *>(SAL2::CSALResidentNVP * &)
0x1800acd33  lock dec cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x1800acd3a  mov     rcx, rdi; this
0x1800acd3d  call    ??1SBEBasicTracers@@UEAA@XZ; SBEBasicTracers::~SBEBasicTracers(void)
0x1800acd42  mov     rcx, [rsp+2A8h+var_48]
0x1800acd4a  xor     rcx, rsp; StackCookie
0x1800acd4d  call    __security_check_cookie
0x1800acd52  add     rsp, 278h
0x1800acd59  pop     r15
0x1800acd5b  pop     r14
0x1800acd5d  pop     rdi
0x1800acd5e  pop     rsi
0x1800acd5f  pop     rbp
0x1800acd60  pop     rbx
0x1800acd61  retn
```
