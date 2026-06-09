# DrvGetDisplayConfigBufferSizesAndLeaveUserCrit

- ea: `0x14001a1e4`
- end: `0x14001a40f`
- name: `DrvGetDisplayConfigBufferSizesAndLeaveUserCrit`
- size: `555`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140034ad0`

## callees

- `0x140019ef8`
- `0x14001a1e4`
- `0x14001a418`
- `0x14001bdf0`
- `0x14001d160`
- `0x140025b90`
- `0x140031bf4`
- `0x1400af49c`
- `0x140117d40`
- `0x140190760`
- `0x140238240`

## import_xrefs

- `ntoskrnl!PsGetThreadWin32Thread` at `0x14001a2e4`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x14001a2e4`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14001a343`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14001a343`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14001a334`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14001a334`
- `ntoskrnl!KeIsAttachedProcess` at `0x14001a2d1`
- `ntoskrnl!KeIsAttachedProcess` at `0x14001a2d1`
- `watchdog!WdLogSingleEntry1` at `0x14001a252`
- `watchdog!WdLogSingleEntry1` at `0x14001a29b`
- `watchdog!WdLogSingleEntry1` at `0x14001a252`
- `watchdog!WdLogSingleEntry1` at `0x14001a29b`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x14001a277`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x14001a277`
- `WIN32K!W32GetSessionState` at `0x14001a20b`
- `WIN32K!W32GetSessionState` at `0x14001a20b`

## pseudocode

```c
__int64 __fastcall DrvGetDisplayConfigBufferSizesAndLeaveUserCrit(__int64 a1, unsigned int *a2)
{
  __int64 v2; // rbx
  bool v4; // di
  int v5; // ecx
  int v6; // r8d
  _DWORD *v7; // r14
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 DxgkWin32kInterface; // rax
  int v12; // esi
  int v13; // ecx
  int v14; // r8d
  __int64 v15; // rbp
  struct _KTHREAD *CurrentThread; // r14
  __int64 v17; // rdi
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 *ThreadWin32Thread; // rax
  __int64 v22; // rax
  __int64 v23; // rdi
  int CurrentWin32kSessionId; // ebx
  __int64 CurrentThreadProcess; // rax
  int DisplayConfig; // eax
  bool v29; // [rsp+28h] [rbp-40h]

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
  UserSessionSwitchLeaveCritWithNonPaged();
  WdLogSingleEntry1(4, v2);
  WdLogGlobalForLineNumber = 11959;
  if ( (unsigned __int8)DrvIsQdcHandledByDispBroker((unsigned int)v2) )
  {
    if ( (unsigned int)DispBrokerGetCurrentMode() == 3 )
    {
      DisplayConfig = DispBrokerQueryDisplayConfig(v2 & 0xFFFFFFEF, v2 & 0x10, a2, 0, 0, v29);
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
    v15 = *(_QWORD *)v7;
    if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
      McTemplateK0pz_EtwWriteTransfer(v13, (unsigned int)LockRelease, v14, v15 + 624, (__int64)L"DynamicModeChange");
    CurrentThread = KeGetCurrentThread();
    v17 = 0;
    if ( !(unsigned __int8)KeIsAttachedProcess()
      || (CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(v19, v18, v20),
          CurrentThreadProcess = PsGetCurrentThreadProcess(),
          CurrentWin32kSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
    {
      ThreadWin32Thread = (__int64 *)PsGetThreadWin32Thread(CurrentThread);
      if ( ThreadWin32Thread )
        v17 = *ThreadWin32Thread;
    }
    v22 = v17 + 8;
    v23 = -v17;
    if ( (v22 & -(__int64)(v23 != 0)) != 0 && (*(_BYTE *)((v22 & -(__int64)(v23 != 0)) + 9))-- == 1 )
      *(_QWORD *)(v22 & -(__int64)(v23 != 0)) &= ~2uLL;
    GreReleaseSemaphoreSharedInternal((HSEMAPHORE)(v15 + 624));
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14001a1e4  push    rbx
0x14001a1e6  push    rbp
0x14001a1e7  push    rsi
0x14001a1e8  push    rdi
0x14001a1e9  push    r13
0x14001a1eb  push    r14
0x14001a1ed  sub     rsp, 38h
0x14001a1f1  mov     eax, ecx
0x14001a1f3  mov     ebx, ecx
0x14001a1f5  and     al, 7
0x14001a1f7  mov     ebp, 4
0x14001a1fc  mov     rsi, rdx
0x14001a1ff  cmp     al, bpl
0x14001a202  jz      loc_14001A355
0x14001a208  mov     dil, 1
0x14001a20b  call    cs:__imp_W32GetSessionState
0x14001a212  nop     dword ptr [rax+rax+00h]
0x14001a217  lea     r13, aDynamicmodecha; "DynamicModeChange"
0x14001a21e  mov     r14, [rax+58h]
0x14001a222  test    dil, dil
0x14001a225  jz      short loc_14001A248
0x14001a227  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, 0
0x14001a22e  jnz     loc_14001A377
0x14001a234  mov     rcx, [r14]
0x14001a237  add     rcx, 270h; hsem
0x14001a23e  call    EngAcquireSemaphoreShared
0x14001a243  call    ??$GrepAcquireLockValidate@$00@@YAXXZ; GrepAcquireLockValidate<1>(void)
0x14001a248  call    UserSessionSwitchLeaveCritWithNonPaged
0x14001a24d  mov     rdx, rbx
0x14001a250  mov     ecx, ebp
0x14001a252  call    cs:__imp_WdLogSingleEntry1
0x14001a259  nop     dword ptr [rax+rax+00h]
0x14001a25e  mov     ecx, ebx
0x14001a260  mov     cs:WdLogGlobalForLineNumber, 2EB7h
0x14001a26a  call    DrvIsQdcHandledByDispBroker
0x14001a26f  test    al, al
0x14001a271  jnz     loc_14001A3A4
0x14001a277  call    cs:__imp_DxDdGetDxgkWin32kInterface
0x14001a27e  nop     dword ptr [rax+rax+00h]
0x14001a283  mov     rdx, rsi
0x14001a286  mov     ecx, ebx
0x14001a288  mov     rax, [rax+0D0h]
0x14001a28f  call    _guard_dispatch_icall
0x14001a294  mov     esi, eax
0x14001a296  movsxd  rdx, esi
0x14001a299  mov     ecx, ebp
0x14001a29b  call    cs:__imp_WdLogSingleEntry1
0x14001a2a2  nop     dword ptr [rax+rax+00h]
0x14001a2a7  mov     cs:WdLogGlobalForLineNumber, 2ED6h
0x14001a2b1  test    dil, dil
0x14001a2b4  jz      short loc_14001A31D
0x14001a2b6  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, 0
0x14001a2bd  mov     rbp, [r14]
0x14001a2c0  jnz     loc_14001A3E5
0x14001a2c6  mov     r14, gs:188h
0x14001a2cf  xor     edi, edi
0x14001a2d1  call    cs:__imp_KeIsAttachedProcess
0x14001a2d8  nop     dword ptr [rax+rax+00h]
0x14001a2dd  test    al, al
0x14001a2df  jnz     short loc_14001A32D
0x14001a2e1  mov     rcx, r14
0x14001a2e4  call    cs:__imp_PsGetThreadWin32Thread
0x14001a2eb  nop     dword ptr [rax+rax+00h]
0x14001a2f0  test    rax, rax
0x14001a2f3  jz      short loc_14001A2F8
0x14001a2f5  mov     rdi, [rax]
0x14001a2f8  lea     rax, [rdi+8]
0x14001a2fc  neg     rdi
0x14001a2ff  sbb     rdx, rdx
0x14001a302  and     rdx, rax
0x14001a305  jz      short loc_14001A311
0x14001a307  add     byte ptr [rdx+9], 0FFh
0x14001a30b  jnz     short loc_14001A311
0x14001a30d  and     qword ptr [rdx], 0FFFFFFFFFFFFFFFDh
0x14001a311  lea     rcx, [rbp+270h]; HSEMAPHORE
0x14001a318  call    ?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x14001a31d  mov     eax, esi
0x14001a31f  add     rsp, 38h
0x14001a323  pop     r14
0x14001a325  pop     r13
0x14001a327  pop     rdi
0x14001a328  pop     rsi
0x14001a329  pop     rbp
0x14001a32a  pop     rbx
0x14001a32b  retn
0x14001a32d  call    W32GetCurrentWin32kSessionId
0x14001a332  mov     ebx, eax
0x14001a334  call    cs:__imp_PsGetCurrentThreadProcess
0x14001a33b  nop     dword ptr [rax+rax+00h]
0x14001a340  mov     rcx, rax
0x14001a343  call    cs:__imp_PsGetProcessSessionIdEx
0x14001a34a  nop     dword ptr [rax+rax+00h]
0x14001a34f  cmp     ebx, eax
0x14001a351  jz      short loc_14001A2E1
0x14001a353  jmp     short loc_14001A2F8
0x14001a355  call    DispBrokerGetCurrentMode
0x14001a35a  cmp     eax, 3
0x14001a35d  jnz     short loc_14001A367
0x14001a35f  xor     dil, dil
0x14001a362  jmp     loc_14001A20B
0x14001a367  call    DispBrokerGetCurrentMode
0x14001a36c  cmp     eax, 2
0x14001a36f  jnz     loc_14001A208
0x14001a375  jmp     short loc_14001A35F
0x14001a377  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits, 10h
0x14001a37e  jz      loc_14001A234
0x14001a384  mov     r9, [r14]
0x14001a387  lea     rdx, LockAcquireShared
0x14001a38e  add     r9, 270h
0x14001a395  mov     [rsp+68h+var_48], r13
0x14001a39a  call    McTemplateK0pz_EtwWriteTransfer
0x14001a39f  jmp     loc_14001A234
0x14001a3a4  call    DispBrokerGetCurrentMode
0x14001a3a9  cmp     eax, 3
0x14001a3ac  jnz     short loc_14001A3DB
0x14001a3ae  mov     edx, ebx
0x14001a3b0  mov     [rsp+68h+var_48], 0; enum DISPLAYCONFIG_TOPOLOGY_ID *
0x14001a3b9  and     ebx, 0FFFFFFEFh
0x14001a3bc  and     edx, 10h; unsigned int
0x14001a3bf  mov     ecx, ebx; unsigned int
0x14001a3c1  xor     r9d, r9d; struct DISPLAYCONFIG_PATH_INFO_INTERNAL *
0x14001a3c4  mov     r8, rsi; unsigned int *
0x14001a3c7  call    ?DispBrokerQueryDisplayConfig@@YAJIIPEAIPEAUDISPLAYCONFIG_PATH_INFO_INTERNAL@@PEAW4DISPLAYCONFIG_TOPOLOGY_ID@@_N@Z; DispBrokerQueryDisplayConfig(uint,uint,uint *,DISPLAYCONFIG_PATH_INFO_INTERNAL *,DISPLAYCONFIG_TOPOLOGY_ID *,bool)
0x14001a3cc  xor     esi, esi
0x14001a3ce  cmp     eax, 0C0000023h
0x14001a3d3  cmovnz  esi, eax
0x14001a3d6  jmp     loc_14001A296
0x14001a3db  mov     esi, 0C0000022h
0x14001a3e0  jmp     loc_14001A296
0x14001a3e5  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits, 10h
0x14001a3ec  jz      loc_14001A2C6
0x14001a3f2  lea     r9, [rbp+270h]
0x14001a3f9  mov     [rsp+68h+var_48], r13
0x14001a3fe  lea     rdx, LockRelease
0x14001a405  call    McTemplateK0pz_EtwWriteTransfer
0x14001a40a  jmp     loc_14001A2C6
```
