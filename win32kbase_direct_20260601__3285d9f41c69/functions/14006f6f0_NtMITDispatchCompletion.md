# NtMITDispatchCompletion

- ea: `0x14006f6f0`
- end: `0x14006fc0f`
- name: `NtMITDispatchCompletion`
- size: `1311`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140033268`
- `0x14006f6f0`
- `0x14006fec0`
- `0x1400700d8`
- `0x140072a90`
- `0x140158980`
- `0x1401a9f9c`
- `0x1401b7810`
- `0x140238240`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14006f71e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006f71e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006f75e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006f75e`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14006f72f`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14006f72f`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14006f752`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14006f752`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14006f73b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14006f73b`
- `ntoskrnl!DbgkWerCaptureLiveKernelDump` at `0x14006fa9a`
- `ntoskrnl!DbgkWerCaptureLiveKernelDump` at `0x14006fb14`
- `ntoskrnl!DbgkWerCaptureLiveKernelDump` at `0x14006fb8a`
- `ntoskrnl!DbgkWerCaptureLiveKernelDump` at `0x14006fa9a`
- `ntoskrnl!DbgkWerCaptureLiveKernelDump` at `0x14006fb14`
- `ntoskrnl!DbgkWerCaptureLiveKernelDump` at `0x14006fb8a`
- `ntoskrnl!KeBugCheck` at `0x14006fadc`
- `ntoskrnl!KeBugCheck` at `0x14006fbd7`
- `ntoskrnl!KeBugCheck` at `0x14006fadc`
- `ntoskrnl!KeBugCheck` at `0x14006fbd7`
- `ntoskrnl!ZwAssociateWaitCompletionPacket` at `0x14006f83f`
- `ntoskrnl!ZwAssociateWaitCompletionPacket` at `0x14006f99e`
- `ntoskrnl!ZwAssociateWaitCompletionPacket` at `0x14006f83f`
- `ntoskrnl!ZwAssociateWaitCompletionPacket` at `0x14006f99e`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14006f892`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14006f9d9`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14006f892`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14006f9d9`
- `WIN32K!W32GetUserSessionState` at `0x14006f707`
- `WIN32K!W32GetUserSessionState` at `0x14006f7d3`
- `WIN32K!W32GetUserSessionState` at `0x14006f707`
- `WIN32K!W32GetUserSessionState` at `0x14006f7d3`

## string_xrefs

- `0x14006f94d`: `HandleInputThreadSignal`

## pseudocode

```c
__int64 __fastcall NtMITDispatchCompletion(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // ebp
  int v4; // r14d
  __int64 v5; // rbx
  __int64 v6; // rsi
  unsigned int CurrentThreadId; // eax
  unsigned int v8; // edi
  __int64 v9; // rdx
  __int64 v10; // r8
  CTouchProcessor *v11; // rcx
  char v12; // si
  int v13; // edx
  __int64 v14; // rbx
  int v15; // r8d
  unsigned int v16; // r14d
  __int64 v17; // rdi
  __int64 v18; // rbp
  __int64 v19; // rbx
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v21; // rcx
  __int64 v23; // rdi
  __int64 KernelIocpWcp; // rax
  __int64 v25; // r14
  void (__fastcall *v26)(_QWORD); // rax
  __int64 v27; // rbx
  __int64 *v28; // rax
  __int64 v29; // rcx
  __int64 v30; // [rsp+B0h] [rbp+18h] BYREF

  v3 = a2;
  v4 = a1;
  v5 = *(_QWORD *)(W32GetUserSessionState(a1, a2, a3) + 18856);
  v6 = v5 + 8;
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(v5 + 8, 0);
  CurrentThreadId = (unsigned int)PsGetCurrentThreadId();
  LODWORD(v5) = *(_DWORD *)(v5 + 40);
  v8 = CurrentThreadId;
  ExReleasePushLockSharedEx(v6, 0);
  KeLeaveCriticalRegion();
  if ( v8 == (_DWORD)v5 )
  {
    v11 = WPP_GLOBAL_Control;
    v12 = 1;
    if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || (LOBYTE(v9) = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
    {
      LOBYTE(v9) = 0;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
      || (LOBYTE(v10) = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
    {
      LOBYTE(v10) = 0;
    }
    if ( (_BYTE)v9 || (_BYTE)v10 )
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v9,
        v10,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        5,
        2,
        13,
        (__int64)WPP_34bc8fbd5710336976da4e93dfcb98ad_Traceguids);
    v14 = *(_QWORD *)(W32GetUserSessionState(v11, v9, v10) + 19288);
    if ( v4 == 0x80000000 )
    {
      v16 = v3;
      if ( v3 >= *(_DWORD *)(v14 + 2568) )
      {
        LODWORD(v30) = 0x20000;
        MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 3580);
        DbgkWerCaptureLiveKernelDump(L"win32kbase.sys", 400, v3, *(unsigned int *)(v14 + 2568), 0, 0, 0, 0, 0);
      }
      else
      {
        v17 = v14 + 40LL * v3;
        v18 = *(_QWORD *)(v17 + 24);
        if ( v18 )
        {
          if ( (int)ZwAssociateWaitCompletionPacket(
                      v18,
                      *(_QWORD *)(v14 + 2904),
                      *(_QWORD *)(v17 + 8),
                      v16,
                      0xFFFFFFFF80000000uLL,
                      0,
                      0,
                      0) < 0 )
            KeBugCheck(0x164u);
          if ( v18 == *(_QWORD *)(v17 + 24) )
          {
            InputTraceLogging::ThreadLockedPerfRegion::ThreadLockedPerfRegion(
              (InputTraceLogging::ThreadLockedPerfRegion *)&v30,
              "HandleSensorDispatcherSignal",
              0);
            (*(void (__fastcall **)(_QWORD, _QWORD))(v17 + 32))(*(_QWORD *)(v17 + 16), *(_QWORD *)(v17 + 40));
            v19 = v30;
            if ( v30 )
            {
              CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread();
              if ( CurrentThreadWin32Thread )
                v21 = *CurrentThreadWin32Thread;
              else
                v21 = 0;
              *(_QWORD *)(v21 + 376) = *(_QWORD *)(v19 + 48);
              InputTraceLogging::ThreadLockedPerfRegion::Cleanup((InputTraceLogging::ThreadLockedPerfRegion *)&v30);
            }
          }
          else
          {
            IOCPDispatcher::SensorIOCPWCP::Cleanup((IOCPDispatcher::SensorIOCPWCP *)(v17 + 8));
          }
        }
        else
        {
          LODWORD(v30) = 0x20000;
          MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 3598);
          DbgkWerCaptureLiveKernelDump(L"win32kbase.sys", 400, v17 + 8, 0, 0, 0, 0, 0, 0);
        }
      }
    }
    else if ( v4 == -2147483647 )
    {
      if ( v3 < *(_DWORD *)(v14 + 2896) )
      {
        v23 = 32LL * v3;
        if ( *(_QWORD *)(v23 + v14 + 2584) )
        {
          InputTraceLogging::ThreadLockedPerfRegion::ThreadLockedPerfRegion(
            (InputTraceLogging::ThreadLockedPerfRegion *)&v30,
            "HandleInputThreadSignal",
            0);
          KernelIocpWcp = *(_QWORD *)(v23 + v14 + 2584);
          v25 = *(_QWORD *)(v23 + v14 + 2576);
          if ( !KernelIocpWcp && (KernelIocpWcp = CreateKernelIocpWcp()) == 0
            || (int)ZwAssociateWaitCompletionPacket(
                      KernelIocpWcp,
                      *(_QWORD *)(v14 + 2904),
                      v25,
                      v3,
                      -2147483647,
                      0,
                      0,
                      0) < 0 )
          {
            KeBugCheck(0x164u);
          }
          v26 = *(void (__fastcall **)(_QWORD))(v23 + v14 + 2592);
          if ( v26 )
            v26(*(_QWORD *)(v23 + v14 + 2600));
          v27 = v30;
          if ( v30 )
          {
            v28 = (__int64 *)PsGetCurrentThreadWin32Thread();
            if ( v28 )
              v29 = *v28;
            else
              v29 = 0;
            *(_QWORD *)(v29 + 376) = *(_QWORD *)(v27 + 48);
            InputTraceLogging::ThreadLockedPerfRegion::Cleanup((InputTraceLogging::ThreadLockedPerfRegion *)&v30);
          }
        }
      }
    }
    else
    {
      DbgkWerCaptureLiveKernelDump(L"win32kbase.sys", 400, v4, v3, 0, 0, 0, 0, 0);
    }
    if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || (LOBYTE(v13) = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
    {
      LOBYTE(v13) = 0;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED || !*((_WORD *)WPP_GLOBAL_Control + 36) )
      v12 = 0;
    if ( (_BYTE)v13 || v12 )
    {
      LOBYTE(v15) = v12;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v13,
        v15,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        5,
        2,
        14,
        (__int64)WPP_34bc8fbd5710336976da4e93dfcb98ad_Traceguids);
    }
  }
  else
  {
    UserSetLastError(5);
  }
  return 0;
}

```

## disassembly

```asm
0x14006f6f0  push    rbx
0x14006f6f2  push    rbp
0x14006f6f3  push    rsi
0x14006f6f4  push    rdi
0x14006f6f5  push    r12
0x14006f6f7  push    r13
0x14006f6f9  push    r14
0x14006f6fb  push    r15
0x14006f6fd  sub     rsp, 58h
0x14006f701  mov     rbp, rdx
0x14006f704  mov     r14, rcx
0x14006f707  call    cs:__imp_W32GetUserSessionState
0x14006f70e  nop     dword ptr [rax+rax+00h]
0x14006f713  mov     rbx, [rax+49A8h]
0x14006f71a  lea     rsi, [rbx+8]
0x14006f71e  call    cs:__imp_KeEnterCriticalRegion
0x14006f725  nop     dword ptr [rax+rax+00h]
0x14006f72a  xor     edx, edx
0x14006f72c  mov     rcx, rsi
0x14006f72f  call    cs:__imp_ExAcquirePushLockSharedEx
0x14006f736  nop     dword ptr [rax+rax+00h]
0x14006f73b  call    cs:__imp_PsGetCurrentThreadId
0x14006f742  nop     dword ptr [rax+rax+00h]
0x14006f747  mov     ebx, [rbx+28h]
0x14006f74a  xor     edx, edx
0x14006f74c  mov     rcx, rsi
0x14006f74f  mov     rdi, rax
0x14006f752  call    cs:__imp_ExReleasePushLockSharedEx
0x14006f759  nop     dword ptr [rax+rax+00h]
0x14006f75e  call    cs:__imp_KeLeaveCriticalRegion
0x14006f765  nop     dword ptr [rax+rax+00h]
0x14006f76a  cmp     edi, ebx
0x14006f76c  jnz     loc_14006FB9B
0x14006f772  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f779  lea     rax, WPP_GLOBAL_Control
0x14006f780  xor     r15d, r15d
0x14006f783  mov     sil, 1
0x14006f786  lea     r13d, [r15+2]
0x14006f78a  cmp     rcx, rax
0x14006f78d  jz      short loc_14006F79B
0x14006f78f  mov     eax, [rcx+2Ch]
0x14006f792  test    r13b, al
0x14006f795  jnz     loc_14006FB25
0x14006f79b  mov     dl, r15b
0x14006f79e  lea     rdi, WPP_RECORDER_INITIALIZED
0x14006f7a5  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14006f7ac  jz      short loc_14006F7B8
0x14006f7ae  mov     r8b, sil
0x14006f7b1  cmp     [rcx+48h], r15w
0x14006f7b6  jnz     short loc_14006F7BB
0x14006f7b8  mov     r8b, r15b
0x14006f7bb  lea     r12, WPP_34bc8fbd5710336976da4e93dfcb98ad_Traceguids
0x14006f7c2  test    dl, dl
0x14006f7c4  jnz     loc_14006FBAA
0x14006f7ca  test    r8b, r8b
0x14006f7cd  jnz     loc_14006FBAA
0x14006f7d3  call    cs:__imp_W32GetUserSessionState
0x14006f7da  nop     dword ptr [rax+rax+00h]
0x14006f7df  mov     rcx, 0FFFFFFFF80000000h
0x14006f7e6  mov     rbx, [rax+4B58h]
0x14006f7ed  cmp     r14d, ecx
0x14006f7f0  jnz     loc_14006F918
0x14006f7f6  mov     r14d, ebp
0x14006f7f9  cmp     ebp, [rbx+0A08h]
0x14006f7ff  jnb     loc_14006FB37
0x14006f805  lea     rax, [r14+r14*4]
0x14006f809  lea     rdi, [rbx+rax*8]
0x14006f80d  mov     rbp, [rdi+18h]
0x14006f811  test    rbp, rbp
0x14006f814  jz      loc_14006FA4A
0x14006f81a  mov     r8, [rdi+8]
0x14006f81e  mov     r9d, r14d
0x14006f821  mov     rdx, [rbx+0B58h]
0x14006f828  mov     [rsp+98h+var_60], r15
0x14006f82d  mov     [rsp+98h+var_68], r15
0x14006f832  mov     dword ptr [rsp+98h+var_70], r15d
0x14006f837  mov     [rsp+98h+var_78], rcx
0x14006f83c  mov     rcx, rbp
0x14006f83f  call    cs:__imp_ZwAssociateWaitCompletionPacket
0x14006f846  nop     dword ptr [rax+rax+00h]
0x14006f84b  test    eax, eax
0x14006f84d  js      loc_14006FBD2
0x14006f853  cmp     rbp, [rdi+18h]
0x14006f857  jnz     loc_14006FABB
0x14006f85d  xor     r8d, r8d; struct InputTraceLogging::ThreadLockedPerfRegion *
0x14006f860  lea     rdx, aHandlesensordi; "HandleSensorDispatcherSignal"
0x14006f867  lea     rcx, [rsp+98h+arg_10]; this
0x14006f86f  call    ??0ThreadLockedPerfRegion@InputTraceLogging@@QEAA@PEBDPEBU01@@Z; InputTraceLogging::ThreadLockedPerfRegion::ThreadLockedPerfRegion(char const *,InputTraceLogging::ThreadLockedPerfRegion const *)
0x14006f874  mov     rax, [rdi+20h]
0x14006f878  mov     rdx, [rdi+28h]
0x14006f87c  mov     rcx, [rdi+10h]
0x14006f880  call    _guard_dispatch_icall
0x14006f885  mov     rbx, [rsp+98h+arg_10]
0x14006f88d  test    rbx, rbx
0x14006f890  jz      short loc_14006F8C2
0x14006f892  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14006f899  nop     dword ptr [rax+rax+00h]
0x14006f89e  test    rax, rax
0x14006f8a1  jz      loc_14006FAAB
0x14006f8a7  mov     rcx, [rax]
0x14006f8aa  mov     rax, [rbx+30h]
0x14006f8ae  mov     [rcx+178h], rax
0x14006f8b5  lea     rcx, [rsp+98h+arg_10]; this
0x14006f8bd  call    ?Cleanup@ThreadLockedPerfRegion@InputTraceLogging@@AEAAXXZ; InputTraceLogging::ThreadLockedPerfRegion::Cleanup(void)
0x14006f8c2  lea     rdi, WPP_RECORDER_INITIALIZED
0x14006f8c9  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f8d0  lea     rax, WPP_GLOBAL_Control
0x14006f8d7  cmp     rcx, rax
0x14006f8da  jnz     loc_14006FA2C
0x14006f8e0  mov     dl, r15b
0x14006f8e3  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14006f8ea  jnz     loc_14006FA1C
0x14006f8f0  mov     sil, r15b
0x14006f8f3  test    dl, dl
0x14006f8f5  jnz     loc_14006FBE4
0x14006f8fb  test    sil, sil
0x14006f8fe  jnz     loc_14006FBE4
0x14006f904  xor     eax, eax
0x14006f906  add     rsp, 58h
0x14006f90a  pop     r15
0x14006f90c  pop     r14
0x14006f90e  pop     r13
0x14006f910  pop     r12
0x14006f912  pop     rdi
0x14006f913  pop     rsi
0x14006f914  pop     rbp
0x14006f915  pop     rbx
0x14006f916  retn
0x14006f918  mov     r12, 0FFFFFFFF80000001h
0x14006f91f  cmp     r14d, r12d
0x14006f922  jnz     loc_14006FAE9
0x14006f928  cmp     ebp, [rbx+0B50h]
0x14006f92e  jnb     loc_14006FA10
0x14006f934  mov     ebp, ebp
0x14006f936  mov     edi, ebp
0x14006f938  shl     rdi, 5
0x14006f93c  cmp     [rdi+rbx+0A18h], r15
0x14006f944  jz      loc_14006FA09
0x14006f94a  xor     r8d, r8d; struct InputTraceLogging::ThreadLockedPerfRegion *
0x14006f94d  lea     rdx, aHandleinputthr; "HandleInputThreadSignal"
0x14006f954  lea     rcx, [rsp+98h+arg_10]; this
0x14006f95c  call    ??0ThreadLockedPerfRegion@InputTraceLogging@@QEAA@PEBDPEBU01@@Z; InputTraceLogging::ThreadLockedPerfRegion::ThreadLockedPerfRegion(char const *,InputTraceLogging::ThreadLockedPerfRegion const *)
0x14006f961  mov     rax, [rdi+rbx+0A18h]
0x14006f969  mov     r14, [rdi+rbx+0A10h]
0x14006f971  test    rax, rax
0x14006f974  jz      loc_14006FAC9
0x14006f97a  mov     rdx, [rbx+0B58h]
0x14006f981  mov     r9, rbp
0x14006f984  mov     [rsp+98h+var_60], r15
0x14006f989  mov     r8, r14
0x14006f98c  mov     [rsp+98h+var_68], r15
0x14006f991  mov     rcx, rax
0x14006f994  mov     dword ptr [rsp+98h+var_70], r15d
0x14006f999  mov     [rsp+98h+var_78], r12
0x14006f99e  call    cs:__imp_ZwAssociateWaitCompletionPacket
0x14006f9a5  nop     dword ptr [rax+rax+00h]
0x14006f9aa  test    eax, eax
0x14006f9ac  js      loc_14006FAD7
0x14006f9b2  mov     rax, [rdi+rbx+0A20h]
0x14006f9ba  test    rax, rax
0x14006f9bd  jz      short loc_14006F9CC
0x14006f9bf  mov     rcx, [rdi+rbx+0A28h]
0x14006f9c7  call    _guard_dispatch_icall
0x14006f9cc  mov     rbx, [rsp+98h+arg_10]
0x14006f9d4  test    rbx, rbx
0x14006f9d7  jz      short loc_14006FA09
0x14006f9d9  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14006f9e0  nop     dword ptr [rax+rax+00h]
0x14006f9e5  test    rax, rax
0x14006f9e8  jz      loc_14006FAB3
0x14006f9ee  mov     rcx, [rax]
0x14006f9f1  mov     rax, [rbx+30h]
0x14006f9f5  mov     [rcx+178h], rax
0x14006f9fc  lea     rcx, [rsp+98h+arg_10]; this
0x14006fa04  call    ?Cleanup@ThreadLockedPerfRegion@InputTraceLogging@@AEAAXXZ; InputTraceLogging::ThreadLockedPerfRegion::Cleanup(void)
0x14006fa09  lea     rdi, WPP_RECORDER_INITIALIZED
0x14006fa10  lea     r12, WPP_34bc8fbd5710336976da4e93dfcb98ad_Traceguids
0x14006fa17  jmp     loc_14006F8C9
0x14006fa1c  cmp     [rcx+48h], r15w
0x14006fa21  jnz     loc_14006F8F3
0x14006fa27  jmp     loc_14006F8F0
0x14006fa2c  mov     eax, [rcx+2Ch]
0x14006fa2f  test    r13b, al
0x14006fa32  jz      loc_14006F8E0
0x14006fa38  cmp     byte ptr [rcx+29h], 5
0x14006fa3c  mov     dl, sil
0x14006fa3f  jnb     loc_14006F8E3
0x14006fa45  jmp     loc_14006F8E0
0x14006fa4a  mov     dword ptr [rsp+98h+arg_10], 20000h
0x14006fa55  lea     rcx, aIxptelassert; "IXPTelAssert"
0x14006fa5c  mov     edx, dword ptr [rsp+98h+arg_10]
0x14006fa63  mov     r8d, 0E0Eh
0x14006fa69  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x14006fa6e  mov     [rsp+98h+var_58], r15d
0x14006fa73  lea     r8, [rdi+8]
0x14006fa77  mov     [rsp+98h+var_60], r15
0x14006fa7c  lea     rcx, aWin32kbaseSys; "win32kbase.sys"
0x14006fa83  mov     [rsp+98h+var_68], r15
0x14006fa88  xor     r9d, r9d
0x14006fa8b  mov     [rsp+98h+var_70], r15
0x14006fa90  mov     edx, 190h
0x14006fa95  mov     [rsp+98h+var_78], r15
0x14006fa9a  call    cs:__imp_DbgkWerCaptureLiveKernelDump
0x14006faa1  nop     dword ptr [rax+rax+00h]
0x14006faa6  jmp     loc_14006F8C2
0x14006faab  mov     rcx, r15
0x14006faae  jmp     loc_14006F8AA
0x14006fab3  mov     rcx, r15
0x14006fab6  jmp     loc_14006F9F1
0x14006fabb  lea     rcx, [rdi+8]; this
0x14006fabf  call    ?Cleanup@SensorIOCPWCP@IOCPDispatcher@@QEAAXXZ; IOCPDispatcher::SensorIOCPWCP::Cleanup(void)
0x14006fac4  jmp     loc_14006F8C2
0x14006fac9  call    CreateKernelIocpWcp
0x14006face  test    rax, rax
0x14006fad1  jnz     loc_14006F97A
0x14006fad7  mov     ecx, 164h; BugCheckCode
0x14006fadc  call    cs:__imp_KeBugCheck
0x14006fae9  mov     [rsp+98h+var_58], r15d
0x14006faee  lea     rcx, aWin32kbaseSys; "win32kbase.sys"
0x14006faf5  mov     [rsp+98h+var_60], r15
0x14006fafa  mov     edx, 190h
0x14006faff  mov     [rsp+98h+var_68], r15
0x14006fb04  mov     [rsp+98h+var_70], r15
0x14006fb09  mov     r9d, ebp
0x14006fb0c  movsxd  r8, r14d
0x14006fb0f  mov     [rsp+98h+var_78], r15
0x14006fb14  call    cs:__imp_DbgkWerCaptureLiveKernelDump
0x14006fb1b  nop     dword ptr [rax+rax+00h]
0x14006fb20  jmp     loc_14006FA10
0x14006fb25  cmp     byte ptr [rcx+29h], 5
0x14006fb29  mov     dl, sil
0x14006fb2c  jb      loc_14006F79B
0x14006fb32  jmp     loc_14006F79E
0x14006fb37  mov     dword ptr [rsp+98h+arg_10], 20000h
0x14006fb42  lea     rcx, aIxptelassert; "IXPTelAssert"
0x14006fb49  mov     edx, dword ptr [rsp+98h+arg_10]
0x14006fb50  mov     r8d, 0DFCh
0x14006fb56  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x14006fb5b  mov     r9d, [rbx+0A08h]
0x14006fb62  lea     rcx, aWin32kbaseSys; "win32kbase.sys"
0x14006fb69  mov     [rsp+98h+var_58], r15d
0x14006fb6e  mov     r8, r14
0x14006fb71  mov     [rsp+98h+var_60], r15
0x14006fb76  mov     edx, 190h
0x14006fb7b  mov     [rsp+98h+var_68], r15
0x14006fb80  mov     [rsp+98h+var_70], r15
0x14006fb85  mov     [rsp+98h+var_78], r15
0x14006fb8a  call    cs:__imp_DbgkWerCaptureLiveKernelDump
0x14006fb91  nop     dword ptr [rax+rax+00h]
0x14006fb96  jmp     loc_14006F8C9
0x14006fb9b  mov     ecx, 5
0x14006fba0  call    UserSetLastError
0x14006fba5  jmp     loc_14006F904
0x14006fbaa  mov     r9, [rcx+40h]
0x14006fbae  mov     rcx, [rcx+18h]
0x14006fbb2  mov     [rsp+98h+var_60], r12
0x14006fbb7  mov     word ptr [rsp+98h+var_68], 0Dh
0x14006fbbe  mov     dword ptr [rsp+98h+var_70], r13d
0x14006fbc3  mov     byte ptr [rsp+98h+var_78], 5
0x14006fbc8  call    WPP_RECORDER_AND_TRACE_SF_
0x14006fbcd  jmp     loc_14006F7D3
0x14006fbd2  mov     ecx, 164h; BugCheckCode
0x14006fbd7  call    cs:__imp_KeBugCheck
0x14006fbe4  mov     r9, [rcx+40h]
0x14006fbe8  mov     r8b, sil
0x14006fbeb  mov     rcx, [rcx+18h]
0x14006fbef  mov     [rsp+98h+var_60], r12
0x14006fbf4  mov     word ptr [rsp+98h+var_68], 0Eh
0x14006fbfb  mov     dword ptr [rsp+98h+var_70], r13d
0x14006fc00  mov     byte ptr [rsp+98h+var_78], 5
0x14006fc05  call    WPP_RECORDER_AND_TRACE_SF_
0x14006fc0a  jmp     loc_14006F904
```
