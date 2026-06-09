# W32CalloutDispatchThunk

- ea: `0x140006710`
- end: `0x1400068b3`
- name: `W32CalloutDispatchThunk`
- size: `419`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update`

## callees

- `0x140001100`
- `0x140002670`
- `0x140003330`
- `0x140006710`
- `0x1400068bc`
- `0x14000d180`
- `0x14000d4c0`
- `0x14000dd80`
- `0x140018f40`
- `0x14001ad40`
- `0x14001ad6c`

## import_xrefs

- `ntoskrnl!PsSetProcessWin32Process` at `0x14000685f`
- `ntoskrnl!PsSetProcessWin32Process` at `0x14000685f`
- `ntoskrnl!PsGetProcessWin32Process` at `0x140006816`
- `ntoskrnl!PsGetProcessWin32Process` at `0x140006816`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140006807`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140006807`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140006870`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140006870`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x1400067e3`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x1400067e3`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x1400067a3`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x1400067a3`

## pseudocode

```c
__int64 __fastcall W32CalloutDispatchThunk(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v5; // esi
  int v6; // ebx
  int v7; // ebx
  int v8; // ebx
  int v9; // ebx
  __int64 ThreadWin32Thread; // rax
  bool v12; // zf
  __int64 v13; // rsi
  __int64 v14; // rdx
  int v15; // ebx
  __int64 v16; // r14
  __int64 v17; // rbp
  __int64 v18; // rsi
  __int64 v19; // rdx
  __int64 ProcessWin32Process; // [rsp+58h] [rbp+20h] BYREF

  v5 = W32SessionAttachAndCalloutDispatch();
  if ( v5 != -1073741796 )
  {
    ExecuteHotpatchTestRuntimeFunction();
    if ( (unsigned int)GetHotpatchTestRuntimeFunctionState() && a2 == 25 )
      *(_QWORD *)(a3 + 16) = 4025479151LL;
    return v5;
  }
  if ( !(_DWORD)a2 )
  {
    v16 = *(_QWORD *)(a3 + 16);
    v17 = **(_QWORD **)(W32GetSessionState() + 24);
    ExEnterCriticalRegionAndAcquireFastMutexUnsafe(v17);
    ProcessWin32Process = PsGetProcessWin32Process(v16);
    v18 = ProcessWin32Process;
    if ( ProcessWin32Process && (*(_DWORD *)(a3 + 24) & 1) != 0 )
    {
      v15 = 1073741851;
    }
    else
    {
      v19 = *(unsigned int *)(a3 + 24);
      LOBYTE(v19) = v19 & 1;
      v15 = DxDdProcessCallout(&ProcessWin32Process, v19);
      if ( v15 >= 0 )
        v15 = PsSetProcessWin32Process(v16, ProcessWin32Process, v18);
    }
    ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v17);
    return (unsigned int)v15;
  }
  v6 = a2 - 1;
  if ( !v6 )
  {
    ThreadWin32Thread = PsGetThreadWin32Thread(KeGetCurrentThread());
    v12 = *(_DWORD *)(a3 + 24) == 0;
    v13 = ThreadWin32Thread;
    ProcessWin32Process = ThreadWin32Thread;
    LOBYTE(v14) = v12;
    v15 = DxDdThreadCallout(&ProcessWin32Process, v14);
    if ( v15 >= 0 )
      PsSetThreadWin32Thread(KeGetCurrentThread(), ProcessWin32Process, v13);
    return (unsigned int)v15;
  }
  v7 = v6 - 23;
  if ( v7 )
  {
    v8 = v7 - 1;
    if ( v8 )
    {
      v9 = v8 - 18;
      if ( v9 )
      {
        if ( v9 != 1 )
          return 3221225659LL;
        DxNotifyProcessThawCallout(*(_QWORD *)(a3 + 16));
      }
      else
      {
        DxNotifyProcessFreezeCallout(*(_QWORD *)(a3 + 16));
      }
    }
    else
    {
      DxGetGpuUsageStatistics(a3 + 16);
    }
  }
  else
  {
    DxGetProcessInterferenceCount(*(_QWORD *)(a3 + 16), *(_QWORD *)(a3 + 24));
  }
  return 0;
}

```

## disassembly

```asm
0x140006710  mov     [rsp+arg_0], rbx
0x140006715  mov     [rsp+arg_8], rbp
0x14000671a  push    rsi
0x14000671b  push    rdi
0x14000671c  push    r14
0x14000671e  sub     rsp, 20h
0x140006722  mov     rdi, r8
0x140006725  mov     rbx, rdx
0x140006728  call    W32SessionAttachAndCalloutDispatch
0x14000672d  mov     esi, eax
0x14000672f  cmp     eax, 0C000001Ch
0x140006734  jnz     loc_140006880
0x14000673a  test    ebx, ebx
0x14000673c  jz      loc_1400067F4
0x140006742  sub     ebx, 1
0x140006745  jz      short loc_14000679A
0x140006747  sub     ebx, 17h
0x14000674a  jz      short loc_140006786
0x14000674c  sub     ebx, 1
0x14000674f  jz      short loc_14000677B
0x140006751  sub     ebx, 12h
0x140006754  jz      short loc_140006770
0x140006756  cmp     ebx, 1
0x140006759  jz      short loc_140006765
0x14000675b  mov     eax, 0C00000BBh
0x140006760  jmp     loc_14000689F
0x140006765  mov     rcx, [rdi+10h]
0x140006769  call    DxNotifyProcessThawCallout
0x14000676e  jmp     short loc_140006793
0x140006770  mov     rcx, [rdi+10h]
0x140006774  call    DxNotifyProcessFreezeCallout
0x140006779  jmp     short loc_140006793
0x14000677b  lea     rcx, [rdi+10h]
0x14000677f  call    DxGetGpuUsageStatistics
0x140006784  jmp     short loc_140006793
0x140006786  mov     rdx, [rdi+18h]
0x14000678a  mov     rcx, [rdi+10h]
0x14000678e  call    DxGetProcessInterferenceCount
0x140006793  xor     eax, eax
0x140006795  jmp     loc_14000689F
0x14000679a  mov     rcx, gs:188h
0x1400067a3  call    cs:__imp_PsGetThreadWin32Thread
0x1400067aa  nop     dword ptr [rax+rax+00h]
0x1400067af  cmp     dword ptr [rdi+18h], 0
0x1400067b3  lea     rcx, [rsp+38h+arg_18]
0x1400067b8  mov     rsi, rax
0x1400067bb  mov     [rsp+38h+arg_18], rax
0x1400067c0  setz    dl
0x1400067c3  call    DxDdThreadCallout
0x1400067c8  mov     ebx, eax
0x1400067ca  test    eax, eax
0x1400067cc  js      loc_14000687C
0x1400067d2  mov     rcx, gs:188h
0x1400067db  mov     r8, rsi
0x1400067de  mov     rdx, [rsp+38h+arg_18]
0x1400067e3  call    cs:__imp_PsSetThreadWin32Thread
0x1400067ea  nop     dword ptr [rax+rax+00h]
0x1400067ef  jmp     loc_14000687C
0x1400067f4  mov     r14, [rdi+10h]
0x1400067f8  call    W32GetSessionState
0x1400067fd  mov     rcx, [rax+18h]
0x140006801  mov     rbp, [rcx]
0x140006804  mov     rcx, rbp
0x140006807  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14000680e  nop     dword ptr [rax+rax+00h]
0x140006813  mov     rcx, r14
0x140006816  call    cs:__imp_PsGetProcessWin32Process
0x14000681d  nop     dword ptr [rax+rax+00h]
0x140006822  mov     [rsp+38h+arg_18], rax
0x140006827  mov     rsi, rax
0x14000682a  test    rax, rax
0x14000682d  jz      short loc_14000683E
0x14000682f  mov     ecx, [rdi+18h]
0x140006832  test    cl, 1
0x140006835  jz      short loc_14000683E
0x140006837  mov     ebx, 4000001Bh
0x14000683c  jmp     short loc_14000686D
0x14000683e  mov     edx, [rdi+18h]
0x140006841  lea     rcx, [rsp+38h+arg_18]
0x140006846  and     dl, 1
0x140006849  call    DxDdProcessCallout
0x14000684e  mov     ebx, eax
0x140006850  test    eax, eax
0x140006852  js      short loc_14000686D
0x140006854  mov     rdx, [rsp+38h+arg_18]
0x140006859  mov     r8, rsi
0x14000685c  mov     rcx, r14
0x14000685f  call    cs:__imp_PsSetProcessWin32Process
0x140006866  nop     dword ptr [rax+rax+00h]
0x14000686b  mov     ebx, eax
0x14000686d  mov     rcx, rbp
0x140006870  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x140006877  nop     dword ptr [rax+rax+00h]
0x14000687c  mov     eax, ebx
0x14000687e  jmp     short loc_14000689F
0x140006880  call    ExecuteHotpatchTestRuntimeFunction
0x140006885  call    GetHotpatchTestRuntimeFunctionState
0x14000688a  test    eax, eax
0x14000688c  jz      short loc_14000689D
0x14000688e  cmp     rbx, 19h
0x140006892  jnz     short loc_14000689D
0x140006894  mov     eax, 0EFEFEFEFh
0x140006899  mov     [rdi+10h], rax
0x14000689d  mov     eax, esi
0x14000689f  mov     rbx, [rsp+38h+arg_0]
0x1400068a4  mov     rbp, [rsp+38h+arg_8]
0x1400068a9  add     rsp, 20h
0x1400068ad  pop     r14
0x1400068af  pop     rdi
0x1400068b0  pop     rsi
0x1400068b1  retn
```
