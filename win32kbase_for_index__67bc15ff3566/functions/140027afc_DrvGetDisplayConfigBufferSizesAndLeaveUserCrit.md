# DrvGetDisplayConfigBufferSizesAndLeaveUserCrit

- ea: `0x140027afc`
- end: `0x140027d27`
- name: `DrvGetDisplayConfigBufferSizesAndLeaveUserCrit`
- size: `555`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140071180`

## callees

- `0x140027810`
- `0x140027afc`
- `0x140027d30`
- `0x140029710`
- `0x140031fa0`
- `0x140033390`
- `0x1400371c0`
- `0x1400a0ad0`
- `0x1400a3120`
- `0x140192b70`
- `0x1402389c0`

## import_xrefs

- `ntoskrnl!PsGetThreadWin32Thread` at `0x140027bfc`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x140027bfc`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140027c5b`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140027c5b`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140027c4c`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140027c4c`
- `ntoskrnl!KeIsAttachedProcess` at `0x140027be9`
- `ntoskrnl!KeIsAttachedProcess` at `0x140027be9`
- `watchdog!WdLogSingleEntry1` at `0x140027b6a`
- `watchdog!WdLogSingleEntry1` at `0x140027bb3`
- `watchdog!WdLogSingleEntry1` at `0x140027b6a`
- `watchdog!WdLogSingleEntry1` at `0x140027bb3`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x140027b8f`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x140027b8f`
- `WIN32K!W32GetSessionState` at `0x140027b23`
- `WIN32K!W32GetSessionState` at `0x140027b23`

## pseudocode

```c
__int64 __fastcall DrvGetDisplayConfigBufferSizesAndLeaveUserCrit(__int64 a1, unsigned int *a2)
{
  __int64 v2; // rbx
  bool v4; // di
  __int64 v5; // rcx
  int v6; // r8d
  _DWORD *v7; // r14
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 DxgkWin32kInterface; // rax
  int v12; // esi
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // r8d
  __int64 v16; // rbp
  struct _KTHREAD *CurrentThread; // r14
  __int64 v18; // rdi
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 *ThreadWin32Thread; // rax
  __int64 v23; // rax
  __int64 v24; // rdi
  int CurrentWin32kSessionId; // ebx
  __int64 CurrentThreadProcess; // rax
  int DisplayConfig; // eax
  bool v30; // [rsp+28h] [rbp-40h]

  v2 = (unsigned int)a1;
  v4 = (a1 & 7) != 4 || (unsigned int)DispBrokerGetCurrentMode() != 3 && (unsigned int)DispBrokerGetCurrentMode() != 2;
  v7 = *(_DWORD **)(W32GetSessionState(a1) + 88);
  if ( v4 )
  {
    if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
      McTemplateK0pz_EtwWriteTransfer(v5, (unsigned int)LockAcquireShared, v6, *v7 + 624, (__int64)L"DynamicModeChange");
    EngAcquireSemaphoreShared((HSEMAPHORE)(*(_QWORD *)v7 + 624LL));
    GrepAcquireLockValidate<1>();
  }
  UserSessionSwitchLeaveCritWithNonPaged(v5);
  WdLogSingleEntry1(4, v2);
  WdLogGlobalForLineNumber = 11959;
  if ( (unsigned __int8)DrvIsQdcHandledByDispBroker((unsigned int)v2) )
  {
    if ( (unsigned int)DispBrokerGetCurrentMode() == 3 )
    {
      DisplayConfig = DispBrokerQueryDisplayConfig(v2 & 0xFFFFFFEF, v2 & 0x10, a2, 0, 0, v30);
      v12 = 0;
      if ( DisplayConfig != -1073741789 )
        v12 = DisplayConfig;
    }
    else
    {
      v12 = -1073741790;
    }
  }
  else
  {
    DxgkWin32kInterface = DxDdGetDxgkWin32kInterface(v9, v8, v10);
    v12 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(DxgkWin32kInterface + 208))((unsigned int)v2, a2);
  }
  WdLogSingleEntry1(4, v12);
  WdLogGlobalForLineNumber = 11990;
  if ( v4 )
  {
    v16 = *(_QWORD *)v7;
    if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
      McTemplateK0pz_EtwWriteTransfer(v14, (unsigned int)LockRelease, v15, v16 + 624, (__int64)L"DynamicModeChange");
    CurrentThread = KeGetCurrentThread();
    v18 = 0;
    if ( !(unsigned __int8)KeIsAttachedProcess(v14, v13)
      || (CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(v20, v19, v21),
          CurrentThreadProcess = PsGetCurrentThreadProcess(),
          CurrentWin32kSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
    {
      ThreadWin32Thread = (__int64 *)PsGetThreadWin32Thread(CurrentThread);
      if ( ThreadWin32Thread )
        v18 = *ThreadWin32Thread;
    }
    v23 = v18 + 8;
    v24 = -v18;
    if ( (v23 & -(__int64)(v24 != 0)) != 0 && (*(_BYTE *)((v23 & -(__int64)(v24 != 0)) + 9))-- == 1 )
      *(_QWORD *)(v23 & -(__int64)(v24 != 0)) &= ~2uLL;
    GreReleaseSemaphoreSharedInternal((HSEMAPHORE)(v16 + 624));
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140027afc  push    rbx
0x140027afe  push    rbp
0x140027aff  push    rsi
0x140027b00  push    rdi
0x140027b01  push    r13
0x140027b03  push    r14
0x140027b05  sub     rsp, 38h
0x140027b09  mov     eax, ecx
0x140027b0b  mov     ebx, ecx
0x140027b0d  and     al, 7
0x140027b0f  mov     ebp, 4
0x140027b14  mov     rsi, rdx
0x140027b17  cmp     al, bpl
0x140027b1a  jz      loc_140027C6D
0x140027b20  mov     dil, 1
0x140027b23  call    cs:__imp_W32GetSessionState
0x140027b2a  nop     dword ptr [rax+rax+00h]
0x140027b2f  lea     r13, aDynamicmodecha; "DynamicModeChange"
0x140027b36  mov     r14, [rax+58h]
0x140027b3a  test    dil, dil
0x140027b3d  jz      short loc_140027B60
0x140027b3f  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, 0
0x140027b46  jnz     loc_140027C8F
0x140027b4c  mov     rcx, [r14]
0x140027b4f  add     rcx, 270h; hsem
0x140027b56  call    EngAcquireSemaphoreShared
0x140027b5b  call    ??$GrepAcquireLockValidate@$00@@YAXXZ; GrepAcquireLockValidate<1>(void)
0x140027b60  call    UserSessionSwitchLeaveCritWithNonPaged
0x140027b65  mov     rdx, rbx
0x140027b68  mov     ecx, ebp
0x140027b6a  call    cs:__imp_WdLogSingleEntry1
0x140027b71  nop     dword ptr [rax+rax+00h]
0x140027b76  mov     ecx, ebx
0x140027b78  mov     cs:WdLogGlobalForLineNumber, 2EB7h
0x140027b82  call    DrvIsQdcHandledByDispBroker
0x140027b87  test    al, al
0x140027b89  jnz     loc_140027CBC
0x140027b8f  call    cs:__imp_DxDdGetDxgkWin32kInterface
0x140027b96  nop     dword ptr [rax+rax+00h]
0x140027b9b  mov     rdx, rsi
0x140027b9e  mov     ecx, ebx
0x140027ba0  mov     rax, [rax+0D0h]
0x140027ba7  call    _guard_dispatch_icall
0x140027bac  mov     esi, eax
0x140027bae  movsxd  rdx, esi
0x140027bb1  mov     ecx, ebp
0x140027bb3  call    cs:__imp_WdLogSingleEntry1
0x140027bba  nop     dword ptr [rax+rax+00h]
0x140027bbf  mov     cs:WdLogGlobalForLineNumber, 2ED6h
0x140027bc9  test    dil, dil
0x140027bcc  jz      short loc_140027C35
0x140027bce  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, 0
0x140027bd5  mov     rbp, [r14]
0x140027bd8  jnz     loc_140027CFD
0x140027bde  mov     r14, gs:188h
0x140027be7  xor     edi, edi
0x140027be9  call    cs:__imp_KeIsAttachedProcess
0x140027bf0  nop     dword ptr [rax+rax+00h]
0x140027bf5  test    al, al
0x140027bf7  jnz     short loc_140027C45
0x140027bf9  mov     rcx, r14
0x140027bfc  call    cs:__imp_PsGetThreadWin32Thread
0x140027c03  nop     dword ptr [rax+rax+00h]
0x140027c08  test    rax, rax
0x140027c0b  jz      short loc_140027C10
0x140027c0d  mov     rdi, [rax]
0x140027c10  lea     rax, [rdi+8]
0x140027c14  neg     rdi
0x140027c17  sbb     rdx, rdx
0x140027c1a  and     rdx, rax
0x140027c1d  jz      short loc_140027C29
0x140027c1f  add     byte ptr [rdx+9], 0FFh
0x140027c23  jnz     short loc_140027C29
0x140027c25  and     qword ptr [rdx], 0FFFFFFFFFFFFFFFDh
0x140027c29  lea     rcx, [rbp+270h]; HSEMAPHORE
0x140027c30  call    ?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x140027c35  mov     eax, esi
0x140027c37  add     rsp, 38h
0x140027c3b  pop     r14
0x140027c3d  pop     r13
0x140027c3f  pop     rdi
0x140027c40  pop     rsi
0x140027c41  pop     rbp
0x140027c42  pop     rbx
0x140027c43  retn
0x140027c45  call    W32GetCurrentWin32kSessionId
0x140027c4a  mov     ebx, eax
0x140027c4c  call    cs:__imp_PsGetCurrentThreadProcess
0x140027c53  nop     dword ptr [rax+rax+00h]
0x140027c58  mov     rcx, rax
0x140027c5b  call    cs:__imp_PsGetProcessSessionIdEx
0x140027c62  nop     dword ptr [rax+rax+00h]
0x140027c67  cmp     ebx, eax
0x140027c69  jz      short loc_140027BF9
0x140027c6b  jmp     short loc_140027C10
0x140027c6d  call    DispBrokerGetCurrentMode
0x140027c72  cmp     eax, 3
0x140027c75  jnz     short loc_140027C7F
0x140027c77  xor     dil, dil
0x140027c7a  jmp     loc_140027B23
0x140027c7f  call    DispBrokerGetCurrentMode
0x140027c84  cmp     eax, 2
0x140027c87  jnz     loc_140027B20
0x140027c8d  jmp     short loc_140027C77
0x140027c8f  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits, 10h
0x140027c96  jz      loc_140027B4C
0x140027c9c  mov     r9, [r14]
0x140027c9f  lea     rdx, LockAcquireShared
0x140027ca6  add     r9, 270h
0x140027cad  mov     [rsp+68h+var_48], r13
0x140027cb2  call    McTemplateK0pz_EtwWriteTransfer
0x140027cb7  jmp     loc_140027B4C
0x140027cbc  call    DispBrokerGetCurrentMode
0x140027cc1  cmp     eax, 3
0x140027cc4  jnz     short loc_140027CF3
0x140027cc6  mov     edx, ebx
0x140027cc8  mov     [rsp+68h+var_48], 0; enum DISPLAYCONFIG_TOPOLOGY_ID *
0x140027cd1  and     ebx, 0FFFFFFEFh
0x140027cd4  and     edx, 10h; unsigned int
0x140027cd7  mov     ecx, ebx; unsigned int
0x140027cd9  xor     r9d, r9d; struct DISPLAYCONFIG_PATH_INFO_INTERNAL *
0x140027cdc  mov     r8, rsi; unsigned int *
0x140027cdf  call    ?DispBrokerQueryDisplayConfig@@YAJIIPEAIPEAUDISPLAYCONFIG_PATH_INFO_INTERNAL@@PEAW4DISPLAYCONFIG_TOPOLOGY_ID@@_N@Z; DispBrokerQueryDisplayConfig(uint,uint,uint *,DISPLAYCONFIG_PATH_INFO_INTERNAL *,DISPLAYCONFIG_TOPOLOGY_ID *,bool)
0x140027ce4  xor     esi, esi
0x140027ce6  cmp     eax, 0C0000023h
0x140027ceb  cmovnz  esi, eax
0x140027cee  jmp     loc_140027BAE
0x140027cf3  mov     esi, 0C0000022h
0x140027cf8  jmp     loc_140027BAE
0x140027cfd  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits, 10h
0x140027d04  jz      loc_140027BDE
0x140027d0a  lea     r9, [rbp+270h]
0x140027d11  mov     [rsp+68h+var_48], r13
0x140027d16  lea     rdx, LockRelease
0x140027d1d  call    McTemplateK0pz_EtwWriteTransfer
0x140027d22  jmp     loc_140027BDE
```
