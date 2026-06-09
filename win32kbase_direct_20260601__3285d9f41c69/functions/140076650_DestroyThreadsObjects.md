# DestroyThreadsObjects

- ea: `0x140076650`
- end: `0x140076897`
- name: `DestroyThreadsObjects`
- size: `583`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14003804c`

## callees

- `0x140074bf0`
- `0x140076650`
- `0x1400768a0`
- `0x140098190`
- `0x1400984d0`
- `0x140120a44`
- `0x1401b6788`
- `0x140238240`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14007665d`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400766a8`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14007665d`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400766a8`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400767d5`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140076801`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140076836`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140076862`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400767d5`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140076801`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140076836`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140076862`
- `WIN32K!W32GetUserSessionState` at `0x1400766d4`
- `WIN32K!W32GetUserSessionState` at `0x1400766e3`
- `WIN32K!W32GetUserSessionState` at `0x14007671f`
- `WIN32K!W32GetUserSessionState` at `0x1400766d4`
- `WIN32K!W32GetUserSessionState` at `0x1400766e3`
- `WIN32K!W32GetUserSessionState` at `0x14007671f`

## pseudocode

```c
void __fastcall DestroyThreadsObjects(__int64 a1)
{
  _QWORD **CurrentThreadWin32Thread; // rax
  _QWORD *v2; // rbx
  ULONG_PTR i; // rax
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r15
  __int64 UserSessionState; // r14
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rcx
  unsigned int j; // edi
  _QWORD *v17; // r8
  __int64 v18; // rbp
  __int64 v19; // rax
  int (*v20)(void); // rax
  __int64 v21; // rdi
  void (__fastcall *v22)(__int64, __int64); // rax
  int (*v23)(void); // rax
  __int64 v24; // rdi
  void (__fastcall *v25)(__int64, __int64); // rax

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
  v9 = PsGetCurrentThreadWin32Thread(v5);
  ++*(_DWORD *)(v9 + 28);
  if ( v2[149] )
  {
    v7 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v7, v6) + 48);
    v20 = *(int (**)(void))(v7 + 2640);
    if ( v20 )
    {
      if ( v20() >= 0 )
      {
        v21 = v2[149];
        v6 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v7, v6) + 48);
        v22 = *(void (__fastcall **)(__int64, __int64))(v6 + 2648);
        if ( v22 )
          v22(v21, 1);
      }
    }
    v2[149] = 0;
  }
  if ( v2[150] )
  {
    v7 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v7, v6) + 48);
    v23 = *(int (**)(void))(v7 + 2656);
    if ( v23 )
    {
      if ( v23() >= 0 )
      {
        v24 = v2[150];
        v8 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v7, v6) + 48);
        v25 = *(void (__fastcall **)(__int64, __int64))(v8 + 2664);
        if ( v25 )
          v25(v24, 1);
      }
    }
    v2[150] = 0;
  }
  UserSessionState = W32GetUserSessionState(v7, v6, v8);
  for ( j = *(_DWORD *)(W32GetUserSessionState(v12, v11, v13) + 19648); (j & 0x80000000) == 0; --j )
  {
    v18 = *(_QWORD *)(UserSessionState + 19720) + 32LL * j;
    v19 = W32GetUserSessionState(v15, v14, v17);
    v14 = *(unsigned __int8 *)(v18 + 24);
    if ( (_BYTE)v14 )
    {
      v15 = 5LL * j;
      v17 = (_QWORD *)(*(_QWORD *)(v19 + 19664) + 40LL * j);
      if ( (dword_14023BD3C[6 * v14] & 2) != 0 )
      {
        if ( (_BYTE)v14 == 2 )
        {
          v15 = *(_QWORD *)(*v17 + 80LL);
          if ( v15 )
          {
            if ( *(_QWORD **)(v15 + 16) == v2 )
            {
              *(_QWORD *)(*v17 + 80LL) = 0;
              HMUnlockObject(v15);
            }
          }
        }
      }
      else if ( (_QWORD *)v17[1] == v2 && (*(_BYTE *)(v18 + 25) & 1) == 0 )
      {
        HMDestroyUnlockedObjectWorker((struct _HANDLEENTRY *)v18, v14, (__int64)v17);
      }
    }
  }
  --*(_DWORD *)(v9 + 28);
}

```

## disassembly

```asm
0x140076650  push    rbx
0x140076652  push    rdi
0x140076653  push    r13
0x140076655  push    r14
0x140076657  push    r15
0x140076659  sub     rsp, 20h
0x14007665d  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140076664  nop     dword ptr [rax+rax+00h]
0x140076669  xor     r13d, r13d
0x14007666c  test    rax, rax
0x14007666f  jz      loc_1400767CD
0x140076675  mov     rbx, [rax]
0x140076678  mov     rcx, rbx
0x14007667b  call    DestroyCacheDCEntries
0x140076680  mov     rax, [rbx+1C0h]
0x140076687  test    rax, rax
0x14007668a  jnz     loc_1400767B0
0x140076690  mov     rcx, [rbx+178h]; this
0x140076697  test    rcx, rcx
0x14007669a  jz      short loc_1400766A3
0x14007669c  call    PopAndFreeW32ThreadLock
0x1400766a1  jmp     short loc_140076690
0x1400766a3  call    ?EnforceConsistency@AtomicExecutionCheck@@AEAAXXZ; AtomicExecutionCheck::EnforceConsistency(void)
0x1400766a8  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400766af  nop     dword ptr [rax+rax+00h]
0x1400766b4  mov     r15, rax
0x1400766b7  inc     dword ptr [rax+1Ch]
0x1400766ba  cmp     [rbx+4A8h], r13
0x1400766c1  jnz     loc_1400767D5
0x1400766c7  cmp     [rbx+4B0h], r13
0x1400766ce  jnz     loc_140076836
0x1400766d4  call    cs:__imp_W32GetUserSessionState
0x1400766db  nop     dword ptr [rax+rax+00h]
0x1400766e0  mov     r14, rax
0x1400766e3  call    cs:__imp_W32GetUserSessionState
0x1400766ea  nop     dword ptr [rax+rax+00h]
0x1400766ef  mov     edi, [rax+4CC0h]
0x1400766f5  test    edi, edi
0x1400766f7  js      short loc_140076767
0x1400766f9  mov     [rsp+48h+arg_0], rbp
0x1400766fe  mov     [rsp+48h+arg_8], rsi
0x140076703  mov     [rsp+48h+arg_10], r12
0x140076708  lea     r12, dword_14023BD3C
0x14007670f  nop
0x140076710  mov     ebp, edi
0x140076712  shl     rbp, 5
0x140076716  add     rbp, [r14+4D08h]
0x14007671d  mov     esi, edi
0x14007671f  call    cs:__imp_W32GetUserSessionState
0x140076726  nop     dword ptr [rax+rax+00h]
0x14007672b  movzx   edx, byte ptr [rbp+18h]
0x14007672f  test    dl, dl
0x140076731  jz      short loc_140076753
0x140076733  mov     rax, [rax+4CD0h]
0x14007673a  lea     rcx, [rsi+rsi*4]
0x14007673e  lea     r8, [rax+rcx*8]
0x140076742  lea     rax, [rdx+rdx*2]
0x140076746  test    byte ptr [r12+rax*8], 2
0x14007674b  jnz     short loc_140076779
0x14007674d  cmp     [r8+8], rbx
0x140076751  jz      short loc_14007679B
0x140076753  sub     edi, 1
0x140076756  jns     short loc_140076710
0x140076758  mov     r12, [rsp+48h+arg_10]
0x14007675d  mov     rsi, [rsp+48h+arg_8]
0x140076762  mov     rbp, [rsp+48h+arg_0]
0x140076767  dec     dword ptr [r15+1Ch]
0x14007676b  add     rsp, 20h
0x14007676f  pop     r15
0x140076771  pop     r14
0x140076773  pop     r13
0x140076775  pop     rdi
0x140076776  pop     rbx
0x140076777  retn
0x140076779  cmp     dl, 2
0x14007677c  jnz     short loc_140076753
0x14007677e  mov     rax, [r8]
0x140076781  mov     rcx, [rax+50h]
0x140076785  test    rcx, rcx
0x140076788  jz      short loc_140076753
0x14007678a  cmp     [rcx+10h], rbx
0x14007678e  jnz     short loc_140076753
0x140076790  mov     [rax+50h], r13
0x140076794  call    HMUnlockObject
0x140076799  jmp     short loc_140076753
0x14007679b  test    byte ptr [rbp+19h], 1
0x14007679f  jnz     short loc_140076753
0x1400767a1  mov     rcx, rbp; struct _HANDLEENTRY *
0x1400767a4  call    ?HMDestroyUnlockedObjectWorker@@YAXPEAU_HANDLEENTRY@@@Z; HMDestroyUnlockedObjectWorker(_HANDLEENTRY *)
0x1400767a9  jmp     short loc_140076753
0x1400767b0  mov     rdx, rax; BugCheckParameter3
0x1400767b3  mov     rcx, rbx; BugCheckParameter2
0x1400767b6  call    ??$Win32HM_UnlockFromThread@$00@@YAPEAU_HEAD@@PEAUtagTHREADINFO@@PEAU_Win32HMThreadLockItem@@@Z; Win32HM_UnlockFromThread<1>(tagTHREADINFO *,_Win32HMThreadLockItem *)
0x1400767bb  mov     rax, [rbx+1C0h]
0x1400767c2  test    rax, rax
0x1400767c5  jz      loc_140076690
0x1400767cb  jmp     short loc_1400767B0
0x1400767cd  mov     rbx, r13
0x1400767d0  jmp     loc_140076678
0x1400767d5  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1400767dc  nop     dword ptr [rax+rax+00h]
0x1400767e1  mov     rcx, [rax+30h]
0x1400767e5  mov     rax, [rcx+0A50h]
0x1400767ec  test    rax, rax
0x1400767ef  jz      short loc_14007682A
0x1400767f1  call    _guard_dispatch_icall
0x1400767f6  test    eax, eax
0x1400767f8  js      short loc_14007682A
0x1400767fa  mov     rdi, [rbx+4A8h]
0x140076801  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140076808  nop     dword ptr [rax+rax+00h]
0x14007680d  mov     rdx, [rax+30h]
0x140076811  mov     rax, [rdx+0A58h]
0x140076818  test    rax, rax
0x14007681b  jz      short loc_14007682A
0x14007681d  mov     edx, 1
0x140076822  mov     rcx, rdi
0x140076825  call    _guard_dispatch_icall
0x14007682a  mov     [rbx+4A8h], r13
0x140076831  jmp     loc_1400766C7
0x140076836  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14007683d  nop     dword ptr [rax+rax+00h]
0x140076842  mov     rcx, [rax+30h]
0x140076846  mov     rax, [rcx+0A60h]
0x14007684d  test    rax, rax
0x140076850  jz      short loc_14007688B
0x140076852  call    _guard_dispatch_icall
0x140076857  test    eax, eax
0x140076859  js      short loc_14007688B
0x14007685b  mov     rdi, [rbx+4B0h]
0x140076862  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140076869  nop     dword ptr [rax+rax+00h]
0x14007686e  mov     r8, [rax+30h]
0x140076872  mov     rax, [r8+0A68h]
0x140076879  test    rax, rax
0x14007687c  jz      short loc_14007688B
0x14007687e  mov     edx, 1
0x140076883  mov     rcx, rdi
0x140076886  call    _guard_dispatch_icall
0x14007688b  mov     [rbx+4B0h], r13
0x140076892  jmp     loc_1400766D4
```
