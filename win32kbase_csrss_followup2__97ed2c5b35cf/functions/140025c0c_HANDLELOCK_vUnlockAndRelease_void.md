# HANDLELOCK::vUnlockAndRelease(void)

- ea: `0x140025c0c`
- end: `0x140026265`
- name: `?vUnlockAndRelease@HANDLELOCK@@QEAAXXZ`
- size: `1625`
- prototype: `void __fastcall(HANDLELOCK *__hidden this)`
- caller_count: `7`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000f718`
- `0x140024fc0`
- `0x140027f3c`
- `0x14002ad20`
- `0x14002b07c`
- `0x14003d090`
- `0x1401e1af0`

## callees

- `0x14001d160`
- `0x140025a30`
- `0x140025c0c`
- `0x140027600`
- `0x140031bf4`
- `0x14004a0d0`
- `0x140190760`
- `0x1401ab150`
- `0x140238240`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x140025dbd`
- `ntoskrnl!PsGetCurrentProcess` at `0x140025dbd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140025eea`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140025eea`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140025c5f`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140025c5f`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x140025ce2`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x140025ce2`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140025c47`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140025c47`
- `ntoskrnl!PsSetProcessWin32Process` at `0x14002624c`
- `ntoskrnl!PsSetProcessWin32Process` at `0x14002624c`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140025dcc`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140026046`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140025dcc`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140026046`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14002608f`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14002608f`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140026037`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140026037`
- `ntoskrnl!KeIsAttachedProcess` at `0x140025ccb`
- `ntoskrnl!KeIsAttachedProcess` at `0x140025ccb`
- `ntoskrnl!ObfReferenceObject` at `0x140025c89`
- `ntoskrnl!ObfReferenceObject` at `0x1400260ca`
- `ntoskrnl!ObfReferenceObject` at `0x140025c89`
- `ntoskrnl!ObfReferenceObject` at `0x1400260ca`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140025e5e`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140025e5e`
- `ntoskrnl!ObfDereferenceObject` at `0x140025d3b`
- `ntoskrnl!ObfDereferenceObject` at `0x1400260df`
- `ntoskrnl!ObfDereferenceObject` at `0x140025d3b`
- `ntoskrnl!ObfDereferenceObject` at `0x1400260df`
- `ntoskrnl!PsGetProcessWin32Process` at `0x1400260a8`
- `ntoskrnl!PsGetProcessWin32Process` at `0x1400260a8`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140025df4`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140025e38`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140025df4`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140025e38`

## pseudocode

```c
void __fastcall HANDLELOCK::vUnlockAndRelease(HANDLELOCK *this)
{
  signed int v2; // r15d
  _QWORD *v3; // rdi
  PVOID *CurrentProcessWin32Process; // rax
  volatile signed __int32 *v5; // rbx
  __int64 v6; // rcx
  HSEMAPHORE v7; // r14
  int v8; // ecx
  int v9; // r8d
  struct _KTHREAD *CurrentThread; // r12
  __int64 v11; // rbp
  __int64 *ThreadWin32Thread; // rax
  __int64 v13; // rax
  __int64 v14; // rbp
  void *v16; // rdi
  bool v17; // cl
  char v18; // di
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  __int64 *v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // rbx
  __int64 CurrentProcess; // rax
  char ProcessSessionId; // al
  int v31; // ecx
  int v32; // r8d
  int (*v33)(void); // rax
  char v34; // bl
  __int64 v35; // rdi
  void (__fastcall *v36)(__int64, __int64); // rax
  __int64 v37; // rdx
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v39; // rcx
  __int64 v40; // rax
  __int64 v41; // rcx
  __int64 v42; // rdi
  __int64 *v43; // rdi
  __int64 v44; // rbx
  __int64 v45; // rax
  unsigned int v46; // ecx
  int v47; // ebx
  int v48; // r8d
  unsigned __int64 v49; // rax
  unsigned __int64 i; // rcx
  __int64 v51; // rdx
  unsigned int v52; // ecx
  unsigned int v53; // ecx
  unsigned int v54; // ecx
  unsigned int v55; // ecx
  unsigned int v56; // ecx
  unsigned int v57; // ecx
  int CurrentWin32kSessionId; // edi
  __int64 CurrentThreadProcess; // rax
  bool v60; // cl
  PVOID *ProcessWin32Process; // rax
  unsigned int v62; // ecx
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
      v7 = (HSEMAPHORE)(*v3 + 1512LL);
      GreAcquireSemaphoreCommon<20,void (*)(HSEMAPHORE__ *)>(v6, v7);
      --*((_DWORD *)v5 + 15);
      if ( v7 )
      {
        if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
          McTemplateK0pz_EtwWriteTransfer(v8, (unsigned int)LockRelease, v9, (_DWORD)v7, (__int64)L"Hmgr");
        CurrentThread = KeGetCurrentThread();
        v11 = 0;
        if ( !(unsigned __int8)KeIsAttachedProcess()
          || (CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(),
              CurrentThreadProcess = PsGetCurrentThreadProcess(),
              CurrentWin32kSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
        {
          ThreadWin32Thread = (__int64 *)PsGetThreadWin32Thread(CurrentThread);
          if ( ThreadWin32Thread )
            v11 = *ThreadWin32Thread;
        }
        v13 = v11 + 8;
        v14 = -v11;
        if ( (v13 & -(__int64)(v14 != 0)) != 0 && (*(_BYTE *)((v13 & -(__int64)(v14 != 0)) + 0x1C))-- == 1 )
          *(_QWORD *)(v13 & -(__int64)(v14 != 0)) &= ~0x100000uLL;
        GreReleaseSemaphoreSharedInternal(v7);
      }
      v16 = *(void **)v5;
      v17 = (v5[69] & 0x200) != 0;
      if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
      {
        v60 = !v17;
        if ( v60 )
        {
          if ( v60 )
            UserDeleteW32Process((PVOID)v5);
        }
        else
        {
          PsSetProcessWin32Process(*(_QWORD *)v5, 0, v5);
          GreDeleteFastMutex((PVOID)v5);
        }
      }
      ObfDereferenceObject(v16);
    }
  }
LABEL_19:
  v18 = 15;
  v19 = *(unsigned __int8 *)(*(_QWORD *)this + 14LL);
  if ( v19 > 0xF )
  {
    v18 = 23;
    if ( v19 > 0x17 )
    {
      v18 = 24;
      v62 = v19 - 24;
      if ( !v62 )
        goto LABEL_29;
      v63 = v62 - 1;
      if ( !v63 )
      {
        v18 = 25;
        goto LABEL_29;
      }
      v64 = v63 - 1;
      if ( !v64 )
      {
        v18 = 26;
        goto LABEL_29;
      }
      v65 = v64 - 1;
      if ( !v65 )
      {
        v18 = 27;
        goto LABEL_29;
      }
      v66 = v65 - 1;
      if ( !v66 )
      {
        v18 = 28;
        goto LABEL_29;
      }
      v67 = v66 - 1;
      if ( !v67 )
      {
        v18 = 29;
        goto LABEL_29;
      }
      if ( v67 == 1 )
      {
        v18 = 30;
        goto LABEL_29;
      }
    }
    else
    {
      if ( v19 == 23 )
        goto LABEL_29;
      v55 = v19 - 16;
      if ( !v55 )
      {
        v18 = 16;
        goto LABEL_29;
      }
      v56 = v55 - 1;
      if ( !v56 )
      {
        v18 = 17;
        goto LABEL_29;
      }
      v57 = v56 - 1;
      if ( !v57 )
      {
        v18 = 18;
        goto LABEL_29;
      }
      v71 = v57 - 1;
      if ( !v71 )
      {
        v18 = 19;
        goto LABEL_29;
      }
      v72 = v71 - 1;
      if ( !v72 )
      {
        v18 = 20;
        goto LABEL_29;
      }
      v73 = v72 - 1;
      if ( !v73 )
      {
        v18 = 21;
        goto LABEL_29;
      }
      if ( v73 == 1 )
      {
        v18 = 22;
        goto LABEL_29;
      }
    }
  }
  else
  {
    if ( v19 == 15 )
      goto LABEL_29;
    v18 = 7;
    if ( v19 > 7 )
    {
      v18 = 8;
      v52 = v19 - 8;
      if ( !v52 )
        goto LABEL_29;
      v53 = v52 - 1;
      if ( !v53 )
      {
        v18 = 9;
        goto LABEL_29;
      }
      v54 = v53 - 1;
      if ( !v54 )
      {
        v18 = 10;
        goto LABEL_29;
      }
      v68 = v54 - 1;
      if ( !v68 )
      {
        v18 = 11;
        goto LABEL_29;
      }
      v69 = v68 - 1;
      if ( !v69 )
      {
        v18 = 12;
        goto LABEL_29;
      }
      v70 = v69 - 1;
      if ( !v70 )
      {
        v18 = 13;
        goto LABEL_29;
      }
      if ( v70 == 1 )
      {
        v18 = 14;
        goto LABEL_29;
      }
    }
    else
    {
      if ( v19 == 7 )
        goto LABEL_29;
      if ( !*(_BYTE *)(*(_QWORD *)this + 14LL) )
      {
        v18 = 0;
        goto LABEL_29;
      }
      v20 = v19 - 1;
      if ( !v20 )
      {
        v18 = 1;
        goto LABEL_29;
      }
      v21 = v20 - 1;
      if ( !v21 )
      {
        v18 = 2;
        goto LABEL_29;
      }
      v22 = v21 - 1;
      if ( !v22 )
      {
        v18 = 3;
        goto LABEL_29;
      }
      v23 = v22 - 1;
      if ( !v23 )
      {
        v18 = 4;
        goto LABEL_29;
      }
      v46 = v23 - 1;
      if ( !v46 )
      {
        v18 = 5;
        goto LABEL_29;
      }
      if ( v46 == 1 )
      {
        v18 = 6;
        goto LABEL_29;
      }
    }
  }
  v18 = -1;
LABEL_29:
  v24 = (__int64 *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 8LL) + 96LL))(
                     *(_QWORD *)(*((_QWORD *)this + 2) + 8LL),
                     **(unsigned int **)this);
  if ( (Microsoft_Windows_Win32kEnableBits & 0x20000000000LL) != 0 )
  {
    v28 = *v24;
    CurrentProcess = PsGetCurrentProcess(v26, v25, v27);
    ProcessSessionId = PsGetProcessSessionIdEx(CurrentProcess);
    McTemplateK0pqqq_EtwWriteTransfer(v31, (unsigned int)GdiDestroyHandle, v32, v28, v18, ProcessSessionId, v2);
  }
  v33 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 24) + 2688LL);
  if ( v33 )
  {
    if ( v33() >= 0 )
    {
      v34 = *(_BYTE *)(*(_QWORD *)this + 14LL);
      v35 = *(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 8LL) + 96LL))(
                         *(_QWORD *)(*((_QWORD *)this + 2) + 8LL),
                         **(unsigned int **)this);
      v36 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 24) + 2696LL);
      if ( v36 )
      {
        LOBYTE(v37) = v34;
        v36(v35, v37);
      }
    }
  }
  CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread();
  if ( CurrentThreadWin32Thread )
    v39 = *CurrentThreadWin32Thread;
  else
    v39 = 0;
  v40 = v39 + 8;
  v41 = -v39;
  if ( (v40 & -(__int64)(v41 != 0)) != 0 )
  {
    v42 = *(_QWORD *)((v40 & -(__int64)(v41 != 0)) + 0x148);
    if ( v42 )
    {
      v47 = (unsigned __int16)*(_DWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 2)
                                                                                                 + 8LL)
                                                                                   + 96LL))(
                                           *(_QWORD *)(*((_QWORD *)this + 2) + 8LL),
                                           **(unsigned int **)this);
      v48 = v47
          | (*(_DWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 8LL) + 96LL))(
                          *(_QWORD *)(*((_QWORD *)this + 2) + 8LL),
                          **(unsigned int **)this) >> 8)
          & 0xFF0000;
      v49 = *(_QWORD *)(v42 + 24);
      for ( i = 0; i < v49; ++i )
      {
        v51 = *(_QWORD *)(v42 + 40);
        if ( *(_DWORD *)(v51 + 4 * i) == v48 )
        {
          *(_DWORD *)(v51 + 4 * i) = *(_DWORD *)(v51 + 4 * v49 - 4);
          *(_DWORD *)(*(_QWORD *)(v42 + 40) + 4LL * (*(_QWORD *)(v42 + 24))-- - 4) = 0;
          break;
        }
      }
    }
  }
  *(_BYTE *)(*(_QWORD *)this + 14LL) = 0;
  *(_QWORD *)(*(_QWORD *)this + 16LL) = 0;
  *(_DWORD *)(*(_QWORD *)this + 8LL) = 0;
  v43 = *(__int64 **)(*((_QWORD *)this + 2) + 8LL);
  v44 = *v43;
  v45 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v43 + 96))(v43, **(unsigned int **)this);
  (*(void (__fastcall **)(__int64 *, __int64))(v44 + 56))(v43, v45);
  *((_DWORD *)this + 2) = 0;
  *(_QWORD *)this = 0;
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x140025c0c  mov     [rsp+arg_10], rbx
0x140025c11  mov     [rsp+arg_18], rbp
0x140025c16  push    rsi
0x140025c17  push    rdi
0x140025c18  push    r12
0x140025c1a  push    r14
0x140025c1c  push    r15
0x140025c1e  sub     rsp, 40h
0x140025c22  mov     rax, [rcx]
0x140025c25  mov     rsi, rcx
0x140025c28  mov     r15d, [rax+8]
0x140025c2c  and     r15d, 0FFFFFFFEh
0x140025c30  jz      loc_140025D47
0x140025c36  cmp     r15d, 80000012h
0x140025c3d  jz      loc_140025D47
0x140025c43  mov     rdi, [rcx+10h]
0x140025c47  call    cs:__imp_PsGetCurrentProcessId
0x140025c4e  nop     dword ptr [rax+rax+00h]
0x140025c53  and     eax, 0FFFFFFFCh
0x140025c56  cmp     r15d, eax
0x140025c59  jnz     loc_14002607E
0x140025c5f  call    cs:__imp_PsGetCurrentProcessWin32Process
0x140025c66  nop     dword ptr [rax+rax+00h]
0x140025c6b  mov     rbx, rax
0x140025c6e  test    rax, rax
0x140025c71  jz      short loc_140025C7D
0x140025c73  cmp     qword ptr [rax], 0
0x140025c77  jz      loc_140025D47
0x140025c7d  test    rbx, rbx
0x140025c80  jz      loc_140025D47
0x140025c86  mov     rcx, [rax]; Object
0x140025c89  call    cs:__imp_ObfReferenceObject
0x140025c90  nop     dword ptr [rax+rax+00h]
0x140025c95  lock inc dword ptr [rbx+8]
0x140025c99  mov     r14, [rdi]
0x140025c9c  add     r14, 5E8h
0x140025ca3  mov     rdx, r14
0x140025ca6  call    ??$GreAcquireSemaphoreCommon@$0BE@P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreAcquireSemaphoreCommon<20,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x140025cab  dec     dword ptr [rbx+3Ch]
0x140025cae  test    r14, r14
0x140025cb1  jz      short loc_140025D18
0x140025cb3  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, 0
0x140025cba  jnz     loc_140026217
0x140025cc0  mov     r12, gs:188h
0x140025cc9  xor     ebp, ebp
0x140025ccb  call    cs:__imp_KeIsAttachedProcess
0x140025cd2  nop     dword ptr [rax+rax+00h]
0x140025cd7  test    al, al
0x140025cd9  jnz     loc_140026030
0x140025cdf  mov     rcx, r12
0x140025ce2  call    cs:__imp_PsGetThreadWin32Thread
0x140025ce9  nop     dword ptr [rax+rax+00h]
0x140025cee  test    rax, rax
0x140025cf1  jz      short loc_140025CF6
0x140025cf3  mov     rbp, [rax]
0x140025cf6  lea     rax, [rbp+8]
0x140025cfa  neg     rbp
0x140025cfd  sbb     rdx, rdx
0x140025d00  and     rdx, rax
0x140025d03  jz      short loc_140025D10
0x140025d05  add     byte ptr [rdx+1Ch], 0FFh
0x140025d09  jnz     short loc_140025D10
0x140025d0b  btr     qword ptr [rdx], 14h
0x140025d10  mov     rcx, r14; HSEMAPHORE
0x140025d13  call    ?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x140025d18  mov     ecx, [rbx+114h]
0x140025d1e  mov     rdi, [rbx]
0x140025d21  shr     ecx, 9
0x140025d24  and     cl, 1
0x140025d27  or      eax, 0FFFFFFFFh
0x140025d2a  lock xadd [rbx+8], eax
0x140025d2f  cmp     eax, 1
0x140025d32  jz      loc_14002605F
0x140025d38  mov     rcx, rdi; Object
0x140025d3b  call    cs:__imp_ObfDereferenceObject
0x140025d42  nop     dword ptr [rax+rax+00h]
0x140025d47  mov     rdx, [rsi]
0x140025d4a  mov     edi, 0Fh
0x140025d4f  movzx   ecx, byte ptr [rdx+0Eh]
0x140025d53  cmp     ecx, edi
0x140025d55  ja      loc_140025FD8
0x140025d5b  jz      short loc_140025D9B
0x140025d5d  mov     edi, 7
0x140025d62  cmp     ecx, edi
0x140025d64  ja      loc_140025FB1
0x140025d6a  jz      short loc_140025D9B
0x140025d6c  test    ecx, ecx
0x140025d6e  jz      loc_140026194
0x140025d74  sub     ecx, 1
0x140025d77  jz      loc_140025F87
0x140025d7d  sub     ecx, 1
0x140025d80  jz      loc_14002618A
0x140025d86  sub     ecx, 1
0x140025d89  jz      loc_140026180
0x140025d8f  sub     ecx, 1
0x140025d92  jnz     loc_140025F10
0x140025d98  lea     edi, [rcx+4]
0x140025d9b  mov     rax, [rsi+10h]
0x140025d9f  mov     edx, [rdx]
0x140025da1  mov     rcx, [rax+8]
0x140025da5  mov     rax, [rcx]
0x140025da8  mov     rax, [rax+60h]
0x140025dac  call    _guard_dispatch_icall
0x140025db1  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits+5, 2
0x140025db8  jz      short loc_140025DF4
0x140025dba  mov     rbx, [rax]
0x140025dbd  call    cs:__imp_PsGetCurrentProcess
0x140025dc4  nop     dword ptr [rax+rax+00h]
0x140025dc9  mov     rcx, rax
0x140025dcc  call    cs:__imp_PsGetProcessSessionIdEx
0x140025dd3  nop     dword ptr [rax+rax+00h]
0x140025dd8  mov     [rsp+68h+var_38], r15d
0x140025ddd  lea     rdx, GdiDestroyHandle
0x140025de4  mov     [rsp+68h+var_40], eax
0x140025de8  mov     r9, rbx
0x140025deb  mov     dword ptr [rsp+68h+var_48], edi
0x140025def  call    McTemplateK0pqqq_EtwWriteTransfer
0x140025df4  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140025dfb  nop     dword ptr [rax+rax+00h]
0x140025e00  mov     rcx, [rax+18h]
0x140025e04  mov     rax, [rcx+0A80h]
0x140025e0b  test    rax, rax
0x140025e0e  jz      short loc_140025E5E
0x140025e10  call    _guard_dispatch_icall
0x140025e15  test    eax, eax
0x140025e17  js      short loc_140025E5E
0x140025e19  mov     rax, [rsi+10h]
0x140025e1d  mov     rdx, [rsi]
0x140025e20  mov     rcx, [rax+8]
0x140025e24  mov     bl, [rdx+0Eh]
0x140025e27  mov     edx, [rdx]
0x140025e29  mov     rax, [rcx]
0x140025e2c  mov     rax, [rax+60h]
0x140025e30  call    _guard_dispatch_icall
0x140025e35  mov     rdi, [rax]
0x140025e38  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140025e3f  nop     dword ptr [rax+rax+00h]
0x140025e44  mov     r8, [rax+18h]
0x140025e48  mov     rax, [r8+0A88h]
0x140025e4f  test    rax, rax
0x140025e52  jz      short loc_140025E5E
0x140025e54  mov     dl, bl
0x140025e56  mov     rcx, rdi
0x140025e59  call    _guard_dispatch_icall
0x140025e5e  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140025e65  nop     dword ptr [rax+rax+00h]
0x140025e6a  test    rax, rax
0x140025e6d  jz      loc_14002600E
0x140025e73  mov     rcx, [rax]
0x140025e76  lea     rax, [rcx+8]
0x140025e7a  neg     rcx
0x140025e7d  sbb     rdi, rdi
0x140025e80  and     rdi, rax
0x140025e83  jz      short loc_140025E95
0x140025e85  mov     rdi, [rdi+148h]
0x140025e8c  test    rdi, rdi
0x140025e8f  jnz     loc_140025F21
0x140025e95  mov     rax, [rsi]
0x140025e98  mov     byte ptr [rax+0Eh], 0
0x140025e9c  mov     rax, [rsi]
0x140025e9f  mov     qword ptr [rax+10h], 0
0x140025ea7  mov     rax, [rsi]
0x140025eaa  mov     dword ptr [rax+8], 0
0x140025eb1  mov     rax, [rsi+10h]
0x140025eb5  mov     rdx, [rsi]
0x140025eb8  mov     rdi, [rax+8]
0x140025ebc  mov     edx, [rdx]
0x140025ebe  mov     rcx, rdi
0x140025ec1  mov     rbx, [rdi]
0x140025ec4  mov     rax, [rbx+60h]
0x140025ec8  call    _guard_dispatch_icall
0x140025ecd  mov     rdx, rax
0x140025ed0  mov     rcx, rdi
0x140025ed3  mov     rax, [rbx+38h]
0x140025ed7  call    _guard_dispatch_icall
0x140025edc  mov     dword ptr [rsi+8], 0
0x140025ee3  mov     qword ptr [rsi], 0
0x140025eea  call    cs:__imp_KeLeaveCriticalRegion
0x140025ef1  nop     dword ptr [rax+rax+00h]
0x140025ef6  lea     r11, [rsp+68h+var_28]
0x140025efb  mov     rbx, [r11+40h]
0x140025eff  mov     rbp, [r11+48h]
0x140025f03  mov     rsp, r11
0x140025f06  pop     r15
0x140025f08  pop     r14
0x140025f0a  pop     r12
0x140025f0c  pop     rdi
0x140025f0d  pop     rsi
0x140025f0e  retn
0x140025f10  sub     ecx, 1
0x140025f13  jnz     loc_14002601F
0x140025f19  lea     edi, [rcx+5]
0x140025f1c  jmp     loc_140025D9B
0x140025f21  mov     rax, [rsi+10h]
0x140025f25  mov     rdx, [rsi]
0x140025f28  mov     rcx, [rax+8]
0x140025f2c  mov     edx, [rdx]
0x140025f2e  mov     rax, [rcx]
0x140025f31  mov     rax, [rax+60h]
0x140025f35  call    _guard_dispatch_icall
0x140025f3a  mov     rdx, [rsi]
0x140025f3d  mov     ebx, [rax]
0x140025f3f  mov     rax, [rsi+10h]
0x140025f43  mov     edx, [rdx]
0x140025f45  movzx   ebx, bx
0x140025f48  mov     rcx, [rax+8]
0x140025f4c  mov     rax, [rcx]
0x140025f4f  mov     rax, [rax+60h]
0x140025f53  call    _guard_dispatch_icall
0x140025f58  mov     r8d, [rax]
0x140025f5b  shr     r8d, 8
0x140025f5f  and     r8d, 0FF0000h
0x140025f66  or      r8d, ebx
0x140025f69  mov     rax, [rdi+18h]
0x140025f6d  xor     ecx, ecx
0x140025f6f  cmp     rcx, rax
0x140025f72  jnb     loc_140025E95
0x140025f78  mov     rdx, [rdi+28h]
0x140025f7c  cmp     [rdx+rcx*4], r8d
0x140025f80  jz      short loc_140025F91
0x140025f82  inc     rcx
0x140025f85  jmp     short loc_140025F6F
0x140025f87  mov     edi, 1
0x140025f8c  jmp     loc_140025D9B
0x140025f91  mov     eax, [rdx+rax*4-4]
0x140025f95  mov     [rdx+rcx*4], eax
0x140025f98  mov     rcx, [rdi+18h]
0x140025f9c  mov     rax, [rdi+28h]
0x140025fa0  mov     dword ptr [rax+rcx*4-4], 0
0x140025fa8  dec     qword ptr [rdi+18h]
0x140025fac  jmp     loc_140025E95
0x140025fb1  mov     edi, 8
0x140025fb6  sub     ecx, edi
0x140025fb8  jz      loc_140025D9B
0x140025fbe  sub     ecx, 1
0x140025fc1  jz      loc_140026176
0x140025fc7  sub     ecx, 1
0x140025fca  jnz     loc_140026148
0x140025fd0  lea     edi, [rcx+0Ah]
0x140025fd3  jmp     loc_140025D9B
0x140025fd8  mov     edi, 17h
0x140025fdd  cmp     ecx, edi
0x140025fdf  ja      loc_1400260FD
0x140025fe5  jz      loc_140025D9B
0x140025feb  sub     ecx, 10h
0x140025fee  jnz     short loc_140025FF8
0x140025ff0  lea     edi, [rcx+10h]
0x140025ff3  jmp     loc_140025D9B
0x140025ff8  sub     ecx, 1
0x140025ffb  jz      short loc_140026015
0x140025ffd  sub     ecx, 1
0x140026000  jnz     loc_14002615F
0x140026006  lea     edi, [rcx+12h]
0x140026009  jmp     loc_140025D9B
0x14002600e  xor     ecx, ecx
0x140026010  jmp     loc_140025E76
0x140026015  mov     edi, 11h
0x14002601a  jmp     loc_140025D9B
0x14002601f  cmp     ecx, 1
0x140026022  jnz     loc_14002620F
0x140026028  lea     edi, [rcx+5]
0x14002602b  jmp     loc_140025D9B
0x140026030  call    W32GetCurrentWin32kSessionId
0x140026035  mov     edi, eax
0x140026037  call    cs:__imp_PsGetCurrentThreadProcess
0x14002603e  nop     dword ptr [rax+rax+00h]
0x140026043  mov     rcx, rax
0x140026046  call    cs:__imp_PsGetProcessSessionIdEx
0x14002604d  nop     dword ptr [rax+rax+00h]
0x140026052  cmp     edi, eax
0x140026054  jz      loc_140025CDF
0x14002605a  jmp     loc_140025CF6
0x14002605f  xor     cl, 1
0x140026062  jz      loc_140026244
0x140026068  cmp     cl, 1
0x14002606b  jnz     loc_140025D38
0x140026071  mov     rcx, rbx; Buffer
0x140026074  call    UserDeleteW32Process
0x140026079  jmp     loc_140025D38
0x14002607e  movsxd  rcx, r15d; ProcessId
0x140026081  lea     rdx, [rsp+68h+Process]; Process
0x140026086  mov     [rsp+68h+Process], 0
0x14002608f  call    cs:__imp_PsLookupProcessByProcessId
0x140026096  nop     dword ptr [rax+rax+00h]
0x14002609b  test    eax, eax
0x14002609d  js      loc_140025D47
0x1400260a3  mov     rcx, [rsp+68h+Process]
0x1400260a8  call    cs:__imp_PsGetProcessWin32Process
0x1400260af  nop     dword ptr [rax+rax+00h]
0x1400260b4  mov     rbx, rax
0x1400260b7  test    rax, rax
0x1400260ba  jz      short loc_1400260C2
0x1400260bc  cmp     qword ptr [rax], 0
0x1400260c0  jz      short loc_1400260F9
0x1400260c2  test    rbx, rbx
0x1400260c5  jz      short loc_1400260DA
0x1400260c7  mov     rcx, [rax]; Object
0x1400260ca  call    cs:__imp_ObfReferenceObject
0x1400260d1  nop     dword ptr [rax+rax+00h]
0x1400260d6  lock inc dword ptr [rbx+8]
  ... truncated ...
```
