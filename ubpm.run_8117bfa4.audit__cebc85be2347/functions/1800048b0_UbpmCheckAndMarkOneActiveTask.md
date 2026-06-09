# UbpmCheckAndMarkOneActiveTask

- ea: `0x1800048b0`
- end: `0x180004c1e`
- name: `UbpmCheckAndMarkOneActiveTask`
- size: `878`
- prototype: `__int64 __fastcall(UUID *Uuid2)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x18000f880`

## callees

- `0x1800048b0`
- `0x180004c30`
- `0x18000fbf0`
- `0x1800150c0`
- `0x1800351ec`
- `0x18003f758`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x180004918`
- `ntdll!RtlReleaseSRWLockShared` at `0x180004992`
- `ntdll!RtlReleaseSRWLockShared` at `0x180004b0e`
- `ntdll!RtlReleaseSRWLockShared` at `0x180004918`
- `ntdll!RtlReleaseSRWLockShared` at `0x180004992`
- `ntdll!RtlReleaseSRWLockShared` at `0x180004b0e`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800048de`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800048de`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800049be`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800049be`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004a16`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004a89`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004ab3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004b7c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004bdb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004a16`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004a89`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004ab3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004b7c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004bdb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800049ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800049ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b3b`
- `RPCRT4!UuidEqual` at `0x1800049fa`
- `RPCRT4!UuidEqual` at `0x180004a4e`
- `RPCRT4!UuidEqual` at `0x1800049fa`
- `RPCRT4!UuidEqual` at `0x180004a4e`

## pseudocode

```c
__int64 __fastcall UbpmCheckAndMarkOneActiveTask(UUID *Uuid2)
{
  UUID *v1; // rdi
  unsigned int v2; // ebx
  _QWORD *v3; // r12
  unsigned __int8 v4; // bp
  _UNKNOWN **v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  volatile signed __int64 *v10; // rdx
  int v11; // r8d
  unsigned int i; // ebp
  __int64 v13; // r15
  char v14; // al
  int v15; // eax
  __int64 v16; // rcx
  __int64 *j; // rdi
  __int64 v18; // r8
  unsigned int k; // edi
  DWORD LastError; // eax
  RPC_STATUS Status; // [rsp+78h] [rbp+10h] BYREF

  v1 = Uuid2;
  Status = 0;
  v2 = 0;
  v3 = 0;
  v4 = 0;
  RtlAcquireSRWLockShared(&g_TaskHostContextListLock);
  v5 = (_UNKNOWN **)g_leTaskHostContextListHead;
  if ( g_leTaskHostContextListHead == (_UNKNOWN *)&g_leTaskHostContextListHead )
    goto LABEL_4;
  do
  {
    v5 = (_UNKNOWN **)*v5;
    ++v2;
  }
  while ( v5 != &g_leTaskHostContextListHead );
  if ( !v2 )
    goto LABEL_4;
  v3 = UbpmAlloc(8 * v2);
  if ( !v3 )
  {
    RtlReleaseSRWLockShared(&g_TaskHostContextListLock);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, LastError);
    }
    return v4;
  }
  v10 = (volatile signed __int64 *)g_leTaskHostContextListHead;
  v11 = 0;
  if ( g_leTaskHostContextListHead == (_UNKNOWN *)&g_leTaskHostContextListHead )
  {
LABEL_4:
    RtlReleaseSRWLockShared(&g_TaskHostContextListLock);
    if ( !v2 )
      goto LABEL_5;
  }
  else
  {
    do
    {
      v3[v11] = v10 - 1;
      _InterlockedIncrement64(v10 + 11);
      v10 = (volatile signed __int64 *)*v10;
      ++v11;
    }
    while ( v10 != (volatile signed __int64 *)&g_leTaskHostContextListHead );
    RtlReleaseSRWLockShared(&g_TaskHostContextListLock);
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= v2 )
    {
      v4 = 0;
      goto LABEL_5;
    }
    v13 = v3[i];
    RtlAcquireSRWLockExclusive(v13 + 64);
    *(_DWORD *)(v13 + 72) = GetCurrentThreadId();
    v14 = *(_BYTE *)(v13 + 104);
    if ( (v14 & 4) != 0 )
    {
      *(_DWORD *)(v13 + 72) = 0;
      RtlReleaseSRWLockExclusive(v13 + 64);
      continue;
    }
    if ( (v14 & 0x10) != 0 )
      break;
    v15 = UuidEqual((UUID *)(v13 + 280), v1, &Status);
    v16 = v13 + 64;
    if ( v15 )
    {
      *(_WORD *)(v13 + 276) = 1;
      v4 = 1;
      *(_DWORD *)(v13 + 72) = 0;
      RtlReleaseSRWLockExclusive(v16);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        WPP_SF_qdi(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, v7, v13, *(_DWORD *)(v13 + 32), *(_QWORD *)(v13 + 304));
      goto LABEL_5;
    }
    *(_DWORD *)(v13 + 72) = 0;
    RtlReleaseSRWLockExclusive(v16);
LABEL_17:
    ;
  }
  for ( j = *(__int64 **)(v13 + 200); ; j = (__int64 *)*j )
  {
    if ( j == (__int64 *)(v13 + 200) )
    {
      *(_DWORD *)(v13 + 72) = 0;
      RtlReleaseSRWLockExclusive(v13 + 64);
      v1 = Uuid2;
      goto LABEL_17;
    }
    if ( (j[11] & 1) == 0 && UuidEqual((UUID *)((char *)j + 92), Uuid2, &Status) )
      break;
  }
  *((_WORD *)j + 45) = 1;
  v4 = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_qdi(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, v18, j - 2, *(_DWORD *)(v13 + 32), j[14]);
  *(_DWORD *)(v13 + 72) = 0;
  RtlReleaseSRWLockExclusive(v13 + 64);
LABEL_5:
  if ( v3 )
  {
    for ( k = 0; k < v2; ++k )
      UbpmpDecrementRefAndDelete(&v3[k], 1, v7, v8);
    UBPM_MIDL_user_free(v3, v6, v7, v8);
  }
  return v4;
}

```

## disassembly

```asm
0x1800048b0  mov     [rsp+Uuid2], rcx
0x1800048b5  push    rbx
0x1800048b6  push    rbp
0x1800048b7  push    rsi
0x1800048b8  push    rdi
0x1800048b9  push    r12
0x1800048bb  push    r14
0x1800048bd  push    r15
0x1800048bf  sub     rsp, 30h
0x1800048c3  xor     r14d, r14d
0x1800048c6  mov     rdi, rcx
0x1800048c9  lea     rcx, g_TaskHostContextListLock
0x1800048d0  mov     [rsp+68h+Status], r14d
0x1800048d5  mov     ebx, r14d
0x1800048d8  mov     r12d, r14d
0x1800048db  xor     bpl, bpl
0x1800048de  call    cs:__imp_RtlAcquireSRWLockShared
0x1800048e5  nop     dword ptr [rax+rax+00h]
0x1800048ea  mov     rax, cs:g_leTaskHostContextListHead
0x1800048f1  lea     rsi, g_leTaskHostContextListHead
0x1800048f8  mov     r15d, 1
0x1800048fe  cmp     rax, rsi
0x180004901  jz      short loc_180004911
0x180004903  mov     rax, [rax]
0x180004906  inc     ebx
0x180004908  cmp     rax, rsi
0x18000490b  jnz     short loc_180004903
0x18000490d  test    ebx, ebx
0x18000490f  jnz     short loc_180004945
0x180004911  lea     rcx, g_TaskHostContextListLock
0x180004918  call    cs:__imp_RtlReleaseSRWLockShared
0x18000491f  nop     dword ptr [rax+rax+00h]
0x180004924  test    ebx, ebx
0x180004926  jnz     short loc_18000499E
0x180004928  test    r12, r12
0x18000492b  jnz     loc_180004AC9
0x180004931  movzx   eax, bpl
0x180004935  add     rsp, 30h
0x180004939  pop     r15
0x18000493b  pop     r14
0x18000493d  pop     r12
0x18000493f  pop     rdi
0x180004940  pop     rsi
0x180004941  pop     rbp
0x180004942  pop     rbx
0x180004943  retn
0x180004945  lea     ecx, ds:0[rbx*8]; Size
0x18000494c  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x180004951  mov     r12, rax
0x180004954  test    rax, rax
0x180004957  jz      loc_180004B07
0x18000495d  mov     rdx, cs:g_leTaskHostContextListHead
0x180004964  mov     r8d, r14d
0x180004967  cmp     rdx, rsi
0x18000496a  jz      short loc_180004911
0x18000496c  nop     dword ptr [rax+00h]
0x180004970  mov     eax, r8d
0x180004973  lea     rcx, [rdx-8]
0x180004977  mov     [r12+rax*8], rcx
0x18000497b  lock inc qword ptr [rcx+60h]
0x180004980  mov     rdx, [rdx]
0x180004983  inc     r8d
0x180004986  cmp     rdx, rsi
0x180004989  jnz     short loc_180004970
0x18000498b  lea     rcx, g_TaskHostContextListLock
0x180004992  call    cs:__imp_RtlReleaseSRWLockShared
0x180004999  nop     dword ptr [rax+rax+00h]
0x18000499e  mov     ebp, r14d
0x1800049a1  mov     [rsp+68h+arg_10], r13
0x1800049a9  mov     rcx, r12
0x1800049ac  cmp     ebp, ebx
0x1800049ae  jnb     loc_180004AF1
0x1800049b4  mov     eax, ebp
0x1800049b6  mov     r15, [rcx+rax*8]
0x1800049ba  lea     rcx, [r15+40h]
0x1800049be  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800049c5  nop     dword ptr [rax+rax+00h]
0x1800049ca  call    cs:__imp_GetCurrentThreadId
0x1800049d1  nop     dword ptr [rax+rax+00h]
0x1800049d6  mov     [r15+48h], eax
0x1800049da  movzx   eax, byte ptr [r15+68h]
0x1800049df  test    al, 4
0x1800049e1  jnz     loc_180004BD3
0x1800049e7  test    al, 10h
0x1800049e9  jnz     short loc_180004A26
0x1800049eb  lea     rcx, [r15+118h]; Uuid1
0x1800049f2  mov     rdx, rdi; Uuid2
0x1800049f5  lea     r8, [rsp+68h+Status]; Status
0x1800049fa  call    cs:__imp_UuidEqual
0x180004a01  nop     dword ptr [rax+rax+00h]
0x180004a06  lea     rcx, [r15+40h]
0x180004a0a  test    eax, eax
0x180004a0c  jnz     loc_180004B6B
0x180004a12  mov     [r15+48h], r14d
0x180004a16  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180004a1d  nop     dword ptr [rax+rax+00h]
0x180004a22  inc     ebp
0x180004a24  jmp     short loc_1800049A9
0x180004a26  lea     r14, [r15+0C8h]
0x180004a2d  mov     rdi, [r14]
0x180004a30  cmp     rdi, r14
0x180004a33  jz      short loc_180004AA8
0x180004a35  test    byte ptr [rdi+58h], 1
0x180004a39  jz      short loc_180004A40
0x180004a3b  mov     rdi, [rdi]
0x180004a3e  jmp     short loc_180004A30
0x180004a40  mov     rdx, [rsp+68h+Uuid2]; Uuid2
0x180004a45  lea     rcx, [rdi+5Ch]; Uuid1
0x180004a49  lea     r8, [rsp+68h+Status]; Status
0x180004a4e  call    cs:__imp_UuidEqual
0x180004a55  nop     dword ptr [rax+rax+00h]
0x180004a5a  test    eax, eax
0x180004a5c  jz      short loc_180004A3B
0x180004a5e  mov     word ptr [rdi+5Ah], 1
0x180004a64  mov     bpl, 1
0x180004a67  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a6e  lea     rax, WPP_GLOBAL_Control
0x180004a75  cmp     rcx, rax
0x180004a78  jnz     loc_180004BEC
0x180004a7e  xor     r14d, r14d
0x180004a81  lea     rcx, [r15+40h]
0x180004a85  mov     [r15+48h], r14d
0x180004a89  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180004a90  nop     dword ptr [rax+rax+00h]
0x180004a95  mov     r13, [rsp+68h+arg_10]
0x180004a9d  mov     r15d, 1
0x180004aa3  jmp     loc_180004928
0x180004aa8  xor     r14d, r14d
0x180004aab  lea     rcx, [r15+40h]
0x180004aaf  mov     [r15+48h], r14d
0x180004ab3  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180004aba  nop     dword ptr [rax+rax+00h]
0x180004abf  mov     rdi, [rsp+68h+Uuid2]
0x180004ac4  jmp     loc_180004A22
0x180004ac9  mov     edi, r14d
0x180004acc  test    ebx, ebx
0x180004ace  jz      short loc_180004AE4
0x180004ad0  mov     eax, edi
0x180004ad2  mov     edx, r15d
0x180004ad5  lea     rcx, [r12+rax*8]
0x180004ad9  call    UbpmpDecrementRefAndDelete
0x180004ade  inc     edi
0x180004ae0  cmp     edi, ebx
0x180004ae2  jb      short loc_180004AD0
0x180004ae4  mov     rcx, r12
0x180004ae7  call    UBPM_MIDL_user_free
0x180004aec  jmp     loc_180004931
0x180004af1  xor     bpl, bpl
0x180004af4  mov     r13, [rsp+68h+arg_10]
0x180004afc  mov     r15d, 1
0x180004b02  jmp     loc_180004928
0x180004b07  lea     rcx, g_TaskHostContextListLock
0x180004b0e  call    cs:__imp_RtlReleaseSRWLockShared
0x180004b15  nop     dword ptr [rax+rax+00h]
0x180004b1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004b21  lea     rax, WPP_GLOBAL_Control
0x180004b28  cmp     rcx, rax
0x180004b2b  jz      loc_180004931
0x180004b31  test    [rcx+1Ch], r15b
0x180004b35  jz      loc_180004931
0x180004b3b  call    cs:__imp_GetLastError
0x180004b42  nop     dword ptr [rax+rax+00h]
0x180004b47  mov     rcx, cs:WPP_GLOBAL_Control
0x180004b4e  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x180004b55  mov     edx, 33h ; '3'
0x180004b5a  mov     r9d, eax
0x180004b5d  mov     rcx, [rcx+10h]
0x180004b61  call    WPP_SF_d
0x180004b66  jmp     loc_180004931
0x180004b6b  mov     word ptr [r15+114h], 1
0x180004b75  mov     bpl, 1
0x180004b78  mov     [r15+48h], r14d
0x180004b7c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180004b83  nop     dword ptr [rax+rax+00h]
0x180004b88  mov     rcx, cs:WPP_GLOBAL_Control
0x180004b8f  lea     rax, WPP_GLOBAL_Control
0x180004b96  cmp     rcx, rax
0x180004b99  jz      loc_180004AF4
0x180004b9f  test    byte ptr [rcx+1Ch], 80h
0x180004ba3  jz      loc_180004AF4
0x180004ba9  mov     rax, [r15+130h]
0x180004bb0  mov     edx, 34h ; '4'
0x180004bb5  mov     rcx, [rcx+10h]
0x180004bb9  mov     r9, r15
0x180004bbc  mov     [rsp+68h+var_40], rax
0x180004bc1  mov     eax, [r15+20h]
0x180004bc5  mov     [rsp+68h+var_48], eax
0x180004bc9  call    WPP_SF_qdi
0x180004bce  jmp     loc_180004AF4
0x180004bd3  lea     rcx, [r15+40h]
0x180004bd7  mov     [r15+48h], r14d
0x180004bdb  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180004be2  nop     dword ptr [rax+rax+00h]
0x180004be7  jmp     loc_180004A22
0x180004bec  test    byte ptr [rcx+1Ch], 80h
0x180004bf0  jz      loc_180004A7E
0x180004bf6  mov     rax, [rdi+70h]
0x180004bfa  lea     r9, [rdi-10h]
0x180004bfe  mov     rcx, [rcx+10h]
0x180004c02  mov     edx, 35h ; '5'
0x180004c07  mov     [rsp+68h+var_40], rax
0x180004c0c  mov     eax, [r15+20h]
0x180004c10  mov     [rsp+68h+var_48], eax
0x180004c14  call    WPP_SF_qdi
0x180004c19  jmp     loc_180004A7E
```
