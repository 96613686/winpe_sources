# HANDLELOCK::vUnlockAndRelease(void)

- ea: `0x14003340c`
- end: `0x140033a65`
- name: `?vUnlockAndRelease@HANDLELOCK@@QEAAXXZ`
- size: `1625`
- prototype: `void __fastcall(HANDLELOCK *__hidden this)`
- caller_count: `7`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140011be0`
- `0x140011f3c`
- `0x14001ae6c`
- `0x1400318f0`
- `0x1400798ac`
- `0x14016aef0`
- `0x1401e2630`

## callees

- `0x140031fa0`
- `0x1400323a0`
- `0x14003340c`
- `0x14003478c`
- `0x1400371c0`
- `0x14007b930`
- `0x140192b70`
- `0x1401abd50`
- `0x1402389c0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1400335bd`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400335bd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400336ea`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400336ea`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14003345f`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14003345f`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x1400334e2`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x1400334e2`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140033447`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140033447`
- `ntoskrnl!PsSetProcessWin32Process` at `0x140033a4c`
- `ntoskrnl!PsSetProcessWin32Process` at `0x140033a4c`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400335cc`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140033846`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400335cc`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140033846`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14003388f`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14003388f`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140033837`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140033837`
- `ntoskrnl!KeIsAttachedProcess` at `0x1400334cb`
- `ntoskrnl!KeIsAttachedProcess` at `0x1400334cb`
- `ntoskrnl!ObfReferenceObject` at `0x140033489`
- `ntoskrnl!ObfReferenceObject` at `0x1400338ca`
- `ntoskrnl!ObfReferenceObject` at `0x140033489`
- `ntoskrnl!ObfReferenceObject` at `0x1400338ca`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14003365e`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14003365e`
- `ntoskrnl!ObfDereferenceObject` at `0x14003353b`
- `ntoskrnl!ObfDereferenceObject` at `0x1400338df`
- `ntoskrnl!ObfDereferenceObject` at `0x14003353b`
- `ntoskrnl!ObfDereferenceObject` at `0x1400338df`
- `ntoskrnl!PsGetProcessWin32Process` at `0x1400338a8`
- `ntoskrnl!PsGetProcessWin32Process` at `0x1400338a8`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400335f4`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140033638`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400335f4`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140033638`

## pseudocode

```c
void __fastcall HANDLELOCK::vUnlockAndRelease(HANDLELOCK *this)
{
  signed int v2; // r15d
  _QWORD *v3; // rdi
  PVOID *CurrentProcessWin32Process; // rax
  volatile signed __int32 *v5; // rbx
  __int64 v6; // rcx
  struct _ERESOURCE *v7; // r14
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // r8d
  struct _KTHREAD *CurrentThread; // r12
  __int64 v12; // rbp
  __int64 *ThreadWin32Thread; // rax
  __int64 v14; // rax
  __int64 v15; // rbp
  void *v17; // rdi
  bool v18; // cl
  char v19; // di
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  __int64 *v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rbx
  __int64 CurrentProcess; // rax
  char ProcessSessionId; // al
  int v30; // ecx
  int v31; // r8d
  __int64 v32; // rcx
  int (*v33)(void); // rax
  char v34; // bl
  __int64 v35; // rdi
  __int64 v36; // rcx
  void (__fastcall *v37)(__int64, __int64); // rax
  __int64 v38; // rdx
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v40; // rcx
  __int64 v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rdi
  __int64 *v44; // rdi
  __int64 v45; // rbx
  __int64 v46; // rax
  unsigned int v47; // ecx
  int v48; // ebx
  int v49; // r8d
  unsigned __int64 v50; // rax
  unsigned __int64 i; // rcx
  __int64 v52; // rdx
  unsigned int v53; // ecx
  unsigned int v54; // ecx
  unsigned int v55; // ecx
  unsigned int v56; // ecx
  unsigned int v57; // ecx
  unsigned int v58; // ecx
  int CurrentWin32kSessionId; // edi
  __int64 CurrentThreadProcess; // rax
  bool v61; // cl
  PVOID *ProcessWin32Process; // rax
  unsigned int v63; // ecx
  unsigned int v64; // ecx
  unsigned int v65; // ecx
  unsigned int v66; // ecx
  unsigned int v67; // ecx
  unsigned int v68; // ecx
  unsigned int v69; // ecx
  unsigned int v70; // ecx
  unsigned int v71; // ecx
  unsigned int v72; // ecx
  unsigned int v73; // ecx
  unsigned int v74; // ecx
  PEPROCESS Process; // [rsp+78h] [rbp+10h] BYREF

  v2 = *(_DWORD *)(*(_QWORD *)this + 8LL) & 0xFFFFFFFE;
  if ( !v2 || v2 == -2147483630 )
    goto LABEL_19;
  v3 = (_QWORD *)*((_QWORD *)this + 2);
  if ( v2 == ((unsigned int)PsGetCurrentProcessId() & 0xFFFFFFFC) )
  {
    CurrentProcessWin32Process = (PVOID *)PsGetCurrentProcessWin32Process();
    v5 = (volatile signed __int32 *)CurrentProcessWin32Process;
    if ( CurrentProcessWin32Process && !*CurrentProcessWin32Process || !CurrentProcessWin32Process )
      goto LABEL_19;
    ObfReferenceObject(*CurrentProcessWin32Process);
    _InterlockedIncrement(v5 + 2);
    goto LABEL_8;
  }
  Process = 0;
  if ( PsLookupProcessByProcessId((HANDLE)v2, &Process) >= 0 )
  {
    ProcessWin32Process = (PVOID *)PsGetProcessWin32Process(Process);
    v5 = (volatile signed __int32 *)ProcessWin32Process;
    if ( ProcessWin32Process && !*ProcessWin32Process )
    {
      v5 = 0;
    }
    else if ( ProcessWin32Process )
    {
      ObfReferenceObject(*ProcessWin32Process);
      _InterlockedIncrement(v5 + 2);
    }
    ObfDereferenceObject(Process);
    if ( v5 )
    {
LABEL_8:
      v7 = (struct _ERESOURCE *)(*v3 + 1512LL);
      GreAcquireSemaphoreCommon<20,void (*)(HSEMAPHORE__ *)>(v6, (HSEMAPHORE)v7);
      --*((_DWORD *)v5 + 15);
      if ( v7 )
      {
        if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
          McTemplateK0pz_EtwWriteTransfer(v9, (unsigned int)LockRelease, v10, (_DWORD)v7, (__int64)L"Hmgr");
        CurrentThread = KeGetCurrentThread();
        v12 = 0;
        if ( !(unsigned __int8)KeIsAttachedProcess(v9, v8)
          || (CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(),
              CurrentThreadProcess = PsGetCurrentThreadProcess(),
              CurrentWin32kSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
        {
          ThreadWin32Thread = (__int64 *)PsGetThreadWin32Thread(CurrentThread);
          if ( ThreadWin32Thread )
            v12 = *ThreadWin32Thread;
        }
        v14 = v12 + 8;
        v15 = -v12;
        if ( (v14 & -(__int64)(v15 != 0)) != 0 && (*(_BYTE *)((v14 & -(__int64)(v15 != 0)) + 0x1C))-- == 1 )
          *(_QWORD *)(v14 & -(__int64)(v15 != 0)) &= ~0x100000uLL;
        GreReleaseSemaphoreSharedInternal(v7);
      }
      v17 = *(void **)v5;
      v18 = (v5[69] & 0x200) != 0;
      if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
      {
        v61 = !v18;
        if ( v61 )
        {
          if ( v61 )
            UserDeleteW32Process((PVOID)v5);
        }
        else
        {
          PsSetProcessWin32Process(*(_QWORD *)v5, 0, v5);
          GreDeleteFastMutex((PVOID)v5);
        }
      }
      ObfDereferenceObject(v17);
    }
  }
LABEL_19:
  v19 = 15;
  v20 = *(unsigned __int8 *)(*(_QWORD *)this + 14LL);
  if ( v20 > 0xF )
  {
    v19 = 23;
    if ( v20 > 0x17 )
    {
      v19 = 24;
      v63 = v20 - 24;
      if ( !v63 )
        goto LABEL_29;
      v64 = v63 - 1;
      if ( !v64 )
      {
        v19 = 25;
        goto LABEL_29;
      }
      v65 = v64 - 1;
      if ( !v65 )
      {
        v19 = 26;
        goto LABEL_29;
      }
      v66 = v65 - 1;
      if ( !v66 )
      {
        v19 = 27;
        goto LABEL_29;
      }
      v67 = v66 - 1;
      if ( !v67 )
      {
        v19 = 28;
        goto LABEL_29;
      }
      v68 = v67 - 1;
      if ( !v68 )
      {
        v19 = 29;
        goto LABEL_29;
      }
      if ( v68 == 1 )
      {
        v19 = 30;
        goto LABEL_29;
      }
    }
    else
    {
      if ( v20 == 23 )
        goto LABEL_29;
      v56 = v20 - 16;
      if ( !v56 )
      {
        v19 = 16;
        goto LABEL_29;
      }
      v57 = v56 - 1;
      if ( !v57 )
      {
        v19 = 17;
        goto LABEL_29;
      }
      v58 = v57 - 1;
      if ( !v58 )
      {
        v19 = 18;
        goto LABEL_29;
      }
      v72 = v58 - 1;
      if ( !v72 )
      {
        v19 = 19;
        goto LABEL_29;
      }
      v73 = v72 - 1;
      if ( !v73 )
      {
        v19 = 20;
        goto LABEL_29;
      }
      v74 = v73 - 1;
      if ( !v74 )
      {
        v19 = 21;
        goto LABEL_29;
      }
      if ( v74 == 1 )
      {
        v19 = 22;
        goto LABEL_29;
      }
    }
  }
  else
  {
    if ( v20 == 15 )
      goto LABEL_29;
    v19 = 7;
    if ( v20 > 7 )
    {
      v19 = 8;
      v53 = v20 - 8;
      if ( !v53 )
        goto LABEL_29;
      v54 = v53 - 1;
      if ( !v54 )
      {
        v19 = 9;
        goto LABEL_29;
      }
      v55 = v54 - 1;
      if ( !v55 )
      {
        v19 = 10;
        goto LABEL_29;
      }
      v69 = v55 - 1;
      if ( !v69 )
      {
        v19 = 11;
        goto LABEL_29;
      }
      v70 = v69 - 1;
      if ( !v70 )
      {
        v19 = 12;
        goto LABEL_29;
      }
      v71 = v70 - 1;
      if ( !v71 )
      {
        v19 = 13;
        goto LABEL_29;
      }
      if ( v71 == 1 )
      {
        v19 = 14;
        goto LABEL_29;
      }
    }
    else
    {
      if ( v20 == 7 )
        goto LABEL_29;
      if ( !*(_BYTE *)(*(_QWORD *)this + 14LL) )
      {
        v19 = 0;
        goto LABEL_29;
      }
      v21 = v20 - 1;
      if ( !v21 )
      {
        v19 = 1;
        goto LABEL_29;
      }
      v22 = v21 - 1;
      if ( !v22 )
      {
        v19 = 2;
        goto LABEL_29;
      }
      v23 = v22 - 1;
      if ( !v23 )
      {
        v19 = 3;
        goto LABEL_29;
      }
      v24 = v23 - 1;
      if ( !v24 )
      {
        v19 = 4;
        goto LABEL_29;
      }
      v47 = v24 - 1;
      if ( !v47 )
      {
        v19 = 5;
        goto LABEL_29;
      }
      if ( v47 == 1 )
      {
        v19 = 6;
        goto LABEL_29;
      }
    }
  }
  v19 = -1;
LABEL_29:
  v25 = (__int64 *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 8LL) + 96LL))(
                     *(_QWORD *)(*((_QWORD *)this + 2) + 8LL),
                     **(unsigned int **)this);
  if ( (Microsoft_Windows_Win32kEnableBits & 0x20000000000LL) != 0 )
  {
    v27 = *v25;
    CurrentProcess = PsGetCurrentProcess(v26);
    ProcessSessionId = PsGetProcessSessionIdEx(CurrentProcess);
    McTemplateK0pqqq_EtwWriteTransfer(v30, (unsigned int)GdiDestroyHandle, v31, v27, v19, ProcessSessionId, v2);
  }
  v32 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v26) + 24);
  v33 = *(int (**)(void))(v32 + 2688);
  if ( v33 )
  {
    if ( v33() >= 0 )
    {
      v34 = *(_BYTE *)(*(_QWORD *)this + 14LL);
      v35 = *(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 8LL) + 96LL))(
                         *(_QWORD *)(*((_QWORD *)this + 2) + 8LL),
                         **(unsigned int **)this);
      v37 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v36) + 24) + 2696LL);
      if ( v37 )
      {
        LOBYTE(v38) = v34;
        v37(v35, v38);
      }
    }
  }
  CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread(v32);
  if ( CurrentThreadWin32Thread )
    v40 = *CurrentThreadWin32Thread;
  else
    v40 = 0;
  v41 = v40 + 8;
  v42 = -v40;
  if ( (v41 & -(__int64)(v42 != 0)) != 0 )
  {
    v43 = *(_QWORD *)((v41 & -(__int64)(v42 != 0)) + 0x148);
    if ( v43 )
    {
      v48 = (unsigned __int16)*(_DWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 2)
                                                                                                 + 8LL)
                                                                                   + 96LL))(
                                           *(_QWORD *)(*((_QWORD *)this + 2) + 8LL),
                                           **(unsigned int **)this);
      v49 = v48
          | (*(_DWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 8LL) + 96LL))(
                          *(_QWORD *)(*((_QWORD *)this + 2) + 8LL),
                          **(unsigned int **)this) >> 8)
          & 0xFF0000;
      v50 = *(_QWORD *)(v43 + 24);
      for ( i = 0; i < v50; ++i )
      {
        v52 = *(_QWORD *)(v43 + 40);
        if ( *(_DWORD *)(v52 + 4 * i) == v49 )
        {
          *(_DWORD *)(v52 + 4 * i) = *(_DWORD *)(v52 + 4 * v50 - 4);
          *(_DWORD *)(*(_QWORD *)(v43 + 40) + 4LL * (*(_QWORD *)(v43 + 24))-- - 4) = 0;
          break;
        }
      }
    }
  }
  *(_BYTE *)(*(_QWORD *)this + 14LL) = 0;
  *(_QWORD *)(*(_QWORD *)this + 16LL) = 0;
  *(_DWORD *)(*(_QWORD *)this + 8LL) = 0;
  v44 = *(__int64 **)(*((_QWORD *)this + 2) + 8LL);
  v45 = *v44;
  v46 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v44 + 96))(v44, **(unsigned int **)this);
  (*(void (__fastcall **)(__int64 *, __int64))(v45 + 56))(v44, v46);
  *((_DWORD *)this + 2) = 0;
  *(_QWORD *)this = 0;
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x14003340c  mov     [rsp+arg_10], rbx
0x140033411  mov     [rsp+arg_18], rbp
0x140033416  push    rsi
0x140033417  push    rdi
0x140033418  push    r12
0x14003341a  push    r14
0x14003341c  push    r15
0x14003341e  sub     rsp, 40h
0x140033422  mov     rax, [rcx]
0x140033425  mov     rsi, rcx
0x140033428  mov     r15d, [rax+8]
0x14003342c  and     r15d, 0FFFFFFFEh
0x140033430  jz      loc_140033547
0x140033436  cmp     r15d, 80000012h
0x14003343d  jz      loc_140033547
0x140033443  mov     rdi, [rcx+10h]
0x140033447  call    cs:__imp_PsGetCurrentProcessId
0x14003344e  nop     dword ptr [rax+rax+00h]
0x140033453  and     eax, 0FFFFFFFCh
0x140033456  cmp     r15d, eax
0x140033459  jnz     loc_14003387E
0x14003345f  call    cs:__imp_PsGetCurrentProcessWin32Process
0x140033466  nop     dword ptr [rax+rax+00h]
0x14003346b  mov     rbx, rax
0x14003346e  test    rax, rax
0x140033471  jz      short loc_14003347D
0x140033473  cmp     qword ptr [rax], 0
0x140033477  jz      loc_140033547
0x14003347d  test    rbx, rbx
0x140033480  jz      loc_140033547
0x140033486  mov     rcx, [rax]; Object
0x140033489  call    cs:__imp_ObfReferenceObject
0x140033490  nop     dword ptr [rax+rax+00h]
0x140033495  lock inc dword ptr [rbx+8]
0x140033499  mov     r14, [rdi]
0x14003349c  add     r14, 5E8h
0x1400334a3  mov     rdx, r14
0x1400334a6  call    ??$GreAcquireSemaphoreCommon@$0BE@P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreAcquireSemaphoreCommon<20,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x1400334ab  dec     dword ptr [rbx+3Ch]
0x1400334ae  test    r14, r14
0x1400334b1  jz      short loc_140033518
0x1400334b3  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, 0
0x1400334ba  jnz     loc_140033A17
0x1400334c0  mov     r12, gs:188h
0x1400334c9  xor     ebp, ebp
0x1400334cb  call    cs:__imp_KeIsAttachedProcess
0x1400334d2  nop     dword ptr [rax+rax+00h]
0x1400334d7  test    al, al
0x1400334d9  jnz     loc_140033830
0x1400334df  mov     rcx, r12
0x1400334e2  call    cs:__imp_PsGetThreadWin32Thread
0x1400334e9  nop     dword ptr [rax+rax+00h]
0x1400334ee  test    rax, rax
0x1400334f1  jz      short loc_1400334F6
0x1400334f3  mov     rbp, [rax]
0x1400334f6  lea     rax, [rbp+8]
0x1400334fa  neg     rbp
0x1400334fd  sbb     rdx, rdx
0x140033500  and     rdx, rax
0x140033503  jz      short loc_140033510
0x140033505  add     byte ptr [rdx+1Ch], 0FFh
0x140033509  jnz     short loc_140033510
0x14003350b  btr     qword ptr [rdx], 14h
0x140033510  mov     rcx, r14; HSEMAPHORE
0x140033513  call    ?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x140033518  mov     ecx, [rbx+114h]
0x14003351e  mov     rdi, [rbx]
0x140033521  shr     ecx, 9
0x140033524  and     cl, 1
0x140033527  or      eax, 0FFFFFFFFh
0x14003352a  lock xadd [rbx+8], eax
0x14003352f  cmp     eax, 1
0x140033532  jz      loc_14003385F
0x140033538  mov     rcx, rdi; Object
0x14003353b  call    cs:__imp_ObfDereferenceObject
0x140033542  nop     dword ptr [rax+rax+00h]
0x140033547  mov     rdx, [rsi]
0x14003354a  mov     edi, 0Fh
0x14003354f  movzx   ecx, byte ptr [rdx+0Eh]
0x140033553  cmp     ecx, edi
0x140033555  ja      loc_1400337D8
0x14003355b  jz      short loc_14003359B
0x14003355d  mov     edi, 7
0x140033562  cmp     ecx, edi
0x140033564  ja      loc_1400337B1
0x14003356a  jz      short loc_14003359B
0x14003356c  test    ecx, ecx
0x14003356e  jz      loc_140033994
0x140033574  sub     ecx, 1
0x140033577  jz      loc_140033787
0x14003357d  sub     ecx, 1
0x140033580  jz      loc_14003398A
0x140033586  sub     ecx, 1
0x140033589  jz      loc_140033980
0x14003358f  sub     ecx, 1
0x140033592  jnz     loc_140033710
0x140033598  lea     edi, [rcx+4]
0x14003359b  mov     rax, [rsi+10h]
0x14003359f  mov     edx, [rdx]
0x1400335a1  mov     rcx, [rax+8]
0x1400335a5  mov     rax, [rcx]
0x1400335a8  mov     rax, [rax+60h]
0x1400335ac  call    _guard_dispatch_icall
0x1400335b1  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits+5, 2
0x1400335b8  jz      short loc_1400335F4
0x1400335ba  mov     rbx, [rax]
0x1400335bd  call    cs:__imp_PsGetCurrentProcess
0x1400335c4  nop     dword ptr [rax+rax+00h]
0x1400335c9  mov     rcx, rax
0x1400335cc  call    cs:__imp_PsGetProcessSessionIdEx
0x1400335d3  nop     dword ptr [rax+rax+00h]
0x1400335d8  mov     [rsp+68h+var_38], r15d
0x1400335dd  lea     rdx, GdiDestroyHandle
0x1400335e4  mov     [rsp+68h+var_40], eax
0x1400335e8  mov     r9, rbx
0x1400335eb  mov     dword ptr [rsp+68h+var_48], edi
0x1400335ef  call    McTemplateK0pqqq_EtwWriteTransfer
0x1400335f4  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1400335fb  nop     dword ptr [rax+rax+00h]
0x140033600  mov     rcx, [rax+18h]
0x140033604  mov     rax, [rcx+0A80h]
0x14003360b  test    rax, rax
0x14003360e  jz      short loc_14003365E
0x140033610  call    _guard_dispatch_icall
0x140033615  test    eax, eax
0x140033617  js      short loc_14003365E
0x140033619  mov     rax, [rsi+10h]
0x14003361d  mov     rdx, [rsi]
0x140033620  mov     rcx, [rax+8]
0x140033624  mov     bl, [rdx+0Eh]
0x140033627  mov     edx, [rdx]
0x140033629  mov     rax, [rcx]
0x14003362c  mov     rax, [rax+60h]
0x140033630  call    _guard_dispatch_icall
0x140033635  mov     rdi, [rax]
0x140033638  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14003363f  nop     dword ptr [rax+rax+00h]
0x140033644  mov     r8, [rax+18h]
0x140033648  mov     rax, [r8+0A88h]
0x14003364f  test    rax, rax
0x140033652  jz      short loc_14003365E
0x140033654  mov     dl, bl
0x140033656  mov     rcx, rdi
0x140033659  call    _guard_dispatch_icall
0x14003365e  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140033665  nop     dword ptr [rax+rax+00h]
0x14003366a  test    rax, rax
0x14003366d  jz      loc_14003380E
0x140033673  mov     rcx, [rax]
0x140033676  lea     rax, [rcx+8]
0x14003367a  neg     rcx
0x14003367d  sbb     rdi, rdi
0x140033680  and     rdi, rax
0x140033683  jz      short loc_140033695
0x140033685  mov     rdi, [rdi+148h]
0x14003368c  test    rdi, rdi
0x14003368f  jnz     loc_140033721
0x140033695  mov     rax, [rsi]
0x140033698  mov     byte ptr [rax+0Eh], 0
0x14003369c  mov     rax, [rsi]
0x14003369f  mov     qword ptr [rax+10h], 0
0x1400336a7  mov     rax, [rsi]
0x1400336aa  mov     dword ptr [rax+8], 0
0x1400336b1  mov     rax, [rsi+10h]
0x1400336b5  mov     rdx, [rsi]
0x1400336b8  mov     rdi, [rax+8]
0x1400336bc  mov     edx, [rdx]
0x1400336be  mov     rcx, rdi
0x1400336c1  mov     rbx, [rdi]
0x1400336c4  mov     rax, [rbx+60h]
0x1400336c8  call    _guard_dispatch_icall
0x1400336cd  mov     rdx, rax
0x1400336d0  mov     rcx, rdi
0x1400336d3  mov     rax, [rbx+38h]
0x1400336d7  call    _guard_dispatch_icall
0x1400336dc  mov     dword ptr [rsi+8], 0
0x1400336e3  mov     qword ptr [rsi], 0
0x1400336ea  call    cs:__imp_KeLeaveCriticalRegion
0x1400336f1  nop     dword ptr [rax+rax+00h]
0x1400336f6  lea     r11, [rsp+68h+var_28]
0x1400336fb  mov     rbx, [r11+40h]
0x1400336ff  mov     rbp, [r11+48h]
0x140033703  mov     rsp, r11
0x140033706  pop     r15
0x140033708  pop     r14
0x14003370a  pop     r12
0x14003370c  pop     rdi
0x14003370d  pop     rsi
0x14003370e  retn
0x140033710  sub     ecx, 1
0x140033713  jnz     loc_14003381F
0x140033719  lea     edi, [rcx+5]
0x14003371c  jmp     loc_14003359B
0x140033721  mov     rax, [rsi+10h]
0x140033725  mov     rdx, [rsi]
0x140033728  mov     rcx, [rax+8]
0x14003372c  mov     edx, [rdx]
0x14003372e  mov     rax, [rcx]
0x140033731  mov     rax, [rax+60h]
0x140033735  call    _guard_dispatch_icall
0x14003373a  mov     rdx, [rsi]
0x14003373d  mov     ebx, [rax]
0x14003373f  mov     rax, [rsi+10h]
0x140033743  mov     edx, [rdx]
0x140033745  movzx   ebx, bx
0x140033748  mov     rcx, [rax+8]
0x14003374c  mov     rax, [rcx]
0x14003374f  mov     rax, [rax+60h]
0x140033753  call    _guard_dispatch_icall
0x140033758  mov     r8d, [rax]
0x14003375b  shr     r8d, 8
0x14003375f  and     r8d, 0FF0000h
0x140033766  or      r8d, ebx
0x140033769  mov     rax, [rdi+18h]
0x14003376d  xor     ecx, ecx
0x14003376f  cmp     rcx, rax
0x140033772  jnb     loc_140033695
0x140033778  mov     rdx, [rdi+28h]
0x14003377c  cmp     [rdx+rcx*4], r8d
0x140033780  jz      short loc_140033791
0x140033782  inc     rcx
0x140033785  jmp     short loc_14003376F
0x140033787  mov     edi, 1
0x14003378c  jmp     loc_14003359B
0x140033791  mov     eax, [rdx+rax*4-4]
0x140033795  mov     [rdx+rcx*4], eax
0x140033798  mov     rcx, [rdi+18h]
0x14003379c  mov     rax, [rdi+28h]
0x1400337a0  mov     dword ptr [rax+rcx*4-4], 0
0x1400337a8  dec     qword ptr [rdi+18h]
0x1400337ac  jmp     loc_140033695
0x1400337b1  mov     edi, 8
0x1400337b6  sub     ecx, edi
0x1400337b8  jz      loc_14003359B
0x1400337be  sub     ecx, 1
0x1400337c1  jz      loc_140033976
0x1400337c7  sub     ecx, 1
0x1400337ca  jnz     loc_140033948
0x1400337d0  lea     edi, [rcx+0Ah]
0x1400337d3  jmp     loc_14003359B
0x1400337d8  mov     edi, 17h
0x1400337dd  cmp     ecx, edi
0x1400337df  ja      loc_1400338FD
0x1400337e5  jz      loc_14003359B
0x1400337eb  sub     ecx, 10h
0x1400337ee  jnz     short loc_1400337F8
0x1400337f0  lea     edi, [rcx+10h]
0x1400337f3  jmp     loc_14003359B
0x1400337f8  sub     ecx, 1
0x1400337fb  jz      short loc_140033815
0x1400337fd  sub     ecx, 1
0x140033800  jnz     loc_14003395F
0x140033806  lea     edi, [rcx+12h]
0x140033809  jmp     loc_14003359B
0x14003380e  xor     ecx, ecx
0x140033810  jmp     loc_140033676
0x140033815  mov     edi, 11h
0x14003381a  jmp     loc_14003359B
0x14003381f  cmp     ecx, 1
0x140033822  jnz     loc_140033A0F
0x140033828  lea     edi, [rcx+5]
0x14003382b  jmp     loc_14003359B
0x140033830  call    W32GetCurrentWin32kSessionId
0x140033835  mov     edi, eax
0x140033837  call    cs:__imp_PsGetCurrentThreadProcess
0x14003383e  nop     dword ptr [rax+rax+00h]
0x140033843  mov     rcx, rax
0x140033846  call    cs:__imp_PsGetProcessSessionIdEx
0x14003384d  nop     dword ptr [rax+rax+00h]
0x140033852  cmp     edi, eax
0x140033854  jz      loc_1400334DF
0x14003385a  jmp     loc_1400334F6
0x14003385f  xor     cl, 1
0x140033862  jz      loc_140033A44
0x140033868  cmp     cl, 1
0x14003386b  jnz     loc_140033538
0x140033871  mov     rcx, rbx; Buffer
0x140033874  call    UserDeleteW32Process
0x140033879  jmp     loc_140033538
0x14003387e  movsxd  rcx, r15d; ProcessId
0x140033881  lea     rdx, [rsp+68h+Process]; Process
0x140033886  mov     [rsp+68h+Process], 0
0x14003388f  call    cs:__imp_PsLookupProcessByProcessId
0x140033896  nop     dword ptr [rax+rax+00h]
0x14003389b  test    eax, eax
0x14003389d  js      loc_140033547
0x1400338a3  mov     rcx, [rsp+68h+Process]
0x1400338a8  call    cs:__imp_PsGetProcessWin32Process
0x1400338af  nop     dword ptr [rax+rax+00h]
0x1400338b4  mov     rbx, rax
0x1400338b7  test    rax, rax
0x1400338ba  jz      short loc_1400338C2
0x1400338bc  cmp     qword ptr [rax], 0
0x1400338c0  jz      short loc_1400338F9
0x1400338c2  test    rbx, rbx
0x1400338c5  jz      short loc_1400338DA
0x1400338c7  mov     rcx, [rax]; Object
0x1400338ca  call    cs:__imp_ObfReferenceObject
0x1400338d1  nop     dword ptr [rax+rax+00h]
0x1400338d6  lock inc dword ptr [rbx+8]
  ... truncated ...
```
