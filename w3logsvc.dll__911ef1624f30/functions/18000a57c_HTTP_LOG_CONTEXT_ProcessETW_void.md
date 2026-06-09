# HTTP_LOG_CONTEXT::ProcessETW(void)

- ea: `0x18000a57c`
- end: `0x18000a906`
- name: `?ProcessETW@HTTP_LOG_CONTEXT@@QEAAJXZ`
- size: `906`
- prototype: `__int64 __fastcall(HTTP_LOG_CONTEXT *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000a290`

## callees

- `0x1800062c4`
- `0x180007670`
- `0x180007e20`
- `0x180008174`
- `0x180009ae4`
- `0x18000a124`
- `0x18000a36c`
- `0x18000a57c`
- `0x18000b964`
- `0x18000e9a0`
- `0x180010010`

## import_xrefs

- `msvcrt!_strnicmp` at `0x18000a6ce`
- `msvcrt!_strnicmp` at `0x18000a6ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a7ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a7ab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a78f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a78f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000a637`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000a637`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000a653`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000a653`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18000a6f2`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18000a6f2`
- `iisutil!?CopyA@STRU@@QEAAJPEBDK@Z` at `0x18000a618`
- `iisutil!?CopyA@STRU@@QEAAJPEBDK@Z` at `0x18000a618`
- `iisutil!PuDbgPrintError` at `0x18000a806`
- `iisutil!PuDbgPrintError` at `0x18000a806`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000a5ab`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000a5ab`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000a8de`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000a8de`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000a8d2`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000a8d2`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000a5d7`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000a5d7`

## string_xrefs

- `0x18000a7f8`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logcontext.cpp`

## pseudocode

```c
__int64 __fastcall HTTP_LOG_CONTEXT::ProcessETW(HTTP_LOG_CONTEXT *this)
{
  int v2; // r12d
  LOG_WRITER *v3; // r14
  struct HTTP_LOG_PIPE_CLIENT *v4; // r15
  RTL_SRWLOCK *v5; // r13
  int PipeClient; // ebx
  const char *v7; // rdx
  unsigned __int16 *v8; // rbx
  struct HTTP_LOG_SITE_ENTRY *v9; // rdi
  int v10; // ecx
  int Writer; // eax
  LOG_WRITER *v12; // rbx
  __int64 v13; // rcx
  unsigned int v14; // ebx
  LOG_WRITER *v15; // rcx
  LOG_WRITER *v17; // [rsp+30h] [rbp-D0h] BYREF
  struct HTTP_LOG_SITE_ENTRY *v18; // [rsp+38h] [rbp-C8h] BYREF
  struct HTTP_LOG_PIPE_CLIENT *v19; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v20[32]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v21; // [rsp+68h] [rbp-98h]
  _BYTE v22[32]; // [rsp+80h] [rbp-80h] BYREF
  char *v23; // [rsp+A0h] [rbp-60h]
  char v24[56]; // [rsp+B8h] [rbp-48h] BYREF

  STRU::STRU((STRU *)v20);
  v2 = 0;
  v18 = 0;
  v3 = 0;
  v17 = 0;
  v4 = 0;
  v19 = 0;
  STRA::STRA((STRA *)v22, v24, 0x38u);
  v5 = (RTL_SRWLOCK *)g_pLogSvcAdmin;
  PipeClient = HTTP_LOG_CONTEXT::ParseHttpLogData(this);
  if ( PipeClient >= 0 )
  {
    v7 = (char *)this + 924;
    if ( !*((_DWORD *)this + 295) )
      v7 = (char *)this + 881;
    PipeClient = STRU::CopyA((STRU *)v20, v7, 8u);
    if ( PipeClient >= 0 )
    {
      v8 = v21;
      AcquireSRWLockShared(v5 + 142);
      LODWORD(v8) = HTTP_LOG_SITE_TABLE::ContainsNoLock((HTTP_LOG_SITE_TABLE *)&v5[5], v8, &v18);
      ReleaseSRWLockShared(v5 + 142);
      v9 = v18;
      if ( !(_DWORD)v8 )
      {
        PipeClient = -2147023728;
LABEL_35:
        if ( v9 )
          (*(void (__fastcall **)(struct HTTP_LOG_SITE_ENTRY *))(*(_QWORD *)v9 + 8LL))(v9);
        if ( v3 && _InterlockedExchangeAdd((volatile signed __int32 *)v3 + 168, 0xFFFFFFFF) == 1 )
          (**(void (__fastcall ***)(LOG_WRITER *, __int64))v3)(v3, 1);
        if ( v4 && _InterlockedExchangeAdd((volatile signed __int32 *)v4 + 6, 0xFFFFFFFF) == 1 )
          (**(void (__fastcall ***)(struct HTTP_LOG_PIPE_CLIENT *, __int64))v4)(v4, 1);
        goto LABEL_43;
      }
      v10 = *((_DWORD *)v5[141].Ptr + 56);
      if ( v10 == 2 )
      {
        Writer = HTTP_LOG_SITE_TABLE::GetWriter((HTTP_LOG_SITE_TABLE *)&v5[5], &v17);
      }
      else
      {
        if ( v10 )
        {
          PipeClient = 0;
          goto LABEL_35;
        }
        Writer = HTTP_LOG_SITE_ENTRY::GetWriter(v18, &v17);
      }
      PipeClient = Writer;
      if ( Writer < 0 )
        goto LABEL_33;
      if ( *((_DWORD *)this + 295) )
        goto LABEL_31;
      if ( _strnicmp((const char *)this + 905, "0000000000000000", 0x10u) )
      {
        LODWORD(v18) = 0;
        PipeClient = STRA::Copy((STRA *)v22, (const char *)this + 826, 0x37u);
        if ( PipeClient >= 0 )
        {
          PipeClient = LOG_SVC_ADMIN::GetPipeClient(
                         (LOG_SVC_ADMIN *)g_pLogSvcAdmin,
                         v23,
                         *((_DWORD *)this + 298) == 0,
                         &v19);
          if ( PipeClient < 0 )
          {
            v3 = v17;
            LOG_WRITER::Write((RTL_SRWLOCK *)v17, this);
            v4 = v19;
            goto LABEL_35;
          }
          v12 = v17;
          v13 = *((_QWORD *)this + 148);
          if ( v13 && _InterlockedExchangeAdd((volatile signed __int32 *)(v13 + 672), 0xFFFFFFFF) == 1 )
            (**(void (__fastcall ***)(__int64, __int64))v13)(v13, 1);
          *((_QWORD *)this + 148) = v12;
          v3 = 0;
          v14 = *(_DWORD *)(*((_QWORD *)v9 + 11) + 36LL);
          if ( v14 )
          {
            EnterCriticalSection((LPCRITICAL_SECTION)v9 + 1);
            if ( ++*((_DWORD *)v9 + 29) >= v14 )
            {
              v2 = 1;
              *((_DWORD *)v9 + 29) = 0;
            }
            LeaveCriticalSection((LPCRITICAL_SECTION)v9 + 1);
          }
          v4 = v19;
          PipeClient = HTTP_LOG_PIPE_CLIENT::SendQueryToWorkerProcess(v19, this, v2, (int *)&v18);
          if ( PipeClient >= 0 )
            goto LABEL_35;
          if ( (g_dwDebugFlags & 0xF) != 0 )
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logcontext.cpp",
              555,
              "HTTP_LOG_CONTEXT::ProcessETW",
              PipeClient,
              "Failed to send request to worker process");
          if ( (_DWORD)v18 )
            goto LABEL_35;
          v15 = (LOG_WRITER *)*((_QWORD *)this + 148);
LABEL_29:
          PipeClient = LOG_WRITER::Write((RTL_SRWLOCK *)v15, this);
          goto LABEL_35;
        }
LABEL_33:
        v3 = v17;
        goto LABEL_35;
      }
      if ( *((_DWORD *)this + 295) )
      {
LABEL_31:
        PipeClient = HTTP_LOG_CONTEXT::CreateCustomLogString(this);
        if ( PipeClient < 0 )
          goto LABEL_33;
      }
      v3 = v17;
      v15 = v17;
      goto LABEL_29;
    }
  }
LABEL_43:
  (*(void (__fastcall **)(HTTP_LOG_CONTEXT *))(*(_QWORD *)this + 8LL))(this);
  STRA::~STRA((STRA *)v22);
  STRU::~STRU((STRU *)v20);
  return (unsigned int)PipeClient;
}

```

## disassembly

```asm
0x18000a57c  push    rbp
0x18000a57e  push    rbx
0x18000a57f  push    rsi
0x18000a580  push    rdi
0x18000a581  push    r12
0x18000a583  push    r13
0x18000a585  push    r14
0x18000a587  push    r15
0x18000a589  lea     rbp, [rsp-8]
0x18000a58e  sub     rsp, 108h
0x18000a595  mov     rax, cs:__security_cookie
0x18000a59c  xor     rax, rsp
0x18000a59f  mov     [rbp+40h+var_50], rax
0x18000a5a3  mov     rsi, rcx
0x18000a5a6  lea     rcx, [rsp+140h+var_F8]
0x18000a5ab  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000a5b1  nop
0x18000a5b2  xor     r12d, r12d
0x18000a5b5  mov     [rsp+140h+var_108], r12
0x18000a5ba  mov     r14d, r12d
0x18000a5bd  mov     [rsp+140h+var_110], r12
0x18000a5c2  mov     r15d, r12d
0x18000a5c5  mov     [rsp+140h+var_100], r12
0x18000a5ca  lea     r8d, [r12+38h]
0x18000a5cf  lea     rdx, [rbp+40h+var_88]
0x18000a5d3  lea     rcx, [rbp+40h+var_C0]
0x18000a5d7  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18000a5dd  nop
0x18000a5de  mov     r13, cs:?g_pLogSvcAdmin@@3PEAVLOG_SVC_ADMIN@@EA; LOG_SVC_ADMIN * g_pLogSvcAdmin
0x18000a5e5  mov     rcx, rsi; this
0x18000a5e8  call    ?ParseHttpLogData@HTTP_LOG_CONTEXT@@QEAAJXZ; HTTP_LOG_CONTEXT::ParseHttpLogData(void)
0x18000a5ed  mov     ebx, eax
0x18000a5ef  test    eax, eax
0x18000a5f1  js      loc_18000A8BE
0x18000a5f7  lea     r8d, [r12+8]
0x18000a5fc  lea     rcx, [rsp+140h+var_F8]
0x18000a601  cmp     [rsi+49Ch], r12d
0x18000a608  lea     rdx, [rsi+39Ch]
0x18000a60f  jnz     short loc_18000A618
0x18000a611  lea     rdx, [rsi+371h]
0x18000a618  call    cs:__imp_?CopyA@STRU@@QEAAJPEBDK@Z; STRU::CopyA(char const *,ulong)
0x18000a61e  mov     ebx, eax
0x18000a620  test    eax, eax
0x18000a622  js      loc_18000A8BE
0x18000a628  mov     rbx, [rsp+140h+var_D8]
0x18000a62d  lea     rdi, [r13+470h]
0x18000a634  mov     rcx, rdi; SRWLock
0x18000a637  call    cs:__imp_AcquireSRWLockShared
0x18000a63d  lea     r8, [rsp+140h+var_108]; struct HTTP_LOG_SITE_ENTRY **
0x18000a642  mov     rdx, rbx; unsigned __int16 *
0x18000a645  lea     rcx, [r13+28h]; this
0x18000a649  call    ?ContainsNoLock@HTTP_LOG_SITE_TABLE@@AEAAHPEBGPEAPEAVHTTP_LOG_SITE_ENTRY@@@Z; HTTP_LOG_SITE_TABLE::ContainsNoLock(ushort const *,HTTP_LOG_SITE_ENTRY * *)
0x18000a64e  mov     ebx, eax
0x18000a650  mov     rcx, rdi; SRWLock
0x18000a653  call    cs:__imp_ReleaseSRWLockShared
0x18000a659  mov     rdi, [rsp+140h+var_108]
0x18000a65e  test    ebx, ebx
0x18000a660  jnz     short loc_18000A66C
0x18000a662  mov     ebx, 80070490h
0x18000a667  jmp     loc_18000A851
0x18000a66c  mov     rax, [r13+468h]
0x18000a673  mov     ecx, [rax+0E0h]
0x18000a679  cmp     ecx, 2
0x18000a67c  jnz     short loc_18000A68E
0x18000a67e  lea     rdx, [rsp+140h+var_110]; struct LOG_WRITER **
0x18000a683  lea     rcx, [r13+28h]; this
0x18000a687  call    ?GetWriter@HTTP_LOG_SITE_TABLE@@QEAAJPEAPEAVLOG_WRITER@@@Z; HTTP_LOG_SITE_TABLE::GetWriter(LOG_WRITER * *)
0x18000a68c  jmp     short loc_18000A6A3
0x18000a68e  test    ecx, ecx
0x18000a690  jnz     loc_18000A84E
0x18000a696  lea     rdx, [rsp+140h+var_110]; struct LOG_WRITER **
0x18000a69b  mov     rcx, rdi; this
0x18000a69e  call    ?GetWriter@HTTP_LOG_SITE_ENTRY@@QEAAJPEAPEAVLOG_WRITER@@@Z; HTTP_LOG_SITE_ENTRY::GetWriter(LOG_WRITER * *)
0x18000a6a3  test    eax, eax
0x18000a6a5  mov     ebx, eax
0x18000a6a7  js      loc_18000A847
0x18000a6ad  cmp     [rsi+49Ch], r12d
0x18000a6b4  jnz     loc_18000A82F
0x18000a6ba  lea     rcx, [rsi+389h]; String1
0x18000a6c1  mov     r8d, 10h; MaxCount
0x18000a6c7  lea     rdx, String2; "0000000000000000"
0x18000a6ce  call    cs:__imp__strnicmp
0x18000a6d4  test    eax, eax
0x18000a6d6  jz      loc_18000A826
0x18000a6dc  mov     dword ptr [rsp+140h+var_108], r12d
0x18000a6e1  lea     rdx, [rsi+33Ah]
0x18000a6e8  mov     r8d, 37h ; '7'
0x18000a6ee  lea     rcx, [rbp+40h+var_C0]
0x18000a6f2  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x18000a6f8  mov     ebx, eax
0x18000a6fa  test    eax, eax
0x18000a6fc  js      loc_18000A847
0x18000a702  mov     r8d, r12d
0x18000a705  cmp     [rsi+4A8h], r12d
0x18000a70c  setz    r8b; int
0x18000a710  lea     r9, [rsp+140h+var_100]; struct HTTP_LOG_PIPE_CLIENT **
0x18000a715  mov     rdx, [rbp+40h+var_A0]; char *
0x18000a719  mov     rcx, cs:?g_pLogSvcAdmin@@3PEAVLOG_SVC_ADMIN@@EA; this
0x18000a720  call    ?GetPipeClient@LOG_SVC_ADMIN@@QEAAJPEBDHPEAPEAVHTTP_LOG_PIPE_CLIENT@@@Z; LOG_SVC_ADMIN::GetPipeClient(char const *,int,HTTP_LOG_PIPE_CLIENT * *)
0x18000a725  mov     ebx, eax
0x18000a727  test    eax, eax
0x18000a729  jns     short loc_18000A745
0x18000a72b  mov     rdx, rsi; struct HTTP_LOG_CONTEXT *
0x18000a72e  mov     r14, [rsp+140h+var_110]
0x18000a733  mov     rcx, r14; this
0x18000a736  call    ?Write@LOG_WRITER@@QEAAJPEAVHTTP_LOG_CONTEXT@@@Z; LOG_WRITER::Write(HTTP_LOG_CONTEXT *)
0x18000a73b  mov     r15, [rsp+140h+var_100]
0x18000a740  jmp     loc_18000A851
0x18000a745  mov     rbx, [rsp+140h+var_110]
0x18000a74a  mov     rcx, [rsi+4A0h]
0x18000a751  test    rcx, rcx
0x18000a754  jz      short loc_18000A776
0x18000a756  or      eax, 0FFFFFFFFh
0x18000a759  lock xadd [rcx+2A0h], eax
0x18000a761  cmp     eax, 1
0x18000a764  jnz     short loc_18000A776
0x18000a766  mov     rax, [rcx]
0x18000a769  mov     edx, 1
0x18000a76e  mov     rax, [rax]
0x18000a771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a776  mov     [rsi+4A0h], rbx
0x18000a77d  mov     r14, r12
0x18000a780  mov     rax, [rdi+58h]
0x18000a784  mov     ebx, [rax+24h]
0x18000a787  test    ebx, ebx
0x18000a789  jz      short loc_18000A7B1
0x18000a78b  lea     rcx, [rdi+28h]; lpCriticalSection
0x18000a78f  call    cs:__imp_EnterCriticalSection
0x18000a795  inc     dword ptr [rdi+74h]
0x18000a798  cmp     [rdi+74h], ebx
0x18000a79b  jb      short loc_18000A7A7
0x18000a79d  mov     r12d, 1
0x18000a7a3  mov     [rdi+74h], r14d
0x18000a7a7  lea     rcx, [rdi+28h]; lpCriticalSection
0x18000a7ab  call    cs:__imp_LeaveCriticalSection
0x18000a7b1  lea     r9, [rsp+140h+var_108]; int *
0x18000a7b6  mov     r8d, r12d; int
0x18000a7b9  mov     rdx, rsi; struct HTTP_LOG_CONTEXT *
0x18000a7bc  mov     r15, [rsp+140h+var_100]
0x18000a7c1  mov     rcx, r15; this
0x18000a7c4  call    ?SendQueryToWorkerProcess@HTTP_LOG_PIPE_CLIENT@@QEAAJPEAVHTTP_LOG_CONTEXT@@HPEAH@Z; HTTP_LOG_PIPE_CLIENT::SendQueryToWorkerProcess(HTTP_LOG_CONTEXT *,int,int *)
0x18000a7c9  mov     ebx, eax
0x18000a7cb  xor     r12d, r12d
0x18000a7ce  test    eax, eax
0x18000a7d0  jns     short loc_18000A851
0x18000a7d2  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000a7d9  jz      short loc_18000A80C
0x18000a7db  lea     rax, aFailedToSendRe; "Failed to send request to worker proces"...
0x18000a7e2  mov     [rsp+140h+var_118], rax
0x18000a7e7  mov     [rsp+140h+var_120], ebx
0x18000a7eb  lea     r9, aHttpLogContext_2; "HTTP_LOG_CONTEXT::ProcessETW"
0x18000a7f2  mov     r8d, 22Bh
0x18000a7f8  lea     rdx, aServercommonIn_8; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000a7ff  mov     rcx, cs:g_pDebug
0x18000a806  call    cs:__imp_PuDbgPrintError
0x18000a80c  cmp     dword ptr [rsp+140h+var_108], r12d
0x18000a811  jnz     short loc_18000A851
0x18000a813  mov     rcx, [rsi+4A0h]; this
0x18000a81a  mov     rdx, rsi; struct HTTP_LOG_CONTEXT *
0x18000a81d  call    ?Write@LOG_WRITER@@QEAAJPEAVHTTP_LOG_CONTEXT@@@Z; LOG_WRITER::Write(HTTP_LOG_CONTEXT *)
0x18000a822  mov     ebx, eax
0x18000a824  jmp     short loc_18000A851
0x18000a826  cmp     [rsi+49Ch], r12d
0x18000a82d  jz      short loc_18000A83D
0x18000a82f  mov     rcx, rsi; this
0x18000a832  call    ?CreateCustomLogString@HTTP_LOG_CONTEXT@@QEAAJXZ; HTTP_LOG_CONTEXT::CreateCustomLogString(void)
0x18000a837  mov     ebx, eax
0x18000a839  test    eax, eax
0x18000a83b  js      short loc_18000A847
0x18000a83d  mov     r14, [rsp+140h+var_110]
0x18000a842  mov     rcx, r14
0x18000a845  jmp     short loc_18000A81A
0x18000a847  mov     r14, [rsp+140h+var_110]
0x18000a84c  jmp     short loc_18000A851
0x18000a84e  mov     ebx, r12d
0x18000a851  test    rdi, rdi
0x18000a854  jz      short loc_18000A865
0x18000a856  mov     rax, [rdi]
0x18000a859  mov     rcx, rdi
0x18000a85c  mov     rax, [rax+8]
0x18000a860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a865  test    r14, r14
0x18000a868  jz      short loc_18000A893
0x18000a86a  or      eax, 0FFFFFFFFh
0x18000a86d  lock xadd [r14+2A0h], eax
0x18000a876  cmp     eax, 1
0x18000a879  jnz     short loc_18000A893
0x18000a87b  test    r14, r14
0x18000a87e  jz      short loc_18000A893
0x18000a880  mov     rax, [r14]
0x18000a883  mov     edx, 1
0x18000a888  mov     rcx, r14
0x18000a88b  mov     rax, [rax]
0x18000a88e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a893  test    r15, r15
0x18000a896  jz      short loc_18000A8BE
0x18000a898  or      eax, 0FFFFFFFFh
0x18000a89b  lock xadd [r15+18h], eax
0x18000a8a1  cmp     eax, 1
0x18000a8a4  jnz     short loc_18000A8BE
0x18000a8a6  test    r15, r15
0x18000a8a9  jz      short loc_18000A8BE
0x18000a8ab  mov     rax, [r15]
0x18000a8ae  mov     edx, 1
0x18000a8b3  mov     rcx, r15
0x18000a8b6  mov     rax, [rax]
0x18000a8b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8be  mov     rax, [rsi]
0x18000a8c1  mov     rcx, rsi
0x18000a8c4  mov     rax, [rax+8]
0x18000a8c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8cd  nop
0x18000a8ce  lea     rcx, [rbp+40h+var_C0]
0x18000a8d2  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000a8d8  nop
0x18000a8d9  lea     rcx, [rsp+140h+var_F8]
0x18000a8de  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000a8e4  mov     eax, ebx
0x18000a8e6  mov     rcx, [rbp+40h+var_50]
0x18000a8ea  xor     rcx, rsp; StackCookie
0x18000a8ed  call    __security_check_cookie
0x18000a8f2  add     rsp, 108h
0x18000a8f9  pop     r15
0x18000a8fb  pop     r14
0x18000a8fd  pop     r13
0x18000a8ff  pop     r12
0x18000a901  pop     rdi
0x18000a902  pop     rsi
0x18000a903  pop     rbx
0x18000a904  pop     rbp
0x18000a905  retn
```
