# CReportManager::SetRecoveryRestartFlagsinReport(void)

- ea: `0x18002d7e0`
- end: `0x18002d911`
- name: `?SetRecoveryRestartFlagsinReport@CReportManager@@AEAAXXZ`
- size: `305`
- prototype: `void __fastcall(CReportManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003285c`

## callees

- `0x18002d7e0`
- `0x1800a3f64`
- `0x1800a473c`
- `0x1800a52f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002d8db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002d8db`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18002d8d3`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18002d8d3`
- `api-ms-win-core-windowserrorreporting-l1-1-0!GetApplicationRecoveryCallback` at `0x18002d84d`
- `api-ms-win-core-windowserrorreporting-l1-1-0!GetApplicationRecoveryCallback` at `0x18002d84d`

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
  signed int RestartCommandLine; // eax
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
      RestartCommandLine = WerpGetRestartCommandLine(*(void **)(v1 + 6640), 0, &v12, &v11);
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
0x18002d7e0  mov     rax, rsp
0x18002d7e3  mov     [rax+20h], rbx
0x18002d7e7  push    rbp
0x18002d7e8  push    rsi
0x18002d7e9  push    rdi
0x18002d7ea  sub     rsp, 30h
0x18002d7ee  mov     rbx, [rcx+8]
0x18002d7f2  mov     rsi, rcx
0x18002d7f5  mov     qword ptr [rax+18h], 0
0x18002d7fd  mov     dword ptr [rax+10h], 0
0x18002d804  mov     dword ptr [rax+8], 0
0x18002d80b  mov     rcx, [rbx+19F0h]; hProcess
0x18002d812  mov     edi, [rbx+19D8h]
0x18002d818  test    rcx, rcx
0x18002d81b  jnz     short loc_18002D82B
0x18002d81d  and     edi, 0FFFFFFFCh
0x18002d820  mov     [rbx+19D8h], edi
0x18002d826  jmp     loc_18002D904
0x18002d82b  mov     rax, [rsi]
0x18002d82e  mov     rbp, [rax+10h]
0x18002d832  test    dil, 1
0x18002d836  jz      short loc_18002D861
0x18002d838  test    rbp, rbp
0x18002d83b  jnz     short loc_18002D861
0x18002d83d  xor     r9d, r9d; pdwPingInterval
0x18002d840  mov     [rsp+48h+pdwFlags], rbp; pdwFlags
0x18002d845  xor     r8d, r8d; ppvParameter
0x18002d848  lea     rdx, [rsp+48h+pRecoveryCallback]; pRecoveryCallback
0x18002d84d  call    cs:__imp_GetApplicationRecoveryCallback
0x18002d853  test    eax, eax
0x18002d855  jnz     short loc_18002D85E
0x18002d857  cmp     [rsp+48h+pRecoveryCallback], rbp
0x18002d85c  jnz     short loc_18002D861
0x18002d85e  and     edi, 0FFFFFFFEh
0x18002d861  test    dil, 2
0x18002d865  jz      short loc_18002D8C4
0x18002d867  mov     rcx, [rbx+19F0h]; hProcess
0x18002d86e  call    ?UtilCheckProcessExecutionTimeForRestart@@YAHPEAX@Z; UtilCheckProcessExecutionTimeForRestart(void *)
0x18002d873  mov     ecx, edi
0x18002d875  lea     r9, [rsp+48h+arg_0]
0x18002d87a  and     ecx, 0FFFFFFFDh
0x18002d87d  lea     r8, [rsp+48h+arg_8]
0x18002d882  test    eax, eax
0x18002d884  cmovnz  ecx, edi
0x18002d887  xor     edx, edx
0x18002d889  mov     edi, ecx
0x18002d88b  mov     rcx, [rbx+19F0h]
0x18002d892  call    WerpGetRestartCommandLine
0x18002d897  cmp     eax, 8007007Ah
0x18002d89c  jz      short loc_18002D8AA
0x18002d89e  test    eax, eax
0x18002d8a0  jz      short loc_18002D8AA
0x18002d8a2  test    rbp, rbp
0x18002d8a5  jnz     short loc_18002D8AA
0x18002d8a7  and     edi, 0FFFFFFFDh
0x18002d8aa  mov     rcx, [rsi+8]
0x18002d8ae  mov     edx, [rsp+48h+arg_0]; unsigned int
0x18002d8b2  mov     ecx, [rcx+16F0h]; enum _WER_REPORT_TYPE
0x18002d8b8  call    ?UtilOkToRestartForFlagsAndType@@YAHW4_WER_REPORT_TYPE@@K@Z; UtilOkToRestartForFlagsAndType(_WER_REPORT_TYPE,ulong)
0x18002d8bd  test    eax, eax
0x18002d8bf  jnz     short loc_18002D8C4
0x18002d8c1  and     edi, 0FFFFFFFDh
0x18002d8c4  test    edi, 420h
0x18002d8ca  jnz     short loc_18002D8EE
0x18002d8cc  mov     rcx, [rbx+19F0h]; Process
0x18002d8d3  call    cs:__imp_GetProcessId
0x18002d8d9  mov     ebx, eax
0x18002d8db  call    cs:__imp_GetCurrentProcessId
0x18002d8e1  cmp     eax, ebx
0x18002d8e3  jnz     short loc_18002D8EE
0x18002d8e5  test    dil, 3
0x18002d8e9  jz      short loc_18002D8EE
0x18002d8eb  or      edi, 20h
0x18002d8ee  mov     rax, [rsi+8]
0x18002d8f2  mov     ecx, edi
0x18002d8f4  or      ecx, 40h
0x18002d8f7  test    dil, 2
0x18002d8fb  cmovz   ecx, edi
0x18002d8fe  mov     [rax+19D8h], ecx
0x18002d904  mov     rbx, [rsp+48h+arg_18]
0x18002d909  add     rsp, 30h
0x18002d90d  pop     rdi
0x18002d90e  pop     rsi
0x18002d90f  pop     rbp
0x18002d910  retn
```
