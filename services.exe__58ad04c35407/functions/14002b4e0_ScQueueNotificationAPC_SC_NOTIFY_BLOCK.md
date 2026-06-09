# ScQueueNotificationAPC(_SC_NOTIFY_BLOCK *)

- ea: `0x14002b4e0`
- end: `0x14002b804`
- name: `?ScQueueNotificationAPC@@YAKPEAU_SC_NOTIFY_BLOCK@@@Z`
- size: `804`
- prototype: `unsigned int __fastcall(struct _SC_NOTIFY_BLOCK *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1400044a4`

## callees

- `0x140029228`
- `0x14002b4e0`
- `0x140033670`
- `0x1400813f4`
- `0x140081700`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b526`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b593`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b6a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b526`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b593`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b6a8`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x14002b589`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x14002b589`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002b7e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002b7ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002b7e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002b7ed`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14002b518`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14002b518`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x14002b69e`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x14002b69e`
- `ntdll!NtQueueApcThread` at `0x14002b76a`
- `ntdll!NtQueueApcThread` at `0x14002b76a`
- `ntdll!RtlQueueApcWow64Thread` at `0x14002b70e`
- `ntdll!RtlQueueApcWow64Thread` at `0x14002b70e`
- `ntdll!RtlNtStatusToDosError` at `0x14002b71a`
- `ntdll!RtlNtStatusToDosError` at `0x14002b776`
- `ntdll!RtlNtStatusToDosError` at `0x14002b71a`
- `ntdll!RtlNtStatusToDosError` at `0x14002b776`

## pseudocode

```c
__int64 __fastcall ScQueueNotificationAPC(struct _SC_NOTIFY_BLOCK *a1)
{
  DWORD v1; // r8d
  HANDLE v3; // r12
  DWORD LastError; // ebx
  unsigned int v5; // eax
  HANDLE v6; // rsi
  void *v7; // r14
  void (__stdcall *v8)(PVOID, PVOID, PVOID); // r15
  PRPC_ASYNC_STATE v9; // rcx
  __int64 v10; // rdx
  NTSTATUS v11; // eax
  __int64 v12; // r8
  PRPC_ASYNC_STATE v13; // rcx
  __int64 v14; // rdx
  int v15; // eax
  WINBOOL Wow64Process; // [rsp+80h] [rbp+40h] BYREF
  struct _FILETIME ExitTime; // [rsp+88h] [rbp+48h] BYREF
  struct _FILETIME CreationTime; // [rsp+90h] [rbp+50h] BYREF
  HANDLE ThreadHandle; // [rsp+98h] [rbp+58h] BYREF

  v1 = *((_DWORD *)a1 + 2);
  ThreadHandle = 0;
  CreationTime = 0;
  ExitTime = 0;
  v3 = OpenProcess(0x400u, 0, v1);
  if ( v3 )
  {
    if ( !GetProcessTimes(v3, &CreationTime, &ExitTime, &ExitTime, &ExitTime) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_Dd(WPP_GLOBAL_Control->StubInfo, 75, WPP_1d352e7a0bd43dd98d3d0c2932bfa1b0_Traceguids);
LABEL_40:
      CloseHandle(v3);
      return LastError;
    }
    if ( CreationTime != *((_QWORD *)a1 + 2) )
    {
      LastError = 1067;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_iidd(WPP_GLOBAL_Control->StubInfo);
      goto LABEL_40;
    }
    v5 = ScCheckClientThreadId(*((_DWORD *)a1 + 2), *((_QWORD *)a1 + 3), &ThreadHandle);
    v6 = ThreadHandle;
    LastError = v5;
    if ( v5 )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_Dd(WPP_GLOBAL_Control->StubInfo, 77, WPP_1d352e7a0bd43dd98d3d0c2932bfa1b0_Traceguids);
      goto LABEL_38;
    }
    v7 = *(void **)((char *)a1 + 52);
    v8 = *(void (__stdcall **)(PVOID, PVOID, PVOID))((char *)a1 + 36);
    Wow64Process = 0;
    if ( !IsWow64Process(v3, &Wow64Process) )
    {
      LastError = GetLastError();
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      {
        v10 = 78;
LABEL_21:
        WPP_SF_Dd(v9->StubInfo, v10, WPP_1d352e7a0bd43dd98d3d0c2932bfa1b0_Traceguids);
        goto LABEL_38;
      }
      goto LABEL_38;
    }
    if ( Wow64Process )
    {
      v11 = RtlQueueApcWow64Thread(v6, v8, v7);
      if ( v11 < 0 )
      {
        LastError = RtlNtStatusToDosError(v11);
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          v10 = 79;
          goto LABEL_21;
        }
LABEL_38:
        if ( v6 )
          CloseHandle(v6);
        goto LABEL_40;
      }
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 8) == 0 )
        goto LABEL_38;
      v14 = 80;
    }
    else
    {
      v15 = NtQueueApcThread(v6, v8, v7, 0, 0);
      if ( v15 < 0 )
      {
        LastError = RtlNtStatusToDosError(v15);
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          v10 = 81;
          goto LABEL_21;
        }
        goto LABEL_38;
      }
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 8) == 0 )
        goto LABEL_38;
      v14 = 82;
    }
    WPP_SF_qqqd(v13->StubInfo, v14, v12, v8, v7, v6, *((_DWORD *)a1 + 2));
    goto LABEL_38;
  }
  LastError = GetLastError();
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control->StubInfo, 74, WPP_1d352e7a0bd43dd98d3d0c2932bfa1b0_Traceguids);
  return LastError;
}

```

## disassembly

```asm
0x14002b4e0  push    rbp
0x14002b4e2  push    rbx
0x14002b4e3  push    rsi
0x14002b4e4  push    rdi
0x14002b4e5  push    r12
0x14002b4e7  push    r14
0x14002b4e9  push    r15
0x14002b4eb  mov     rbp, rsp
0x14002b4ee  sub     rsp, 40h
0x14002b4f2  mov     r8d, [rcx+8]; dwProcessId
0x14002b4f6  mov     rdi, rcx
0x14002b4f9  mov     ecx, 400h; dwDesiredAccess
0x14002b4fe  mov     [rbp+ThreadHandle], 0
0x14002b506  xor     edx, edx; bInheritHandle
0x14002b508  mov     qword ptr [rbp+CreationTime.dwLowDateTime], 0
0x14002b510  mov     qword ptr [rbp+ExitTime.dwLowDateTime], 0
0x14002b518  call    cs:__imp_OpenProcess
0x14002b51e  mov     r12, rax
0x14002b521  test    rax, rax
0x14002b524  jnz     short loc_14002B571
0x14002b526  call    cs:__imp_GetLastError
0x14002b52c  mov     ebx, eax
0x14002b52e  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b535  lea     rdx, WPP_GLOBAL_Control
0x14002b53c  cmp     rcx, rdx
0x14002b53f  jz      loc_14002B7F3
0x14002b545  test    byte ptr [rcx+1Ch], 1
0x14002b549  jz      loc_14002B7F3
0x14002b54f  mov     r9d, [rdi+8]
0x14002b553  lea     edx, [r12+4Ah]
0x14002b558  mov     rcx, [rcx+10h]
0x14002b55c  lea     r8, WPP_1d352e7a0bd43dd98d3d0c2932bfa1b0_Traceguids
0x14002b563  mov     dword ptr [rsp+40h+lpUserTime], eax
0x14002b567  call    WPP_SF_Dd
0x14002b56c  jmp     loc_14002B7F3
0x14002b571  lea     rax, [rbp+ExitTime]
0x14002b575  mov     rcx, r12; hProcess
0x14002b578  lea     r9, [rbp+ExitTime]; lpKernelTime
0x14002b57c  mov     [rsp+40h+lpUserTime], rax; lpUserTime
0x14002b581  lea     r8, [rbp+ExitTime]; lpExitTime
0x14002b585  lea     rdx, [rbp+CreationTime]; lpCreationTime
0x14002b589  call    cs:__imp_GetProcessTimes
0x14002b58f  test    eax, eax
0x14002b591  jnz     short loc_14002B5DE
0x14002b593  call    cs:__imp_GetLastError
0x14002b599  mov     ebx, eax
0x14002b59b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b5a2  lea     rdx, WPP_GLOBAL_Control
0x14002b5a9  cmp     rcx, rdx
0x14002b5ac  jz      loc_14002B7EA
0x14002b5b2  test    byte ptr [rcx+1Ch], 1
0x14002b5b6  jz      loc_14002B7EA
0x14002b5bc  mov     r9d, [rdi+8]
0x14002b5c0  lea     r8, WPP_1d352e7a0bd43dd98d3d0c2932bfa1b0_Traceguids
0x14002b5c7  mov     rcx, [rcx+10h]
0x14002b5cb  mov     edx, 4Bh ; 'K'
0x14002b5d0  mov     dword ptr [rsp+40h+lpUserTime], eax
0x14002b5d4  call    WPP_SF_Dd
0x14002b5d9  jmp     loc_14002B7EA
0x14002b5de  mov     r8, [rdi+10h]
0x14002b5e2  mov     r9, qword ptr [rbp+CreationTime.dwLowDateTime]
0x14002b5e6  cmp     r9, r8
0x14002b5e9  jz      short loc_14002B62B
0x14002b5eb  mov     ebx, 42Bh
0x14002b5f0  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b5f7  lea     rdx, WPP_GLOBAL_Control
0x14002b5fe  cmp     rcx, rdx
0x14002b601  jz      loc_14002B7EA
0x14002b607  test    byte ptr [rcx+1Ch], 1
0x14002b60b  jz      loc_14002B7EA
0x14002b611  mov     eax, [rdi+8]
0x14002b614  mov     rcx, [rcx+10h]
0x14002b618  mov     dword ptr [rsp+40h+var_18], eax
0x14002b61c  mov     [rsp+40h+lpUserTime], r8
0x14002b621  call    WPP_SF_iidd
0x14002b626  jmp     loc_14002B7EA
0x14002b62b  mov     rdx, [rdi+18h]; unsigned __int64
0x14002b62f  lea     r8, [rbp+ThreadHandle]; void **
0x14002b633  mov     ecx, [rdi+8]; unsigned int
0x14002b636  call    ?ScCheckClientThreadId@@YAKK_KPEAPEAX@Z; ScCheckClientThreadId(ulong,unsigned __int64,void * *)
0x14002b63b  mov     rsi, [rbp+ThreadHandle]
0x14002b63f  mov     ebx, eax
0x14002b641  test    eax, eax
0x14002b643  jz      short loc_14002B688
0x14002b645  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b64c  lea     rdx, WPP_GLOBAL_Control
0x14002b653  cmp     rcx, rdx
0x14002b656  jz      loc_14002B7DC
0x14002b65c  test    byte ptr [rcx+1Ch], 1
0x14002b660  jz      loc_14002B7DC
0x14002b666  mov     r9d, [rdi+18h]
0x14002b66a  lea     r8, WPP_1d352e7a0bd43dd98d3d0c2932bfa1b0_Traceguids
0x14002b671  mov     rcx, [rcx+10h]
0x14002b675  mov     edx, 4Dh ; 'M'
0x14002b67a  mov     dword ptr [rsp+40h+lpUserTime], eax
0x14002b67e  call    WPP_SF_Dd
0x14002b683  jmp     loc_14002B7DC
0x14002b688  mov     r14, [rdi+34h]
0x14002b68c  lea     rdx, [rbp+Wow64Process]; Wow64Process
0x14002b690  mov     r15, [rdi+24h]
0x14002b694  mov     rcx, r12; hProcess
0x14002b697  mov     [rbp+Wow64Process], 0
0x14002b69e  call    cs:__imp_IsWow64Process
0x14002b6a4  test    eax, eax
0x14002b6a6  jnz     short loc_14002B6F3
0x14002b6a8  call    cs:__imp_GetLastError
0x14002b6ae  mov     ebx, eax
0x14002b6b0  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b6b7  lea     rdx, WPP_GLOBAL_Control
0x14002b6be  cmp     rcx, rdx
0x14002b6c1  jz      loc_14002B7DC
0x14002b6c7  test    byte ptr [rcx+1Ch], 1
0x14002b6cb  jz      loc_14002B7DC
0x14002b6d1  mov     edx, 4Eh ; 'N'
0x14002b6d6  mov     r9d, [rdi+8]
0x14002b6da  lea     r8, WPP_1d352e7a0bd43dd98d3d0c2932bfa1b0_Traceguids
0x14002b6e1  mov     rcx, [rcx+10h]
0x14002b6e5  mov     dword ptr [rsp+40h+lpUserTime], eax
0x14002b6e9  call    WPP_SF_Dd
0x14002b6ee  jmp     loc_14002B7DC
0x14002b6f3  xor     r9d, r9d; SystemArgument1
0x14002b6f6  mov     [rsp+40h+lpUserTime], 0; SystemArgument2
0x14002b6ff  mov     r8, r14; NormalContext
0x14002b702  mov     rdx, r15; ApcRoutine
0x14002b705  mov     rcx, rsi; ThreadHandle
0x14002b708  cmp     [rbp+Wow64Process], r9d
0x14002b70c  jz      short loc_14002B76A
0x14002b70e  call    cs:__imp_RtlQueueApcWow64Thread
0x14002b714  test    eax, eax
0x14002b716  jns     short loc_14002B74A
0x14002b718  mov     ecx, eax; Status
0x14002b71a  call    cs:__imp_RtlNtStatusToDosError
0x14002b720  mov     ebx, eax
0x14002b722  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b729  lea     rdx, WPP_GLOBAL_Control
0x14002b730  cmp     rcx, rdx
0x14002b733  jz      loc_14002B7DC
0x14002b739  test    byte ptr [rcx+1Ch], 1
0x14002b73d  jz      loc_14002B7DC
0x14002b743  mov     edx, 4Fh ; 'O'
0x14002b748  jmp     short loc_14002B6D6
0x14002b74a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b751  lea     rdx, WPP_GLOBAL_Control
0x14002b758  cmp     rcx, rdx
0x14002b75b  jz      short loc_14002B7DC
0x14002b75d  test    byte ptr [rcx+1Ch], 8
0x14002b761  jz      short loc_14002B7DC
0x14002b763  mov     edx, 50h ; 'P'
0x14002b768  jmp     short loc_14002B7BF
0x14002b76a  call    cs:__imp_NtQueueApcThread
0x14002b770  test    eax, eax
0x14002b772  jns     short loc_14002B7A1
0x14002b774  mov     ecx, eax; Status
0x14002b776  call    cs:__imp_RtlNtStatusToDosError
0x14002b77c  mov     ebx, eax
0x14002b77e  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b785  lea     rdx, WPP_GLOBAL_Control
0x14002b78c  cmp     rcx, rdx
0x14002b78f  jz      short loc_14002B7DC
0x14002b791  test    byte ptr [rcx+1Ch], 1
0x14002b795  jz      short loc_14002B7DC
0x14002b797  mov     edx, 51h ; 'Q'
0x14002b79c  jmp     loc_14002B6D6
0x14002b7a1  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b7a8  lea     rdx, WPP_GLOBAL_Control
0x14002b7af  cmp     rcx, rdx
0x14002b7b2  jz      short loc_14002B7DC
0x14002b7b4  test    byte ptr [rcx+1Ch], 8
0x14002b7b8  jz      short loc_14002B7DC
0x14002b7ba  mov     edx, 52h ; 'R'
0x14002b7bf  mov     eax, [rdi+8]
0x14002b7c2  mov     r9, r15
0x14002b7c5  mov     rcx, [rcx+10h]
0x14002b7c9  mov     [rsp+40h+var_10], eax
0x14002b7cd  mov     [rsp+40h+var_18], rsi
0x14002b7d2  mov     [rsp+40h+lpUserTime], r14
0x14002b7d7  call    WPP_SF_qqqd
0x14002b7dc  test    rsi, rsi
0x14002b7df  jz      short loc_14002B7EA
0x14002b7e1  mov     rcx, rsi; hObject
0x14002b7e4  call    cs:__imp_CloseHandle
0x14002b7ea  mov     rcx, r12; hObject
0x14002b7ed  call    cs:__imp_CloseHandle
0x14002b7f3  mov     eax, ebx
0x14002b7f5  add     rsp, 40h
0x14002b7f9  pop     r15
0x14002b7fb  pop     r14
0x14002b7fd  pop     r12
0x14002b7ff  pop     rdi
0x14002b800  pop     rsi
0x14002b801  pop     rbx
0x14002b802  pop     rbp
0x14002b803  retn
```
