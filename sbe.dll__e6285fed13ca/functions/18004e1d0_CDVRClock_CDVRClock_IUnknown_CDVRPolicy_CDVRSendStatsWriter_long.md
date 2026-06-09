# CDVRClock::CDVRClock(IUnknown *,CDVRPolicy *,CDVRSendStatsWriter *,long *)

- ea: `0x18004e1d0`
- end: `0x18004e2eb`
- name: `??0CDVRClock@@QEAA@PEAUIUnknown@@PEAVCDVRPolicy@@PEAVCDVRSendStatsWriter@@PEAJ@Z`
- size: `283`
- prototype: `CDVRClock *__fastcall(CDVRClock *__hidden this, struct IUnknown *, struct CDVRPolicy *, struct CDVRSendStatsWriter *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180008a78`

## callees

- `0x18004de60`
- `0x18004e1d0`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x18004e2b8`
- `KERNEL32!CreateEventW` at `0x18004e2b8`
- `KERNEL32!InitializeCriticalSection` at `0x18004e2a6`
- `KERNEL32!InitializeCriticalSection` at `0x18004e2a6`
- `KERNEL32!GetLastError` at `0x18004e269`
- `KERNEL32!GetLastError` at `0x18004e2c7`
- `KERNEL32!GetLastError` at `0x18004e269`
- `KERNEL32!GetLastError` at `0x18004e2c7`
- `KERNEL32!QueryPerformanceCounter` at `0x18004e25f`
- `KERNEL32!QueryPerformanceCounter` at `0x18004e25f`
- `KERNEL32!QueryPerformanceFrequency` at `0x18004e249`
- `KERNEL32!QueryPerformanceFrequency` at `0x18004e249`

## pseudocode

```c
CDVRClock *__fastcall CDVRClock::CDVRClock(
        CDVRClock *this,
        struct IUnknown *a2,
        struct CDVRPolicy *a3,
        struct CDVRSendStatsWriter *a4,
        int *a5)
{
  int v5; // r14d
  LARGE_INTEGER *v6; // rsi
  int v9; // r15d
  int v10; // r9d
  signed int LastError; // eax
  HANDLE EventW; // rax
  signed int v13; // eax

  v5 = (_DWORD)this + 8;
  *((_QWORD *)this + 2) = a4;
  *((_QWORD *)this + 3) = a2;
  *(_QWORD *)this = &CDVRClock::`vftable'{for `IReferenceClock'};
  v6 = (LARGE_INTEGER *)((char *)this + 168);
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  v9 = (int)a3;
  *((_QWORD *)this + 8) = 0;
  *((_DWORD *)this + 18) = 0;
  *((_DWORD *)this + 40) = 0;
  *((_QWORD *)this + 1) = &CDVRClock::`vftable'{for `CTIGetTime<__int64>'};
  if ( !QueryPerformanceFrequency((LARGE_INTEGER *)this + 21) || !QueryPerformanceCounter(v6 + 1) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    *a5 = LastError;
  }
  CTCClockSubordinate<__int64,unsigned __int64>::CTCClockSubordinate<__int64,unsigned __int64>(
    (_DWORD)this + 184,
    v5 & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64),
    v9,
    v10,
    (__int64)a4);
  if ( *a5 >= 0 )
  {
    InitializeCriticalSection((LPCRITICAL_SECTION)this + 2);
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 8) = EventW;
    if ( !EventW )
    {
      v13 = GetLastError();
      if ( v13 > 0 )
        v13 = (unsigned __int16)v13 | 0x80070000;
      *a5 = v13;
    }
  }
  return this;
}

```

## disassembly

```asm
0x18004e1d0  push    rbx
0x18004e1d2  push    rbp
0x18004e1d3  push    rsi
0x18004e1d4  push    rdi
0x18004e1d5  push    r14
0x18004e1d7  push    r15
0x18004e1d9  sub     rsp, 38h
0x18004e1dd  lea     r14, [rcx+8]
0x18004e1e1  mov     [rcx+10h], r9
0x18004e1e5  lea     rax, ??_7CDVRClock@@6BIReferenceClock@@@; const CDVRClock::`vftable'{for `IReferenceClock'}
0x18004e1ec  mov     [rcx+18h], rdx
0x18004e1f0  mov     [rcx], rax
0x18004e1f3  lea     rsi, [rcx+0A8h]
0x18004e1fa  lea     rax, ??_7CDVRClock@@6B?$CTIGetTime@_J@@@; const CDVRClock::`vftable'{for `CTIGetTime<__int64>'}
0x18004e201  mov     qword ptr [rcx+20h], 0
0x18004e209  mov     rbx, rcx
0x18004e20c  mov     qword ptr [rcx+28h], 0
0x18004e214  mov     qword ptr [rcx+30h], 0
0x18004e21c  mov     rbp, r9
0x18004e21f  mov     qword ptr [rcx+38h], 0
0x18004e227  mov     r15, r8
0x18004e22a  mov     qword ptr [rcx+40h], 0
0x18004e232  mov     dword ptr [rcx+48h], 0
0x18004e239  mov     dword ptr [rcx+0A0h], 0
0x18004e243  mov     rcx, rsi; lpFrequency
0x18004e246  mov     [r14], rax
0x18004e249  call    cs:__imp_QueryPerformanceFrequency
0x18004e24f  mov     rdi, [rsp+68h+arg_20]
0x18004e257  test    eax, eax
0x18004e259  jz      short loc_18004E269
0x18004e25b  lea     rcx, [rsi+8]; lpPerformanceCount
0x18004e25f  call    cs:__imp_QueryPerformanceCounter
0x18004e265  test    eax, eax
0x18004e267  jnz     short loc_18004E27D
0x18004e269  call    cs:__imp_GetLastError
0x18004e26f  test    eax, eax
0x18004e271  jle     short loc_18004E27B
0x18004e273  movzx   eax, ax
0x18004e276  or      eax, 80070000h
0x18004e27b  mov     [rdi], eax
0x18004e27d  mov     rax, rbx
0x18004e280  mov     [rsp+68h+var_48], rbp
0x18004e285  neg     rax
0x18004e288  lea     rcx, [rbx+0B8h]
0x18004e28f  mov     r8, r15
0x18004e292  sbb     rdx, rdx
0x18004e295  and     rdx, r14
0x18004e298  call    ??0?$CTCClockSubordinate@_J_K@@QEAA@PEAV?$CTIGetTime@_J@@PEAVCDVRPolicy@@_KPEAVCDVRSendStatsWriter@@@Z; CTCClockSubordinate<__int64,unsigned __int64>::CTCClockSubordinate<__int64,unsigned __int64>(CTIGetTime<__int64> *,CDVRPolicy *,unsigned __int64,CDVRSendStatsWriter *)
0x18004e29d  cmp     dword ptr [rdi], 0
0x18004e2a0  jl      short loc_18004E2DB
0x18004e2a2  lea     rcx, [rbx+50h]; lpCriticalSection
0x18004e2a6  call    cs:__imp_InitializeCriticalSection
0x18004e2ac  xor     r9d, r9d; lpName
0x18004e2af  xor     r8d, r8d; bInitialState
0x18004e2b2  xor     ecx, ecx; lpEventAttributes
0x18004e2b4  lea     edx, [r9+1]; bManualReset
0x18004e2b8  call    cs:__imp_CreateEventW
0x18004e2be  mov     [rbx+40h], rax
0x18004e2c2  test    rax, rax
0x18004e2c5  jnz     short loc_18004E2DB
0x18004e2c7  call    cs:__imp_GetLastError
0x18004e2cd  test    eax, eax
0x18004e2cf  jle     short loc_18004E2D9
0x18004e2d1  movzx   eax, ax
0x18004e2d4  or      eax, 80070000h
0x18004e2d9  mov     [rdi], eax
0x18004e2db  mov     rax, rbx
0x18004e2de  add     rsp, 38h
0x18004e2e2  pop     r15
0x18004e2e4  pop     r14
0x18004e2e6  pop     rdi
0x18004e2e7  pop     rsi
0x18004e2e8  pop     rbp
0x18004e2e9  pop     rbx
0x18004e2ea  retn
```
