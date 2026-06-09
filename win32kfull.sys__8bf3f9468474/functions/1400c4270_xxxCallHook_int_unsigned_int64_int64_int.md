# xxxCallHook(int,unsigned __int64,__int64,int)

- ea: `0x1400c4270`
- end: `0x1400c4595`
- name: `?xxxCallHook@@YAHH_K_JH@Z`
- size: `805`
- prototype: `__int64 __fastcall(int, unsigned __int64, __int64, int)`
- caller_count: `36`
- callee_count: `3`
- tags: ``

## callers

- `0x14001070c`
- `0x14001270c`
- `0x140014968`
- `0x140021d30`
- `0x140027d44`
- `0x14002936c`
- `0x14002bca4`
- `0x1400354a0`
- `0x1400c26b0`
- `0x1400c31e0`
- `0x1400c459c`
- `0x1400c591c`
- `0x1400d53f8`
- `0x1400eec14`
- `0x140107aa8`
- `0x1401203e4`
- `0x1401494f4`
- `0x140175fe8`
- `0x140177038`
- `0x140178b7c`
- `0x140188ea0`
- `0x1401bb1f8`
- `0x1401c4bb8`
- `0x1401cdc10`
- `0x1401f45dc`
- `0x1401f4cd0`
- `0x14020f7d8`
- `0x14021e940`
- `0x14021f6f4`
- `0x140222400`
- `0x140232afc`
- `0x1402362d0`
- `0x140236db0`
- `0x140257930`
- `0x14027ad54`
- `0x1402bdb20`

## callees

- `0x1400c4270`
- `0x1400c459c`
- `0x140123e7c`

## import_xrefs

- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1400c42fb`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1400c43ca`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1400c447a`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1400c42fb`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1400c43ca`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1400c447a`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400c42e8`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400c43b7`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400c4467`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400c42e8`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400c43b7`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400c4467`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c42b7`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c42d1`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c4349`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c4389`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c43a0`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c4439`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c4450`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c449c`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c42b7`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c42d1`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c4349`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c4389`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c43a0`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c4439`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c4450`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c449c`
- `WIN32K!W32GetUserSessionState` at `0x1400c428f`
- `WIN32K!W32GetUserSessionState` at `0x1400c42a2`
- `WIN32K!W32GetUserSessionState` at `0x1400c4361`
- `WIN32K!W32GetUserSessionState` at `0x1400c4374`
- `WIN32K!W32GetUserSessionState` at `0x1400c4411`
- `WIN32K!W32GetUserSessionState` at `0x1400c4424`
- `WIN32K!W32GetUserSessionState` at `0x1400c428f`
- `WIN32K!W32GetUserSessionState` at `0x1400c42a2`
- `WIN32K!W32GetUserSessionState` at `0x1400c4361`
- `WIN32K!W32GetUserSessionState` at `0x1400c4374`
- `WIN32K!W32GetUserSessionState` at `0x1400c4411`
- `WIN32K!W32GetUserSessionState` at `0x1400c4424`

## pseudocode

```c
__int64 __fastcall xxxCallHook(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rbx
  unsigned int v7; // r15d
  struct _ERESOURCE *v8; // rdi
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rdi
  struct _ERESOURCE *v23; // rsi
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // rax
  __int64 v33; // rbx
  struct _ERESOURCE *v34; // rdi
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // r8
  __int64 v38; // r9
  __int64 v39; // rcx
  __int64 *v40; // rax

  v4 = (int)a4;
  v7 = a1;
  v8 = *(struct _ERESOURCE **)(W32GetUserSessionState(a1, a2, a3, a4) + 42136);
  if ( !*(_DWORD *)(W32GetUserSessionState(v10, v9, v11, v12) + 19592)
    && (*(_DWORD *)(PsGetCurrentThreadWin32Thread(v13) + 24) & 0xC) != 8
    && ((*(_DWORD *)(PsGetCurrentThreadWin32Thread(v14) + 24) & 0xC) == 0
     || ExIsResourceAcquiredExclusiveLite(v8) != 1 && !ExIsResourceAcquiredSharedLite(v8)) )
  {
    __int2c();
  }
  if ( (_DWORD)v4 == 6 )
    goto LABEL_8;
  if ( (_DWORD)v4 != 4 )
  {
    if ( (_DWORD)v4 == 12 )
    {
      v15 = *(unsigned int *)(a3 + 24);
      goto LABEL_9;
    }
    if ( (_DWORD)v4 != 3 && (_DWORD)v4 != -1 )
    {
      v15 = 0;
      LOWORD(v16) = 0;
LABEL_12:
      if ( (_DWORD)v15 == 528 && (_WORD)v16 == 582 )
        return xxxPointerCallHook(v7, a2, a3, (unsigned int)v4);
      goto LABEL_13;
    }
LABEL_8:
    v15 = *(unsigned int *)(a3 + 8);
LABEL_9:
    v16 = *(_QWORD *)(a3 + 16);
    goto LABEL_10;
  }
  v15 = *(unsigned int *)(a3 + 16);
  v16 = *(_QWORD *)(a3 + 8);
LABEL_10:
  if ( (unsigned int)(v15 - 577) <= 3 )
    return xxxPointerCallHook(v7, a2, a3, (unsigned int)v4);
  if ( (unsigned int)v15 < 0x245 || (unsigned int)v15 > 0x257 || (_DWORD)v15 == 589 )
    goto LABEL_12;
  if ( (_DWORD)v15 != 595 )
    return xxxPointerCallHook(v7, a2, a3, (unsigned int)v4);
LABEL_13:
  CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread(v15);
  if ( CurrentThreadWin32Thread )
    v22 = *CurrentThreadWin32Thread;
  else
    v22 = 0;
  v23 = *(struct _ERESOURCE **)(W32GetUserSessionState(v19, v18, v20, v21) + 42136);
  if ( !*(_DWORD *)(W32GetUserSessionState(v25, v24, v26, v27) + 19592) )
  {
    v29 = *(unsigned int *)(PsGetCurrentThreadWin32Thread(v29) + 24);
    LOBYTE(v29) = v29 & 0xC;
    if ( (_BYTE)v29 != 8 )
    {
      v28 = *(unsigned int *)(PsGetCurrentThreadWin32Thread(v29) + 24);
      if ( (v28 & 0xC) == 0 || ExIsResourceAcquiredExclusiveLite(v23) != 1 && !ExIsResourceAcquiredSharedLite(v23) )
        __int2c();
    }
  }
  v32 = v4;
  v33 = *(_QWORD *)(v22 + 8 * v4 + 960);
  if ( (v33 || (v33 = *(_QWORD *)(*(_QWORD *)(v22 + 496) + 8 * v32 + 48)) != 0) && (*(_DWORD *)(v33 + 64) & 0x80u) != 0 )
  {
    v34 = *(struct _ERESOURCE **)(W32GetUserSessionState(v29, v28, v30, v31) + 42136);
    if ( !*(_DWORD *)(W32GetUserSessionState(v36, v35, v37, v38) + 19592) )
    {
      v39 = *(unsigned int *)(PsGetCurrentThreadWin32Thread(v39) + 24);
      LOBYTE(v39) = v39 & 0xC;
      if ( (_BYTE)v39 != 8
        && ((*(_DWORD *)(PsGetCurrentThreadWin32Thread(v39) + 24) & 0xC) == 0
         || ExIsResourceAcquiredExclusiveLite(v34) != 1 && !ExIsResourceAcquiredSharedLite(v34)) )
      {
        __int2c();
      }
    }
    do
    {
      if ( *(_QWORD *)(v33 + 40) )
      {
        v33 = *(_QWORD *)(v33 + 40);
      }
      else
      {
        if ( (*(_DWORD *)(v33 + 64) & 1) != 0 )
        {
          v33 = 0;
          return xxxCallHook2(v33, v7, a2, a3, 1u);
        }
        v40 = (__int64 *)PsGetCurrentThreadWin32Thread(v39);
        if ( v40 )
          v39 = *v40;
        else
          v39 = 0;
        v33 = *(_QWORD *)(*(_QWORD *)(v39 + 496) + 8LL * *(int *)(v33 + 48) + 48);
        if ( !v33 )
          return xxxCallHook2(v33, v7, a2, a3, 1u);
      }
    }
    while ( (*(_DWORD *)(v33 + 64) & 0x80u) != 0 );
  }
  return xxxCallHook2(v33, v7, a2, a3, 1u);
}

```

## disassembly

```asm
0x1400c4270  mov     [rsp+arg_8], rbx
0x1400c4275  mov     [rsp+arg_10], rbp
0x1400c427a  push    rdi
0x1400c427b  push    r14
0x1400c427d  push    r15
0x1400c427f  sub     rsp, 30h
0x1400c4283  movsxd  rbx, r9d
0x1400c4286  mov     rbp, r8
0x1400c4289  mov     r14, rdx
0x1400c428c  mov     r15d, ecx
0x1400c428f  call    cs:__imp_W32GetUserSessionState
0x1400c4296  nop     dword ptr [rax+rax+00h]
0x1400c429b  mov     rdi, [rax+0A498h]
0x1400c42a2  call    cs:__imp_W32GetUserSessionState
0x1400c42a9  nop     dword ptr [rax+rax+00h]
0x1400c42ae  cmp     dword ptr [rax+4C88h], 0
0x1400c42b5  jnz     short loc_1400C430D
0x1400c42b7  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400c42be  nop     dword ptr [rax+rax+00h]
0x1400c42c3  mov     r9d, [rax+18h]
0x1400c42c7  and     r9b, 0Ch
0x1400c42cb  cmp     r9b, 8
0x1400c42cf  jz      short loc_1400C430D
0x1400c42d1  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400c42d8  nop     dword ptr [rax+rax+00h]
0x1400c42dd  mov     edx, [rax+18h]
0x1400c42e0  test    dl, 0Ch
0x1400c42e3  jz      short loc_1400C430B
0x1400c42e5  mov     rcx, rdi; Resource
0x1400c42e8  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x1400c42ef  nop     dword ptr [rax+rax+00h]
0x1400c42f4  cmp     al, 1
0x1400c42f6  jz      short loc_1400C430D
0x1400c42f8  mov     rcx, rdi; Resource
0x1400c42fb  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x1400c4302  nop     dword ptr [rax+rax+00h]
0x1400c4307  test    eax, eax
0x1400c4309  jnz     short loc_1400C430D
0x1400c430b  int     2Ch; Windows NT - assertion failure
0x1400c430d  cmp     ebx, 6
0x1400c4310  jnz     loc_1400C4503
0x1400c4316  mov     ecx, [rbp+8]
0x1400c4319  mov     rdx, [rbp+10h]
0x1400c431d  lea     eax, [rcx-241h]
0x1400c4323  cmp     eax, 3
0x1400c4326  jbe     loc_1400C4549
0x1400c432c  cmp     ecx, 245h
0x1400c4332  jnb     loc_1400C4525
0x1400c4338  cmp     ecx, 210h
0x1400c433e  jz      loc_1400C4577
0x1400c4344  mov     [rsp+48h+arg_0], rsi
0x1400c4349  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400c4350  nop     dword ptr [rax+rax+00h]
0x1400c4355  test    rax, rax
0x1400c4358  jz      loc_1400C4587
0x1400c435e  mov     rdi, [rax]
0x1400c4361  call    cs:__imp_W32GetUserSessionState
0x1400c4368  nop     dword ptr [rax+rax+00h]
0x1400c436d  mov     rsi, [rax+0A498h]
0x1400c4374  call    cs:__imp_W32GetUserSessionState
0x1400c437b  nop     dword ptr [rax+rax+00h]
0x1400c4380  cmp     dword ptr [rax+4C88h], 0
0x1400c4387  jnz     short loc_1400C43DC
0x1400c4389  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400c4390  nop     dword ptr [rax+rax+00h]
0x1400c4395  mov     ecx, [rax+18h]
0x1400c4398  and     cl, 0Ch
0x1400c439b  cmp     cl, 8
0x1400c439e  jz      short loc_1400C43DC
0x1400c43a0  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400c43a7  nop     dword ptr [rax+rax+00h]
0x1400c43ac  mov     edx, [rax+18h]
0x1400c43af  test    dl, 0Ch
0x1400c43b2  jz      short loc_1400C43DA
0x1400c43b4  mov     rcx, rsi; Resource
0x1400c43b7  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x1400c43be  nop     dword ptr [rax+rax+00h]
0x1400c43c3  cmp     al, 1
0x1400c43c5  jz      short loc_1400C43DC
0x1400c43c7  mov     rcx, rsi; Resource
0x1400c43ca  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x1400c43d1  nop     dword ptr [rax+rax+00h]
0x1400c43d6  test    eax, eax
0x1400c43d8  jnz     short loc_1400C43DC
0x1400c43da  int     2Ch; Windows NT - assertion failure
0x1400c43dc  mov     rsi, [rsp+48h+arg_0]
0x1400c43e1  mov     rax, rbx
0x1400c43e4  mov     rbx, [rdi+rbx*8+3C0h]
0x1400c43ec  test    rbx, rbx
0x1400c43ef  jnz     short loc_1400C4406
0x1400c43f1  mov     rbx, [rdi+1F0h]
0x1400c43f8  mov     rbx, [rbx+rax*8+30h]
0x1400c43fd  test    rbx, rbx
0x1400c4400  jz      loc_1400C44C9
0x1400c4406  mov     eax, [rbx+40h]
0x1400c4409  test    al, al
0x1400c440b  jns     loc_1400C44C9
0x1400c4411  call    cs:__imp_W32GetUserSessionState
0x1400c4418  nop     dword ptr [rax+rax+00h]
0x1400c441d  mov     rdi, [rax+0A498h]
0x1400c4424  call    cs:__imp_W32GetUserSessionState
0x1400c442b  nop     dword ptr [rax+rax+00h]
0x1400c4430  cmp     dword ptr [rax+4C88h], 0
0x1400c4437  jnz     short loc_1400C448C
0x1400c4439  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400c4440  nop     dword ptr [rax+rax+00h]
0x1400c4445  mov     ecx, [rax+18h]
0x1400c4448  and     cl, 0Ch
0x1400c444b  cmp     cl, 8
0x1400c444e  jz      short loc_1400C448C
0x1400c4450  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400c4457  nop     dword ptr [rax+rax+00h]
0x1400c445c  mov     edx, [rax+18h]
0x1400c445f  test    dl, 0Ch
0x1400c4462  jz      short loc_1400C448A
0x1400c4464  mov     rcx, rdi; Resource
0x1400c4467  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x1400c446e  nop     dword ptr [rax+rax+00h]
0x1400c4473  cmp     al, 1
0x1400c4475  jz      short loc_1400C448C
0x1400c4477  mov     rcx, rdi; Resource
0x1400c447a  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x1400c4481  nop     dword ptr [rax+rax+00h]
0x1400c4486  test    eax, eax
0x1400c4488  jnz     short loc_1400C448C
0x1400c448a  int     2Ch; Windows NT - assertion failure
0x1400c448c  mov     rax, [rbx+28h]
0x1400c4490  test    rax, rax
0x1400c4493  jnz     short loc_1400C44F7
0x1400c4495  mov     eax, [rbx+40h]
0x1400c4498  test    al, 1
0x1400c449a  jnz     short loc_1400C4514
0x1400c449c  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400c44a3  nop     dword ptr [rax+rax+00h]
0x1400c44a8  test    rax, rax
0x1400c44ab  jz      loc_1400C458E
0x1400c44b1  mov     rcx, [rax]
0x1400c44b4  movsxd  rax, dword ptr [rbx+30h]
0x1400c44b8  mov     rbx, [rcx+1F0h]
0x1400c44bf  mov     rbx, [rbx+rax*8+30h]
0x1400c44c4  test    rbx, rbx
0x1400c44c7  jnz     short loc_1400C44FA
0x1400c44c9  mov     r9, rbp
0x1400c44cc  mov     [rsp+48h+var_28], 1
0x1400c44d4  mov     r8, r14
0x1400c44d7  mov     edx, r15d
0x1400c44da  mov     rcx, rbx
0x1400c44dd  call    ?xxxCallHook2@@YA_JPEAUtagHOOK@@H_K_JW4CallHookHints@@@Z; xxxCallHook2(tagHOOK *,int,unsigned __int64,__int64,CallHookHints)
0x1400c44e2  mov     rbx, [rsp+48h+arg_8]
0x1400c44e7  mov     rbp, [rsp+48h+arg_10]
0x1400c44ec  add     rsp, 30h
0x1400c44f0  pop     r15
0x1400c44f2  pop     r14
0x1400c44f4  pop     rdi
0x1400c44f5  retn
0x1400c44f7  mov     rbx, rax
0x1400c44fa  mov     eax, [rbx+40h]
0x1400c44fd  test    al, al
0x1400c44ff  jns     short loc_1400C44C9
0x1400c4501  jmp     short loc_1400C448C
0x1400c4503  cmp     ebx, 4
0x1400c4506  jnz     short loc_1400C4518
0x1400c4508  mov     ecx, [rbp+10h]
0x1400c450b  mov     rdx, [rbp+8]
0x1400c450f  jmp     loc_1400C431D
0x1400c4514  xor     ebx, ebx
0x1400c4516  jmp     short loc_1400C44C9
0x1400c4518  cmp     ebx, 0Ch
0x1400c451b  jnz     short loc_1400C455C
0x1400c451d  mov     ecx, [rbp+18h]
0x1400c4520  jmp     loc_1400C4319
0x1400c4525  cmp     ecx, 257h
0x1400c452b  ja      loc_1400C4338
0x1400c4531  cmp     ecx, 24Dh
0x1400c4537  jz      loc_1400C4338
0x1400c453d  cmp     ecx, 253h
0x1400c4543  jz      loc_1400C4344
0x1400c4549  mov     r9d, ebx
0x1400c454c  mov     r8, rbp
0x1400c454f  mov     rdx, r14
0x1400c4552  mov     ecx, r15d
0x1400c4555  call    xxxPointerCallHook
0x1400c455a  jmp     short loc_1400C44E2
0x1400c455c  cmp     ebx, 3
0x1400c455f  jz      loc_1400C4316
0x1400c4565  cmp     ebx, 0FFFFFFFFh
0x1400c4568  jz      loc_1400C4316
0x1400c456e  xor     ecx, ecx
0x1400c4570  xor     edx, edx
0x1400c4572  jmp     loc_1400C4338
0x1400c4577  mov     eax, 246h
0x1400c457c  cmp     dx, ax
0x1400c457f  jnz     loc_1400C4344
0x1400c4585  jmp     short loc_1400C4549
0x1400c4587  xor     edi, edi
0x1400c4589  jmp     loc_1400C4361
0x1400c458e  xor     ecx, ecx
0x1400c4590  jmp     loc_1400C44B4
```
