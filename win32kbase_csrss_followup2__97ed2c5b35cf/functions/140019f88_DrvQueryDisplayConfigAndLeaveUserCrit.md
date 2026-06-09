# DrvQueryDisplayConfigAndLeaveUserCrit

- ea: `0x140019f88`
- end: `0x14001a1dc`
- name: `DrvQueryDisplayConfigAndLeaveUserCrit`
- size: `596`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400337a0`

## callees

- `0x140019ef8`
- `0x140019f88`
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

- `ntoskrnl!PsGetThreadWin32Thread` at `0x14001a09e`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x14001a09e`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14001a0fd`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14001a0fd`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14001a0ee`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14001a0ee`
- `ntoskrnl!KeIsAttachedProcess` at `0x14001a08b`
- `ntoskrnl!KeIsAttachedProcess` at `0x14001a08b`
- `watchdog!WdLogSingleEntry1` at `0x140019ff9`
- `watchdog!WdLogSingleEntry1` at `0x14001a055`
- `watchdog!WdLogSingleEntry1` at `0x140019ff9`
- `watchdog!WdLogSingleEntry1` at `0x14001a055`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x14001a01e`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x14001a01e`
- `WIN32K!W32GetSessionState` at `0x140019faf`
- `WIN32K!W32GetSessionState` at `0x140019faf`

## pseudocode

```c
__int64 __fastcall DrvQueryDisplayConfigAndLeaveUserCrit(
        __int64 a1,
        unsigned int *a2,
        struct DISPLAYCONFIG_PATH_INFO_INTERNAL *a3,
        enum DISPLAYCONFIG_TOPOLOGY_ID *a4)
{
  __int64 v4; // rbx
  bool v8; // di
  __int64 SessionState; // rax
  int v10; // r8d
  const wchar_t *v11; // rcx
  _DWORD *v12; // r14
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 DxgkWin32kInterface; // rax
  int v17; // esi
  int v18; // ecx
  int v19; // r8d
  __int64 v20; // rbp
  struct _KTHREAD *CurrentThread; // r14
  __int64 v22; // rdi
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 *ThreadWin32Thread; // rax
  __int64 v27; // rax
  __int64 v28; // rdi
  int CurrentWin32kSessionId; // ebx
  __int64 CurrentThreadProcess; // rax
  bool v33; // [rsp+28h] [rbp-40h]
  unsigned int v34; // [rsp+70h] [rbp+8h] BYREF

  v4 = (unsigned int)a1;
  v8 = (a1 & 7) != 4 || (unsigned int)DispBrokerGetCurrentMode() != 3 && (unsigned int)DispBrokerGetCurrentMode() != 2;
  SessionState = W32GetSessionState(a1);
  v11 = L"DynamicModeChange";
  v12 = *(_DWORD **)(SessionState + 88);
  if ( v8 )
  {
    if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
      McTemplateK0pz_EtwWriteTransfer(
        (unsigned int)L"DynamicModeChange",
        (unsigned int)LockAcquireShared,
        v10,
        *v12 + 624,
        (__int64)L"DynamicModeChange");
    EngAcquireSemaphoreShared((HSEMAPHORE)(*(_QWORD *)v12 + 624LL));
    GrepAcquireLockValidate<1>();
  }
  UserSessionSwitchLeaveCritWithNonPaged(v11);
  WdLogSingleEntry1(4, v4);
  WdLogGlobalForLineNumber = 12036;
  if ( (unsigned __int8)DrvIsQdcHandledByDispBroker((unsigned int)v4) )
  {
    if ( (unsigned int)DispBrokerGetCurrentMode() == 3 )
    {
      v34 = *a2;
      v17 = DispBrokerQueryDisplayConfig(v4 & 0xFFFFFFEF, v4 & 0x10, &v34, a3, a4, v33);
      if ( v17 >= 0 )
        *a2 = v34;
    }
    else
    {
      v17 = -1073741790;
    }
  }
  else
  {
    DxgkWin32kInterface = DxDdGetDxgkWin32kInterface(v14, v13, v15);
    v17 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned int *, struct DISPLAYCONFIG_PATH_INFO_INTERNAL *, enum DISPLAYCONFIG_TOPOLOGY_ID *))(DxgkWin32kInterface + 216))(
            (unsigned int)v4 & 0xFFFFFFEF,
            v4 & 0x10,
            a2,
            a3,
            a4);
  }
  WdLogSingleEntry1(4, v17);
  WdLogGlobalForLineNumber = 12073;
  if ( v8 )
  {
    v20 = *(_QWORD *)v12;
    if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
      McTemplateK0pz_EtwWriteTransfer(v18, (unsigned int)LockRelease, v19, v20 + 624, (__int64)L"DynamicModeChange");
    CurrentThread = KeGetCurrentThread();
    v22 = 0;
    if ( !(unsigned __int8)KeIsAttachedProcess()
      || (CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(v24, v23, v25),
          CurrentThreadProcess = PsGetCurrentThreadProcess(),
          CurrentWin32kSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
    {
      ThreadWin32Thread = (__int64 *)PsGetThreadWin32Thread(CurrentThread);
      if ( ThreadWin32Thread )
        v22 = *ThreadWin32Thread;
    }
    v27 = v22 + 8;
    v28 = -v22;
    if ( (v27 & -(__int64)(v28 != 0)) != 0 && (*(_BYTE *)((v27 & -(__int64)(v28 != 0)) + 9))-- == 1 )
      *(_QWORD *)(v27 & -(__int64)(v28 != 0)) &= ~2uLL;
    GreReleaseSemaphoreSharedInternal((HSEMAPHORE)(v20 + 624));
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x140019f88  push    rbx
0x140019f8a  push    rbp
0x140019f8b  push    rsi
0x140019f8c  push    rdi
0x140019f8d  push    r14
0x140019f8f  push    r15
0x140019f91  sub     rsp, 38h
0x140019f95  mov     eax, ecx
0x140019f97  mov     ebx, ecx
0x140019f99  and     al, 7
0x140019f9b  mov     rsi, r9
0x140019f9e  mov     rbp, r8
0x140019fa1  mov     r15, rdx
0x140019fa4  cmp     al, 4
0x140019fa6  jz      loc_14001A10F
0x140019fac  mov     dil, 1
0x140019faf  call    cs:__imp_W32GetSessionState
0x140019fb6  nop     dword ptr [rax+rax+00h]
0x140019fbb  lea     rcx, aDynamicmodecha; "DynamicModeChange"
0x140019fc2  mov     r14, [rax+58h]
0x140019fc6  test    dil, dil
0x140019fc9  jz      short loc_140019FEC
0x140019fcb  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, 0
0x140019fd2  jnz     loc_14001A131
0x140019fd8  mov     rcx, [r14]
0x140019fdb  add     rcx, 270h; hsem
0x140019fe2  call    EngAcquireSemaphoreShared
0x140019fe7  call    ??$GrepAcquireLockValidate@$00@@YAXXZ; GrepAcquireLockValidate<1>(void)
0x140019fec  call    UserSessionSwitchLeaveCritWithNonPaged
0x140019ff1  mov     rdx, rbx
0x140019ff4  mov     ecx, 4
0x140019ff9  call    cs:__imp_WdLogSingleEntry1
0x14001a000  nop     dword ptr [rax+rax+00h]
0x14001a005  mov     ecx, ebx
0x14001a007  mov     cs:WdLogGlobalForLineNumber, 2F04h
0x14001a011  call    DrvIsQdcHandledByDispBroker
0x14001a016  test    al, al
0x14001a018  jnz     loc_14001A15E
0x14001a01e  call    cs:__imp_DxDdGetDxgkWin32kInterface
0x14001a025  nop     dword ptr [rax+rax+00h]
0x14001a02a  mov     edx, ebx
0x14001a02c  mov     [rsp+68h+var_48], rsi
0x14001a031  and     ebx, 0FFFFFFEFh
0x14001a034  and     edx, 10h
0x14001a037  mov     r9, rbp
0x14001a03a  mov     r8, r15
0x14001a03d  mov     rax, [rax+0D8h]
0x14001a044  mov     ecx, ebx
0x14001a046  call    _guard_dispatch_icall
0x14001a04b  mov     esi, eax
0x14001a04d  movsxd  rdx, esi
0x14001a050  mov     ecx, 4
0x14001a055  call    cs:__imp_WdLogSingleEntry1
0x14001a05c  nop     dword ptr [rax+rax+00h]
0x14001a061  mov     cs:WdLogGlobalForLineNumber, 2F29h
0x14001a06b  test    dil, dil
0x14001a06e  jz      short loc_14001A0D7
0x14001a070  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, 0
0x14001a077  mov     rbp, [r14]
0x14001a07a  jnz     loc_14001A1AB
0x14001a080  mov     r14, gs:188h
0x14001a089  xor     edi, edi
0x14001a08b  call    cs:__imp_KeIsAttachedProcess
0x14001a092  nop     dword ptr [rax+rax+00h]
0x14001a097  test    al, al
0x14001a099  jnz     short loc_14001A0E7
0x14001a09b  mov     rcx, r14
0x14001a09e  call    cs:__imp_PsGetThreadWin32Thread
0x14001a0a5  nop     dword ptr [rax+rax+00h]
0x14001a0aa  test    rax, rax
0x14001a0ad  jz      short loc_14001A0B2
0x14001a0af  mov     rdi, [rax]
0x14001a0b2  lea     rax, [rdi+8]
0x14001a0b6  neg     rdi
0x14001a0b9  sbb     rdx, rdx
0x14001a0bc  and     rdx, rax
0x14001a0bf  jz      short loc_14001A0CB
0x14001a0c1  add     byte ptr [rdx+9], 0FFh
0x14001a0c5  jnz     short loc_14001A0CB
0x14001a0c7  and     qword ptr [rdx], 0FFFFFFFFFFFFFFFDh
0x14001a0cb  lea     rcx, [rbp+270h]; HSEMAPHORE
0x14001a0d2  call    ?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x14001a0d7  mov     eax, esi
0x14001a0d9  add     rsp, 38h
0x14001a0dd  pop     r15
0x14001a0df  pop     r14
0x14001a0e1  pop     rdi
0x14001a0e2  pop     rsi
0x14001a0e3  pop     rbp
0x14001a0e4  pop     rbx
0x14001a0e5  retn
0x14001a0e7  call    W32GetCurrentWin32kSessionId
0x14001a0ec  mov     ebx, eax
0x14001a0ee  call    cs:__imp_PsGetCurrentThreadProcess
0x14001a0f5  nop     dword ptr [rax+rax+00h]
0x14001a0fa  mov     rcx, rax
0x14001a0fd  call    cs:__imp_PsGetProcessSessionIdEx
0x14001a104  nop     dword ptr [rax+rax+00h]
0x14001a109  cmp     ebx, eax
0x14001a10b  jz      short loc_14001A09B
0x14001a10d  jmp     short loc_14001A0B2
0x14001a10f  call    DispBrokerGetCurrentMode
0x14001a114  cmp     eax, 3
0x14001a117  jnz     short loc_14001A121
0x14001a119  xor     dil, dil
0x14001a11c  jmp     loc_140019FAF
0x14001a121  call    DispBrokerGetCurrentMode
0x14001a126  cmp     eax, 2
0x14001a129  jnz     loc_140019FAC
0x14001a12f  jmp     short loc_14001A119
0x14001a131  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits, 10h
0x14001a138  jz      loc_140019FD8
0x14001a13e  mov     r9, [r14]
0x14001a141  lea     rdx, LockAcquireShared
0x14001a148  add     r9, 270h
0x14001a14f  mov     [rsp+68h+var_48], rcx
0x14001a154  call    McTemplateK0pz_EtwWriteTransfer
0x14001a159  jmp     loc_140019FD8
0x14001a15e  call    DispBrokerGetCurrentMode
0x14001a163  cmp     eax, 3
0x14001a166  jnz     short loc_14001A1A1
0x14001a168  mov     eax, [r15]
0x14001a16b  lea     r8, [rsp+68h+arg_0]; unsigned int *
0x14001a170  mov     edx, ebx
0x14001a172  mov     [rsp+68h+arg_0], eax
0x14001a176  and     ebx, 0FFFFFFEFh
0x14001a179  mov     [rsp+68h+var_48], rsi; enum DISPLAYCONFIG_TOPOLOGY_ID *
0x14001a17e  mov     ecx, ebx; unsigned int
0x14001a180  and     edx, 10h; unsigned int
0x14001a183  mov     r9, rbp; struct DISPLAYCONFIG_PATH_INFO_INTERNAL *
0x14001a186  call    ?DispBrokerQueryDisplayConfig@@YAJIIPEAIPEAUDISPLAYCONFIG_PATH_INFO_INTERNAL@@PEAW4DISPLAYCONFIG_TOPOLOGY_ID@@_N@Z; DispBrokerQueryDisplayConfig(uint,uint,uint *,DISPLAYCONFIG_PATH_INFO_INTERNAL *,DISPLAYCONFIG_TOPOLOGY_ID *,bool)
0x14001a18b  mov     esi, eax
0x14001a18d  test    eax, eax
0x14001a18f  js      loc_14001A04D
0x14001a195  mov     ecx, [rsp+68h+arg_0]
0x14001a199  mov     [r15], ecx
0x14001a19c  jmp     loc_14001A04D
0x14001a1a1  mov     esi, 0C0000022h
0x14001a1a6  jmp     loc_14001A04D
0x14001a1ab  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits, 10h
0x14001a1b2  jz      loc_14001A080
0x14001a1b8  lea     rax, aDynamicmodecha; "DynamicModeChange"
0x14001a1bf  lea     r9, [rbp+270h]
0x14001a1c6  mov     [rsp+68h+var_48], rax
0x14001a1cb  lea     rdx, LockRelease
0x14001a1d2  call    McTemplateK0pz_EtwWriteTransfer
0x14001a1d7  jmp     loc_14001A080
```
