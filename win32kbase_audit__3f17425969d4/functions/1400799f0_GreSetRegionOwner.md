# GreSetRegionOwner

- ea: `0x1400799f0`
- end: `0x140079cc4`
- name: `GreSetRegionOwner`
- size: `724`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400405b0`
- `0x140175af4`

## callees

- `0x140031fa0`
- `0x1400323a0`
- `0x140035008`
- `0x1400371c0`
- `0x1400771b8`
- `0x140077494`
- `0x1400799f0`
- `0x140079cd0`
- `0x140079f00`
- `0x14012e228`
- `0x140192b70`
- `0x1402389c0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140079b43`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140079b43`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x140079b83`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x140079b83`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140079a06`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140079a21`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140079a3c`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140079a06`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140079a21`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140079a3c`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140079c44`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140079c44`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140079c35`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140079c35`
- `ntoskrnl!KeIsAttachedProcess` at `0x140079b6c`
- `ntoskrnl!KeIsAttachedProcess` at `0x140079b6c`
- `WIN32K!W32GetSessionState` at `0x140079a4e`
- `WIN32K!W32GetSessionState` at `0x140079a4e`

## pseudocode

```c
__int64 __fastcall GreSetRegionOwner(__int64 a1, int a2)
{
  unsigned __int64 v2; // rbx
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  unsigned int v8; // r12d
  _QWORD *v9; // r13
  struct _ERESOURCE *v10; // r15
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // r8d
  unsigned int *v15; // r14
  BOOL v16; // esi
  __int64 v17; // rdi
  struct _GRETHREAD *CurrentThread; // rax
  __int64 v19; // r9
  __int64 v20; // rdx
  __int64 v21; // r8
  unsigned int v22; // ebp
  __int64 *v23; // rdi
  __int64 v24; // rbx
  __int64 v25; // rax
  struct _KTHREAD *v26; // rsi
  __int64 v27; // rdi
  __int64 v28; // rcx
  __int64 *ThreadWin32Thread; // rax
  __int64 v30; // rax
  __int64 v31; // rdi
  int CurrentWin32kSessionId; // ebx
  __int64 CurrentThreadProcess; // rax
  unsigned int *v36; // [rsp+30h] [rbp-68h] BYREF
  int v37; // [rsp+38h] [rbp-60h]
  __int64 v38; // [rsp+40h] [rbp-58h]

  LODWORD(v2) = a2;
  PsGetCurrentProcessId();
  if ( (_DWORD)v2 == -2147483646 )
    v2 = (unsigned __int64)PsGetCurrentProcessId() & 0xFFFFFFFC;
  v8 = 0;
  if ( (_DWORD)v2 == -2147483646 )
    v2 = (unsigned __int64)PsGetCurrentProcessId() & 0xFFFFFFFC;
  v9 = *(_QWORD **)(W32GetSessionState(v5, v4, v6, v7) + 88);
  v10 = (struct _ERESOURCE *)(*v9 + 1512LL);
  GreAcquireSemaphoreCommon<20,void (*)(HSEMAPHORE__ *)>(v11, (HSEMAPHORE)v10);
  HANDLELOCK::HANDLELOCK(&v36, v9, a1, 1);
  if ( v37 )
  {
    v15 = v36;
    if ( *((_BYTE *)v36 + 14) == 4 && *((_WORD *)v36 + 6) == WORD1(a1) )
    {
      v16 = 0;
      v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v38 + 8) + 96LL))(*(_QWORD *)(v38 + 8), *v36);
      CurrentThread = GreGetCurrentThread();
      v20 = (__int64)CurrentThread;
      v21 = 1;
      if ( CurrentThread && *((_QWORD *)CurrentThread + 8) )
        v16 = v2 != 0;
      if ( !*(_WORD *)(v17 + 12) || *(struct _KTHREAD **)(v17 + 16) == KeGetCurrentThread() || v16 )
      {
        v8 = 1;
        v22 = v15[2] & 0xFFFFFFFE;
        if ( v16 )
          LODWORD(v2) = UMPDGetThreadClientPID(CurrentThread);
        if ( v22 != (_DWORD)v2 )
        {
          v8 = HmgIncProcessHandleCount((unsigned int)v2, v20, v21, v19);
          if ( v8 )
          {
            HmgDecProcessHandleCount(v9, v22);
            HANDLELOCK::Pid((HANDLELOCK *)&v36, v2);
            if ( !(_DWORD)v2 || (_DWORD)v2 == -2147483630 )
            {
              *(_WORD *)(v17 + 14) &= ~0x10u;
            }
            else if ( *(_WORD *)(v17 + 12) || *(_DWORD *)(v17 + 8) )
            {
              *(_WORD *)(v17 + 14) |= 0x10u;
            }
          }
        }
      }
    }
    v23 = *(__int64 **)(v38 + 8);
    v24 = *v23;
    v25 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v23 + 96))(v23, *v15);
    (*(void (__fastcall **)(__int64 *, __int64))(v24 + 48))(v23, v25);
    KeLeaveCriticalRegion();
  }
  if ( v10 )
  {
    if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
      McTemplateK0pz_EtwWriteTransfer(v13, (unsigned int)LockRelease, v14, (_DWORD)v10, (__int64)L"Hmgr");
    v26 = KeGetCurrentThread();
    v27 = 0;
    if ( !(unsigned __int8)KeIsAttachedProcess(v13, v12)
      || (CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(v28),
          CurrentThreadProcess = PsGetCurrentThreadProcess(),
          CurrentWin32kSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
    {
      ThreadWin32Thread = (__int64 *)PsGetThreadWin32Thread(v26);
      if ( ThreadWin32Thread )
        v27 = *ThreadWin32Thread;
    }
    v30 = v27 + 8;
    v31 = -v27;
    if ( (v30 & -(__int64)(v31 != 0)) != 0 && (*(_BYTE *)((v30 & -(__int64)(v31 != 0)) + 0x1C))-- == 1 )
      *(_QWORD *)(v30 & -(__int64)(v31 != 0)) &= ~0x100000uLL;
    GreReleaseSemaphoreSharedInternal(v10);
  }
  return v8;
}

```

## disassembly

```asm
0x1400799f0  push    rbx
0x1400799f2  push    rbp
0x1400799f3  push    rsi
0x1400799f4  push    rdi
0x1400799f5  push    r12
0x1400799f7  push    r13
0x1400799f9  push    r14
0x1400799fb  push    r15
0x1400799fd  sub     rsp, 58h
0x140079a01  mov     ebx, edx
0x140079a03  mov     rdi, rcx
0x140079a06  call    cs:__imp_PsGetCurrentProcessId
0x140079a0d  nop     dword ptr [rax+rax+00h]
0x140079a12  mov     esi, 80000002h
0x140079a17  mov     r14d, 0FFFFFFFCh
0x140079a1d  cmp     ebx, esi
0x140079a1f  jnz     short loc_140079A33
0x140079a21  call    cs:__imp_PsGetCurrentProcessId
0x140079a28  nop     dword ptr [rax+rax+00h]
0x140079a2d  mov     rbx, rax
0x140079a30  and     ebx, r14d
0x140079a33  xor     ebp, ebp
0x140079a35  mov     r12d, ebp
0x140079a38  cmp     ebx, esi
0x140079a3a  jnz     short loc_140079A4E
0x140079a3c  call    cs:__imp_PsGetCurrentProcessId
0x140079a43  nop     dword ptr [rax+rax+00h]
0x140079a48  mov     rbx, rax
0x140079a4b  and     ebx, r14d
0x140079a4e  call    cs:__imp_W32GetSessionState
0x140079a55  nop     dword ptr [rax+rax+00h]
0x140079a5a  mov     r13, [rax+58h]
0x140079a5e  mov     r15, [r13+0]
0x140079a62  add     r15, 5E8h
0x140079a69  mov     rdx, r15
0x140079a6c  call    ??$GreAcquireSemaphoreCommon@$0BE@P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreAcquireSemaphoreCommon<20,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x140079a71  mov     r9d, 1
0x140079a77  lea     rcx, [rsp+98h+var_68]
0x140079a7c  mov     r8, rdi
0x140079a7f  mov     rdx, r13
0x140079a82  call    ??0HANDLELOCK@@QEAA@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@W4HandleLockOptions@@@Z; HANDLELOCK::HANDLELOCK(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,HandleLockOptions)
0x140079a87  cmp     [rsp+98h+var_60], ebp
0x140079a8b  jz      loc_140079B4F
0x140079a91  mov     r14, [rsp+98h+var_68]
0x140079a96  cmp     byte ptr [r14+0Eh], 4
0x140079a9b  jnz     short loc_140079B19
0x140079a9d  movzx   ecx, byte ptr [r14+0Dh]
0x140079aa2  movzx   eax, byte ptr [r14+0Ch]
0x140079aa7  shl     cx, 8
0x140079aab  or      cx, ax
0x140079aae  shr     edi, 10h
0x140079ab1  cmp     cx, di
0x140079ab4  jnz     short loc_140079B19
0x140079ab6  mov     rcx, [rsp+98h+var_58]
0x140079abb  mov     esi, ebp
0x140079abd  mov     edx, [r14]
0x140079ac0  mov     rcx, [rcx+8]
0x140079ac4  mov     rax, [rcx]
0x140079ac7  mov     rax, [rax+60h]
0x140079acb  call    _guard_dispatch_icall
0x140079ad0  mov     rdi, rax
0x140079ad3  call    ?GreGetCurrentThread@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThread(void)
0x140079ad8  mov     rdx, rax
0x140079adb  mov     r8d, 1
0x140079ae1  test    rax, rax
0x140079ae4  jz      short loc_140079AF0
0x140079ae6  cmp     [rax+40h], rbp
0x140079aea  jnz     loc_140079C5D
0x140079af0  movzx   ecx, word ptr [rdi+0Ch]
0x140079af4  test    cx, cx
0x140079af7  jnz     loc_140079C68
0x140079afd  mov     ebp, [r14+8]
0x140079b01  mov     r12d, r8d
0x140079b04  and     ebp, 0FFFFFFFEh
0x140079b07  test    esi, esi
0x140079b09  jnz     loc_140079C88
0x140079b0f  cmp     ebp, ebx
0x140079b11  jnz     loc_140079BCE
0x140079b17  xor     ebp, ebp
0x140079b19  mov     rax, [rsp+98h+var_58]
0x140079b1e  mov     edx, [r14]
0x140079b21  mov     rdi, [rax+8]
0x140079b25  mov     rcx, rdi
0x140079b28  mov     rbx, [rdi]
0x140079b2b  mov     rax, [rbx+60h]
0x140079b2f  call    _guard_dispatch_icall
0x140079b34  mov     rdx, rax
0x140079b37  mov     rcx, rdi
0x140079b3a  mov     rax, [rbx+30h]
0x140079b3e  call    _guard_dispatch_icall
0x140079b43  call    cs:__imp_KeLeaveCriticalRegion
0x140079b4a  nop     dword ptr [rax+rax+00h]
0x140079b4f  test    r15, r15
0x140079b52  jz      short loc_140079BB9
0x140079b54  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, ebp
0x140079b5a  jnz     loc_140079C97
0x140079b60  mov     rsi, gs:188h
0x140079b69  mov     rdi, rbp
0x140079b6c  call    cs:__imp_KeIsAttachedProcess
0x140079b73  nop     dword ptr [rax+rax+00h]
0x140079b78  test    al, al
0x140079b7a  jnz     loc_140079C2E
0x140079b80  mov     rcx, rsi
0x140079b83  call    cs:__imp_PsGetThreadWin32Thread
0x140079b8a  nop     dword ptr [rax+rax+00h]
0x140079b8f  test    rax, rax
0x140079b92  jz      short loc_140079B97
0x140079b94  mov     rdi, [rax]
0x140079b97  lea     rax, [rdi+8]
0x140079b9b  neg     rdi
0x140079b9e  sbb     rdx, rdx
0x140079ba1  and     rdx, rax
0x140079ba4  jz      short loc_140079BB1
0x140079ba6  add     byte ptr [rdx+1Ch], 0FFh
0x140079baa  jnz     short loc_140079BB1
0x140079bac  btr     qword ptr [rdx], 14h
0x140079bb1  mov     rcx, r15; HSEMAPHORE
0x140079bb4  call    ?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x140079bb9  mov     eax, r12d
0x140079bbc  add     rsp, 58h
0x140079bc0  pop     r15
0x140079bc2  pop     r14
0x140079bc4  pop     r13
0x140079bc6  pop     r12
0x140079bc8  pop     rdi
0x140079bc9  pop     rsi
0x140079bca  pop     rbp
0x140079bcb  pop     rbx
0x140079bcc  retn
0x140079bce  mov     ecx, ebx
0x140079bd0  call    HmgIncProcessHandleCount
0x140079bd5  mov     r12d, eax
0x140079bd8  test    eax, eax
0x140079bda  jz      loc_140079B17
0x140079be0  mov     edx, ebp
0x140079be2  mov     rcx, r13
0x140079be5  call    HmgDecProcessHandleCount
0x140079bea  mov     edx, ebx; unsigned int
0x140079bec  lea     rcx, [rsp+98h+var_68]; this
0x140079bf1  call    ?Pid@HANDLELOCK@@QEAAXK@Z; HANDLELOCK::Pid(ulong)
0x140079bf6  xor     ebp, ebp
0x140079bf8  test    ebx, ebx
0x140079bfa  jnz     short loc_140079C0A
0x140079bfc  mov     eax, 0FFEFh
0x140079c01  and     [rdi+0Eh], ax
0x140079c05  jmp     loc_140079B19
0x140079c0a  cmp     ebx, 80000012h
0x140079c10  jz      short loc_140079BFC
0x140079c12  movzx   eax, word ptr [rdi+0Ch]
0x140079c16  test    ax, ax
0x140079c19  jnz     short loc_140079C24
0x140079c1b  cmp     [rdi+8], ebp
0x140079c1e  jz      loc_140079B19
0x140079c24  or      word ptr [rdi+0Eh], 10h
0x140079c29  jmp     loc_140079B19
0x140079c2e  call    W32GetCurrentWin32kSessionId
0x140079c33  mov     ebx, eax
0x140079c35  call    cs:__imp_PsGetCurrentThreadProcess
0x140079c3c  nop     dword ptr [rax+rax+00h]
0x140079c41  mov     rcx, rax
0x140079c44  call    cs:__imp_PsGetProcessSessionIdEx
0x140079c4b  nop     dword ptr [rax+rax+00h]
0x140079c50  cmp     ebx, eax
0x140079c52  jz      loc_140079B80
0x140079c58  jmp     loc_140079B97
0x140079c5d  test    ebx, ebx
0x140079c5f  cmovnz  esi, r8d
0x140079c63  jmp     loc_140079AF0
0x140079c68  mov     rax, gs:188h
0x140079c71  cmp     [rdi+10h], rax
0x140079c75  jz      loc_140079AFD
0x140079c7b  test    esi, esi
0x140079c7d  jz      loc_140079B19
0x140079c83  jmp     loc_140079AFD
0x140079c88  mov     rcx, rdx
0x140079c8b  call    UMPDGetThreadClientPID
0x140079c90  mov     ebx, eax
0x140079c92  jmp     loc_140079B0F
0x140079c97  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits, 10h
0x140079c9e  jz      loc_140079B60
0x140079ca4  lea     rax, aHmgr; "Hmgr"
0x140079cab  mov     r9, r15
0x140079cae  lea     rdx, LockRelease
0x140079cb5  mov     [rsp+98h+var_78], rax
0x140079cba  call    McTemplateK0pz_EtwWriteTransfer
0x140079cbf  jmp     loc_140079B60
```
