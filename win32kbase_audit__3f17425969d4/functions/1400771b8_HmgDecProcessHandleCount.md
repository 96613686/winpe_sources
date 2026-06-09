# HmgDecProcessHandleCount

- ea: `0x1400771b8`
- end: `0x14007748b`
- name: `HmgDecProcessHandleCount`
- size: `723`
- prototype: `void __fastcall(_QWORD *, int)`
- caller_count: `9`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400119f0`
- `0x140012c00`
- `0x14002ade0`
- `0x14002e5a0`
- `0x14002eef0`
- `0x14002f970`
- `0x14003d500`
- `0x140078900`
- `0x1400799f0`

## callees

- `0x140031fa0`
- `0x140032300`
- `0x1400324c0`
- `0x1400371c0`
- `0x1400771b8`
- `0x14007b930`
- `0x140111520`
- `0x140192b70`
- `0x1401abd50`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400771fb`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400771fb`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x1400772b2`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x1400772b2`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400771e4`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400771e4`
- `ntoskrnl!PsSetProcessWin32Process` at `0x140077472`
- `ntoskrnl!PsSetProcessWin32Process` at `0x140077472`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14007733d`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14007733d`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14007737f`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14007737f`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14007732e`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14007732e`
- `ntoskrnl!KeIsAttachedProcess` at `0x14007729f`
- `ntoskrnl!KeIsAttachedProcess` at `0x14007729f`
- `ntoskrnl!ObfReferenceObject` at `0x140077225`
- `ntoskrnl!ObfReferenceObject` at `0x1400773ba`
- `ntoskrnl!ObfReferenceObject` at `0x140077225`
- `ntoskrnl!ObfReferenceObject` at `0x1400773ba`
- `ntoskrnl!ObfDereferenceObject` at `0x140077307`
- `ntoskrnl!ObfDereferenceObject` at `0x1400773cf`
- `ntoskrnl!ObfDereferenceObject` at `0x140077307`
- `ntoskrnl!ObfDereferenceObject` at `0x1400773cf`
- `ntoskrnl!PsGetProcessWin32Process` at `0x140077394`
- `ntoskrnl!PsGetProcessWin32Process` at `0x140077394`

## pseudocode

```c
void __fastcall HmgDecProcessHandleCount(_QWORD *a1, int a2)
{
  void *v2; // rbx
  __int64 v4; // rcx
  PVOID *CurrentProcessWin32Process; // rax
  volatile signed __int32 *v6; // rbx
  struct _ERESOURCE *v7; // rbp
  struct _GRETHREAD *v8; // rax
  __int64 v9; // rdx
  unsigned __int64 i; // rcx
  __int64 v11; // r8
  struct _GRETHREAD *v12; // rdi
  struct _KTHREAD *CurrentThread; // r14
  __int64 v14; // rsi
  __int64 v15; // rcx
  __int64 *ThreadWin32Thread; // rax
  __int64 v17; // rax
  __int64 v18; // rsi
  void *v20; // rdi
  bool v21; // cl
  int CurrentWin32kSessionId; // edi
  __int64 CurrentThreadProcess; // rax
  bool v24; // cl
  PVOID *ProcessWin32Process; // rax
  int v26; // eax
  PEPROCESS Process; // [rsp+60h] [rbp+18h] BYREF

  if ( !a2 )
    return;
  v2 = (void *)a2;
  if ( a2 == -2147483630 )
    return;
  if ( a2 == ((unsigned int)PsGetCurrentProcessId() & 0xFFFFFFFC) )
  {
    CurrentProcessWin32Process = (PVOID *)PsGetCurrentProcessWin32Process(v4);
    v6 = (volatile signed __int32 *)CurrentProcessWin32Process;
    if ( CurrentProcessWin32Process && !*CurrentProcessWin32Process || !CurrentProcessWin32Process )
      return;
    ObfReferenceObject(*CurrentProcessWin32Process);
    _InterlockedIncrement(v6 + 2);
    goto LABEL_8;
  }
  Process = 0;
  if ( PsLookupProcessByProcessId(v2, &Process) >= 0 )
  {
    ProcessWin32Process = (PVOID *)PsGetProcessWin32Process(Process);
    v6 = (volatile signed __int32 *)ProcessWin32Process;
    if ( !ProcessWin32Process || *ProcessWin32Process )
    {
      if ( ProcessWin32Process )
      {
        ObfReferenceObject(*ProcessWin32Process);
        _InterlockedIncrement(v6 + 2);
      }
    }
    else
    {
      v6 = 0;
    }
    ObfDereferenceObject(Process);
    if ( v6 )
    {
LABEL_8:
      v7 = (struct _ERESOURCE *)(*a1 + 1512LL);
      GreAcquireSemaphoreInternal(v7);
      v8 = GreGetCurrentThreadCrossSessionCheck();
      v12 = v8;
      if ( v8 )
      {
        v11 = *(_QWORD *)v8;
        if ( (*(_QWORD *)v8 & 0xFFFFFFDFFFF00000uLL) != 0 && (v11 & 0x100000) == 0 )
        {
          LODWORD(v9) = 38;
          for ( i = 0; i < 0x40; ++i )
          {
            v26 = i;
            if ( ((1LL << i) & 0xFFFFFFDFFFFFFFFFuLL & v11) == 0 )
              v26 = v9;
            v9 = (unsigned int)v26;
          }
          if ( v26 > 20 && v26 != 38 )
            MicrosoftTelemetryAssertTriggeredNoArgsKM(i, (unsigned int)v26);
        }
        LOBYTE(i) = *((_BYTE *)v12 + 28);
        *((_BYTE *)v12 + 28) = i + 1;
        if ( !(_BYTE)i )
          *(_QWORD *)v12 |= 0x100000uLL;
      }
      --*((_DWORD *)v6 + 15);
      if ( v7 )
      {
        if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
          McTemplateK0pz_EtwWriteTransfer(i, (unsigned int)LockRelease, v11, (_DWORD)v7, (__int64)L"Hmgr");
        CurrentThread = KeGetCurrentThread();
        v14 = 0;
        if ( !(unsigned __int8)KeIsAttachedProcess(i, v9)
          || (CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(v15),
              CurrentThreadProcess = PsGetCurrentThreadProcess(),
              CurrentWin32kSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
        {
          ThreadWin32Thread = (__int64 *)PsGetThreadWin32Thread(CurrentThread);
          if ( ThreadWin32Thread )
            v14 = *ThreadWin32Thread;
        }
        v17 = v14 + 8;
        v18 = -v14;
        if ( (v17 & -(__int64)(v18 != 0)) != 0 && (*(_BYTE *)((v17 & -(__int64)(v18 != 0)) + 0x1C))-- == 1 )
          *(_QWORD *)(v17 & -(__int64)(v18 != 0)) &= ~0x100000uLL;
        GreReleaseSemaphoreSharedInternal(v7);
      }
      v20 = *(void **)v6;
      v21 = (v6[69] & 0x200) != 0;
      if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
      {
        v24 = !v21;
        if ( v24 )
        {
          if ( v24 )
            UserDeleteW32Process((PVOID)v6);
        }
        else
        {
          PsSetProcessWin32Process(*(_QWORD *)v6, 0, v6);
          GreDeleteFastMutex((PVOID)v6);
        }
      }
      ObfDereferenceObject(v20);
    }
  }
}

```

## disassembly

```asm
0x1400771b8  test    edx, edx
0x1400771ba  jz      locret_140077325
0x1400771c0  mov     [rsp+arg_0], rbx
0x1400771c5  mov     [rsp+arg_18], rbp
0x1400771ca  push    rsi
0x1400771cb  push    rdi
0x1400771cc  push    r14
0x1400771ce  sub     rsp, 30h
0x1400771d2  movsxd  rbx, edx
0x1400771d5  mov     rdi, rcx
0x1400771d8  cmp     ebx, 80000012h
0x1400771de  jz      loc_140077313
0x1400771e4  call    cs:__imp_PsGetCurrentProcessId
0x1400771eb  nop     dword ptr [rax+rax+00h]
0x1400771f0  and     eax, 0FFFFFFFCh
0x1400771f3  cmp     ebx, eax
0x1400771f5  jnz     loc_14007736E
0x1400771fb  call    cs:__imp_PsGetCurrentProcessWin32Process
0x140077202  nop     dword ptr [rax+rax+00h]
0x140077207  mov     rbx, rax
0x14007720a  test    rax, rax
0x14007720d  jz      short loc_140077219
0x14007720f  cmp     qword ptr [rax], 0
0x140077213  jz      loc_140077313
0x140077219  test    rbx, rbx
0x14007721c  jz      loc_140077313
0x140077222  mov     rcx, [rax]; Object
0x140077225  call    cs:__imp_ObfReferenceObject
0x14007722c  nop     dword ptr [rax+rax+00h]
0x140077231  lock inc dword ptr [rbx+8]
0x140077235  mov     rbp, [rdi]
0x140077238  add     rbp, 5E8h
0x14007723f  mov     rcx, rbp; Resource
0x140077242  call    ?GreAcquireSemaphoreInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreInternal(HSEMAPHORE__ *)
0x140077247  call    ?GreGetCurrentThreadCrossSessionCheck@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThreadCrossSessionCheck(void)
0x14007724c  mov     rdi, rax
0x14007724f  test    rax, rax
0x140077252  jz      short loc_14007727F
0x140077254  mov     r8, [rax]
0x140077257  mov     esi, 100000h
0x14007725c  mov     rax, 0FFFFFFDFFFF00000h
0x140077266  test    rax, r8
0x140077269  jnz     loc_1400773E9
0x14007726f  mov     cl, [rdi+1Ch]
0x140077272  lea     eax, [rcx+1]
0x140077275  mov     [rdi+1Ch], al
0x140077278  test    cl, cl
0x14007727a  jnz     short loc_14007727F
0x14007727c  or      [rdi], rsi
0x14007727f  dec     dword ptr [rbx+3Ch]
0x140077282  test    rbp, rbp
0x140077285  jz      short loc_1400772E8
0x140077287  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, 0
0x14007728e  jnz     loc_14007743D
0x140077294  mov     r14, gs:188h
0x14007729d  xor     esi, esi
0x14007729f  call    cs:__imp_KeIsAttachedProcess
0x1400772a6  nop     dword ptr [rax+rax+00h]
0x1400772ab  test    al, al
0x1400772ad  jnz     short loc_140077327
0x1400772af  mov     rcx, r14
0x1400772b2  call    cs:__imp_PsGetThreadWin32Thread
0x1400772b9  nop     dword ptr [rax+rax+00h]
0x1400772be  test    rax, rax
0x1400772c1  jz      short loc_1400772C6
0x1400772c3  mov     rsi, [rax]
0x1400772c6  lea     rax, [rsi+8]
0x1400772ca  neg     rsi
0x1400772cd  sbb     rdx, rdx
0x1400772d0  and     rdx, rax
0x1400772d3  jz      short loc_1400772E0
0x1400772d5  add     byte ptr [rdx+1Ch], 0FFh
0x1400772d9  jnz     short loc_1400772E0
0x1400772db  btr     qword ptr [rdx], 14h
0x1400772e0  mov     rcx, rbp; HSEMAPHORE
0x1400772e3  call    ?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x1400772e8  mov     ecx, [rbx+114h]
0x1400772ee  mov     rdi, [rbx]
0x1400772f1  shr     ecx, 9
0x1400772f4  and     cl, 1
0x1400772f7  or      eax, 0FFFFFFFFh
0x1400772fa  lock xadd [rbx+8], eax
0x1400772ff  cmp     eax, 1
0x140077302  jz      short loc_140077356
0x140077304  mov     rcx, rdi; Object
0x140077307  call    cs:__imp_ObfDereferenceObject
0x14007730e  nop     dword ptr [rax+rax+00h]
0x140077313  mov     rbx, [rsp+48h+arg_0]
0x140077318  mov     rbp, [rsp+48h+arg_18]
0x14007731d  add     rsp, 30h
0x140077321  pop     r14
0x140077323  pop     rdi
0x140077324  pop     rsi
0x140077325  retn
0x140077327  call    W32GetCurrentWin32kSessionId
0x14007732c  mov     edi, eax
0x14007732e  call    cs:__imp_PsGetCurrentThreadProcess
0x140077335  nop     dword ptr [rax+rax+00h]
0x14007733a  mov     rcx, rax
0x14007733d  call    cs:__imp_PsGetProcessSessionIdEx
0x140077344  nop     dword ptr [rax+rax+00h]
0x140077349  cmp     edi, eax
0x14007734b  jz      loc_1400772AF
0x140077351  jmp     loc_1400772C6
0x140077356  xor     cl, 1
0x140077359  jz      loc_14007746A
0x14007735f  cmp     cl, 1
0x140077362  jnz     short loc_140077304
0x140077364  mov     rcx, rbx; Buffer
0x140077367  call    UserDeleteW32Process
0x14007736c  jmp     short loc_140077304
0x14007736e  mov     rcx, rbx; ProcessId
0x140077371  mov     [rsp+48h+Process], 0
0x14007737a  lea     rdx, [rsp+48h+Process]; Process
0x14007737f  call    cs:__imp_PsLookupProcessByProcessId
0x140077386  nop     dword ptr [rax+rax+00h]
0x14007738b  test    eax, eax
0x14007738d  js      short loc_140077313
0x14007738f  mov     rcx, [rsp+48h+Process]
0x140077394  call    cs:__imp_PsGetProcessWin32Process
0x14007739b  nop     dword ptr [rax+rax+00h]
0x1400773a0  mov     rbx, rax
0x1400773a3  test    rax, rax
0x1400773a6  jz      short loc_1400773B2
0x1400773a8  cmp     qword ptr [rax], 0
0x1400773ac  jnz     short loc_1400773B2
0x1400773ae  xor     ebx, ebx
0x1400773b0  jmp     short loc_1400773CA
0x1400773b2  test    rbx, rbx
0x1400773b5  jz      short loc_1400773CA
0x1400773b7  mov     rcx, [rax]; Object
0x1400773ba  call    cs:__imp_ObfReferenceObject
0x1400773c1  nop     dword ptr [rax+rax+00h]
0x1400773c6  lock inc dword ptr [rbx+8]
0x1400773ca  mov     rcx, [rsp+48h+Process]; Object
0x1400773cf  call    cs:__imp_ObfDereferenceObject
0x1400773d6  nop     dword ptr [rax+rax+00h]
0x1400773db  test    rbx, rbx
0x1400773de  jnz     loc_140077235
0x1400773e4  jmp     loc_140077313
0x1400773e9  test    rsi, r8
0x1400773ec  jnz     loc_14007726F
0x1400773f2  mov     edx, 26h ; '&'
0x1400773f7  xor     ecx, ecx
0x1400773f9  mov     eax, 1
0x1400773fe  mov     r9, 0FFFFFFDFFFFFFFFFh
0x140077408  shl     rax, cl
0x14007740b  and     rax, r9
0x14007740e  test    r8, rax
0x140077411  mov     eax, ecx
0x140077413  cmovz   eax, edx
0x140077416  inc     rcx
0x140077419  mov     edx, eax
0x14007741b  cmp     rcx, 40h ; '@'
0x14007741f  jb      short loc_1400773F9
0x140077421  cmp     eax, 14h
0x140077424  jle     loc_14007726F
0x14007742a  cmp     eax, 26h ; '&'
0x14007742d  jz      loc_14007726F
0x140077433  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140077438  jmp     loc_14007726F
0x14007743d  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits, 10h
0x140077444  jz      loc_140077294
0x14007744a  lea     rax, aHmgr; "Hmgr"
0x140077451  mov     r9, rbp
0x140077454  lea     rdx, LockRelease
0x14007745b  mov     [rsp+48h+var_28], rax
0x140077460  call    McTemplateK0pz_EtwWriteTransfer
0x140077465  jmp     loc_140077294
0x14007746a  mov     rcx, [rbx]
0x14007746d  mov     r8, rbx
0x140077470  xor     edx, edx
0x140077472  call    cs:__imp_PsSetProcessWin32Process
0x140077479  nop     dword ptr [rax+rax+00h]
0x14007747e  mov     rcx, rbx; Buffer
0x140077481  call    GreDeleteFastMutex
0x140077486  jmp     loc_140077304
```
