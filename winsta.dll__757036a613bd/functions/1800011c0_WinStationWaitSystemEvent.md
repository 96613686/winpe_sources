# WinStationWaitSystemEvent

- ea: `0x1800011c0`
- end: `0x18000155d`
- name: `WinStationWaitSystemEvent`
- size: `925`
- prototype: `__int64 __fastcall(CPublicBinding *this, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x1800011c0`
- `0x180001b68`
- `0x1800022f0`
- `0x1800023a0`
- `0x180005c30`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x1800230b8`
- `0x180028cdc`
- `0x18002d668`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800013f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001403`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800013f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001403`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800012dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800012dd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180001418`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180001418`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180001340`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180001340`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001324`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800013cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001488`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001502`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001324`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800013cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001488`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001502`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800012c4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000138d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000144e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800014b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800012c4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000138d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000144e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800014b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001496`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001496`

## string_xrefs

- `0x1800011f7`: `Failed to open binding`

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
            v19 = (_QWORD *)qword_180057430;
            if ( *(struct _LIST_ENTRY **)qword_180057430 != &gSystemEventsListHead )
              goto LABEL_60;
            *((_QWORD *)v7 + 204) = &gSystemEventsListHead;
            *((_QWORD *)v7 + 205) = v19;
            *v19 = (char *)v7 + 1632;
            qword_180057430 = (__int64)v7 + 1632;
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
0x1800011c0  push    rbx
0x1800011c2  push    rbp
0x1800011c3  push    rsi
0x1800011c4  push    rdi
0x1800011c5  push    r12
0x1800011c7  push    r14
0x1800011c9  push    r15
0x1800011cb  sub     rsp, 30h
0x1800011cf  mov     r15d, edx
0x1800011d2  mov     r12, r8
0x1800011d5  mov     rdx, rcx; void *
0x1800011d8  mov     rbp, rcx
0x1800011db  lea     rcx, [rsp+68h+var_48]; this
0x1800011e0  xor     r8d, r8d; int
0x1800011e3  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x1800011e8  lea     rcx, [rsp+68h+var_48]; unsigned __int16 *
0x1800011ed  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800011f2  test    rax, rax
0x1800011f5  jnz     short loc_180001217
0x1800011f7  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x1800011fe  lea     ecx, [rax+8]; int
0x180001201  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180001206  lea     rcx, [rsp+68h+var_48]; this
0x18000120b  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180001210  xor     al, al
0x180001212  jmp     loc_18000154E
0x180001217  mov     rax, [rsp+68h+var_40]
0x18000121c  test    rax, rax
0x18000121f  jz      loc_180001532
0x180001225  cmp     dword ptr [rax+34h], 0
0x180001229  jnz     loc_180001532
0x18000122f  xor     ebx, ebx
0x180001231  lea     rsi, ?gSystemEventsListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY gSystemEventsListHead
0x180001238  cmp     r15d, 7FFFFFFFh
0x18000123f  jnz     short loc_180001246
0x180001241  or      edi, 0FFFFFFFFh
0x180001244  jmp     short loc_1800012BD
0x180001246  xor     eax, eax
0x180001248  mov     r9d, 80h
0x18000124e  mov     ecx, r15d
0x180001251  and     ecx, 8
0x180001254  sub     al, cl
0x180001256  mov     dl, al
0x180001258  mov     eax, r15d
0x18000125b  neg     dl
0x18000125d  sbb     ecx, ecx
0x18000125f  and     ecx, 102h
0x180001265  mov     edx, ecx
0x180001267  or      edx, 1
0x18000126a  test    r15b, 1
0x18000126e  cmovz   edx, ecx
0x180001271  mov     r8d, edx
0x180001274  or      r8d, r9d
0x180001277  test    r15b, 2
0x18000127b  cmovz   r8d, edx
0x18000127f  mov     ecx, r8d
0x180001282  or      ecx, 204h
0x180001288  test    r15b, 10h
0x18000128c  cmovz   ecx, r8d
0x180001290  mov     edx, ecx
0x180001292  or      edx, 10h
0x180001295  test    r15b, 40h
0x180001299  cmovz   edx, ecx
0x18000129c  mov     edi, edx
0x18000129e  or      edi, 8
0x1800012a1  test    r15b, 20h
0x1800012a5  cmovz   edi, edx
0x1800012a8  and     eax, r9d
0x1800012ab  test    al, al
0x1800012ad  jz      short loc_1800012B5
0x1800012af  or      edi, 366h
0x1800012b5  test    edi, edi
0x1800012b7  jz      loc_18000143D
0x1800012bd  lea     rcx, ?gWinstaCrit@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800012c4  call    cs:__imp_EnterCriticalSection
0x1800012ca  mov     r14, cs:?gSystemEventsListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY gSystemEventsListHead
0x1800012d1  cmp     r14, rsi
0x1800012d4  jz      short loc_18000131D
0x1800012d6  lea     rsi, [r14-660h]
0x1800012dd  call    cs:__imp_GetCurrentThreadId
0x1800012e3  cmp     eax, [rsi+658h]
0x1800012e9  jnz     short loc_18000130A
0x1800012eb  cmp     rbp, [rsi+650h]
0x1800012f2  jnz     short loc_18000130A
0x1800012f4  cmp     edi, [rsi+648h]
0x1800012fa  jnz     short loc_18000130A
0x1800012fc  mov     eax, [rsi+0C8h]
0x180001302  sub     eax, 3
0x180001305  cmp     eax, 1
0x180001308  ja      short loc_180001316
0x18000130a  mov     r14, [r14]
0x18000130d  lea     rsi, ?gSystemEventsListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY gSystemEventsListHead
0x180001314  jmp     short loc_1800012D1
0x180001316  mov     rbx, rsi
0x180001319  lock inc dword ptr [rsi+8]
0x18000131d  lea     rcx, ?gWinstaCrit@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180001324  call    cs:__imp_LeaveCriticalSection
0x18000132a  test    rbx, rbx
0x18000132d  jnz     loc_18000140B
0x180001333  xor     r9d, r9d; lpName
0x180001336  xor     r8d, r8d; bInitialState
0x180001339  xor     edx, edx; bManualReset
0x18000133b  xor     ecx, ecx; lpEventAttributes
0x18000133d  xor     r14b, r14b
0x180001340  call    cs:__imp_CreateEventW
0x180001346  mov     rsi, rax
0x180001349  test    rax, rax
0x18000134c  jz      loc_180001442
0x180001352  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180001359  mov     ecx, 670h; unsigned __int64
0x18000135e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180001363  test    rax, rax
0x180001366  jz      loc_1800013FC
0x18000136c  mov     r8, rbp; void *
0x18000136f  mov     rdx, rsi; void *
0x180001372  mov     rcx, rax; this
0x180001375  call    ??0CWaitEventCollect@@QEAA@PEAX0@Z; CWaitEventCollect::CWaitEventCollect(void *,void *)
0x18000137a  mov     rbx, rax
0x18000137d  test    rax, rax
0x180001380  jz      short loc_1800013FE
0x180001382  lock inc dword ptr [rax+8]
0x180001386  lea     rcx, ?gWinstaCrit@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000138d  call    cs:__imp_EnterCriticalSection
0x180001393  mov     rcx, cs:qword_180057430
0x18000139a  lea     rsi, ?gSystemEventsListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY gSystemEventsListHead
0x1800013a1  cmp     [rcx], rsi
0x1800013a4  jnz     loc_18000152B
0x1800013aa  lea     rax, [rbx+660h]
0x1800013b1  mov     [rax], rsi
0x1800013b4  mov     [rax+8], rcx
0x1800013b8  mov     [rcx], rax
0x1800013bb  mov     cs:qword_180057430, rax
0x1800013c2  lock inc dword ptr [rbx+8]
0x1800013c6  lea     rcx, ?gWinstaCrit@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800013cd  call    cs:__imp_LeaveCriticalSection
0x1800013d3  mov     r8d, edi; unsigned int
0x1800013d6  mov     [rbx+648h], edi
0x1800013dc  or      edx, 0FFFFFFFFh; int
0x1800013df  mov     rcx, rbx; Context
0x1800013e2  call    ?StartWait@CWaitItem@@QEAAJJK@Z; CWaitItem::StartWait(long,ulong)
0x1800013e7  test    eax, eax
0x1800013e9  jns     short loc_18000140B
0x1800013eb  mov     ecx, eax; int
0x1800013ed  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x1800013f2  mov     ecx, eax; dwErrCode
0x1800013f4  call    cs:__imp_SetLastError
0x1800013fa  jmp     short loc_180001440
0x1800013fc  xor     ebx, ebx
0x1800013fe  mov     ecx, 8; dwErrCode
0x180001403  call    cs:__imp_SetLastError
0x180001409  jmp     short loc_180001442
0x18000140b  mov     rdi, rbx
0x18000140e  mov     rcx, [rdi+640h]; hHandle
0x180001415  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180001418  call    cs:__imp_WaitForSingleObject
0x18000141e  mov     eax, [rbx+638h]
0x180001424  test    eax, eax
0x180001426  jnz     short loc_180001431
0x180001428  cmp     dword ptr [rbx+0C8h], 4
0x18000142f  jnz     short loc_18000140E
0x180001431  xor     eax, eax
0x180001433  xchg    eax, [rbx+638h]
0x180001439  mov     [r12], eax
0x18000143d  mov     r14b, 1
0x180001440  xor     esi, esi
0x180001442  test    r15d, r15d
0x180001445  jns     short loc_18000148E
0x180001447  lea     rcx, ?gWinstaCrit@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000144e  call    cs:__imp_EnterCriticalSection
0x180001454  mov     rdi, cs:?gSystemEventsListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY gSystemEventsListHead
0x18000145b  lea     r15, ?gSystemEventsListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY gSystemEventsListHead
0x180001462  jmp     short loc_18000147C
0x180001464  lea     rcx, [rdi-660h]; this
0x18000146b  mov     rdi, [rdi]
0x18000146e  cmp     rbp, [rcx+650h]
0x180001475  jnz     short loc_18000147C
0x180001477  call    ?StopWait@CWaitItem@@QEAAJXZ; CWaitItem::StopWait(void)
0x18000147c  cmp     rdi, r15
0x18000147f  jnz     short loc_180001464
0x180001481  lea     rcx, ?gWinstaCrit@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180001488  call    cs:__imp_LeaveCriticalSection
0x18000148e  test    rsi, rsi
0x180001491  jz      short loc_18000149C
0x180001493  mov     rcx, rsi; hObject
0x180001496  call    cs:__imp_CloseHandle
0x18000149c  test    rbx, rbx
0x18000149f  jz      short loc_18000151C
0x1800014a1  mov     eax, [rbx+0C8h]
0x1800014a7  sub     eax, 3
0x1800014aa  cmp     eax, 1
0x1800014ad  ja      short loc_180001514
0x1800014af  lea     rcx, ?gWinstaCrit@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800014b6  xor     esi, esi
0x1800014b8  call    cs:__imp_EnterCriticalSection
0x1800014be  lea     rdi, [rbx+660h]
0x1800014c5  mov     rax, [rdi]
0x1800014c8  cmp     rax, rdi
0x1800014cb  jz      short loc_1800014F4
0x1800014cd  cmp     [rax+8], rdi
0x1800014d1  jnz     short loc_18000152B
0x1800014d3  mov     rcx, [rdi+8]
0x1800014d7  cmp     [rcx], rdi
0x1800014da  jnz     short loc_18000152B
0x1800014dc  mov     [rcx], rax
0x1800014df  mov     [rax+8], rcx
0x1800014e3  mov     rcx, rbx; this
0x1800014e6  call    ?Release@CWaitItem@@QEAAJXZ; CWaitItem::Release(void)
0x1800014eb  mov     [rdi+8], rdi
0x1800014ef  mov     esi, 1
0x1800014f4  lea     rcx, ?gWinstaCrit@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800014fb  mov     [rdi+8], rdi
0x1800014ff  mov     [rdi], rdi
0x180001502  call    cs:__imp_LeaveCriticalSection
0x180001508  test    esi, esi
0x18000150a  jz      short loc_180001514
0x18000150c  mov     rcx, rbx; this
0x18000150f  call    ?StopWait@CWaitItem@@QEAAJXZ; CWaitItem::StopWait(void)
0x180001514  mov     rcx, rbx; this
0x180001517  call    ?Release@CWaitItem@@QEAAJXZ; CWaitItem::Release(void)
0x18000151c  lea     rcx, [rsp+68h+var_48]; this
0x180001521  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180001526  mov     al, r14b
0x180001529  jmp     short loc_18000154E
0x18000152b  mov     ecx, 3
0x180001530  int     29h; Win8: RtlFailFast(ecx)
0x180001532  mov     r8, r12; unsigned int *
0x180001535  mov     edx, r15d; unsigned int
0x180001538  mov     rcx, rbp; this
0x18000153b  call    ?Legacy_WinStationWaitSystemEvent@@YAEPEAXKPEAK@Z; Legacy_WinStationWaitSystemEvent(void *,ulong,ulong *)
0x180001540  lea     rcx, [rsp+68h+var_48]; this
0x180001545  mov     bl, al
0x180001547  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18000154c  mov     al, bl
0x18000154e  add     rsp, 30h
0x180001552  pop     r15
0x180001554  pop     r14
0x180001556  pop     r12
0x180001558  pop     rdi
0x180001559  pop     rsi
0x18000155a  pop     rbp
0x18000155b  pop     rbx
0x18000155c  retn
```
