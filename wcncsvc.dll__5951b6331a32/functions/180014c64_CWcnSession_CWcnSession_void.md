# CWcnSession::~CWcnSession(void)

- ea: `0x180014c64`
- end: `0x180014e6f`
- name: `??1CWcnSession@@AEAA@XZ`
- size: `523`
- prototype: `void __fastcall(CWcnSession *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180017424`

## callees

- `0x18000a5ac`
- `0x18000b414`
- `0x180014c64`
- `0x180018804`
- `0x18001cd04`
- `0x1800530ec`
- `0x18005a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180014dbc`
- `msvcrt!??3@YAXPEAX@Z` at `0x180014dd3`
- `msvcrt!??3@YAXPEAX@Z` at `0x180014df3`
- `msvcrt!??3@YAXPEAX@Z` at `0x180014dbc`
- `msvcrt!??3@YAXPEAX@Z` at `0x180014dd3`
- `msvcrt!??3@YAXPEAX@Z` at `0x180014df3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014e14`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014e14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014d6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014d7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014d6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014d7e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180014cd0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180014d06`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180014cd0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180014d06`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180014d18`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180014d18`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014cb4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014cea`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014cb4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014cea`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180014cc3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180014cf9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180014cc3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180014cf9`

## pseudocode

```c
void __fastcall CWcnSession::~CWcnSession(CWcnSession *this)
{
  struct _TP_TIMER *v2; // rcx
  struct _TP_TIMER *v3; // rcx
  struct _TP_WORK *v4; // rcx
  void (__fastcall ***v5)(_QWORD, __int64); // rcx
  void (__fastcall ***v6)(_QWORD, __int64); // rcx
  __int64 v7; // rax
  void *v8; // rcx
  void *v9; // rcx
  int i; // esi
  __int64 j; // rbp
  __int64 v12; // rdi
  CSbSafeBuffer **v13; // r12
  CSbSafeBuffer **k; // r14
  CSbSafeBuffer *v15; // r15

  if ( *((_QWORD *)this + 4) && *((_DWORD *)this + 56) >= 2u )
    CWcnSession::StartDisconnect(this, 1);
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 29);
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 29), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 29));
  }
  v3 = (struct _TP_TIMER *)*((_QWORD *)this + 30);
  if ( v3 )
  {
    SetThreadpoolTimer(v3, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 30), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 30));
  }
  v4 = (struct _TP_WORK *)*((_QWORD *)this + 31);
  if ( v4 )
    CloseThreadpoolWork(v4);
  v5 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 25);
  if ( v5 )
    (**v5)(v5, 1);
  v6 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 27);
  if ( v6 )
    (**v6)(v6, 1);
  v7 = *((_QWORD *)this + 4);
  if ( v7 )
    _InterlockedDecrement((volatile signed __int32 *)(v7 + 264));
  v8 = (void *)*((_QWORD *)this + 32);
  if ( v8 )
    CloseHandle(v8);
  v9 = (void *)*((_QWORD *)this + 33);
  if ( v9 )
    CloseHandle(v9);
  for ( i = 0; i < 2; ++i )
  {
    for ( j = 0; j != 3; ++j )
    {
      v12 = *((_QWORD *)this + 3 * (unsigned int)i + j + 186);
      if ( v12 )
      {
        v13 = *(CSbSafeBuffer ***)(v12 + 8);
        for ( k = *(CSbSafeBuffer ***)v12; k != v13; ++k )
        {
          v15 = *k;
          if ( *k )
          {
            CSbSafeBuffer::~CSbSafeBuffer(*k);
            operator delete(v15);
          }
        }
        if ( *(_QWORD *)v12 )
        {
          operator delete(*(void **)v12);
          *(_QWORD *)v12 = 0;
          *(_QWORD *)(v12 + 8) = 0;
          *(_QWORD *)(v12 + 16) = 0;
        }
        operator delete((void *)v12);
      }
    }
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1536));
  CCmCryptoState::~CCmCryptoState((CWcnSession *)((char *)this + 464));
  CSbSafeBuffer::~CSbSafeBuffer((CWcnSession *)((char *)this + 400));
  CSbSafeBuffer::~CSbSafeBuffer((CWcnSession *)((char *)this + 352));
  CSbSafeBuffer::~CSbSafeBuffer((CWcnSession *)((char *)this + 304));
  CWcnAttributeDatabase::~CWcnAttributeDatabase((CWcnSession *)((char *)this + 160));
  CWcnIdentity::~CWcnIdentity((CWcnSession *)((char *)this + 40));
}

```

## disassembly

```asm
0x180014c64  push    rbx
0x180014c66  push    rbp
0x180014c67  push    rsi
0x180014c68  push    rdi
0x180014c69  push    r12
0x180014c6b  push    r13
0x180014c6d  push    r14
0x180014c6f  push    r15
0x180014c71  sub     rsp, 28h
0x180014c75  mov     rbx, rcx
0x180014c78  mov     edi, 1
0x180014c7d  cmp     qword ptr [rcx+20h], 0
0x180014c82  jz      short loc_180014CA0
0x180014c84  mov     eax, [rcx+0E0h]
0x180014c8a  test    eax, eax
0x180014c8c  jz      short loc_180014CA0
0x180014c8e  mov     eax, [rcx+0E0h]
0x180014c94  cmp     eax, edi
0x180014c96  jz      short loc_180014CA0
0x180014c98  mov     dl, dil; bool
0x180014c9b  call    ?StartDisconnect@CWcnSession@@QEAAX_N@Z; CWcnSession::StartDisconnect(bool)
0x180014ca0  mov     rcx, [rbx+0E8h]; pti
0x180014ca7  test    rcx, rcx
0x180014caa  jz      short loc_180014CD6
0x180014cac  xor     r9d, r9d; msWindowLength
0x180014caf  xor     r8d, r8d; msPeriod
0x180014cb2  xor     edx, edx; pftDueTime
0x180014cb4  call    cs:__imp_SetThreadpoolTimer
0x180014cba  mov     edx, edi; fCancelPendingCallbacks
0x180014cbc  mov     rcx, [rbx+0E8h]; pti
0x180014cc3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180014cc9  mov     rcx, [rbx+0E8h]; pti
0x180014cd0  call    cs:__imp_CloseThreadpoolTimer
0x180014cd6  mov     rcx, [rbx+0F0h]; pti
0x180014cdd  test    rcx, rcx
0x180014ce0  jz      short loc_180014D0C
0x180014ce2  xor     r9d, r9d; msWindowLength
0x180014ce5  xor     r8d, r8d; msPeriod
0x180014ce8  xor     edx, edx; pftDueTime
0x180014cea  call    cs:__imp_SetThreadpoolTimer
0x180014cf0  mov     edx, edi; fCancelPendingCallbacks
0x180014cf2  mov     rcx, [rbx+0F0h]; pti
0x180014cf9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180014cff  mov     rcx, [rbx+0F0h]; pti
0x180014d06  call    cs:__imp_CloseThreadpoolTimer
0x180014d0c  mov     rcx, [rbx+0F8h]; pwk
0x180014d13  test    rcx, rcx
0x180014d16  jz      short loc_180014D1E
0x180014d18  call    cs:__imp_CloseThreadpoolWork
0x180014d1e  mov     rcx, [rbx+0C8h]
0x180014d25  test    rcx, rcx
0x180014d28  jz      short loc_180014D37
0x180014d2a  mov     rax, [rcx]
0x180014d2d  mov     edx, edi
0x180014d2f  mov     rax, [rax]
0x180014d32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d37  mov     rcx, [rbx+0D8h]
0x180014d3e  test    rcx, rcx
0x180014d41  jz      short loc_180014D50
0x180014d43  mov     rax, [rcx]
0x180014d46  mov     edx, edi
0x180014d48  mov     rax, [rax]
0x180014d4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d50  mov     rax, [rbx+20h]
0x180014d54  test    rax, rax
0x180014d57  jz      short loc_180014D60
0x180014d59  lock dec dword ptr [rax+108h]
0x180014d60  mov     rcx, [rbx+100h]; hObject
0x180014d67  test    rcx, rcx
0x180014d6a  jz      short loc_180014D72
0x180014d6c  call    cs:__imp_CloseHandle
0x180014d72  mov     rcx, [rbx+108h]; hObject
0x180014d79  test    rcx, rcx
0x180014d7c  jz      short loc_180014D84
0x180014d7e  call    cs:__imp_CloseHandle
0x180014d84  xor     esi, esi
0x180014d86  mov     eax, esi
0x180014d88  add     rax, 3Eh ; '>'
0x180014d8c  lea     rax, [rax+rax*2]
0x180014d90  lea     r13, [rbx+rax*8]
0x180014d94  xor     ebp, ebp
0x180014d96  mov     rdi, [r13+rbp*8+0]
0x180014d9b  test    rdi, rdi
0x180014d9e  jz      short loc_180014DF9
0x180014da0  mov     r12, [rdi+8]
0x180014da4  mov     r14, [rdi]
0x180014da7  jmp     short loc_180014DC6
0x180014da9  mov     r15, [r14]
0x180014dac  test    r15, r15
0x180014daf  jz      short loc_180014DC2
0x180014db1  mov     rcx, r15; this
0x180014db4  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x180014db9  mov     rcx, r15
0x180014dbc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180014dc2  add     r14, 8
0x180014dc6  cmp     r14, r12
0x180014dc9  jnz     short loc_180014DA9
0x180014dcb  mov     rcx, [rdi]
0x180014dce  test    rcx, rcx
0x180014dd1  jz      short loc_180014DF0
0x180014dd3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180014dd9  mov     qword ptr [rdi], 0
0x180014de0  mov     qword ptr [rdi+8], 0
0x180014de8  mov     qword ptr [rdi+10h], 0
0x180014df0  mov     rcx, rdi
0x180014df3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180014df9  inc     rbp
0x180014dfc  cmp     rbp, 3
0x180014e00  jnz     short loc_180014D96
0x180014e02  inc     esi
0x180014e04  cmp     esi, 2
0x180014e07  jl      loc_180014D86
0x180014e0d  lea     rcx, [rbx+600h]; lpCriticalSection
0x180014e14  call    cs:__imp_DeleteCriticalSection
0x180014e1a  lea     rcx, [rbx+1D0h]; this
0x180014e21  call    ??1CCmCryptoState@@QEAA@XZ; CCmCryptoState::~CCmCryptoState(void)
0x180014e26  lea     rcx, [rbx+190h]; this
0x180014e2d  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x180014e32  lea     rcx, [rbx+160h]; this
0x180014e39  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x180014e3e  lea     rcx, [rbx+130h]; this
0x180014e45  call    ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
0x180014e4a  lea     rcx, [rbx+0A0h]; this
0x180014e51  call    ??1CWcnAttributeDatabase@@QEAA@XZ; CWcnAttributeDatabase::~CWcnAttributeDatabase(void)
0x180014e56  lea     rcx, [rbx+28h]; this
0x180014e5a  add     rsp, 28h
0x180014e5e  pop     r15
0x180014e60  pop     r14
0x180014e62  pop     r13
0x180014e64  pop     r12
0x180014e66  pop     rdi
0x180014e67  pop     rsi
0x180014e68  pop     rbp
0x180014e69  pop     rbx
0x180014e6a  jmp     ??1CWcnIdentity@@QEAA@XZ; CWcnIdentity::~CWcnIdentity(void)
```
