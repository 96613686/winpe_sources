# NtMITDispatchCompletion

- ea: `0x14006e550`
- end: `0x14006ea6f`
- name: `NtMITDispatchCompletion`
- size: `1311`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140029fe8`
- `0x14006e550`
- `0x14006ed20`
- `0x14006ef38`
- `0x1400718f0`
- `0x1401581c0`
- `0x1401aa4fc`
- `0x1401b7d70`
- `0x140238bf0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14006e57e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006e57e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006e5be`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006e5be`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14006e58f`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14006e58f`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14006e5b2`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14006e5b2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14006e59b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14006e59b`
- `ntoskrnl!DbgkWerCaptureLiveKernelDump` at `0x14006e8fa`
- `ntoskrnl!DbgkWerCaptureLiveKernelDump` at `0x14006e974`
- `ntoskrnl!DbgkWerCaptureLiveKernelDump` at `0x14006e9ea`
- `ntoskrnl!DbgkWerCaptureLiveKernelDump` at `0x14006e8fa`
- `ntoskrnl!DbgkWerCaptureLiveKernelDump` at `0x14006e974`
- `ntoskrnl!DbgkWerCaptureLiveKernelDump` at `0x14006e9ea`
- `ntoskrnl!KeBugCheck` at `0x14006e93c`
- `ntoskrnl!KeBugCheck` at `0x14006ea37`
- `ntoskrnl!KeBugCheck` at `0x14006e93c`
- `ntoskrnl!KeBugCheck` at `0x14006ea37`
- `ntoskrnl!ZwAssociateWaitCompletionPacket` at `0x14006e69f`
- `ntoskrnl!ZwAssociateWaitCompletionPacket` at `0x14006e7fe`
- `ntoskrnl!ZwAssociateWaitCompletionPacket` at `0x14006e69f`
- `ntoskrnl!ZwAssociateWaitCompletionPacket` at `0x14006e7fe`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14006e6f2`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14006e839`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14006e6f2`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14006e839`
- `WIN32K!W32GetUserSessionState` at `0x14006e567`
- `WIN32K!W32GetUserSessionState` at `0x14006e633`
- `WIN32K!W32GetUserSessionState` at `0x14006e567`
- `WIN32K!W32GetUserSessionState` at `0x14006e633`

## string_xrefs

- `0x14006e7ad`: `HandleInputThreadSignal`

## pseudocode

```c
__int64 __fastcall NtMITDispatchCompletion(__int64 a1, unsigned int a2)
{
  int v3; // r14d
  __int64 v4; // rbx
  __int64 v5; // rsi
  unsigned int CurrentThreadId; // eax
  unsigned int v7; // edi
  int v8; // edx
  int v9; // r8d
  CTouchProcessor *v10; // rcx
  char v11; // si
  int v12; // edx
  __int64 v13; // rbx
  int v14; // r8d
  unsigned int v15; // r14d
  __int64 v16; // rdi
  __int64 v17; // rbp
  __int64 v18; // rbx
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v20; // rcx
  __int64 v22; // rdi
  __int64 KernelIocpWcp; // rax
  __int64 v24; // r14
  void (__fastcall *v25)(_QWORD); // rax
  __int64 v26; // rbx
  __int64 *v27; // rax
  __int64 v28; // rcx
  __int64 v29; // [rsp+B0h] [rbp+18h] BYREF

  v3 = a1;
  v4 = *(_QWORD *)(W32GetUserSessionState(a1) + 18856);
  v5 = v4 + 8;
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(v4 + 8, 0);
  CurrentThreadId = (unsigned int)PsGetCurrentThreadId();
  LODWORD(v4) = *(_DWORD *)(v4 + 40);
  v7 = CurrentThreadId;
  ExReleasePushLockSharedEx(v5, 0);
  KeLeaveCriticalRegion();
  if ( v7 == (_DWORD)v4 )
  {
    v10 = WPP_GLOBAL_Control;
    v11 = 1;
    if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || (LOBYTE(v8) = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
    {
      LOBYTE(v8) = 0;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
      || (LOBYTE(v9) = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
    {
      LOBYTE(v9) = 0;
    }
    if ( (_BYTE)v8 || (_BYTE)v9 )
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v8,
        v9,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        5,
        2,
        13,
        (__int64)WPP_34bc8fbd5710336976da4e93dfcb98ad_Traceguids);
    v13 = *(_QWORD *)(W32GetUserSessionState(v10) + 19288);
    if ( v3 == 0x80000000 )
    {
      v15 = a2;
      if ( a2 >= *(_DWORD *)(v13 + 2568) )
      {
        LODWORD(v29) = 0x20000;
        MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 3580);
        DbgkWerCaptureLiveKernelDump(L"win32kbase.sys", 400, a2, *(unsigned int *)(v13 + 2568), 0, 0, 0, 0, 0);
      }
      else
      {
        v16 = v13 + 40LL * a2;
        v17 = *(_QWORD *)(v16 + 24);
        if ( v17 )
        {
          if ( (int)ZwAssociateWaitCompletionPacket(
                      v17,
                      *(_QWORD *)(v13 + 2904),
                      *(_QWORD *)(v16 + 8),
                      v15,
                      0xFFFFFFFF80000000uLL,
                      0,
                      0,
                      0) < 0 )
            KeBugCheck(0x164u);
          if ( v17 == *(_QWORD *)(v16 + 24) )
          {
            InputTraceLogging::ThreadLockedPerfRegion::ThreadLockedPerfRegion(
              (InputTraceLogging::ThreadLockedPerfRegion *)&v29,
              "HandleSensorDispatcherSignal",
              0);
            (*(void (__fastcall **)(_QWORD, _QWORD))(v16 + 32))(*(_QWORD *)(v16 + 16), *(_QWORD *)(v16 + 40));
            v18 = v29;
            if ( v29 )
            {
              CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread();
              if ( CurrentThreadWin32Thread )
                v20 = *CurrentThreadWin32Thread;
              else
                v20 = 0;
              *(_QWORD *)(v20 + 376) = *(_QWORD *)(v18 + 48);
              InputTraceLogging::ThreadLockedPerfRegion::Cleanup((InputTraceLogging::ThreadLockedPerfRegion *)&v29);
            }
          }
          else
          {
            IOCPDispatcher::SensorIOCPWCP::Cleanup((IOCPDispatcher::SensorIOCPWCP *)(v16 + 8));
          }
        }
        else
        {
          LODWORD(v29) = 0x20000;
          MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 3598);
          DbgkWerCaptureLiveKernelDump(L"win32kbase.sys", 400, v16 + 8, 0, 0, 0, 0, 0, 0);
        }
      }
    }
    else if ( v3 == -2147483647 )
    {
      if ( a2 < *(_DWORD *)(v13 + 2896) )
      {
        v22 = 32LL * a2;
        if ( *(_QWORD *)(v22 + v13 + 2584) )
        {
          InputTraceLogging::ThreadLockedPerfRegion::ThreadLockedPerfRegion(
            (InputTraceLogging::ThreadLockedPerfRegion *)&v29,
            "HandleInputThreadSignal",
            0);
          KernelIocpWcp = *(_QWORD *)(v22 + v13 + 2584);
          v24 = *(_QWORD *)(v22 + v13 + 2576);
          if ( !KernelIocpWcp && (KernelIocpWcp = CreateKernelIocpWcp()) == 0
            || (int)ZwAssociateWaitCompletionPacket(
                      KernelIocpWcp,
                      *(_QWORD *)(v13 + 2904),
                      v24,
                      a2,
                      -2147483647,
                      0,
                      0,
                      0) < 0 )
          {
            KeBugCheck(0x164u);
          }
          v25 = *(void (__fastcall **)(_QWORD))(v22 + v13 + 2592);
          if ( v25 )
            v25(*(_QWORD *)(v22 + v13 + 2600));
          v26 = v29;
          if ( v29 )
          {
            v27 = (__int64 *)PsGetCurrentThreadWin32Thread();
            if ( v27 )
              v28 = *v27;
            else
              v28 = 0;
            *(_QWORD *)(v28 + 376) = *(_QWORD *)(v26 + 48);
            InputTraceLogging::ThreadLockedPerfRegion::Cleanup((InputTraceLogging::ThreadLockedPerfRegion *)&v29);
          }
        }
      }
    }
    else
    {
      DbgkWerCaptureLiveKernelDump(L"win32kbase.sys", 400, v3, a2, 0, 0, 0, 0, 0);
    }
    if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || (LOBYTE(v12) = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
    {
      LOBYTE(v12) = 0;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED || !*((_WORD *)WPP_GLOBAL_Control + 36) )
      v11 = 0;
    if ( (_BYTE)v12 || v11 )
    {
      LOBYTE(v14) = v11;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v12,
        v14,
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
0x14006e550  push    rbx
0x14006e552  push    rbp
0x14006e553  push    rsi
0x14006e554  push    rdi
0x14006e555  push    r12
0x14006e557  push    r13
0x14006e559  push    r14
0x14006e55b  push    r15
0x14006e55d  sub     rsp, 58h
0x14006e561  mov     rbp, rdx
0x14006e564  mov     r14, rcx
0x14006e567  call    cs:__imp_W32GetUserSessionState
0x14006e56e  nop     dword ptr [rax+rax+00h]
0x14006e573  mov     rbx, [rax+49A8h]
0x14006e57a  lea     rsi, [rbx+8]
0x14006e57e  call    cs:__imp_KeEnterCriticalRegion
0x14006e585  nop     dword ptr [rax+rax+00h]
0x14006e58a  xor     edx, edx
0x14006e58c  mov     rcx, rsi
0x14006e58f  call    cs:__imp_ExAcquirePushLockSharedEx
0x14006e596  nop     dword ptr [rax+rax+00h]
0x14006e59b  call    cs:__imp_PsGetCurrentThreadId
0x14006e5a2  nop     dword ptr [rax+rax+00h]
0x14006e5a7  mov     ebx, [rbx+28h]
0x14006e5aa  xor     edx, edx
0x14006e5ac  mov     rcx, rsi
0x14006e5af  mov     rdi, rax
0x14006e5b2  call    cs:__imp_ExReleasePushLockSharedEx
0x14006e5b9  nop     dword ptr [rax+rax+00h]
0x14006e5be  call    cs:__imp_KeLeaveCriticalRegion
0x14006e5c5  nop     dword ptr [rax+rax+00h]
0x14006e5ca  cmp     edi, ebx
0x14006e5cc  jnz     loc_14006E9FB
0x14006e5d2  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e5d9  lea     rax, WPP_GLOBAL_Control
0x14006e5e0  xor     r15d, r15d
0x14006e5e3  mov     sil, 1
0x14006e5e6  lea     r13d, [r15+2]
0x14006e5ea  cmp     rcx, rax
0x14006e5ed  jz      short loc_14006E5FB
0x14006e5ef  mov     eax, [rcx+2Ch]
0x14006e5f2  test    r13b, al
0x14006e5f5  jnz     loc_14006E985
0x14006e5fb  mov     dl, r15b
0x14006e5fe  lea     rdi, WPP_RECORDER_INITIALIZED
0x14006e605  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14006e60c  jz      short loc_14006E618
0x14006e60e  mov     r8b, sil
0x14006e611  cmp     [rcx+48h], r15w
0x14006e616  jnz     short loc_14006E61B
0x14006e618  mov     r8b, r15b
0x14006e61b  lea     r12, WPP_34bc8fbd5710336976da4e93dfcb98ad_Traceguids
0x14006e622  test    dl, dl
0x14006e624  jnz     loc_14006EA0A
0x14006e62a  test    r8b, r8b
0x14006e62d  jnz     loc_14006EA0A
0x14006e633  call    cs:__imp_W32GetUserSessionState
0x14006e63a  nop     dword ptr [rax+rax+00h]
0x14006e63f  mov     rcx, 0FFFFFFFF80000000h
0x14006e646  mov     rbx, [rax+4B58h]
0x14006e64d  cmp     r14d, ecx
0x14006e650  jnz     loc_14006E778
0x14006e656  mov     r14d, ebp
0x14006e659  cmp     ebp, [rbx+0A08h]
0x14006e65f  jnb     loc_14006E997
0x14006e665  lea     rax, [r14+r14*4]
0x14006e669  lea     rdi, [rbx+rax*8]
0x14006e66d  mov     rbp, [rdi+18h]
0x14006e671  test    rbp, rbp
0x14006e674  jz      loc_14006E8AA
0x14006e67a  mov     r8, [rdi+8]
0x14006e67e  mov     r9d, r14d
0x14006e681  mov     rdx, [rbx+0B58h]
0x14006e688  mov     [rsp+98h+var_60], r15
0x14006e68d  mov     [rsp+98h+var_68], r15
0x14006e692  mov     dword ptr [rsp+98h+var_70], r15d
0x14006e697  mov     [rsp+98h+var_78], rcx
0x14006e69c  mov     rcx, rbp
0x14006e69f  call    cs:__imp_ZwAssociateWaitCompletionPacket
0x14006e6a6  nop     dword ptr [rax+rax+00h]
0x14006e6ab  test    eax, eax
0x14006e6ad  js      loc_14006EA32
0x14006e6b3  cmp     rbp, [rdi+18h]
0x14006e6b7  jnz     loc_14006E91B
0x14006e6bd  xor     r8d, r8d; struct InputTraceLogging::ThreadLockedPerfRegion *
0x14006e6c0  lea     rdx, aHandlesensordi; "HandleSensorDispatcherSignal"
0x14006e6c7  lea     rcx, [rsp+98h+arg_10]; this
0x14006e6cf  call    ??0ThreadLockedPerfRegion@InputTraceLogging@@QEAA@PEBDPEBU01@@Z; InputTraceLogging::ThreadLockedPerfRegion::ThreadLockedPerfRegion(char const *,InputTraceLogging::ThreadLockedPerfRegion const *)
0x14006e6d4  mov     rax, [rdi+20h]
0x14006e6d8  mov     rdx, [rdi+28h]
0x14006e6dc  mov     rcx, [rdi+10h]
0x14006e6e0  call    _guard_dispatch_icall
0x14006e6e5  mov     rbx, [rsp+98h+arg_10]
0x14006e6ed  test    rbx, rbx
0x14006e6f0  jz      short loc_14006E722
0x14006e6f2  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14006e6f9  nop     dword ptr [rax+rax+00h]
0x14006e6fe  test    rax, rax
0x14006e701  jz      loc_14006E90B
0x14006e707  mov     rcx, [rax]
0x14006e70a  mov     rax, [rbx+30h]
0x14006e70e  mov     [rcx+178h], rax
0x14006e715  lea     rcx, [rsp+98h+arg_10]; this
0x14006e71d  call    ?Cleanup@ThreadLockedPerfRegion@InputTraceLogging@@AEAAXXZ; InputTraceLogging::ThreadLockedPerfRegion::Cleanup(void)
0x14006e722  lea     rdi, WPP_RECORDER_INITIALIZED
0x14006e729  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e730  lea     rax, WPP_GLOBAL_Control
0x14006e737  cmp     rcx, rax
0x14006e73a  jnz     loc_14006E88C
0x14006e740  mov     dl, r15b
0x14006e743  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14006e74a  jnz     loc_14006E87C
0x14006e750  mov     sil, r15b
0x14006e753  test    dl, dl
0x14006e755  jnz     loc_14006EA44
0x14006e75b  test    sil, sil
0x14006e75e  jnz     loc_14006EA44
0x14006e764  xor     eax, eax
0x14006e766  add     rsp, 58h
0x14006e76a  pop     r15
0x14006e76c  pop     r14
0x14006e76e  pop     r13
0x14006e770  pop     r12
0x14006e772  pop     rdi
0x14006e773  pop     rsi
0x14006e774  pop     rbp
0x14006e775  pop     rbx
0x14006e776  retn
0x14006e778  mov     r12, 0FFFFFFFF80000001h
0x14006e77f  cmp     r14d, r12d
0x14006e782  jnz     loc_14006E949
0x14006e788  cmp     ebp, [rbx+0B50h]
0x14006e78e  jnb     loc_14006E870
0x14006e794  mov     ebp, ebp
0x14006e796  mov     edi, ebp
0x14006e798  shl     rdi, 5
0x14006e79c  cmp     [rdi+rbx+0A18h], r15
0x14006e7a4  jz      loc_14006E869
0x14006e7aa  xor     r8d, r8d; struct InputTraceLogging::ThreadLockedPerfRegion *
0x14006e7ad  lea     rdx, aHandleinputthr; "HandleInputThreadSignal"
0x14006e7b4  lea     rcx, [rsp+98h+arg_10]; this
0x14006e7bc  call    ??0ThreadLockedPerfRegion@InputTraceLogging@@QEAA@PEBDPEBU01@@Z; InputTraceLogging::ThreadLockedPerfRegion::ThreadLockedPerfRegion(char const *,InputTraceLogging::ThreadLockedPerfRegion const *)
0x14006e7c1  mov     rax, [rdi+rbx+0A18h]
0x14006e7c9  mov     r14, [rdi+rbx+0A10h]
0x14006e7d1  test    rax, rax
0x14006e7d4  jz      loc_14006E929
0x14006e7da  mov     rdx, [rbx+0B58h]
0x14006e7e1  mov     r9, rbp
0x14006e7e4  mov     [rsp+98h+var_60], r15
0x14006e7e9  mov     r8, r14
0x14006e7ec  mov     [rsp+98h+var_68], r15
0x14006e7f1  mov     rcx, rax
0x14006e7f4  mov     dword ptr [rsp+98h+var_70], r15d
0x14006e7f9  mov     [rsp+98h+var_78], r12
0x14006e7fe  call    cs:__imp_ZwAssociateWaitCompletionPacket
0x14006e805  nop     dword ptr [rax+rax+00h]
0x14006e80a  test    eax, eax
0x14006e80c  js      loc_14006E937
0x14006e812  mov     rax, [rdi+rbx+0A20h]
0x14006e81a  test    rax, rax
0x14006e81d  jz      short loc_14006E82C
0x14006e81f  mov     rcx, [rdi+rbx+0A28h]
0x14006e827  call    _guard_dispatch_icall
0x14006e82c  mov     rbx, [rsp+98h+arg_10]
0x14006e834  test    rbx, rbx
0x14006e837  jz      short loc_14006E869
0x14006e839  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14006e840  nop     dword ptr [rax+rax+00h]
0x14006e845  test    rax, rax
0x14006e848  jz      loc_14006E913
0x14006e84e  mov     rcx, [rax]
0x14006e851  mov     rax, [rbx+30h]
0x14006e855  mov     [rcx+178h], rax
0x14006e85c  lea     rcx, [rsp+98h+arg_10]; this
0x14006e864  call    ?Cleanup@ThreadLockedPerfRegion@InputTraceLogging@@AEAAXXZ; InputTraceLogging::ThreadLockedPerfRegion::Cleanup(void)
0x14006e869  lea     rdi, WPP_RECORDER_INITIALIZED
0x14006e870  lea     r12, WPP_34bc8fbd5710336976da4e93dfcb98ad_Traceguids
0x14006e877  jmp     loc_14006E729
0x14006e87c  cmp     [rcx+48h], r15w
0x14006e881  jnz     loc_14006E753
0x14006e887  jmp     loc_14006E750
0x14006e88c  mov     eax, [rcx+2Ch]
0x14006e88f  test    r13b, al
0x14006e892  jz      loc_14006E740
0x14006e898  cmp     byte ptr [rcx+29h], 5
0x14006e89c  mov     dl, sil
0x14006e89f  jnb     loc_14006E743
0x14006e8a5  jmp     loc_14006E740
0x14006e8aa  mov     dword ptr [rsp+98h+arg_10], 20000h
0x14006e8b5  lea     rcx, aIxptelassert; "IXPTelAssert"
0x14006e8bc  mov     edx, dword ptr [rsp+98h+arg_10]
0x14006e8c3  mov     r8d, 0E0Eh
0x14006e8c9  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x14006e8ce  mov     [rsp+98h+var_58], r15d
0x14006e8d3  lea     r8, [rdi+8]
0x14006e8d7  mov     [rsp+98h+var_60], r15
0x14006e8dc  lea     rcx, aWin32kbaseSys; "win32kbase.sys"
0x14006e8e3  mov     [rsp+98h+var_68], r15
0x14006e8e8  xor     r9d, r9d
0x14006e8eb  mov     [rsp+98h+var_70], r15
0x14006e8f0  mov     edx, 190h
0x14006e8f5  mov     [rsp+98h+var_78], r15
0x14006e8fa  call    cs:__imp_DbgkWerCaptureLiveKernelDump
0x14006e901  nop     dword ptr [rax+rax+00h]
0x14006e906  jmp     loc_14006E722
0x14006e90b  mov     rcx, r15
0x14006e90e  jmp     loc_14006E70A
0x14006e913  mov     rcx, r15
0x14006e916  jmp     loc_14006E851
0x14006e91b  lea     rcx, [rdi+8]; this
0x14006e91f  call    ?Cleanup@SensorIOCPWCP@IOCPDispatcher@@QEAAXXZ; IOCPDispatcher::SensorIOCPWCP::Cleanup(void)
0x14006e924  jmp     loc_14006E722
0x14006e929  call    CreateKernelIocpWcp
0x14006e92e  test    rax, rax
0x14006e931  jnz     loc_14006E7DA
0x14006e937  mov     ecx, 164h; BugCheckCode
0x14006e93c  call    cs:__imp_KeBugCheck
0x14006e949  mov     [rsp+98h+var_58], r15d
0x14006e94e  lea     rcx, aWin32kbaseSys; "win32kbase.sys"
0x14006e955  mov     [rsp+98h+var_60], r15
0x14006e95a  mov     edx, 190h
0x14006e95f  mov     [rsp+98h+var_68], r15
0x14006e964  mov     [rsp+98h+var_70], r15
0x14006e969  mov     r9d, ebp
0x14006e96c  movsxd  r8, r14d
0x14006e96f  mov     [rsp+98h+var_78], r15
0x14006e974  call    cs:__imp_DbgkWerCaptureLiveKernelDump
0x14006e97b  nop     dword ptr [rax+rax+00h]
0x14006e980  jmp     loc_14006E870
0x14006e985  cmp     byte ptr [rcx+29h], 5
0x14006e989  mov     dl, sil
0x14006e98c  jb      loc_14006E5FB
0x14006e992  jmp     loc_14006E5FE
0x14006e997  mov     dword ptr [rsp+98h+arg_10], 20000h
0x14006e9a2  lea     rcx, aIxptelassert; "IXPTelAssert"
0x14006e9a9  mov     edx, dword ptr [rsp+98h+arg_10]
0x14006e9b0  mov     r8d, 0DFCh
0x14006e9b6  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x14006e9bb  mov     r9d, [rbx+0A08h]
0x14006e9c2  lea     rcx, aWin32kbaseSys; "win32kbase.sys"
0x14006e9c9  mov     [rsp+98h+var_58], r15d
0x14006e9ce  mov     r8, r14
0x14006e9d1  mov     [rsp+98h+var_60], r15
0x14006e9d6  mov     edx, 190h
0x14006e9db  mov     [rsp+98h+var_68], r15
0x14006e9e0  mov     [rsp+98h+var_70], r15
0x14006e9e5  mov     [rsp+98h+var_78], r15
0x14006e9ea  call    cs:__imp_DbgkWerCaptureLiveKernelDump
0x14006e9f1  nop     dword ptr [rax+rax+00h]
0x14006e9f6  jmp     loc_14006E729
0x14006e9fb  mov     ecx, 5
0x14006ea00  call    UserSetLastError
0x14006ea05  jmp     loc_14006E764
0x14006ea0a  mov     r9, [rcx+40h]
0x14006ea0e  mov     rcx, [rcx+18h]
0x14006ea12  mov     [rsp+98h+var_60], r12
0x14006ea17  mov     word ptr [rsp+98h+var_68], 0Dh
0x14006ea1e  mov     dword ptr [rsp+98h+var_70], r13d
0x14006ea23  mov     byte ptr [rsp+98h+var_78], 5
0x14006ea28  call    WPP_RECORDER_AND_TRACE_SF_
0x14006ea2d  jmp     loc_14006E633
0x14006ea32  mov     ecx, 164h; BugCheckCode
0x14006ea37  call    cs:__imp_KeBugCheck
0x14006ea44  mov     r9, [rcx+40h]
0x14006ea48  mov     r8b, sil
0x14006ea4b  mov     rcx, [rcx+18h]
0x14006ea4f  mov     [rsp+98h+var_60], r12
0x14006ea54  mov     word ptr [rsp+98h+var_68], 0Eh
0x14006ea5b  mov     dword ptr [rsp+98h+var_70], r13d
0x14006ea60  mov     byte ptr [rsp+98h+var_78], 5
0x14006ea65  call    WPP_RECORDER_AND_TRACE_SF_
0x14006ea6a  jmp     loc_14006E764
```
