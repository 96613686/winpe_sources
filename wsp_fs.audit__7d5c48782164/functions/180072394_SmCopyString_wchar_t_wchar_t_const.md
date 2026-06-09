# SmCopyString(wchar_t * *,wchar_t const *)

- ea: `0x180072394`
- end: `0x1800724e9`
- name: `?SmCopyString@@YAJPEAPEA_WPEB_W@Z`
- size: `341`
- prototype: `int(wchar_t **, const wchar_t *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180071e70`
- `0x180071f40`

## callees

- `0x180004fac`
- `0x180009f90`
- `0x1800707b8`
- `0x180070808`
- `0x180070860`
- `0x1800708d0`
- `0x180070b74`
- `0x180072394`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800723b9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800723b9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800723df`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18007246b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800723df`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18007246b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18007249d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18007249d`

## pseudocode

```c
__int64 __fastcall SmCopyString(wchar_t **a1, const wchar_t *a2)
{
  BOOL v4; // eax
  __int64 v5; // rcx
  __int64 v6; // rdx
  unsigned int v7; // ebx
  __int64 v8; // rbx
  unsigned __int64 v9; // rbx
  wchar_t *v10; // rax
  int v11; // eax
  __int64 v12; // rcx
  BOOL v13; // eax
  LARGE_INTEGER v14; // rcx
  LARGE_INTEGER v15; // rax
  LARGE_INTEGER PerformanceCount; // [rsp+20h] [rbp-28h] BYREF
  LARGE_INTEGER v18; // [rsp+28h] [rbp-20h] BYREF
  LARGE_INTEGER Frequency; // [rsp+30h] [rbp-18h] BYREF
  HANDLE Timer; // [rsp+38h] [rbp-10h]

  PerformanceCount.QuadPart = 0;
  v18.QuadPart = 0;
  if ( !QueryPerformanceFrequency(&Frequency) || !Frequency.QuadPart )
    Frequency.QuadPart = 1;
  Timer = 0;
  v4 = QueryPerformanceCounter(&PerformanceCount);
  PerformanceCount.QuadPart &= -(__int64)v4;
  TraceEnterFunction<5,0,0>();
  if ( !a1 )
  {
    v6 = 77;
LABEL_6:
    v7 = -2147024809;
    TraceBadArgumentError<2,0,0>(v5, v6);
    goto LABEL_13;
  }
  if ( !a2 )
  {
    v6 = 78;
    goto LABEL_6;
  }
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  v9 = v8 + 1;
  v10 = (wchar_t *)operator new[](saturated_mul(v9, 2u));
  *a1 = v10;
  *v10 = 0;
  v11 = StringCchCopyW(v10, v9, a2);
  v7 = v11;
  if ( v11 < 0 )
    TraceHRError<2,0,0>(v12, 83, (unsigned int)v11);
LABEL_13:
  v13 = QueryPerformanceCounter(&v18);
  v14 = PerformanceCount;
  if ( !v13 || (v15 = v18, v18.QuadPart < (unsigned __int64)PerformanceCount.QuadPart) )
  {
    v15 = PerformanceCount;
    v18 = PerformanceCount;
  }
  if ( Timer )
  {
    DeleteTimerQueueTimer(0, Timer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    v15 = v18;
    v14 = PerformanceCount;
    Timer = 0;
  }
  ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))TraceExitFunction<5,0,0>)(
    (LARGE_INTEGER)v14.QuadPart,
    (unsigned __int64)(1000 * (v15.QuadPart - v14.QuadPart)) % Frequency.QuadPart,
    (unsigned __int64)(1000 * (v15.QuadPart - v14.QuadPart)) / Frequency.QuadPart,
    v7);
  CSmTimer::~CSmTimer((CSmTimer *)&PerformanceCount);
  return v7;
}

```

## disassembly

```asm
0x180072394  push    rbp
0x180072396  push    rbx
0x180072397  push    rsi
0x180072398  push    rdi
0x180072399  push    r14
0x18007239b  push    r15
0x18007239d  mov     rbp, rsp
0x1800723a0  sub     rsp, 48h
0x1800723a4  mov     rsi, rcx
0x1800723a7  xor     r14d, r14d
0x1800723aa  lea     rcx, [rbp+Frequency]; lpFrequency
0x1800723ae  mov     qword ptr [rbp+PerformanceCount], r14
0x1800723b2  mov     qword ptr [rbp+var_20], r14
0x1800723b6  mov     rdi, rdx
0x1800723b9  call    cs:__imp_QueryPerformanceFrequency
0x1800723c0  nop     dword ptr [rax+rax+00h]
0x1800723c5  test    eax, eax
0x1800723c7  jz      short loc_1800723CF
0x1800723c9  cmp     qword ptr [rbp+Frequency], r14
0x1800723cd  jnz     short loc_1800723D7
0x1800723cf  mov     qword ptr [rbp+Frequency], 1
0x1800723d7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800723db  mov     [rbp+Timer], r14
0x1800723df  call    cs:__imp_QueryPerformanceCounter
0x1800723e6  nop     dword ptr [rax+rax+00h]
0x1800723eb  neg     eax
0x1800723ed  sbb     rcx, rcx
0x1800723f0  and     qword ptr [rbp+PerformanceCount], rcx
0x1800723f4  call    ??$TraceEnterFunction@$04$0A@$0A@@@YAXPEB_WI@Z; TraceEnterFunction<5,0,0>(wchar_t const *,uint)
0x1800723f9  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800723fd  test    rsi, rsi
0x180072400  jnz     short loc_180072411
0x180072402  lea     edx, [rsi+4Dh]
0x180072405  mov     ebx, 80070057h
0x18007240a  call    ??$TraceBadArgumentError@$01$0A@$0A@@@YAXPEB_WI@Z; TraceBadArgumentError<2,0,0>(wchar_t const *,uint)
0x18007240f  jmp     short loc_180072467
0x180072411  test    rdi, rdi
0x180072414  jnz     short loc_18007241B
0x180072416  lea     edx, [rdi+4Eh]
0x180072419  jmp     short loc_180072405
0x18007241b  mov     rbx, r15
0x18007241e  inc     rbx
0x180072421  cmp     [rdi+rbx*2], r14w
0x180072426  jnz     short loc_18007241E
0x180072428  inc     rbx
0x18007242b  mov     eax, 2
0x180072430  mul     rbx
0x180072433  cmovb   rax, r15
0x180072437  mov     rcx, rax; unsigned __int64
0x18007243a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18007243f  mov     r8, rdi; wchar_t *
0x180072442  mov     [rsi], rax
0x180072445  mov     rdx, rbx; unsigned __int64
0x180072448  mov     rcx, rax; wchar_t *
0x18007244b  mov     [rax], r14w
0x18007244f  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180072454  mov     ebx, eax
0x180072456  test    eax, eax
0x180072458  jns     short loc_180072467
0x18007245a  mov     r8d, eax
0x18007245d  mov     edx, 53h ; 'S'
0x180072462  call    ??$TraceHRError@$01$0A@$0A@@@YAXPEB_WII@Z; TraceHRError<2,0,0>(wchar_t const *,uint,uint)
0x180072467  lea     rcx, [rbp+var_20]; lpPerformanceCount
0x18007246b  call    cs:__imp_QueryPerformanceCounter
0x180072472  nop     dword ptr [rax+rax+00h]
0x180072477  mov     rcx, qword ptr [rbp+PerformanceCount]
0x18007247b  test    eax, eax
0x18007247d  jz      short loc_180072488
0x18007247f  mov     rax, qword ptr [rbp+var_20]
0x180072483  cmp     rax, rcx
0x180072486  jnb     short loc_18007248F
0x180072488  mov     rax, rcx
0x18007248b  mov     qword ptr [rbp+var_20], rcx
0x18007248f  mov     rdx, [rbp+Timer]; Timer
0x180072493  test    rdx, rdx
0x180072496  jz      short loc_1800724B5
0x180072498  mov     r8, r15; CompletionEvent
0x18007249b  xor     ecx, ecx; TimerQueue
0x18007249d  call    cs:__imp_DeleteTimerQueueTimer
0x1800724a4  nop     dword ptr [rax+rax+00h]
0x1800724a9  mov     rax, qword ptr [rbp+var_20]
0x1800724ad  mov     rcx, qword ptr [rbp+PerformanceCount]
0x1800724b1  mov     [rbp+Timer], r14
0x1800724b5  sub     rax, rcx
0x1800724b8  xor     edx, edx
0x1800724ba  imul    rax, 3E8h
0x1800724c1  mov     r9d, ebx
0x1800724c4  div     qword ptr [rbp+Frequency]
0x1800724c8  mov     r8, rax
0x1800724cb  call    ??$TraceExitFunction@$04$0A@$0A@@@YAXPEB_WI_KJ@Z; TraceExitFunction<5,0,0>(wchar_t const *,uint,unsigned __int64,long)
0x1800724d0  lea     rcx, [rbp+PerformanceCount]; this
0x1800724d4  call    ??1CSmTimer@@QEAA@XZ; CSmTimer::~CSmTimer(void)
0x1800724d9  mov     eax, ebx
0x1800724db  add     rsp, 48h
0x1800724df  pop     r15
0x1800724e1  pop     r14
0x1800724e3  pop     rdi
0x1800724e4  pop     rsi
0x1800724e5  pop     rbx
0x1800724e6  pop     rbp
0x1800724e7  retn
```
