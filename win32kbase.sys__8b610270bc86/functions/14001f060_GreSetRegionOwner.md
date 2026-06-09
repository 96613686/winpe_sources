# GreSetRegionOwner

- ea: `0x14001f060`
- end: `0x14001f334`
- name: `GreSetRegionOwner`
- size: `724`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140066b34`
- `0x140068400`

## callees

- `0x140006cf8`
- `0x140013ff0`
- `0x14001ca10`
- `0x14001f060`
- `0x14001f340`
- `0x14001f570`
- `0x140020728`
- `0x140020758`
- `0x140020a34`
- `0x140028974`
- `0x140190650`
- `0x140238bf0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001f1b3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001f1b3`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x14001f1f3`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x14001f1f3`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14001f076`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14001f091`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14001f0ac`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14001f076`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14001f091`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14001f0ac`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14001f2b4`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14001f2b4`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14001f2a5`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14001f2a5`
- `ntoskrnl!KeIsAttachedProcess` at `0x14001f1dc`
- `ntoskrnl!KeIsAttachedProcess` at `0x14001f1dc`
- `WIN32K!W32GetSessionState` at `0x14001f0be`
- `WIN32K!W32GetSessionState` at `0x14001f0be`

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
  struct _GRETHREAD *v15; // rdx
  __int64 v16; // r8
  unsigned int v17; // ebp
  __int64 *v18; // rdi
  __int64 v19; // rbx
  __int64 v20; // rax
  struct _KTHREAD *v21; // rsi
  __int64 v22; // rdi
  __int64 *ThreadWin32Thread; // rax
  __int64 v24; // rax
  __int64 v25; // rdi
  int CurrentWin32kSessionId; // ebx
  __int64 CurrentThreadProcess; // rax
  unsigned int *v30; // [rsp+30h] [rbp-68h] BYREF
  int v31; // [rsp+38h] [rbp-60h]
  __int64 v32; // [rsp+40h] [rbp-58h]

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
  HANDLELOCK::HANDLELOCK(&v30, v6, a1, 1);
  if ( v31 )
  {
    v11 = v30;
    if ( *((_BYTE *)v30 + 14) == 4 && *((_WORD *)v30 + 6) == WORD1(a1) )
    {
      v12 = 0;
      v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v32 + 8) + 96LL))(*(_QWORD *)(v32 + 8), *v30);
      CurrentThread = GreGetCurrentThread();
      v15 = CurrentThread;
      v16 = 1;
      if ( CurrentThread && *((_QWORD *)CurrentThread + 8) )
        v12 = v2 != 0;
      if ( !*(_WORD *)(v13 + 12) || *(struct _KTHREAD **)(v13 + 16) == KeGetCurrentThread() || v12 )
      {
        v5 = 1;
        v17 = v11[2] & 0xFFFFFFFE;
        if ( v12 )
          LODWORD(v2) = UMPDGetThreadClientPID(CurrentThread);
        if ( v17 != (_DWORD)v2 )
        {
          v5 = HmgIncProcessHandleCount((unsigned int)v2, v15, v16);
          if ( v5 )
          {
            HmgDecProcessHandleCount(v6, v17);
            HANDLELOCK::Pid((HANDLELOCK *)&v30, v2);
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
    v18 = *(__int64 **)(v32 + 8);
    v19 = *v18;
    v20 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v18 + 96))(v18, *v11);
    (*(void (__fastcall **)(__int64 *, __int64))(v19 + 48))(v18, v20);
    KeLeaveCriticalRegion();
  }
  if ( v7 )
  {
    if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
      McTemplateK0pz_EtwWriteTransfer(v9, (unsigned int)LockRelease, v10, (_DWORD)v7, (__int64)L"Hmgr");
    v21 = KeGetCurrentThread();
    v22 = 0;
    if ( !(unsigned __int8)KeIsAttachedProcess()
      || (CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(),
          CurrentThreadProcess = PsGetCurrentThreadProcess(),
          CurrentWin32kSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
    {
      ThreadWin32Thread = (__int64 *)PsGetThreadWin32Thread(v21);
      if ( ThreadWin32Thread )
        v22 = *ThreadWin32Thread;
    }
    v24 = v22 + 8;
    v25 = -v22;
    if ( (v24 & -(__int64)(v25 != 0)) != 0 && (*(_BYTE *)((v24 & -(__int64)(v25 != 0)) + 0x1C))-- == 1 )
      *(_QWORD *)(v24 & -(__int64)(v25 != 0)) &= ~0x100000uLL;
    GreReleaseSemaphoreSharedInternal(v7);
  }
  return v5;
}

```

## disassembly

```asm
0x14001f060  push    rbx
0x14001f062  push    rbp
0x14001f063  push    rsi
0x14001f064  push    rdi
0x14001f065  push    r12
0x14001f067  push    r13
0x14001f069  push    r14
0x14001f06b  push    r15
0x14001f06d  sub     rsp, 58h
0x14001f071  mov     ebx, edx
0x14001f073  mov     rdi, rcx
0x14001f076  call    cs:__imp_PsGetCurrentProcessId
0x14001f07d  nop     dword ptr [rax+rax+00h]
0x14001f082  mov     esi, 80000002h
0x14001f087  mov     r14d, 0FFFFFFFCh
0x14001f08d  cmp     ebx, esi
0x14001f08f  jnz     short loc_14001F0A3
0x14001f091  call    cs:__imp_PsGetCurrentProcessId
0x14001f098  nop     dword ptr [rax+rax+00h]
0x14001f09d  mov     rbx, rax
0x14001f0a0  and     ebx, r14d
0x14001f0a3  xor     ebp, ebp
0x14001f0a5  mov     r12d, ebp
0x14001f0a8  cmp     ebx, esi
0x14001f0aa  jnz     short loc_14001F0BE
0x14001f0ac  call    cs:__imp_PsGetCurrentProcessId
0x14001f0b3  nop     dword ptr [rax+rax+00h]
0x14001f0b8  mov     rbx, rax
0x14001f0bb  and     ebx, r14d
0x14001f0be  call    cs:__imp_W32GetSessionState
0x14001f0c5  nop     dword ptr [rax+rax+00h]
0x14001f0ca  mov     r13, [rax+58h]
0x14001f0ce  mov     r15, [r13+0]
0x14001f0d2  add     r15, 5E8h
0x14001f0d9  mov     rdx, r15
0x14001f0dc  call    ??$GreAcquireSemaphoreCommon@$0BE@P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreAcquireSemaphoreCommon<20,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x14001f0e1  mov     r9d, 1
0x14001f0e7  lea     rcx, [rsp+98h+var_68]
0x14001f0ec  mov     r8, rdi
0x14001f0ef  mov     rdx, r13
0x14001f0f2  call    ??0HANDLELOCK@@QEAA@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@W4HandleLockOptions@@@Z; HANDLELOCK::HANDLELOCK(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,HandleLockOptions)
0x14001f0f7  cmp     [rsp+98h+var_60], ebp
0x14001f0fb  jz      loc_14001F1BF
0x14001f101  mov     r14, [rsp+98h+var_68]
0x14001f106  cmp     byte ptr [r14+0Eh], 4
0x14001f10b  jnz     short loc_14001F189
0x14001f10d  movzx   ecx, byte ptr [r14+0Dh]
0x14001f112  movzx   eax, byte ptr [r14+0Ch]
0x14001f117  shl     cx, 8
0x14001f11b  or      cx, ax
0x14001f11e  shr     edi, 10h
0x14001f121  cmp     cx, di
0x14001f124  jnz     short loc_14001F189
0x14001f126  mov     rcx, [rsp+98h+var_58]
0x14001f12b  mov     esi, ebp
0x14001f12d  mov     edx, [r14]
0x14001f130  mov     rcx, [rcx+8]
0x14001f134  mov     rax, [rcx]
0x14001f137  mov     rax, [rax+60h]
0x14001f13b  call    _guard_dispatch_icall
0x14001f140  mov     rdi, rax
0x14001f143  call    ?GreGetCurrentThread@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThread(void)
0x14001f148  mov     rdx, rax
0x14001f14b  mov     r8d, 1
0x14001f151  test    rax, rax
0x14001f154  jz      short loc_14001F160
0x14001f156  cmp     [rax+40h], rbp
0x14001f15a  jnz     loc_14001F2CD
0x14001f160  movzx   ecx, word ptr [rdi+0Ch]
0x14001f164  test    cx, cx
0x14001f167  jnz     loc_14001F2D8
0x14001f16d  mov     ebp, [r14+8]
0x14001f171  mov     r12d, r8d
0x14001f174  and     ebp, 0FFFFFFFEh
0x14001f177  test    esi, esi
0x14001f179  jnz     loc_14001F2F8
0x14001f17f  cmp     ebp, ebx
0x14001f181  jnz     loc_14001F23E
0x14001f187  xor     ebp, ebp
0x14001f189  mov     rax, [rsp+98h+var_58]
0x14001f18e  mov     edx, [r14]
0x14001f191  mov     rdi, [rax+8]
0x14001f195  mov     rcx, rdi
0x14001f198  mov     rbx, [rdi]
0x14001f19b  mov     rax, [rbx+60h]
0x14001f19f  call    _guard_dispatch_icall
0x14001f1a4  mov     rdx, rax
0x14001f1a7  mov     rcx, rdi
0x14001f1aa  mov     rax, [rbx+30h]
0x14001f1ae  call    _guard_dispatch_icall
0x14001f1b3  call    cs:__imp_KeLeaveCriticalRegion
0x14001f1ba  nop     dword ptr [rax+rax+00h]
0x14001f1bf  test    r15, r15
0x14001f1c2  jz      short loc_14001F229
0x14001f1c4  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, ebp
0x14001f1ca  jnz     loc_14001F307
0x14001f1d0  mov     rsi, gs:188h
0x14001f1d9  mov     rdi, rbp
0x14001f1dc  call    cs:__imp_KeIsAttachedProcess
0x14001f1e3  nop     dword ptr [rax+rax+00h]
0x14001f1e8  test    al, al
0x14001f1ea  jnz     loc_14001F29E
0x14001f1f0  mov     rcx, rsi
0x14001f1f3  call    cs:__imp_PsGetThreadWin32Thread
0x14001f1fa  nop     dword ptr [rax+rax+00h]
0x14001f1ff  test    rax, rax
0x14001f202  jz      short loc_14001F207
0x14001f204  mov     rdi, [rax]
0x14001f207  lea     rax, [rdi+8]
0x14001f20b  neg     rdi
0x14001f20e  sbb     rdx, rdx
0x14001f211  and     rdx, rax
0x14001f214  jz      short loc_14001F221
0x14001f216  add     byte ptr [rdx+1Ch], 0FFh
0x14001f21a  jnz     short loc_14001F221
0x14001f21c  btr     qword ptr [rdx], 14h
0x14001f221  mov     rcx, r15; HSEMAPHORE
0x14001f224  call    ?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x14001f229  mov     eax, r12d
0x14001f22c  add     rsp, 58h
0x14001f230  pop     r15
0x14001f232  pop     r14
0x14001f234  pop     r13
0x14001f236  pop     r12
0x14001f238  pop     rdi
0x14001f239  pop     rsi
0x14001f23a  pop     rbp
0x14001f23b  pop     rbx
0x14001f23c  retn
0x14001f23e  mov     ecx, ebx
0x14001f240  call    HmgIncProcessHandleCount
0x14001f245  mov     r12d, eax
0x14001f248  test    eax, eax
0x14001f24a  jz      loc_14001F187
0x14001f250  mov     edx, ebp
0x14001f252  mov     rcx, r13
0x14001f255  call    HmgDecProcessHandleCount
0x14001f25a  mov     edx, ebx; unsigned int
0x14001f25c  lea     rcx, [rsp+98h+var_68]; this
0x14001f261  call    ?Pid@HANDLELOCK@@QEAAXK@Z; HANDLELOCK::Pid(ulong)
0x14001f266  xor     ebp, ebp
0x14001f268  test    ebx, ebx
0x14001f26a  jnz     short loc_14001F27A
0x14001f26c  mov     eax, 0FFEFh
0x14001f271  and     [rdi+0Eh], ax
0x14001f275  jmp     loc_14001F189
0x14001f27a  cmp     ebx, 80000012h
0x14001f280  jz      short loc_14001F26C
0x14001f282  movzx   eax, word ptr [rdi+0Ch]
0x14001f286  test    ax, ax
0x14001f289  jnz     short loc_14001F294
0x14001f28b  cmp     [rdi+8], ebp
0x14001f28e  jz      loc_14001F189
0x14001f294  or      word ptr [rdi+0Eh], 10h
0x14001f299  jmp     loc_14001F189
0x14001f29e  call    W32GetCurrentWin32kSessionId
0x14001f2a3  mov     ebx, eax
0x14001f2a5  call    cs:__imp_PsGetCurrentThreadProcess
0x14001f2ac  nop     dword ptr [rax+rax+00h]
0x14001f2b1  mov     rcx, rax
0x14001f2b4  call    cs:__imp_PsGetProcessSessionIdEx
0x14001f2bb  nop     dword ptr [rax+rax+00h]
0x14001f2c0  cmp     ebx, eax
0x14001f2c2  jz      loc_14001F1F0
0x14001f2c8  jmp     loc_14001F207
0x14001f2cd  test    ebx, ebx
0x14001f2cf  cmovnz  esi, r8d
0x14001f2d3  jmp     loc_14001F160
0x14001f2d8  mov     rax, gs:188h
0x14001f2e1  cmp     [rdi+10h], rax
0x14001f2e5  jz      loc_14001F16D
0x14001f2eb  test    esi, esi
0x14001f2ed  jz      loc_14001F189
0x14001f2f3  jmp     loc_14001F16D
0x14001f2f8  mov     rcx, rdx
0x14001f2fb  call    UMPDGetThreadClientPID
0x14001f300  mov     ebx, eax
0x14001f302  jmp     loc_14001F17F
0x14001f307  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits, 10h
0x14001f30e  jz      loc_14001F1D0
0x14001f314  lea     rax, aHmgr; "Hmgr"
0x14001f31b  mov     r9, r15
0x14001f31e  lea     rdx, LockRelease
0x14001f325  mov     [rsp+98h+var_78], rax
0x14001f32a  call    McTemplateK0pz_EtwWriteTransfer
0x14001f32f  jmp     loc_14001F1D0
```
