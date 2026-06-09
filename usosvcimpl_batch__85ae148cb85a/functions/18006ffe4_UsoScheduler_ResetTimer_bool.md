# UsoScheduler::ResetTimer(bool)

- ea: `0x18006ffe4`
- end: `0x180070130`
- name: `?ResetTimer@UsoScheduler@@QEAAX_N@Z`
- size: `332`
- prototype: `void __fastcall(UsoScheduler *this, char)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18006f880`
- `0x18006f928`
- `0x180070138`

## callees

- `0x18006fbe4`
- `0x18006fd5c`
- `0x18006ffe4`
- `0x1800dd930`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070108`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070108`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007000e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007000e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800700fe`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800700fe`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18007004e`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180070080`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18007004e`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180070080`

## pseudocode

```c
void __fastcall UsoScheduler::ResetTimer(UsoScheduler *this, char a2)
{
  __int64 v4; // rbx
  signed __int64 v5; // rcx
  signed __int64 v6; // [rsp+20h] [rbp-30h] BYREF
  char v7; // [rsp+28h] [rbp-28h]
  UsoScheduler *v8; // [rsp+30h] [rbp-20h]
  struct _FILETIME pftDueTime; // [rsp+38h] [rbp-18h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)this);
  v8 = this;
  v4 = *((_QWORD *)this + 35);
  if ( *((_BYTE *)this + 288) )
  {
    UsoScheduler::GetLastRunTime(this, &v6);
    if ( v7
      && (pftDueTime = 0,
          GetSystemTimePreciseAsFileTime(&pftDueTime),
          v6 < (__int64)(pftDueTime.dwLowDateTime
                       + ((unsigned __int64)pftDueTime.dwHighDateTime << 32)
                       - 116444736000000000LL)) )
    {
      pftDueTime = 0;
      GetSystemTimePreciseAsFileTime(&pftDueTime);
      v5 = ((unsigned __int64)pftDueTime.dwHighDateTime << 32) - v6 - 116444736000000000LL + pftDueTime.dwLowDateTime;
      if ( v5 == 10000000 * v4 || v5 < 10000000 * v4 )
        v4 += ((unsigned __int64)(((unsigned __int128)(v5 * (__int128)0x29406B2A1A85BD43LL) >> 64) - v5) >> 63)
            + ((__int64)(((unsigned __int128)(v5 * (__int128)0x29406B2A1A85BD43LL) >> 64) - v5) >> 23);
      else
        v4 = 0;
    }
    else
    {
      UsoScheduler::SaveRunTime(this);
    }
    if ( *((_BYTE *)this + 288) )
      goto LABEL_11;
  }
  if ( a2 )
  {
LABEL_11:
    pftDueTime = (struct _FILETIME)(-10000000 * v4);
    SetThreadpoolTimer(*((PTP_TIMER *)this + 15), &pftDueTime, 0, 0);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x18006ffe4  mov     [rsp-18h+arg_8], rbx
0x18006ffe9  mov     [rsp-18h+arg_10], rsi
0x18006ffee  push    rbp
0x18006ffef  push    r12
0x18006fff1  push    r14
0x18006fff3  mov     rbp, rsp
0x18006fff6  sub     rsp, 50h
0x18006fffa  mov     rax, cs:__security_cookie
0x180070001  xor     rax, rsp
0x180070004  mov     [rbp+var_10], rax
0x180070008  mov     r14b, dl
0x18007000b  mov     rsi, rcx
0x18007000e  call    cs:__imp_EnterCriticalSection
0x180070014  mov     [rbp+var_20], rsi
0x180070018  mov     rbx, [rsi+118h]
0x18007001f  cmp     byte ptr [rsi+120h], 0
0x180070026  jz      loc_1800700E0
0x18007002c  lea     rdx, [rbp+var_30]
0x180070030  mov     rcx, rsi
0x180070033  call    ?GetLastRunTime@UsoScheduler@@AEAA?AV?$optional@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@std@@XZ; UsoScheduler::GetLastRunTime(void)
0x180070038  cmp     [rbp+var_28], 0
0x18007003c  jz      loc_1800700CF
0x180070042  mov     qword ptr [rbp+pftDueTime.dwLowDateTime], 0
0x18007004a  lea     rcx, [rbp+pftDueTime]
0x18007004e  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x180070054  mov     edx, [rbp+pftDueTime.dwHighDateTime]
0x180070057  shl     rdx, 20h
0x18007005b  mov     ecx, [rbp+pftDueTime.dwLowDateTime]
0x18007005e  mov     r12, 0FE624E212AC18000h
0x180070068  add     rdx, r12
0x18007006b  add     rdx, rcx
0x18007006e  cmp     [rbp+var_30], rdx
0x180070072  jge     short loc_1800700CF
0x180070074  mov     qword ptr [rbp+pftDueTime.dwLowDateTime], 0
0x18007007c  lea     rcx, [rbp+pftDueTime]
0x180070080  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x180070086  mov     eax, [rbp+pftDueTime.dwHighDateTime]
0x180070089  shl     rax, 20h
0x18007008d  sub     rax, [rbp+var_30]
0x180070091  mov     ecx, [rbp+pftDueTime.dwLowDateTime]
0x180070094  add     rax, r12
0x180070097  add     rcx, rax
0x18007009a  imul    rax, rbx, 989680h
0x1800700a1  cmp     rcx, rax
0x1800700a4  jz      short loc_1800700AC
0x1800700a6  jl      short loc_1800700AC
0x1800700a8  xor     ebx, ebx
0x1800700aa  jmp     short loc_1800700D7
0x1800700ac  mov     rax, 29406B2A1A85BD43h
0x1800700b6  imul    rcx
0x1800700b9  sub     rdx, rcx
0x1800700bc  sar     rdx, 17h
0x1800700c0  mov     rax, rdx
0x1800700c3  shr     rax, 3Fh
0x1800700c7  add     rdx, rax
0x1800700ca  add     rbx, rdx
0x1800700cd  jmp     short loc_1800700D7
0x1800700cf  mov     rcx, rsi; this
0x1800700d2  call    ?SaveRunTime@UsoScheduler@@QEAAXXZ; UsoScheduler::SaveRunTime(void)
0x1800700d7  cmp     byte ptr [rsi+120h], 0
0x1800700de  jnz     short loc_1800700E5
0x1800700e0  test    r14b, r14b
0x1800700e3  jz      short loc_180070105
0x1800700e5  imul    rax, rbx, 0FFFFFFFFFF676980h
0x1800700ec  mov     qword ptr [rbp+pftDueTime.dwLowDateTime], rax
0x1800700f0  xor     r9d, r9d; msWindowLength
0x1800700f3  xor     r8d, r8d; msPeriod
0x1800700f6  lea     rdx, [rbp+pftDueTime]; pftDueTime
0x1800700fa  mov     rcx, [rsi+78h]; pti
0x1800700fe  call    cs:__imp_SetThreadpoolTimer
0x180070104  nop
0x180070105  mov     rcx, rsi; lpCriticalSection
0x180070108  call    cs:__imp_LeaveCriticalSection
0x18007010e  mov     rcx, [rbp+var_10]
0x180070112  xor     rcx, rsp; StackCookie
0x180070115  call    __security_check_cookie
0x18007011a  lea     r11, [rsp+50h+var_s0]
0x18007011f  mov     rbx, [r11+28h]
0x180070123  mov     rsi, [r11+30h]
0x180070127  mov     rsp, r11
0x18007012a  pop     r14
0x18007012c  pop     r12
0x18007012e  pop     rbp
0x18007012f  retn
```
