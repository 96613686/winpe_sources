# timeSetEvent

- ea: `0x1800021d0`
- end: `0x1800024f6`
- name: `timeSetEvent`
- size: `806`
- prototype: `MMRESULT __stdcall(UINT uDelay, UINT uResolution, LPTIMECALLBACK fptc, DWORD_PTR dwUser, UINT fuEvent)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800021d0`
- `0x18000b5ec`

## import_xrefs

- `ntdll!NtCreateTimer` at `0x1800024d2`
- `ntdll!NtCreateTimer` at `0x1800024d2`
- `ntdll!NtSetEvent` at `0x1800022e5`
- `ntdll!NtSetEvent` at `0x180002314`
- `ntdll!NtSetEvent` at `0x1800022e5`
- `ntdll!NtSetEvent` at `0x180002314`
- `ntdll!NtSetTimer` at `0x180002436`
- `ntdll!NtSetTimer` at `0x180002436`
- `api-ms-win-mm-time-l1-1-0!timeBeginPeriod` at `0x180002270`
- `api-ms-win-mm-time-l1-1-0!timeBeginPeriod` at `0x180002270`
- `api-ms-win-mm-time-l1-1-0!timeEndPeriod` at `0x18000232d`
- `api-ms-win-mm-time-l1-1-0!timeEndPeriod` at `0x18000232d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002285`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800022a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002285`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800022a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800022d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800022f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002305`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002321`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800024b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800022d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800022f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002305`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002321`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800024b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000225d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000225d`

## pseudocode

```c
MMRESULT __stdcall timeSetEvent(UINT uDelay, UINT uResolution, LPTIMECALLBACK fptc, DWORD_PTR dwUser, UINT fuEvent)
{
  unsigned int v5; // esi
  MMRESULT v6; // edi
  unsigned int i; // eax
  unsigned __int64 v8; // rbx
  __int64 v10; // rcx
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  unsigned __int16 v13; // cx
  __int128 v14; // xmm1
  signed __int64 v15; // rcx
  union _LARGE_INTEGER v16; // rax
  void *TimerHandle; // [rsp+40h] [rbp-58h] BYREF
  union _LARGE_INTEGER DueTime; // [rsp+48h] [rbp-50h] BYREF
  __int128 v19; // [rsp+50h] [rbp-48h]
  __int128 v20; // [rsp+60h] [rbp-38h]
  __int128 v21; // [rsp+70h] [rbp-28h]
  __int128 v22; // [rsp+80h] [rbp-18h]

  v5 = uResolution;
  if ( (fuEvent & 0xFFFFFE0E) == 0 )
  {
    if ( uDelay > 0xF4240 || uDelay < TDD_MAXRESOLUTION )
      return 0;
    if ( uResolution > TimerData )
    {
      v5 = TimerData;
    }
    else if ( uResolution < TDD_MAXRESOLUTION )
    {
      v5 = TDD_MAXRESOLUTION;
    }
    if ( v5 > uDelay )
      v5 = TimerData;
    v6 = 0;
    if ( (fuEvent & 1) != 0 )
    {
      TimerHandle = 0;
      do
        TimerHandle = (void *)MEMORY[0x7FFE0008];
      while ( MEMORY[0x7FFE000C] != MEMORY[0x7FFE0010] );
      *(_QWORD *)&v22 = TimerHandle;
    }
    else
    {
      *(_QWORD *)&v22 = 0;
    }
    *(_QWORD *)&v19 = __PAIR64__(v5, uDelay);
    *((_QWORD *)&v19 + 1) = fptc;
    *(_QWORD *)&v20 = dwUser;
    HIDWORD(v20) = fuEvent;
    DWORD2(v21) = GetCurrentThreadId();
    DWORD2(v22) = 0;
    if ( timeBeginPeriod(v5) )
      return v6;
    EnterCriticalSection(&TimerThreadCritSec);
    if ( !Handle && !(unsigned int)TimeInitThread() )
    {
      LeaveCriticalSection(&TimerThreadCritSec);
      return v6;
    }
    EnterCriticalSection(&TimerThreadCritSec);
    for ( i = 0; ; ++i )
    {
      if ( i >= 0x10 )
        goto LABEL_18;
      v8 = (unsigned __int64)i << 6;
      if ( !*(_DWORD *)((char *)&Events[3] + v8) )
        break;
    }
    v10 = *(__int64 *)((char *)&Events[4] + v8);
    v11 = v20;
    *(_OWORD *)((char *)Events + v8) = v19;
    *(_QWORD *)&v21 = v10;
    v12 = v21;
    v13 = word_18002698C;
    *(_OWORD *)((char *)&Events[2] + v8) = v11;
    v14 = v22;
    *(_OWORD *)((char *)&Events[4] + v8) = v12;
    *(_OWORD *)((char *)&Events[6] + v8) = v14;
    do
      v13 += 16;
    while ( !v13 );
    word_18002698C = v13;
    DueTime.QuadPart = 0;
    *(_DWORD *)((char *)&Events[3] + v8) = i + v13;
    *(__int64 *)((char *)&Events[6] + v8) += 10000LL * *(unsigned int *)((char *)Events + v8);
    if ( (*(_DWORD *)((_BYTE *)&Events[3] + v8 + 4) & 1) != 0 )
    {
      while ( MEMORY[0x7FFE000C] != MEMORY[0x7FFE0010] )
        ;
      v15 = (MEMORY[0x7FFE0008] | ((unsigned __int64)MEMORY[0x7FFE000C] << 32)) - *(__int64 *)((char *)&Events[6] + v8);
    }
    else
    {
      v15 = -10000LL * *(unsigned int *)((char *)Events + v8);
    }
    v16.QuadPart = 0;
    if ( v15 <= 0 )
      v16.QuadPart = v15;
    DueTime = v16;
    if ( !*(__int64 *)((char *)&Events[4] + v8) )
    {
      TimerHandle = 0;
      if ( NtCreateTimer(&TimerHandle, 0x1F0003u, 0, NotificationTimer) < 0 )
        goto LABEL_17;
      *(__int64 *)((char *)&Events[4] + v8) = (__int64)TimerHandle;
    }
    if ( NtSetTimer(
           *(HANDLE *)((char *)&Events[4] + v8),
           &DueTime,
           0,
           (PVOID)*(unsigned int *)((char *)&Events[3] + v8),
           0,
           0,
           0) >= 0 )
    {
      v6 = *(_DWORD *)((char *)&Events[3] + v8);
      LeaveCriticalSection(&TimerThreadCritSec);
      NtSetEvent(Handle, 0);
      LeaveCriticalSection(&TimerThreadCritSec);
      if ( v6 )
        return v6;
LABEL_20:
      timeEndPeriod(v5);
      return v6;
    }
LABEL_17:
    *(_DWORD *)((char *)&Events[3] + v8) = 0;
LABEL_18:
    LeaveCriticalSection(&TimerThreadCritSec);
    NtSetEvent(Handle, 0);
    LeaveCriticalSection(&TimerThreadCritSec);
    goto LABEL_20;
  }
  return 0;
}

```

## disassembly

```asm
0x1800021d0  mov     rax, rsp
0x1800021d3  push    rsi
0x1800021d4  sub     rsp, 90h
0x1800021db  mov     r10d, [rsp+98h+fuEvent]
0x1800021e3  mov     esi, edx
0x1800021e5  mov     edx, ecx
0x1800021e7  test    r10d, 0FFFFFE0Eh
0x1800021ee  jnz     loc_1800024EF
0x1800021f4  mov     [rax+8], rbx
0x1800021f8  mov     [rax+10h], rbp
0x1800021fc  mov     [rax+18h], rdi
0x180002200  cmp     ecx, 0F4240h
0x180002206  ja      loc_180002481
0x18000220c  mov     eax, cs:TDD_MAXRESOLUTION
0x180002212  cmp     ecx, eax
0x180002214  jb      loc_180002481
0x18000221a  mov     ecx, cs:TimerData
0x180002220  cmp     esi, ecx
0x180002222  ja      loc_180002497
0x180002228  cmp     esi, eax
0x18000222a  cmovb   esi, eax
0x18000222d  cmp     esi, edx
0x18000222f  cmova   esi, ecx
0x180002232  xor     edi, edi
0x180002234  test    r10b, 1
0x180002238  jnz     loc_180002449
0x18000223e  mov     qword ptr [rsp+98h+var_18], rdi
0x180002246  mov     dword ptr [rsp+98h+var_48], edx
0x18000224a  mov     dword ptr [rsp+98h+var_48+4], esi
0x18000224e  mov     qword ptr [rsp+98h+var_48+8], r8
0x180002253  mov     qword ptr [rsp+98h+var_38], r9
0x180002258  mov     dword ptr [rsp+98h+var_38+0Ch], r10d
0x18000225d  call    cs:__imp_GetCurrentThreadId
0x180002263  mov     dword ptr [rsp+98h+var_28+8], eax
0x180002267  mov     ecx, esi; uPeriod
0x180002269  mov     dword ptr [rsp+98h+var_18+8], edi
0x180002270  call    cs:__imp_timeBeginPeriod
0x180002276  test    eax, eax
0x180002278  jnz     loc_180002333
0x18000227e  lea     rcx, TimerThreadCritSec; lpCriticalSection
0x180002285  call    cs:__imp_EnterCriticalSection
0x18000228b  cmp     cs:Handle, 0
0x180002293  jz      loc_18000249E
0x180002299  lea     rcx, TimerThreadCritSec; lpCriticalSection
0x1800022a0  call    cs:__imp_EnterCriticalSection
0x1800022a6  mov     eax, edi
0x1800022a8  lea     rbp, Events
0x1800022af  nop
0x1800022b0  cmp     eax, 10h
0x1800022b3  jnb     short loc_1800022CF
0x1800022b5  mov     ebx, eax
0x1800022b7  shl     rbx, 6
0x1800022bb  mov     ecx, [rbx+rbp+18h]
0x1800022bf  test    ecx, ecx
0x1800022c1  jz      loc_180002356
0x1800022c7  inc     eax
0x1800022c9  jmp     short loc_1800022B0
0x1800022cb  mov     [rbx+rbp+18h], edi
0x1800022cf  lea     rcx, TimerThreadCritSec; lpCriticalSection
0x1800022d6  call    cs:__imp_LeaveCriticalSection
0x1800022dc  mov     rcx, cs:Handle; EventHandle
0x1800022e3  xor     edx, edx; PreviousState
0x1800022e5  call    cs:__imp_NtSetEvent
0x1800022eb  lea     rcx, TimerThreadCritSec; lpCriticalSection
0x1800022f2  call    cs:__imp_LeaveCriticalSection
0x1800022f8  jmp     short loc_18000232B
0x1800022fa  mov     edi, [rbx+rbp+18h]
0x1800022fe  lea     rcx, TimerThreadCritSec; lpCriticalSection
0x180002305  call    cs:__imp_LeaveCriticalSection
0x18000230b  mov     rcx, cs:Handle; EventHandle
0x180002312  xor     edx, edx; PreviousState
0x180002314  call    cs:__imp_NtSetEvent
0x18000231a  lea     rcx, TimerThreadCritSec; lpCriticalSection
0x180002321  call    cs:__imp_LeaveCriticalSection
0x180002327  test    edi, edi
0x180002329  jnz     short loc_180002333
0x18000232b  mov     ecx, esi; uPeriod
0x18000232d  call    cs:__imp_timeEndPeriod
0x180002333  mov     rbp, [rsp+98h+arg_8]
0x18000233b  mov     eax, edi
0x18000233d  mov     rdi, [rsp+98h+arg_10]
0x180002345  mov     rbx, [rsp+98h+arg_0]
0x18000234d  add     rsp, 90h
0x180002354  pop     rsi
0x180002355  retn
0x180002356  mov     rcx, [rbx+rbp+20h]
0x18000235b  movaps  xmm0, [rsp+98h+var_48]
0x180002360  movaps  xmm1, [rsp+98h+var_38]
0x180002365  movups  xmmword ptr [rbx+rbp], xmm0
0x180002369  mov     qword ptr [rsp+98h+var_28], rcx
0x18000236e  movaps  xmm0, [rsp+98h+var_28]
0x180002373  movzx   ecx, cs:word_18002698C
0x18000237a  movups  xmmword ptr [rbx+rbp+10h], xmm1
0x18000237f  movaps  xmm1, [rsp+98h+var_18]
0x180002387  movups  xmmword ptr [rbx+rbp+20h], xmm0
0x18000238c  movups  xmmword ptr [rbx+rbp+30h], xmm1
0x180002391  add     cx, 10h
0x180002395  jz      short loc_180002391
0x180002397  mov     cs:word_18002698C, cx
0x18000239e  movzx   ecx, cx
0x1800023a1  add     ecx, eax
0x1800023a3  mov     qword ptr [rsp+98h+DueTime], rdi
0x1800023a8  mov     [rbx+rbp+18h], ecx
0x1800023ac  mov     eax, [rbx+rbp]
0x1800023af  mov     rcx, [rbx+rbp+30h]
0x1800023b4  imul    rax, 2710h
0x1800023bb  add     rcx, rax
0x1800023be  mov     [rbx+rbp+30h], rcx
0x1800023c3  mov     eax, [rbx+rbp+1Ch]
0x1800023c7  test    al, 1
0x1800023c9  jz      loc_180002488
0x1800023cf  mov     ecx, ds:7FFE000Ch
0x1800023d6  mov     edx, ds:7FFE0008h
0x1800023dd  mov     eax, ds:7FFE0010h
0x1800023e4  cmp     ecx, eax
0x1800023e6  jnz     short loc_1800023CF
0x1800023e8  shl     rcx, 20h
0x1800023ec  mov     eax, edx
0x1800023ee  or      rcx, rax
0x1800023f1  mov     rax, [rbx+rbp+30h]
0x1800023f6  sub     rcx, rax
0x1800023f9  test    rcx, rcx
0x1800023fc  mov     rax, rdi
0x1800023ff  cmovle  rax, rcx
0x180002403  mov     qword ptr [rsp+98h+DueTime], rax
0x180002408  mov     rax, [rbx+rbp+20h]
0x18000240d  test    rax, rax
0x180002410  jz      loc_1800024BD
0x180002416  mov     r9d, [rbx+rbp+18h]; TimerContext
0x18000241b  lea     rdx, [rsp+98h+DueTime]; DueTime
0x180002420  mov     rcx, [rbx+rbp+20h]; TimerHandle
0x180002425  xor     r8d, r8d; TimerApcRoutine
0x180002428  mov     [rsp+98h+PreviousState], rdi; PreviousState
0x18000242d  mov     [rsp+98h+Period], edi; Period
0x180002431  mov     [rsp+98h+WakeTimer], 0; WakeTimer
0x180002436  call    cs:__imp_NtSetTimer
0x18000243c  test    eax, eax
0x18000243e  js      loc_1800022CB
0x180002444  jmp     loc_1800022FA
0x180002449  mov     [rsp+98h+TimerHandle], rdi
0x18000244e  mov     ecx, ds:7FFE000Ch
0x180002455  mov     eax, ds:7FFE0008h
0x18000245c  mov     dword ptr [rsp+98h+TimerHandle], eax
0x180002460  mov     eax, ds:7FFE0010h
0x180002467  mov     dword ptr [rsp+98h+TimerHandle+4], ecx
0x18000246b  cmp     ecx, eax
0x18000246d  jnz     short loc_18000244E
0x18000246f  mov     rax, [rsp+98h+TimerHandle]
0x180002474  mov     qword ptr [rsp+98h+var_18], rax
0x18000247c  jmp     loc_180002246
0x180002481  xor     edi, edi
0x180002483  jmp     loc_180002333
0x180002488  mov     eax, [rbx+rbp]
0x18000248b  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x180002492  jmp     loc_1800023F9
0x180002497  mov     esi, ecx
0x180002499  jmp     loc_18000222D
0x18000249e  call    TimeInitThread
0x1800024a3  test    eax, eax
0x1800024a5  jnz     loc_180002299
0x1800024ab  lea     rcx, TimerThreadCritSec; lpCriticalSection
0x1800024b2  call    cs:__imp_LeaveCriticalSection
0x1800024b8  jmp     loc_180002333
0x1800024bd  xor     r9d, r9d; TimerType
0x1800024c0  mov     [rsp+98h+TimerHandle], rdi
0x1800024c5  xor     r8d, r8d; ObjectAttributes
0x1800024c8  lea     rcx, [rsp+98h+TimerHandle]; TimerHandle
0x1800024cd  mov     edx, 1F0003h; DesiredAccess
0x1800024d2  call    cs:__imp_NtCreateTimer
0x1800024d8  test    eax, eax
0x1800024da  js      loc_1800022CB
0x1800024e0  mov     rax, [rsp+98h+TimerHandle]
0x1800024e5  mov     [rbx+rbp+20h], rax
0x1800024ea  jmp     loc_180002416
0x1800024ef  xor     eax, eax
0x1800024f1  jmp     loc_18000234D
```
