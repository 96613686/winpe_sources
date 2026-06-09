# CDVRClock::ConfirmAdviseThreadRunning_(void)

- ea: `0x18004e81c`
- end: `0x18004e8fc`
- name: `?ConfirmAdviseThreadRunning_@CDVRClock@@AEAAJXZ`
- size: `224`
- prototype: `__int64 __fastcall(CDVRClock *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18004e458`
- `0x18004e654`

## callees

- `0x180001c00`
- `0x18004e81c`

## import_xrefs

- `KERNEL32!CreateThread` at `0x18004e8a0`
- `KERNEL32!CreateThread` at `0x18004e8a0`
- `KERNEL32!GetLastError` at `0x18004e8af`
- `KERNEL32!GetLastError` at `0x18004e8af`
- `KERNEL32!SetThreadPriority` at `0x18004e8dc`
- `KERNEL32!SetThreadPriority` at `0x18004e8dc`
- `WINMM!timeGetDevCaps` at `0x18004e85d`
- `WINMM!timeGetDevCaps` at `0x18004e85d`
- `WINMM!timeEndPeriod` at `0x18004e8bd`
- `WINMM!timeEndPeriod` at `0x18004e8bd`
- `WINMM!timeBeginPeriod` at `0x18004e87b`
- `WINMM!timeBeginPeriod` at `0x18004e87b`

## pseudocode

```c
__int64 __fastcall CDVRClock::ConfirmAdviseThreadRunning_(CDVRClock *this)
{
  bool v1; // zf
  UINT wPeriodMin; // ecx
  HANDLE Thread; // rax
  signed int LastError; // ebx
  timecaps_tag ptc; // [rsp+30h] [rbp-18h] BYREF

  v1 = *((_QWORD *)this + 7) == 0;
  ptc = 0;
  if ( !v1 )
    return 0;
  *((_DWORD *)this + 18) = 0;
  if ( timeGetDevCaps(&ptc, 8u) || (wPeriodMin = ptc.wPeriodMin, ptc.wPeriodMin < 0xA) )
    wPeriodMin = 10;
  *((_DWORD *)this + 40) = wPeriodMin;
  timeBeginPeriod(wPeriodMin);
  Thread = CreateThread(0, 0, CDVRClock::ThreadEntry, this, 0, 0);
  *((_QWORD *)this + 7) = Thread;
  if ( Thread )
  {
    SetThreadPriority(Thread, 15);
    return 0;
  }
  LastError = GetLastError();
  timeEndPeriod(*((_DWORD *)this + 40));
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18004e81c  mov     [rsp+arg_8], rbx
0x18004e821  push    rdi
0x18004e822  sub     rsp, 40h
0x18004e826  mov     rax, cs:__security_cookie
0x18004e82d  xor     rax, rsp
0x18004e830  mov     [rsp+48h+var_10], rax
0x18004e835  cmp     qword ptr [rcx+38h], 0
0x18004e83a  mov     rdi, rcx
0x18004e83d  mov     qword ptr [rsp+48h+ptc.wPeriodMin], 0
0x18004e846  jnz     loc_18004E8E2
0x18004e84c  mov     dword ptr [rcx+48h], 0
0x18004e853  mov     edx, 8; cbtc
0x18004e858  lea     rcx, [rsp+48h+ptc]; ptc
0x18004e85d  call    cs:__imp_timeGetDevCaps
0x18004e863  test    eax, eax
0x18004e865  jnz     short loc_18004E870
0x18004e867  mov     ecx, [rsp+48h+ptc.wPeriodMin]
0x18004e86b  cmp     ecx, 0Ah
0x18004e86e  jnb     short loc_18004E875
0x18004e870  mov     ecx, 0Ah; uPeriod
0x18004e875  mov     [rdi+0A0h], ecx
0x18004e87b  call    cs:__imp_timeBeginPeriod
0x18004e881  mov     r9, rdi; lpParameter
0x18004e884  mov     [rsp+48h+lpThreadId], 0; lpThreadId
0x18004e88d  lea     r8, ?ThreadEntry@CDVRClock@@SAKPEAX@Z; lpStartAddress
0x18004e894  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x18004e89c  xor     edx, edx; dwStackSize
0x18004e89e  xor     ecx, ecx; lpThreadAttributes
0x18004e8a0  call    cs:__imp_CreateThread
0x18004e8a6  mov     [rdi+38h], rax
0x18004e8aa  test    rax, rax
0x18004e8ad  jnz     short loc_18004E8D4
0x18004e8af  call    cs:__imp_GetLastError
0x18004e8b5  mov     ecx, [rdi+0A0h]; uPeriod
0x18004e8bb  mov     ebx, eax
0x18004e8bd  call    cs:__imp_timeEndPeriod
0x18004e8c3  test    ebx, ebx
0x18004e8c5  jle     short loc_18004E8D0
0x18004e8c7  movzx   ebx, bx
0x18004e8ca  or      ebx, 80070000h
0x18004e8d0  mov     eax, ebx
0x18004e8d2  jmp     short loc_18004E8E4
0x18004e8d4  mov     edx, 0Fh; nPriority
0x18004e8d9  mov     rcx, rax; hThread
0x18004e8dc  call    cs:__imp_SetThreadPriority
0x18004e8e2  xor     eax, eax
0x18004e8e4  mov     rcx, [rsp+48h+var_10]
0x18004e8e9  xor     rcx, rsp; StackCookie
0x18004e8ec  call    __security_check_cookie
0x18004e8f1  mov     rbx, [rsp+48h+arg_8]
0x18004e8f6  add     rsp, 40h
0x18004e8fa  pop     rdi
0x18004e8fb  retn
```
