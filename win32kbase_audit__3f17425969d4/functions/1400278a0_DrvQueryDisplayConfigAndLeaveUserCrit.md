# DrvQueryDisplayConfigAndLeaveUserCrit

- ea: `0x1400278a0`
- end: `0x140027af4`
- name: `DrvQueryDisplayConfigAndLeaveUserCrit`
- size: `596`
- prototype: `__int64 __fastcall(__int64, unsigned int *, struct DISPLAYCONFIG_PATH_INFO_INTERNAL *, enum DISPLAYCONFIG_TOPOLOGY_ID *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14006e420`

## callees

- `0x140027810`
- `0x1400278a0`
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

- `ntoskrnl!PsGetThreadWin32Thread` at `0x1400279b6`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x1400279b6`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140027a15`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140027a15`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140027a06`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140027a06`
- `ntoskrnl!KeIsAttachedProcess` at `0x1400279a3`
- `ntoskrnl!KeIsAttachedProcess` at `0x1400279a3`
- `watchdog!WdLogSingleEntry1` at `0x140027911`
- `watchdog!WdLogSingleEntry1` at `0x14002796d`
- `watchdog!WdLogSingleEntry1` at `0x140027911`
- `watchdog!WdLogSingleEntry1` at `0x14002796d`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x140027936`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x140027936`
- `WIN32K!W32GetSessionState` at `0x1400278c7`
- `WIN32K!W32GetSessionState` at `0x1400278c7`

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
  __int64 v13; // rcx
  __int64 DxgkWin32kInterface; // rax
  int v15; // esi
  int v16; // ecx
  int v17; // r8d
  __int64 v18; // rbp
  struct _KTHREAD *CurrentThread; // r14
  __int64 v20; // rdi
  __int64 *ThreadWin32Thread; // rax
  __int64 v22; // rax
  __int64 v23; // rdi
  int CurrentWin32kSessionId; // ebx
  __int64 CurrentThreadProcess; // rax
  unsigned int v28; // [rsp+70h] [rbp+8h] BYREF

  v4 = (unsigned int)a1;
  v8 = (a1 & 7) != 4 || (unsigned int)DispBrokerGetCurrentMode() != 3 && (unsigned int)DispBrokerGetCurrentMode() != 2;
  SessionState = W32GetSessionState(a1, a2, a3, a4);
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
      v28 = *a2;
      v15 = DispBrokerQueryDisplayConfig((unsigned int)v4 & 0xFFFFFFEF, v4 & 0x10, &v28, a3, a4);
      if ( v15 >= 0 )
        *a2 = v28;
    }
    else
    {
      v15 = -1073741790;
    }
  }
  else
  {
    DxgkWin32kInterface = DxDdGetDxgkWin32kInterface(v13);
    v15 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned int *, struct DISPLAYCONFIG_PATH_INFO_INTERNAL *, enum DISPLAYCONFIG_TOPOLOGY_ID *))(DxgkWin32kInterface + 216))(
            (unsigned int)v4 & 0xFFFFFFEF,
            v4 & 0x10,
            a2,
            a3,
            a4);
  }
  WdLogSingleEntry1(4, v15);
  WdLogGlobalForLineNumber = 12073;
  if ( v8 )
  {
    v18 = *(_QWORD *)v12;
    if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
      McTemplateK0pz_EtwWriteTransfer(v16, (unsigned int)LockRelease, v17, v18 + 624, (__int64)L"DynamicModeChange");
    CurrentThread = KeGetCurrentThread();
    v20 = 0;
    if ( !(unsigned __int8)KeIsAttachedProcess()
      || (CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(),
          CurrentThreadProcess = PsGetCurrentThreadProcess(),
          CurrentWin32kSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
    {
      ThreadWin32Thread = (__int64 *)PsGetThreadWin32Thread(CurrentThread);
      if ( ThreadWin32Thread )
        v20 = *ThreadWin32Thread;
    }
    v22 = v20 + 8;
    v23 = -v20;
    if ( (v22 & -(__int64)(v23 != 0)) != 0 && (*(_BYTE *)((v22 & -(__int64)(v23 != 0)) + 9))-- == 1 )
      *(_QWORD *)(v22 & -(__int64)(v23 != 0)) &= ~2uLL;
    GreReleaseSemaphoreSharedInternal((HSEMAPHORE)(v18 + 624));
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1400278a0  push    rbx
0x1400278a2  push    rbp
0x1400278a3  push    rsi
0x1400278a4  push    rdi
0x1400278a5  push    r14
0x1400278a7  push    r15
0x1400278a9  sub     rsp, 38h
0x1400278ad  mov     eax, ecx
0x1400278af  mov     ebx, ecx
0x1400278b1  and     al, 7
0x1400278b3  mov     rsi, r9
0x1400278b6  mov     rbp, r8
0x1400278b9  mov     r15, rdx
0x1400278bc  cmp     al, 4
0x1400278be  jz      loc_140027A27
0x1400278c4  mov     dil, 1
0x1400278c7  call    cs:__imp_W32GetSessionState
0x1400278ce  nop     dword ptr [rax+rax+00h]
0x1400278d3  lea     rcx, aDynamicmodecha; "DynamicModeChange"
0x1400278da  mov     r14, [rax+58h]
0x1400278de  test    dil, dil
0x1400278e1  jz      short loc_140027904
0x1400278e3  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, 0
0x1400278ea  jnz     loc_140027A49
0x1400278f0  mov     rcx, [r14]
0x1400278f3  add     rcx, 270h; hsem
0x1400278fa  call    EngAcquireSemaphoreShared
0x1400278ff  call    ??$GrepAcquireLockValidate@$00@@YAXXZ; GrepAcquireLockValidate<1>(void)
0x140027904  call    UserSessionSwitchLeaveCritWithNonPaged
0x140027909  mov     rdx, rbx
0x14002790c  mov     ecx, 4
0x140027911  call    cs:__imp_WdLogSingleEntry1
0x140027918  nop     dword ptr [rax+rax+00h]
0x14002791d  mov     ecx, ebx
0x14002791f  mov     cs:WdLogGlobalForLineNumber, 2F04h
0x140027929  call    DrvIsQdcHandledByDispBroker
0x14002792e  test    al, al
0x140027930  jnz     loc_140027A76
0x140027936  call    cs:__imp_DxDdGetDxgkWin32kInterface
0x14002793d  nop     dword ptr [rax+rax+00h]
0x140027942  mov     edx, ebx
0x140027944  mov     [rsp+68h+var_48], rsi
0x140027949  and     ebx, 0FFFFFFEFh
0x14002794c  and     edx, 10h
0x14002794f  mov     r9, rbp
0x140027952  mov     r8, r15
0x140027955  mov     rax, [rax+0D8h]
0x14002795c  mov     ecx, ebx
0x14002795e  call    _guard_dispatch_icall
0x140027963  mov     esi, eax
0x140027965  movsxd  rdx, esi
0x140027968  mov     ecx, 4
0x14002796d  call    cs:__imp_WdLogSingleEntry1
0x140027974  nop     dword ptr [rax+rax+00h]
0x140027979  mov     cs:WdLogGlobalForLineNumber, 2F29h
0x140027983  test    dil, dil
0x140027986  jz      short loc_1400279EF
0x140027988  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, 0
0x14002798f  mov     rbp, [r14]
0x140027992  jnz     loc_140027AC3
0x140027998  mov     r14, gs:188h
0x1400279a1  xor     edi, edi
0x1400279a3  call    cs:__imp_KeIsAttachedProcess
0x1400279aa  nop     dword ptr [rax+rax+00h]
0x1400279af  test    al, al
0x1400279b1  jnz     short loc_1400279FF
0x1400279b3  mov     rcx, r14
0x1400279b6  call    cs:__imp_PsGetThreadWin32Thread
0x1400279bd  nop     dword ptr [rax+rax+00h]
0x1400279c2  test    rax, rax
0x1400279c5  jz      short loc_1400279CA
0x1400279c7  mov     rdi, [rax]
0x1400279ca  lea     rax, [rdi+8]
0x1400279ce  neg     rdi
0x1400279d1  sbb     rdx, rdx
0x1400279d4  and     rdx, rax
0x1400279d7  jz      short loc_1400279E3
0x1400279d9  add     byte ptr [rdx+9], 0FFh
0x1400279dd  jnz     short loc_1400279E3
0x1400279df  and     qword ptr [rdx], 0FFFFFFFFFFFFFFFDh
0x1400279e3  lea     rcx, [rbp+270h]; HSEMAPHORE
0x1400279ea  call    ?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x1400279ef  mov     eax, esi
0x1400279f1  add     rsp, 38h
0x1400279f5  pop     r15
0x1400279f7  pop     r14
0x1400279f9  pop     rdi
0x1400279fa  pop     rsi
0x1400279fb  pop     rbp
0x1400279fc  pop     rbx
0x1400279fd  retn
0x1400279ff  call    W32GetCurrentWin32kSessionId
0x140027a04  mov     ebx, eax
0x140027a06  call    cs:__imp_PsGetCurrentThreadProcess
0x140027a0d  nop     dword ptr [rax+rax+00h]
0x140027a12  mov     rcx, rax
0x140027a15  call    cs:__imp_PsGetProcessSessionIdEx
0x140027a1c  nop     dword ptr [rax+rax+00h]
0x140027a21  cmp     ebx, eax
0x140027a23  jz      short loc_1400279B3
0x140027a25  jmp     short loc_1400279CA
0x140027a27  call    DispBrokerGetCurrentMode
0x140027a2c  cmp     eax, 3
0x140027a2f  jnz     short loc_140027A39
0x140027a31  xor     dil, dil
0x140027a34  jmp     loc_1400278C7
0x140027a39  call    DispBrokerGetCurrentMode
0x140027a3e  cmp     eax, 2
0x140027a41  jnz     loc_1400278C4
0x140027a47  jmp     short loc_140027A31
0x140027a49  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits, 10h
0x140027a50  jz      loc_1400278F0
0x140027a56  mov     r9, [r14]
0x140027a59  lea     rdx, LockAcquireShared
0x140027a60  add     r9, 270h
0x140027a67  mov     [rsp+68h+var_48], rcx
0x140027a6c  call    McTemplateK0pz_EtwWriteTransfer
0x140027a71  jmp     loc_1400278F0
0x140027a76  call    DispBrokerGetCurrentMode
0x140027a7b  cmp     eax, 3
0x140027a7e  jnz     short loc_140027AB9
0x140027a80  mov     eax, [r15]
0x140027a83  lea     r8, [rsp+68h+arg_0]; unsigned int *
0x140027a88  mov     edx, ebx
0x140027a8a  mov     [rsp+68h+arg_0], eax
0x140027a8e  and     ebx, 0FFFFFFEFh
0x140027a91  mov     [rsp+68h+var_48], rsi; enum DISPLAYCONFIG_TOPOLOGY_ID *
0x140027a96  mov     ecx, ebx; unsigned int
0x140027a98  and     edx, 10h; unsigned int
0x140027a9b  mov     r9, rbp; struct DISPLAYCONFIG_PATH_INFO_INTERNAL *
0x140027a9e  call    ?DispBrokerQueryDisplayConfig@@YAJIIPEAIPEAUDISPLAYCONFIG_PATH_INFO_INTERNAL@@PEAW4DISPLAYCONFIG_TOPOLOGY_ID@@_N@Z; DispBrokerQueryDisplayConfig(uint,uint,uint *,DISPLAYCONFIG_PATH_INFO_INTERNAL *,DISPLAYCONFIG_TOPOLOGY_ID *,bool)
0x140027aa3  mov     esi, eax
0x140027aa5  test    eax, eax
0x140027aa7  js      loc_140027965
0x140027aad  mov     ecx, [rsp+68h+arg_0]
0x140027ab1  mov     [r15], ecx
0x140027ab4  jmp     loc_140027965
0x140027ab9  mov     esi, 0C0000022h
0x140027abe  jmp     loc_140027965
0x140027ac3  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits, 10h
0x140027aca  jz      loc_140027998
0x140027ad0  lea     rax, aDynamicmodecha; "DynamicModeChange"
0x140027ad7  lea     r9, [rbp+270h]
0x140027ade  mov     [rsp+68h+var_48], rax
0x140027ae3  lea     rdx, LockRelease
0x140027aea  call    McTemplateK0pz_EtwWriteTransfer
0x140027aef  jmp     loc_140027998
```
