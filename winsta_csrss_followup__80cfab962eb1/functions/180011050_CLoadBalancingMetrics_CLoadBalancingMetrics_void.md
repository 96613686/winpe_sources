# CLoadBalancingMetrics::CLoadBalancingMetrics(void)

- ea: `0x180011050`
- end: `0x180011291`
- name: `??0CLoadBalancingMetrics@@QEAA@XZ`
- size: `577`
- prototype: `CLoadBalancingMetrics *__fastcall(CLoadBalancingMetrics *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800096c0`

## callees

- `0x180005b40`
- `0x180011050`
- `0x180032be6`
- `0x180032c20`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x1800110e6`
- `ntdll!NtQuerySystemInformation` at `0x180011140`
- `ntdll!NtQuerySystemInformation` at `0x180011180`
- `ntdll!NtQuerySystemInformation` at `0x1800110e6`
- `ntdll!NtQuerySystemInformation` at `0x180011140`
- `ntdll!NtQuerySystemInformation` at `0x180011180`

## string_xrefs

- `0x180011190`: `InitializeLoadMetrics failed! SystemProcessorPerformanceInformation: %lx`
- `0x180011268`: `   PtesAvail  [%6ld], PagedUsed [%6ld], Commit   [%6ld]`
- `0x180011279`: `InitializeLoadMetrics failed! SystemPerformanceInformation: %lx`

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
0x180011050  mov     [rsp-8+arg_8], rbx
0x180011055  mov     [rsp-8+arg_10], rsi
0x18001105a  push    rbp
0x18001105b  lea     rbp, [rsp-700h]
0x180011063  sub     rsp, 800h
0x18001106a  mov     rax, cs:__security_cookie
0x180011071  xor     rax, rsp
0x180011074  mov     [rbp+700h+var_10], rax
0x18001107b  xor     esi, esi
0x18001107d  mov     rbx, rcx
0x180011080  mov     [rcx], sil
0x180011083  xor     edx, edx; Val
0x180011085  mov     [rcx+4], rsi
0x180011089  mov     r8d, 178h; Size
0x18001108f  mov     [rcx+0Ch], rsi
0x180011093  mov     [rcx+14h], rsi
0x180011097  mov     [rcx+1Ch], rsi
0x18001109b  mov     [rcx+24h], rsi
0x18001109f  mov     [rcx+2Ch], rsi
0x1800110a3  mov     [rcx+34h], rsi
0x1800110a7  mov     [rcx+3Ch], rsi
0x1800110ab  mov     [rcx+44h], rsi
0x1800110af  mov     [rcx+60h], rsi
0x1800110b3  mov     [rcx+68h], esi
0x1800110b6  lea     rcx, [rsp+800h+var_790]; void *
0x1800110bb  call    memset_0
0x1800110c0  xor     edx, edx; Val
0x1800110c2  lea     r8d, [rsi+40h]; Size
0x1800110c6  lea     rcx, [rsp+800h+SystemInformation]; void *
0x1800110cb  call    memset_0
0x1800110d0  xor     r9d, r9d; ReturnLength
0x1800110d3  mov     [rbx+50h], rsi
0x1800110d7  lea     r8d, [rsi+40h]; SystemInformationLength
0x1800110db  mov     [rbx+58h], rsi
0x1800110df  lea     rdx, [rsp+800h+SystemInformation]; SystemInformation
0x1800110e4  xor     ecx, ecx; SystemInformationClass
0x1800110e6  call    cs:__imp_NtQuerySystemInformation
0x1800110ed  nop     dword ptr [rax+rax+00h]
0x1800110f2  test    eax, eax
0x1800110f4  js      loc_180011285
0x1800110fa  mov     ecx, [rsp+800h+var_7C8]
0x1800110fe  xor     edx, edx
0x180011100  movsx   eax, [rsp+800h+var_798]
0x180011105  xor     r9d, r9d; ReturnLength
0x180011108  mov     [rbx+4], eax
0x18001110b  mov     r8d, 178h; SystemInformationLength
0x180011111  mov     eax, [rsp+800h+var_7C4]
0x180011115  mov     [rbx+0Ch], eax
0x180011118  mov     eax, 0A2400h
0x18001111d  div     ecx
0x18001111f  xor     edx, edx
0x180011121  mov     [rbx+8], ecx
0x180011124  mov     [rbx+20h], eax
0x180011127  mov     eax, 366400h
0x18001112c  div     ecx
0x18001112e  lea     rdx, [rsp+800h+var_790]; SystemInformation
0x180011133  mov     dword ptr [rbx+1Ch], 59Ah
0x18001113a  lea     ecx, [rsi+2]; SystemInformationClass
0x18001113d  mov     [rbx+24h], eax
0x180011140  call    cs:__imp_NtQuerySystemInformation
0x180011147  nop     dword ptr [rax+rax+00h]
0x18001114c  lea     ecx, [rsi+8]; SystemInformationClass
0x18001114f  test    eax, eax
0x180011151  js      loc_180011279
0x180011157  xor     edx, edx
0x180011159  mov     eax, 4000000h
0x18001115e  div     dword ptr [rbx+8]
0x180011161  xor     r9d, r9d; ReturnLength
0x180011164  lea     rdx, [rbp+700h+var_610]; SystemInformation
0x18001116b  mov     [rbx+18h], eax
0x18001116e  mov     r8d, 600h; SystemInformationLength
0x180011174  mov     eax, [rbp+700h+var_708]
0x180011177  mov     [rbx+10h], eax
0x18001117a  mov     eax, [rbp+700h+var_720]
0x18001117d  mov     [rbx+14h], eax
0x180011180  call    cs:__imp_NtQuerySystemInformation
0x180011187  nop     dword ptr [rax+rax+00h]
0x18001118c  test    eax, eax
0x18001118e  jns     short loc_1800111CC
0x180011190  lea     rdx, aInitializeload_1; "InitializeLoadMetrics failed! SystemPro"...
0x180011197  mov     ecx, 8; int
0x18001119c  mov     r8d, eax
0x18001119f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800111a4  mov     rax, rbx
0x1800111a7  mov     rcx, [rbp+700h+var_10]
0x1800111ae  xor     rcx, rsp; StackCookie
0x1800111b1  call    __security_check_cookie
0x1800111b6  lea     r11, [rsp+800h+var_s0]
0x1800111be  mov     rbx, [r11+18h]
0x1800111c2  mov     rsi, [r11+20h]
0x1800111c6  mov     rsp, r11
0x1800111c9  pop     rbp
0x1800111ca  retn
0x1800111cc  mov     r10d, esi
0x1800111cf  cmp     [rbx+4], esi
0x1800111d2  jbe     short loc_180011216
0x1800111d4  mov     rdx, [rbx+58h]
0x1800111d8  mov     r9, rsi
0x1800111db  mov     r8, [rbx+50h]
0x1800111df  lea     rcx, [r9+r9*2]
0x1800111e3  inc     r10d
0x1800111e6  shl     rcx, 4
0x1800111ea  inc     r9
0x1800111ed  mov     rax, [rbp+rcx+700h+var_600]
0x1800111f5  add     rax, [rbp+rcx+700h+var_608]
0x1800111fd  add     rdx, [rbp+rcx+700h+var_610]
0x180011205  add     r8, rax
0x180011208  cmp     r10d, [rbx+4]
0x18001120c  jb      short loc_1800111DF
0x18001120e  mov     [rbx+50h], r8
0x180011212  mov     [rbx+58h], rdx
0x180011216  lea     rdx, aInitializeload; "InitializeLoadMetrics():"
0x18001121d  mov     dword ptr [rbx+48h], 0CCh
0x180011224  mov     ecx, 1; int
0x180011229  mov     [rbx+60h], esi
0x18001122c  mov     byte ptr [rbx], 1
0x18001122f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180011234  mov     eax, [rbx+0Ch]
0x180011237  lea     rdx, aProcessors6ldP; "   Processors [%6ld], PageSize  [%6ld],"...
0x18001123e  mov     r9d, [rbx+8]
0x180011242  mov     ecx, 1; int
0x180011247  mov     r8d, [rbx+4]
0x18001124b  mov     [rsp+800h+var_7E0], eax
0x18001124f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180011254  mov     edx, [rbx+18h]
0x180011257  mov     ecx, 1; int
0x18001125c  mov     r9d, [rbx+14h]
0x180011260  mov     r8d, [rbx+10h]
0x180011264  mov     [rsp+800h+var_7E0], edx
0x180011268  lea     rdx, aPtesavail6ldPa; "   PtesAvail  [%6ld], PagedUsed [%6ld],"...
0x18001126f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180011274  jmp     loc_1800111A4
0x180011279  lea     rdx, aInitializeload_0; "InitializeLoadMetrics failed! SystemPer"...
0x180011280  jmp     loc_18001119C
0x180011285  lea     rdx, aInitializeload_2; "InitializeLoadMetrics failed! SystemBas"...
0x18001128c  jmp     loc_180011197
```
