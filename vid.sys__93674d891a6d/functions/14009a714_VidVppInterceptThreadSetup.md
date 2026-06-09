# VidVppInterceptThreadSetup

- ea: `0x14009a714`
- end: `0x14009a8c9`
- name: `VidVppInterceptThreadSetup`
- size: `437`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x140099fcc`
- `0x1400fcb5c`

## callees

- `0x140021c60`
- `0x140037798`
- `0x1400386a0`
- `0x140076088`
- `0x140076220`
- `0x14009a714`
- `0x1400fa818`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x14009a7fa`
- `ntoskrnl!PsGetThreadId` at `0x14009a7fa`
- `ntoskrnl!KeSetPriorityThread` at `0x14009a82e`
- `ntoskrnl!KeSetPriorityThread` at `0x14009a82e`
- `ntoskrnl!ZwSetInformationThread` at `0x14009a86f`
- `ntoskrnl!ZwSetInformationThread` at `0x14009a86f`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14009a88b`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14009a88b`
- `ntoskrnl!ZwClose` at `0x14009a8a1`
- `ntoskrnl!ZwClose` at `0x14009a8a1`

## string_xrefs

- `0x14009a7ce`: `VidVppInterceptThreadSetup`

## pseudocode

```c
__int64 __fastcall VidVppInterceptThreadSetup(PKTHREAD *a1)
{
  HANDLE v1; // rbx
  int PartitionThread; // esi
  __int64 v4; // r8
  PKTHREAD v5; // r15
  __int64 (__fastcall *v6)(); // rdx
  PKTHREAD *v7; // r14
  struct _KTHREAD *v8; // rcx
  unsigned int v9; // ebx
  HANDLE ThreadId; // rax
  __int64 v11; // rcx
  HANDLE ThreadHandle[2]; // [rsp+30h] [rbp-48h] BYREF
  __int128 v14; // [rsp+40h] [rbp-38h] BYREF
  _QWORD ThreadInformation[2]; // [rsp+50h] [rbp-28h] BYREF

  v1 = 0;
  memset(ThreadInformation, 0, 12);
  ThreadHandle[0] = 0;
  if ( (*((_DWORD *)VidDeviceExtension + 162) & 0x20) != 0 )
  {
    PartitionThread = VidXSchedulerVpDispatchContextSetup();
    if ( PartitionThread < 0 )
    {
      v4 = 1679;
LABEL_9:
      VidTraceErrorInternal0("VidVppInterceptThreadSetup", "onecore\\vm\\vid\\sys\\driver\\vidvp.c", v4);
      VidVppInterceptThreadTeardown(a1);
      goto LABEL_17;
    }
  }
  v5 = *a1;
  if ( *((_QWORD *)*a1 + 1289) )
  {
    v6 = VidXSchedulerVpThreadStartRoutine;
    v7 = a1 + 42;
    if ( (*((_DWORD *)VidDeviceExtension + 162) & 0x20) == 0 )
      v6 = VidVppInterceptThreadRoutine;
    PartitionThread = VidCreatePartitionThread(
                        (unsigned int)*a1,
                        (_DWORD)v6,
                        (_DWORD)a1,
                        (int)a1 + 336,
                        (__int64)ThreadHandle);
    if ( PartitionThread < 0 )
    {
      v1 = ThreadHandle[0];
      v4 = 1711;
      goto LABEL_9;
    }
    v8 = *v7;
    v9 = *((_DWORD *)a1 + 2);
    v14 = *((_OWORD *)v5 + 41);
    ThreadId = PsGetThreadId(v8);
    VidTraceRoutineGuidWithUint64AndUint64(v11, &v14, v9, ThreadId);
    if ( (*((_DWORD *)VidDeviceExtension + 162) & 0x20) != 0 )
    {
      v1 = ThreadHandle[0];
      if ( (*((_DWORD *)*a1 + 4) & 0x2000LL) == 0 )
      {
        *(_QWORD *)((char *)ThreadInformation + 4) = 1;
        LODWORD(ThreadInformation[0]) = 1;
        ZwSetInformationThread(ThreadHandle[0], ThreadHideFromDebugger|0x20, ThreadInformation, 0xCu);
      }
      if ( *((_DWORD *)*a1 + 806) )
        KeSetActualBasePriorityThread(*v7);
    }
    else
    {
      KeSetPriorityThread(*v7, 31);
      v1 = ThreadHandle[0];
    }
  }
  PartitionThread = 0;
LABEL_17:
  if ( v1 )
    ZwClose(v1);
  return (unsigned int)PartitionThread;
}

```

## disassembly

```asm
0x14009a714  push    rbp
0x14009a716  push    rbx
0x14009a717  push    rsi
0x14009a718  push    rdi
0x14009a719  push    r14
0x14009a71b  push    r15
0x14009a71d  mov     rbp, rsp
0x14009a720  sub     rsp, 78h
0x14009a724  mov     rax, cs:__security_cookie
0x14009a72b  xor     rax, rsp
0x14009a72e  mov     [rbp+var_18], rax
0x14009a732  xor     eax, eax
0x14009a734  xor     ebx, ebx
0x14009a736  mov     [rbp+ThreadInformation], rax
0x14009a73a  mov     rdi, rcx
0x14009a73d  mov     [rbp+var_20], eax
0x14009a740  mov     rax, cs:VidDeviceExtension
0x14009a747  mov     [rbp+ThreadHandle], rbx
0x14009a74b  mov     eax, [rax+288h]
0x14009a751  test    al, 20h
0x14009a753  jz      short loc_14009A768
0x14009a755  call    VidXSchedulerVpDispatchContextSetup
0x14009a75a  mov     esi, eax
0x14009a75c  test    eax, eax
0x14009a75e  jns     short loc_14009A768
0x14009a760  mov     r8d, 68Fh
0x14009a766  jmp     short loc_14009A7C7
0x14009a768  mov     r15, [rdi]
0x14009a76b  cmp     [r15+2848h], rbx
0x14009a772  jz      loc_14009A897
0x14009a778  mov     rax, cs:VidDeviceExtension
0x14009a77f  lea     rdx, VidXSchedulerVpThreadStartRoutine
0x14009a786  lea     r14, [rdi+150h]
0x14009a78d  mov     r8, rdi
0x14009a790  mov     r9, r14
0x14009a793  mov     rcx, r15
0x14009a796  mov     eax, [rax+288h]
0x14009a79c  test    al, 20h
0x14009a79e  lea     rax, VidVppInterceptThreadRoutine
0x14009a7a5  cmovz   rdx, rax
0x14009a7a9  lea     rax, [rbp+ThreadHandle]
0x14009a7ad  mov     [rsp+78h+var_58], rax
0x14009a7b2  call    VidCreatePartitionThread
0x14009a7b7  mov     esi, eax
0x14009a7b9  test    eax, eax
0x14009a7bb  jns     short loc_14009A7E7
0x14009a7bd  mov     rbx, [rbp+ThreadHandle]
0x14009a7c1  mov     r8d, 6AFh
0x14009a7c7  lea     rdx, aOnecoreVmVidSy_2; "onecore\\vm\\vid\\sys\\driver\\vidvp.c"
0x14009a7ce  lea     rcx, aVidvppintercep; "VidVppInterceptThreadSetup"
0x14009a7d5  call    VidTraceErrorInternal0
0x14009a7da  mov     rcx, rdi
0x14009a7dd  call    VidVppInterceptThreadTeardown
0x14009a7e2  jmp     loc_14009A899
0x14009a7e7  movups  xmm0, xmmword ptr [r15+290h]
0x14009a7ef  mov     rcx, [r14]; Thread
0x14009a7f2  mov     ebx, [rdi+8]
0x14009a7f5  movdqu  [rbp+var_38], xmm0
0x14009a7fa  call    cs:__imp_PsGetThreadId
0x14009a801  nop     dword ptr [rax+rax+00h]
0x14009a806  mov     r8d, ebx
0x14009a809  lea     rdx, [rbp+var_38]
0x14009a80d  mov     r9, rax
0x14009a810  call    VidTraceRoutineGuidWithUint64AndUint64
0x14009a815  mov     rax, cs:VidDeviceExtension
0x14009a81c  mov     eax, [rax+288h]
0x14009a822  test    al, 20h
0x14009a824  jnz     short loc_14009A840
0x14009a826  mov     rcx, [r14]; Thread
0x14009a829  mov     edx, 1Fh; Priority
0x14009a82e  call    cs:__imp_KeSetPriorityThread
0x14009a835  nop     dword ptr [rax+rax+00h]
0x14009a83a  mov     rbx, [rbp+ThreadHandle]
0x14009a83e  jmp     short loc_14009A897
0x14009a840  mov     rax, [rdi]
0x14009a843  mov     rbx, [rbp+ThreadHandle]
0x14009a847  mov     ecx, [rax+10h]
0x14009a84a  bt      rcx, 0Dh
0x14009a84f  jb      short loc_14009A87B
0x14009a851  mov     eax, 1
0x14009a856  mov     [rbp+ThreadInformation+4], 1
0x14009a85e  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x14009a862  mov     dword ptr [rbp+ThreadInformation], eax
0x14009a865  mov     rcx, rbx; ThreadHandle
0x14009a868  lea     r9d, [rax+0Bh]; ThreadInformationLength
0x14009a86c  lea     edx, [rax+30h]; ThreadInformationClass
0x14009a86f  call    cs:__imp_ZwSetInformationThread
0x14009a876  nop     dword ptr [rax+rax+00h]
0x14009a87b  mov     rax, [rdi]
0x14009a87e  mov     edx, [rax+0C98h]
0x14009a884  test    edx, edx
0x14009a886  jz      short loc_14009A897
0x14009a888  mov     rcx, [r14]
0x14009a88b  call    cs:__imp_KeSetActualBasePriorityThread
0x14009a892  nop     dword ptr [rax+rax+00h]
0x14009a897  xor     esi, esi
0x14009a899  test    rbx, rbx
0x14009a89c  jz      short loc_14009A8AD
0x14009a89e  mov     rcx, rbx; Handle
0x14009a8a1  call    cs:__imp_ZwClose
0x14009a8a8  nop     dword ptr [rax+rax+00h]
0x14009a8ad  mov     eax, esi
0x14009a8af  mov     rcx, [rbp+var_18]
0x14009a8b3  xor     rcx, rsp; StackCookie
0x14009a8b6  call    __security_check_cookie
0x14009a8bb  add     rsp, 78h
0x14009a8bf  pop     r15
0x14009a8c1  pop     r14
0x14009a8c3  pop     rdi
0x14009a8c4  pop     rsi
0x14009a8c5  pop     rbx
0x14009a8c6  pop     rbp
0x14009a8c7  retn
```
