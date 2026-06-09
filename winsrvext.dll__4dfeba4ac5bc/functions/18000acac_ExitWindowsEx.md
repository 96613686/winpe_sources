# _ExitWindowsEx

- ea: `0x18000acac`
- end: `0x18000af8d`
- name: `_ExitWindowsEx`
- size: `737`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180008040`

## callees

- `0x180005378`
- `0x180006b7c`
- `0x180007184`
- `0x18000725c`
- `0x180007310`
- `0x18000acac`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000ae40`
- `ntdll!RtlNtStatusToDosError` at `0x18000ae40`
- `ntdll!NtSetEvent` at `0x18000af57`
- `ntdll!NtSetEvent` at `0x18000af57`
- `ntdll!RtlLeaveCriticalSection` at `0x18000ae7e`
- `ntdll!RtlLeaveCriticalSection` at `0x18000af66`
- `ntdll!RtlLeaveCriticalSection` at `0x18000ae7e`
- `ntdll!RtlLeaveCriticalSection` at `0x18000af66`
- `ntdll!RtlEnterCriticalSection` at `0x18000ae66`
- `ntdll!RtlEnterCriticalSection` at `0x18000af38`
- `ntdll!RtlEnterCriticalSection` at `0x18000ae66`
- `ntdll!RtlEnterCriticalSection` at `0x18000af38`
- `ntdll!NtClose` at `0x18000ad94`
- `ntdll!NtClose` at `0x18000ad94`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ae4e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ae4e`
- `CSRSRV!CsrGetProcessLuid` at `0x18000ad34`
- `CSRSRV!CsrGetProcessLuid` at `0x18000ad34`
- `CSRSRV!CsrShutdownProcesses` at `0x18000ae91`
- `CSRSRV!CsrShutdownProcesses` at `0x18000ae91`
- `CSRSRV!CsrImpersonateClient` at `0x18000ad14`
- `CSRSRV!CsrImpersonateClient` at `0x18000ad14`
- `CSRSRV!CsrRevertToSelf` at `0x18000ae11`
- `CSRSRV!CsrRevertToSelf` at `0x18000aefd`
- `CSRSRV!CsrRevertToSelf` at `0x18000ae11`
- `CSRSRV!CsrRevertToSelf` at `0x18000aefd`
- `win32u!NtUserSetInformationThread` at `0x18000adbc`
- `win32u!NtUserSetInformationThread` at `0x18000adf7`
- `win32u!NtUserSetInformationThread` at `0x18000af29`
- `win32u!NtUserSetInformationThread` at `0x18000adbc`
- `win32u!NtUserSetInformationThread` at `0x18000adf7`
- `win32u!NtUserSetInformationThread` at `0x18000af29`
- `USER32!RecordShutdownReason` at `0x18000aed6`
- `USER32!RecordShutdownReason` at `0x18000aed6`
- `USER32!GetSystemMetrics` at `0x18000acf8`
- `USER32!GetSystemMetrics` at `0x18000ad57`
- `USER32!GetSystemMetrics` at `0x18000acf8`
- `USER32!GetSystemMetrics` at `0x18000ad57`

## pseudocode

```c
__int64 __fastcall ExitWindowsEx(__int64 a1, unsigned int a2)
{
  int v3; // eax
  int v4; // ebx
  __int64 result; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rcx
  int DwordKey; // eax
  unsigned int v12; // eax
  DWORD v13; // eax
  unsigned int v14; // eax
  HANDLE Handle; // [rsp+20h] [rbp-30h] BYREF
  __int64 v16; // [rsp+28h] [rbp-28h] BYREF
  _DWORD v17[4]; // [rsp+30h] [rbp-20h] BYREF
  __int64 v18; // [rsp+40h] [rbp-10h]
  __int64 v19; // [rsp+48h] [rbp-8h]
  unsigned int v20; // [rsp+78h] [rbp+28h] BYREF
  unsigned int ProcessLuid; // [rsp+80h] [rbp+30h] BYREF
  int v22; // [rsp+88h] [rbp+38h]

  v20 = a2;
  v16 = 0;
  ProcessLuid = 0;
  RecordPowerTransitionCheckpoint(6);
  v3 = v20;
  if ( (v20 & 0x40000A) != 0 )
  {
    v3 = v20 | 1;
    v20 |= 1u;
  }
  if ( (v3 & 0xC0AB7F80) != 0 )
  {
    v4 = *(_DWORD *)(a1 + 40);
    if ( v4 != GetSystemMetrics(93) )
      return 3221225506LL;
  }
  if ( !(unsigned __int8)CsrImpersonateClient(0) )
    return 3221225637LL;
  ProcessLuid = CsrGetProcessLuid(0, &v16);
  if ( (ProcessLuid & 0x80000000) != 0 )
    goto LABEL_22;
  v8 = 0;
  v22 = 0;
  Handle = 0;
  if ( !GetSystemMetrics(67) && (int)OpenCurrentUserKey(v10, v9, &Handle) >= 0 )
  {
    DwordKey = ReadDwordKey(Handle);
    v8 = v22;
    if ( DwordKey < 0 )
      v8 = 0;
  }
  if ( Handle )
    NtClose(Handle);
  if ( v8 )
    v20 |= 0x40u;
  v12 = NtUserSetInformationThread(*(_QWORD *)(a1 + 64), 5, &v20);
  ProcessLuid = v12;
  if ( v12 == -1073741608 )
    goto LABEL_22;
  v7 = v12;
  v6 = v12;
  while ( (_DWORD)v7 == -1073741267 )
  {
    if ( !(unsigned int)CancelExitWindows(v7, v6) )
    {
      ProcessLuid = 259;
      goto LABEL_22;
    }
    v12 = NtUserSetInformationThread(*(_QWORD *)(a1 + 64), 5, &v20);
    ProcessLuid = v12;
    v7 = v12;
    v6 = v12;
    if ( v12 == -1073741608 )
      goto LABEL_22;
  }
  if ( (_DWORD)v7 == 259 )
    goto LABEL_22;
  if ( (int)v6 < 0 )
  {
    v13 = RtlNtStatusToDosError(v12);
    SetLastError(v13);
LABEL_22:
    CsrRevertToSelf(v7, v6);
    return ProcessLuid;
  }
  RtlEnterCriticalSection(&gcsUserSrv);
  gdwThreadEndSession = *(_DWORD *)(a1 + 48);
  RtlLeaveCriticalSection(&gcsUserSrv);
  v14 = CsrShutdownProcesses(&v16, v20);
  ProcessLuid = v14;
  if ( v14 == -1073741536 )
  {
    v17[1] = v20;
    v18 = 1;
    v17[0] = 32;
    v17[2] = 0;
    v17[3] = 3;
    v19 = 0;
    RecordShutdownReason(v17);
    RecordPowerTransitionCheckpoint(11);
    v14 = ProcessLuid;
  }
  if ( v14 == -2147483622 )
    ProcessLuid = 0;
  ((void (*)(void))CsrRevertToSelf)();
  if ( (v20 & 0x40) != 0 )
    HandlePendingRestartCommands(ProcessLuid);
  NtUserSetInformationThread(*(_QWORD *)(a1 + 64), 6, &ProcessLuid);
  RtlEnterCriticalSection(&gcsUserSrv);
  gdwThreadEndSession = 0;
  NtSetEvent(gheventCancelled, 0);
  RtlLeaveCriticalSection(&gcsUserSrv);
  result = ProcessLuid;
  if ( !ProcessLuid )
  {
    RecordPowerTransitionCheckpoint(6);
    return ProcessLuid;
  }
  return result;
}

```

## disassembly

```asm
0x18000acac  mov     [rsp-18h+arg_8], edx
0x18000acb0  push    rbp
0x18000acb1  push    rbx
0x18000acb2  push    rdi
0x18000acb3  mov     rbp, rsp
0x18000acb6  sub     rsp, 50h
0x18000acba  mov     edx, 1
0x18000acbf  mov     [rbp+var_28], 0
0x18000acc7  mov     rdi, rcx
0x18000acca  mov     [rbp+arg_10], 0
0x18000acd1  lea     ecx, [rdx+5]
0x18000acd4  call    RecordPowerTransitionCheckpoint
0x18000acd9  mov     eax, [rbp+arg_8]
0x18000acdc  test    eax, 40000Ah
0x18000ace1  jz      short loc_18000ACE9
0x18000ace3  or      eax, 1
0x18000ace6  mov     [rbp+arg_8], eax
0x18000ace9  test    eax, 0C0AB7F80h
0x18000acee  jz      short loc_18000AD12
0x18000acf0  mov     ebx, [rdi+28h]
0x18000acf3  mov     ecx, 5Dh ; ']'; nIndex
0x18000acf8  call    cs:__imp_GetSystemMetrics
0x18000acff  nop     dword ptr [rax+rax+00h]
0x18000ad04  cmp     ebx, eax
0x18000ad06  jz      short loc_18000AD12
0x18000ad08  mov     eax, 0C0000022h
0x18000ad0d  jmp     loc_18000AE20
0x18000ad12  xor     ecx, ecx
0x18000ad14  call    cs:__imp_CsrImpersonateClient
0x18000ad1b  nop     dword ptr [rax+rax+00h]
0x18000ad20  test    al, al
0x18000ad22  jnz     short loc_18000AD2E
0x18000ad24  mov     eax, 0C00000A5h
0x18000ad29  jmp     loc_18000AE20
0x18000ad2e  lea     rdx, [rbp+var_28]
0x18000ad32  xor     ecx, ecx
0x18000ad34  call    cs:__imp_CsrGetProcessLuid
0x18000ad3b  nop     dword ptr [rax+rax+00h]
0x18000ad40  mov     [rbp+arg_10], eax
0x18000ad43  test    eax, eax
0x18000ad45  js      loc_18000AE11
0x18000ad4b  xor     ebx, ebx
0x18000ad4d  mov     [rbp+arg_18], ebx
0x18000ad50  mov     [rbp+Handle], rbx
0x18000ad54  lea     ecx, [rbx+43h]; nIndex
0x18000ad57  call    cs:__imp_GetSystemMetrics
0x18000ad5e  nop     dword ptr [rax+rax+00h]
0x18000ad63  test    eax, eax
0x18000ad65  jnz     short loc_18000AD8B
0x18000ad67  lea     r8, [rbp+Handle]
0x18000ad6b  call    OpenCurrentUserKey
0x18000ad70  test    eax, eax
0x18000ad72  js      short loc_18000AD8B
0x18000ad74  mov     rcx, [rbp+Handle]; KeyHandle
0x18000ad78  lea     r8, [rbp+arg_18]
0x18000ad7c  call    ReadDwordKey
0x18000ad81  mov     ebx, [rbp+arg_18]
0x18000ad84  xor     ecx, ecx
0x18000ad86  test    eax, eax
0x18000ad88  cmovs   ebx, ecx
0x18000ad8b  mov     rcx, [rbp+Handle]; Handle
0x18000ad8f  test    rcx, rcx
0x18000ad92  jz      short loc_18000ADA0
0x18000ad94  call    cs:__imp_NtClose
0x18000ad9b  nop     dword ptr [rax+rax+00h]
0x18000ada0  test    ebx, ebx
0x18000ada2  jz      short loc_18000ADA8
0x18000ada4  or      [rbp+arg_8], 40h
0x18000ada8  mov     rcx, [rdi+40h]
0x18000adac  lea     r8, [rbp+arg_8]
0x18000adb0  mov     r9d, 4
0x18000adb6  lea     ebx, [r9+1]
0x18000adba  mov     edx, ebx
0x18000adbc  call    cs:__imp_NtUserSetInformationThread
0x18000adc3  nop     dword ptr [rax+rax+00h]
0x18000adc8  mov     [rbp+arg_10], eax
0x18000adcb  cmp     eax, 0C00000D8h
0x18000add0  jz      short loc_18000AE11
0x18000add2  mov     ecx, eax
0x18000add4  mov     edx, eax
0x18000add6  cmp     ecx, 0C000022Dh
0x18000addc  jnz     short loc_18000AE32
0x18000adde  call    CancelExitWindows
0x18000ade3  test    eax, eax
0x18000ade5  jz      short loc_18000AE29
0x18000ade7  mov     rcx, [rdi+40h]
0x18000adeb  lea     r8, [rbp+arg_8]
0x18000adef  mov     r9d, 4
0x18000adf5  mov     edx, ebx
0x18000adf7  call    cs:__imp_NtUserSetInformationThread
0x18000adfe  nop     dword ptr [rax+rax+00h]
0x18000ae03  mov     [rbp+arg_10], eax
0x18000ae06  mov     ecx, eax
0x18000ae08  mov     edx, eax
0x18000ae0a  cmp     eax, 0C00000D8h
0x18000ae0f  jnz     short loc_18000ADD6
0x18000ae11  call    cs:__imp_CsrRevertToSelf
0x18000ae18  nop     dword ptr [rax+rax+00h]
0x18000ae1d  mov     eax, [rbp+arg_10]
0x18000ae20  add     rsp, 50h
0x18000ae24  pop     rdi
0x18000ae25  pop     rbx
0x18000ae26  pop     rbp
0x18000ae27  retn
0x18000ae29  mov     [rbp+arg_10], 103h
0x18000ae30  jmp     short loc_18000AE11
0x18000ae32  cmp     ecx, 103h
0x18000ae38  jz      short loc_18000AE11
0x18000ae3a  test    edx, edx
0x18000ae3c  jns     short loc_18000AE5C
0x18000ae3e  mov     ecx, eax; Status
0x18000ae40  call    cs:__imp_RtlNtStatusToDosError
0x18000ae47  nop     dword ptr [rax+rax+00h]
0x18000ae4c  mov     ecx, eax; dwErrCode
0x18000ae4e  call    cs:__imp_SetLastError
0x18000ae55  nop     dword ptr [rax+rax+00h]
0x18000ae5a  jmp     short loc_18000AE11
0x18000ae5c  lea     rbx, gcsUserSrv
0x18000ae63  mov     rcx, rbx; CriticalSection
0x18000ae66  call    cs:__imp_RtlEnterCriticalSection
0x18000ae6d  nop     dword ptr [rax+rax+00h]
0x18000ae72  mov     eax, [rdi+30h]
0x18000ae75  mov     rcx, rbx; CriticalSection
0x18000ae78  mov     cs:gdwThreadEndSession, eax
0x18000ae7e  call    cs:__imp_RtlLeaveCriticalSection
0x18000ae85  nop     dword ptr [rax+rax+00h]
0x18000ae8a  mov     edx, [rbp+arg_8]
0x18000ae8d  lea     rcx, [rbp+var_28]
0x18000ae91  call    cs:__imp_CsrShutdownProcesses
0x18000ae98  nop     dword ptr [rax+rax+00h]
0x18000ae9d  mov     [rbp+arg_10], eax
0x18000aea0  cmp     eax, 0C0000120h
0x18000aea5  jnz     short loc_18000AEEF
0x18000aea7  mov     eax, [rbp+arg_8]
0x18000aeaa  lea     rcx, [rbp+var_20]
0x18000aeae  mov     [rbp+var_1C], eax
0x18000aeb1  mov     [rbp+var_10], 1
0x18000aeb9  mov     [rbp+var_20], 20h ; ' '
0x18000aec0  mov     [rbp+var_18], 0
0x18000aec7  mov     [rbp+var_14], 3
0x18000aece  mov     [rbp+var_8], 0
0x18000aed6  call    cs:__imp_RecordShutdownReason
0x18000aedd  nop     dword ptr [rax+rax+00h]
0x18000aee2  xor     edx, edx
0x18000aee4  lea     ecx, [rdx+0Bh]
0x18000aee7  call    RecordPowerTransitionCheckpoint
0x18000aeec  mov     eax, [rbp+arg_10]
0x18000aeef  cmp     eax, 8000001Ah
0x18000aef4  jnz     short loc_18000AEFD
0x18000aef6  mov     [rbp+arg_10], 0
0x18000aefd  call    cs:__imp_CsrRevertToSelf
0x18000af04  nop     dword ptr [rax+rax+00h]
0x18000af09  test    byte ptr [rbp+arg_8], 40h
0x18000af0d  jz      short loc_18000AF17
0x18000af0f  mov     ecx, [rbp+arg_10]
0x18000af12  call    HandlePendingRestartCommands
0x18000af17  mov     rcx, [rdi+40h]
0x18000af1b  lea     r8, [rbp+arg_10]
0x18000af1f  mov     r9d, 4
0x18000af25  lea     edx, [r9+2]
0x18000af29  call    cs:__imp_NtUserSetInformationThread
0x18000af30  nop     dword ptr [rax+rax+00h]
0x18000af35  mov     rcx, rbx; CriticalSection
0x18000af38  call    cs:__imp_RtlEnterCriticalSection
0x18000af3f  nop     dword ptr [rax+rax+00h]
0x18000af44  mov     rcx, cs:gheventCancelled; EventHandle
0x18000af4b  xor     edx, edx; PreviousState
0x18000af4d  mov     cs:gdwThreadEndSession, 0
0x18000af57  call    cs:__imp_NtSetEvent
0x18000af5e  nop     dword ptr [rax+rax+00h]
0x18000af63  mov     rcx, rbx; CriticalSection
0x18000af66  call    cs:__imp_RtlLeaveCriticalSection
0x18000af6d  nop     dword ptr [rax+rax+00h]
0x18000af72  mov     eax, [rbp+arg_10]
0x18000af75  test    eax, eax
0x18000af77  jnz     loc_18000AE20
0x18000af7d  lea     edx, [rax+2]
0x18000af80  lea     ecx, [rax+6]
0x18000af83  call    RecordPowerTransitionCheckpoint
0x18000af88  jmp     loc_18000AE1D
```
