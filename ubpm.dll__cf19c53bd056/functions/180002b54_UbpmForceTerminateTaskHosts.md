# UbpmForceTerminateTaskHosts

- ea: `0x180002b54`
- end: `0x180002db2`
- name: `UbpmForceTerminateTaskHosts`
- size: `606`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x180002ac0`
- `0x180017d70`

## callees

- `0x180002b54`
- `0x180009750`
- `0x18000a570`
- `0x18000a6e0`
- `0x180030cec`
- `0x180032e38`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x180002cb9`
- `ntdll!NtWaitForSingleObject` at `0x180002cb9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180002b9d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180002b9d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002bf7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002c43`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002ca9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002bf7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002c43`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002ca9`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180002d0f`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180002d0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002ba3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002ba3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d2b`

## pseudocode

```c
__int64 UbpmForceTerminateTaskHosts()
{
  volatile signed __int64 *v0; // rbx
  char v1; // si
  _UNKNOWN **v2; // rbp
  _UNKNOWN **v3; // rax
  char *v4; // rdi
  bool v5; // zf
  __int64 result; // rax
  void *v7; // rsi
  void *v8; // r14
  _QWORD *v9; // rcx
  __int64 v10; // r9
  __int64 v11; // rdx
  char *i; // rcx
  DWORD LastError; // eax
  union _LARGE_INTEGER Timeout; // [rsp+60h] [rbp+8h] BYREF
  _UNKNOWN **v15; // [rsp+68h] [rbp+10h] BYREF

  Timeout.QuadPart = MEMORY[0x7FFE0014] + 300000000LL;
  while ( 1 )
  {
    v0 = 0;
    v15 = 0;
    v1 = 0;
    RtlAcquireSRWLockExclusive(&g_TaskHostContextListLock);
    dword_18004CF18 = GetCurrentThreadId();
    v2 = 0;
    v3 = (_UNKNOWN **)g_leTaskHostContextListHead;
    v4 = 0;
    while ( v3 != &g_leTaskHostContextListHead )
    {
      v0 = (volatile signed __int64 *)(v3 - 1);
      v5 = ((_BYTE)v3[12] & 4) == 0;
      v2 = v3 - 1;
      v15 = v3 - 1;
      v4 = (char *)(v3 - 1);
      if ( v5 )
      {
        _InterlockedIncrement64(v0 + 12);
        v1 = 1;
        break;
      }
      v3 = (_UNKNOWN **)*v3;
    }
    dword_18004CF18 = 0;
    result = RtlReleaseSRWLockExclusive(&g_TaskHostContextListLock);
    if ( !v1 )
      return result;
    v7 = 0;
    UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)(v2 + 8));
    v8 = (void *)*((_QWORD *)v4 + 3);
    if ( !v8 )
      goto LABEL_12;
    if ( v4[104] < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_11;
      v10 = *((unsigned int *)v4 + 8);
      v11 = 54;
      goto LABEL_27;
    }
    if ( *((_WORD *)v4 + 98) )
    {
      for ( i = (char *)*((_QWORD *)v4 + 25); i != v4 + 200; i = *(char **)i )
      {
        if ( *((__int64 *)i - 1) > 1 )
        {
          *((_DWORD *)v0 + 18) = 0;
          RtlReleaseSRWLockExclusive(v0 + 8);
          NtWaitForSingleObject(v8, 0, &Timeout);
          UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)(v2 + 8));
          break;
        }
      }
    }
    if ( v4[104] >= 0 )
    {
      if ( TerminateProcess(*((HANDLE *)v4 + 3), 0x42Bu) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            57,
            WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
            *((unsigned int *)v0 + 8));
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          56,
          WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
          *((unsigned int *)v0 + 8),
          LastError);
      }
      v4[104] |= 0x80u;
      goto LABEL_11;
    }
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v10 = *((unsigned int *)v0 + 8);
      v11 = 55;
LABEL_27:
      WPP_SF_d(v9[2], v11, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, v10);
    }
LABEL_11:
    v7 = (void *)*((_QWORD *)v0 + 5);
    *((_QWORD *)v0 + 5) = 0;
LABEL_12:
    *((_DWORD *)v0 + 18) = 0;
    RtlReleaseSRWLockExclusive(v0 + 8);
    if ( v7 )
      UbpmpTaskHostTerminationCleanup((struct _UBPM_TASK_HOST_CONTEXT_BLOCK *)v0, v7);
    UbpmpDecrementRefAndDelete((__int64 *)&v15, 1);
  }
}

```

## disassembly

```asm
0x180002b54  mov     r11, rsp
0x180002b57  mov     [r11+18h], rbx
0x180002b5b  mov     [r11+20h], rbp
0x180002b5f  push    rsi
0x180002b60  push    rdi
0x180002b61  push    r12
0x180002b63  push    r14
0x180002b65  push    r15
0x180002b67  sub     rsp, 30h
0x180002b6b  xor     r15d, r15d
0x180002b6e  lea     r12, WPP_GLOBAL_Control
0x180002b75  mov     [r11+8], r15
0x180002b79  mov     eax, 7FFE0014h
0x180002b7e  mov     rax, [rax]
0x180002b81  add     rax, 11E1A300h
0x180002b87  mov     [r11+8], rax
0x180002b8b  mov     rbx, r15
0x180002b8e  lea     rcx, g_TaskHostContextListLock
0x180002b95  mov     [rsp+58h+arg_8], rbx
0x180002b9a  mov     sil, r15b
0x180002b9d  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180002ba3  call    cs:__imp_GetCurrentThreadId
0x180002ba9  mov     cs:dword_18004CF18, eax
0x180002baf  mov     rbp, r15
0x180002bb2  mov     rax, cs:g_leTaskHostContextListHead
0x180002bb9  mov     rdi, r15
0x180002bbc  lea     rcx, g_leTaskHostContextListHead
0x180002bc3  cmp     rax, rcx
0x180002bc6  jz      short loc_180002BE9
0x180002bc8  lea     rbx, [rax-8]
0x180002bcc  test    byte ptr [rbx+68h], 4
0x180002bd0  mov     rbp, rbx
0x180002bd3  mov     [rsp+58h+arg_8], rbx
0x180002bd8  mov     rdi, rbx
0x180002bdb  jnz     loc_180002C66
0x180002be1  lock inc qword ptr [rbx+60h]
0x180002be6  mov     sil, 1
0x180002be9  lea     rcx, g_TaskHostContextListLock
0x180002bf0  mov     cs:dword_18004CF18, r15d
0x180002bf7  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180002bfd  test    sil, sil
0x180002c00  jz      loc_180002D9B
0x180002c06  lea     rcx, [rbp+40h]; struct _UBPM_SRWLOCK *
0x180002c0a  mov     rsi, r15
0x180002c0d  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x180002c12  mov     r14, [rdi+18h]
0x180002c16  test    r14, r14
0x180002c19  jz      short loc_180002C3B
0x180002c1b  cmp     [rdi+68h], r15b
0x180002c1f  jge     short loc_180002C79
0x180002c21  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c28  cmp     rcx, r12
0x180002c2b  jz      short loc_180002C33
0x180002c2d  test    byte ptr [rcx+1Ch], 2
0x180002c31  jnz     short loc_180002C6E
0x180002c33  mov     rsi, [rbx+28h]
0x180002c37  mov     [rbx+28h], r15
0x180002c3b  lea     rcx, [rbx+40h]
0x180002c3f  mov     [rcx+8], r15d
0x180002c43  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180002c49  test    rsi, rsi
0x180002c4c  jnz     loc_180002D8B
0x180002c52  mov     edx, 1
0x180002c57  lea     rcx, [rsp+58h+arg_8]
0x180002c5c  call    UbpmpDecrementRefAndDelete
0x180002c61  jmp     loc_180002B8B
0x180002c66  mov     rax, [rax]
0x180002c69  jmp     loc_180002BBC
0x180002c6e  mov     r9d, [rdi+20h]
0x180002c72  mov     edx, 36h ; '6'
0x180002c77  jmp     short loc_180002CF1
0x180002c79  cmp     [rdi+0C4h], r15w
0x180002c81  jbe     short loc_180002CC8
0x180002c83  lea     rdx, [rdi+0C8h]
0x180002c8a  mov     rcx, [rdx]
0x180002c8d  cmp     rcx, rdx
0x180002c90  jz      short loc_180002CC8
0x180002c92  mov     rax, [rcx-8]
0x180002c96  cmp     rax, 1
0x180002c9a  jg      short loc_180002CA1
0x180002c9c  mov     rcx, [rcx]
0x180002c9f  jmp     short loc_180002C8D
0x180002ca1  lea     rcx, [rbx+40h]
0x180002ca5  mov     [rcx+8], r15d
0x180002ca9  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180002caf  lea     r8, [rsp+58h+Timeout]; Timeout
0x180002cb4  xor     edx, edx; Alertable
0x180002cb6  mov     rcx, r14; Handle
0x180002cb9  call    cs:__imp_NtWaitForSingleObject
0x180002cbf  lea     rcx, [rbp+40h]; struct _UBPM_SRWLOCK *
0x180002cc3  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x180002cc8  cmp     [rdi+68h], r15b
0x180002ccc  jge     short loc_180002D06
0x180002cce  mov     rcx, cs:WPP_GLOBAL_Control
0x180002cd5  cmp     rcx, r12
0x180002cd8  jz      loc_180002C33
0x180002cde  test    byte ptr [rcx+1Ch], 2
0x180002ce2  jz      loc_180002C33
0x180002ce8  mov     r9d, [rbx+20h]
0x180002cec  mov     edx, 37h ; '7'
0x180002cf1  mov     rcx, [rcx+10h]
0x180002cf5  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x180002cfc  call    WPP_SF_d
0x180002d01  jmp     loc_180002C33
0x180002d06  mov     rcx, [rdi+18h]; hProcess
0x180002d0a  mov     edx, 42Bh; uExitCode
0x180002d0f  call    cs:__imp_TerminateProcess
0x180002d15  test    eax, eax
0x180002d17  jnz     short loc_180002D57
0x180002d19  mov     rax, cs:WPP_GLOBAL_Control
0x180002d20  cmp     rax, r12
0x180002d23  jz      short loc_180002D82
0x180002d25  test    byte ptr [rax+1Ch], 2
0x180002d29  jz      short loc_180002D82
0x180002d2b  call    cs:__imp_GetLastError
0x180002d31  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d38  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x180002d3f  mov     r9d, [rbx+20h]
0x180002d43  mov     edx, 38h ; '8'
0x180002d48  mov     [rsp+58h+var_38], eax
0x180002d4c  mov     rcx, [rcx+10h]
0x180002d50  call    WPP_SF_dd
0x180002d55  jmp     short loc_180002D82
0x180002d57  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d5e  cmp     rcx, r12
0x180002d61  jz      short loc_180002D82
0x180002d63  test    byte ptr [rcx+1Ch], 80h
0x180002d67  jz      short loc_180002D82
0x180002d69  mov     r9d, [rbx+20h]
0x180002d6d  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x180002d74  mov     rcx, [rcx+10h]
0x180002d78  mov     edx, 39h ; '9'
0x180002d7d  call    WPP_SF_d
0x180002d82  or      byte ptr [rdi+68h], 80h
0x180002d86  jmp     loc_180002C33
0x180002d8b  mov     rdx, rsi; WaitHandle
0x180002d8e  mov     rcx, rbx; struct _UBPM_TASK_HOST_CONTEXT_BLOCK *
0x180002d91  call    ?UbpmpTaskHostTerminationCleanup@@YAXPEAU_UBPM_TASK_HOST_CONTEXT_BLOCK@@PEAX@Z; UbpmpTaskHostTerminationCleanup(_UBPM_TASK_HOST_CONTEXT_BLOCK *,void *)
0x180002d96  jmp     loc_180002C52
0x180002d9b  mov     rbx, [rsp+58h+arg_10]
0x180002da0  mov     rbp, [rsp+58h+arg_18]
0x180002da5  add     rsp, 30h
0x180002da9  pop     r15
0x180002dab  pop     r14
0x180002dad  pop     r12
0x180002daf  pop     rdi
0x180002db0  pop     rsi
0x180002db1  retn
```
