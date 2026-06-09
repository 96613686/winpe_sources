# WdcProcessMonitor::StartQuery(void)

- ea: `0x18001ff08`
- end: `0x18002007c`
- name: `?StartQuery@WdcProcessMonitor@@QEAAJXZ`
- size: `372`
- prototype: `__int64 __fastcall(WdcProcessMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001fc00`

## callees

- `0x18000b854`
- `0x18001ff08`

## import_xrefs

- `pdh!PdhCollectQueryData` at `0x18002002d`
- `pdh!PdhCollectQueryData` at `0x18002002d`
- `pdh!PdhOpenQueryW` at `0x18001ff4b`
- `pdh!PdhOpenQueryW` at `0x18001ff4b`
- `pdh!PdhAddEnglishCounterW` at `0x18001ffa1`
- `pdh!PdhAddEnglishCounterW` at `0x18001ffcb`
- `pdh!PdhAddEnglishCounterW` at `0x18001fff5`
- `pdh!PdhAddEnglishCounterW` at `0x180020023`
- `pdh!PdhAddEnglishCounterW` at `0x18001ffa1`
- `pdh!PdhAddEnglishCounterW` at `0x18001ffcb`
- `pdh!PdhAddEnglishCounterW` at `0x18001fff5`
- `pdh!PdhAddEnglishCounterW` at `0x180020023`

## pseudocode

```c
__int64 __fastcall WdcProcessMonitor::StartQuery(WdcProcessMonitor *this)
{
  PDH_STATUS v2; // eax
  signed int v3; // ebx
  PDH_STATUS v4; // eax
  PDH_STATUS v5; // eax
  PDH_STATUS v6; // eax
  signed int v8; // [rsp+20h] [rbp-20h]
  PDH_HCOUNTER v9; // [rsp+30h] [rbp-10h] BYREF
  PDH_HCOUNTER v10; // [rsp+38h] [rbp-8h] BYREF
  PDH_HQUERY phQuery; // [rsp+68h] [rbp+28h] BYREF
  PDH_HCOUNTER phCounter; // [rsp+70h] [rbp+30h] BYREF
  PDH_HCOUNTER v13; // [rsp+78h] [rbp+38h] BYREF

  phQuery = 0;
  phCounter = 0;
  v13 = 0;
  v9 = 0;
  v10 = 0;
  v2 = PdhOpenQueryW(0, 0, &phQuery);
  v3 = v2;
  if ( v2 )
  {
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    if ( v3 < 0 )
      goto LABEL_5;
  }
  v4 = PdhAddEnglishCounterW(phQuery, L"\\Processor Information(_Total)\\% DPC Time", 0, &phCounter);
  v3 = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
    if ( v3 < 0 )
      goto LABEL_5;
  }
  v5 = PdhAddEnglishCounterW(phQuery, L"\\Processor Information(_Total)\\% Interrupt Time", 0, &v13);
  v3 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v3 = (unsigned __int16)v5 | 0x80070000;
    if ( v3 < 0 )
      goto LABEL_5;
  }
  v6 = PdhAddEnglishCounterW(phQuery, L"\\Processor Information(*)\\% Processor Utility", 0, &v9);
  v3 = v6;
  if ( !v6 )
    goto LABEL_18;
  if ( v6 > 0 )
    v3 = (unsigned __int16)v6 | 0x80070000;
  if ( v3 < 0 )
  {
LABEL_5:
    v8 = v3;
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\process.cpp",
      "WdcProcessMonitor::StartQuery",
      0,
      L"FAILURE: 0x%08x",
      v8);
  }
  else
  {
LABEL_18:
    PdhAddEnglishCounterW(phQuery, L"\\Processor Information(*)\\Parking Status", 0, &v10);
    PdhCollectQueryData(phQuery);
    v3 = 0;
    *((_QWORD *)this + 1687) = phQuery;
    *((_QWORD *)this + 1688) = phCounter;
    *((_QWORD *)this + 1689) = v13;
    *((_QWORD *)this + 1690) = v9;
    *((_QWORD *)this + 1693) = v10;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001ff08  mov     [rsp-18h+arg_0], rbx
0x18001ff0d  push    rbp
0x18001ff0e  push    rdi
0x18001ff0f  push    r14
0x18001ff11  mov     rbp, rsp
0x18001ff14  sub     rsp, 40h
0x18001ff18  mov     rdi, rcx
0x18001ff1b  mov     [rbp+phQuery], 0
0x18001ff23  xor     ecx, ecx; szDataSource
0x18001ff25  mov     [rbp+phCounter], 0
0x18001ff2d  lea     r8, [rbp+phQuery]; phQuery
0x18001ff31  mov     [rbp+arg_18], 0
0x18001ff39  xor     edx, edx; dwUserData
0x18001ff3b  mov     [rbp+var_10], 0
0x18001ff43  mov     [rbp+var_8], 0
0x18001ff4b  call    cs:__imp_PdhOpenQueryW
0x18001ff51  mov     ebx, eax
0x18001ff53  mov     r14d, 80070000h
0x18001ff59  test    eax, eax
0x18001ff5b  jz      short loc_18001FF8F
0x18001ff5d  jle     short loc_18001FF65
0x18001ff5f  movzx   ebx, ax
0x18001ff62  or      ebx, r14d
0x18001ff65  test    ebx, ebx
0x18001ff67  jns     short loc_18001FF8F
0x18001ff69  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18001ff70  mov     [rsp+40h+var_20], ebx
0x18001ff74  xor     r8d, r8d; int
0x18001ff77  lea     rdx, aWdcprocessmoni_4; "WdcProcessMonitor::StartQuery"
0x18001ff7e  lea     rcx, aBaseDiagnosisP_42; "base\\diagnosis\\pdui\\perfmon\\mon\\pr"...
0x18001ff85  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18001ff8a  jmp     loc_18002006C
0x18001ff8f  mov     rcx, [rbp+phQuery]; hQuery
0x18001ff93  lea     r9, [rbp+phCounter]; phCounter
0x18001ff97  xor     r8d, r8d; dwUserData
0x18001ff9a  lea     rdx, szFullCounterPath; "\\Processor Information(_Total)\\% DPC "...
0x18001ffa1  call    cs:__imp_PdhAddEnglishCounterW
0x18001ffa7  mov     ebx, eax
0x18001ffa9  test    eax, eax
0x18001ffab  jz      short loc_18001FFB9
0x18001ffad  jle     short loc_18001FFB5
0x18001ffaf  movzx   ebx, ax
0x18001ffb2  or      ebx, r14d
0x18001ffb5  test    ebx, ebx
0x18001ffb7  js      short loc_18001FF69
0x18001ffb9  mov     rcx, [rbp+phQuery]; hQuery
0x18001ffbd  lea     r9, [rbp+arg_18]; phCounter
0x18001ffc1  xor     r8d, r8d; dwUserData
0x18001ffc4  lea     rdx, aProcessorInfor_2; "\\Processor Information(_Total)\\% Inte"...
0x18001ffcb  call    cs:__imp_PdhAddEnglishCounterW
0x18001ffd1  mov     ebx, eax
0x18001ffd3  test    eax, eax
0x18001ffd5  jz      short loc_18001FFE3
0x18001ffd7  jle     short loc_18001FFDF
0x18001ffd9  movzx   ebx, ax
0x18001ffdc  or      ebx, r14d
0x18001ffdf  test    ebx, ebx
0x18001ffe1  js      short loc_18001FF69
0x18001ffe3  mov     rcx, [rbp+phQuery]; hQuery
0x18001ffe7  lea     r9, [rbp+var_10]; phCounter
0x18001ffeb  xor     r8d, r8d; dwUserData
0x18001ffee  lea     rdx, aProcessorInfor_0; "\\Processor Information(*)\\% Processor"...
0x18001fff5  call    cs:__imp_PdhAddEnglishCounterW
0x18001fffb  mov     ebx, eax
0x18001fffd  test    eax, eax
0x18001ffff  jz      short loc_180020011
0x180020001  jle     short loc_180020009
0x180020003  movzx   ebx, ax
0x180020006  or      ebx, r14d
0x180020009  test    ebx, ebx
0x18002000b  js      loc_18001FF69
0x180020011  mov     rcx, [rbp+phQuery]; hQuery
0x180020015  lea     r9, [rbp+var_8]; phCounter
0x180020019  xor     r8d, r8d; dwUserData
0x18002001c  lea     rdx, aProcessorInfor; "\\Processor Information(*)\\Parking Sta"...
0x180020023  call    cs:__imp_PdhAddEnglishCounterW
0x180020029  mov     rcx, [rbp+phQuery]; hQuery
0x18002002d  call    cs:__imp_PdhCollectQueryData
0x180020033  mov     rax, [rbp+phQuery]
0x180020037  xor     ebx, ebx
0x180020039  mov     [rdi+34B8h], rax
0x180020040  mov     rax, [rbp+phCounter]
0x180020044  mov     [rdi+34C0h], rax
0x18002004b  mov     rax, [rbp+arg_18]
0x18002004f  mov     [rdi+34C8h], rax
0x180020056  mov     rax, [rbp+var_10]
0x18002005a  mov     [rdi+34D0h], rax
0x180020061  mov     rax, [rbp+var_8]
0x180020065  mov     [rdi+34E8h], rax
0x18002006c  mov     eax, ebx
0x18002006e  mov     rbx, [rsp+40h+arg_0]
0x180020073  add     rsp, 40h
0x180020077  pop     r14
0x180020079  pop     rdi
0x18002007a  pop     rbp
0x18002007b  retn
```
