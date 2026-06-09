# DEVLOCKOBJ::~DEVLOCKOBJ(void)

- ea: `0x140022dbc`
- end: `0x140023074`
- name: `??1DEVLOCKOBJ@@QEAA@XZ`
- size: `696`
- prototype: `void __fastcall(DEVLOCKOBJ *__hidden this)`
- caller_count: `8`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x140016274`
- `0x140017400`
- `0x1400179f0`
- `0x1400222f0`
- `0x140022740`
- `0x14003dee0`
- `0x140103200`
- `0x1401c24c0`

## callees

- `0x140017490`
- `0x140017ea8`
- `0x140022510`
- `0x140022dbc`
- `0x14002307c`
- `0x1400232f4`
- `0x1400317e0`
- `0x140031fa0`
- `0x1400371c0`
- `0x140079f00`
- `0x140192b70`
- `0x1402389c0`

## import_xrefs

- `ntoskrnl!PsGetThreadWin32Thread` at `0x140022eae`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x140022eae`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14002300c`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14002300c`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140022ffd`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140022ffd`
- `ntoskrnl!KeIsAttachedProcess` at `0x140022e97`
- `ntoskrnl!KeIsAttachedProcess` at `0x140022e97`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140022e2d`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140022e2d`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140022dd1`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140022df6`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140022ee3`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140022f08`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140022dd1`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140022df6`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140022ee3`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140022f08`
- `WIN32K!W32GetSessionState` at `0x140022fb1`
- `WIN32K!W32GetSessionState` at `0x140022fb1`

## pseudocode

```c
void __fastcall DEVLOCKOBJ::~DEVLOCKOBJ(DEVLOCKOBJ *this, __int64 a2)
{
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  int (*v7)(void); // rax
  void (__fastcall *v8)(DEVLOCKOBJ *); // rax
  int v9; // eax
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v11; // rcx
  __int64 v12; // rax
  int v13; // eax
  HSEMAPHORE v14; // rbp
  struct _KTHREAD *v15; // r14
  __int64 v16; // rsi
  __int64 *ThreadWin32Thread; // rax
  __int64 v18; // rax
  __int64 v19; // rsi
  int (*v21)(void); // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  void (__fastcall *v24)(char *, char *, char *, char *); // rax
  __int64 v25; // rax
  struct _GRETHREAD *CurrentThread; // rax
  __int64 SessionState; // rax
  int CurrentWin32kSessionId; // ebx
  __int64 CurrentThreadProcess; // rax

  v3 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(this, a2) + 24);
  v7 = *(int (**)(void))(v3 + 784);
  if ( v7 )
  {
    if ( v7() >= 0 )
    {
      v4 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v4, v3) + 24);
      v8 = *(void (__fastcall **)(DEVLOCKOBJ *))(v4 + 792);
      if ( v8 )
        v8(this);
    }
  }
  v9 = *((_DWORD *)this + 6);
  if ( (v9 & 0x1000) != 0 )
  {
    GreDecLockCount();
    *((_DWORD *)this + 6) &= ~0x1000u;
    CurrentThread = GreGetCurrentThread();
    if ( CurrentThread )
    {
      *((_QWORD *)CurrentThread + 38) = 0;
      *((_QWORD *)CurrentThread + 37) = 0;
    }
  }
  else if ( (v9 & 0x80000) != 0 )
  {
    CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread(v4, v3, v5, v6);
    if ( CurrentThreadWin32Thread )
      v11 = *CurrentThreadWin32Thread;
    else
      v11 = 0;
    v12 = v11 + 8;
    v4 = -v11;
    v3 = v12 & -(__int64)(v4 != 0);
    if ( v3 )
      --*(_DWORD *)((v12 & -(__int64)(v4 != 0)) + 0x154);
    *((_DWORD *)this + 6) &= ~0x80000u;
  }
  if ( *(_QWORD *)this )
  {
    if ( (*((_DWORD *)this + 6) & 0x100000) != 0 )
    {
      SessionState = W32GetSessionState(v4);
      GreReleaseSemaphoreCommon<2,void (*)(HSEMAPHORE__ *)>(
        GreReleaseSemaphoreSharedInternal,
        **(_QWORD **)(SessionState + 88) + 1144LL);
      *((_DWORD *)this + 6) &= ~0x100000u;
    }
    else
    {
      GreReleaseSemaphoreExclusive<8,PDEVOBJ>(*((_QWORD *)this + 2));
    }
  }
  v13 = *((_DWORD *)this + 6);
  if ( (v13 & 8) != 0 )
    *((_DWORD *)this + 6) = v13 & 0xFFFFFFF7;
  v14 = (HSEMAPHORE)*((_QWORD *)this + 1);
  if ( v14 )
  {
    if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
      McTemplateK0pz_EtwWriteTransfer(
        v4,
        (unsigned int)LockRelease,
        v5,
        *((_QWORD *)this + 1),
        (__int64)L"DynamicModeChange");
    v15 = KeGetCurrentThread();
    v16 = 0;
    if ( !(unsigned __int8)KeIsAttachedProcess(v4, v3)
      || (CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(),
          CurrentThreadProcess = PsGetCurrentThreadProcess(),
          CurrentWin32kSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
    {
      ThreadWin32Thread = (__int64 *)PsGetThreadWin32Thread(v15);
      if ( ThreadWin32Thread )
        v16 = *ThreadWin32Thread;
    }
    v18 = v16 + 8;
    v19 = -v16;
    if ( (v18 & -(__int64)(v19 != 0)) != 0 && (*(_BYTE *)((v18 & -(__int64)(v19 != 0)) + 9))-- == 1 )
      *(_QWORD *)(v18 & -(__int64)(v19 != 0)) &= ~2uLL;
    GreReleaseSemaphoreSharedInternal(v14);
  }
  v21 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v4, v3) + 24) + 800LL);
  if ( v21 )
  {
    if ( v21() >= 0 )
    {
      v24 = *(void (__fastcall **)(char *, char *, char *, char *))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v23, v22)
                                                                              + 24)
                                                                  + 808LL);
      if ( v24 )
        v24((char *)this + 152, (char *)this + 144, (char *)this + 136, (char *)this + 28);
    }
  }
  v25 = *((_QWORD *)this + 4);
  if ( v25 )
  {
    if ( *((_BYTE *)this + 128) )
    {
      *(_DWORD *)(v25 + 40) &= ~2u;
      *((_BYTE *)this + 128) = 0;
    }
    DCOBJ::vUnlock((DEVLOCKOBJ *)((char *)this + 32));
  }
  PopThreadGuardedObject((char *)this + 96);
  DCOBJ::~DCOBJ((DEVLOCKOBJ *)((char *)this + 32));
}

```

## disassembly

```asm
0x140022dbc  mov     [rsp+arg_8], rbx
0x140022dc1  mov     [rsp+arg_10], rbp
0x140022dc6  push    rsi
0x140022dc7  push    rdi
0x140022dc8  push    r14
0x140022dca  sub     rsp, 30h
0x140022dce  mov     rdi, rcx
0x140022dd1  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140022dd8  nop     dword ptr [rax+rax+00h]
0x140022ddd  mov     rdx, [rax+18h]
0x140022de1  mov     rax, [rdx+310h]
0x140022de8  test    rax, rax
0x140022deb  jz      short loc_140022E1A
0x140022ded  call    _guard_dispatch_icall
0x140022df2  test    eax, eax
0x140022df4  js      short loc_140022E1A
0x140022df6  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140022dfd  nop     dword ptr [rax+rax+00h]
0x140022e02  mov     rcx, [rax+18h]
0x140022e06  mov     rax, [rcx+318h]
0x140022e0d  test    rax, rax
0x140022e10  jz      short loc_140022E1A
0x140022e12  mov     rcx, rdi
0x140022e15  call    _guard_dispatch_icall
0x140022e1a  mov     eax, [rdi+18h]
0x140022e1d  bt      eax, 0Ch
0x140022e21  jb      loc_140022F75
0x140022e27  bt      eax, 13h
0x140022e2b  jnb     short loc_140022E5F
0x140022e2d  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140022e34  nop     dword ptr [rax+rax+00h]
0x140022e39  test    rax, rax
0x140022e3c  jz      loc_140022FEF
0x140022e42  mov     rcx, [rax]
0x140022e45  lea     rax, [rcx+8]
0x140022e49  neg     rcx
0x140022e4c  sbb     rdx, rdx
0x140022e4f  and     rdx, rax
0x140022e52  jz      short loc_140022E5A
0x140022e54  dec     dword ptr [rdx+154h]
0x140022e5a  btr     dword ptr [rdi+18h], 13h
0x140022e5f  cmp     qword ptr [rdi], 0
0x140022e63  jnz     loc_140022FA8
0x140022e69  mov     eax, [rdi+18h]
0x140022e6c  test    al, 8
0x140022e6e  jz      short loc_140022E76
0x140022e70  and     eax, 0FFFFFFF7h
0x140022e73  mov     [rdi+18h], eax
0x140022e76  mov     rbp, [rdi+8]
0x140022e7a  test    rbp, rbp
0x140022e7d  jz      short loc_140022EE3
0x140022e7f  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, 0
0x140022e86  jnz     loc_140023025
0x140022e8c  mov     r14, gs:188h
0x140022e95  xor     esi, esi
0x140022e97  call    cs:__imp_KeIsAttachedProcess
0x140022e9e  nop     dword ptr [rax+rax+00h]
0x140022ea3  test    al, al
0x140022ea5  jnz     loc_140022FF6
0x140022eab  mov     rcx, r14
0x140022eae  call    cs:__imp_PsGetThreadWin32Thread
0x140022eb5  nop     dword ptr [rax+rax+00h]
0x140022eba  test    rax, rax
0x140022ebd  jz      short loc_140022EC2
0x140022ebf  mov     rsi, [rax]
0x140022ec2  lea     rax, [rsi+8]
0x140022ec6  neg     rsi
0x140022ec9  sbb     rdx, rdx
0x140022ecc  and     rdx, rax
0x140022ecf  jz      short loc_140022EDB
0x140022ed1  add     byte ptr [rdx+9], 0FFh
0x140022ed5  jnz     short loc_140022EDB
0x140022ed7  and     qword ptr [rdx], 0FFFFFFFFFFFFFFFDh
0x140022edb  mov     rcx, rbp; HSEMAPHORE
0x140022ede  call    ?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x140022ee3  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140022eea  nop     dword ptr [rax+rax+00h]
0x140022eef  mov     rcx, [rax+18h]
0x140022ef3  mov     rax, [rcx+320h]
0x140022efa  test    rax, rax
0x140022efd  jz      short loc_140022F42
0x140022eff  call    _guard_dispatch_icall
0x140022f04  test    eax, eax
0x140022f06  js      short loc_140022F42
0x140022f08  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140022f0f  nop     dword ptr [rax+rax+00h]
0x140022f14  mov     rcx, [rax+18h]
0x140022f18  mov     rax, [rcx+328h]
0x140022f1f  test    rax, rax
0x140022f22  jz      short loc_140022F42
0x140022f24  lea     r9, [rdi+1Ch]
0x140022f28  lea     r8, [rdi+88h]
0x140022f2f  lea     rdx, [rdi+90h]
0x140022f36  lea     rcx, [rdi+98h]
0x140022f3d  call    _guard_dispatch_icall
0x140022f42  mov     rax, [rdi+20h]
0x140022f46  test    rax, rax
0x140022f49  jnz     loc_140023052
0x140022f4f  lea     rcx, [rdi+60h]
0x140022f53  call    PopThreadGuardedObject
0x140022f58  lea     rcx, [rdi+20h]; this
0x140022f5c  call    ??1DCOBJ@@QEAA@XZ; DCOBJ::~DCOBJ(void)
0x140022f61  mov     rbx, [rsp+48h+arg_8]
0x140022f66  mov     rbp, [rsp+48h+arg_10]
0x140022f6b  add     rsp, 30h
0x140022f6f  pop     r14
0x140022f71  pop     rdi
0x140022f72  pop     rsi
0x140022f73  retn
0x140022f75  call    GreDecLockCount
0x140022f7a  btr     dword ptr [rdi+18h], 0Ch
0x140022f7f  call    ?GreGetCurrentThread@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThread(void)
0x140022f84  test    rax, rax
0x140022f87  jz      loc_140022E5F
0x140022f8d  mov     qword ptr [rax+130h], 0
0x140022f98  mov     qword ptr [rax+128h], 0
0x140022fa3  jmp     loc_140022E5F
0x140022fa8  test    dword ptr [rdi+18h], 100000h
0x140022faf  jz      short loc_140022FE1
0x140022fb1  call    cs:__imp_W32GetSessionState
0x140022fb8  nop     dword ptr [rax+rax+00h]
0x140022fbd  mov     rcx, [rax+58h]
0x140022fc1  mov     rdx, [rcx]
0x140022fc4  lea     rcx, ?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x140022fcb  add     rdx, 478h
0x140022fd2  call    ??$GreReleaseSemaphoreCommon@$01P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<2,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x140022fd7  btr     dword ptr [rdi+18h], 14h
0x140022fdc  jmp     loc_140022E69
0x140022fe1  mov     rcx, [rdi+10h]
0x140022fe5  call    ??$GreReleaseSemaphoreExclusive@$07VPDEVOBJ@@@@YAXVPDEVOBJ@@@Z; GreReleaseSemaphoreExclusive<8,PDEVOBJ>(PDEVOBJ)
0x140022fea  jmp     loc_140022E69
0x140022fef  xor     ecx, ecx
0x140022ff1  jmp     loc_140022E45
0x140022ff6  call    W32GetCurrentWin32kSessionId
0x140022ffb  mov     ebx, eax
0x140022ffd  call    cs:__imp_PsGetCurrentThreadProcess
0x140023004  nop     dword ptr [rax+rax+00h]
0x140023009  mov     rcx, rax
0x14002300c  call    cs:__imp_PsGetProcessSessionIdEx
0x140023013  nop     dword ptr [rax+rax+00h]
0x140023018  cmp     ebx, eax
0x14002301a  jz      loc_140022EAB
0x140023020  jmp     loc_140022EC2
0x140023025  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits, 10h
0x14002302c  jz      loc_140022E8C
0x140023032  lea     rax, aDynamicmodecha; "DynamicModeChange"
0x140023039  mov     r9, rbp
0x14002303c  lea     rdx, LockRelease
0x140023043  mov     [rsp+48h+var_28], rax
0x140023048  call    McTemplateK0pz_EtwWriteTransfer
0x14002304d  jmp     loc_140022E8C
0x140023052  cmp     byte ptr [rdi+80h], 0
0x140023059  jz      short loc_140023066
0x14002305b  and     dword ptr [rax+28h], 0FFFFFFFDh
0x14002305f  mov     byte ptr [rdi+80h], 0
0x140023066  lea     rcx, [rdi+20h]; this
0x14002306a  call    ?vUnlock@DCOBJ@@QEAAXXZ; DCOBJ::vUnlock(void)
0x14002306f  jmp     loc_140022F4F
```
