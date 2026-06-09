# KmclExceededWatchdogLimit

- ea: `0x140006ff4`
- end: `0x140007062`
- name: `KmclExceededWatchdogLimit`
- size: `110`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140001370`
- `0x140001780`
- `0x140001ce0`

## callees

- `0x140006ff4`
- `0x140011e90`

## import_xrefs

- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14000701e`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14000701e`

## pseudocode

```c
bool KmclExceededWatchdogLimit()
{
  char v0; // bl
  _KDPC_WATCHDOG_INFORMATION WatchdogInformation; // [rsp+20h] [rbp-28h] BYREF

  v0 = 0;
  memset(&WatchdogInformation, 0, sizeof(WatchdogInformation));
  if ( KeQueryDpcWatchdogInformation(&WatchdogInformation) >= 0 )
    return WatchdogInformation.DpcWatchdogCount < 30 * WatchdogInformation.DpcWatchdogLimit / 0x64;
  return v0;
}

```

## disassembly

```asm
0x140006ff4  push    rbx
0x140006ff6  sub     rsp, 40h
0x140006ffa  mov     rax, cs:__security_cookie
0x140007001  xor     rax, rsp
0x140007004  mov     [rsp+48h+var_10], rax
0x140007009  xorps   xmm0, xmm0
0x14000700c  lea     rcx, [rsp+48h+WatchdogInformation]; WatchdogInformation
0x140007011  xor     eax, eax
0x140007013  xor     bl, bl
0x140007015  movups  xmmword ptr [rsp+48h+WatchdogInformation.DpcTimeLimit], xmm0
0x14000701a  mov     [rsp+48h+WatchdogInformation.Reserved], eax
0x14000701e  call    cs:__imp_KeQueryDpcWatchdogInformation
0x140007025  nop     dword ptr [rax+rax+00h]
0x14000702a  test    eax, eax
0x14000702c  js      short loc_14000704C
0x14000702e  imul    ecx, [rsp+48h+WatchdogInformation.DpcWatchdogLimit], 1Eh
0x140007033  mov     eax, 51EB851Fh
0x140007038  movzx   ebx, bl
0x14000703b  mul     ecx
0x14000703d  mov     eax, 1
0x140007042  shr     edx, 5
0x140007045  cmp     [rsp+48h+WatchdogInformation.DpcWatchdogCount], edx
0x140007049  cmovb   ebx, eax
0x14000704c  mov     al, bl
0x14000704e  mov     rcx, [rsp+48h+var_10]
0x140007053  xor     rcx, rsp; StackCookie
0x140007056  call    __security_check_cookie
0x14000705b  add     rsp, 40h
0x14000705f  pop     rbx
0x140007060  retn
```
