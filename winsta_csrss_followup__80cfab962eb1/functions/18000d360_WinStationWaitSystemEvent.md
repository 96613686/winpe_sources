# WinStationWaitSystemEvent

- ea: `0x18000d360`
- end: `0x18000d75a`
- name: `WinStationWaitSystemEvent`
- size: `1018`
- prototype: `__int64 __fastcall(CPublicBinding *this, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x1800041a0`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x18000b8d4`
- `0x18000c0c4`
- `0x18000c180`
- `0x18000d360`
- `0x1800249e8`
- `0x18002a8ac`
- `0x18002fae8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d5bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d5d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d5bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d5d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d483`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d483`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000d5ec`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000d5ec`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d4f2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d4f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d4d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d58f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d668`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d6f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d4d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d58f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d668`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d6f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d464`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d549`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d628`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d6a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d464`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d549`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d628`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d6a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d67c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d67c`

## string_xrefs

- `0x18000d397`: `Failed to open binding`

## pseudocode

```c
char __fastcall WinStationWaitSystemEvent(CPublicBinding *this, signed int a2, unsigned int *a3)
{
  CWaitEventCollect *v7; // rbx
  unsigned int v8; // edi
  int v9; // edx
  int v10; // r8d
  int v11; // ecx
  int v12; // edx
  struct _LIST_ENTRY *i; // r14
  struct _LIST_ENTRY *v14; // rsi
  char v15; // r14
  HANDLE EventW; // rsi
  CWaitEventCollect *v17; // rax
  CWaitEventCollect *v18; // rax
  _QWORD *v19; // rcx
  int started; // eax
  DWORD v21; // eax
  struct _LIST_ENTRY *Flink; // rdi
  CPublicBinding **v23; // rcx
  int v24; // esi
  _QWORD *v25; // rdi
  _QWORD *v26; // rax
  _QWORD *v27; // rcx
  unsigned __int8 v28; // bl
  unsigned __int16 v29; // [rsp+20h] [rbp-48h] BYREF
  __int64 v30; // [rsp+28h] [rbp-40h]

  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)&v29, this, 0);
  if ( !CSmartPublicBinding::operator void *(&v29) )
  {
    _DbgPrintMessage(8, "Failed to open binding");
    CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)&v29);
    return 0;
  }
  if ( v30 && !*(_DWORD *)(v30 + 52) )
  {
    v7 = 0;
    if ( a2 == 0x7FFFFFFF )
    {
      v8 = -1;
    }
    else
    {
      v9 = ((a2 & 8) != 0 ? 0x102 : 0) | 1;
      if ( (a2 & 1) == 0 )
        v9 = (a2 & 8) != 0 ? 0x102 : 0;
      v10 = v9 | 0x80;
      if ( (a2 & 2) == 0 )
        v10 = v9;
      v11 = v10 | 0x204;
      if ( (a2 & 0x10) == 0 )
        v11 = v10;
      v12 = v11 | 0x10;
      if ( (a2 & 0x40) == 0 )
        v12 = v11;
      v8 = v12 | 8;
      if ( (a2 & 0x20) == 0 )
        v8 = v12;
      if ( (a2 & 0x80) != 0 )
        v8 |= 0x366u;
      if ( !v8 )
        goto LABEL_40;
    }
    EnterCriticalSection(&gWinstaCrit);
    for ( i = gSystemEventsListHead.Flink; i != &gSystemEventsListHead; i = i->Flink )
    {
      v14 = i - 102;
      if ( GetCurrentThreadId() == LODWORD(i[-1].Blink)
        && this == (CPublicBinding *)v14[101].Flink
        && v8 == LODWORD(v14[100].Blink)
        && (unsigned int)(LODWORD(v14[12].Blink) - 3) > 1 )
      {
        v7 = (CWaitEventCollect *)&i[-102];
        _InterlockedIncrement((volatile signed __int32 *)&v14->Blink);
        break;
      }
    }
    LeaveCriticalSection(&gWinstaCrit);
    if ( !v7 )
    {
      v15 = 0;
      EventW = CreateEventW(0, 0, 0, 0);
      if ( EventW )
      {
        v17 = (CWaitEventCollect *)operator new(0x670u, (const struct std::nothrow_t *)&std::nothrow);
        if ( v17 )
        {
          v18 = CWaitEventCollect::CWaitEventCollect(v17, EventW, this);
          v7 = v18;
          if ( v18 )
          {
            _InterlockedIncrement((volatile signed __int32 *)v18 + 2);
            EnterCriticalSection(&gWinstaCrit);
            v19 = (_QWORD *)qword_18005A430;
            if ( *(struct _LIST_ENTRY **)qword_18005A430 != &gSystemEventsListHead )
              goto LABEL_60;
            *((_QWORD *)v7 + 204) = &gSystemEventsListHead;
            *((_QWORD *)v7 + 205) = v19;
            *v19 = (char *)v7 + 1632;
            qword_18005A430 = (__int64)v7 + 1632;
            _InterlockedIncrement((volatile signed __int32 *)v7 + 2);
            LeaveCriticalSection(&gWinstaCrit);
            *((_DWORD *)v7 + 402) = v8;
            started = CWaitItem::StartWait(v7, -1, v8);
            if ( started < 0 )
            {
              v21 = ConvertHRESULT2WIN32(started);
              SetLastError(v21);
LABEL_41:
              EventW = 0;
              goto LABEL_42;
            }
            goto LABEL_37;
          }
        }
        else
        {
          v7 = 0;
        }
        SetLastError(8u);
      }
LABEL_42:
      if ( a2 < 0 )
      {
        EnterCriticalSection(&gWinstaCrit);
        Flink = gSystemEventsListHead.Flink;
        while ( Flink != &gSystemEventsListHead )
        {
          v23 = (CPublicBinding **)&Flink[-102];
          Flink = Flink->Flink;
          if ( this == v23[202] )
            CWaitItem::StopWait((CWaitItem *)v23);
        }
        LeaveCriticalSection(&gWinstaCrit);
      }
      if ( EventW )
        CloseHandle(EventW);
      if ( !v7 )
        goto LABEL_59;
      if ( (unsigned int)(*((_DWORD *)v7 + 50) - 3) > 1 )
      {
LABEL_58:
        CWaitItem::Release(v7);
LABEL_59:
        CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)&v29);
        return v15;
      }
      v24 = 0;
      EnterCriticalSection(&gWinstaCrit);
      v25 = (_QWORD *)((char *)v7 + 1632);
      v26 = (_QWORD *)*((_QWORD *)v7 + 204);
      if ( v26 == (_QWORD *)((char *)v7 + 1632) )
      {
LABEL_56:
        *((_QWORD *)v7 + 205) = (char *)v7 + 1632;
        *v25 = v25;
        LeaveCriticalSection(&gWinstaCrit);
        if ( v24 )
          CWaitItem::StopWait(v7);
        goto LABEL_58;
      }
      if ( (_QWORD *)v26[1] == v25 )
      {
        v27 = (_QWORD *)*((_QWORD *)v7 + 205);
        if ( (_QWORD *)*v27 == v25 )
        {
          *v27 = v26;
          v26[1] = v27;
          CWaitItem::Release(v7);
          *((_QWORD *)v7 + 205) = (char *)v7 + 1632;
          v24 = 1;
          goto LABEL_56;
        }
      }
LABEL_60:
      __fastfail(3u);
    }
    do
LABEL_37:
      WaitForSingleObject(*((HANDLE *)v7 + 200), 0xFFFFFFFF);
    while ( !*((_DWORD *)v7 + 398) && *((_DWORD *)v7 + 50) != 4 );
    *a3 = _InterlockedExchange((volatile __int32 *)v7 + 398, 0);
LABEL_40:
    v15 = 1;
    goto LABEL_41;
  }
  v28 = Legacy_WinStationWaitSystemEvent(this, a2, a3);
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)&v29);
  return v28;
}

```

## disassembly

```asm
0x18000d360  push    rbx
0x18000d362  push    rbp
0x18000d363  push    rsi
0x18000d364  push    rdi
0x18000d365  push    r12
0x18000d367  push    r14
0x18000d369  push    r15
0x18000d36b  sub     rsp, 30h
0x18000d36f  mov     r15d, edx
0x18000d372  mov     r12, r8
0x18000d375  mov     rdx, rcx; void *
0x18000d378  mov     rbp, rcx
0x18000d37b  lea     rcx, [rsp+68h+var_48]; this
0x18000d380  xor     r8d, r8d; int
0x18000d383  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x18000d388  lea     rcx, [rsp+68h+var_48]; unsigned __int16 *
0x18000d38d  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000d392  test    rax, rax
0x18000d395  jnz     short loc_18000D3B7
0x18000d397  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x18000d39e  lea     ecx, [rax+8]; int
0x18000d3a1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d3a6  lea     rcx, [rsp+68h+var_48]; this
0x18000d3ab  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18000d3b0  xor     al, al
0x18000d3b2  jmp     loc_18000D74A
0x18000d3b7  mov     rax, [rsp+68h+var_40]
0x18000d3bc  test    rax, rax
0x18000d3bf  jz      loc_18000D72E
0x18000d3c5  cmp     dword ptr [rax+34h], 0
0x18000d3c9  jnz     loc_18000D72E
0x18000d3cf  xor     ebx, ebx
0x18000d3d1  lea     rsi, ?gSystemEventsListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY gSystemEventsListHead
0x18000d3d8  cmp     r15d, 7FFFFFFFh
0x18000d3df  jnz     short loc_18000D3E6
0x18000d3e1  or      edi, 0FFFFFFFFh
0x18000d3e4  jmp     short loc_18000D45D
0x18000d3e6  xor     eax, eax
0x18000d3e8  mov     r9d, 80h
0x18000d3ee  mov     ecx, r15d
0x18000d3f1  and     ecx, 8
0x18000d3f4  sub     al, cl
0x18000d3f6  mov     dl, al
0x18000d3f8  mov     eax, r15d
0x18000d3fb  neg     dl
0x18000d3fd  sbb     ecx, ecx
0x18000d3ff  and     ecx, 102h
0x18000d405  mov     edx, ecx
0x18000d407  or      edx, 1
0x18000d40a  test    r15b, 1
0x18000d40e  cmovz   edx, ecx
0x18000d411  mov     r8d, edx
0x18000d414  or      r8d, r9d
0x18000d417  test    r15b, 2
0x18000d41b  cmovz   r8d, edx
0x18000d41f  mov     ecx, r8d
0x18000d422  or      ecx, 204h
0x18000d428  test    r15b, 10h
0x18000d42c  cmovz   ecx, r8d
0x18000d430  mov     edx, ecx
0x18000d432  or      edx, 10h
0x18000d435  test    r15b, 40h
0x18000d439  cmovz   edx, ecx
0x18000d43c  mov     edi, edx
0x18000d43e  or      edi, 8
0x18000d441  test    r15b, 20h
0x18000d445  cmovz   edi, edx
0x18000d448  and     eax, r9d
0x18000d44b  test    al, al
0x18000d44d  jz      short loc_18000D455
0x18000d44f  or      edi, 366h
0x18000d455  test    edi, edi
0x18000d457  jz      loc_18000D617
0x18000d45d  lea     rcx, ?gWinstaCrit@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d464  call    cs:__imp_EnterCriticalSection
0x18000d46b  nop     dword ptr [rax+rax+00h]
0x18000d470  mov     r14, cs:?gSystemEventsListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY gSystemEventsListHead
0x18000d477  cmp     r14, rsi
0x18000d47a  jz      short loc_18000D4C9
0x18000d47c  lea     rsi, [r14-660h]
0x18000d483  call    cs:__imp_GetCurrentThreadId
0x18000d48a  nop     dword ptr [rax+rax+00h]
0x18000d48f  cmp     eax, [rsi+658h]
0x18000d495  jnz     short loc_18000D4B6
0x18000d497  cmp     rbp, [rsi+650h]
0x18000d49e  jnz     short loc_18000D4B6
0x18000d4a0  cmp     edi, [rsi+648h]
0x18000d4a6  jnz     short loc_18000D4B6
0x18000d4a8  mov     eax, [rsi+0C8h]
0x18000d4ae  sub     eax, 3
0x18000d4b1  cmp     eax, 1
0x18000d4b4  ja      short loc_18000D4C2
0x18000d4b6  mov     r14, [r14]
0x18000d4b9  lea     rsi, ?gSystemEventsListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY gSystemEventsListHead
0x18000d4c0  jmp     short loc_18000D477
0x18000d4c2  mov     rbx, rsi
0x18000d4c5  lock inc dword ptr [rsi+8]
0x18000d4c9  lea     rcx, ?gWinstaCrit@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d4d0  call    cs:__imp_LeaveCriticalSection
0x18000d4d7  nop     dword ptr [rax+rax+00h]
0x18000d4dc  test    rbx, rbx
0x18000d4df  jnz     loc_18000D5DF
0x18000d4e5  xor     r9d, r9d; lpName
0x18000d4e8  xor     r8d, r8d; bInitialState
0x18000d4eb  xor     edx, edx; bManualReset
0x18000d4ed  xor     ecx, ecx; lpEventAttributes
0x18000d4ef  xor     r14b, r14b
0x18000d4f2  call    cs:__imp_CreateEventW
0x18000d4f9  nop     dword ptr [rax+rax+00h]
0x18000d4fe  mov     rsi, rax
0x18000d501  test    rax, rax
0x18000d504  jz      loc_18000D61C
0x18000d50a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d511  mov     ecx, 670h; unsigned __int64
0x18000d516  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000d51b  test    rax, rax
0x18000d51e  jz      loc_18000D5CA
0x18000d524  mov     r8, rbp; void *
0x18000d527  mov     rdx, rsi; void *
0x18000d52a  mov     rcx, rax; this
0x18000d52d  call    ??0CWaitEventCollect@@QEAA@PEAX0@Z; CWaitEventCollect::CWaitEventCollect(void *,void *)
0x18000d532  mov     rbx, rax
0x18000d535  test    rax, rax
0x18000d538  jz      loc_18000D5CC
0x18000d53e  lock inc dword ptr [rax+8]
0x18000d542  lea     rcx, ?gWinstaCrit@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d549  call    cs:__imp_EnterCriticalSection
0x18000d550  nop     dword ptr [rax+rax+00h]
0x18000d555  mov     rcx, cs:qword_18005A430
0x18000d55c  lea     rsi, ?gSystemEventsListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY gSystemEventsListHead
0x18000d563  cmp     [rcx], rsi
0x18000d566  jnz     loc_18000D727
0x18000d56c  lea     rax, [rbx+660h]
0x18000d573  mov     [rax], rsi
0x18000d576  mov     [rax+8], rcx
0x18000d57a  mov     [rcx], rax
0x18000d57d  mov     cs:qword_18005A430, rax
0x18000d584  lock inc dword ptr [rbx+8]
0x18000d588  lea     rcx, ?gWinstaCrit@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d58f  call    cs:__imp_LeaveCriticalSection
0x18000d596  nop     dword ptr [rax+rax+00h]
0x18000d59b  mov     r8d, edi; unsigned int
0x18000d59e  mov     [rbx+648h], edi
0x18000d5a4  or      edx, 0FFFFFFFFh; int
0x18000d5a7  mov     rcx, rbx; Context
0x18000d5aa  call    ?StartWait@CWaitItem@@QEAAJJK@Z; CWaitItem::StartWait(long,ulong)
0x18000d5af  test    eax, eax
0x18000d5b1  jns     short loc_18000D5DF
0x18000d5b3  mov     ecx, eax; int
0x18000d5b5  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18000d5ba  mov     ecx, eax; dwErrCode
0x18000d5bc  call    cs:__imp_SetLastError
0x18000d5c3  nop     dword ptr [rax+rax+00h]
0x18000d5c8  jmp     short loc_18000D61A
0x18000d5ca  xor     ebx, ebx
0x18000d5cc  mov     ecx, 8; dwErrCode
0x18000d5d1  call    cs:__imp_SetLastError
0x18000d5d8  nop     dword ptr [rax+rax+00h]
0x18000d5dd  jmp     short loc_18000D61C
0x18000d5df  mov     rdi, rbx
0x18000d5e2  mov     rcx, [rdi+640h]; hHandle
0x18000d5e9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000d5ec  call    cs:__imp_WaitForSingleObject
0x18000d5f3  nop     dword ptr [rax+rax+00h]
0x18000d5f8  mov     eax, [rbx+638h]
0x18000d5fe  test    eax, eax
0x18000d600  jnz     short loc_18000D60B
0x18000d602  cmp     dword ptr [rbx+0C8h], 4
0x18000d609  jnz     short loc_18000D5E2
0x18000d60b  xor     eax, eax
0x18000d60d  xchg    eax, [rbx+638h]
0x18000d613  mov     [r12], eax
0x18000d617  mov     r14b, 1
0x18000d61a  xor     esi, esi
0x18000d61c  test    r15d, r15d
0x18000d61f  jns     short loc_18000D674
0x18000d621  lea     rcx, ?gWinstaCrit@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d628  call    cs:__imp_EnterCriticalSection
0x18000d62f  nop     dword ptr [rax+rax+00h]
0x18000d634  mov     rdi, cs:?gSystemEventsListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY gSystemEventsListHead
0x18000d63b  lea     r15, ?gSystemEventsListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY gSystemEventsListHead
0x18000d642  jmp     short loc_18000D65C
0x18000d644  lea     rcx, [rdi-660h]; this
0x18000d64b  mov     rdi, [rdi]
0x18000d64e  cmp     rbp, [rcx+650h]
0x18000d655  jnz     short loc_18000D65C
0x18000d657  call    ?StopWait@CWaitItem@@QEAAJXZ; CWaitItem::StopWait(void)
0x18000d65c  cmp     rdi, r15
0x18000d65f  jnz     short loc_18000D644
0x18000d661  lea     rcx, ?gWinstaCrit@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d668  call    cs:__imp_LeaveCriticalSection
0x18000d66f  nop     dword ptr [rax+rax+00h]
0x18000d674  test    rsi, rsi
0x18000d677  jz      short loc_18000D688
0x18000d679  mov     rcx, rsi; hObject
0x18000d67c  call    cs:__imp_CloseHandle
0x18000d683  nop     dword ptr [rax+rax+00h]
0x18000d688  test    rbx, rbx
0x18000d68b  jz      loc_18000D718
0x18000d691  mov     eax, [rbx+0C8h]
0x18000d697  sub     eax, 3
0x18000d69a  cmp     eax, 1
0x18000d69d  ja      short loc_18000D710
0x18000d69f  lea     rcx, ?gWinstaCrit@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d6a6  xor     esi, esi
0x18000d6a8  call    cs:__imp_EnterCriticalSection
0x18000d6af  nop     dword ptr [rax+rax+00h]
0x18000d6b4  lea     rdi, [rbx+660h]
0x18000d6bb  mov     rax, [rdi]
0x18000d6be  cmp     rax, rdi
0x18000d6c1  jz      short loc_18000D6EA
0x18000d6c3  cmp     [rax+8], rdi
0x18000d6c7  jnz     short loc_18000D727
0x18000d6c9  mov     rcx, [rdi+8]
0x18000d6cd  cmp     [rcx], rdi
0x18000d6d0  jnz     short loc_18000D727
0x18000d6d2  mov     [rcx], rax
0x18000d6d5  mov     [rax+8], rcx
0x18000d6d9  mov     rcx, rbx; this
0x18000d6dc  call    ?Release@CWaitItem@@QEAAJXZ; CWaitItem::Release(void)
0x18000d6e1  mov     [rdi+8], rdi
0x18000d6e5  mov     esi, 1
0x18000d6ea  lea     rcx, ?gWinstaCrit@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d6f1  mov     [rdi+8], rdi
0x18000d6f5  mov     [rdi], rdi
0x18000d6f8  call    cs:__imp_LeaveCriticalSection
0x18000d6ff  nop     dword ptr [rax+rax+00h]
0x18000d704  test    esi, esi
0x18000d706  jz      short loc_18000D710
0x18000d708  mov     rcx, rbx; this
0x18000d70b  call    ?StopWait@CWaitItem@@QEAAJXZ; CWaitItem::StopWait(void)
0x18000d710  mov     rcx, rbx; this
0x18000d713  call    ?Release@CWaitItem@@QEAAJXZ; CWaitItem::Release(void)
0x18000d718  lea     rcx, [rsp+68h+var_48]; this
0x18000d71d  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18000d722  mov     al, r14b
0x18000d725  jmp     short loc_18000D74A
0x18000d727  mov     ecx, 3
0x18000d72c  int     29h; Win8: RtlFailFast(ecx)
0x18000d72e  mov     r8, r12; unsigned int *
0x18000d731  mov     edx, r15d; unsigned int
0x18000d734  mov     rcx, rbp; this
0x18000d737  call    ?Legacy_WinStationWaitSystemEvent@@YAEPEAXKPEAK@Z; Legacy_WinStationWaitSystemEvent(void *,ulong,ulong *)
0x18000d73c  lea     rcx, [rsp+68h+var_48]; this
0x18000d741  mov     bl, al
0x18000d743  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18000d748  mov     al, bl
0x18000d74a  add     rsp, 30h
0x18000d74e  pop     r15
0x18000d750  pop     r14
0x18000d752  pop     r12
0x18000d754  pop     rdi
0x18000d755  pop     rsi
0x18000d756  pop     rbp
0x18000d757  pop     rbx
0x18000d758  retn
```
