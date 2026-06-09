# SAL2::CSALCommitQueue::CSALCommitQueue(SAL2::CSALPolicy *,SAL2::CSALCache *,SAL2::CSALLog *,SAL2::CSALFileSize *,SAL2::ISALIoMgr *,int,int,long *)

- ea: `0x180090fb8`
- end: `0x1800911dd`
- name: `??0CSALCommitQueue@SAL2@@AEAA@PEAVCSALPolicy@1@PEAVCSALCache@1@PEAVCSALLog@1@PEAVCSALFileSize@1@PEAVISALIoMgr@1@HHPEAJ@Z`
- size: `549`
- prototype: `__int64 __fastcall(SAL2::CSALCommitQueue *__hidden this, struct SAL2::CSALPolicy *, struct SAL2::CSALCache *, struct SAL2::CSALLog *, struct SAL2::CSALFileSize *, struct SAL2::ISALIoMgr *, int, int, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800918d4`

## callees

- `0x180044ec8`
- `0x18006201c`
- `0x1800627f0`
- `0x18007eac8`
- `0x18007fe60`
- `0x180090fb8`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180091187`
- `KERNEL32!CreateEventW` at `0x180091187`
- `KERNEL32!InitializeCriticalSection` at `0x180091074`
- `KERNEL32!InitializeCriticalSection` at `0x180091074`
- `KERNEL32!GetLastError` at `0x180091199`
- `KERNEL32!GetLastError` at `0x180091199`

## string_xrefs

- `0x1800911bb`: `multimedia\dshow\filters\sbe\sal\salcommit.cpp`

## pseudocode

```c
SAL2::CSALCommitQueue *__fastcall SAL2::CSALCommitQueue::CSALCommitQueue(
        SAL2::CSALCommitQueue *this,
        struct SAL2::CSALPolicy *a2,
        struct SAL2::CSALCache *a3,
        struct SAL2::CSALLog *a4,
        struct SAL2::CSALFileSize *a5,
        struct SAL2::ISALIoMgr *a6,
        int a7,
        int a8,
        int *a9)
{
  int v13; // ebx
  struct CEhEventTracer *v14; // rcx
  unsigned int v15; // r8d
  __int64 v16; // rax
  __int64 v17; // rax
  HANDLE EventW; // rax
  signed int LastError; // eax

  SBEBasicTracers::SBEBasicTracers(
    this,
    (const struct SBEBasicTracers *)(((unsigned __int64)a2 + 16)
                                   & ((unsigned __int128)-(__int128)(unsigned __int64)a2 >> 64)));
  *((_DWORD *)this + 68) = 0;
  *(_QWORD *)this = &SAL2::CSALCommitQueue::`vftable'{for `SBEBasicTracers'};
  *((_DWORD *)this + 70) = 0;
  *((_QWORD *)this + 33) = &SAL2::CSALCommitQueue::`vftable'{for `SAL2::CRefCounted'};
  *((_QWORD *)this + 39) = a5;
  *((_QWORD *)this + 40) = a6;
  *((_DWORD *)this + 82) = a7;
  *((_DWORD *)this + 83) = a8;
  *((_QWORD *)this + 36) = a3;
  *((_QWORD *)this + 37) = a2;
  *((_QWORD *)this + 38) = a4;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 336));
  *((_QWORD *)this + 47) = 0;
  *((_DWORD *)this + 96) = 0;
  *((_QWORD *)this + 49) = 0;
  v13 = *a9;
  *((_QWORD *)this + 51) = (char *)this + 400;
  *((_QWORD *)this + 50) = (char *)this + 400;
  *((_QWORD *)this + 52) = 0;
  *((_DWORD *)this + 106) = 0;
  *((_QWORD *)this + 54) = 0;
  *((_QWORD *)this + 55) = 0;
  *((_QWORD *)this + 56) = 0;
  *((_DWORD *)this + 114) = 0;
  *((_DWORD *)this + 115) = **((_DWORD **)a2 + 36);
  *((_DWORD *)this + 116) = *(_DWORD *)(*((_QWORD *)a2 + 36) + 4LL);
  *((_DWORD *)this + 117) = *(_DWORD *)(*((_QWORD *)a2 + 36) + 28LL);
  *((_DWORD *)this + 118) = *(_DWORD *)(*((_QWORD *)a2 + 36) + 32LL);
  *((_DWORD *)this + 119) = *(_DWORD *)(*((_QWORD *)a2 + 36) + 20LL);
  *((_DWORD *)this + 120) = *(_DWORD *)(*((_QWORD *)a2 + 36) + 24LL);
  if ( v13 < 0 )
  {
    v14 = (SAL2::CSALCommitQueue *)((char *)this + 88);
    v15 = 182;
LABEL_11:
    SBEBasicTracers::EtwTraceError(v14, "multimedia\\dshow\\filters\\sbe\\sal\\salcommit.cpp", v15, v13);
    goto LABEL_12;
  }
  SBECoreUtil::AddRef<SBEPerf::CeHomeETWSBE2PauseBuffer *>((char *)this + 296);
  SAL2::AddRef<SAL2::CSALCache *>((char *)this + 288);
  v16 = *((_QWORD *)this + 38);
  if ( v16 )
    _InterlockedIncrement((volatile signed __int32 *)(v16 + 8));
  v17 = *((_QWORD *)this + 39);
  if ( v17 )
    _InterlockedIncrement((volatile signed __int32 *)(v17 + 8));
  SBF2::AddRef<ISBFEvent *>((char *)this + 320);
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 49) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    v14 = (SAL2::CSALCommitQueue *)((char *)this + 48);
    v15 = 200;
    goto LABEL_11;
  }
LABEL_12:
  *a9 = v13;
  return this;
}

```

## disassembly

```asm
0x180090fb8  push    rbx
0x180090fba  push    rbp
0x180090fbb  push    rsi
0x180090fbc  push    rdi
0x180090fbd  push    r12
0x180090fbf  push    r13
0x180090fc1  push    r14
0x180090fc3  push    r15
0x180090fc5  sub     rsp, 28h
0x180090fc9  mov     rax, rdx
0x180090fcc  lea     r10, [rdx+10h]
0x180090fd0  mov     rsi, rdx
0x180090fd3  neg     rax
0x180090fd6  mov     rdi, r9
0x180090fd9  mov     rbx, r8
0x180090fdc  sbb     rdx, rdx
0x180090fdf  mov     r14, rcx
0x180090fe2  and     rdx, r10; struct SBEBasicTracers *
0x180090fe5  call    ??0SBEBasicTracers@@QEAA@PEBV0@@Z; SBEBasicTracers::SBEBasicTracers(SBEBasicTracers const *)
0x180090fea  xor     r13d, r13d
0x180090fed  lea     rax, ??_7CSALCommitQueue@SAL2@@6BSBEBasicTracers@@@; const SAL2::CSALCommitQueue::`vftable'{for `SBEBasicTracers'}
0x180090ff4  mov     [r14+110h], r13d
0x180090ffb  lea     r12, [r14+140h]
0x180091002  mov     [r14], rax
0x180091005  lea     r15, [r14+120h]
0x18009100c  lea     rax, ??_7CSALCommitQueue@SAL2@@6BCRefCounted@1@@; const SAL2::CSALCommitQueue::`vftable'{for `SAL2::CRefCounted'}
0x180091013  mov     [r14+118h], r13d
0x18009101a  mov     [r14+108h], rax
0x180091021  lea     rbp, [r14+128h]
0x180091028  mov     rax, [rsp+68h+arg_20]
0x180091030  lea     rcx, [r14+150h]; lpCriticalSection
0x180091037  mov     [r14+138h], rax
0x18009103e  mov     rax, [rsp+68h+arg_28]
0x180091046  mov     [r12], rax
0x18009104a  mov     eax, [rsp+68h+arg_30]
0x180091051  mov     [r14+148h], eax
0x180091058  mov     eax, [rsp+68h+arg_38]
0x18009105f  mov     [r14+14Ch], eax
0x180091066  mov     [r15], rbx
0x180091069  mov     [rbp+0], rsi
0x18009106d  mov     [r14+130h], rdi
0x180091074  call    cs:__imp_InitializeCriticalSection
0x18009107a  mov     rdi, [rsp+68h+arg_40]
0x180091082  lea     rax, [r14+190h]
0x180091089  mov     [r14+178h], r13
0x180091090  mov     [r14+180h], r13d
0x180091097  mov     [r14+188h], r13
0x18009109e  mov     ebx, [rdi]
0x1800910a0  mov     [rax+8], rax
0x1800910a4  mov     [rax], rax
0x1800910a7  mov     [rax+10h], r13
0x1800910ab  mov     [r14+1A8h], r13d
0x1800910b2  mov     [r14+1B0h], r13
0x1800910b9  mov     [r14+1B8h], r13
0x1800910c0  mov     [r14+1C0h], r13
0x1800910c7  mov     [r14+1C8h], r13d
0x1800910ce  mov     rax, [rsi+120h]
0x1800910d5  mov     ecx, [rax]
0x1800910d7  mov     [r14+1CCh], ecx
0x1800910de  mov     rax, [rsi+120h]
0x1800910e5  mov     ecx, [rax+4]
0x1800910e8  mov     [r14+1D0h], ecx
0x1800910ef  mov     rax, [rsi+120h]
0x1800910f6  mov     ecx, [rax+1Ch]
0x1800910f9  mov     [r14+1D4h], ecx
0x180091100  mov     rax, [rsi+120h]
0x180091107  mov     ecx, [rax+20h]
0x18009110a  mov     [r14+1D8h], ecx
0x180091111  mov     rax, [rsi+120h]
0x180091118  mov     ecx, [rax+14h]
0x18009111b  mov     [r14+1DCh], ecx
0x180091122  mov     rax, [rsi+120h]
0x180091129  mov     ecx, [rax+18h]
0x18009112c  mov     [r14+1E0h], ecx
0x180091133  test    ebx, ebx
0x180091135  jns     short loc_180091143
0x180091137  lea     rcx, [r14+58h]
0x18009113b  mov     r8d, 0B6h
0x180091141  jmp     short loc_1800911B8
0x180091143  mov     rcx, rbp
0x180091146  call    ??$AddRef@PEAVCeHomeETWSBE2PauseBuffer@SBEPerf@@@SBECoreUtil@@YAXAEAPEAVCeHomeETWSBE2PauseBuffer@SBEPerf@@@Z; SBECoreUtil::AddRef<SBEPerf::CeHomeETWSBE2PauseBuffer *>(SBEPerf::CeHomeETWSBE2PauseBuffer * &)
0x18009114b  mov     rcx, r15
0x18009114e  call    ??$AddRef@PEAVCSALCache@SAL2@@@SAL2@@YAXAEAPEAVCSALCache@0@@Z; SAL2::AddRef<SAL2::CSALCache *>(SAL2::CSALCache * &)
0x180091153  mov     rax, [r14+130h]
0x18009115a  test    rax, rax
0x18009115d  jz      short loc_180091163
0x18009115f  lock inc dword ptr [rax+8]
0x180091163  mov     rax, [r14+138h]
0x18009116a  test    rax, rax
0x18009116d  jz      short loc_180091173
0x18009116f  lock inc dword ptr [rax+8]
0x180091173  mov     rcx, r12
0x180091176  call    ??$AddRef@PEAUISBFEvent@@@SBF2@@YAXAEAPEAUISBFEvent@@@Z; SBF2::AddRef<ISBFEvent *>(ISBFEvent * &)
0x18009117b  xor     r9d, r9d; lpName
0x18009117e  xor     r8d, r8d; bInitialState
0x180091181  xor     ecx, ecx; lpEventAttributes
0x180091183  lea     edx, [r9+1]; bManualReset
0x180091187  call    cs:__imp_CreateEventW
0x18009118d  mov     [r14+188h], rax
0x180091194  test    rax, rax
0x180091197  jnz     short loc_1800911C7
0x180091199  call    cs:__imp_GetLastError
0x18009119f  mov     ebx, eax
0x1800911a1  test    eax, eax
0x1800911a3  jle     short loc_1800911AE
0x1800911a5  movzx   ebx, ax
0x1800911a8  or      ebx, 80070000h
0x1800911ae  lea     rcx, [r14+30h]; struct CEhEventTracer *
0x1800911b2  mov     r8d, 0C8h; unsigned int
0x1800911b8  mov     r9d, ebx; unsigned int
0x1800911bb  lea     rdx, aMultimediaDsho_16; "multimedia\\dshow\\filters\\sbe\\sal\\s"...
0x1800911c2  call    ?EtwTraceError@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDKK@Z; SBEBasicTracers::EtwTraceError(CEhEventTracer &,char const *,ulong,ulong)
0x1800911c7  mov     [rdi], ebx
0x1800911c9  mov     rax, r14
0x1800911cc  add     rsp, 28h
0x1800911d0  pop     r15
0x1800911d2  pop     r14
0x1800911d4  pop     r13
0x1800911d6  pop     r12
0x1800911d8  pop     rdi
0x1800911d9  pop     rsi
0x1800911da  pop     rbp
0x1800911db  pop     rbx
0x1800911dc  retn
```
