# CLoadBalancingMetrics::CLoadBalancingMetrics(void)

- ea: `0x18000d2e8`
- end: `0x18000d516`
- name: `??0CLoadBalancingMetrics@@QEAA@XZ`
- size: `558`
- prototype: `CLoadBalancingMetrics *__fastcall(CLoadBalancingMetrics *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c820`

## callees

- `0x180007890`
- `0x18000d2e8`
- `0x18002fe06`
- `0x18002fe40`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x18000d37e`
- `ntdll!NtQuerySystemInformation` at `0x18000d3d2`
- `ntdll!NtQuerySystemInformation` at `0x18000d40c`
- `ntdll!NtQuerySystemInformation` at `0x18000d37e`
- `ntdll!NtQuerySystemInformation` at `0x18000d3d2`
- `ntdll!NtQuerySystemInformation` at `0x18000d40c`

## string_xrefs

- `0x18000d416`: `InitializeLoadMetrics failed! SystemProcessorPerformanceInformation: %lx`
- `0x18000d4ed`: `   PtesAvail  [%6ld], PagedUsed [%6ld], Commit   [%6ld]`
- `0x18000d4fe`: `InitializeLoadMetrics failed! SystemPerformanceInformation: %lx`

## pseudocode

```c
CLoadBalancingMetrics *__fastcall CLoadBalancingMetrics::CLoadBalancingMetrics(CLoadBalancingMetrics *this)
{
  NTSTATUS v2; // eax
  unsigned int v3; // ecx
  NTSTATUS v4; // eax
  const char *v5; // rdx
  unsigned int v7; // r10d
  __int64 v8; // rdx
  __int64 v9; // r9
  __int64 v10; // r8
  __int64 v11; // rcx
  _BYTE SystemInformation[8]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v13; // [rsp+38h] [rbp-C8h]
  int v14; // [rsp+3Ch] [rbp-C4h]
  char v15; // [rsp+68h] [rbp-98h]
  _BYTE v16[112]; // [rsp+70h] [rbp-90h] BYREF
  int v17; // [rsp+E0h] [rbp-20h]
  int v18; // [rsp+F8h] [rbp-8h]
  _QWORD v19[192]; // [rsp+1F0h] [rbp+F0h] BYREF

  *(_BYTE *)this = 0;
  *(_QWORD *)((char *)this + 4) = 0;
  *(_QWORD *)((char *)this + 12) = 0;
  *(_QWORD *)((char *)this + 20) = 0;
  *(_QWORD *)((char *)this + 28) = 0;
  *(_QWORD *)((char *)this + 36) = 0;
  *(_QWORD *)((char *)this + 44) = 0;
  *(_QWORD *)((char *)this + 52) = 0;
  *(_QWORD *)((char *)this + 60) = 0;
  *(_QWORD *)((char *)this + 68) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_DWORD *)this + 26) = 0;
  memset_0(v16, 0, 0x178u);
  memset_0(SystemInformation, 0, 0x40u);
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  v2 = NtQuerySystemInformation(SystemBasicInformation, SystemInformation, 0x40u, 0);
  if ( v2 < 0 )
  {
    v5 = "InitializeLoadMetrics failed! SystemBasicInformation: %lx";
    goto LABEL_5;
  }
  v3 = v13;
  *((_DWORD *)this + 1) = v15;
  *((_DWORD *)this + 3) = v14;
  *((_DWORD *)this + 2) = v3;
  *((_DWORD *)this + 8) = 0xA2400 / v3;
  *((_DWORD *)this + 7) = 1434;
  *((_DWORD *)this + 9) = 0x366400 / v3;
  v4 = NtQuerySystemInformation(SystemPerformanceInformation, v16, 0x178u, 0);
  if ( v4 < 0 )
  {
    _DbgPrintMessage(8, "InitializeLoadMetrics failed! SystemPerformanceInformation: %lx", (unsigned int)v4);
    return this;
  }
  *((_DWORD *)this + 6) = 0x4000000u / *((_DWORD *)this + 2);
  *((_DWORD *)this + 4) = v18;
  *((_DWORD *)this + 5) = v17;
  v2 = NtQuerySystemInformation(SystemProcessorPerformanceInformation, v19, 0x600u, 0);
  if ( v2 < 0 )
  {
    v5 = "InitializeLoadMetrics failed! SystemProcessorPerformanceInformation: %lx";
LABEL_5:
    _DbgPrintMessage(8, v5, (unsigned int)v2);
    return this;
  }
  v7 = 0;
  if ( *((_DWORD *)this + 1) )
  {
    v8 = *((_QWORD *)this + 11);
    v9 = 0;
    v10 = *((_QWORD *)this + 10);
    do
    {
      ++v7;
      v11 = 6 * v9++;
      v8 += v19[v11];
      v10 += v19[v11 + 1] + v19[v11 + 2];
    }
    while ( v7 < *((_DWORD *)this + 1) );
    *((_QWORD *)this + 10) = v10;
    *((_QWORD *)this + 11) = v8;
  }
  *((_DWORD *)this + 18) = 204;
  *((_DWORD *)this + 24) = 0;
  *(_BYTE *)this = 1;
  _DbgPrintMessage(1, "InitializeLoadMetrics():");
  _DbgPrintMessage(
    1,
    "   Processors [%6ld], PageSize  [%6ld], Physical [%6ld]",
    *((_DWORD *)this + 1),
    *((_DWORD *)this + 2),
    *((_DWORD *)this + 3));
  _DbgPrintMessage(
    1,
    "   PtesAvail  [%6ld], PagedUsed [%6ld], Commit   [%6ld]",
    *((_DWORD *)this + 4),
    *((_DWORD *)this + 5),
    *((_DWORD *)this + 6));
  return this;
}

```

## disassembly

```asm
0x18000d2e8  mov     [rsp-8+arg_8], rbx
0x18000d2ed  mov     [rsp-8+arg_10], rsi
0x18000d2f2  push    rbp
0x18000d2f3  lea     rbp, [rsp-700h]
0x18000d2fb  sub     rsp, 800h
0x18000d302  mov     rax, cs:__security_cookie
0x18000d309  xor     rax, rsp
0x18000d30c  mov     [rbp+700h+var_10], rax
0x18000d313  xor     esi, esi
0x18000d315  mov     rbx, rcx
0x18000d318  mov     [rcx], sil
0x18000d31b  xor     edx, edx; Val
0x18000d31d  mov     [rcx+4], rsi
0x18000d321  mov     r8d, 178h; Size
0x18000d327  mov     [rcx+0Ch], rsi
0x18000d32b  mov     [rcx+14h], rsi
0x18000d32f  mov     [rcx+1Ch], rsi
0x18000d333  mov     [rcx+24h], rsi
0x18000d337  mov     [rcx+2Ch], rsi
0x18000d33b  mov     [rcx+34h], rsi
0x18000d33f  mov     [rcx+3Ch], rsi
0x18000d343  mov     [rcx+44h], rsi
0x18000d347  mov     [rcx+60h], rsi
0x18000d34b  mov     [rcx+68h], esi
0x18000d34e  lea     rcx, [rsp+800h+var_790]; void *
0x18000d353  call    memset_0
0x18000d358  xor     edx, edx; Val
0x18000d35a  lea     r8d, [rsi+40h]; Size
0x18000d35e  lea     rcx, [rsp+800h+SystemInformation]; void *
0x18000d363  call    memset_0
0x18000d368  xor     r9d, r9d; ReturnLength
0x18000d36b  mov     [rbx+50h], rsi
0x18000d36f  lea     r8d, [rsi+40h]; SystemInformationLength
0x18000d373  mov     [rbx+58h], rsi
0x18000d377  lea     rdx, [rsp+800h+SystemInformation]; SystemInformation
0x18000d37c  xor     ecx, ecx; SystemInformationClass
0x18000d37e  call    cs:__imp_NtQuerySystemInformation
0x18000d384  test    eax, eax
0x18000d386  js      loc_18000D50A
0x18000d38c  mov     ecx, [rsp+800h+var_7C8]
0x18000d390  xor     edx, edx
0x18000d392  movsx   eax, [rsp+800h+var_798]
0x18000d397  xor     r9d, r9d; ReturnLength
0x18000d39a  mov     [rbx+4], eax
0x18000d39d  mov     r8d, 178h; SystemInformationLength
0x18000d3a3  mov     eax, [rsp+800h+var_7C4]
0x18000d3a7  mov     [rbx+0Ch], eax
0x18000d3aa  mov     eax, 0A2400h
0x18000d3af  div     ecx
0x18000d3b1  xor     edx, edx
0x18000d3b3  mov     [rbx+8], ecx
0x18000d3b6  mov     [rbx+20h], eax
0x18000d3b9  mov     eax, 366400h
0x18000d3be  div     ecx
0x18000d3c0  lea     rdx, [rsp+800h+var_790]; SystemInformation
0x18000d3c5  mov     dword ptr [rbx+1Ch], 59Ah
0x18000d3cc  lea     ecx, [rsi+2]; SystemInformationClass
0x18000d3cf  mov     [rbx+24h], eax
0x18000d3d2  call    cs:__imp_NtQuerySystemInformation
0x18000d3d8  lea     ecx, [rsi+8]; SystemInformationClass
0x18000d3db  test    eax, eax
0x18000d3dd  js      loc_18000D4FE
0x18000d3e3  xor     edx, edx
0x18000d3e5  mov     eax, 4000000h
0x18000d3ea  div     dword ptr [rbx+8]
0x18000d3ed  xor     r9d, r9d; ReturnLength
0x18000d3f0  lea     rdx, [rbp+700h+var_610]; SystemInformation
0x18000d3f7  mov     [rbx+18h], eax
0x18000d3fa  mov     r8d, 600h; SystemInformationLength
0x18000d400  mov     eax, [rbp+700h+var_708]
0x18000d403  mov     [rbx+10h], eax
0x18000d406  mov     eax, [rbp+700h+var_720]
0x18000d409  mov     [rbx+14h], eax
0x18000d40c  call    cs:__imp_NtQuerySystemInformation
0x18000d412  test    eax, eax
0x18000d414  jns     short loc_18000D451
0x18000d416  lea     rdx, aInitializeload_1; "InitializeLoadMetrics failed! SystemPro"...
0x18000d41d  mov     ecx, 8; int
0x18000d422  mov     r8d, eax
0x18000d425  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d42a  mov     rax, rbx
0x18000d42d  mov     rcx, [rbp+700h+var_10]
0x18000d434  xor     rcx, rsp; StackCookie
0x18000d437  call    __security_check_cookie
0x18000d43c  lea     r11, [rsp+800h+var_s0]
0x18000d444  mov     rbx, [r11+18h]
0x18000d448  mov     rsi, [r11+20h]
0x18000d44c  mov     rsp, r11
0x18000d44f  pop     rbp
0x18000d450  retn
0x18000d451  mov     r10d, esi
0x18000d454  cmp     [rbx+4], esi
0x18000d457  jbe     short loc_18000D49B
0x18000d459  mov     rdx, [rbx+58h]
0x18000d45d  mov     r9, rsi
0x18000d460  mov     r8, [rbx+50h]
0x18000d464  lea     rcx, [r9+r9*2]
0x18000d468  inc     r10d
0x18000d46b  shl     rcx, 4
0x18000d46f  inc     r9
0x18000d472  mov     rax, [rbp+rcx+700h+var_600]
0x18000d47a  add     rax, [rbp+rcx+700h+var_608]
0x18000d482  add     rdx, [rbp+rcx+700h+var_610]
0x18000d48a  add     r8, rax
0x18000d48d  cmp     r10d, [rbx+4]
0x18000d491  jb      short loc_18000D464
0x18000d493  mov     [rbx+50h], r8
0x18000d497  mov     [rbx+58h], rdx
0x18000d49b  lea     rdx, aInitializeload; "InitializeLoadMetrics():"
0x18000d4a2  mov     dword ptr [rbx+48h], 0CCh
0x18000d4a9  mov     ecx, 1; int
0x18000d4ae  mov     [rbx+60h], esi
0x18000d4b1  mov     byte ptr [rbx], 1
0x18000d4b4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d4b9  mov     eax, [rbx+0Ch]
0x18000d4bc  lea     rdx, aProcessors6ldP; "   Processors [%6ld], PageSize  [%6ld],"...
0x18000d4c3  mov     r9d, [rbx+8]
0x18000d4c7  mov     ecx, 1; int
0x18000d4cc  mov     r8d, [rbx+4]
0x18000d4d0  mov     [rsp+800h+var_7E0], eax
0x18000d4d4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d4d9  mov     edx, [rbx+18h]
0x18000d4dc  mov     ecx, 1; int
0x18000d4e1  mov     r9d, [rbx+14h]
0x18000d4e5  mov     r8d, [rbx+10h]
0x18000d4e9  mov     [rsp+800h+var_7E0], edx
0x18000d4ed  lea     rdx, aPtesavail6ldPa; "   PtesAvail  [%6ld], PagedUsed [%6ld],"...
0x18000d4f4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000d4f9  jmp     loc_18000D42A
0x18000d4fe  lea     rdx, aInitializeload_0; "InitializeLoadMetrics failed! SystemPer"...
0x18000d505  jmp     loc_18000D422
0x18000d50a  lea     rdx, aInitializeload_2; "InitializeLoadMetrics failed! SystemBas"...
0x18000d511  jmp     loc_18000D41D
```
