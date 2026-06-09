# CReportManager::SetRecoveryRestartFlagsinReport(void)

- ea: `0x18002ee60`
- end: `0x18002efa4`
- name: `?SetRecoveryRestartFlagsinReport@CReportManager@@AEAAXXZ`
- size: `324`
- prototype: `void __fastcall(CReportManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180034288`

## callees

- `0x18002ee60`
- `0x1800a8c2c`
- `0x1800a9464`
- `0x1800aa12c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002ef67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002ef67`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18002ef59`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18002ef59`
- `api-ms-win-core-windowserrorreporting-l1-1-0!GetApplicationRecoveryCallback` at `0x18002eecd`
- `api-ms-win-core-windowserrorreporting-l1-1-0!GetApplicationRecoveryCallback` at `0x18002eecd`

## pseudocode

```c
void __fastcall CReportManager::SetRecoveryRestartFlagsinReport(CReportManager *this)
{
  __int64 v1; // rbx
  void *v3; // rcx
  unsigned int v4; // edi
  __int64 v5; // rbp
  int v6; // eax
  unsigned int v7; // ecx
  int RestartCommandLine; // eax
  DWORD ProcessId; // ebx
  int v10; // ecx
  unsigned int v11; // [rsp+50h] [rbp+8h] BYREF
  int v12; // [rsp+58h] [rbp+10h] BYREF
  APPLICATION_RECOVERY_CALLBACK pRecoveryCallback; // [rsp+60h] [rbp+18h] BYREF

  v1 = *((_QWORD *)this + 1);
  pRecoveryCallback = 0;
  v12 = 0;
  v11 = 0;
  v3 = *(void **)(v1 + 6640);
  v4 = *(_DWORD *)(v1 + 6616);
  if ( v3 )
  {
    v5 = *(_QWORD *)(*(_QWORD *)this + 16LL);
    if ( (v4 & 1) != 0 && !v5 && (GetApplicationRecoveryCallback(v3, &pRecoveryCallback, 0, 0, 0) || !pRecoveryCallback) )
      v4 &= ~1u;
    if ( (v4 & 2) != 0 )
    {
      v6 = UtilCheckProcessExecutionTimeForRestart(*(HANDLE *)(v1 + 6640));
      v7 = v4 & 0xFFFFFFFD;
      if ( v6 )
        v7 = v4;
      v4 = v7;
      RestartCommandLine = WerpGetRestartCommandLine(*(_QWORD *)(v1 + 6640), 0, &v12, &v11);
      if ( RestartCommandLine != -2147024774 && RestartCommandLine && !v5 )
        v4 &= ~2u;
      if ( !(unsigned int)UtilOkToRestartForFlagsAndType(
                            (enum _WER_REPORT_TYPE)*(_DWORD *)(*((_QWORD *)this + 1) + 5872LL),
                            v11) )
        v4 &= ~2u;
    }
    if ( (v4 & 0x420) == 0 )
    {
      ProcessId = GetProcessId(*(HANDLE *)(v1 + 6640));
      if ( GetCurrentProcessId() == ProcessId && (v4 & 3) != 0 )
        v4 |= 0x20u;
    }
    v10 = v4 | 0x40;
    if ( (v4 & 2) == 0 )
      v10 = v4;
    *(_DWORD *)(*((_QWORD *)this + 1) + 6616LL) = v10;
  }
  else
  {
    *(_DWORD *)(v1 + 6616) = v4 & 0xFFFFFFFC;
  }
}

```

## disassembly

```asm
0x18002ee60  mov     rax, rsp
0x18002ee63  mov     [rax+20h], rbx
0x18002ee67  push    rbp
0x18002ee68  push    rsi
0x18002ee69  push    rdi
0x18002ee6a  sub     rsp, 30h
0x18002ee6e  mov     rbx, [rcx+8]
0x18002ee72  mov     rsi, rcx
0x18002ee75  mov     qword ptr [rax+18h], 0
0x18002ee7d  mov     dword ptr [rax+10h], 0
0x18002ee84  mov     dword ptr [rax+8], 0
0x18002ee8b  mov     rcx, [rbx+19F0h]; hProcess
0x18002ee92  mov     edi, [rbx+19D8h]
0x18002ee98  test    rcx, rcx
0x18002ee9b  jnz     short loc_18002EEAB
0x18002ee9d  and     edi, 0FFFFFFFCh
0x18002eea0  mov     [rbx+19D8h], edi
0x18002eea6  jmp     loc_18002EF96
0x18002eeab  mov     rax, [rsi]
0x18002eeae  mov     rbp, [rax+10h]
0x18002eeb2  test    dil, 1
0x18002eeb6  jz      short loc_18002EEE7
0x18002eeb8  test    rbp, rbp
0x18002eebb  jnz     short loc_18002EEE7
0x18002eebd  xor     r9d, r9d; pdwPingInterval
0x18002eec0  mov     [rsp+48h+pdwFlags], rbp; pdwFlags
0x18002eec5  xor     r8d, r8d; ppvParameter
0x18002eec8  lea     rdx, [rsp+48h+pRecoveryCallback]; pRecoveryCallback
0x18002eecd  call    cs:__imp_GetApplicationRecoveryCallback
0x18002eed4  nop     dword ptr [rax+rax+00h]
0x18002eed9  test    eax, eax
0x18002eedb  jnz     short loc_18002EEE4
0x18002eedd  cmp     [rsp+48h+pRecoveryCallback], rbp
0x18002eee2  jnz     short loc_18002EEE7
0x18002eee4  and     edi, 0FFFFFFFEh
0x18002eee7  test    dil, 2
0x18002eeeb  jz      short loc_18002EF4A
0x18002eeed  mov     rcx, [rbx+19F0h]; hProcess
0x18002eef4  call    ?UtilCheckProcessExecutionTimeForRestart@@YAHPEAX@Z; UtilCheckProcessExecutionTimeForRestart(void *)
0x18002eef9  mov     ecx, edi
0x18002eefb  lea     r9, [rsp+48h+arg_0]
0x18002ef00  and     ecx, 0FFFFFFFDh
0x18002ef03  lea     r8, [rsp+48h+arg_8]
0x18002ef08  test    eax, eax
0x18002ef0a  cmovnz  ecx, edi
0x18002ef0d  xor     edx, edx
0x18002ef0f  mov     edi, ecx
0x18002ef11  mov     rcx, [rbx+19F0h]
0x18002ef18  call    WerpGetRestartCommandLine
0x18002ef1d  cmp     eax, 8007007Ah
0x18002ef22  jz      short loc_18002EF30
0x18002ef24  test    eax, eax
0x18002ef26  jz      short loc_18002EF30
0x18002ef28  test    rbp, rbp
0x18002ef2b  jnz     short loc_18002EF30
0x18002ef2d  and     edi, 0FFFFFFFDh
0x18002ef30  mov     rcx, [rsi+8]
0x18002ef34  mov     edx, [rsp+48h+arg_0]; unsigned int
0x18002ef38  mov     ecx, [rcx+16F0h]; enum _WER_REPORT_TYPE
0x18002ef3e  call    ?UtilOkToRestartForFlagsAndType@@YAHW4_WER_REPORT_TYPE@@K@Z; UtilOkToRestartForFlagsAndType(_WER_REPORT_TYPE,ulong)
0x18002ef43  test    eax, eax
0x18002ef45  jnz     short loc_18002EF4A
0x18002ef47  and     edi, 0FFFFFFFDh
0x18002ef4a  test    edi, 420h
0x18002ef50  jnz     short loc_18002EF80
0x18002ef52  mov     rcx, [rbx+19F0h]; Process
0x18002ef59  call    cs:__imp_GetProcessId
0x18002ef60  nop     dword ptr [rax+rax+00h]
0x18002ef65  mov     ebx, eax
0x18002ef67  call    cs:__imp_GetCurrentProcessId
0x18002ef6e  nop     dword ptr [rax+rax+00h]
0x18002ef73  cmp     eax, ebx
0x18002ef75  jnz     short loc_18002EF80
0x18002ef77  test    dil, 3
0x18002ef7b  jz      short loc_18002EF80
0x18002ef7d  or      edi, 20h
0x18002ef80  mov     rax, [rsi+8]
0x18002ef84  mov     ecx, edi
0x18002ef86  or      ecx, 40h
0x18002ef89  test    dil, 2
0x18002ef8d  cmovz   ecx, edi
0x18002ef90  mov     [rax+19D8h], ecx
0x18002ef96  mov     rbx, [rsp+48h+arg_18]
0x18002ef9b  add     rsp, 30h
0x18002ef9f  pop     rdi
0x18002efa0  pop     rsi
0x18002efa1  pop     rbp
0x18002efa2  retn
```
