# PfsActionItemQueueEx

- ea: `0x18003cbe4`
- end: `0x18003cd9d`
- name: `PfsActionItemQueueEx`
- size: `441`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `69`
- callee_count: `3`
- tags: ``

## callers

- `0x1800163b0`
- `0x180017370`
- `0x180038bf8`
- `0x180039598`
- `0x180039a44`
- `0x18003b118`
- `0x18003b57c`
- `0x18003b920`
- `0x18003bb70`
- `0x18003c250`
- `0x18003c534`
- `0x18003c5b4`
- `0x18003c85c`
- `0x18003d1c0`
- `0x18003e594`
- `0x1800406cc`
- `0x18004c020`
- `0x18004fce0`
- `0x180050628`
- `0x180051190`
- `0x180051420`
- `0x18005159c`
- `0x180051ec4`
- `0x180055b7c`
- `0x180057710`
- `0x180058d80`
- `0x1800592f8`
- `0x180059aac`
- `0x18005afd0`
- `0x18005c994`
- `0x18005e298`
- `0x18005e4c0`
- `0x18005f708`
- `0x18005f760`
- `0x180060d50`
- `0x18006445c`
- `0x18006598c`
- `0x180066ae8`
- `0x1800675cc`
- `0x180067e34`
- `0x1800680d0`
- `0x180068200`
- `0x18006a020`
- `0x18006d810`
- `0x18006ebcc`
- `0x180070380`
- `0x180070b6c`
- `0x1800736c8`
- `0x1800739c0`
- `0x18007403c`

## callees

- `0x18003cbe4`
- `0x18003cf08`
- `0x180059594`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cc1a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cc1a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cccb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cccb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003cd33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003cd33`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18003cd2b`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18003cd3c`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18003cd2b`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18003cd3c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003cd50`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003cd50`

## pseudocode

```c
__int64 __fastcall PfsActionItemQueueEx(
        LPCRITICAL_SECTION lpCriticalSection,
        unsigned int a2,
        unsigned __int64 *a3,
        _QWORD *a4)
{
  unsigned __int16 *OwningThread; // rsi
  int v5; // r12d
  unsigned __int64 v7; // r14
  unsigned int v8; // ebp
  __int64 v10; // rbp
  unsigned __int16 *v11; // rbx
  __int64 i; // rax
  unsigned __int16 *v13; // r9
  __int64 v14; // rcx
  __int64 v15; // rdx
  unsigned int v16; // ebx
  __int64 v18; // rdx
  void *v19; // rcx
  int ThreadPriority; // ebx
  HANDLE CurrentThread; // rax
  int v22; // eax
  _QWORD *v23; // rdx
  _QWORD *j; // rcx

  OwningThread = (unsigned __int16 *)lpCriticalSection[1].OwningThread;
  v5 = 0;
  v7 = *a3;
  v8 = a2;
  if ( a2 >= LODWORD(lpCriticalSection[1].LockSemaphore) )
  {
    v8 = a2 - LODWORD(lpCriticalSection[1].LockSemaphore);
    v19 = *(void **)&lpCriticalSection[1].LockCount;
    if ( v19 )
    {
      ThreadPriority = GetThreadPriority(v19);
      CurrentThread = GetCurrentThread();
      v22 = GetThreadPriority(CurrentThread);
      if ( ThreadPriority < v22 )
      {
        if ( SetThreadPriority(*(HANDLE *)&lpCriticalSection[1].LockCount, v22) )
          BYTE5(lpCriticalSection[1].LockSemaphore) = 1;
      }
    }
  }
  v10 = v8 + 1;
  EnterCriticalSection(lpCriticalSection);
  v11 = &OwningThread[12 * (unsigned int)v10];
  if ( *((_QWORD *)v11 + 2) != 0x7FFFFFFFFFFFFFFFLL )
  {
    v18 = *v11;
    LOBYTE(v5) = v11 == &OwningThread[12 * *OwningThread];
    OwningThread[12 * v11[1]] = v18;
    OwningThread[12 * v18 + 1] = v11[1];
  }
  if ( v7 != 0x7FFFFFFFFFFFFFFFLL )
  {
    for ( i = *OwningThread; ; i = *v13 )
    {
      v13 = &OwningThread[12 * i];
      if ( v13 == OwningThread || *((_QWORD *)v13 + 2) >= v7 )
        break;
    }
    v14 = 3LL * v13[1];
    v15 = 3LL * (unsigned __int16)v10;
    OwningThread[4 * v15] = OwningThread[12 * v13[1]];
    OwningThread[4 * v15 + 1] = v13[1];
    OwningThread[4 * v14] = v10;
    v13[1] = v10;
    if ( v11 == &OwningThread[12 * *OwningThread] )
      v5 = 1;
  }
  if ( a4 )
  {
    v23 = v11 + 4;
    for ( j = (_QWORD *)*((_QWORD *)v11 + 1); j; j = (_QWORD *)*j )
      v23 = j;
    *v23 = a4;
    *a4 = 0;
  }
  else if ( v7 == 0x7FFFFFFFFFFFFFFFLL )
  {
    PfsActionItemCleanup(&OwningThread[12 * v10]);
  }
  *((_QWORD *)v11 + 2) = v7;
  if ( v5 )
    v16 = PfsActionItemMgrSetTimer(lpCriticalSection);
  else
    v16 = 0;
  LeaveCriticalSection(lpCriticalSection);
  return v16;
}

```

## disassembly

```asm
0x18003cbe4  push    rbx
0x18003cbe6  push    rbp
0x18003cbe7  push    rsi
0x18003cbe8  push    rdi
0x18003cbe9  push    r12
0x18003cbeb  push    r13
0x18003cbed  push    r14
0x18003cbef  push    r15
0x18003cbf1  sub     rsp, 28h
0x18003cbf5  mov     rsi, [rcx+38h]
0x18003cbf9  xor     r12d, r12d
0x18003cbfc  mov     r15, r9
0x18003cbff  mov     r14, [r8]
0x18003cc02  mov     ebp, edx
0x18003cc04  mov     rdi, rcx
0x18003cc07  lea     r13d, [r12+1]
0x18003cc0c  cmp     edx, [rcx+40h]
0x18003cc0f  jnb     loc_18003CD1B
0x18003cc15  mov     rcx, rdi; lpCriticalSection
0x18003cc18  inc     ebp
0x18003cc1a  call    cs:__imp_EnterCriticalSection
0x18003cc20  lea     rcx, ds:0[rbp*2]
0x18003cc28  mov     r10, 7FFFFFFFFFFFFFFFh
0x18003cc32  add     rcx, rbp
0x18003cc35  lea     rbx, [rsi+rcx*8]
0x18003cc39  cmp     [rbx+10h], r10
0x18003cc3d  jnz     loc_18003CCE4
0x18003cc43  cmp     r14, r10
0x18003cc46  jz      short loc_18003CCA3
0x18003cc48  movzx   eax, word ptr [rsi]
0x18003cc4b  jmp     short loc_18003CC57
0x18003cc4d  cmp     [r9+10h], r14
0x18003cc51  jnb     short loc_18003CC64
0x18003cc53  movzx   eax, word ptr [r9]
0x18003cc57  lea     rcx, [rax+rax*2]
0x18003cc5b  lea     r9, [rsi+rcx*8]
0x18003cc5f  cmp     r9, rsi
0x18003cc62  jnz     short loc_18003CC4D
0x18003cc64  movzx   eax, word ptr [r9+2]
0x18003cc69  movzx   r8d, bp
0x18003cc6d  lea     rcx, [rax+rax*2]
0x18003cc71  movzx   eax, word ptr [rsi+rcx*8]
0x18003cc75  lea     rdx, [r8+r8*2]
0x18003cc79  mov     [rsi+rdx*8], ax
0x18003cc7d  movzx   eax, word ptr [r9+2]
0x18003cc82  mov     [rsi+rdx*8+2], ax
0x18003cc87  mov     [rsi+rcx*8], r8w
0x18003cc8c  mov     [r9+2], r8w
0x18003cc91  movzx   eax, word ptr [rsi]
0x18003cc94  lea     rcx, [rax+rax*2]
0x18003cc98  lea     rax, [rsi+rcx*8]
0x18003cc9c  cmp     rbx, rax
0x18003cc9f  cmovz   r12d, r13d
0x18003cca3  test    r15, r15
0x18003cca6  jnz     loc_18003CD67
0x18003ccac  cmp     r14, r10
0x18003ccaf  jz      loc_18003CD90
0x18003ccb5  mov     [rbx+10h], r14
0x18003ccb9  test    r12d, r12d
0x18003ccbc  jz      short loc_18003CD17
0x18003ccbe  mov     rcx, rdi
0x18003ccc1  call    PfsActionItemMgrSetTimer
0x18003ccc6  mov     ebx, eax
0x18003ccc8  mov     rcx, rdi; lpCriticalSection
0x18003cccb  call    cs:__imp_LeaveCriticalSection
0x18003ccd1  mov     eax, ebx
0x18003ccd3  add     rsp, 28h
0x18003ccd7  pop     r15
0x18003ccd9  pop     r14
0x18003ccdb  pop     r13
0x18003ccdd  pop     r12
0x18003ccdf  pop     rdi
0x18003cce0  pop     rsi
0x18003cce1  pop     rbp
0x18003cce2  pop     rbx
0x18003cce3  retn
0x18003cce4  movzx   eax, word ptr [rsi]
0x18003cce7  movzx   edx, word ptr [rbx]
0x18003ccea  lea     rcx, [rax+rax*2]
0x18003ccee  lea     rax, [rsi+rcx*8]
0x18003ccf2  cmp     rbx, rax
0x18003ccf5  movzx   eax, word ptr [rbx+2]
0x18003ccf9  setz    r12b
0x18003ccfd  lea     rcx, [rax+rax*2]
0x18003cd01  mov     [rsi+rcx*8], dx
0x18003cd05  lea     rcx, [rdx+rdx*2]
0x18003cd09  movzx   eax, word ptr [rbx+2]
0x18003cd0d  mov     [rsi+rcx*8+2], ax
0x18003cd12  jmp     loc_18003CC43
0x18003cd17  xor     ebx, ebx
0x18003cd19  jmp     short loc_18003CCC8
0x18003cd1b  sub     ebp, [rcx+40h]
0x18003cd1e  mov     rcx, [rcx+30h]; hThread
0x18003cd22  test    rcx, rcx
0x18003cd25  jz      loc_18003CC15
0x18003cd2b  call    cs:__imp_GetThreadPriority
0x18003cd31  mov     ebx, eax
0x18003cd33  call    cs:__imp_GetCurrentThread
0x18003cd39  mov     rcx, rax; hThread
0x18003cd3c  call    cs:__imp_GetThreadPriority
0x18003cd42  cmp     ebx, eax
0x18003cd44  jge     loc_18003CC15
0x18003cd4a  mov     rcx, [rdi+30h]; hThread
0x18003cd4e  mov     edx, eax; nPriority
0x18003cd50  call    cs:__imp_SetThreadPriority
0x18003cd56  test    eax, eax
0x18003cd58  jz      loc_18003CC15
0x18003cd5e  mov     [rdi+45h], r13b
0x18003cd62  jmp     loc_18003CC15
0x18003cd67  lea     rdx, [rbx+8]
0x18003cd6b  mov     rcx, [rdx]
0x18003cd6e  test    rcx, rcx
0x18003cd71  jz      short loc_18003CD81
0x18003cd73  mov     rax, [rcx]
0x18003cd76  mov     rdx, rcx
0x18003cd79  mov     rcx, rax
0x18003cd7c  test    rax, rax
0x18003cd7f  jnz     short loc_18003CD73
0x18003cd81  mov     [rdx], r15
0x18003cd84  mov     qword ptr [r15], 0
0x18003cd8b  jmp     loc_18003CCB5
0x18003cd90  mov     rcx, rbx
0x18003cd93  call    PfsActionItemCleanup
0x18003cd98  jmp     loc_18003CCB5
```
