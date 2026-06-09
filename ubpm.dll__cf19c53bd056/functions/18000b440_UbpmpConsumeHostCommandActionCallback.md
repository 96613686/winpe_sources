# UbpmpConsumeHostCommandActionCallback

- ea: `0x18000b440`
- end: `0x18000b6ca`
- name: `UbpmpConsumeHostCommandActionCallback`
- size: `650`
- prototype: `__int64 __fastcall(struct _UBPM_TASK_HOST_CONTEXT_BLOCK *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180009750`
- `0x18000b440`
- `0x18000b6d0`
- `0x18000c248`
- `0x18001e9f4`
- `0x180026318`
- `0x180030cec`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000b592`
- `ntdll!RtlFreeHeap` at `0x18000b592`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000b4ca`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000b55a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000b4ca`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000b55a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000b523`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000b57a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000b523`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000b57a`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18000b5c9`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18000b5c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b4d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b560`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b4d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b560`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b694`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b694`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000b515`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000b515`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000b4b8`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000b4b8`

## pseudocode

```c
char __fastcall UbpmpConsumeHostCommandActionCallback(struct _UBPM_TASK_HOST_CONTEXT_BLOCK *a1, char a2)
{
  int Response; // eax
  char v4; // r15
  struct _UBPM_TASK_HOST_CONTEXT_BLOCK *v5; // rbp
  DWORD v6; // eax
  _QWORD *v7; // rax
  struct _UBPM_TASK_HOST_CONTEXT_BLOCK *v8; // rcx
  __int64 v9; // rdx
  struct _UBPM_TASK_HOST_CONTEXT_BLOCK *v10; // rsi
  int v11; // eax
  DWORD LastError; // eax
  HANDLE Handles[11]; // [rsp+30h] [rbp-58h] BYREF
  struct _UBPM_TASK_HOST_CONTEXT_BLOCK *v15; // [rsp+90h] [rbp+8h] BYREF

  Handles[0] = *((HANDLE *)a1 + 29);
  Handles[1] = *((HANDLE *)a1 + 3);
  v15 = a1;
  if ( (a2 & 4) == 0 )
  {
    Response = UbpmpWaitForFirstResponse();
    if ( Response )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          153,
          (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
          *((_QWORD *)a1 + 18),
          Response);
      if ( !TerminateProcess(*((HANDLE *)a1 + 3), 0x42Bu)
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          154,
          WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
          *((unsigned int *)a1 + 8),
          LastError);
      }
    }
    else
    {
      v4 = 0;
      v5 = 0;
      do
      {
        v6 = WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0);
        if ( v6 )
        {
          if ( v6 == 1 )
            v4 = 1;
        }
        else
        {
          RtlAcquireSRWLockExclusive((char *)a1 + 64);
          *((_DWORD *)a1 + 18) = GetCurrentThreadId();
          v7 = (_QWORD *)((char *)a1 + 216);
          v8 = (struct _UBPM_TASK_HOST_CONTEXT_BLOCK *)*((_QWORD *)a1 + 27);
          if ( v8 != (struct _UBPM_TASK_HOST_CONTEXT_BLOCK *)((char *)a1 + 216) )
          {
            if ( *((_QWORD **)v8 + 1) != v7
              || (v9 = *(_QWORD *)v8, *(struct _UBPM_TASK_HOST_CONTEXT_BLOCK **)(*(_QWORD *)v8 + 8LL) != v8) )
            {
              __fastfail(3u);
            }
            *v7 = v9;
            v5 = v8;
            *(_QWORD *)(v9 + 8) = v7;
          }
          if ( (_QWORD *)*v7 == v7 )
            ResetEvent(*((HANDLE *)a1 + 29));
          *((_DWORD *)a1 + 18) = 0;
          RtlReleaseSRWLockExclusive((char *)a1 + 64);
          if ( v5 )
          {
            v10 = v5;
            v5 = 0;
            v11 = UbpmpProcessHostCommand(a1, *((unsigned __int16 **)v10 + 2), *((_QWORD *)v10 + 3));
            if ( v11 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                155,
                (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
                *((_QWORD *)a1 + 18),
                v11);
            *((_QWORD *)v10 + 2) = 0;
            if ( *((_QWORD *)v10 + 3) )
            {
              RtlAcquireSRWLockExclusive((char *)a1 + 64);
              *((_DWORD *)a1 + 18) = GetCurrentThreadId();
              UbpmpDecrementTaskRefAndDelete((char *)v10 + 24);
              *((_DWORD *)a1 + 18) = 0;
              RtlReleaseSRWLockExclusive((char *)a1 + 64);
            }
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
          }
        }
      }
      while ( (*((_BYTE *)a1 + 104) & 4) == 0 && !v4 );
    }
  }
  return UbpmpDecrementRefAndDelete((__int64 *)&v15, 1);
}

```

## disassembly

```asm
0x18000b440  push    rbx
0x18000b442  push    rbp
0x18000b443  push    rsi
0x18000b444  push    rdi
0x18000b445  push    r12
0x18000b447  push    r13
0x18000b449  push    r14
0x18000b44b  push    r15
0x18000b44d  sub     rsp, 48h
0x18000b451  mov     rax, [rcx+0E8h]
0x18000b458  mov     rdi, rcx
0x18000b45b  mov     [rsp+88h+Handles], rax
0x18000b460  mov     rax, [rcx+18h]
0x18000b464  mov     [rsp+88h+var_50], rax
0x18000b469  mov     [rsp+88h+arg_0], rcx
0x18000b471  test    dl, 4
0x18000b474  jnz     loc_18000B5D7
0x18000b47a  call    UbpmpWaitForFirstResponse
0x18000b47f  test    eax, eax
0x18000b481  jnz     loc_18000B5A9
0x18000b487  xor     r15b, r15b
0x18000b48a  lea     r12, WPP_GLOBAL_Control
0x18000b491  xor     r13d, r13d
0x18000b494  mov     ebp, r13d
0x18000b497  nop     word ptr [rax+rax+00000000h]
0x18000b4a0  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x18000b4a6  mov     [rsp+88h+bAlertable], r13d; bAlertable
0x18000b4ab  xor     r8d, r8d; bWaitAll
0x18000b4ae  lea     rdx, [rsp+88h+Handles]; lpHandles
0x18000b4b3  mov     ecx, 2; nCount
0x18000b4b8  call    cs:__imp_WaitForMultipleObjectsEx
0x18000b4be  test    eax, eax
0x18000b4c0  jnz     loc_18000B639
0x18000b4c6  lea     rcx, [rdi+40h]
0x18000b4ca  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000b4d0  call    cs:__imp_GetCurrentThreadId
0x18000b4d6  mov     [rdi+48h], eax
0x18000b4d9  lea     rax, [rdi+0D8h]
0x18000b4e0  mov     rcx, [rax]
0x18000b4e3  cmp     rcx, rax
0x18000b4e6  jz      short loc_18000B509
0x18000b4e8  cmp     [rcx+8], rax
0x18000b4ec  jnz     loc_18000B6C3
0x18000b4f2  mov     rdx, [rcx]
0x18000b4f5  cmp     [rdx+8], rcx
0x18000b4f9  jnz     loc_18000B6C3
0x18000b4ff  mov     [rax], rdx
0x18000b502  mov     rbp, rcx
0x18000b505  mov     [rdx+8], rax
0x18000b509  cmp     [rax], rax
0x18000b50c  jnz     short loc_18000B51B
0x18000b50e  mov     rcx, [rdi+0E8h]; hEvent
0x18000b515  call    cs:__imp_ResetEvent
0x18000b51b  lea     rcx, [rdi+40h]
0x18000b51f  mov     [rdi+48h], r13d
0x18000b523  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000b529  test    rbp, rbp
0x18000b52c  jz      short loc_18000B598
0x18000b52e  mov     rsi, rbp
0x18000b531  mov     rcx, rdi; struct _UBPM_TASK_HOST_CONTEXT_BLOCK *
0x18000b534  mov     rbp, r13
0x18000b537  mov     r8, [rsi+18h]
0x18000b53b  mov     rdx, [rsi+10h]
0x18000b53f  call    UbpmpProcessHostCommand
0x18000b544  test    eax, eax
0x18000b546  jnz     loc_18000B5FA
0x18000b54c  mov     [rsi+10h], r13
0x18000b550  cmp     [rsi+18h], rbp
0x18000b554  jz      short loc_18000B580
0x18000b556  lea     rcx, [rdi+40h]
0x18000b55a  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000b560  call    cs:__imp_GetCurrentThreadId
0x18000b566  lea     rcx, [rsi+18h]
0x18000b56a  mov     [rdi+48h], eax
0x18000b56d  call    UbpmpDecrementTaskRefAndDelete
0x18000b572  lea     rcx, [rdi+40h]
0x18000b576  mov     [rdi+48h], r13d
0x18000b57a  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000b580  mov     rcx, gs:60h
0x18000b589  mov     r8, rsi; P
0x18000b58c  xor     edx, edx; Flags
0x18000b58e  mov     rcx, [rcx+30h]; HeapHandle
0x18000b592  call    cs:__imp_RtlFreeHeap
0x18000b598  test    byte ptr [rdi+68h], 4
0x18000b59c  jnz     short loc_18000B5D7
0x18000b59e  test    r15b, r15b
0x18000b5a1  jz      loc_18000B4A0
0x18000b5a7  jmp     short loc_18000B5D7
0x18000b5a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b5b0  lea     r12, WPP_GLOBAL_Control
0x18000b5b7  cmp     rcx, r12
0x18000b5ba  jnz     loc_18000B64B
0x18000b5c0  mov     rcx, [rdi+18h]; hProcess
0x18000b5c4  mov     edx, 42Bh; uExitCode
0x18000b5c9  call    cs:__imp_TerminateProcess
0x18000b5cf  test    eax, eax
0x18000b5d1  jz      loc_18000B67A
0x18000b5d7  mov     edx, 1
0x18000b5dc  lea     rcx, [rsp+88h+arg_0]
0x18000b5e4  call    UbpmpDecrementRefAndDelete
0x18000b5e9  add     rsp, 48h
0x18000b5ed  pop     r15
0x18000b5ef  pop     r14
0x18000b5f1  pop     r13
0x18000b5f3  pop     r12
0x18000b5f5  pop     rdi
0x18000b5f6  pop     rsi
0x18000b5f7  pop     rbp
0x18000b5f8  pop     rbx
0x18000b5f9  retn
0x18000b5fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b601  cmp     rcx, r12
0x18000b604  jz      loc_18000B54C
0x18000b60a  test    byte ptr [rcx+1Ch], 1
0x18000b60e  jz      loc_18000B54C
0x18000b614  mov     r9, [rdi+90h]
0x18000b61b  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18000b622  mov     rcx, [rcx+10h]
0x18000b626  mov     edx, 9Bh
0x18000b62b  mov     [rsp+88h+bAlertable], eax
0x18000b62f  call    WPP_SF_Sd
0x18000b634  jmp     loc_18000B54C
0x18000b639  cmp     eax, 1
0x18000b63c  jnz     loc_18000B598
0x18000b642  movzx   r15d, al
0x18000b646  jmp     loc_18000B598
0x18000b64b  test    byte ptr [rcx+1Ch], 1
0x18000b64f  jz      loc_18000B5C0
0x18000b655  mov     r9, [rdi+90h]
0x18000b65c  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18000b663  mov     rcx, [rcx+10h]
0x18000b667  mov     edx, 99h
0x18000b66c  mov     [rsp+88h+bAlertable], eax
0x18000b670  call    WPP_SF_Sd
0x18000b675  jmp     loc_18000B5C0
0x18000b67a  mov     rax, cs:WPP_GLOBAL_Control
0x18000b681  cmp     rax, r12
0x18000b684  jz      loc_18000B5D7
0x18000b68a  test    byte ptr [rax+1Ch], 2
0x18000b68e  jz      loc_18000B5D7
0x18000b694  call    cs:__imp_GetLastError
0x18000b69a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b6a1  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18000b6a8  mov     r9d, [rdi+20h]
0x18000b6ac  mov     edx, 9Ah
0x18000b6b1  mov     [rsp+88h+bAlertable], eax
0x18000b6b5  mov     rcx, [rcx+10h]
0x18000b6b9  call    WPP_SF_dd
0x18000b6be  jmp     loc_18000B5D7
0x18000b6c3  mov     ecx, 3
0x18000b6c8  int     29h; Win8: RtlFailFast(ecx)
```
