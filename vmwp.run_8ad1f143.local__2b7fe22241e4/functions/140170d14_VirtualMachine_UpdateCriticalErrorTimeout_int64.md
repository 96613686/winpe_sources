# VirtualMachine::UpdateCriticalErrorTimeout(__int64)

- ea: `0x140170d14`
- end: `0x140170e74`
- name: `?UpdateCriticalErrorTimeout@VirtualMachine@@AEAAX_J@Z`
- size: `352`
- prototype: `void __fastcall(VirtualMachine *__hidden this, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14006a550`

## callees

- `0x140132960`
- `0x140170410`
- `0x140170d14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140170d47`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140170d47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140170e4a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140170e4a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140170e1f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140170e1f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimerEx` at `0x140170d8a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimerEx` at `0x140170d8a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140170dac`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140170dac`

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
0x140170d14  mov     [rsp+arg_10], rbx
0x140170d19  mov     [rsp+arg_18], rsi
0x140170d1e  push    rdi
0x140170d1f  sub     rsp, 50h
0x140170d23  mov     rax, cs:__security_cookie
0x140170d2a  xor     rax, rsp
0x140170d2d  mov     [rsp+58h+var_18], rax
0x140170d32  mov     rsi, rdx
0x140170d35  mov     rbx, rcx
0x140170d38  lea     rdi, [rcx+998h]
0x140170d3f  mov     [rsp+58h+var_30], rdi
0x140170d44  mov     rcx, rdi; lpCriticalSection
0x140170d47  call    cs:__imp_EnterCriticalSection
0x140170d4e  nop     dword ptr [rax+rax+00h]
0x140170d53  mov     al, 1
0x140170d55  mov     [rsp+58h+var_28], al
0x140170d59  test    al, al
0x140170d5b  jz      loc_140170E47
0x140170d61  cmp     [rbx+990h], rsi
0x140170d68  jz      loc_140170E47
0x140170d6e  cmp     dword ptr [rbx+9C8h], 0
0x140170d75  jz      loc_140170E40
0x140170d7b  xor     r9d, r9d; msWindowLength
0x140170d7e  xor     r8d, r8d; msPeriod
0x140170d81  xor     edx, edx; pftDueTime
0x140170d83  mov     rcx, [rbx+9C0h]; pti
0x140170d8a  call    cs:__imp_SetThreadpoolTimerEx
0x140170d91  nop     dword ptr [rax+rax+00h]
0x140170d96  test    eax, eax
0x140170d98  jz      loc_140170E47
0x140170d9e  mov     qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime], 0
0x140170da7  lea     rcx, [rsp+58h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140170dac  call    cs:__imp_GetSystemTimeAsFileTime
0x140170db3  nop     dword ptr [rax+rax+00h]
0x140170db8  mov     rax, qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime]
0x140170dbd  mov     [rsp+58h+var_38], rax
0x140170dc2  mov     ecx, [rbx+9CCh]
0x140170dc8  mov     dword ptr [rsp+58h+var_38], ecx
0x140170dcc  mov     ecx, [rbx+9D0h]
0x140170dd2  mov     dword ptr [rsp+58h+var_38+4], ecx
0x140170dd6  imul    r8, rsi, 989680h
0x140170ddd  mov     rcx, [rsp+58h+var_38]
0x140170de2  lea     rdx, [r8+rcx]
0x140170de6  cmp     rax, rdx
0x140170de9  jge     short loc_140170E36
0x140170deb  mov     [rbx+990h], rsi
0x140170df2  sub     rax, r8
0x140170df5  sub     rax, rcx
0x140170df8  mov     [rsp+58h+var_38], rax
0x140170dfd  shr     rax, 20h
0x140170e01  mov     [rsp+58h+SystemTimeAsFileTime.dwHighDateTime], eax
0x140170e05  mov     eax, dword ptr [rsp+58h+var_38]
0x140170e09  mov     [rsp+58h+SystemTimeAsFileTime.dwLowDateTime], eax
0x140170e0d  xor     r9d, r9d; msWindowLength
0x140170e10  xor     r8d, r8d; msPeriod
0x140170e13  lea     rdx, [rsp+58h+SystemTimeAsFileTime]; pftDueTime
0x140170e18  mov     rcx, [rbx+9C0h]; pti
0x140170e1f  call    cs:__imp_SetThreadpoolTimer
0x140170e26  nop     dword ptr [rax+rax+00h]
0x140170e2b  xor     al, al
0x140170e2d  mov     [rsp+58h+var_28], al
0x140170e31  jmp     loc_140170D59
0x140170e36  mov     rcx, rbx; this
0x140170e39  call    ?StopCritical@VirtualMachine@@AEAAJXZ; VirtualMachine::StopCritical(void)
0x140170e3e  jmp     short loc_140170E47
0x140170e40  mov     [rbx+990h], rsi
0x140170e47  mov     rcx, rdi; lpCriticalSection
0x140170e4a  call    cs:__imp_LeaveCriticalSection
0x140170e51  nop     dword ptr [rax+rax+00h]
0x140170e56  mov     rcx, [rsp+58h+var_18]
0x140170e5b  xor     rcx, rsp; StackCookie
0x140170e5e  call    __security_check_cookie
0x140170e63  mov     rbx, [rsp+58h+arg_10]
0x140170e68  mov     rsi, [rsp+58h+arg_18]
0x140170e6d  add     rsp, 50h
0x140170e71  pop     rdi
0x140170e72  retn
```
