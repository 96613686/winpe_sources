# DefaultProcessShutdown

- ea: `0x18000592c`
- end: `0x180005b69`
- name: `DefaultProcessShutdown`
- size: `573`
- prototype: `__int64 __fastcall(unsigned int *, char)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x180009688`

## callees

- `0x18000592c`
- `0x180006d88`
- `0x180006f80`
- `0x1800070ac`
- `0x18000755c`
- `0x18000b9a8`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x180005982`
- `ntdll!NtQueryInformationProcess` at `0x180005982`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180005aa0`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180005aa0`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180005a8d`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180005a8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b3b`
- `BASESRV!BaseGetProcessCrtlRoutine` at `0x1800059a9`
- `BASESRV!BaseGetProcessCrtlRoutine` at `0x1800059a9`
- `CSRSRV!CsrDereferenceProcess` at `0x180005b4a`
- `CSRSRV!CsrDereferenceProcess` at `0x180005b4a`
- `CSRSRV!CsrUnlockProcess` at `0x180005b11`
- `CSRSRV!CsrUnlockProcess` at `0x180005b11`
- `CSRSRV!CsrLockProcessByClientId` at `0x180005ae7`
- `CSRSRV!CsrLockProcessByClientId` at `0x180005ae7`

## pseudocode

```c
__int64 __fastcall DefaultProcessShutdown(unsigned int *a1, char a2)
{
  void *v2; // r15
  __int64 v3; // rsi
  PVOID v6; // rdx
  int v7; // edi
  BOOL v8; // ebx
  void *v9; // r8
  unsigned int v10; // edi
  int v11; // r12d
  __int64 v12; // rdx
  int v13; // eax
  __int64 v14; // rcx
  unsigned int v16; // [rsp+30h] [rbp-20h]
  int v17; // [rsp+34h] [rbp-1Ch]
  HANDLE hThread; // [rsp+38h] [rbp-18h] BYREF
  PVOID Reserved5[2]; // [rsp+40h] [rbp-10h] BYREF
  __int64 ExitCode; // [rsp+90h] [rbp+40h] BYREF
  int ProcessInformation; // [rsp+98h] [rbp+48h] BYREF
  DWORD v22; // [rsp+A0h] [rbp+50h] BYREF
  unsigned int v23; // [rsp+A8h] [rbp+58h]

  v2 = (void *)*((_QWORD *)a1 + 10);
  v3 = *a1;
  hThread = 0;
  v23 = 1;
  ProcessInformation = 0;
  Reserved5[0] = 0;
  if ( NtQueryInformationProcess(v2, ProcessSessionInformation, &ProcessInformation, 4u, 0) < 0
    || ((int)BaseGetProcessCrtlRoutine(a1, Reserved5) >= 0 ? (v6 = Reserved5[0]) : (v6 = 0, Reserved5[0] = 0), !v6) )
  {
    KillProcess(v2);
    goto LABEL_37;
  }
  v7 = a1[31] & 0xC;
  v16 = (a2 & 1) + 5;
  v9 = (void *)v16;
  v17 = v7;
  v8 = v7 == 0;
  LODWORD(v9) = v16 | 0x80000000;
  if ( !v7 )
    v9 = (void *)((a2 & 1u) + 5);
  if ( InternalCreateCallbackThread(v2, v6, v9, &hThread) < 0 )
  {
    if ( v7 )
      goto LABEL_35;
    goto LABEL_11;
  }
  v10 = gCmsWaitToKillTimeout;
  if ( (a2 & 0x20) != 0 && gCmsWaitToKillTimeout > (unsigned int)gCmsQuickAppShutdownTimeout )
    v10 = gCmsQuickAppShutdownTimeout;
  if ( ProcessInformation == gServiceSessionId )
    v10 = gdwServicesWaitToKillTimeout;
  while ( 1 )
  {
    v11 = BoostHardError(v3, 1);
    v12 = v10;
    if ( v11 )
      v12 = 1000;
    v13 = InternalWaitCancel(hThread, v12);
    if ( v13 != 258 )
      break;
    if ( !v11 )
      goto LABEL_29;
  }
  if ( v13 )
  {
    if ( v13 == 1 )
      v23 = 3;
  }
  else
  {
    v22 = 0;
    LODWORD(ExitCode) = 0;
    GetExitCodeThread(hThread, (LPDWORD)&ExitCode);
    GetExitCodeProcess(v2, &v22);
    if ( !v11 && ((_DWORD)ExitCode != v16 || v22 != 259) )
      v8 = 0;
  }
LABEL_29:
  if ( v17 )
    goto LABEL_35;
  ExitCode = 0;
  if ( (int)CsrLockProcessByClientId(v3, &ExitCode) < 0 )
    goto LABEL_35;
  if ( v8 )
    ReportShutdownDelayingProcess((__int64)a1, v10, 0);
  v14 = ExitCode;
  a1[23] |= 0x40u;
  CsrUnlockProcess(v14);
  if ( v8 )
  {
LABEL_11:
    KillProcess(v2);
    goto LABEL_35;
  }
  BoostHardError(v3, 1);
LABEL_35:
  if ( hThread )
    CloseHandle(hThread);
LABEL_37:
  CsrDereferenceProcess(a1);
  return v23;
}

```

## disassembly

```asm
0x18000592c  push    rbp
0x18000592e  push    rbx
0x18000592f  push    rsi
0x180005930  push    rdi
0x180005931  push    r12
0x180005933  push    r14
0x180005935  push    r15
0x180005937  mov     rbp, rsp
0x18000593a  sub     rsp, 50h
0x18000593e  mov     r15, [rcx+50h]
0x180005942  lea     r8, [rbp+ProcessInformation]; ProcessInformation
0x180005946  mov     esi, [rcx]
0x180005948  mov     r9d, 4; ProcessInformationLength
0x18000594e  mov     r12d, edx
0x180005951  mov     [rbp+hThread], 0
0x180005959  mov     r14, rcx
0x18000595c  mov     [rbp+arg_18], 1
0x180005963  mov     rcx, r15; ProcessHandle
0x180005966  mov     [rbp+ProcessInformation], 0
0x18000596d  lea     edx, [r9+14h]; ProcessInformationClass
0x180005971  mov     [rbp+Reserved5], 0
0x180005979  mov     [rsp+50h+ReturnLength], 0; ReturnLength
0x180005982  call    cs:__imp_NtQueryInformationProcess
0x180005989  nop     dword ptr [rax+rax+00h]
0x18000598e  test    eax, eax
0x180005990  jns     short loc_1800059A2
0x180005992  mov     rdx, rsi
0x180005995  mov     rcx, r15; Handle
0x180005998  call    KillProcess
0x18000599d  jmp     loc_180005B47
0x1800059a2  lea     rdx, [rbp+Reserved5]
0x1800059a6  mov     rcx, r14
0x1800059a9  call    cs:__imp_BaseGetProcessCrtlRoutine
0x1800059b0  nop     dword ptr [rax+rax+00h]
0x1800059b5  test    eax, eax
0x1800059b7  jns     short loc_1800059C1
0x1800059b9  xor     edx, edx
0x1800059bb  mov     [rbp+Reserved5], rdx
0x1800059bf  jmp     short loc_1800059C5
0x1800059c1  mov     rdx, [rbp+Reserved5]; Reserved5
0x1800059c5  test    rdx, rdx
0x1800059c8  jz      short loc_180005992
0x1800059ca  mov     edi, [r14+7Ch]
0x1800059ce  lea     r9, [rbp+hThread]
0x1800059d2  mov     ecx, r12d
0x1800059d5  mov     ebx, 0
0x1800059da  and     ecx, 1
0x1800059dd  add     ecx, 5
0x1800059e0  and     edi, 0Ch
0x1800059e3  mov     [rbp+var_20], ecx
0x1800059e6  mov     r8d, ecx
0x1800059e9  mov     [rbp+var_1C], edi
0x1800059ec  setz    bl
0x1800059ef  bts     r8d, 1Fh
0x1800059f4  test    edi, edi
0x1800059f6  cmovz   r8d, ecx; Reserved6
0x1800059fa  mov     rcx, r15; ThreadContext
0x1800059fd  call    InternalCreateCallbackThread
0x180005a02  test    eax, eax
0x180005a04  jns     short loc_180005A1E
0x180005a06  test    edi, edi
0x180005a08  jnz     loc_180005B30
0x180005a0e  mov     rdx, rsi
0x180005a11  mov     rcx, r15; Handle
0x180005a14  call    KillProcess
0x180005a19  jmp     loc_180005B30
0x180005a1e  mov     edi, cs:gCmsWaitToKillTimeout
0x180005a24  test    r12b, 20h
0x180005a28  jz      short loc_180005A37
0x180005a2a  cmp     edi, cs:gCmsQuickAppShutdownTimeout
0x180005a30  cmova   edi, cs:gCmsQuickAppShutdownTimeout
0x180005a37  mov     eax, cs:gServiceSessionId
0x180005a3d  cmp     [rbp+ProcessInformation], eax
0x180005a40  cmovz   edi, cs:gdwServicesWaitToKillTimeout
0x180005a47  mov     edx, 1
0x180005a4c  mov     rcx, rsi
0x180005a4f  call    BoostHardError
0x180005a54  mov     rcx, [rbp+hThread]
0x180005a58  mov     r12d, eax
0x180005a5b  mov     edx, edi
0x180005a5d  mov     eax, 3E8h
0x180005a62  test    r12d, r12d
0x180005a65  cmovnz  edx, eax
0x180005a68  call    InternalWaitCancel
0x180005a6d  cmp     eax, 102h
0x180005a72  jnz     short loc_180005A7B
0x180005a74  test    r12d, r12d
0x180005a77  jnz     short loc_180005A47
0x180005a79  jmp     short loc_180005AD2
0x180005a7b  test    eax, eax
0x180005a7d  jnz     short loc_180005AC6
0x180005a7f  mov     rcx, [rbp+hThread]; hThread
0x180005a83  lea     rdx, [rbp+ExitCode]; lpExitCode
0x180005a87  mov     [rbp+arg_10], eax
0x180005a8a  mov     dword ptr [rbp+ExitCode], eax
0x180005a8d  call    cs:__imp_GetExitCodeThread
0x180005a94  nop     dword ptr [rax+rax+00h]
0x180005a99  lea     rdx, [rbp+arg_10]; lpExitCode
0x180005a9d  mov     rcx, r15; hProcess
0x180005aa0  call    cs:__imp_GetExitCodeProcess
0x180005aa7  nop     dword ptr [rax+rax+00h]
0x180005aac  test    r12d, r12d
0x180005aaf  jnz     short loc_180005AD2
0x180005ab1  mov     eax, [rbp+var_20]
0x180005ab4  cmp     dword ptr [rbp+ExitCode], eax
0x180005ab7  jnz     short loc_180005AC2
0x180005ab9  cmp     [rbp+arg_10], 103h
0x180005ac0  jz      short loc_180005AD2
0x180005ac2  xor     ebx, ebx
0x180005ac4  jmp     short loc_180005AD2
0x180005ac6  cmp     eax, 1
0x180005ac9  jnz     short loc_180005AD2
0x180005acb  mov     [rbp+arg_18], 3
0x180005ad2  cmp     [rbp+var_1C], 0
0x180005ad6  jnz     short loc_180005B30
0x180005ad8  lea     rdx, [rbp+ExitCode]
0x180005adc  mov     [rbp+ExitCode], 0
0x180005ae4  mov     rcx, rsi
0x180005ae7  call    cs:__imp_CsrLockProcessByClientId
0x180005aee  nop     dword ptr [rax+rax+00h]
0x180005af3  test    eax, eax
0x180005af5  js      short loc_180005B30
0x180005af7  test    ebx, ebx
0x180005af9  jz      short loc_180005B08
0x180005afb  xor     r8d, r8d
0x180005afe  mov     edx, edi
0x180005b00  mov     rcx, r14
0x180005b03  call    ReportShutdownDelayingProcess
0x180005b08  mov     rcx, [rbp+ExitCode]
0x180005b0c  or      dword ptr [r14+5Ch], 40h
0x180005b11  call    cs:__imp_CsrUnlockProcess
0x180005b18  nop     dword ptr [rax+rax+00h]
0x180005b1d  test    ebx, ebx
0x180005b1f  jnz     loc_180005A0E
0x180005b25  lea     edx, [rbx+1]
0x180005b28  mov     rcx, rsi
0x180005b2b  call    BoostHardError
0x180005b30  cmp     [rbp+hThread], 0
0x180005b35  jz      short loc_180005B47
0x180005b37  mov     rcx, [rbp+hThread]; hObject
0x180005b3b  call    cs:__imp_CloseHandle
0x180005b42  nop     dword ptr [rax+rax+00h]
0x180005b47  mov     rcx, r14
0x180005b4a  call    cs:__imp_CsrDereferenceProcess
0x180005b51  nop     dword ptr [rax+rax+00h]
0x180005b56  mov     eax, [rbp+arg_18]
0x180005b59  add     rsp, 50h
0x180005b5d  pop     r15
0x180005b5f  pop     r14
0x180005b61  pop     r12
0x180005b63  pop     rdi
0x180005b64  pop     rsi
0x180005b65  pop     rbx
0x180005b66  pop     rbp
0x180005b67  retn
```
