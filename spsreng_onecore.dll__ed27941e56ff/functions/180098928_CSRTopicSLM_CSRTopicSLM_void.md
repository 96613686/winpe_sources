# CSRTopicSLM::~CSRTopicSLM(void)

- ea: `0x180098928`
- end: `0x180098a41`
- name: `??1CSRTopicSLM@@QEAA@XZ`
- size: `281`
- prototype: `void __fastcall(CSRTopicSLM *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180006e0c`

## callees

- `0x180002aac`
- `0x1800061d0`
- `0x18005b974`
- `0x180098928`
- `0x180098a48`
- `0x180098a98`
- `0x180098c9c`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180098944`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180098944`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180098972`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009897c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180098972`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009897c`

## pseudocode

```c
void __fastcall CSRTopicSLM::~CSRTopicSLM(CSRTopicSLM *this)
{
  void *v2; // rcx
  __int64 v3; // rcx
  unsigned int v4; // edx
  CPPT *v5; // rcx
  CTrigramStore *v6; // rcx
  CMRU *v7; // rcx

  *(_QWORD *)this = &CSRTopicSLM::`vftable';
  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
    CloseHandle(v2);
  CSRTopicSLM::DeleteTrigramLMChain((CSRTopicSLM *)v2, *((struct TRIGRAMLM **)this + 20));
  v3 = *((_QWORD *)this + 3);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 5);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 1);
  CWinHeap::Free(*((CWinHeap **)this + 18), *((void **)this + 32));
  CWinHeap::Free(*((CWinHeap **)this + 18), *((void **)this + 33));
  CWinHeap::Free(*((CWinHeap **)this + 18), *((void **)this + 34));
  v5 = (CPPT *)*((_QWORD *)this + 19);
  if ( v5 )
    CPPT::`scalar deleting destructor'(v5, v4);
  v6 = (CTrigramStore *)*((_QWORD *)this + 21);
  if ( v6 )
    CTrigramStore::`scalar deleting destructor'(v6, v4);
  v7 = (CMRU *)*((_QWORD *)this + 22);
  if ( v7 )
    CMRU::`scalar deleting destructor'(v7, v4);
  CSpDynamicString::_free((CSRTopicSLM *)((char *)this + 136));
  CSpDynamicString::_free((CSRTopicSLM *)((char *)this + 128));
  CSpDynamicString::_free((CSRTopicSLM *)((char *)this + 120));
  CSpDynamicString::_free((CSRTopicSLM *)((char *)this + 112));
  CSpDynamicString::_free((CSRTopicSLM *)((char *)this + 104));
  CSpDynamicString::_free((CSRTopicSLM *)((char *)this + 96));
  CSpDynamicString::_free((CSRTopicSLM *)((char *)this + 88));
  CSpDynamicString::_free((CSRTopicSLM *)((char *)this + 80));
}

```

## disassembly

```asm
0x180098928  push    rbx
0x18009892a  sub     rsp, 20h
0x18009892e  mov     rbx, rcx
0x180098931  lea     rax, ??_7CSRTopicSLM@@6B@; const CSRTopicSLM::`vftable'
0x180098938  mov     [rcx], rax
0x18009893b  mov     rcx, [rcx+8]; hObject
0x18009893f  test    rcx, rcx
0x180098942  jz      short loc_18009894A
0x180098944  call    cs:__imp_CloseHandle
0x18009894a  mov     rdx, [rbx+0A0h]; struct TRIGRAMLM *
0x180098951  call    ?DeleteTrigramLMChain@CSRTopicSLM@@AEAAXPEAVTRIGRAMLM@@@Z; CSRTopicSLM::DeleteTrigramLMChain(TRIGRAMLM *)
0x180098956  mov     rcx, [rbx+18h]
0x18009895a  test    rcx, rcx
0x18009895d  jz      short loc_18009896B
0x18009895f  mov     rax, [rcx]
0x180098962  mov     rax, [rax+10h]
0x180098966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009896b  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180098972  call    cs:__imp_DeleteCriticalSection
0x180098978  lea     rcx, [rbx+28h]; lpCriticalSection
0x18009897c  call    cs:__imp_DeleteCriticalSection
0x180098982  mov     rdx, [rbx+100h]; void *
0x180098989  mov     rcx, [rbx+90h]; this
0x180098990  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x180098995  mov     rdx, [rbx+108h]; void *
0x18009899c  mov     rcx, [rbx+90h]; this
0x1800989a3  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x1800989a8  mov     rdx, [rbx+110h]; void *
0x1800989af  mov     rcx, [rbx+90h]; this
0x1800989b6  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x1800989bb  mov     rcx, [rbx+98h]; this
0x1800989c2  test    rcx, rcx
0x1800989c5  jz      short loc_1800989CC
0x1800989c7  call    ??_GCPPT@@QEAAPEAXI@Z; CPPT::`scalar deleting destructor'(uint)
0x1800989cc  mov     rcx, [rbx+0A8h]; this
0x1800989d3  test    rcx, rcx
0x1800989d6  jz      short loc_1800989DD
0x1800989d8  call    ??_GCTrigramStore@@QEAAPEAXI@Z; CTrigramStore::`scalar deleting destructor'(uint)
0x1800989dd  mov     rcx, [rbx+0B0h]; this
0x1800989e4  test    rcx, rcx
0x1800989e7  jz      short loc_1800989EE
0x1800989e9  call    ??_GCMRU@@QEAAPEAXI@Z; CMRU::`scalar deleting destructor'(uint)
0x1800989ee  lea     rcx, [rbx+88h]; this
0x1800989f5  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x1800989fa  lea     rcx, [rbx+80h]; this
0x180098a01  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x180098a06  lea     rcx, [rbx+78h]; this
0x180098a0a  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x180098a0f  lea     rcx, [rbx+70h]; this
0x180098a13  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x180098a18  lea     rcx, [rbx+68h]; this
0x180098a1c  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x180098a21  lea     rcx, [rbx+60h]; this
0x180098a25  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x180098a2a  lea     rcx, [rbx+58h]; this
0x180098a2e  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x180098a33  lea     rcx, [rbx+50h]; this
0x180098a37  add     rsp, 20h
0x180098a3b  pop     rbx
0x180098a3c  jmp     ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
```
