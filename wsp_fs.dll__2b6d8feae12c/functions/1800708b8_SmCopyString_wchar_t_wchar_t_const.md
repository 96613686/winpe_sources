# SmCopyString(wchar_t * *,wchar_t const *)

- ea: `0x1800708b8`
- end: `0x1800709f4`
- name: `?SmCopyString@@YAJPEAPEA_WPEB_W@Z`
- size: `316`
- prototype: `int(wchar_t **, const wchar_t *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x1800703f0`
- `0x1800704b0`

## callees

- `0x180004f1c`
- `0x180009c30`
- `0x18006eef8`
- `0x18006ef44`
- `0x18006ef98`
- `0x18006f004`
- `0x18006f284`
- `0x1800708b8`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800708dd`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800708dd`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800708fd`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180070983`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800708fd`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180070983`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800709af`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800709af`

## pseudocode

```c
__int64 __fastcall SmCopyString(wchar_t **a1, const wchar_t *a2)
{
  __int64 v4; // rcx
  int v5; // edx
  int v6; // r8d
  int v7; // r9d
  __int64 v8; // rcx
  int v9; // r8d
  int v10; // r9d
  int v11; // edx
  unsigned int v12; // ebx
  __int64 v13; // rbx
  unsigned __int64 v14; // rbx
  wchar_t *v15; // rax
  int v16; // eax
  __int64 v17; // rcx
  int v18; // r9d
  BOOL v19; // eax
  __int64 QuadPart; // rcx
  LARGE_INTEGER v21; // rax
  LARGE_INTEGER PerformanceCount; // [rsp+20h] [rbp-28h] BYREF
  LARGE_INTEGER v24; // [rsp+28h] [rbp-20h] BYREF
  LARGE_INTEGER Frequency; // [rsp+30h] [rbp-18h] BYREF
  HANDLE Timer; // [rsp+38h] [rbp-10h]

  PerformanceCount.QuadPart = 0;
  v24.QuadPart = 0;
  if ( !QueryPerformanceFrequency(&Frequency) || !Frequency.QuadPart )
    Frequency.QuadPart = 1;
  Timer = 0;
  v4 = -(__int64)QueryPerformanceCounter(&PerformanceCount);
  PerformanceCount.QuadPart &= v4;
  TraceEnterFunction<5,0,0>((const wchar_t *)v4, v5, v6, v7);
  if ( !a1 )
  {
    v11 = 77;
LABEL_6:
    v12 = -2147024809;
    TraceBadArgumentError<2,0,0>(v8, v11, v9, v10);
    goto LABEL_13;
  }
  if ( !a2 )
  {
    v11 = 78;
    goto LABEL_6;
  }
  v13 = -1;
  do
    ++v13;
  while ( a2[v13] );
  v14 = v13 + 1;
  v15 = (wchar_t *)operator new[](saturated_mul(v14, 2u));
  *a1 = v15;
  *v15 = 0;
  v16 = StringCchCopyW(v15, v14, a2);
  v12 = v16;
  if ( v16 < 0 )
    TraceHRError<2,0,0>(v17, 83, v16, v18);
LABEL_13:
  v19 = QueryPerformanceCounter(&v24);
  QuadPart = PerformanceCount.QuadPart;
  if ( !v19 || (v21 = v24, v24.QuadPart < (unsigned __int64)PerformanceCount.QuadPart) )
  {
    v21 = PerformanceCount;
    v24 = PerformanceCount;
  }
  if ( Timer )
  {
    DeleteTimerQueueTimer(0, Timer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    v21 = v24;
    QuadPart = PerformanceCount.QuadPart;
    Timer = 0;
  }
  TraceExitFunction<5,0,0>(
    QuadPart,
    (unsigned __int64)(1000 * (v21.QuadPart - QuadPart)) % Frequency.QuadPart,
    (unsigned __int64)(1000 * (v21.QuadPart - QuadPart)) / Frequency.QuadPart,
    v12);
  CSmTimer::~CSmTimer((CSmTimer *)&PerformanceCount);
  return v12;
}

```

## disassembly

```asm
0x1800708b8  push    rbp
0x1800708ba  push    rbx
0x1800708bb  push    rsi
0x1800708bc  push    rdi
0x1800708bd  push    r14
0x1800708bf  push    r15
0x1800708c1  mov     rbp, rsp
0x1800708c4  sub     rsp, 48h
0x1800708c8  mov     rsi, rcx
0x1800708cb  xor     r14d, r14d
0x1800708ce  lea     rcx, [rbp+Frequency]; lpFrequency
0x1800708d2  mov     qword ptr [rbp+PerformanceCount], r14
0x1800708d6  mov     qword ptr [rbp+var_20], r14
0x1800708da  mov     rdi, rdx
0x1800708dd  call    cs:__imp_QueryPerformanceFrequency
0x1800708e3  test    eax, eax
0x1800708e5  jz      short loc_1800708ED
0x1800708e7  cmp     qword ptr [rbp+Frequency], r14
0x1800708eb  jnz     short loc_1800708F5
0x1800708ed  mov     qword ptr [rbp+Frequency], 1
0x1800708f5  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800708f9  mov     [rbp+Timer], r14
0x1800708fd  call    cs:__imp_QueryPerformanceCounter
0x180070903  neg     eax
0x180070905  sbb     rcx, rcx
0x180070908  and     qword ptr [rbp+PerformanceCount], rcx
0x18007090c  call    ??$TraceEnterFunction@$04$0A@$0A@@@YAXPEB_WI@Z; TraceEnterFunction<5,0,0>(wchar_t const *,uint)
0x180070911  or      r15, 0FFFFFFFFFFFFFFFFh
0x180070915  test    rsi, rsi
0x180070918  jnz     short loc_180070929
0x18007091a  lea     edx, [rsi+4Dh]
0x18007091d  mov     ebx, 80070057h
0x180070922  call    ??$TraceBadArgumentError@$01$0A@$0A@@@YAXPEB_WI@Z; TraceBadArgumentError<2,0,0>(wchar_t const *,uint)
0x180070927  jmp     short loc_18007097F
0x180070929  test    rdi, rdi
0x18007092c  jnz     short loc_180070933
0x18007092e  lea     edx, [rdi+4Eh]
0x180070931  jmp     short loc_18007091D
0x180070933  mov     rbx, r15
0x180070936  inc     rbx
0x180070939  cmp     [rdi+rbx*2], r14w
0x18007093e  jnz     short loc_180070936
0x180070940  inc     rbx
0x180070943  mov     eax, 2
0x180070948  mul     rbx
0x18007094b  cmovb   rax, r15
0x18007094f  mov     rcx, rax; unsigned __int64
0x180070952  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180070957  mov     r8, rdi; wchar_t *
0x18007095a  mov     [rsi], rax
0x18007095d  mov     rdx, rbx; unsigned __int64
0x180070960  mov     rcx, rax; wchar_t *
0x180070963  mov     [rax], r14w
0x180070967  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18007096c  mov     ebx, eax
0x18007096e  test    eax, eax
0x180070970  jns     short loc_18007097F
0x180070972  mov     r8d, eax
0x180070975  mov     edx, 53h ; 'S'
0x18007097a  call    ??$TraceHRError@$01$0A@$0A@@@YAXPEB_WII@Z; TraceHRError<2,0,0>(wchar_t const *,uint,uint)
0x18007097f  lea     rcx, [rbp+var_20]; lpPerformanceCount
0x180070983  call    cs:__imp_QueryPerformanceCounter
0x180070989  mov     rcx, qword ptr [rbp+PerformanceCount]
0x18007098d  test    eax, eax
0x18007098f  jz      short loc_18007099A
0x180070991  mov     rax, qword ptr [rbp+var_20]
0x180070995  cmp     rax, rcx
0x180070998  jnb     short loc_1800709A1
0x18007099a  mov     rax, rcx
0x18007099d  mov     qword ptr [rbp+var_20], rcx
0x1800709a1  mov     rdx, [rbp+Timer]; Timer
0x1800709a5  test    rdx, rdx
0x1800709a8  jz      short loc_1800709C1
0x1800709aa  mov     r8, r15; CompletionEvent
0x1800709ad  xor     ecx, ecx; TimerQueue
0x1800709af  call    cs:__imp_DeleteTimerQueueTimer
0x1800709b5  mov     rax, qword ptr [rbp+var_20]
0x1800709b9  mov     rcx, qword ptr [rbp+PerformanceCount]
0x1800709bd  mov     [rbp+Timer], r14
0x1800709c1  sub     rax, rcx
0x1800709c4  xor     edx, edx
0x1800709c6  imul    rax, 3E8h
0x1800709cd  mov     r9d, ebx
0x1800709d0  div     qword ptr [rbp+Frequency]
0x1800709d4  mov     r8, rax
0x1800709d7  call    ??$TraceExitFunction@$04$0A@$0A@@@YAXPEB_WI_KJ@Z; TraceExitFunction<5,0,0>(wchar_t const *,uint,unsigned __int64,long)
0x1800709dc  lea     rcx, [rbp+PerformanceCount]; this
0x1800709e0  call    ??1CSmTimer@@QEAA@XZ; CSmTimer::~CSmTimer(void)
0x1800709e5  mov     eax, ebx
0x1800709e7  add     rsp, 48h
0x1800709eb  pop     r15
0x1800709ed  pop     r14
0x1800709ef  pop     rdi
0x1800709f0  pop     rsi
0x1800709f1  pop     rbx
0x1800709f2  pop     rbp
0x1800709f3  retn
```
