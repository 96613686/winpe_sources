# WdcProcessMonitor::OnProcessCommand(unsigned __int64,uint)

- ea: `0x1800281c4`
- end: `0x1800283f9`
- name: `?OnProcessCommand@WdcProcessMonitor@@QEAAJ_KI@Z`
- size: `565`
- prototype: `__int64 __fastcall(WdcProcessMonitor *__hidden this, unsigned __int64, unsigned int)`
- caller_count: `4`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18002d2c8`
- `0x180032f58`
- `0x18007a1fc`
- `0x18007af10`

## callees

- `0x18000b854`
- `0x1800101a0`
- `0x180012420`
- `0x1800150d0`
- `0x180016880`
- `0x180019990`
- `0x18001c9b4`
- `0x1800281c4`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800283d9`
- `KERNEL32!CloseHandle` at `0x1800283d9`
- `KERNEL32!GetLastError` at `0x180028383`
- `KERNEL32!GetLastError` at `0x180028383`
- `KERNEL32!TerminateProcess` at `0x180028379`
- `KERNEL32!TerminateProcess` at `0x180028379`

## string_xrefs

- `0x180028260`: `WdcProcessMonitor::OnProcessCommand`
- `0x180028321`: `WdcProcessMonitor::OnProcessCommand`
- `0x1800283b5`: `WdcProcessMonitor::OnProcessCommand`

## pseudocode

```c
__int64 __fastcall WdcProcessMonitor::OnProcessCommand(WdcProcessMonitor *this, unsigned __int64 a2, int a3)
{
  char *v6; // rsi
  signed int v7; // edi
  int v8; // r15d
  union _LARGE_INTEGER v9; // rbx
  int v10; // eax
  __int64 v11; // rdx
  int v12; // ecx
  unsigned int v13; // r15d
  int v14; // eax
  int v15; // r14d
  int v16; // r14d
  int v17; // ecx
  int v18; // eax
  signed int LastError; // eax
  signed int v21; // [rsp+20h] [rbp-30h]
  void **v22; // [rsp+20h] [rbp-30h]
  HANDLE hProcess; // [rsp+30h] [rbp-20h] BYREF
  struct _WDC_DATA_INFO *v24; // [rsp+38h] [rbp-18h] BYREF
  union _LARGE_INTEGER v25; // [rsp+40h] [rbp-10h]
  int v26; // [rsp+98h] [rbp+48h] BYREF
  unsigned int v27; // [rsp+A8h] [rbp+58h] BYREF

  v26 = 0;
  v24 = 0;
  v25.QuadPart = 0;
  v6 = 0;
  v27 = 0;
  hProcess = 0;
  if ( a2 == 1 )
    return 0;
  v8 = 0;
  WdcLockObject::LockEnter(this, &v26);
  v7 = WdcDataMonitor::InfoFind(this, a2, &v24);
  if ( v7 < 0 )
  {
    v9 = v25;
  }
  else
  {
    v9 = *(union _LARGE_INTEGER *)((char *)v24 + 320);
    v8 = (int)*((double *)v24 + 18);
  }
  WdcLockObject::LockLeave(this, &v26);
  if ( v7 < 0 )
  {
    v21 = v7;
LABEL_8:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\process.cpp",
      "WdcProcessMonitor::OnProcessCommand",
      0,
      L"FAILURE: 0x%08x",
      v21);
    return (unsigned int)v7;
  }
  if ( (a3 != 30400 || v8 == 32213) && (a3 != 30402 || ((v8 - 32210) & 0xFFFFFFFD) != 0) && (a3 != 30403 || v8 != 32211) )
  {
LABEL_39:
    v7 = 0;
    goto LABEL_40;
  }
  v10 = ULongLongToULong(a2, &v27);
  v7 = v10;
  if ( v10 < 0 )
  {
    v21 = v10;
    goto LABEL_8;
  }
  v12 = 0;
  if ( a3 == 30400 )
  {
    v12 = 1;
  }
  else if ( (unsigned int)(a3 - 30402) <= 1 )
  {
    v12 = 2048;
  }
  v13 = v27;
  v14 = WdcSafeOpenProcess(v12, v11, v27, v9, &hProcess);
  v7 = v14;
  if ( v14 < 0 )
  {
    LODWORD(v22) = v14;
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mon\\process.cpp",
      "WdcProcessMonitor::OnProcessCommand",
      0,
      L"FAILURE: 0x%08x",
      v22);
    v6 = (char *)hProcess;
    goto LABEL_40;
  }
  v6 = (char *)hProcess;
  v15 = a3 - 30400;
  if ( !v15 )
  {
    if ( !TerminateProcess(hProcess, 1u) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        if ( v7 >= 0 )
          goto LABEL_40;
      }
      else
      {
        v7 = -2147467259;
      }
      v18 = v7;
LABEL_38:
      LODWORD(v22) = v18;
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mon\\process.cpp",
        "WdcProcessMonitor::OnProcessCommand",
        0,
        L"FAILURE: 0x%08x",
        v22);
      goto LABEL_40;
    }
    goto LABEL_39;
  }
  v16 = v15 - 2;
  if ( v16 )
  {
    if ( v16 != 1 )
      goto LABEL_40;
    v17 = 0;
  }
  else
  {
    v17 = 1;
  }
  v18 = WdcSuspendResumeProcess(v17, v13, v9, hProcess);
  v7 = v18;
  if ( v18 < 0 )
    goto LABEL_38;
LABEL_40:
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800281c4  mov     [rsp-38h+arg_0], rbx
0x1800281c9  push    rbp
0x1800281ca  push    rsi
0x1800281cb  push    rdi
0x1800281cc  push    r12
0x1800281ce  push    r13
0x1800281d0  push    r14
0x1800281d2  push    r15
0x1800281d4  mov     rbp, rsp
0x1800281d7  sub     rsp, 50h
0x1800281db  xor     ebx, ebx
0x1800281dd  mov     r14d, r8d
0x1800281e0  mov     [rbp+arg_8], ebx
0x1800281e3  mov     r13, rdx
0x1800281e6  mov     [rbp+var_18], rbx
0x1800281ea  mov     r12, rcx
0x1800281ed  mov     [rbp+var_10], rbx
0x1800281f1  mov     esi, ebx
0x1800281f3  mov     [rbp+arg_18], ebx
0x1800281f6  mov     [rbp+hProcess], rbx
0x1800281fa  cmp     rdx, 1
0x1800281fe  jnz     short loc_180028207
0x180028200  mov     edi, ebx
0x180028202  jmp     loc_1800283DF
0x180028207  lea     rdx, [rbp+arg_8]; int *
0x18002820b  mov     r15d, ebx
0x18002820e  call    ?LockEnter@WdcLockObject@@QEAAXPEAH@Z; WdcLockObject::LockEnter(int *)
0x180028213  lea     r8, [rbp+var_18]; struct _WDC_DATA_INFO **
0x180028217  mov     rdx, r13; unsigned __int64
0x18002821a  mov     rcx, r12; this
0x18002821d  call    ?InfoFind@WdcDataMonitor@@QEAAJ_KPEAPEAU_WDC_DATA_INFO@@@Z; WdcDataMonitor::InfoFind(unsigned __int64,_WDC_DATA_INFO * *)
0x180028222  mov     edi, eax
0x180028224  test    eax, eax
0x180028226  js      short loc_18002823E
0x180028228  mov     rcx, [rbp+var_18]
0x18002822c  mov     rbx, [rcx+140h]
0x180028233  cvttsd2si r15, qword ptr [rcx+90h]
0x18002823c  jmp     short loc_180028242
0x18002823e  mov     rbx, [rbp+var_10]
0x180028242  lea     rdx, [rbp+arg_8]; int *
0x180028246  mov     rcx, r12; this
0x180028249  call    ?LockLeave@WdcLockObject@@QEAAXPEAH@Z; WdcLockObject::LockLeave(int *)
0x18002824e  test    edi, edi
0x180028250  jns     short loc_180028278
0x180028252  mov     dword ptr [rsp+50h+var_30], edi
0x180028256  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002825d  xor     r8d, r8d; int
0x180028260  lea     rdx, aWdcprocessmoni_0; "WdcProcessMonitor::OnProcessCommand"
0x180028267  lea     rcx, aBaseDiagnosisP_42; "base\\diagnosis\\pdui\\perfmon\\mon\\pr"...
0x18002826e  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180028273  jmp     loc_1800283DF
0x180028278  mov     r12d, 76C0h
0x18002827e  cmp     r14d, r12d
0x180028281  jnz     short loc_18002828C
0x180028283  cmp     r15d, 7DD5h
0x18002828a  jnz     short loc_1800282BD
0x18002828c  cmp     r14d, 76C2h
0x180028293  jnz     short loc_1800282A3
0x180028295  lea     eax, [r15-7DD2h]
0x18002829c  test    eax, 0FFFFFFFDh
0x1800282a1  jz      short loc_1800282BD
0x1800282a3  cmp     r14d, 76C3h
0x1800282aa  jnz     loc_1800283CA
0x1800282b0  cmp     r15d, 7DD3h
0x1800282b7  jnz     loc_1800283CA
0x1800282bd  lea     rdx, [rbp+arg_18]; unsigned int *
0x1800282c1  mov     rcx, r13; unsigned __int64
0x1800282c4  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800282c9  mov     edi, eax
0x1800282cb  test    eax, eax
0x1800282cd  jns     short loc_1800282D5
0x1800282cf  mov     dword ptr [rsp+50h+var_30], eax
0x1800282d3  jmp     short loc_180028256
0x1800282d5  xor     ecx, ecx
0x1800282d7  mov     eax, r14d
0x1800282da  sub     eax, r12d
0x1800282dd  jz      short loc_1800282F0
0x1800282df  sub     eax, 2
0x1800282e2  jz      short loc_1800282E9
0x1800282e4  cmp     eax, 1
0x1800282e7  jnz     short loc_1800282F5
0x1800282e9  mov     ecx, 800h
0x1800282ee  jmp     short loc_1800282F5
0x1800282f0  mov     ecx, 1; unsigned int
0x1800282f5  mov     r15d, [rbp+arg_18]
0x1800282f9  lea     rax, [rbp+hProcess]
0x1800282fd  mov     r8d, r15d; unsigned int
0x180028300  mov     [rsp+50h+var_30], rax; void **
0x180028305  mov     r9, rbx; union _LARGE_INTEGER
0x180028308  call    ?WdcSafeOpenProcess@@YAJKHKT_LARGE_INTEGER@@PEAPEAX@Z; WdcSafeOpenProcess(ulong,int,ulong,_LARGE_INTEGER,void * *)
0x18002830d  mov     edi, eax
0x18002830f  test    eax, eax
0x180028311  jns     short loc_18002833D
0x180028313  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002831a  mov     dword ptr [rsp+50h+var_30], eax
0x18002831e  xor     r8d, r8d; int
0x180028321  lea     rdx, aWdcprocessmoni_0; "WdcProcessMonitor::OnProcessCommand"
0x180028328  lea     rcx, aBaseDiagnosisP_42; "base\\diagnosis\\pdui\\perfmon\\mon\\pr"...
0x18002832f  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180028334  mov     rsi, [rbp+hProcess]
0x180028338  jmp     loc_1800283CC
0x18002833d  mov     rsi, [rbp+hProcess]
0x180028341  sub     r14d, r12d
0x180028344  jz      short loc_180028371
0x180028346  sub     r14d, 2
0x18002834a  jz      short loc_180028356
0x18002834c  cmp     r14d, 1
0x180028350  jnz     short loc_1800283CC
0x180028352  xor     ecx, ecx
0x180028354  jmp     short loc_18002835B
0x180028356  mov     ecx, 1; int
0x18002835b  mov     edx, r15d; unsigned int
0x18002835e  mov     r8, rbx; union _LARGE_INTEGER
0x180028361  mov     r9, rsi; void *
0x180028364  call    ?WdcSuspendResumeProcess@@YAJHKT_LARGE_INTEGER@@PEAX@Z; WdcSuspendResumeProcess(int,ulong,_LARGE_INTEGER,void *)
0x180028369  mov     edi, eax
0x18002836b  test    eax, eax
0x18002836d  jns     short loc_1800283CC
0x18002836f  jmp     short loc_1800283A7
0x180028371  mov     edx, 1; uExitCode
0x180028376  mov     rcx, rsi; hProcess
0x180028379  call    cs:__imp_TerminateProcess
0x18002837f  test    eax, eax
0x180028381  jnz     short loc_1800283CA
0x180028383  call    cs:__imp_GetLastError
0x180028389  mov     edi, eax
0x18002838b  test    eax, eax
0x18002838d  jz      short loc_1800283A0
0x18002838f  jle     short loc_18002839A
0x180028391  movzx   edi, ax
0x180028394  or      edi, 80070000h
0x18002839a  test    edi, edi
0x18002839c  jns     short loc_1800283CC
0x18002839e  jmp     short loc_1800283A5
0x1800283a0  mov     edi, 80004005h
0x1800283a5  mov     eax, edi
0x1800283a7  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x1800283ae  mov     dword ptr [rsp+50h+var_30], eax
0x1800283b2  xor     r8d, r8d; int
0x1800283b5  lea     rdx, aWdcprocessmoni_0; "WdcProcessMonitor::OnProcessCommand"
0x1800283bc  lea     rcx, aBaseDiagnosisP_42; "base\\diagnosis\\pdui\\perfmon\\mon\\pr"...
0x1800283c3  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800283c8  jmp     short loc_1800283CC
0x1800283ca  xor     edi, edi
0x1800283cc  lea     rax, [rsi-1]
0x1800283d0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800283d4  ja      short loc_1800283DF
0x1800283d6  mov     rcx, rsi; hObject
0x1800283d9  call    cs:__imp_CloseHandle
0x1800283df  mov     rbx, [rsp+50h+arg_0]
0x1800283e7  mov     eax, edi
0x1800283e9  add     rsp, 50h
0x1800283ed  pop     r15
0x1800283ef  pop     r14
0x1800283f1  pop     r13
0x1800283f3  pop     r12
0x1800283f5  pop     rdi
0x1800283f6  pop     rsi
0x1800283f7  pop     rbp
0x1800283f8  retn
```
