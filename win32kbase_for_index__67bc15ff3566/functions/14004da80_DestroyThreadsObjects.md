# DestroyThreadsObjects

- ea: `0x14004da80`
- end: `0x14004dcc7`
- name: `DestroyThreadsObjects`
- size: `583`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400d98bc`

## callees

- `0x14004c020`
- `0x14004da80`
- `0x14004dcd0`
- `0x14006b2d0`
- `0x14006b610`
- `0x140124424`
- `0x1401b7908`
- `0x1402389c0`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14004da8d`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14004dad8`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14004da8d`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14004dad8`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14004dc05`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14004dc31`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14004dc66`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14004dc92`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14004dc05`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14004dc31`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14004dc66`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14004dc92`
- `WIN32K!W32GetUserSessionState` at `0x14004db04`
- `WIN32K!W32GetUserSessionState` at `0x14004db13`
- `WIN32K!W32GetUserSessionState` at `0x14004db4f`
- `WIN32K!W32GetUserSessionState` at `0x14004db04`
- `WIN32K!W32GetUserSessionState` at `0x14004db13`
- `WIN32K!W32GetUserSessionState` at `0x14004db4f`

## pseudocode

```c
void __fastcall DestroyThreadsObjects(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  _QWORD **CurrentThreadWin32Thread; // rax
  _QWORD *v5; // rbx
  ULONG_PTR i; // rax
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r15
  __int64 UserSessionState; // r14
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // rcx
  unsigned int j; // edi
  _QWORD *v23; // r8
  __int64 v24; // rbp
  __int64 v25; // rax
  int (*v26)(void); // rax
  __int64 v27; // rdi
  void (__fastcall *v28)(__int64, __int64); // rax
  int (*v29)(void); // rax
  __int64 v30; // rdi
  void (__fastcall *v31)(__int64, __int64); // rax

  CurrentThreadWin32Thread = (_QWORD **)PsGetCurrentThreadWin32Thread(a1, a2, a3, a4);
  if ( CurrentThreadWin32Thread )
    v5 = *CurrentThreadWin32Thread;
  else
    v5 = 0;
  DestroyCacheDCEntries(v5);
  for ( i = v5[56]; i; i = v5[56] )
    Win32HM_UnlockFromThread<1>((ULONG_PTR)v5, i);
  while ( 1 )
  {
    v7 = v5[47];
    if ( !v7 )
      break;
    PopAndFreeW32ThreadLock(v7);
  }
  AtomicExecutionCheck::EnforceConsistency(0);
  v15 = PsGetCurrentThreadWin32Thread(v9, v8, v10, v11);
  ++*(_DWORD *)(v15 + 28);
  if ( v5[149] )
  {
    v13 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v13, v12) + 48);
    v26 = *(int (**)(void))(v13 + 2640);
    if ( v26 )
    {
      if ( v26() >= 0 )
      {
        v27 = v5[149];
        v12 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v13, v12) + 48);
        v28 = *(void (__fastcall **)(__int64, __int64))(v12 + 2648);
        if ( v28 )
          v28(v27, 1);
      }
    }
    v5[149] = 0;
  }
  if ( v5[150] )
  {
    v13 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v13, v12) + 48);
    v29 = *(int (**)(void))(v13 + 2656);
    if ( v29 )
    {
      if ( v29() >= 0 )
      {
        v30 = v5[150];
        v14 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v13, v12) + 48);
        v31 = *(void (__fastcall **)(__int64, __int64))(v14 + 2664);
        if ( v31 )
          v31(v30, 1);
      }
    }
    v5[150] = 0;
  }
  UserSessionState = W32GetUserSessionState(v13, v12, v14);
  for ( j = *(_DWORD *)(W32GetUserSessionState(v18, v17, v19) + 19648); (j & 0x80000000) == 0; --j )
  {
    v24 = *(_QWORD *)(UserSessionState + 19720) + 32LL * j;
    v25 = W32GetUserSessionState(v21, v20, v23);
    v20 = *(unsigned __int8 *)(v24 + 24);
    if ( (_BYTE)v20 )
    {
      v21 = 5LL * j;
      v23 = (_QWORD *)(*(_QWORD *)(v25 + 19664) + 40LL * j);
      if ( (dword_14023C27C[6 * v20] & 2) != 0 )
      {
        if ( (_BYTE)v20 == 2 )
        {
          v21 = *(_QWORD *)(*v23 + 80LL);
          if ( v21 )
          {
            if ( *(_QWORD **)(v21 + 16) == v5 )
            {
              *(_QWORD *)(*v23 + 80LL) = 0;
              HMUnlockObject(v21);
            }
          }
        }
      }
      else if ( (_QWORD *)v23[1] == v5 && (*(_BYTE *)(v24 + 25) & 1) == 0 )
      {
        HMDestroyUnlockedObjectWorker((struct _HANDLEENTRY *)v24, v20, (__int64)v23);
      }
    }
  }
  --*(_DWORD *)(v15 + 28);
}

```

## disassembly

```asm
0x14004da80  push    rbx
0x14004da82  push    rdi
0x14004da83  push    r13
0x14004da85  push    r14
0x14004da87  push    r15
0x14004da89  sub     rsp, 20h
0x14004da8d  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14004da94  nop     dword ptr [rax+rax+00h]
0x14004da99  xor     r13d, r13d
0x14004da9c  test    rax, rax
0x14004da9f  jz      loc_14004DBFD
0x14004daa5  mov     rbx, [rax]
0x14004daa8  mov     rcx, rbx
0x14004daab  call    DestroyCacheDCEntries
0x14004dab0  mov     rax, [rbx+1C0h]
0x14004dab7  test    rax, rax
0x14004daba  jnz     loc_14004DBE0
0x14004dac0  mov     rcx, [rbx+178h]; this
0x14004dac7  test    rcx, rcx
0x14004daca  jz      short loc_14004DAD3
0x14004dacc  call    PopAndFreeW32ThreadLock
0x14004dad1  jmp     short loc_14004DAC0
0x14004dad3  call    ?EnforceConsistency@AtomicExecutionCheck@@AEAAXXZ; AtomicExecutionCheck::EnforceConsistency(void)
0x14004dad8  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14004dadf  nop     dword ptr [rax+rax+00h]
0x14004dae4  mov     r15, rax
0x14004dae7  inc     dword ptr [rax+1Ch]
0x14004daea  cmp     [rbx+4A8h], r13
0x14004daf1  jnz     loc_14004DC05
0x14004daf7  cmp     [rbx+4B0h], r13
0x14004dafe  jnz     loc_14004DC66
0x14004db04  call    cs:__imp_W32GetUserSessionState
0x14004db0b  nop     dword ptr [rax+rax+00h]
0x14004db10  mov     r14, rax
0x14004db13  call    cs:__imp_W32GetUserSessionState
0x14004db1a  nop     dword ptr [rax+rax+00h]
0x14004db1f  mov     edi, [rax+4CC0h]
0x14004db25  test    edi, edi
0x14004db27  js      short loc_14004DB97
0x14004db29  mov     [rsp+48h+arg_0], rbp
0x14004db2e  mov     [rsp+48h+arg_8], rsi
0x14004db33  mov     [rsp+48h+arg_10], r12
0x14004db38  lea     r12, dword_14023C27C
0x14004db3f  nop
0x14004db40  mov     ebp, edi
0x14004db42  shl     rbp, 5
0x14004db46  add     rbp, [r14+4D08h]
0x14004db4d  mov     esi, edi
0x14004db4f  call    cs:__imp_W32GetUserSessionState
0x14004db56  nop     dword ptr [rax+rax+00h]
0x14004db5b  movzx   edx, byte ptr [rbp+18h]
0x14004db5f  test    dl, dl
0x14004db61  jz      short loc_14004DB83
0x14004db63  mov     rax, [rax+4CD0h]
0x14004db6a  lea     rcx, [rsi+rsi*4]
0x14004db6e  lea     r8, [rax+rcx*8]
0x14004db72  lea     rax, [rdx+rdx*2]
0x14004db76  test    byte ptr [r12+rax*8], 2
0x14004db7b  jnz     short loc_14004DBA9
0x14004db7d  cmp     [r8+8], rbx
0x14004db81  jz      short loc_14004DBCB
0x14004db83  sub     edi, 1
0x14004db86  jns     short loc_14004DB40
0x14004db88  mov     r12, [rsp+48h+arg_10]
0x14004db8d  mov     rsi, [rsp+48h+arg_8]
0x14004db92  mov     rbp, [rsp+48h+arg_0]
0x14004db97  dec     dword ptr [r15+1Ch]
0x14004db9b  add     rsp, 20h
0x14004db9f  pop     r15
0x14004dba1  pop     r14
0x14004dba3  pop     r13
0x14004dba5  pop     rdi
0x14004dba6  pop     rbx
0x14004dba7  retn
0x14004dba9  cmp     dl, 2
0x14004dbac  jnz     short loc_14004DB83
0x14004dbae  mov     rax, [r8]
0x14004dbb1  mov     rcx, [rax+50h]
0x14004dbb5  test    rcx, rcx
0x14004dbb8  jz      short loc_14004DB83
0x14004dbba  cmp     [rcx+10h], rbx
0x14004dbbe  jnz     short loc_14004DB83
0x14004dbc0  mov     [rax+50h], r13
0x14004dbc4  call    HMUnlockObject
0x14004dbc9  jmp     short loc_14004DB83
0x14004dbcb  test    byte ptr [rbp+19h], 1
0x14004dbcf  jnz     short loc_14004DB83
0x14004dbd1  mov     rcx, rbp; struct _HANDLEENTRY *
0x14004dbd4  call    ?HMDestroyUnlockedObjectWorker@@YAXPEAU_HANDLEENTRY@@@Z; HMDestroyUnlockedObjectWorker(_HANDLEENTRY *)
0x14004dbd9  jmp     short loc_14004DB83
0x14004dbe0  mov     rdx, rax; BugCheckParameter3
0x14004dbe3  mov     rcx, rbx; BugCheckParameter2
0x14004dbe6  call    ??$Win32HM_UnlockFromThread@$00@@YAPEAU_HEAD@@PEAUtagTHREADINFO@@PEAU_Win32HMThreadLockItem@@@Z; Win32HM_UnlockFromThread<1>(tagTHREADINFO *,_Win32HMThreadLockItem *)
0x14004dbeb  mov     rax, [rbx+1C0h]
0x14004dbf2  test    rax, rax
0x14004dbf5  jz      loc_14004DAC0
0x14004dbfb  jmp     short loc_14004DBE0
0x14004dbfd  mov     rbx, r13
0x14004dc00  jmp     loc_14004DAA8
0x14004dc05  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14004dc0c  nop     dword ptr [rax+rax+00h]
0x14004dc11  mov     rcx, [rax+30h]
0x14004dc15  mov     rax, [rcx+0A50h]
0x14004dc1c  test    rax, rax
0x14004dc1f  jz      short loc_14004DC5A
0x14004dc21  call    _guard_dispatch_icall
0x14004dc26  test    eax, eax
0x14004dc28  js      short loc_14004DC5A
0x14004dc2a  mov     rdi, [rbx+4A8h]
0x14004dc31  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14004dc38  nop     dword ptr [rax+rax+00h]
0x14004dc3d  mov     rdx, [rax+30h]
0x14004dc41  mov     rax, [rdx+0A58h]
0x14004dc48  test    rax, rax
0x14004dc4b  jz      short loc_14004DC5A
0x14004dc4d  mov     edx, 1
0x14004dc52  mov     rcx, rdi
0x14004dc55  call    _guard_dispatch_icall
0x14004dc5a  mov     [rbx+4A8h], r13
0x14004dc61  jmp     loc_14004DAF7
0x14004dc66  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14004dc6d  nop     dword ptr [rax+rax+00h]
0x14004dc72  mov     rcx, [rax+30h]
0x14004dc76  mov     rax, [rcx+0A60h]
0x14004dc7d  test    rax, rax
0x14004dc80  jz      short loc_14004DCBB
0x14004dc82  call    _guard_dispatch_icall
0x14004dc87  test    eax, eax
0x14004dc89  js      short loc_14004DCBB
0x14004dc8b  mov     rdi, [rbx+4B0h]
0x14004dc92  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14004dc99  nop     dword ptr [rax+rax+00h]
0x14004dc9e  mov     r8, [rax+30h]
0x14004dca2  mov     rax, [r8+0A68h]
0x14004dca9  test    rax, rax
0x14004dcac  jz      short loc_14004DCBB
0x14004dcae  mov     edx, 1
0x14004dcb3  mov     rcx, rdi
0x14004dcb6  call    _guard_dispatch_icall
0x14004dcbb  mov     [rbx+4B0h], r13
0x14004dcc2  jmp     loc_14004DB04
```
