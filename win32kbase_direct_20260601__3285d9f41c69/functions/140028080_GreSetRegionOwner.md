# GreSetRegionOwner

- ea: `0x140028080`
- end: `0x140028354`
- name: `GreSetRegionOwner`
- size: `724`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140069180`
- `0x140173ed4`

## callees

- `0x14001d160`
- `0x140025a30`
- `0x140028080`
- `0x140028360`
- `0x140028590`
- `0x140029748`
- `0x140029778`
- `0x140029a54`
- `0x140031bf4`
- `0x1400f0fb8`
- `0x140190760`
- `0x140238240`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400281d3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400281d3`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x140028213`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x140028213`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140028096`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400280b1`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400280cc`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140028096`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400280b1`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400280cc`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400282d4`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400282d4`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x1400282c5`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x1400282c5`
- `ntoskrnl!KeIsAttachedProcess` at `0x1400281fc`
- `ntoskrnl!KeIsAttachedProcess` at `0x1400281fc`
- `WIN32K!W32GetSessionState` at `0x1400280de`
- `WIN32K!W32GetSessionState` at `0x1400280de`

## pseudocode

```c
__int64 __fastcall GreSetRegionOwner(__int64 a1, int a2)
{
  unsigned __int64 v2; // rbx
  __int64 v4; // rcx
  unsigned int v5; // r12d
  _QWORD *v6; // r13
  HSEMAPHORE v7; // r15
  __int64 v8; // rcx
  int v9; // ecx
  int v10; // r8d
  unsigned int *v11; // r14
  BOOL v12; // esi
  __int64 v13; // rdi
  struct _GRETHREAD *CurrentThread; // rax
  unsigned int v15; // ebp
  __int64 *v16; // rdi
  __int64 v17; // rbx
  __int64 v18; // rax
  struct _KTHREAD *v19; // rsi
  __int64 v20; // rdi
  __int64 *ThreadWin32Thread; // rax
  __int64 v22; // rax
  __int64 v23; // rdi
  int CurrentWin32kSessionId; // ebx
  __int64 CurrentThreadProcess; // rax
  unsigned int *v28; // [rsp+30h] [rbp-68h] BYREF
  int v29; // [rsp+38h] [rbp-60h]
  __int64 v30; // [rsp+40h] [rbp-58h]

  LODWORD(v2) = a2;
  PsGetCurrentProcessId();
  if ( (_DWORD)v2 == -2147483646 )
    v2 = (unsigned __int64)PsGetCurrentProcessId() & 0xFFFFFFFC;
  v5 = 0;
  if ( (_DWORD)v2 == -2147483646 )
    v2 = (unsigned __int64)PsGetCurrentProcessId() & 0xFFFFFFFC;
  v6 = *(_QWORD **)(W32GetSessionState(v4) + 88);
  v7 = (HSEMAPHORE)(*v6 + 1512LL);
  GreAcquireSemaphoreCommon<20,void (*)(HSEMAPHORE__ *)>(v8, v7);
  HANDLELOCK::HANDLELOCK(&v28, v6, a1, 1);
  if ( v29 )
  {
    v11 = v28;
    if ( *((_BYTE *)v28 + 14) == 4 && *((_WORD *)v28 + 6) == WORD1(a1) )
    {
      v12 = 0;
      v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v30 + 8) + 96LL))(*(_QWORD *)(v30 + 8), *v28);
      CurrentThread = GreGetCurrentThread();
      if ( CurrentThread && *((_QWORD *)CurrentThread + 8) )
        v12 = v2 != 0;
      if ( !*(_WORD *)(v13 + 12) || *(struct _KTHREAD **)(v13 + 16) == KeGetCurrentThread() || v12 )
      {
        v5 = 1;
        v15 = v11[2] & 0xFFFFFFFE;
        if ( v12 )
          LODWORD(v2) = UMPDGetThreadClientPID(CurrentThread);
        if ( v15 != (_DWORD)v2 )
        {
          v5 = HmgIncProcessHandleCount((unsigned int)v2);
          if ( v5 )
          {
            HmgDecProcessHandleCount(v6, v15);
            HANDLELOCK::Pid((HANDLELOCK *)&v28, v2);
            if ( !(_DWORD)v2 || (_DWORD)v2 == -2147483630 )
            {
              *(_WORD *)(v13 + 14) &= ~0x10u;
            }
            else if ( *(_WORD *)(v13 + 12) || *(_DWORD *)(v13 + 8) )
            {
              *(_WORD *)(v13 + 14) |= 0x10u;
            }
          }
        }
      }
    }
    v16 = *(__int64 **)(v30 + 8);
    v17 = *v16;
    v18 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v16 + 96))(v16, *v11);
    (*(void (__fastcall **)(__int64 *, __int64))(v17 + 48))(v16, v18);
    KeLeaveCriticalRegion();
  }
  if ( v7 )
  {
    if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
      McTemplateK0pz_EtwWriteTransfer(v9, (unsigned int)LockRelease, v10, (_DWORD)v7, (__int64)L"Hmgr");
    v19 = KeGetCurrentThread();
    v20 = 0;
    if ( !(unsigned __int8)KeIsAttachedProcess()
      || (CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(),
          CurrentThreadProcess = PsGetCurrentThreadProcess(),
          CurrentWin32kSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
    {
      ThreadWin32Thread = (__int64 *)PsGetThreadWin32Thread(v19);
      if ( ThreadWin32Thread )
        v20 = *ThreadWin32Thread;
    }
    v22 = v20 + 8;
    v23 = -v20;
    if ( (v22 & -(__int64)(v23 != 0)) != 0 && (*(_BYTE *)((v22 & -(__int64)(v23 != 0)) + 0x1C))-- == 1 )
      *(_QWORD *)(v22 & -(__int64)(v23 != 0)) &= ~0x100000uLL;
    GreReleaseSemaphoreSharedInternal(v7);
  }
  return v5;
}

```

## disassembly

```asm
0x140028080  push    rbx
0x140028082  push    rbp
0x140028083  push    rsi
0x140028084  push    rdi
0x140028085  push    r12
0x140028087  push    r13
0x140028089  push    r14
0x14002808b  push    r15
0x14002808d  sub     rsp, 58h
0x140028091  mov     ebx, edx
0x140028093  mov     rdi, rcx
0x140028096  call    cs:__imp_PsGetCurrentProcessId
0x14002809d  nop     dword ptr [rax+rax+00h]
0x1400280a2  mov     esi, 80000002h
0x1400280a7  mov     r14d, 0FFFFFFFCh
0x1400280ad  cmp     ebx, esi
0x1400280af  jnz     short loc_1400280C3
0x1400280b1  call    cs:__imp_PsGetCurrentProcessId
0x1400280b8  nop     dword ptr [rax+rax+00h]
0x1400280bd  mov     rbx, rax
0x1400280c0  and     ebx, r14d
0x1400280c3  xor     ebp, ebp
0x1400280c5  mov     r12d, ebp
0x1400280c8  cmp     ebx, esi
0x1400280ca  jnz     short loc_1400280DE
0x1400280cc  call    cs:__imp_PsGetCurrentProcessId
0x1400280d3  nop     dword ptr [rax+rax+00h]
0x1400280d8  mov     rbx, rax
0x1400280db  and     ebx, r14d
0x1400280de  call    cs:__imp_W32GetSessionState
0x1400280e5  nop     dword ptr [rax+rax+00h]
0x1400280ea  mov     r13, [rax+58h]
0x1400280ee  mov     r15, [r13+0]
0x1400280f2  add     r15, 5E8h
0x1400280f9  mov     rdx, r15
0x1400280fc  call    ??$GreAcquireSemaphoreCommon@$0BE@P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreAcquireSemaphoreCommon<20,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x140028101  mov     r9d, 1
0x140028107  lea     rcx, [rsp+98h+var_68]
0x14002810c  mov     r8, rdi
0x14002810f  mov     rdx, r13
0x140028112  call    ??0HANDLELOCK@@QEAA@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@W4HandleLockOptions@@@Z; HANDLELOCK::HANDLELOCK(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,HandleLockOptions)
0x140028117  cmp     [rsp+98h+var_60], ebp
0x14002811b  jz      loc_1400281DF
0x140028121  mov     r14, [rsp+98h+var_68]
0x140028126  cmp     byte ptr [r14+0Eh], 4
0x14002812b  jnz     short loc_1400281A9
0x14002812d  movzx   ecx, byte ptr [r14+0Dh]
0x140028132  movzx   eax, byte ptr [r14+0Ch]
0x140028137  shl     cx, 8
0x14002813b  or      cx, ax
0x14002813e  shr     edi, 10h
0x140028141  cmp     cx, di
0x140028144  jnz     short loc_1400281A9
0x140028146  mov     rcx, [rsp+98h+var_58]
0x14002814b  mov     esi, ebp
0x14002814d  mov     edx, [r14]
0x140028150  mov     rcx, [rcx+8]
0x140028154  mov     rax, [rcx]
0x140028157  mov     rax, [rax+60h]
0x14002815b  call    _guard_dispatch_icall
0x140028160  mov     rdi, rax
0x140028163  call    ?GreGetCurrentThread@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThread(void)
0x140028168  mov     rdx, rax
0x14002816b  mov     r8d, 1
0x140028171  test    rax, rax
0x140028174  jz      short loc_140028180
0x140028176  cmp     [rax+40h], rbp
0x14002817a  jnz     loc_1400282ED
0x140028180  movzx   ecx, word ptr [rdi+0Ch]
0x140028184  test    cx, cx
0x140028187  jnz     loc_1400282F8
0x14002818d  mov     ebp, [r14+8]
0x140028191  mov     r12d, r8d
0x140028194  and     ebp, 0FFFFFFFEh
0x140028197  test    esi, esi
0x140028199  jnz     loc_140028318
0x14002819f  cmp     ebp, ebx
0x1400281a1  jnz     loc_14002825E
0x1400281a7  xor     ebp, ebp
0x1400281a9  mov     rax, [rsp+98h+var_58]
0x1400281ae  mov     edx, [r14]
0x1400281b1  mov     rdi, [rax+8]
0x1400281b5  mov     rcx, rdi
0x1400281b8  mov     rbx, [rdi]
0x1400281bb  mov     rax, [rbx+60h]
0x1400281bf  call    _guard_dispatch_icall
0x1400281c4  mov     rdx, rax
0x1400281c7  mov     rcx, rdi
0x1400281ca  mov     rax, [rbx+30h]
0x1400281ce  call    _guard_dispatch_icall
0x1400281d3  call    cs:__imp_KeLeaveCriticalRegion
0x1400281da  nop     dword ptr [rax+rax+00h]
0x1400281df  test    r15, r15
0x1400281e2  jz      short loc_140028249
0x1400281e4  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, ebp
0x1400281ea  jnz     loc_140028327
0x1400281f0  mov     rsi, gs:188h
0x1400281f9  mov     rdi, rbp
0x1400281fc  call    cs:__imp_KeIsAttachedProcess
0x140028203  nop     dword ptr [rax+rax+00h]
0x140028208  test    al, al
0x14002820a  jnz     loc_1400282BE
0x140028210  mov     rcx, rsi
0x140028213  call    cs:__imp_PsGetThreadWin32Thread
0x14002821a  nop     dword ptr [rax+rax+00h]
0x14002821f  test    rax, rax
0x140028222  jz      short loc_140028227
0x140028224  mov     rdi, [rax]
0x140028227  lea     rax, [rdi+8]
0x14002822b  neg     rdi
0x14002822e  sbb     rdx, rdx
0x140028231  and     rdx, rax
0x140028234  jz      short loc_140028241
0x140028236  add     byte ptr [rdx+1Ch], 0FFh
0x14002823a  jnz     short loc_140028241
0x14002823c  btr     qword ptr [rdx], 14h
0x140028241  mov     rcx, r15; HSEMAPHORE
0x140028244  call    ?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x140028249  mov     eax, r12d
0x14002824c  add     rsp, 58h
0x140028250  pop     r15
0x140028252  pop     r14
0x140028254  pop     r13
0x140028256  pop     r12
0x140028258  pop     rdi
0x140028259  pop     rsi
0x14002825a  pop     rbp
0x14002825b  pop     rbx
0x14002825c  retn
0x14002825e  mov     ecx, ebx
0x140028260  call    HmgIncProcessHandleCount
0x140028265  mov     r12d, eax
0x140028268  test    eax, eax
0x14002826a  jz      loc_1400281A7
0x140028270  mov     edx, ebp
0x140028272  mov     rcx, r13
0x140028275  call    HmgDecProcessHandleCount
0x14002827a  mov     edx, ebx; unsigned int
0x14002827c  lea     rcx, [rsp+98h+var_68]; this
0x140028281  call    ?Pid@HANDLELOCK@@QEAAXK@Z; HANDLELOCK::Pid(ulong)
0x140028286  xor     ebp, ebp
0x140028288  test    ebx, ebx
0x14002828a  jnz     short loc_14002829A
0x14002828c  mov     eax, 0FFEFh
0x140028291  and     [rdi+0Eh], ax
0x140028295  jmp     loc_1400281A9
0x14002829a  cmp     ebx, 80000012h
0x1400282a0  jz      short loc_14002828C
0x1400282a2  movzx   eax, word ptr [rdi+0Ch]
0x1400282a6  test    ax, ax
0x1400282a9  jnz     short loc_1400282B4
0x1400282ab  cmp     [rdi+8], ebp
0x1400282ae  jz      loc_1400281A9
0x1400282b4  or      word ptr [rdi+0Eh], 10h
0x1400282b9  jmp     loc_1400281A9
0x1400282be  call    W32GetCurrentWin32kSessionId
0x1400282c3  mov     ebx, eax
0x1400282c5  call    cs:__imp_PsGetCurrentThreadProcess
0x1400282cc  nop     dword ptr [rax+rax+00h]
0x1400282d1  mov     rcx, rax
0x1400282d4  call    cs:__imp_PsGetProcessSessionIdEx
0x1400282db  nop     dword ptr [rax+rax+00h]
0x1400282e0  cmp     ebx, eax
0x1400282e2  jz      loc_140028210
0x1400282e8  jmp     loc_140028227
0x1400282ed  test    ebx, ebx
0x1400282ef  cmovnz  esi, r8d
0x1400282f3  jmp     loc_140028180
0x1400282f8  mov     rax, gs:188h
0x140028301  cmp     [rdi+10h], rax
0x140028305  jz      loc_14002818D
0x14002830b  test    esi, esi
0x14002830d  jz      loc_1400281A9
0x140028313  jmp     loc_14002818D
0x140028318  mov     rcx, rdx
0x14002831b  call    UMPDGetThreadClientPID
0x140028320  mov     ebx, eax
0x140028322  jmp     loc_14002819F
0x140028327  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits, 10h
0x14002832e  jz      loc_1400281F0
0x140028334  lea     rax, aHmgr; "Hmgr"
0x14002833b  mov     r9, r15
0x14002833e  lea     rdx, LockRelease
0x140028345  mov     [rsp+98h+var_78], rax
0x14002834a  call    McTemplateK0pz_EtwWriteTransfer
0x14002834f  jmp     loc_1400281F0
```
