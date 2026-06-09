# UbpmCheckAndMarkOneActiveTask

- ea: `0x180009c20`
- end: `0x180009f46`
- name: `UbpmCheckAndMarkOneActiveTask`
- size: `806`
- prototype: `__int64 __fastcall(UUID *Uuid2)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x180019a30`

## callees

- `0x180009750`
- `0x180009c20`
- `0x18000f9a0`
- `0x180019d90`
- `0x180032e38`
- `0x18003cd4c`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x180009c85`
- `ntdll!RtlReleaseSRWLockShared` at `0x180009d02`
- `ntdll!RtlReleaseSRWLockShared` at `0x180009e4e`
- `ntdll!RtlReleaseSRWLockShared` at `0x180009c85`
- `ntdll!RtlReleaseSRWLockShared` at `0x180009d02`
- `ntdll!RtlReleaseSRWLockShared` at `0x180009e4e`
- `ntdll!RtlAcquireSRWLockShared` at `0x180009c4e`
- `ntdll!RtlAcquireSRWLockShared` at `0x180009c4e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009d28`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009d28`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009d6e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009dd5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009df9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009eb0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009f09`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009d6e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009dd5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009df9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009eb0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009f09`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009d2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009d2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e75`
- `RPCRT4!UuidEqual` at `0x180009d58`
- `RPCRT4!UuidEqual` at `0x180009da0`
- `RPCRT4!UuidEqual` at `0x180009d58`
- `RPCRT4!UuidEqual` at `0x180009da0`

## pseudocode

```c
__int64 __fastcall UbpmCheckAndMarkOneActiveTask(UUID *Uuid2)
{
  UUID *v1; // rdi
  unsigned int v2; // ebx
  _QWORD *v3; // r12
  unsigned __int8 v4; // bp
  _UNKNOWN **v5; // rax
  volatile signed __int64 *v7; // rdx
  int v8; // r8d
  unsigned int i; // ebp
  __int64 v10; // r15
  char v11; // al
  int v12; // eax
  __int64 v13; // rcx
  __int64 *j; // rdi
  __int64 v15; // r8
  unsigned int k; // edi
  DWORD LastError; // eax
  __int64 v18; // r8
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
  v7 = (volatile signed __int64 *)g_leTaskHostContextListHead;
  v8 = 0;
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
      v3[v8] = v7 - 1;
      _InterlockedIncrement64(v7 + 11);
      v7 = (volatile signed __int64 *)*v7;
      ++v8;
    }
    while ( v7 != (volatile signed __int64 *)&g_leTaskHostContextListHead );
    RtlReleaseSRWLockShared(&g_TaskHostContextListLock);
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= v2 )
    {
      v4 = 0;
      goto LABEL_5;
    }
    v10 = v3[i];
    RtlAcquireSRWLockExclusive(v10 + 64);
    *(_DWORD *)(v10 + 72) = GetCurrentThreadId();
    v11 = *(_BYTE *)(v10 + 104);
    if ( (v11 & 4) != 0 )
    {
      *(_DWORD *)(v10 + 72) = 0;
      RtlReleaseSRWLockExclusive(v10 + 64);
      continue;
    }
    if ( (v11 & 0x10) != 0 )
      break;
    v12 = UuidEqual((UUID *)(v10 + 280), v1, &Status);
    v13 = v10 + 64;
    if ( v12 )
    {
      *(_WORD *)(v10 + 276) = 1;
      v4 = 1;
      *(_DWORD *)(v10 + 72) = 0;
      RtlReleaseSRWLockExclusive(v13);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        WPP_SF_qdi(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, v18, v10, *(_DWORD *)(v10 + 32), *(_QWORD *)(v10 + 304));
      goto LABEL_5;
    }
    *(_DWORD *)(v10 + 72) = 0;
    RtlReleaseSRWLockExclusive(v13);
LABEL_17:
    ;
  }
  for ( j = *(__int64 **)(v10 + 200); ; j = (__int64 *)*j )
  {
    if ( j == (__int64 *)(v10 + 200) )
    {
      *(_DWORD *)(v10 + 72) = 0;
      RtlReleaseSRWLockExclusive(v10 + 64);
      v1 = Uuid2;
      goto LABEL_17;
    }
    if ( (j[11] & 1) == 0 && UuidEqual((UUID *)((char *)j + 92), Uuid2, &Status) )
      break;
  }
  *((_WORD *)j + 45) = 1;
  v4 = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_qdi(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, v15, j - 2, *(_DWORD *)(v10 + 32), j[14]);
  *(_DWORD *)(v10 + 72) = 0;
  RtlReleaseSRWLockExclusive(v10 + 64);
LABEL_5:
  if ( v3 )
  {
    for ( k = 0; k < v2; ++k )
      UbpmpDecrementRefAndDelete(&v3[k], 1);
    UBPM_MIDL_user_free(v3);
  }
  return v4;
}

```

## disassembly

```asm
0x180009c20  mov     [rsp+Uuid2], rcx
0x180009c25  push    rbx
0x180009c26  push    rbp
0x180009c27  push    rsi
0x180009c28  push    rdi
0x180009c29  push    r12
0x180009c2b  push    r14
0x180009c2d  push    r15
0x180009c2f  sub     rsp, 30h
0x180009c33  xor     r14d, r14d
0x180009c36  mov     rdi, rcx
0x180009c39  lea     rcx, g_TaskHostContextListLock
0x180009c40  mov     [rsp+68h+Status], r14d
0x180009c45  mov     ebx, r14d
0x180009c48  mov     r12d, r14d
0x180009c4b  xor     bpl, bpl
0x180009c4e  call    cs:__imp_RtlAcquireSRWLockShared
0x180009c54  mov     rax, cs:g_leTaskHostContextListHead
0x180009c5b  lea     rsi, g_leTaskHostContextListHead
0x180009c62  mov     r15d, 1
0x180009c68  cmp     rax, rsi
0x180009c6b  jz      short loc_180009C7E
0x180009c6d  nop     dword ptr [rax]
0x180009c70  mov     rax, [rax]
0x180009c73  inc     ebx
0x180009c75  cmp     rax, rsi
0x180009c78  jnz     short loc_180009C70
0x180009c7a  test    ebx, ebx
0x180009c7c  jnz     short loc_180009CAB
0x180009c7e  lea     rcx, g_TaskHostContextListLock
0x180009c85  call    cs:__imp_RtlReleaseSRWLockShared
0x180009c8b  test    ebx, ebx
0x180009c8d  jnz     short loc_180009D08
0x180009c8f  test    r12, r12
0x180009c92  jnz     loc_180009E09
0x180009c98  movzx   eax, bpl
0x180009c9c  add     rsp, 30h
0x180009ca0  pop     r15
0x180009ca2  pop     r14
0x180009ca4  pop     r12
0x180009ca6  pop     rdi
0x180009ca7  pop     rsi
0x180009ca8  pop     rbp
0x180009ca9  pop     rbx
0x180009caa  retn
0x180009cab  lea     ecx, ds:0[rbx*8]; Size
0x180009cb2  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x180009cb7  mov     r12, rax
0x180009cba  test    rax, rax
0x180009cbd  jz      loc_180009E47
0x180009cc3  mov     rdx, cs:g_leTaskHostContextListHead
0x180009cca  mov     r8d, r14d
0x180009ccd  cmp     rdx, rsi
0x180009cd0  jz      short loc_180009C7E
0x180009cd2  nop     dword ptr [rax+00h]
0x180009cd6  nop     word ptr [rax+rax+00000000h]
0x180009ce0  mov     eax, r8d
0x180009ce3  lea     rcx, [rdx-8]
0x180009ce7  mov     [r12+rax*8], rcx
0x180009ceb  lock inc qword ptr [rcx+60h]
0x180009cf0  mov     rdx, [rdx]
0x180009cf3  inc     r8d
0x180009cf6  cmp     rdx, rsi
0x180009cf9  jnz     short loc_180009CE0
0x180009cfb  lea     rcx, g_TaskHostContextListLock
0x180009d02  call    cs:__imp_RtlReleaseSRWLockShared
0x180009d08  mov     ebp, r14d
0x180009d0b  mov     [rsp+68h+arg_10], r13
0x180009d13  mov     rcx, r12
0x180009d16  cmp     ebp, ebx
0x180009d18  jnb     loc_180009E31
0x180009d1e  mov     eax, ebp
0x180009d20  mov     r15, [rcx+rax*8]
0x180009d24  lea     rcx, [r15+40h]
0x180009d28  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180009d2e  call    cs:__imp_GetCurrentThreadId
0x180009d34  mov     [r15+48h], eax
0x180009d38  movzx   eax, byte ptr [r15+68h]
0x180009d3d  test    al, 4
0x180009d3f  jnz     loc_180009F01
0x180009d45  test    al, 10h
0x180009d47  jnz     short loc_180009D78
0x180009d49  lea     rcx, [r15+118h]; Uuid1
0x180009d50  mov     rdx, rdi; Uuid2
0x180009d53  lea     r8, [rsp+68h+Status]; Status
0x180009d58  call    cs:__imp_UuidEqual
0x180009d5e  lea     rcx, [r15+40h]
0x180009d62  test    eax, eax
0x180009d64  jnz     loc_180009E9F
0x180009d6a  mov     [r15+48h], r14d
0x180009d6e  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180009d74  inc     ebp
0x180009d76  jmp     short loc_180009D13
0x180009d78  lea     r14, [r15+0C8h]
0x180009d7f  mov     rdi, [r14]
0x180009d82  cmp     rdi, r14
0x180009d85  jz      short loc_180009DEE
0x180009d87  test    byte ptr [rdi+58h], 1
0x180009d8b  jz      short loc_180009D92
0x180009d8d  mov     rdi, [rdi]
0x180009d90  jmp     short loc_180009D82
0x180009d92  mov     rdx, [rsp+68h+Uuid2]; Uuid2
0x180009d97  lea     rcx, [rdi+5Ch]; Uuid1
0x180009d9b  lea     r8, [rsp+68h+Status]; Status
0x180009da0  call    cs:__imp_UuidEqual
0x180009da6  test    eax, eax
0x180009da8  jz      short loc_180009D8D
0x180009daa  mov     word ptr [rdi+5Ah], 1
0x180009db0  mov     bpl, 1
0x180009db3  mov     rcx, cs:WPP_GLOBAL_Control
0x180009dba  lea     rax, WPP_GLOBAL_Control
0x180009dc1  cmp     rcx, rax
0x180009dc4  jnz     loc_180009F14
0x180009dca  xor     r14d, r14d
0x180009dcd  lea     rcx, [r15+40h]
0x180009dd1  mov     [r15+48h], r14d
0x180009dd5  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180009ddb  mov     r13, [rsp+68h+arg_10]
0x180009de3  mov     r15d, 1
0x180009de9  jmp     loc_180009C8F
0x180009dee  xor     r14d, r14d
0x180009df1  lea     rcx, [r15+40h]
0x180009df5  mov     [r15+48h], r14d
0x180009df9  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180009dff  mov     rdi, [rsp+68h+Uuid2]
0x180009e04  jmp     loc_180009D74
0x180009e09  mov     edi, r14d
0x180009e0c  test    ebx, ebx
0x180009e0e  jz      short loc_180009E24
0x180009e10  mov     eax, edi
0x180009e12  mov     edx, r15d
0x180009e15  lea     rcx, [r12+rax*8]
0x180009e19  call    UbpmpDecrementRefAndDelete
0x180009e1e  inc     edi
0x180009e20  cmp     edi, ebx
0x180009e22  jb      short loc_180009E10
0x180009e24  mov     rcx, r12
0x180009e27  call    UBPM_MIDL_user_free
0x180009e2c  jmp     loc_180009C98
0x180009e31  xor     bpl, bpl
0x180009e34  mov     r13, [rsp+68h+arg_10]
0x180009e3c  mov     r15d, 1
0x180009e42  jmp     loc_180009C8F
0x180009e47  lea     rcx, g_TaskHostContextListLock
0x180009e4e  call    cs:__imp_RtlReleaseSRWLockShared
0x180009e54  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e5b  lea     rax, WPP_GLOBAL_Control
0x180009e62  cmp     rcx, rax
0x180009e65  jz      loc_180009C98
0x180009e6b  test    [rcx+1Ch], r15b
0x180009e6f  jz      loc_180009C98
0x180009e75  call    cs:__imp_GetLastError
0x180009e7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e82  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x180009e89  mov     edx, 33h ; '3'
0x180009e8e  mov     r9d, eax
0x180009e91  mov     rcx, [rcx+10h]
0x180009e95  call    WPP_SF_d
0x180009e9a  jmp     loc_180009C98
0x180009e9f  mov     word ptr [r15+114h], 1
0x180009ea9  mov     bpl, 1
0x180009eac  mov     [r15+48h], r14d
0x180009eb0  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180009eb6  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ebd  lea     rax, WPP_GLOBAL_Control
0x180009ec4  cmp     rcx, rax
0x180009ec7  jz      loc_180009E34
0x180009ecd  test    byte ptr [rcx+1Ch], 80h
0x180009ed1  jz      loc_180009E34
0x180009ed7  mov     rax, [r15+130h]
0x180009ede  mov     edx, 34h ; '4'
0x180009ee3  mov     rcx, [rcx+10h]
0x180009ee7  mov     r9, r15
0x180009eea  mov     [rsp+68h+var_40], rax
0x180009eef  mov     eax, [r15+20h]
0x180009ef3  mov     [rsp+68h+var_48], eax
0x180009ef7  call    WPP_SF_qdi
0x180009efc  jmp     loc_180009E34
0x180009f01  lea     rcx, [r15+40h]
0x180009f05  mov     [r15+48h], r14d
0x180009f09  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180009f0f  jmp     loc_180009D74
0x180009f14  test    byte ptr [rcx+1Ch], 80h
0x180009f18  jz      loc_180009DCA
0x180009f1e  mov     rax, [rdi+70h]
0x180009f22  lea     r9, [rdi-10h]
0x180009f26  mov     rcx, [rcx+10h]
0x180009f2a  mov     edx, 35h ; '5'
0x180009f2f  mov     [rsp+68h+var_40], rax
0x180009f34  mov     eax, [r15+20h]
0x180009f38  mov     [rsp+68h+var_48], eax
0x180009f3c  call    WPP_SF_qdi
0x180009f41  jmp     loc_180009DCA
```
