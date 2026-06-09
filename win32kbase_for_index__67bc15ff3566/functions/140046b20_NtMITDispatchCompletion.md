# NtMITDispatchCompletion

- ea: `0x140046b20`
- end: `0x14004703f`
- name: `NtMITDispatchCompletion`
- size: `1311`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140046b20`
- `0x1400472f0`
- `0x140047508`
- `0x140049ec0`
- `0x1400700d8`
- `0x14015b4f0`
- `0x1401aab9c`
- `0x1401b8990`
- `0x1402389c0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140046b4e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140046b4e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140046b8e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140046b8e`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140046b5f`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140046b5f`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140046b82`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140046b82`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140046b6b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140046b6b`
- `ntoskrnl!DbgkWerCaptureLiveKernelDump` at `0x140046eca`
- `ntoskrnl!DbgkWerCaptureLiveKernelDump` at `0x140046f44`
- `ntoskrnl!DbgkWerCaptureLiveKernelDump` at `0x140046fba`
- `ntoskrnl!DbgkWerCaptureLiveKernelDump` at `0x140046eca`
- `ntoskrnl!DbgkWerCaptureLiveKernelDump` at `0x140046f44`
- `ntoskrnl!DbgkWerCaptureLiveKernelDump` at `0x140046fba`
- `ntoskrnl!KeBugCheck` at `0x140046f0c`
- `ntoskrnl!KeBugCheck` at `0x140047007`
- `ntoskrnl!KeBugCheck` at `0x140046f0c`
- `ntoskrnl!KeBugCheck` at `0x140047007`
- `ntoskrnl!ZwAssociateWaitCompletionPacket` at `0x140046c6f`
- `ntoskrnl!ZwAssociateWaitCompletionPacket` at `0x140046dce`
- `ntoskrnl!ZwAssociateWaitCompletionPacket` at `0x140046c6f`
- `ntoskrnl!ZwAssociateWaitCompletionPacket` at `0x140046dce`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140046cc2`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140046e09`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140046cc2`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140046e09`
- `WIN32K!W32GetUserSessionState` at `0x140046b37`
- `WIN32K!W32GetUserSessionState` at `0x140046c03`
- `WIN32K!W32GetUserSessionState` at `0x140046b37`
- `WIN32K!W32GetUserSessionState` at `0x140046c03`

## string_xrefs

- `0x140046d7d`: `HandleInputThreadSignal`

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
  __int64 v13; // rdx
  __int64 v14; // rbx
  __int64 v15; // r8
  unsigned int v16; // r14d
  __int64 v17; // rdi
  __int64 v18; // rbp
  __int64 v19; // rcx
  __int64 v20; // r9
  __int64 v21; // rbx
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v23; // rcx
  __int64 v25; // rdi
  __int64 KernelIocpWcp; // rax
  __int64 v27; // r14
  __int64 v28; // rcx
  __int64 v29; // r9
  void (__fastcall *v30)(_QWORD); // rax
  __int64 v31; // rbx
  __int64 *v32; // rax
  __int64 v33; // rcx
  __int64 v34; // [rsp+B0h] [rbp+18h] BYREF

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
        LODWORD(v34) = 0x20000;
        MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 3611);
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
              (InputTraceLogging::ThreadLockedPerfRegion *)&v34,
              "HandleSensorDispatcherSignal",
              0);
            (*(void (__fastcall **)(_QWORD, _QWORD))(v17 + 32))(*(_QWORD *)(v17 + 16), *(_QWORD *)(v17 + 40));
            v21 = v34;
            if ( v34 )
            {
              CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread(v19, v13, v15, v20);
              if ( CurrentThreadWin32Thread )
                v23 = *CurrentThreadWin32Thread;
              else
                v23 = 0;
              *(_QWORD *)(v23 + 376) = *(_QWORD *)(v21 + 48);
              InputTraceLogging::ThreadLockedPerfRegion::Cleanup((InputTraceLogging::ThreadLockedPerfRegion *)&v34);
            }
          }
          else
          {
            IOCPDispatcher::SensorIOCPWCP::Cleanup((IOCPDispatcher::SensorIOCPWCP *)(v17 + 8));
          }
        }
        else
        {
          LODWORD(v34) = 0x20000;
          MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 3629);
          DbgkWerCaptureLiveKernelDump(L"win32kbase.sys", 400, v17 + 8, 0, 0, 0, 0, 0, 0);
        }
      }
    }
    else if ( v4 == -2147483647 )
    {
      if ( v3 < *(_DWORD *)(v14 + 2896) )
      {
        v25 = 32LL * v3;
        if ( *(_QWORD *)(v25 + v14 + 2584) )
        {
          InputTraceLogging::ThreadLockedPerfRegion::ThreadLockedPerfRegion(
            (InputTraceLogging::ThreadLockedPerfRegion *)&v34,
            "HandleInputThreadSignal",
            0);
          KernelIocpWcp = *(_QWORD *)(v25 + v14 + 2584);
          v27 = *(_QWORD *)(v25 + v14 + 2576);
          if ( !KernelIocpWcp && (KernelIocpWcp = CreateKernelIocpWcp()) == 0
            || (int)ZwAssociateWaitCompletionPacket(
                      KernelIocpWcp,
                      *(_QWORD *)(v14 + 2904),
                      v27,
                      v3,
                      -2147483647,
                      0,
                      0,
                      0) < 0 )
          {
            KeBugCheck(0x164u);
          }
          v30 = *(void (__fastcall **)(_QWORD))(v25 + v14 + 2592);
          if ( v30 )
            v30(*(_QWORD *)(v25 + v14 + 2600));
          v31 = v34;
          if ( v34 )
          {
            v32 = (__int64 *)PsGetCurrentThreadWin32Thread(v28, v13, v15, v29);
            if ( v32 )
              v33 = *v32;
            else
              v33 = 0;
            *(_QWORD *)(v33 + 376) = *(_QWORD *)(v31 + 48);
            InputTraceLogging::ThreadLockedPerfRegion::Cleanup((InputTraceLogging::ThreadLockedPerfRegion *)&v34);
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
0x140046b20  push    rbx
0x140046b22  push    rbp
0x140046b23  push    rsi
0x140046b24  push    rdi
0x140046b25  push    r12
0x140046b27  push    r13
0x140046b29  push    r14
0x140046b2b  push    r15
0x140046b2d  sub     rsp, 58h
0x140046b31  mov     rbp, rdx
0x140046b34  mov     r14, rcx
0x140046b37  call    cs:__imp_W32GetUserSessionState
0x140046b3e  nop     dword ptr [rax+rax+00h]
0x140046b43  mov     rbx, [rax+49A8h]
0x140046b4a  lea     rsi, [rbx+8]
0x140046b4e  call    cs:__imp_KeEnterCriticalRegion
0x140046b55  nop     dword ptr [rax+rax+00h]
0x140046b5a  xor     edx, edx
0x140046b5c  mov     rcx, rsi
0x140046b5f  call    cs:__imp_ExAcquirePushLockSharedEx
0x140046b66  nop     dword ptr [rax+rax+00h]
0x140046b6b  call    cs:__imp_PsGetCurrentThreadId
0x140046b72  nop     dword ptr [rax+rax+00h]
0x140046b77  mov     ebx, [rbx+28h]
0x140046b7a  xor     edx, edx
0x140046b7c  mov     rcx, rsi
0x140046b7f  mov     rdi, rax
0x140046b82  call    cs:__imp_ExReleasePushLockSharedEx
0x140046b89  nop     dword ptr [rax+rax+00h]
0x140046b8e  call    cs:__imp_KeLeaveCriticalRegion
0x140046b95  nop     dword ptr [rax+rax+00h]
0x140046b9a  cmp     edi, ebx
0x140046b9c  jnz     loc_140046FCB
0x140046ba2  mov     rcx, cs:WPP_GLOBAL_Control
0x140046ba9  lea     rax, WPP_GLOBAL_Control
0x140046bb0  xor     r15d, r15d
0x140046bb3  mov     sil, 1
0x140046bb6  lea     r13d, [r15+2]
0x140046bba  cmp     rcx, rax
0x140046bbd  jz      short loc_140046BCB
0x140046bbf  mov     eax, [rcx+2Ch]
0x140046bc2  test    r13b, al
0x140046bc5  jnz     loc_140046F55
0x140046bcb  mov     dl, r15b
0x140046bce  lea     rdi, WPP_RECORDER_INITIALIZED
0x140046bd5  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140046bdc  jz      short loc_140046BE8
0x140046bde  mov     r8b, sil
0x140046be1  cmp     [rcx+48h], r15w
0x140046be6  jnz     short loc_140046BEB
0x140046be8  mov     r8b, r15b
0x140046beb  lea     r12, WPP_34bc8fbd5710336976da4e93dfcb98ad_Traceguids
0x140046bf2  test    dl, dl
0x140046bf4  jnz     loc_140046FDA
0x140046bfa  test    r8b, r8b
0x140046bfd  jnz     loc_140046FDA
0x140046c03  call    cs:__imp_W32GetUserSessionState
0x140046c0a  nop     dword ptr [rax+rax+00h]
0x140046c0f  mov     rcx, 0FFFFFFFF80000000h
0x140046c16  mov     rbx, [rax+4B58h]
0x140046c1d  cmp     r14d, ecx
0x140046c20  jnz     loc_140046D48
0x140046c26  mov     r14d, ebp
0x140046c29  cmp     ebp, [rbx+0A08h]
0x140046c2f  jnb     loc_140046F67
0x140046c35  lea     rax, [r14+r14*4]
0x140046c39  lea     rdi, [rbx+rax*8]
0x140046c3d  mov     rbp, [rdi+18h]
0x140046c41  test    rbp, rbp
0x140046c44  jz      loc_140046E7A
0x140046c4a  mov     r8, [rdi+8]
0x140046c4e  mov     r9d, r14d
0x140046c51  mov     rdx, [rbx+0B58h]
0x140046c58  mov     [rsp+98h+var_60], r15
0x140046c5d  mov     [rsp+98h+var_68], r15
0x140046c62  mov     dword ptr [rsp+98h+var_70], r15d
0x140046c67  mov     [rsp+98h+var_78], rcx
0x140046c6c  mov     rcx, rbp
0x140046c6f  call    cs:__imp_ZwAssociateWaitCompletionPacket
0x140046c76  nop     dword ptr [rax+rax+00h]
0x140046c7b  test    eax, eax
0x140046c7d  js      loc_140047002
0x140046c83  cmp     rbp, [rdi+18h]
0x140046c87  jnz     loc_140046EEB
0x140046c8d  xor     r8d, r8d; struct InputTraceLogging::ThreadLockedPerfRegion *
0x140046c90  lea     rdx, aHandlesensordi; "HandleSensorDispatcherSignal"
0x140046c97  lea     rcx, [rsp+98h+arg_10]; this
0x140046c9f  call    ??0ThreadLockedPerfRegion@InputTraceLogging@@QEAA@PEBDPEBU01@@Z; InputTraceLogging::ThreadLockedPerfRegion::ThreadLockedPerfRegion(char const *,InputTraceLogging::ThreadLockedPerfRegion const *)
0x140046ca4  mov     rax, [rdi+20h]
0x140046ca8  mov     rdx, [rdi+28h]
0x140046cac  mov     rcx, [rdi+10h]
0x140046cb0  call    _guard_dispatch_icall
0x140046cb5  mov     rbx, [rsp+98h+arg_10]
0x140046cbd  test    rbx, rbx
0x140046cc0  jz      short loc_140046CF2
0x140046cc2  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140046cc9  nop     dword ptr [rax+rax+00h]
0x140046cce  test    rax, rax
0x140046cd1  jz      loc_140046EDB
0x140046cd7  mov     rcx, [rax]
0x140046cda  mov     rax, [rbx+30h]
0x140046cde  mov     [rcx+178h], rax
0x140046ce5  lea     rcx, [rsp+98h+arg_10]; this
0x140046ced  call    ?Cleanup@ThreadLockedPerfRegion@InputTraceLogging@@AEAAXXZ; InputTraceLogging::ThreadLockedPerfRegion::Cleanup(void)
0x140046cf2  lea     rdi, WPP_RECORDER_INITIALIZED
0x140046cf9  mov     rcx, cs:WPP_GLOBAL_Control
0x140046d00  lea     rax, WPP_GLOBAL_Control
0x140046d07  cmp     rcx, rax
0x140046d0a  jnz     loc_140046E5C
0x140046d10  mov     dl, r15b
0x140046d13  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140046d1a  jnz     loc_140046E4C
0x140046d20  mov     sil, r15b
0x140046d23  test    dl, dl
0x140046d25  jnz     loc_140047014
0x140046d2b  test    sil, sil
0x140046d2e  jnz     loc_140047014
0x140046d34  xor     eax, eax
0x140046d36  add     rsp, 58h
0x140046d3a  pop     r15
0x140046d3c  pop     r14
0x140046d3e  pop     r13
0x140046d40  pop     r12
0x140046d42  pop     rdi
0x140046d43  pop     rsi
0x140046d44  pop     rbp
0x140046d45  pop     rbx
0x140046d46  retn
0x140046d48  mov     r12, 0FFFFFFFF80000001h
0x140046d4f  cmp     r14d, r12d
0x140046d52  jnz     loc_140046F19
0x140046d58  cmp     ebp, [rbx+0B50h]
0x140046d5e  jnb     loc_140046E40
0x140046d64  mov     ebp, ebp
0x140046d66  mov     edi, ebp
0x140046d68  shl     rdi, 5
0x140046d6c  cmp     [rdi+rbx+0A18h], r15
0x140046d74  jz      loc_140046E39
0x140046d7a  xor     r8d, r8d; struct InputTraceLogging::ThreadLockedPerfRegion *
0x140046d7d  lea     rdx, aHandleinputthr; "HandleInputThreadSignal"
0x140046d84  lea     rcx, [rsp+98h+arg_10]; this
0x140046d8c  call    ??0ThreadLockedPerfRegion@InputTraceLogging@@QEAA@PEBDPEBU01@@Z; InputTraceLogging::ThreadLockedPerfRegion::ThreadLockedPerfRegion(char const *,InputTraceLogging::ThreadLockedPerfRegion const *)
0x140046d91  mov     rax, [rdi+rbx+0A18h]
0x140046d99  mov     r14, [rdi+rbx+0A10h]
0x140046da1  test    rax, rax
0x140046da4  jz      loc_140046EF9
0x140046daa  mov     rdx, [rbx+0B58h]
0x140046db1  mov     r9, rbp
0x140046db4  mov     [rsp+98h+var_60], r15
0x140046db9  mov     r8, r14
0x140046dbc  mov     [rsp+98h+var_68], r15
0x140046dc1  mov     rcx, rax
0x140046dc4  mov     dword ptr [rsp+98h+var_70], r15d
0x140046dc9  mov     [rsp+98h+var_78], r12
0x140046dce  call    cs:__imp_ZwAssociateWaitCompletionPacket
0x140046dd5  nop     dword ptr [rax+rax+00h]
0x140046dda  test    eax, eax
0x140046ddc  js      loc_140046F07
0x140046de2  mov     rax, [rdi+rbx+0A20h]
0x140046dea  test    rax, rax
0x140046ded  jz      short loc_140046DFC
0x140046def  mov     rcx, [rdi+rbx+0A28h]
0x140046df7  call    _guard_dispatch_icall
0x140046dfc  mov     rbx, [rsp+98h+arg_10]
0x140046e04  test    rbx, rbx
0x140046e07  jz      short loc_140046E39
0x140046e09  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140046e10  nop     dword ptr [rax+rax+00h]
0x140046e15  test    rax, rax
0x140046e18  jz      loc_140046EE3
0x140046e1e  mov     rcx, [rax]
0x140046e21  mov     rax, [rbx+30h]
0x140046e25  mov     [rcx+178h], rax
0x140046e2c  lea     rcx, [rsp+98h+arg_10]; this
0x140046e34  call    ?Cleanup@ThreadLockedPerfRegion@InputTraceLogging@@AEAAXXZ; InputTraceLogging::ThreadLockedPerfRegion::Cleanup(void)
0x140046e39  lea     rdi, WPP_RECORDER_INITIALIZED
0x140046e40  lea     r12, WPP_34bc8fbd5710336976da4e93dfcb98ad_Traceguids
0x140046e47  jmp     loc_140046CF9
0x140046e4c  cmp     [rcx+48h], r15w
0x140046e51  jnz     loc_140046D23
0x140046e57  jmp     loc_140046D20
0x140046e5c  mov     eax, [rcx+2Ch]
0x140046e5f  test    r13b, al
0x140046e62  jz      loc_140046D10
0x140046e68  cmp     byte ptr [rcx+29h], 5
0x140046e6c  mov     dl, sil
0x140046e6f  jnb     loc_140046D13
0x140046e75  jmp     loc_140046D10
0x140046e7a  mov     dword ptr [rsp+98h+arg_10], 20000h
0x140046e85  lea     rcx, aIxptelassert; "IXPTelAssert"
0x140046e8c  mov     edx, dword ptr [rsp+98h+arg_10]
0x140046e93  mov     r8d, 0E2Dh
0x140046e99  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x140046e9e  mov     [rsp+98h+var_58], r15d
0x140046ea3  lea     r8, [rdi+8]
0x140046ea7  mov     [rsp+98h+var_60], r15
0x140046eac  lea     rcx, aWin32kbaseSys; "win32kbase.sys"
0x140046eb3  mov     [rsp+98h+var_68], r15
0x140046eb8  xor     r9d, r9d
0x140046ebb  mov     [rsp+98h+var_70], r15
0x140046ec0  mov     edx, 190h
0x140046ec5  mov     [rsp+98h+var_78], r15
0x140046eca  call    cs:__imp_DbgkWerCaptureLiveKernelDump
0x140046ed1  nop     dword ptr [rax+rax+00h]
0x140046ed6  jmp     loc_140046CF2
0x140046edb  mov     rcx, r15
0x140046ede  jmp     loc_140046CDA
0x140046ee3  mov     rcx, r15
0x140046ee6  jmp     loc_140046E21
0x140046eeb  lea     rcx, [rdi+8]; this
0x140046eef  call    ?Cleanup@SensorIOCPWCP@IOCPDispatcher@@QEAAXXZ; IOCPDispatcher::SensorIOCPWCP::Cleanup(void)
0x140046ef4  jmp     loc_140046CF2
0x140046ef9  call    CreateKernelIocpWcp
0x140046efe  test    rax, rax
0x140046f01  jnz     loc_140046DAA
0x140046f07  mov     ecx, 164h; BugCheckCode
0x140046f0c  call    cs:__imp_KeBugCheck
0x140046f19  mov     [rsp+98h+var_58], r15d
0x140046f1e  lea     rcx, aWin32kbaseSys; "win32kbase.sys"
0x140046f25  mov     [rsp+98h+var_60], r15
0x140046f2a  mov     edx, 190h
0x140046f2f  mov     [rsp+98h+var_68], r15
0x140046f34  mov     [rsp+98h+var_70], r15
0x140046f39  mov     r9d, ebp
0x140046f3c  movsxd  r8, r14d
0x140046f3f  mov     [rsp+98h+var_78], r15
0x140046f44  call    cs:__imp_DbgkWerCaptureLiveKernelDump
0x140046f4b  nop     dword ptr [rax+rax+00h]
0x140046f50  jmp     loc_140046E40
0x140046f55  cmp     byte ptr [rcx+29h], 5
0x140046f59  mov     dl, sil
0x140046f5c  jb      loc_140046BCB
0x140046f62  jmp     loc_140046BCE
0x140046f67  mov     dword ptr [rsp+98h+arg_10], 20000h
0x140046f72  lea     rcx, aIxptelassert; "IXPTelAssert"
0x140046f79  mov     edx, dword ptr [rsp+98h+arg_10]
0x140046f80  mov     r8d, 0E1Bh
0x140046f86  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x140046f8b  mov     r9d, [rbx+0A08h]
0x140046f92  lea     rcx, aWin32kbaseSys; "win32kbase.sys"
0x140046f99  mov     [rsp+98h+var_58], r15d
0x140046f9e  mov     r8, r14
0x140046fa1  mov     [rsp+98h+var_60], r15
0x140046fa6  mov     edx, 190h
0x140046fab  mov     [rsp+98h+var_68], r15
0x140046fb0  mov     [rsp+98h+var_70], r15
0x140046fb5  mov     [rsp+98h+var_78], r15
0x140046fba  call    cs:__imp_DbgkWerCaptureLiveKernelDump
0x140046fc1  nop     dword ptr [rax+rax+00h]
0x140046fc6  jmp     loc_140046CF9
0x140046fcb  mov     ecx, 5
0x140046fd0  call    UserSetLastError
0x140046fd5  jmp     loc_140046D34
0x140046fda  mov     r9, [rcx+40h]
0x140046fde  mov     rcx, [rcx+18h]
0x140046fe2  mov     [rsp+98h+var_60], r12
0x140046fe7  mov     word ptr [rsp+98h+var_68], 0Dh
0x140046fee  mov     dword ptr [rsp+98h+var_70], r13d
0x140046ff3  mov     byte ptr [rsp+98h+var_78], 5
0x140046ff8  call    WPP_RECORDER_AND_TRACE_SF_
0x140046ffd  jmp     loc_140046C03
0x140047002  mov     ecx, 164h; BugCheckCode
0x140047007  call    cs:__imp_KeBugCheck
0x140047014  mov     r9, [rcx+40h]
0x140047018  mov     r8b, sil
0x14004701b  mov     rcx, [rcx+18h]
0x14004701f  mov     [rsp+98h+var_60], r12
0x140047024  mov     word ptr [rsp+98h+var_68], 0Eh
0x14004702b  mov     dword ptr [rsp+98h+var_70], r13d
0x140047030  mov     byte ptr [rsp+98h+var_78], 5
0x140047035  call    WPP_RECORDER_AND_TRACE_SF_
0x14004703a  jmp     loc_140046D34
```
