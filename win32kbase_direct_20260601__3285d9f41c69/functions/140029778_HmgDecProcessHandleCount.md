# HmgDecProcessHandleCount

- ea: `0x140029778`
- end: `0x140029a4b`
- name: `HmgDecProcessHandleCount`
- size: `723`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140010920`
- `0x14001e580`
- `0x140021d40`
- `0x140022690`
- `0x140023110`
- `0x1400268b0`
- `0x140028080`
- `0x140029510`
- `0x140040f40`

## callees

- `0x14001d160`
- `0x140025990`
- `0x140025b50`
- `0x140029778`
- `0x140031bf4`
- `0x14004a0d0`
- `0x140110520`
- `0x140190760`
- `0x1401ab150`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400297bb`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400297bb`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x140029872`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x140029872`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400297a4`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400297a4`
- `ntoskrnl!PsSetProcessWin32Process` at `0x140029a32`
- `ntoskrnl!PsSetProcessWin32Process` at `0x140029a32`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400298fd`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400298fd`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14002993f`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14002993f`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x1400298ee`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x1400298ee`
- `ntoskrnl!KeIsAttachedProcess` at `0x14002985f`
- `ntoskrnl!KeIsAttachedProcess` at `0x14002985f`
- `ntoskrnl!ObfReferenceObject` at `0x1400297e5`
- `ntoskrnl!ObfReferenceObject` at `0x14002997a`
- `ntoskrnl!ObfReferenceObject` at `0x1400297e5`
- `ntoskrnl!ObfReferenceObject` at `0x14002997a`
- `ntoskrnl!ObfDereferenceObject` at `0x1400298c7`
- `ntoskrnl!ObfDereferenceObject` at `0x14002998f`
- `ntoskrnl!ObfDereferenceObject` at `0x1400298c7`
- `ntoskrnl!ObfDereferenceObject` at `0x14002998f`
- `ntoskrnl!PsGetProcessWin32Process` at `0x140029954`
- `ntoskrnl!PsGetProcessWin32Process` at `0x140029954`

## pseudocode

```c
void __fastcall HmgDecProcessHandleCount(_QWORD *a1, int a2)
{
  void *v2; // rbx
  PVOID *CurrentProcessWin32Process; // rax
  volatile signed __int32 *v5; // rbx
  HSEMAPHORE v6; // rbp
  struct _GRETHREAD *v7; // rax
  unsigned __int64 i; // rcx
  __int64 v9; // r8
  struct _GRETHREAD *v10; // rdi
  struct _KTHREAD *CurrentThread; // r14
  __int64 v12; // rsi
  __int64 *ThreadWin32Thread; // rax
  __int64 v14; // rax
  __int64 v15; // rsi
  void *v17; // rdi
  bool v18; // cl
  int CurrentWin32kSessionId; // edi
  __int64 CurrentThreadProcess; // rax
  bool v21; // cl
  PVOID *ProcessWin32Process; // rax
  int v23; // edx
  int v24; // eax
  PEPROCESS Process; // [rsp+60h] [rbp+18h] BYREF

  if ( !a2 )
    return;
  v2 = (void *)a2;
  if ( a2 == -2147483630 )
    return;
  if ( a2 == ((unsigned int)PsGetCurrentProcessId() & 0xFFFFFFFC) )
  {
    CurrentProcessWin32Process = (PVOID *)PsGetCurrentProcessWin32Process();
    v5 = (volatile signed __int32 *)CurrentProcessWin32Process;
    if ( CurrentProcessWin32Process && !*CurrentProcessWin32Process || !CurrentProcessWin32Process )
      return;
    ObfReferenceObject(*CurrentProcessWin32Process);
    _InterlockedIncrement(v5 + 2);
    goto LABEL_8;
  }
  Process = 0;
  if ( PsLookupProcessByProcessId(v2, &Process) >= 0 )
  {
    ProcessWin32Process = (PVOID *)PsGetProcessWin32Process(Process);
    v5 = (volatile signed __int32 *)ProcessWin32Process;
    if ( !ProcessWin32Process || *ProcessWin32Process )
    {
      if ( ProcessWin32Process )
      {
        ObfReferenceObject(*ProcessWin32Process);
        _InterlockedIncrement(v5 + 2);
      }
    }
    else
    {
      v5 = 0;
    }
    ObfDereferenceObject(Process);
    if ( v5 )
    {
LABEL_8:
      v6 = (HSEMAPHORE)(*a1 + 1512LL);
      GreAcquireSemaphoreInternal(v6);
      v7 = GreGetCurrentThreadCrossSessionCheck();
      v10 = v7;
      if ( v7 )
      {
        v9 = *(_QWORD *)v7;
        if ( (*(_QWORD *)v7 & 0xFFFFFFDFFFF00000uLL) != 0 && (v9 & 0x100000) == 0 )
        {
          v23 = 38;
          for ( i = 0; i < 0x40; ++i )
          {
            v24 = i;
            if ( ((1LL << i) & 0xFFFFFFDFFFFFFFFFuLL & v9) == 0 )
              v24 = v23;
            v23 = v24;
          }
          if ( v24 > 20 && v24 != 38 )
            MicrosoftTelemetryAssertTriggeredNoArgsKM(i, (unsigned int)v24);
        }
        LOBYTE(i) = *((_BYTE *)v10 + 28);
        *((_BYTE *)v10 + 28) = i + 1;
        if ( !(_BYTE)i )
          *(_QWORD *)v10 |= 0x100000uLL;
      }
      --*((_DWORD *)v5 + 15);
      if ( v6 )
      {
        if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
          McTemplateK0pz_EtwWriteTransfer(i, (unsigned int)LockRelease, v9, (_DWORD)v6, (__int64)L"Hmgr");
        CurrentThread = KeGetCurrentThread();
        v12 = 0;
        if ( !(unsigned __int8)KeIsAttachedProcess()
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
        GreReleaseSemaphoreSharedInternal(v6);
      }
      v17 = *(void **)v5;
      v18 = (v5[69] & 0x200) != 0;
      if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
      {
        v21 = !v18;
        if ( v21 )
        {
          if ( v21 )
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
}

```

## disassembly

```asm
0x140029778  test    edx, edx
0x14002977a  jz      locret_1400298E5
0x140029780  mov     [rsp+arg_0], rbx
0x140029785  mov     [rsp+arg_18], rbp
0x14002978a  push    rsi
0x14002978b  push    rdi
0x14002978c  push    r14
0x14002978e  sub     rsp, 30h
0x140029792  movsxd  rbx, edx
0x140029795  mov     rdi, rcx
0x140029798  cmp     ebx, 80000012h
0x14002979e  jz      loc_1400298D3
0x1400297a4  call    cs:__imp_PsGetCurrentProcessId
0x1400297ab  nop     dword ptr [rax+rax+00h]
0x1400297b0  and     eax, 0FFFFFFFCh
0x1400297b3  cmp     ebx, eax
0x1400297b5  jnz     loc_14002992E
0x1400297bb  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1400297c2  nop     dword ptr [rax+rax+00h]
0x1400297c7  mov     rbx, rax
0x1400297ca  test    rax, rax
0x1400297cd  jz      short loc_1400297D9
0x1400297cf  cmp     qword ptr [rax], 0
0x1400297d3  jz      loc_1400298D3
0x1400297d9  test    rbx, rbx
0x1400297dc  jz      loc_1400298D3
0x1400297e2  mov     rcx, [rax]; Object
0x1400297e5  call    cs:__imp_ObfReferenceObject
0x1400297ec  nop     dword ptr [rax+rax+00h]
0x1400297f1  lock inc dword ptr [rbx+8]
0x1400297f5  mov     rbp, [rdi]
0x1400297f8  add     rbp, 5E8h
0x1400297ff  mov     rcx, rbp; Resource
0x140029802  call    ?GreAcquireSemaphoreInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreInternal(HSEMAPHORE__ *)
0x140029807  call    ?GreGetCurrentThreadCrossSessionCheck@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThreadCrossSessionCheck(void)
0x14002980c  mov     rdi, rax
0x14002980f  test    rax, rax
0x140029812  jz      short loc_14002983F
0x140029814  mov     r8, [rax]
0x140029817  mov     esi, 100000h
0x14002981c  mov     rax, 0FFFFFFDFFFF00000h
0x140029826  test    rax, r8
0x140029829  jnz     loc_1400299A9
0x14002982f  mov     cl, [rdi+1Ch]
0x140029832  lea     eax, [rcx+1]
0x140029835  mov     [rdi+1Ch], al
0x140029838  test    cl, cl
0x14002983a  jnz     short loc_14002983F
0x14002983c  or      [rdi], rsi
0x14002983f  dec     dword ptr [rbx+3Ch]
0x140029842  test    rbp, rbp
0x140029845  jz      short loc_1400298A8
0x140029847  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, 0
0x14002984e  jnz     loc_1400299FD
0x140029854  mov     r14, gs:188h
0x14002985d  xor     esi, esi
0x14002985f  call    cs:__imp_KeIsAttachedProcess
0x140029866  nop     dword ptr [rax+rax+00h]
0x14002986b  test    al, al
0x14002986d  jnz     short loc_1400298E7
0x14002986f  mov     rcx, r14
0x140029872  call    cs:__imp_PsGetThreadWin32Thread
0x140029879  nop     dword ptr [rax+rax+00h]
0x14002987e  test    rax, rax
0x140029881  jz      short loc_140029886
0x140029883  mov     rsi, [rax]
0x140029886  lea     rax, [rsi+8]
0x14002988a  neg     rsi
0x14002988d  sbb     rdx, rdx
0x140029890  and     rdx, rax
0x140029893  jz      short loc_1400298A0
0x140029895  add     byte ptr [rdx+1Ch], 0FFh
0x140029899  jnz     short loc_1400298A0
0x14002989b  btr     qword ptr [rdx], 14h
0x1400298a0  mov     rcx, rbp; HSEMAPHORE
0x1400298a3  call    ?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x1400298a8  mov     ecx, [rbx+114h]
0x1400298ae  mov     rdi, [rbx]
0x1400298b1  shr     ecx, 9
0x1400298b4  and     cl, 1
0x1400298b7  or      eax, 0FFFFFFFFh
0x1400298ba  lock xadd [rbx+8], eax
0x1400298bf  cmp     eax, 1
0x1400298c2  jz      short loc_140029916
0x1400298c4  mov     rcx, rdi; Object
0x1400298c7  call    cs:__imp_ObfDereferenceObject
0x1400298ce  nop     dword ptr [rax+rax+00h]
0x1400298d3  mov     rbx, [rsp+48h+arg_0]
0x1400298d8  mov     rbp, [rsp+48h+arg_18]
0x1400298dd  add     rsp, 30h
0x1400298e1  pop     r14
0x1400298e3  pop     rdi
0x1400298e4  pop     rsi
0x1400298e5  retn
0x1400298e7  call    W32GetCurrentWin32kSessionId
0x1400298ec  mov     edi, eax
0x1400298ee  call    cs:__imp_PsGetCurrentThreadProcess
0x1400298f5  nop     dword ptr [rax+rax+00h]
0x1400298fa  mov     rcx, rax
0x1400298fd  call    cs:__imp_PsGetProcessSessionIdEx
0x140029904  nop     dword ptr [rax+rax+00h]
0x140029909  cmp     edi, eax
0x14002990b  jz      loc_14002986F
0x140029911  jmp     loc_140029886
0x140029916  xor     cl, 1
0x140029919  jz      loc_140029A2A
0x14002991f  cmp     cl, 1
0x140029922  jnz     short loc_1400298C4
0x140029924  mov     rcx, rbx; Buffer
0x140029927  call    UserDeleteW32Process
0x14002992c  jmp     short loc_1400298C4
0x14002992e  mov     rcx, rbx; ProcessId
0x140029931  mov     [rsp+48h+Process], 0
0x14002993a  lea     rdx, [rsp+48h+Process]; Process
0x14002993f  call    cs:__imp_PsLookupProcessByProcessId
0x140029946  nop     dword ptr [rax+rax+00h]
0x14002994b  test    eax, eax
0x14002994d  js      short loc_1400298D3
0x14002994f  mov     rcx, [rsp+48h+Process]
0x140029954  call    cs:__imp_PsGetProcessWin32Process
0x14002995b  nop     dword ptr [rax+rax+00h]
0x140029960  mov     rbx, rax
0x140029963  test    rax, rax
0x140029966  jz      short loc_140029972
0x140029968  cmp     qword ptr [rax], 0
0x14002996c  jnz     short loc_140029972
0x14002996e  xor     ebx, ebx
0x140029970  jmp     short loc_14002998A
0x140029972  test    rbx, rbx
0x140029975  jz      short loc_14002998A
0x140029977  mov     rcx, [rax]; Object
0x14002997a  call    cs:__imp_ObfReferenceObject
0x140029981  nop     dword ptr [rax+rax+00h]
0x140029986  lock inc dword ptr [rbx+8]
0x14002998a  mov     rcx, [rsp+48h+Process]; Object
0x14002998f  call    cs:__imp_ObfDereferenceObject
0x140029996  nop     dword ptr [rax+rax+00h]
0x14002999b  test    rbx, rbx
0x14002999e  jnz     loc_1400297F5
0x1400299a4  jmp     loc_1400298D3
0x1400299a9  test    rsi, r8
0x1400299ac  jnz     loc_14002982F
0x1400299b2  mov     edx, 26h ; '&'
0x1400299b7  xor     ecx, ecx
0x1400299b9  mov     eax, 1
0x1400299be  mov     r9, 0FFFFFFDFFFFFFFFFh
0x1400299c8  shl     rax, cl
0x1400299cb  and     rax, r9
0x1400299ce  test    r8, rax
0x1400299d1  mov     eax, ecx
0x1400299d3  cmovz   eax, edx
0x1400299d6  inc     rcx
0x1400299d9  mov     edx, eax
0x1400299db  cmp     rcx, 40h ; '@'
0x1400299df  jb      short loc_1400299B9
0x1400299e1  cmp     eax, 14h
0x1400299e4  jle     loc_14002982F
0x1400299ea  cmp     eax, 26h ; '&'
0x1400299ed  jz      loc_14002982F
0x1400299f3  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400299f8  jmp     loc_14002982F
0x1400299fd  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits, 10h
0x140029a04  jz      loc_140029854
0x140029a0a  lea     rax, aHmgr; "Hmgr"
0x140029a11  mov     r9, rbp
0x140029a14  lea     rdx, LockRelease
0x140029a1b  mov     [rsp+48h+var_28], rax
0x140029a20  call    McTemplateK0pz_EtwWriteTransfer
0x140029a25  jmp     loc_140029854
0x140029a2a  mov     rcx, [rbx]
0x140029a2d  mov     r8, rbx
0x140029a30  xor     edx, edx
0x140029a32  call    cs:__imp_PsSetProcessWin32Process
0x140029a39  nop     dword ptr [rax+rax+00h]
0x140029a3e  mov     rcx, rbx; Buffer
0x140029a41  call    GreDeleteFastMutex
0x140029a46  jmp     loc_1400298C4
```
