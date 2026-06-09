# CDVRReader::~CDVRReader(void)

- ea: `0x180063bbc`
- end: `0x180063ce2`
- name: `??1CDVRReader@@UEAA@XZ`
- size: `294`
- prototype: `void __fastcall(CDVRReader *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180063e60`

## callees

- `0x1800017e0`
- `0x18000c1c4`
- `0x18000d5a8`
- `0x180063b90`
- `0x180063bbc`
- `0x180064814`
- `0x180067980`
- `0x18006874c`
- `0x18007b5a0`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180063cb0`
- `KERNEL32!CloseHandle` at `0x180063cb0`
- `KERNEL32!DeleteCriticalSection` at `0x180063cbd`
- `KERNEL32!DeleteCriticalSection` at `0x180063cbd`
- `ADVAPI32!RegCloseKey` at `0x180063c21`
- `ADVAPI32!RegCloseKey` at `0x180063c33`
- `ADVAPI32!RegCloseKey` at `0x180063c21`
- `ADVAPI32!RegCloseKey` at `0x180063c33`

## pseudocode

```c
void __fastcall CDVRReader::~CDVRReader(CDVRReader *this)
{
  unsigned int v2; // edx
  COutstandingOps *v3; // rcx
  HKEY v4; // rcx
  HKEY v5; // rcx
  void *v6; // rdi
  void (__fastcall ***v7)(_QWORD, __int64); // rcx
  CAsyncIo *v8; // rcx
  COutstandingOps *v9; // rcx
  void *v10; // rcx

  *(_QWORD *)this = &CDVRReader::`vftable'{for `IDVRReader'};
  *((_QWORD *)this + 1) = &CDVRReader::`vftable'{for `IDVRSourceAdviseSink'};
  *((_QWORD *)this + 2) = &CDVRReader::`vftable'{for `IDVRIORecordingAttributes'};
  *((_QWORD *)this + 3) = &CDVRReader::`vftable'{for `IDVRReaderNotify'};
  *((_QWORD *)this + 4) = &CDVRReader::`vftable'{for `IDVRCrossBarNotify'};
  CDVRReader::Close(this);
  v3 = (COutstandingOps *)*((_QWORD *)this + 34);
  if ( v3 )
    COutstandingOps::WaitAllCompleted(v3, v2);
  v4 = (HKEY)*((_QWORD *)this + 19);
  if ( v4 )
    RegCloseKey(v4);
  v5 = (HKEY)*((_QWORD *)this + 20);
  if ( v5 )
    RegCloseKey(v5);
  v6 = (void *)*((_QWORD *)this + 58);
  if ( v6 )
  {
    CDVRFileCollection::CClientInfo::~CClientInfo(*((CDVRFileCollection::CClientInfo **)this + 58));
    operator delete(v6, 0x20u);
  }
  v7 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 33);
  if ( v7 )
    (**v7)(v7, 1);
  v8 = (CAsyncIo *)*((_QWORD *)this + 21);
  if ( v8 )
    CAsyncIo::Release(v8);
  v9 = (COutstandingOps *)*((_QWORD *)this + 34);
  if ( v9 )
    COutstandingOps::Release(v9);
  CPVRIOCounters::Release(*((CPVRIOCounters **)this + 32));
  v10 = (void *)*((_QWORD *)this + 61);
  if ( v10 )
    CloseHandle(v10);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 344));
  CDVRFileCollection::CClientInfo::~CClientInfo((CDVRReader *)((char *)this + 432));
  SBECoreUtil::TCDenseVector<CSBERecAttribute *>::~TCDenseVector<CSBERecAttribute *>((char *)this + 40);
}

```

## disassembly

```asm
0x180063bbc  mov     [rsp+arg_0], rbx
0x180063bc1  push    rdi
0x180063bc2  sub     rsp, 20h
0x180063bc6  lea     rax, ??_7CDVRReader@@6BIDVRReader@@@; const CDVRReader::`vftable'{for `IDVRReader'}
0x180063bcd  mov     rbx, rcx
0x180063bd0  mov     [rcx], rax
0x180063bd3  lea     rax, ??_7CDVRReader@@6BIDVRSourceAdviseSink@@@; const CDVRReader::`vftable'{for `IDVRSourceAdviseSink'}
0x180063bda  mov     [rcx+8], rax
0x180063bde  lea     rax, ??_7CDVRReader@@6BIDVRIORecordingAttributes@@@; const CDVRReader::`vftable'{for `IDVRIORecordingAttributes'}
0x180063be5  mov     [rcx+10h], rax
0x180063be9  lea     rax, ??_7CDVRReader@@6BIDVRReaderNotify@@@; const CDVRReader::`vftable'{for `IDVRReaderNotify'}
0x180063bf0  mov     [rcx+18h], rax
0x180063bf4  lea     rax, ??_7CDVRReader@@6BIDVRCrossBarNotify@@@; const CDVRReader::`vftable'{for `IDVRCrossBarNotify'}
0x180063bfb  mov     [rcx+20h], rax
0x180063bff  call    ?Close@CDVRReader@@IEAAJXZ; CDVRReader::Close(void)
0x180063c04  mov     rcx, [rbx+110h]; this
0x180063c0b  test    rcx, rcx
0x180063c0e  jz      short loc_180063C15
0x180063c10  call    ?WaitAllCompleted@COutstandingOps@@QEAAKK@Z; COutstandingOps::WaitAllCompleted(ulong)
0x180063c15  mov     rcx, [rbx+98h]; hKey
0x180063c1c  test    rcx, rcx
0x180063c1f  jz      short loc_180063C27
0x180063c21  call    cs:__imp_RegCloseKey
0x180063c27  mov     rcx, [rbx+0A0h]; hKey
0x180063c2e  test    rcx, rcx
0x180063c31  jz      short loc_180063C39
0x180063c33  call    cs:__imp_RegCloseKey
0x180063c39  mov     rdi, [rbx+1D0h]
0x180063c40  test    rdi, rdi
0x180063c43  jz      short loc_180063C5A
0x180063c45  mov     rcx, rdi; this
0x180063c48  call    ??1CClientInfo@CDVRFileCollection@@QEAA@XZ; CDVRFileCollection::CClientInfo::~CClientInfo(void)
0x180063c4d  mov     edx, 20h ; ' '; unsigned __int64
0x180063c52  mov     rcx, rdi; void *
0x180063c55  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180063c5a  mov     rcx, [rbx+108h]
0x180063c61  test    rcx, rcx
0x180063c64  jz      short loc_180063C76
0x180063c66  mov     rax, [rcx]
0x180063c69  mov     edx, 1
0x180063c6e  mov     rax, [rax]
0x180063c71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063c76  mov     rcx, [rbx+0A8h]; this
0x180063c7d  test    rcx, rcx
0x180063c80  jz      short loc_180063C87
0x180063c82  call    ?Release@CAsyncIo@@QEAAJXZ; CAsyncIo::Release(void)
0x180063c87  mov     rcx, [rbx+110h]; this
0x180063c8e  test    rcx, rcx
0x180063c91  jz      short loc_180063C98
0x180063c93  call    ?Release@COutstandingOps@@QEAAJXZ; COutstandingOps::Release(void)
0x180063c98  mov     rcx, [rbx+100h]; this
0x180063c9f  call    ?Release@CPVRIOCounters@@QEAAJXZ; CPVRIOCounters::Release(void)
0x180063ca4  mov     rcx, [rbx+1E8h]; hObject
0x180063cab  test    rcx, rcx
0x180063cae  jz      short loc_180063CB6
0x180063cb0  call    cs:__imp_CloseHandle
0x180063cb6  lea     rcx, [rbx+158h]; lpCriticalSection
0x180063cbd  call    cs:__imp_DeleteCriticalSection
0x180063cc3  lea     rcx, [rbx+1B0h]; this
0x180063cca  call    ??1CClientInfo@CDVRFileCollection@@QEAA@XZ; CDVRFileCollection::CClientInfo::~CClientInfo(void)
0x180063ccf  lea     rcx, [rbx+28h]
0x180063cd3  mov     rbx, [rsp+28h+arg_0]
0x180063cd8  add     rsp, 20h
0x180063cdc  pop     rdi
0x180063cdd  jmp     ??1?$TCDenseVector@PEAVCSBERecAttribute@@@SBECoreUtil@@UEAA@XZ; SBECoreUtil::TCDenseVector<CSBERecAttribute *>::~TCDenseVector<CSBERecAttribute *>(void)
```
