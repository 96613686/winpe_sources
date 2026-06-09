# UbpmpConsumeHostCommandActionCallback

- ea: `0x180010450`
- end: `0x180010721`
- name: `UbpmpConsumeHostCommandActionCallback`
- size: `721`
- prototype: `__int64 __fastcall(struct _UBPM_TASK_HOST_CONTEXT_BLOCK *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180004c30`
- `0x18000fc1c`
- `0x180010450`
- `0x180010730`
- `0x18001131c`
- `0x18001af64`
- `0x180032f78`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800105d6`
- `ntdll!RtlFreeHeap` at `0x1800105d6`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800104e0`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001058c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800104e0`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001058c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001054b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800105b8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001054b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800105b8`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180010613`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180010613`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800104ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010598`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800104ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010598`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800106e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800106e5`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180010537`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180010537`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800104c8`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800104c8`

## pseudocode

```c
char __fastcall UbpmpConsumeHostCommandActionCallback(
        struct _UBPM_TASK_HOST_CONTEXT_BLOCK *a1,
        char a2,
        __int64 a3,
        __int64 a4)
{
  int Response; // eax
  char v6; // r15
  struct _UBPM_TASK_HOST_CONTEXT_BLOCK *v7; // rbp
  DWORD v8; // eax
  _QWORD *v9; // rax
  struct _UBPM_TASK_HOST_CONTEXT_BLOCK *v10; // rcx
  __int64 v11; // rdx
  struct _UBPM_TASK_HOST_CONTEXT_BLOCK *v12; // rsi
  int v13; // eax
  HANDLE Handles[11]; // [rsp+30h] [rbp-58h] BYREF
  struct _UBPM_TASK_HOST_CONTEXT_BLOCK *v16; // [rsp+90h] [rbp+8h] BYREF

  Handles[0] = *((HANDLE *)a1 + 29);
  Handles[1] = *((HANDLE *)a1 + 3);
  v16 = a1;
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
        GetLastError();
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          154,
          WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
          *((unsigned int *)a1 + 8));
      }
    }
    else
    {
      v6 = 0;
      v7 = 0;
      do
      {
        v8 = WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0);
        if ( v8 )
        {
          if ( v8 == 1 )
            v6 = 1;
        }
        else
        {
          RtlAcquireSRWLockExclusive((char *)a1 + 64);
          *((_DWORD *)a1 + 18) = GetCurrentThreadId();
          v9 = (_QWORD *)((char *)a1 + 216);
          v10 = (struct _UBPM_TASK_HOST_CONTEXT_BLOCK *)*((_QWORD *)a1 + 27);
          if ( v10 != (struct _UBPM_TASK_HOST_CONTEXT_BLOCK *)((char *)a1 + 216) )
          {
            if ( *((_QWORD **)v10 + 1) != v9
              || (v11 = *(_QWORD *)v10, *(struct _UBPM_TASK_HOST_CONTEXT_BLOCK **)(*(_QWORD *)v10 + 8LL) != v10) )
            {
              __fastfail(3u);
            }
            *v9 = v11;
            v7 = v10;
            *(_QWORD *)(v11 + 8) = v9;
          }
          if ( (_QWORD *)*v9 == v9 )
            ResetEvent(*((HANDLE *)a1 + 29));
          *((_DWORD *)a1 + 18) = 0;
          RtlReleaseSRWLockExclusive((char *)a1 + 64);
          if ( v7 )
          {
            v12 = v7;
            v7 = 0;
            v13 = UbpmpProcessHostCommand(a1, *((unsigned __int16 **)v12 + 2), *((_QWORD *)v12 + 3));
            if ( v13 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                155,
                (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
                *((_QWORD *)a1 + 18),
                v13);
            *((_QWORD *)v12 + 2) = 0;
            if ( *((_QWORD *)v12 + 3) )
            {
              RtlAcquireSRWLockExclusive((char *)a1 + 64);
              *((_DWORD *)a1 + 18) = GetCurrentThreadId();
              UbpmpDecrementTaskRefAndDelete((char *)v12 + 24);
              *((_DWORD *)a1 + 18) = 0;
              RtlReleaseSRWLockExclusive((char *)a1 + 64);
            }
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
          }
        }
      }
      while ( (*((_BYTE *)a1 + 104) & 4) == 0 && !v6 );
    }
  }
  return UbpmpDecrementRefAndDelete((__int64 *)&v16, 1, a3, a4);
}

```

## disassembly

```asm
0x180010450  push    rbx
0x180010452  push    rbp
0x180010453  push    rsi
0x180010454  push    rdi
0x180010455  push    r12
0x180010457  push    r13
0x180010459  push    r14
0x18001045b  push    r15
0x18001045d  sub     rsp, 48h
0x180010461  mov     rax, [rcx+0E8h]
0x180010468  mov     rdi, rcx
0x18001046b  mov     [rsp+88h+Handles], rax
0x180010470  mov     rax, [rcx+18h]
0x180010474  mov     [rsp+88h+var_50], rax
0x180010479  mov     [rsp+88h+arg_0], rcx
0x180010481  test    dl, 4
0x180010484  jnz     loc_180010627
0x18001048a  call    UbpmpWaitForFirstResponse
0x18001048f  test    eax, eax
0x180010491  jnz     loc_1800105F3
0x180010497  xor     r15b, r15b
0x18001049a  lea     r12, WPP_GLOBAL_Control
0x1800104a1  xor     r13d, r13d
0x1800104a4  mov     ebp, r13d
0x1800104a7  nop     word ptr [rax+rax+00000000h]
0x1800104b0  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x1800104b6  mov     [rsp+88h+bAlertable], r13d; bAlertable
0x1800104bb  xor     r8d, r8d; bWaitAll
0x1800104be  lea     rdx, [rsp+88h+Handles]; lpHandles
0x1800104c3  mov     ecx, 2; nCount
0x1800104c8  call    cs:__imp_WaitForMultipleObjectsEx
0x1800104cf  nop     dword ptr [rax+rax+00h]
0x1800104d4  test    eax, eax
0x1800104d6  jnz     loc_18001068A
0x1800104dc  lea     rcx, [rdi+40h]
0x1800104e0  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800104e7  nop     dword ptr [rax+rax+00h]
0x1800104ec  call    cs:__imp_GetCurrentThreadId
0x1800104f3  nop     dword ptr [rax+rax+00h]
0x1800104f8  mov     [rdi+48h], eax
0x1800104fb  lea     rax, [rdi+0D8h]
0x180010502  mov     rcx, [rax]
0x180010505  cmp     rcx, rax
0x180010508  jz      short loc_18001052B
0x18001050a  cmp     [rcx+8], rax
0x18001050e  jnz     loc_18001071A
0x180010514  mov     rdx, [rcx]
0x180010517  cmp     [rdx+8], rcx
0x18001051b  jnz     loc_18001071A
0x180010521  mov     [rax], rdx
0x180010524  mov     rbp, rcx
0x180010527  mov     [rdx+8], rax
0x18001052b  cmp     [rax], rax
0x18001052e  jnz     short loc_180010543
0x180010530  mov     rcx, [rdi+0E8h]; hEvent
0x180010537  call    cs:__imp_ResetEvent
0x18001053e  nop     dword ptr [rax+rax+00h]
0x180010543  lea     rcx, [rdi+40h]
0x180010547  mov     [rdi+48h], r13d
0x18001054b  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180010552  nop     dword ptr [rax+rax+00h]
0x180010557  test    rbp, rbp
0x18001055a  jz      loc_1800105E2
0x180010560  mov     rsi, rbp
0x180010563  mov     rcx, rdi; struct _UBPM_TASK_HOST_CONTEXT_BLOCK *
0x180010566  mov     rbp, r13
0x180010569  mov     r8, [rsi+18h]
0x18001056d  mov     rdx, [rsi+10h]
0x180010571  call    UbpmpProcessHostCommand
0x180010576  test    eax, eax
0x180010578  jnz     loc_18001064B
0x18001057e  mov     [rsi+10h], r13
0x180010582  cmp     [rsi+18h], rbp
0x180010586  jz      short loc_1800105C4
0x180010588  lea     rcx, [rdi+40h]
0x18001058c  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180010593  nop     dword ptr [rax+rax+00h]
0x180010598  call    cs:__imp_GetCurrentThreadId
0x18001059f  nop     dword ptr [rax+rax+00h]
0x1800105a4  lea     rcx, [rsi+18h]
0x1800105a8  mov     [rdi+48h], eax
0x1800105ab  call    UbpmpDecrementTaskRefAndDelete
0x1800105b0  lea     rcx, [rdi+40h]
0x1800105b4  mov     [rdi+48h], r13d
0x1800105b8  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800105bf  nop     dword ptr [rax+rax+00h]
0x1800105c4  mov     rcx, gs:60h
0x1800105cd  mov     r8, rsi; P
0x1800105d0  xor     edx, edx; Flags
0x1800105d2  mov     rcx, [rcx+30h]; HeapHandle
0x1800105d6  call    cs:__imp_RtlFreeHeap
0x1800105dd  nop     dword ptr [rax+rax+00h]
0x1800105e2  test    byte ptr [rdi+68h], 4
0x1800105e6  jnz     short loc_180010627
0x1800105e8  test    r15b, r15b
0x1800105eb  jz      loc_1800104B0
0x1800105f1  jmp     short loc_180010627
0x1800105f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800105fa  lea     r12, WPP_GLOBAL_Control
0x180010601  cmp     rcx, r12
0x180010604  jnz     loc_18001069C
0x18001060a  mov     rcx, [rdi+18h]; hProcess
0x18001060e  mov     edx, 42Bh; uExitCode
0x180010613  call    cs:__imp_TerminateProcess
0x18001061a  nop     dword ptr [rax+rax+00h]
0x18001061f  test    eax, eax
0x180010621  jz      loc_1800106CB
0x180010627  mov     edx, 1
0x18001062c  lea     rcx, [rsp+88h+arg_0]
0x180010634  call    UbpmpDecrementRefAndDelete
0x180010639  add     rsp, 48h
0x18001063d  pop     r15
0x18001063f  pop     r14
0x180010641  pop     r13
0x180010643  pop     r12
0x180010645  pop     rdi
0x180010646  pop     rsi
0x180010647  pop     rbp
0x180010648  pop     rbx
0x180010649  retn
0x18001064b  mov     rcx, cs:WPP_GLOBAL_Control
0x180010652  cmp     rcx, r12
0x180010655  jz      loc_18001057E
0x18001065b  test    byte ptr [rcx+1Ch], 1
0x18001065f  jz      loc_18001057E
0x180010665  mov     r9, [rdi+90h]
0x18001066c  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x180010673  mov     rcx, [rcx+10h]
0x180010677  mov     edx, 9Bh
0x18001067c  mov     [rsp+88h+bAlertable], eax
0x180010680  call    WPP_SF_Sd
0x180010685  jmp     loc_18001057E
0x18001068a  cmp     eax, 1
0x18001068d  jnz     loc_1800105E2
0x180010693  movzx   r15d, al
0x180010697  jmp     loc_1800105E2
0x18001069c  test    byte ptr [rcx+1Ch], 1
0x1800106a0  jz      loc_18001060A
0x1800106a6  mov     r9, [rdi+90h]
0x1800106ad  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x1800106b4  mov     rcx, [rcx+10h]
0x1800106b8  mov     edx, 99h
0x1800106bd  mov     [rsp+88h+bAlertable], eax
0x1800106c1  call    WPP_SF_Sd
0x1800106c6  jmp     loc_18001060A
0x1800106cb  mov     rax, cs:WPP_GLOBAL_Control
0x1800106d2  cmp     rax, r12
0x1800106d5  jz      loc_180010627
0x1800106db  test    byte ptr [rax+1Ch], 2
0x1800106df  jz      loc_180010627
0x1800106e5  call    cs:__imp_GetLastError
0x1800106ec  nop     dword ptr [rax+rax+00h]
0x1800106f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800106f8  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x1800106ff  mov     r9d, [rdi+20h]
0x180010703  mov     edx, 9Ah
0x180010708  mov     [rsp+88h+bAlertable], eax
0x18001070c  mov     rcx, [rcx+10h]
0x180010710  call    WPP_SF_dd
0x180010715  jmp     loc_180010627
0x18001071a  mov     ecx, 3
0x18001071f  int     29h; Win8: RtlFailFast(ecx)
```
