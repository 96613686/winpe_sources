# CSusDatastore::LockStoreSection(tagDSStoreSections,CSusEseSession *,ulong,wchar_t const * const)

- ea: `0x180179490`
- end: `0x180179a1c`
- name: `?LockStoreSection@CSusDatastore@@AEAAJW4tagDSStoreSections@@PEAVCSusEseSession@@KQEB_W@Z`
- size: `1420`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180190420`

## callees

- `0x1801119a4`
- `0x18012b618`
- `0x180134ed8`
- `0x180178d60`
- `0x180179490`
- `0x180238960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18017961f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18017961f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801796ba`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801796ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18017955c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180179812`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18017955c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180179812`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801797d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801799ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801797d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801799ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801796cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801798cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801796cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801798cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801795a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180179830`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801795a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180179830`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1801797f3`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1801797f3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSusDatastore::LockStoreSection(__int64 a1, signed int a2, __int64 a3, DWORD a4, wchar_t *a5)
{
  signed int v5; // eax
  struct _RTL_CRITICAL_SECTION *v7; // r15
  int v8; // ebp
  int v9; // ebx
  __int64 v10; // r13
  __int64 v11; // rsi
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rax
  void *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rax
  HANDLE EventW; // rax
  signed int LastError; // eax
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rdx
  int v23; // r10d
  __int64 v24; // rsi
  DWORD v25; // eax
  signed int v26; // eax
  __int64 v27; // r13
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v31; // [rsp+30h] [rbp-A8h]
  __int64 v32; // [rsp+40h] [rbp-98h]
  DWORD dwMilliseconds; // [rsp+54h] [rbp-84h]
  __int64 v35; // [rsp+58h] [rbp-80h]
  __int64 v36; // [rsp+60h] [rbp-78h]
  __int64 v37; // [rsp+78h] [rbp-60h]
  __int128 Handles; // [rsp+88h] [rbp-50h] BYREF

  dwMilliseconds = a4;
  v35 = a3;
  v5 = a2;
  v7 = (struct _RTL_CRITICAL_SECTION *)(a1 + 24);
  v8 = 0;
  v9 = 0;
  Handles = 0;
  if ( !a3 || !a5 || !*a5 || (unsigned int)a2 > 8 )
  {
    v9 = -2147024809;
    WUTrace(0, 0, 0x2000, 1, 0, L"Invalid arg");
    goto LABEL_57;
  }
  if ( *(int *)(a1 + 848) < 4 )
  {
    v9 = -2145124348;
LABEL_7:
    WUTrace(0, 0, 0x2000, 1, 0, L"DS: 0x%08x: Error occurred", v9);
    goto LABEL_57;
  }
  if ( a1 != -24 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
    v8 = 1;
    v5 = a2;
    a3 = v35;
    a4 = dwMilliseconds;
  }
  if ( *(_DWORD *)(a1 + 884) )
  {
    v9 = -2145091584;
    goto LABEL_7;
  }
  v10 = v5;
  v11 = (__int64)v5 << 6;
  v12 = *(_QWORD *)(v11 + a1 + 64);
  if ( v12 )
  {
    if ( v12 == a3 )
    {
      v9 = LockLocationList::Add((LockLocationList *)(v11 + a1 + 80), a5);
      if ( v9 >= 0 )
      {
        v17 = DSStoreSectionToString((unsigned int)a2, v16);
        WUTrace(
          0,
          0,
          0x2000,
          5,
          0,
          L"Section %ws recursively locked by session %p at count %d (from %ws) ",
          v17,
          *(_QWORD *)(v11 + a1 + 64),
          *(_DWORD *)(v11 + a1 + 104),
          a5);
      }
    }
    else
    {
      if ( !a4 )
      {
        v9 = -2145091572;
        goto LABEL_7;
      }
      if ( !*(_QWORD *)(v11 + a1 + 72) )
      {
        EventW = CreateEventW(0, 0, 0, 0);
        *(_QWORD *)(v11 + a1 + 72) = EventW;
        if ( !EventW )
        {
          LastError = GetLastError();
          v9 = (unsigned __int16)LastError | 0x80070000;
          if ( LastError <= 0 )
            v9 = LastError;
          if ( v9 >= 0 )
            v9 = -2147418113;
          goto LABEL_7;
        }
        v5 = a2;
      }
      v20 = *(_QWORD *)(v11 + a1 + 96);
      *(_QWORD *)(v11 + a1 + 112) = v20;
      v21 = 0;
      if ( *(_DWORD *)(v11 + a1 + 104) )
        v21 = *(_QWORD *)(v20 + 16);
      v36 = DSStoreSectionToString((unsigned int)v5, v21);
      WUTrace(
        0,
        0,
        0x2000,
        4,
        v23,
        L"Session %p is waiting for section %ls (last locked from %ws)",
        *(_QWORD *)(v11 + a1 + 64),
        v36,
        v22);
      *(_QWORD *)&Handles = *(_QWORD *)(v11 + a1 + 72);
      *((_QWORD *)&Handles + 1) = *(_QWORD *)(a1 + 856);
      v37 = (__int64)a2 << 6;
      ++*(_DWORD *)(v37 + a1 + 120);
      if ( *(_QWORD *)(((a2 + 1LL) << 6) + a1) != v35 )
      {
        v24 = (__int64)a2 << 6;
        while ( 1 )
        {
          if ( v8 && v7 )
          {
            LeaveCriticalSection(v7);
            --v8;
          }
          v25 = WaitForMultipleObjects(2u, (const HANDLE *)&Handles, 0, dwMilliseconds);
          --*(_DWORD *)(v37 + a1 + 120);
          if ( v25 )
            break;
          if ( v7 )
          {
            EnterCriticalSection(v7);
            ++v8;
          }
          if ( !*(_QWORD *)(v24 + a1 + 64) )
          {
            *(_QWORD *)(v24 + a1 + 64) = v35;
            *(_DWORD *)(v24 + a1 + 124) = GetCurrentThreadId();
            v9 = LockLocationList::Add((LockLocationList *)(a1 + ((__int64)a2 << 6) + 80), a5);
            if ( v9 < 0 )
              goto LABEL_57;
            WUTrace(
              0,
              0,
              0x2000,
              5,
              0,
              L"Section %ls locked by session %p (from %ws)",
              v36,
              *(_QWORD *)(v24 + a1 + 64),
              a5);
          }
          if ( *(_QWORD *)(v24 + a1 + 64) == v35 )
            goto LABEL_57;
        }
        if ( v25 == 1 )
        {
          v9 = -2145091584;
        }
        else if ( v25 == 258 )
        {
          v9 = -2145091572;
        }
        else
        {
          v26 = GetLastError();
          v9 = (unsigned __int16)v26 | 0x80070000;
          if ( v26 <= 0 )
            v9 = v26;
          if ( v9 >= 0 )
            v9 = -2147418113;
        }
        v27 = v10 << 6;
        if ( *(_DWORD *)(a1 + v27 + 104) )
        {
          v29 = *(_QWORD *)(a1 + v27 + 96);
          *(_QWORD *)(a1 + v27 + 112) = v29;
          v28 = *(_QWORD *)(v29 + 16);
        }
        else
        {
          v28 = 0;
        }
        LODWORD(v31) = v9;
        WUTrace(
          0,
          0,
          0x2000,
          1,
          0,
          L"DS: 0x%08x: Error occurred while session %p was waiting for section %ls (last locked from %ws)",
          v31,
          *(_QWORD *)(((a2 + 1LL) << 6) + a1),
          v36,
          v28);
        LODWORD(v32) = v9;
        WUTrace(
          "CSusDatastore::LockStoreSection",
          756,
          32,
          3,
          0,
          L"TelemetryAssert (%ws): %ws (0x%x, 0x%x)",
          L"false",
          L"DS LockStoreSection failed",
          v32,
          0);
        WUTelemetryAssertTriggered(v9, 0);
      }
    }
  }
  else
  {
    *(_QWORD *)(v11 + a1 + 64) = a3;
    *(_DWORD *)(v11 + a1 + 124) = GetCurrentThreadId();
    v9 = LockLocationList::Add((LockLocationList *)(v11 + a1 + 80), a5);
    if ( v9 >= 0 )
    {
      v14 = DSStoreSectionToString((unsigned int)a2, v13);
      WUTrace(0, 0, 0x2000, 5, 0, L"Section %ws locked by session %p (from %ws)", v14, *(_QWORD *)(v11 + a1 + 64), a5);
      v15 = *(void **)(v11 + a1 + 72);
      if ( v15 )
        ResetEvent(v15);
    }
  }
LABEL_57:
  if ( v7 && v8 )
  {
    do
    {
      LeaveCriticalSection(v7);
      --v8;
    }
    while ( v8 );
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180179490  mov     r11, rsp
0x180179493  push    rbx
0x180179494  push    rbp
0x180179495  push    rsi
0x180179496  push    rdi
0x180179497  push    r12
0x180179499  push    r13
0x18017949b  push    r15
0x18017949d  sub     rsp, 0A0h
0x1801794a4  mov     rax, cs:__security_cookie
0x1801794ab  xor     rax, rsp
0x1801794ae  mov     [rsp+0D8h+var_40], rax
0x1801794b6  mov     [rsp+0D8h+dwMilliseconds], r9d
0x1801794bb  mov     [rsp+0D8h+var_80], r8
0x1801794c0  mov     eax, edx
0x1801794c2  mov     [rsp+0D8h+var_88], edx
0x1801794c6  mov     rdi, rcx
0x1801794c9  mov     r12, [rsp+0D8h+arg_20]
0x1801794d1  xorps   xmm0, xmm0
0x1801794d4  movups  [rsp+0D8h+var_70], xmm0
0x1801794d9  lea     r15, [rcx+18h]
0x1801794dd  mov     [r11-70h], r15
0x1801794e1  xor     r10d, r10d
0x1801794e4  mov     ebp, r10d
0x1801794e7  mov     [r11-68h], r10d
0x1801794eb  mov     ebx, r10d
0x1801794ee  movups  xmmword ptr [r11-50h], xmm0
0x1801794f3  test    r8, r8
0x1801794f6  jz      loc_1801799B7
0x1801794fc  test    r12, r12
0x1801794ff  jz      loc_1801799B7
0x180179505  cmp     [r12], r10w
0x18017950a  jz      loc_1801799B7
0x180179510  cmp     eax, 8
0x180179513  ja      loc_1801799B7
0x180179519  cmp     dword ptr [rcx+350h], 4
0x180179520  jge     short loc_180179554
0x180179522  mov     ebx, 80240004h
0x180179527  mov     dword ptr [rsp+0D8h+var_A8], ebx
0x18017952b  lea     rax, aDs0x08xErrorOc; "DS: 0x%08x: Error occurred"
0x180179532  mov     [rsp+0D8h+var_B0], rax
0x180179537  mov     [rsp+0D8h+var_B8], r10
0x18017953c  xor     edx, edx
0x18017953e  xor     ecx, ecx
0x180179540  lea     r9d, [rdx+1]
0x180179544  mov     r8d, 2000h
0x18017954a  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18017954f  jmp     loc_1801799E1
0x180179554  test    r15, r15
0x180179557  jz      short loc_18017957C
0x180179559  mov     rcx, r15; lpCriticalSection
0x18017955c  call    cs:__imp_EnterCriticalSection
0x180179562  mov     ebp, 1
0x180179567  mov     dword ptr [rsp+0D8h+var_70+8], ebp
0x18017956b  mov     eax, [rsp+0D8h+var_88]
0x18017956f  mov     r8, [rsp+0D8h+var_80]
0x180179574  mov     r9d, [rsp+0D8h+dwMilliseconds]
0x180179579  xor     r10d, r10d
0x18017957c  cmp     [rdi+374h], r10d
0x180179583  jz      short loc_18017958C
0x180179585  mov     ebx, 80248000h
0x18017958a  jmp     short loc_180179527
0x18017958c  movsxd  r13, eax
0x18017958f  mov     rsi, r13
0x180179592  shl     rsi, 6
0x180179596  mov     rcx, [rsi+rdi+40h]
0x18017959b  test    rcx, rcx
0x18017959e  jnz     loc_18017962A
0x1801795a4  mov     [rsi+rdi+40h], r8
0x1801795a9  call    cs:__imp_GetCurrentThreadId
0x1801795af  mov     [rsi+rdi+7Ch], eax
0x1801795b3  lea     rcx, [rdi+50h]
0x1801795b7  add     rcx, rsi; this
0x1801795ba  mov     rdx, r12; wchar_t *
0x1801795bd  call    ?Add@LockLocationList@@QEAAJPEB_W@Z; LockLocationList::Add(wchar_t const *)
0x1801795c2  mov     ebx, eax
0x1801795c4  test    eax, eax
0x1801795c6  js      loc_1801799E1
0x1801795cc  mov     ecx, [rsp+0D8h+var_88]
0x1801795d0  call    ?DSStoreSectionToString@@YAPEB_WW4tagDSStoreSections@@@Z; DSStoreSectionToString(tagDSStoreSections)
0x1801795d5  mov     [rsp+0D8h+var_98], r12
0x1801795da  mov     rcx, [rsi+rdi+40h]
0x1801795df  mov     [rsp+0D8h+var_A0], rcx
0x1801795e4  mov     [rsp+0D8h+var_A8], rax
0x1801795e9  lea     rax, aSectionWsLocke; "Section %ws locked by session %p (from "...
0x1801795f0  mov     [rsp+0D8h+var_B0], rax
0x1801795f5  mov     [rsp+0D8h+var_B8], 0
0x1801795fe  xor     edx, edx
0x180179600  xor     ecx, ecx
0x180179602  lea     r9d, [rdx+5]
0x180179606  mov     r8d, 2000h
0x18017960c  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180179611  mov     rcx, [rsi+rdi+48h]; hEvent
0x180179616  test    rcx, rcx
0x180179619  jz      loc_1801799E1
0x18017961f  call    cs:__imp_ResetEvent
0x180179625  jmp     loc_1801799E1
0x18017962a  cmp     rcx, r8
0x18017962d  jnz     short loc_18017969A
0x18017962f  lea     rcx, [rdi+50h]
0x180179633  add     rcx, rsi; this
0x180179636  mov     rdx, r12; wchar_t *
0x180179639  call    ?Add@LockLocationList@@QEAAJPEB_W@Z; LockLocationList::Add(wchar_t const *)
0x18017963e  mov     ebx, eax
0x180179640  test    eax, eax
0x180179642  js      loc_1801799E1
0x180179648  mov     ecx, [rsp+0D8h+var_88]
0x18017964c  call    ?DSStoreSectionToString@@YAPEB_WW4tagDSStoreSections@@@Z; DSStoreSectionToString(tagDSStoreSections)
0x180179651  mov     [rsp+0D8h+var_90], r12
0x180179656  mov     ecx, [rsi+rdi+68h]
0x18017965a  mov     dword ptr [rsp+0D8h+var_98], ecx
0x18017965e  mov     rcx, [rsi+rdi+40h]
0x180179663  mov     [rsp+0D8h+var_A0], rcx
0x180179668  mov     [rsp+0D8h+var_A8], rax
0x18017966d  lea     rax, aSectionWsRecur; "Section %ws recursively locked by sessi"...
0x180179674  mov     [rsp+0D8h+var_B0], rax
0x180179679  mov     [rsp+0D8h+var_B8], 0
0x180179682  xor     edx, edx
0x180179684  xor     ecx, ecx
0x180179686  lea     r9d, [rdx+5]
0x18017968a  mov     r8d, 2000h
0x180179690  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180179695  jmp     loc_1801799E1
0x18017969a  test    r9d, r9d
0x18017969d  jnz     short loc_1801796A9
0x18017969f  mov     ebx, 8024800Ch
0x1801796a4  jmp     loc_180179527
0x1801796a9  cmp     [rsi+rdi+48h], r10
0x1801796ae  jnz     short loc_18017970D
0x1801796b0  xor     r9d, r9d; lpName
0x1801796b3  xor     r8d, r8d; bInitialState
0x1801796b6  xor     edx, edx; bManualReset
0x1801796b8  xor     ecx, ecx; lpEventAttributes
0x1801796ba  call    cs:__imp_CreateEventW
0x1801796c0  mov     [rsi+rdi+48h], rax
0x1801796c5  xor     r10d, r10d
0x1801796c8  test    rax, rax
0x1801796cb  jnz     short loc_180179709
0x1801796cd  call    cs:__imp_GetLastError
0x1801796d3  movzx   ebx, ax
0x1801796d6  or      ebx, 80070000h
0x1801796dc  test    eax, eax
0x1801796de  cmovle  ebx, eax
0x1801796e1  mov     eax, 8000FFFFh
0x1801796e6  test    ebx, ebx
0x1801796e8  cmovns  ebx, eax
0x1801796eb  mov     dword ptr [rsp+0D8h+var_A8], ebx
0x1801796ef  lea     rax, aDs0x08xErrorOc; "DS: 0x%08x: Error occurred"
0x1801796f6  mov     [rsp+0D8h+var_B0], rax
0x1801796fb  mov     [rsp+0D8h+var_B8], 0
0x180179704  jmp     loc_18017953C
0x180179709  mov     eax, [rsp+0D8h+var_88]
0x18017970d  mov     rcx, [rsi+rdi+60h]
0x180179712  mov     [rsi+rdi+70h], rcx
0x180179717  cmp     [rsi+rdi+68h], r10d
0x18017971c  mov     rdx, r10
0x18017971f  jz      short loc_180179725
0x180179721  mov     rdx, [rcx+10h]
0x180179725  mov     ecx, eax
0x180179727  call    ?DSStoreSectionToString@@YAPEB_WW4tagDSStoreSections@@@Z; DSStoreSectionToString(tagDSStoreSections)
0x18017972c  mov     [rsp+0D8h+var_78], rax
0x180179731  mov     [rsp+0D8h+var_98], rdx
0x180179736  mov     [rsp+0D8h+var_A0], rax
0x18017973b  mov     rcx, [rsi+rdi+40h]
0x180179740  mov     [rsp+0D8h+var_A8], rcx
0x180179745  lea     rax, aSessionPIsWait; "Session %p is waiting for section %ls ("...
0x18017974c  mov     [rsp+0D8h+var_B0], rax
0x180179751  mov     [rsp+0D8h+var_B8], r10
0x180179756  xor     edx, edx
0x180179758  xor     ecx, ecx
0x18017975a  lea     r9d, [rdx+4]
0x18017975e  mov     r8d, 2000h
0x180179764  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180179769  mov     rax, [rsi+rdi+48h]
0x18017976e  mov     [rsp+0D8h+Handles], rax
0x180179776  mov     rax, [rdi+358h]
0x18017977d  mov     [rsp+0D8h+var_48], rax
0x180179785  movsxd  rcx, [rsp+0D8h+var_88]
0x18017978a  mov     rax, rcx
0x18017978d  shl     rax, 6
0x180179791  mov     [rsp+0D8h+var_60], rax
0x180179796  inc     dword ptr [rax+rdi+78h]
0x18017979a  lea     rax, [rcx+1]
0x18017979e  shl     rax, 6
0x1801797a2  mov     rdx, [rsp+0D8h+var_80]
0x1801797a7  cmp     [rax+rdi], rdx
0x1801797ab  jz      loc_1801799E1
0x1801797b1  mov     rsi, rcx
0x1801797b4  mov     rax, rcx
0x1801797b7  shl     rax, 6
0x1801797bb  mov     [rsp+0D8h+var_58], rax
0x1801797c3  shl     rsi, 6
0x1801797c7  test    ebp, ebp
0x1801797c9  jz      short loc_1801797DF
0x1801797cb  test    r15, r15
0x1801797ce  jz      short loc_1801797DF
0x1801797d0  mov     rcx, r15; lpCriticalSection
0x1801797d3  call    cs:__imp_LeaveCriticalSection
0x1801797d9  dec     ebp
0x1801797db  mov     dword ptr [rsp+0D8h+var_70+8], ebp
0x1801797df  mov     r9d, [rsp+0D8h+dwMilliseconds]; dwMilliseconds
0x1801797e4  xor     r8d, r8d; bWaitAll
0x1801797e7  lea     rdx, [rsp+0D8h+Handles]; lpHandles
0x1801797ef  lea     ecx, [r8+2]; nCount
0x1801797f3  call    cs:__imp_WaitForMultipleObjects
0x1801797f9  mov     rcx, [rsp+0D8h+var_60]
0x1801797fe  dec     dword ptr [rcx+rdi+78h]
0x180179802  test    eax, eax
0x180179804  jnz     loc_1801798B1
0x18017980a  test    r15, r15
0x18017980d  jz      short loc_18017981E
0x18017980f  mov     rcx, r15; lpCriticalSection
0x180179812  call    cs:__imp_EnterCriticalSection
0x180179818  inc     ebp
0x18017981a  mov     dword ptr [rsp+0D8h+var_70+8], ebp
0x18017981e  cmp     qword ptr [rsi+rdi+40h], 0
0x180179824  jnz     short loc_18017989C
0x180179826  mov     rax, [rsp+0D8h+var_80]
0x18017982b  mov     [rsi+rdi+40h], rax
0x180179830  call    cs:__imp_GetCurrentThreadId
0x180179836  mov     [rsi+rdi+7Ch], eax
0x18017983a  mov     rcx, [rsp+0D8h+var_58]
0x180179842  add     rcx, 50h ; 'P'
0x180179846  add     rcx, rdi; this
0x180179849  mov     rdx, r12; wchar_t *
0x18017984c  call    ?Add@LockLocationList@@QEAAJPEB_W@Z; LockLocationList::Add(wchar_t const *)
0x180179851  mov     ebx, eax
0x180179853  test    eax, eax
0x180179855  js      loc_1801799E1
0x18017985b  mov     [rsp+0D8h+var_98], r12
0x180179860  mov     rax, [rsi+rdi+40h]
0x180179865  mov     [rsp+0D8h+var_A0], rax
0x18017986a  mov     rax, [rsp+0D8h+var_78]
0x18017986f  mov     [rsp+0D8h+var_A8], rax
0x180179874  lea     rax, aSectionLsLocke; "Section %ls locked by session %p (from "...
0x18017987b  mov     [rsp+0D8h+var_B0], rax
0x180179880  mov     [rsp+0D8h+var_B8], 0
0x180179889  xor     edx, edx
0x18017988b  xor     ecx, ecx
0x18017988d  lea     r9d, [rdx+5]
0x180179891  mov     r8d, 2000h
0x180179897  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18017989c  mov     rax, [rsp+0D8h+var_80]
0x1801798a1  cmp     [rsi+rdi+40h], rax
0x1801798a6  jnz     loc_1801797C7
0x1801798ac  jmp     loc_1801799E1
0x1801798b1  cmp     eax, 1
0x1801798b4  jnz     short loc_1801798BD
0x1801798b6  mov     ebx, 80248000h
0x1801798bb  jmp     short loc_1801798E9
0x1801798bd  cmp     eax, 102h
0x1801798c2  jnz     short loc_1801798CB
0x1801798c4  mov     ebx, 8024800Ch
0x1801798c9  jmp     short loc_1801798E9
0x1801798cb  call    cs:__imp_GetLastError
0x1801798d1  movzx   ebx, ax
0x1801798d4  or      ebx, 80070000h
0x1801798da  test    eax, eax
0x1801798dc  cmovle  ebx, eax
0x1801798df  mov     eax, 8000FFFFh
0x1801798e4  test    ebx, ebx
0x1801798e6  cmovns  ebx, eax
0x1801798e9  shl     r13, 6
0x1801798ed  cmp     dword ptr [rdi+r13+68h], 0
0x1801798f3  jnz     short loc_1801798F9
0x1801798f5  xor     ecx, ecx
0x1801798f7  jmp     short loc_180179907
0x1801798f9  mov     rax, [rdi+r13+60h]
0x1801798fe  mov     [rdi+r13+70h], rax
0x180179903  mov     rcx, [rax+10h]
0x180179907  movsxd  rax, [rsp+0D8h+var_88]
0x18017990c  inc     rax
0x18017990f  shl     rax, 6
0x180179913  mov     [rsp+0D8h+var_90], rcx
0x180179918  mov     rcx, [rsp+0D8h+var_78]
0x18017991d  mov     [rsp+0D8h+var_98], rcx
0x180179922  mov     rax, [rax+rdi]
0x180179926  mov     [rsp+0D8h+var_A0], rax
0x18017992b  mov     dword ptr [rsp+0D8h+var_A8], ebx
0x18017992f  lea     rax, aDs0x08xErrorOc_0; "DS: 0x%08x: Error occurred while sessio"...
0x180179936  mov     [rsp+0D8h+var_B0], rax
0x18017993b  mov     [rsp+0D8h+var_B8], 0
0x180179944  xor     edx, edx
0x180179946  xor     ecx, ecx
0x180179948  lea     r9d, [rdx+1]
0x18017994c  mov     r8d, 2000h
0x180179952  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180179957  mov     [rsp+0D8h+var_90], 0
0x180179960  mov     dword ptr [rsp+0D8h+var_98], ebx
0x180179964  lea     rax, aDsLockstoresec; "DS LockStoreSection failed"
0x18017996b  mov     [rsp+0D8h+var_A0], rax
0x180179970  lea     rax, aFalse; "false"
0x180179977  mov     [rsp+0D8h+var_A8], rax
0x18017997c  lea     rax, aTelemetryasser_0; "TelemetryAssert (%ws): %ws (0x%x, 0x%x)"
0x180179983  mov     [rsp+0D8h+var_B0], rax
0x180179988  mov     [rsp+0D8h+var_B8], 0
0x180179991  mov     edx, 2F4h
0x180179996  mov     r9d, 3
0x18017999c  lea     r8d, [r9+1Dh]
0x1801799a0  lea     rcx, aCsusdatastoreL; "CSusDatastore::LockStoreSection"
  ... truncated ...
```
