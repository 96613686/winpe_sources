# VirtualMachine::UpdateCriticalErrorTimeout(__int64)

- ea: `0x14015ef84`
- end: `0x14015f0e4`
- name: `?UpdateCriticalErrorTimeout@VirtualMachine@@AEAAX_J@Z`
- size: `352`
- prototype: `void __fastcall(VirtualMachine *__hidden this, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140077c20`

## callees

- `0x14011ea40`
- `0x14015e630`
- `0x14015ef84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14015efb7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14015efb7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14015f0ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14015f0ba`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimerEx` at `0x14015effa`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimerEx` at `0x14015effa`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14015f08f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14015f08f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14015f01c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14015f01c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall VirtualMachine::UpdateCriticalErrorTimeout(VirtualMachine *this, __int64 a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  char i; // al
  struct _FILETIME v6; // rax
  __int64 v7; // rcx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-20h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 2456);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 2456));
  for ( i = 1; i && *((_QWORD *)this + 306) != a2; i = 0 )
  {
    if ( !*((_DWORD *)this + 626) )
    {
      *((_QWORD *)this + 306) = a2;
      break;
    }
    if ( !SetThreadpoolTimerEx(*((PTP_TIMER *)this + 312), 0, 0, 0) )
      break;
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v6 = SystemTimeAsFileTime;
    v7 = *(_QWORD *)((char *)this + 2508);
    if ( *(_QWORD *)&SystemTimeAsFileTime >= 10000000 * a2 + v7 )
    {
      VirtualMachine::StopCritical(this);
      break;
    }
    *((_QWORD *)this + 306) = a2;
    SystemTimeAsFileTime = (struct _FILETIME)(*(_QWORD *)&v6 - 10000000 * a2 - v7);
    SetThreadpoolTimer(*((PTP_TIMER *)this + 312), &SystemTimeAsFileTime, 0, 0);
  }
  LeaveCriticalSection(v4);
}

```

## disassembly

```asm
0x14015ef84  mov     [rsp+arg_10], rbx
0x14015ef89  mov     [rsp+arg_18], rsi
0x14015ef8e  push    rdi
0x14015ef8f  sub     rsp, 50h
0x14015ef93  mov     rax, cs:__security_cookie
0x14015ef9a  xor     rax, rsp
0x14015ef9d  mov     [rsp+58h+var_18], rax
0x14015efa2  mov     rsi, rdx
0x14015efa5  mov     rbx, rcx
0x14015efa8  lea     rdi, [rcx+998h]
0x14015efaf  mov     [rsp+58h+var_30], rdi
0x14015efb4  mov     rcx, rdi; lpCriticalSection
0x14015efb7  call    cs:__imp_EnterCriticalSection
0x14015efbe  nop     dword ptr [rax+rax+00h]
0x14015efc3  mov     al, 1
0x14015efc5  mov     [rsp+58h+var_28], al
0x14015efc9  test    al, al
0x14015efcb  jz      loc_14015F0B7
0x14015efd1  cmp     [rbx+990h], rsi
0x14015efd8  jz      loc_14015F0B7
0x14015efde  cmp     dword ptr [rbx+9C8h], 0
0x14015efe5  jz      loc_14015F0B0
0x14015efeb  xor     r9d, r9d; msWindowLength
0x14015efee  xor     r8d, r8d; msPeriod
0x14015eff1  xor     edx, edx; pftDueTime
0x14015eff3  mov     rcx, [rbx+9C0h]; pti
0x14015effa  call    cs:__imp_SetThreadpoolTimerEx
0x14015f001  nop     dword ptr [rax+rax+00h]
0x14015f006  test    eax, eax
0x14015f008  jz      loc_14015F0B7
0x14015f00e  mov     qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime], 0
0x14015f017  lea     rcx, [rsp+58h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14015f01c  call    cs:__imp_GetSystemTimeAsFileTime
0x14015f023  nop     dword ptr [rax+rax+00h]
0x14015f028  mov     rax, qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime]
0x14015f02d  mov     [rsp+58h+var_38], rax
0x14015f032  mov     ecx, [rbx+9CCh]
0x14015f038  mov     dword ptr [rsp+58h+var_38], ecx
0x14015f03c  mov     ecx, [rbx+9D0h]
0x14015f042  mov     dword ptr [rsp+58h+var_38+4], ecx
0x14015f046  imul    r8, rsi, 989680h
0x14015f04d  mov     rcx, [rsp+58h+var_38]
0x14015f052  lea     rdx, [r8+rcx]
0x14015f056  cmp     rax, rdx
0x14015f059  jge     short loc_14015F0A6
0x14015f05b  mov     [rbx+990h], rsi
0x14015f062  sub     rax, r8
0x14015f065  sub     rax, rcx
0x14015f068  mov     [rsp+58h+var_38], rax
0x14015f06d  shr     rax, 20h
0x14015f071  mov     [rsp+58h+SystemTimeAsFileTime.dwHighDateTime], eax
0x14015f075  mov     eax, dword ptr [rsp+58h+var_38]
0x14015f079  mov     [rsp+58h+SystemTimeAsFileTime.dwLowDateTime], eax
0x14015f07d  xor     r9d, r9d; msWindowLength
0x14015f080  xor     r8d, r8d; msPeriod
0x14015f083  lea     rdx, [rsp+58h+SystemTimeAsFileTime]; pftDueTime
0x14015f088  mov     rcx, [rbx+9C0h]; pti
0x14015f08f  call    cs:__imp_SetThreadpoolTimer
0x14015f096  nop     dword ptr [rax+rax+00h]
0x14015f09b  xor     al, al
0x14015f09d  mov     [rsp+58h+var_28], al
0x14015f0a1  jmp     loc_14015EFC9
0x14015f0a6  mov     rcx, rbx; this
0x14015f0a9  call    ?StopCritical@VirtualMachine@@AEAAJXZ; VirtualMachine::StopCritical(void)
0x14015f0ae  jmp     short loc_14015F0B7
0x14015f0b0  mov     [rbx+990h], rsi
0x14015f0b7  mov     rcx, rdi; lpCriticalSection
0x14015f0ba  call    cs:__imp_LeaveCriticalSection
0x14015f0c1  nop     dword ptr [rax+rax+00h]
0x14015f0c6  mov     rcx, [rsp+58h+var_18]
0x14015f0cb  xor     rcx, rsp; StackCookie
0x14015f0ce  call    __security_check_cookie
0x14015f0d3  mov     rbx, [rsp+58h+arg_10]
0x14015f0d8  mov     rsi, [rsp+58h+arg_18]
0x14015f0dd  add     rsp, 50h
0x14015f0e1  pop     rdi
0x14015f0e2  retn
```
