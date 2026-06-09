# ClientThreadSetup

- ea: `0x180051800`
- end: `0x180051a7e`
- name: `ClientThreadSetup`
- size: `638`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800517d0`

## callees

- `0x180051800`
- `0x180053630`
- `0x18005ce38`
- `0x18005ed68`
- `0x180069c48`
- `0x180096dc5`
- `0x1800a2010`

## import_xrefs

- `win32u!NtUserRegisterLPK` at `0x180051a39`
- `win32u!NtUserRegisterLPK` at `0x180051a39`
- `win32u!NtUserRemoteConnectState` at `0x18005192e`
- `win32u!NtUserRemoteConnectState` at `0x18005192e`
- `win32u!NtUserInitializeClientPfnArrays` at `0x18009e94e`
- `win32u!NtUserInitializeClientPfnArrays` at `0x18009e94e`
- `win32u!NtUserProcessConnect` at `0x18009e845`
- `win32u!NtUserProcessConnect` at `0x18009e845`
- `win32u!gDispatchTableValues` at `0x18009e82a`
- `win32u!NtUserGetThreadDesktop` at `0x180051947`
- `win32u!NtUserGetThreadDesktop` at `0x180051947`
- `win32u!NtUserGetProcessUIContextInformation` at `0x180051998`
- `win32u!NtUserGetProcessUIContextInformation` at `0x180051998`
- `ntdll!RtlSetLastWin32Error` at `0x180051859`
- `ntdll!RtlSetLastWin32Error` at `0x180051859`
- `ntdll!RtlRetrieveNtUserPfn` at `0x18009e924`
- `ntdll!RtlRetrieveNtUserPfn` at `0x18009e924`
- `ntdll!RtlEnterCriticalSection` at `0x180051830`
- `ntdll!RtlEnterCriticalSection` at `0x180051830`
- `ntdll!RtlLeaveCriticalSection` at `0x18005187b`
- `ntdll!RtlLeaveCriticalSection` at `0x18005187b`
- `ntdll!RtlAllocateHeap` at `0x1800518cf`
- `ntdll!RtlAllocateHeap` at `0x18009e971`
- `ntdll!RtlAllocateHeap` at `0x1800518cf`
- `ntdll!RtlAllocateHeap` at `0x18009e971`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005193f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005193f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800519cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800519cd`
- `api-ms-win-core-processthreads-l1-1-1!GetProcessMitigationPolicy` at `0x1800519e5`
- `api-ms-win-core-processthreads-l1-1-1!GetProcessMitigationPolicy` at `0x1800519e5`
- `api-ms-win-core-appinit-l1-1-0!LoadAppInitDlls` at `0x1800519b8`
- `api-ms-win-core-appinit-l1-1-0!LoadAppInitDlls` at `0x1800519b8`
- `GDI32!GdiProcessSetup` at `0x18005184a`
- `GDI32!GdiProcessSetup` at `0x18005184a`

## pseudocode

```c
__int64 ClientThreadSetup()
{
  __int64 v0; // rsi
  int v1; // edi
  struct _TEB *v3; // rbx
  int v4; // eax
  PVOID Heap; // rax
  SIZE_T v6; // rbx
  int v7; // edi
  DWORD CurrentThreadId; // eax
  HANDLE CurrentProcess; // rax
  __int64 *v10; // rax
  __int64 *v11; // rcx
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int64 v22; // rcx
  void (__fastcall *v23)(_QWORD, _QWORD, _QWORD); // rax
  int v24; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v25; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v26; // [rsp+290h] [rbp+190h] BYREF
  __int64 v27; // [rsp+298h] [rbp+198h] BYREF
  __int64 v28; // [rsp+2A0h] [rbp+1A0h] BYREF

  v0 = 4;
  if ( g_systemCallFilterId == 7 )
  {
    LODWORD(v26) = 0;
    CurrentProcess = GetCurrentProcess();
    if ( (unsigned int)GetProcessMitigationPolicy(CurrentProcess, 11, &v26, 4) )
    {
      g_systemCallFilterId = v26 & 0xF;
      _InterlockedCompareExchange((volatile signed __int32 *)&g_systemCallFilterId, g_systemCallFilterId, 7);
    }
  }
  RtlEnterCriticalSection(&gcsAccelCache);
  v1 = gfFirstThread;
  if ( gfFirstThread )
  {
    gfFirstThread = 0;
    if ( (int)GdiProcessSetup() < 0 )
      goto LABEL_4;
  }
  RtlLeaveCriticalSection(&gcsAccelCache);
  v3 = NtCurrentTeb();
  if ( (v3->Win32ClientInfo[0] & 8) != 0 )
    return 0;
  LODWORD(v3->Win32ClientInfo[34]) = 2;
  v4 = *(_DWORD *)&gfServerProcess;
  if ( *(_DWORD *)&gfServerProcess )
  {
    if ( v1 )
    {
      memset_0(&v24, 0, 0x248u);
      v24 = gDispatchTableValues;
      if ( (int)NtUserProcessConnect(-1, 576, &v24) < 0 )
        return 0;
      v10 = &gSharedInfo;
      v11 = &v25;
      do
      {
        v12 = *((_OWORD *)v11 + 1);
        *(_OWORD *)v10 = *(_OWORD *)v11;
        v13 = *((_OWORD *)v11 + 2);
        *((_OWORD *)v10 + 1) = v12;
        v14 = *((_OWORD *)v11 + 3);
        *((_OWORD *)v10 + 2) = v13;
        v15 = *((_OWORD *)v11 + 4);
        *((_OWORD *)v10 + 3) = v14;
        v16 = *((_OWORD *)v11 + 5);
        *((_OWORD *)v10 + 4) = v15;
        v17 = *((_OWORD *)v11 + 6);
        *((_OWORD *)v10 + 5) = v16;
        v18 = *((_OWORD *)v11 + 7);
        v11 += 16;
        *((_OWORD *)v10 + 6) = v17;
        *((_OWORD *)v10 + 7) = v18;
        v10 += 16;
        --v0;
      }
      while ( v0 );
      v19 = *((_OWORD *)v11 + 1);
      *(_OWORD *)v10 = *(_OWORD *)v11;
      v20 = *((_OWORD *)v11 + 2);
      *((_OWORD *)v10 + 1) = v19;
      v21 = *((_OWORD *)v11 + 3);
      *((_OWORD *)v10 + 2) = v20;
      *((_OWORD *)v10 + 3) = v21;
      gpsi = v25;
      v4 = *(_DWORD *)&gfServerProcess;
    }
    if ( v4 )
    {
      if ( v1 )
      {
        v28 = 0;
        v27 = 0;
        v26 = 0;
        if ( (int)RtlRetrieveNtUserPfn(&v28, &v27, &v26) < 0
          || (int)NtUserInitializeClientPfnArrays(v28, v27, v26, hmodUser) < 0 )
        {
          goto LABEL_4;
        }
      }
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MoveCLIENTINFORWIntoTEB>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MoveCLIENTINFORWIntoTEB>::GetImpl'::`2'::impl) )
  {
    v3->Win32ClientInfo[35] = (SIZE_T)&v3->Win32ClientInfo[36];
  }
  else
  {
    Heap = RtlAllocateHeap(pUserHeap, 8u, 0x10u);
    v3->Win32ClientInfo[35] = (SIZE_T)Heap;
    if ( !Heap )
      goto LABEL_4;
  }
  v3->Win32ClientInfo[0] |= 8uLL;
  if ( v1 )
  {
    v7 = NtUserRemoteConnectState();
    if ( v7 == 1 || (unsigned int)InitClientDrawing() )
    {
      CurrentThreadId = GetCurrentThreadId();
      gfSystemInitialized = NtUserGetThreadDesktop(CurrentThreadId) != 0;
      if ( dword_1800C9C78 )
        NtUserRegisterLPK();
      if ( !*(_DWORD *)&gfServerProcess && NtCurrentTeb()->Win32ClientInfo[4] )
        goto LABEL_20;
      pdiLocal = (struct tagDESKTOPINFO *)RtlAllocateHeap(pUserHeap, 8u, 0x48u);
      if ( pdiLocal )
      {
        NtCurrentTeb()->Win32ClientInfo[4] = (SIZE_T)pdiLocal;
        if ( !*(_DWORD *)&gfServerProcess )
        {
LABEL_20:
          NtUserGetProcessUIContextInformation(-1, &guiContextInfo);
          if ( !*(_DWORD *)&gfServerProcess && !gfLogonProcess )
            LoadAppInitDlls();
          goto LABEL_13;
        }
        if ( v7 == 1 || (unsigned int)LoadCursorsAndIcons() )
        {
          InitOemXlateTables();
          goto LABEL_20;
        }
      }
    }
LABEL_4:
    RtlSetLastWin32Error(0xEu);
    return 0;
  }
  if ( *(_DWORD *)&gfServerProcess )
    NtCurrentTeb()->Win32ClientInfo[4] = (SIZE_T)pdiLocal;
LABEL_13:
  v3->Win32ClientInfo[26] = (SIZE_T)&gdwRegisteredClasses;
  v6 = NtCurrentTeb()->Win32ClientInfo[61];
  if ( v6 )
  {
    if ( *(_QWORD *)v6 )
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))v6)(0, 0, 0);
    v22 = *(_QWORD *)(v6 + 24);
    if ( v22 )
    {
      v23 = *(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(v22 + 8);
      if ( v23 )
        v23(0, 0, 0);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180051800  mov     [rsp-8+arg_18], rbx
0x180051805  push    rbp
0x180051806  push    rsi
0x180051807  push    rdi
0x180051808  lea     rbp, [rsp-170h]
0x180051810  sub     rsp, 270h
0x180051817  cmp     cs:?g_systemCallFilterId@@3KA, 7; ulong g_systemCallFilterId
0x18005181e  mov     esi, 4
0x180051823  jz      loc_1800519C3
0x180051829  lea     rcx, ?gcsAccelCache@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180051830  call    cs:__imp_RtlEnterCriticalSection
0x180051836  mov     edi, cs:?gfFirstThread@@3HA; int gfFirstThread
0x18005183c  test    edi, edi
0x18005183e  jz      short loc_180051874
0x180051840  mov     cs:?gfFirstThread@@3HA, 0; int gfFirstThread
0x18005184a  call    cs:__imp_GdiProcessSetup
0x180051850  test    eax, eax
0x180051852  jns     short loc_180051874
0x180051854  mov     ecx, 0Eh; LastError
0x180051859  call    cs:__imp_RtlSetLastWin32Error
0x18005185f  xor     eax, eax
0x180051861  mov     rbx, [rsp+280h+arg_18]
0x180051869  add     rsp, 270h
0x180051870  pop     rdi
0x180051871  pop     rsi
0x180051872  pop     rbp
0x180051873  retn
0x180051874  lea     rcx, ?gcsAccelCache@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18005187b  call    cs:__imp_RtlLeaveCriticalSection
0x180051881  mov     rbx, gs:30h
0x18005188a  test    byte ptr [rbx+800h], 8
0x180051891  jnz     short loc_18005185F
0x180051893  mov     dword ptr [rbx+910h], 2
0x18005189d  mov     eax, cs:gfServerProcess
0x1800518a3  test    eax, eax
0x1800518a5  jnz     loc_18009E810
0x1800518ab  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MoveCLIENTINFORWIntoTEB@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MoveCLIENTINFORWIntoTEB@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MoveCLIENTINFORWIntoTEB> `wil::Feature<__WilFeatureTraits_Feature_MoveCLIENTINFORWIntoTEB>::GetImpl(void)'::`2'::impl
0x1800518b2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MoveCLIENTINFORWIntoTEB@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MoveCLIENTINFORWIntoTEB>::__private_IsEnabled(void)
0x1800518b7  test    al, al
0x1800518b9  jnz     loc_180051A14
0x1800518bf  mov     rcx, cs:pUserHeap; HeapHandle
0x1800518c6  mov     edx, 8; Flags
0x1800518cb  lea     r8d, [rdx+8]; Size
0x1800518cf  call    cs:__imp_RtlAllocateHeap
0x1800518d5  mov     [rbx+918h], rax
0x1800518dc  test    rax, rax
0x1800518df  jz      loc_180051854
0x1800518e5  or      qword ptr [rbx+800h], 8
0x1800518ed  test    edi, edi
0x1800518ef  jnz     short loc_18005192E
0x1800518f1  cmp     cs:gfServerProcess, edi
0x1800518f7  jnz     loc_180051A44
0x1800518fd  lea     rax, ?gdwRegisteredClasses@@3KA; ulong gdwRegisteredClasses
0x180051904  mov     [rbx+8D0h], rax
0x18005190b  mov     rax, gs:30h
0x180051914  mov     rbx, [rax+9E8h]
0x18005191b  test    rbx, rbx
0x18005191e  jnz     loc_180051A60
0x180051924  mov     eax, 1
0x180051929  jmp     loc_180051861
0x18005192e  call    cs:__imp_NtUserRemoteConnectState
0x180051934  mov     edi, eax
0x180051936  cmp     eax, 1
0x180051939  jnz     loc_180051A27
0x18005193f  call    cs:__imp_GetCurrentThreadId
0x180051945  mov     ecx, eax
0x180051947  call    cs:__imp_NtUserGetThreadDesktop
0x18005194d  xor     ecx, ecx
0x18005194f  test    rax, rax
0x180051952  setnz   cl
0x180051955  mov     cs:?gfSystemInitialized@@3HA, ecx; int gfSystemInitialized
0x18005195b  mov     ecx, cs:dword_1800C9C78
0x180051961  test    ecx, ecx
0x180051963  jnz     loc_180051A39
0x180051969  cmp     cs:gfServerProcess, 0
0x180051970  jnz     loc_18009E961
0x180051976  mov     rax, gs:30h
0x18005197f  cmp     qword ptr [rax+820h], 0
0x180051987  jz      loc_18009E961
0x18005198d  lea     rdx, ?guiContextInfo@@3UPROCESS_UICONTEXT_INFORMATION@@A; PROCESS_UICONTEXT_INFORMATION guiContextInfo
0x180051994  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180051998  call    cs:__imp_NtUserGetProcessUIContextInformation
0x18005199e  cmp     cs:gfServerProcess, 0
0x1800519a5  jnz     loc_1800518FD
0x1800519ab  cmp     cs:?gfLogonProcess@@3HA, 0; int gfLogonProcess
0x1800519b2  jnz     loc_1800518FD
0x1800519b8  call    cs:__imp_LoadAppInitDlls
0x1800519be  jmp     loc_1800518FD
0x1800519c3  mov     dword ptr [rbp+180h+arg_0], 0
0x1800519cd  call    cs:__imp_GetCurrentProcess
0x1800519d3  mov     r9, rsi
0x1800519d6  lea     r8, [rbp+180h+arg_0]
0x1800519dd  mov     rcx, rax
0x1800519e0  mov     edx, 0Bh
0x1800519e5  call    cs:__imp_GetProcessMitigationPolicy
0x1800519eb  test    eax, eax
0x1800519ed  jz      loc_180051829
0x1800519f3  mov     ecx, dword ptr [rbp+180h+arg_0]
0x1800519f9  mov     eax, 7
0x1800519fe  and     ecx, 0Fh
0x180051a01  mov     cs:?g_systemCallFilterId@@3KA, ecx; ulong g_systemCallFilterId
0x180051a07  lock cmpxchg cs:?g_systemCallFilterId@@3KA, ecx; ulong g_systemCallFilterId
0x180051a0f  jmp     loc_180051829
0x180051a14  lea     rax, [rbx+920h]
0x180051a1b  mov     [rbx+918h], rax
0x180051a22  jmp     loc_1800518E5
0x180051a27  call    ?InitClientDrawing@@YAHXZ; InitClientDrawing(void)
0x180051a2c  test    eax, eax
0x180051a2e  jz      loc_180051854
0x180051a34  jmp     loc_18005193F
0x180051a39  call    cs:__imp_NtUserRegisterLPK
0x180051a3f  jmp     loc_180051969
0x180051a44  mov     rcx, gs:30h
0x180051a4d  mov     rax, cs:?pdiLocal@@3PEAUtagDESKTOPINFO@@EA; tagDESKTOPINFO * pdiLocal
0x180051a54  mov     [rcx+820h], rax
0x180051a5b  jmp     loc_1800518FD
0x180051a60  mov     rax, [rbx]
0x180051a63  test    rax, rax
0x180051a66  jz      loc_18009E9C8
0x180051a6c  xor     r8d, r8d
0x180051a6f  xor     edx, edx
0x180051a71  xor     ecx, ecx
0x180051a73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051a78  nop
0x180051a79  jmp     loc_18009E9C8
0x18009e810  test    edi, edi
0x18009e812  jz      loc_18009E8DE
0x18009e818  xor     edx, edx; Val
0x18009e81a  lea     rcx, [rsp+280h+var_260]; void *
0x18009e81f  mov     r8d, 248h; Size
0x18009e825  call    memset_0
0x18009e82a  mov     rax, cs:__imp_gDispatchTableValues
0x18009e831  lea     r8, [rsp+280h+var_260]
0x18009e836  mov     edx, 240h
0x18009e83b  mov     ecx, [rax]
0x18009e83d  mov     [rsp+280h+var_260], ecx
0x18009e841  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18009e845  call    cs:__imp_NtUserProcessConnect
0x18009e84b  test    eax, eax
0x18009e84d  js      loc_18005185F
0x18009e853  lea     rax, gSharedInfo
0x18009e85a  mov     edx, 80h
0x18009e85f  lea     rcx, [rsp+280h+var_258]
0x18009e864  movups  xmm0, xmmword ptr [rcx]
0x18009e867  movups  xmm1, xmmword ptr [rcx+10h]
0x18009e86b  movups  xmmword ptr [rax], xmm0
0x18009e86e  movups  xmm0, xmmword ptr [rcx+20h]
0x18009e872  movups  xmmword ptr [rax+10h], xmm1
0x18009e876  movups  xmm1, xmmword ptr [rcx+30h]
0x18009e87a  movups  xmmword ptr [rax+20h], xmm0
0x18009e87e  movups  xmm0, xmmword ptr [rcx+40h]
0x18009e882  movups  xmmword ptr [rax+30h], xmm1
0x18009e886  movups  xmm1, xmmword ptr [rcx+50h]
0x18009e88a  movups  xmmword ptr [rax+40h], xmm0
0x18009e88e  movups  xmm0, xmmword ptr [rcx+60h]
0x18009e892  movups  xmmword ptr [rax+50h], xmm1
0x18009e896  movups  xmm1, xmmword ptr [rcx+70h]
0x18009e89a  add     rcx, rdx
0x18009e89d  movups  xmmword ptr [rax+60h], xmm0
0x18009e8a1  movups  xmmword ptr [rax+70h], xmm1
0x18009e8a5  add     rax, rdx
0x18009e8a8  sub     rsi, 1
0x18009e8ac  jnz     short loc_18009E864
0x18009e8ae  movups  xmm0, xmmword ptr [rcx]
0x18009e8b1  movups  xmm1, xmmword ptr [rcx+10h]
0x18009e8b5  movups  xmmword ptr [rax], xmm0
0x18009e8b8  movups  xmm0, xmmword ptr [rcx+20h]
0x18009e8bc  movups  xmmword ptr [rax+10h], xmm1
0x18009e8c0  movups  xmm1, xmmword ptr [rcx+30h]
0x18009e8c4  movups  xmmword ptr [rax+20h], xmm0
0x18009e8c8  movups  xmmword ptr [rax+30h], xmm1
0x18009e8cc  mov     rax, [rsp+280h+var_258]
0x18009e8d1  mov     cs:gpsi, rax
0x18009e8d8  mov     eax, cs:gfServerProcess
0x18009e8de  test    eax, eax
0x18009e8e0  jz      loc_1800518AB
0x18009e8e6  test    edi, edi
0x18009e8e8  jz      loc_1800518AB
0x18009e8ee  lea     r8, [rbp+180h+arg_0]
0x18009e8f5  mov     [rbp+180h+arg_10], 0
0x18009e900  lea     rdx, [rbp+180h+arg_8]
0x18009e907  mov     [rbp+180h+arg_8], 0
0x18009e912  lea     rcx, [rbp+180h+arg_10]
0x18009e919  mov     [rbp+180h+arg_0], 0
0x18009e924  call    cs:__imp_RtlRetrieveNtUserPfn
0x18009e92a  test    eax, eax
0x18009e92c  js      loc_180051854
0x18009e932  mov     r9, cs:hmodUser
0x18009e939  mov     r8, [rbp+180h+arg_0]
0x18009e940  mov     rdx, [rbp+180h+arg_8]
0x18009e947  mov     rcx, [rbp+180h+arg_10]
0x18009e94e  call    cs:__imp_NtUserInitializeClientPfnArrays
0x18009e954  test    eax, eax
0x18009e956  js      loc_180051854
0x18009e95c  jmp     loc_1800518AB
0x18009e961  mov     rcx, cs:pUserHeap; HeapHandle
0x18009e968  mov     edx, 8; Flags
0x18009e96d  lea     r8d, [rdx+40h]; Size
0x18009e971  call    cs:__imp_RtlAllocateHeap
0x18009e977  mov     cs:?pdiLocal@@3PEAUtagDESKTOPINFO@@EA, rax; tagDESKTOPINFO * pdiLocal
0x18009e97e  test    rax, rax
0x18009e981  jz      loc_180051854
0x18009e987  mov     rcx, gs:30h
0x18009e990  mov     rax, cs:?pdiLocal@@3PEAUtagDESKTOPINFO@@EA; tagDESKTOPINFO * pdiLocal
0x18009e997  mov     [rcx+820h], rax
0x18009e99e  cmp     cs:gfServerProcess, 0
0x18009e9a5  jz      loc_18005198D
0x18009e9ab  cmp     edi, 1
0x18009e9ae  jz      short loc_18009E9BD
0x18009e9b0  call    ?LoadCursorsAndIcons@@YAHXZ; LoadCursorsAndIcons(void)
0x18009e9b5  test    eax, eax
0x18009e9b7  jz      loc_180051854
0x18009e9bd  call    ?InitOemXlateTables@@YAXXZ; InitOemXlateTables(void)
0x18009e9c2  nop
0x18009e9c3  jmp     loc_18005198D
0x18009e9c8  mov     rcx, [rbx+18h]
0x18009e9cc  test    rcx, rcx
0x18009e9cf  jz      loc_180051924
0x18009e9d5  mov     rax, [rcx+8]
0x18009e9d9  test    rax, rax
0x18009e9dc  jz      loc_180051924
0x18009e9e2  xor     r8d, r8d
0x18009e9e5  xor     edx, edx
0x18009e9e7  xor     ecx, ecx
0x18009e9e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e9ee  nop
0x18009e9ef  jmp     loc_180051924
```
