# DestroyThreadsObjects

- ea: `0x1400754b0`
- end: `0x1400756f7`
- name: `DestroyThreadsObjects`
- size: `583`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14002edcc`

## callees

- `0x140073a50`
- `0x1400754b0`
- `0x140075700`
- `0x1400a1390`
- `0x1400a16d0`
- `0x1401206d4`
- `0x1401b6ce8`
- `0x140238bf0`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400754bd`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140075508`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400754bd`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140075508`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140075635`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140075661`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140075696`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400756c2`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140075635`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140075661`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140075696`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400756c2`
- `WIN32K!W32GetUserSessionState` at `0x140075534`
- `WIN32K!W32GetUserSessionState` at `0x140075543`
- `WIN32K!W32GetUserSessionState` at `0x14007557f`
- `WIN32K!W32GetUserSessionState` at `0x140075534`
- `WIN32K!W32GetUserSessionState` at `0x140075543`
- `WIN32K!W32GetUserSessionState` at `0x14007557f`

## pseudocode

```c
void __fastcall DestroyThreadsObjects(__int64 a1)
{
  _QWORD **CurrentThreadWin32Thread; // rax
  _QWORD *v2; // rbx
  ULONG_PTR i; // rax
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // r15
  __int64 UserSessionState; // r14
  __int64 v9; // rcx
  __int64 v10; // rcx
  unsigned int j; // edi
  __int64 v12; // rbp
  __int64 v13; // rax
  __int64 v14; // rdx
  _QWORD *v15; // r8
  int (*v16)(void); // rax
  __int64 v17; // rdi
  void (__fastcall *v18)(__int64, __int64); // rax
  int (*v19)(void); // rax
  __int64 v20; // rdi
  void (__fastcall *v21)(__int64, __int64); // rax

  CurrentThreadWin32Thread = (_QWORD **)PsGetCurrentThreadWin32Thread(a1);
  if ( CurrentThreadWin32Thread )
    v2 = *CurrentThreadWin32Thread;
  else
    v2 = 0;
  DestroyCacheDCEntries(v2);
  for ( i = v2[56]; i; i = v2[56] )
    Win32HM_UnlockFromThread<1>((ULONG_PTR)v2, i);
  while ( 1 )
  {
    v4 = v2[47];
    if ( !v4 )
      break;
    PopAndFreeW32ThreadLock(v4);
  }
  AtomicExecutionCheck::EnforceConsistency(0);
  v7 = PsGetCurrentThreadWin32Thread(v5);
  ++*(_DWORD *)(v7 + 28);
  if ( v2[149] )
  {
    v6 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v6) + 48);
    v16 = *(int (**)(void))(v6 + 2640);
    if ( v16 )
    {
      if ( v16() >= 0 )
      {
        v17 = v2[149];
        v18 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v6) + 48) + 2648LL);
        if ( v18 )
          v18(v17, 1);
      }
    }
    v2[149] = 0;
  }
  if ( v2[150] )
  {
    v6 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v6) + 48);
    v19 = *(int (**)(void))(v6 + 2656);
    if ( v19 )
    {
      if ( v19() >= 0 )
      {
        v20 = v2[150];
        v21 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v6) + 48) + 2664LL);
        if ( v21 )
          v21(v20, 1);
      }
    }
    v2[150] = 0;
  }
  UserSessionState = W32GetUserSessionState(v6);
  for ( j = *(_DWORD *)(W32GetUserSessionState(v9) + 19648); (j & 0x80000000) == 0; --j )
  {
    v12 = *(_QWORD *)(UserSessionState + 19720) + 32LL * j;
    v13 = W32GetUserSessionState(v10);
    v14 = *(unsigned __int8 *)(v12 + 24);
    if ( (_BYTE)v14 )
    {
      v10 = 5LL * j;
      v15 = (_QWORD *)(*(_QWORD *)(v13 + 19664) + 40LL * j);
      if ( (dword_14023C9CC[6 * v14] & 2) != 0 )
      {
        if ( (_BYTE)v14 == 2 )
        {
          v10 = *(_QWORD *)(*v15 + 80LL);
          if ( v10 )
          {
            if ( *(_QWORD **)(v10 + 16) == v2 )
            {
              *(_QWORD *)(*v15 + 80LL) = 0;
              HMUnlockObject(v10);
            }
          }
        }
      }
      else if ( (_QWORD *)v15[1] == v2 && (*(_BYTE *)(v12 + 25) & 1) == 0 )
      {
        HMDestroyUnlockedObjectWorker((struct _HANDLEENTRY *)v12);
      }
    }
  }
  --*(_DWORD *)(v7 + 28);
}

```

## disassembly

```asm
0x1400754b0  push    rbx
0x1400754b2  push    rdi
0x1400754b3  push    r13
0x1400754b5  push    r14
0x1400754b7  push    r15
0x1400754b9  sub     rsp, 20h
0x1400754bd  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400754c4  nop     dword ptr [rax+rax+00h]
0x1400754c9  xor     r13d, r13d
0x1400754cc  test    rax, rax
0x1400754cf  jz      loc_14007562D
0x1400754d5  mov     rbx, [rax]
0x1400754d8  mov     rcx, rbx
0x1400754db  call    DestroyCacheDCEntries
0x1400754e0  mov     rax, [rbx+1C0h]
0x1400754e7  test    rax, rax
0x1400754ea  jnz     loc_140075610
0x1400754f0  mov     rcx, [rbx+178h]; this
0x1400754f7  test    rcx, rcx
0x1400754fa  jz      short loc_140075503
0x1400754fc  call    PopAndFreeW32ThreadLock
0x140075501  jmp     short loc_1400754F0
0x140075503  call    ?EnforceConsistency@AtomicExecutionCheck@@AEAAXXZ; AtomicExecutionCheck::EnforceConsistency(void)
0x140075508  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14007550f  nop     dword ptr [rax+rax+00h]
0x140075514  mov     r15, rax
0x140075517  inc     dword ptr [rax+1Ch]
0x14007551a  cmp     [rbx+4A8h], r13
0x140075521  jnz     loc_140075635
0x140075527  cmp     [rbx+4B0h], r13
0x14007552e  jnz     loc_140075696
0x140075534  call    cs:__imp_W32GetUserSessionState
0x14007553b  nop     dword ptr [rax+rax+00h]
0x140075540  mov     r14, rax
0x140075543  call    cs:__imp_W32GetUserSessionState
0x14007554a  nop     dword ptr [rax+rax+00h]
0x14007554f  mov     edi, [rax+4CC0h]
0x140075555  test    edi, edi
0x140075557  js      short loc_1400755C7
0x140075559  mov     [rsp+48h+arg_0], rbp
0x14007555e  mov     [rsp+48h+arg_8], rsi
0x140075563  mov     [rsp+48h+arg_10], r12
0x140075568  lea     r12, dword_14023C9CC
0x14007556f  nop
0x140075570  mov     ebp, edi
0x140075572  shl     rbp, 5
0x140075576  add     rbp, [r14+4D08h]
0x14007557d  mov     esi, edi
0x14007557f  call    cs:__imp_W32GetUserSessionState
0x140075586  nop     dword ptr [rax+rax+00h]
0x14007558b  movzx   edx, byte ptr [rbp+18h]
0x14007558f  test    dl, dl
0x140075591  jz      short loc_1400755B3
0x140075593  mov     rax, [rax+4CD0h]
0x14007559a  lea     rcx, [rsi+rsi*4]
0x14007559e  lea     r8, [rax+rcx*8]
0x1400755a2  lea     rax, [rdx+rdx*2]
0x1400755a6  test    byte ptr [r12+rax*8], 2
0x1400755ab  jnz     short loc_1400755D9
0x1400755ad  cmp     [r8+8], rbx
0x1400755b1  jz      short loc_1400755FB
0x1400755b3  sub     edi, 1
0x1400755b6  jns     short loc_140075570
0x1400755b8  mov     r12, [rsp+48h+arg_10]
0x1400755bd  mov     rsi, [rsp+48h+arg_8]
0x1400755c2  mov     rbp, [rsp+48h+arg_0]
0x1400755c7  dec     dword ptr [r15+1Ch]
0x1400755cb  add     rsp, 20h
0x1400755cf  pop     r15
0x1400755d1  pop     r14
0x1400755d3  pop     r13
0x1400755d5  pop     rdi
0x1400755d6  pop     rbx
0x1400755d7  retn
0x1400755d9  cmp     dl, 2
0x1400755dc  jnz     short loc_1400755B3
0x1400755de  mov     rax, [r8]
0x1400755e1  mov     rcx, [rax+50h]
0x1400755e5  test    rcx, rcx
0x1400755e8  jz      short loc_1400755B3
0x1400755ea  cmp     [rcx+10h], rbx
0x1400755ee  jnz     short loc_1400755B3
0x1400755f0  mov     [rax+50h], r13
0x1400755f4  call    HMUnlockObject
0x1400755f9  jmp     short loc_1400755B3
0x1400755fb  test    byte ptr [rbp+19h], 1
0x1400755ff  jnz     short loc_1400755B3
0x140075601  mov     rcx, rbp; struct _HANDLEENTRY *
0x140075604  call    ?HMDestroyUnlockedObjectWorker@@YAXPEAU_HANDLEENTRY@@@Z; HMDestroyUnlockedObjectWorker(_HANDLEENTRY *)
0x140075609  jmp     short loc_1400755B3
0x140075610  mov     rdx, rax; BugCheckParameter3
0x140075613  mov     rcx, rbx; BugCheckParameter2
0x140075616  call    ??$Win32HM_UnlockFromThread@$00@@YAPEAU_HEAD@@PEAUtagTHREADINFO@@PEAU_Win32HMThreadLockItem@@@Z; Win32HM_UnlockFromThread<1>(tagTHREADINFO *,_Win32HMThreadLockItem *)
0x14007561b  mov     rax, [rbx+1C0h]
0x140075622  test    rax, rax
0x140075625  jz      loc_1400754F0
0x14007562b  jmp     short loc_140075610
0x14007562d  mov     rbx, r13
0x140075630  jmp     loc_1400754D8
0x140075635  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14007563c  nop     dword ptr [rax+rax+00h]
0x140075641  mov     rcx, [rax+30h]
0x140075645  mov     rax, [rcx+0A50h]
0x14007564c  test    rax, rax
0x14007564f  jz      short loc_14007568A
0x140075651  call    _guard_dispatch_icall
0x140075656  test    eax, eax
0x140075658  js      short loc_14007568A
0x14007565a  mov     rdi, [rbx+4A8h]
0x140075661  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140075668  nop     dword ptr [rax+rax+00h]
0x14007566d  mov     rdx, [rax+30h]
0x140075671  mov     rax, [rdx+0A58h]
0x140075678  test    rax, rax
0x14007567b  jz      short loc_14007568A
0x14007567d  mov     edx, 1
0x140075682  mov     rcx, rdi
0x140075685  call    _guard_dispatch_icall
0x14007568a  mov     [rbx+4A8h], r13
0x140075691  jmp     loc_140075527
0x140075696  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14007569d  nop     dword ptr [rax+rax+00h]
0x1400756a2  mov     rcx, [rax+30h]
0x1400756a6  mov     rax, [rcx+0A60h]
0x1400756ad  test    rax, rax
0x1400756b0  jz      short loc_1400756EB
0x1400756b2  call    _guard_dispatch_icall
0x1400756b7  test    eax, eax
0x1400756b9  js      short loc_1400756EB
0x1400756bb  mov     rdi, [rbx+4B0h]
0x1400756c2  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1400756c9  nop     dword ptr [rax+rax+00h]
0x1400756ce  mov     r8, [rax+30h]
0x1400756d2  mov     rax, [r8+0A68h]
0x1400756d9  test    rax, rax
0x1400756dc  jz      short loc_1400756EB
0x1400756de  mov     edx, 1
0x1400756e3  mov     rcx, rdi
0x1400756e6  call    _guard_dispatch_icall
0x1400756eb  mov     [rbx+4B0h], r13
0x1400756f2  jmp     loc_140075534
```
