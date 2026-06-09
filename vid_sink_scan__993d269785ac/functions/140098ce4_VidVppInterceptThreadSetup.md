# VidVppInterceptThreadSetup

- ea: `0x140098ce4`
- end: `0x140098e99`
- name: `VidVppInterceptThreadSetup`
- size: `437`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x14009859c`
- `0x1400fa2e8`

## callees

- `0x140021650`
- `0x140037728`
- `0x140038630`
- `0x1400751c8`
- `0x140075360`
- `0x140098ce4`
- `0x1400f803c`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x140098dca`
- `ntoskrnl!PsGetThreadId` at `0x140098dca`
- `ntoskrnl!KeSetPriorityThread` at `0x140098dfe`
- `ntoskrnl!KeSetPriorityThread` at `0x140098dfe`
- `ntoskrnl!ZwSetInformationThread` at `0x140098e3f`
- `ntoskrnl!ZwSetInformationThread` at `0x140098e3f`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x140098e5b`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x140098e5b`
- `ntoskrnl!ZwClose` at `0x140098e71`
- `ntoskrnl!ZwClose` at `0x140098e71`

## string_xrefs

- `0x140098d9e`: `VidVppInterceptThreadSetup`

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
    PartitionThread = VidXSchedulerVpDispatchContextSetup((__int64)a1);
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
0x140098ce4  push    rbp
0x140098ce6  push    rbx
0x140098ce7  push    rsi
0x140098ce8  push    rdi
0x140098ce9  push    r14
0x140098ceb  push    r15
0x140098ced  mov     rbp, rsp
0x140098cf0  sub     rsp, 78h
0x140098cf4  mov     rax, cs:__security_cookie
0x140098cfb  xor     rax, rsp
0x140098cfe  mov     [rbp+var_18], rax
0x140098d02  xor     eax, eax
0x140098d04  xor     ebx, ebx
0x140098d06  mov     [rbp+ThreadInformation], rax
0x140098d0a  mov     rdi, rcx
0x140098d0d  mov     [rbp+var_20], eax
0x140098d10  mov     rax, cs:VidDeviceExtension
0x140098d17  mov     [rbp+ThreadHandle], rbx
0x140098d1b  mov     eax, [rax+288h]
0x140098d21  test    al, 20h
0x140098d23  jz      short loc_140098D38
0x140098d25  call    VidXSchedulerVpDispatchContextSetup
0x140098d2a  mov     esi, eax
0x140098d2c  test    eax, eax
0x140098d2e  jns     short loc_140098D38
0x140098d30  mov     r8d, 68Fh
0x140098d36  jmp     short loc_140098D97
0x140098d38  mov     r15, [rdi]
0x140098d3b  cmp     [r15+2848h], rbx
0x140098d42  jz      loc_140098E67
0x140098d48  mov     rax, cs:VidDeviceExtension
0x140098d4f  lea     rdx, VidXSchedulerVpThreadStartRoutine
0x140098d56  lea     r14, [rdi+150h]
0x140098d5d  mov     r8, rdi
0x140098d60  mov     r9, r14
0x140098d63  mov     rcx, r15
0x140098d66  mov     eax, [rax+288h]
0x140098d6c  test    al, 20h
0x140098d6e  lea     rax, VidVppInterceptThreadRoutine
0x140098d75  cmovz   rdx, rax
0x140098d79  lea     rax, [rbp+ThreadHandle]
0x140098d7d  mov     [rsp+78h+var_58], rax
0x140098d82  call    VidCreatePartitionThread
0x140098d87  mov     esi, eax
0x140098d89  test    eax, eax
0x140098d8b  jns     short loc_140098DB7
0x140098d8d  mov     rbx, [rbp+ThreadHandle]
0x140098d91  mov     r8d, 6AFh
0x140098d97  lea     rdx, aOnecoreVmVidSy_2; "onecore\\vm\\vid\\sys\\driver\\vidvp.c"
0x140098d9e  lea     rcx, aVidvppintercep; "VidVppInterceptThreadSetup"
0x140098da5  call    VidTraceErrorInternal0
0x140098daa  mov     rcx, rdi
0x140098dad  call    VidVppInterceptThreadTeardown
0x140098db2  jmp     loc_140098E69
0x140098db7  movups  xmm0, xmmword ptr [r15+290h]
0x140098dbf  mov     rcx, [r14]; Thread
0x140098dc2  mov     ebx, [rdi+8]
0x140098dc5  movdqu  [rbp+var_38], xmm0
0x140098dca  call    cs:__imp_PsGetThreadId
0x140098dd1  nop     dword ptr [rax+rax+00h]
0x140098dd6  mov     r8d, ebx
0x140098dd9  lea     rdx, [rbp+var_38]
0x140098ddd  mov     r9, rax
0x140098de0  call    VidTraceRoutineGuidWithUint64AndUint64
0x140098de5  mov     rax, cs:VidDeviceExtension
0x140098dec  mov     eax, [rax+288h]
0x140098df2  test    al, 20h
0x140098df4  jnz     short loc_140098E10
0x140098df6  mov     rcx, [r14]; Thread
0x140098df9  mov     edx, 1Fh; Priority
0x140098dfe  call    cs:__imp_KeSetPriorityThread
0x140098e05  nop     dword ptr [rax+rax+00h]
0x140098e0a  mov     rbx, [rbp+ThreadHandle]
0x140098e0e  jmp     short loc_140098E67
0x140098e10  mov     rax, [rdi]
0x140098e13  mov     rbx, [rbp+ThreadHandle]
0x140098e17  mov     ecx, [rax+10h]
0x140098e1a  bt      rcx, 0Dh
0x140098e1f  jb      short loc_140098E4B
0x140098e21  mov     eax, 1
0x140098e26  mov     [rbp+ThreadInformation+4], 1
0x140098e2e  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x140098e32  mov     dword ptr [rbp+ThreadInformation], eax
0x140098e35  mov     rcx, rbx; ThreadHandle
0x140098e38  lea     r9d, [rax+0Bh]; ThreadInformationLength
0x140098e3c  lea     edx, [rax+30h]; ThreadInformationClass
0x140098e3f  call    cs:__imp_ZwSetInformationThread
0x140098e46  nop     dword ptr [rax+rax+00h]
0x140098e4b  mov     rax, [rdi]
0x140098e4e  mov     edx, [rax+0C98h]
0x140098e54  test    edx, edx
0x140098e56  jz      short loc_140098E67
0x140098e58  mov     rcx, [r14]
0x140098e5b  call    cs:__imp_KeSetActualBasePriorityThread
0x140098e62  nop     dword ptr [rax+rax+00h]
0x140098e67  xor     esi, esi
0x140098e69  test    rbx, rbx
0x140098e6c  jz      short loc_140098E7D
0x140098e6e  mov     rcx, rbx; Handle
0x140098e71  call    cs:__imp_ZwClose
0x140098e78  nop     dword ptr [rax+rax+00h]
0x140098e7d  mov     eax, esi
0x140098e7f  mov     rcx, [rbp+var_18]
0x140098e83  xor     rcx, rsp; StackCookie
0x140098e86  call    __security_check_cookie
0x140098e8b  add     rsp, 78h
0x140098e8f  pop     r15
0x140098e91  pop     r14
0x140098e93  pop     rdi
0x140098e94  pop     rsi
0x140098e95  pop     rbx
0x140098e96  pop     rbp
0x140098e97  retn
```
