# WimSqmInitialize

- ea: `0x14002e578`
- end: `0x14002e752`
- name: `WimSqmInitialize`
- size: `474`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140027cec`

## callees

- `0x140011560`
- `0x140011640`
- `0x1400116c0`
- `0x1400119c0`
- `0x14002e578`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14002e665`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002e665`
- `ntoskrnl!KeInitializeMutex` at `0x14002e6c3`
- `ntoskrnl!KeInitializeMutex` at `0x14002e6c3`
- `ntoskrnl!KeInitializeDpc` at `0x14002e6fb`
- `ntoskrnl!KeInitializeDpc` at `0x14002e6fb`
- `ntoskrnl!KeInitializeTimerEx` at `0x14002e6db`
- `ntoskrnl!KeInitializeTimerEx` at `0x14002e6db`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14002e699`
- `ntoskrnl!KeSetCoalescableTimer` at `0x14002e724`
- `ntoskrnl!KeSetCoalescableTimer` at `0x14002e724`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14002e675`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14002e675`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e6ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e6ae`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002e5b2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002e5b2`

## string_xrefs

- `0x14002e614`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
BOOLEAN __fastcall WimSqmInitialize(const void **a1)
{
  _WORD *PoolWithTag; // rax
  _WORD *v3; // rbx
  PVOID SystemRoutineAddress; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-79h] BYREF
  _QWORD v7[22]; // [rsp+40h] [rbp-69h] BYREF

  PoolWithTag = ExAllocatePoolWithTag(PagedPool, *(unsigned __int16 *)a1 + 2LL, 0x6E677077u);
  v3 = PoolWithTag;
  if ( PoolWithTag )
  {
    memmove(PoolWithTag, a1[1], *(unsigned __int16 *)a1);
    v3[(unsigned __int64)*(unsigned __int16 *)a1 >> 1] = 0;
    memset(v7, 0, 0xA8u);
    LODWORD(v7[1]) = 1;
    v7[10] = &WimSqmInterval;
    v7[2] = L"Wim";
    v7[12] = &WimSqmInterval;
    v7[9] = L"SqmInterval";
    v7[3] = 0;
    LODWORD(v7[11]) = 4;
    LODWORD(v7[13]) = 4;
    LODWORD(v7[4]) = 0;
    v7[5] = 0;
    LODWORD(v7[6]) = 0;
    LODWORD(v7[8]) = 32;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
    SystemRoutineAddress = MmGetSystemRoutineAddress(&DestinationString);
    if ( !SystemRoutineAddress )
      SystemRoutineAddress = RtlQueryRegistryValues;
    ((void (__fastcall *)(__int64, _WORD *, _QWORD *, _QWORD, _QWORD))SystemRoutineAddress)(0x80000000LL, v3, v7, 0, 0);
    ExFreePoolWithTag(v3, 0);
  }
  KeInitializeMutex(&WimSqmLock, 0);
  KeInitializeTimerEx(&WimSqmTimer, SynchronizationTimer);
  KeInitializeDpc(&WimSqmDpc, WimSqmDpcRoutine, 0);
  return KeSetCoalescableTimer(&WimSqmTimer, (LARGE_INTEGER)(120 * WimOneSecond), 0, 0x3E8u, &WimSqmDpc);
}

```

## disassembly

```asm
0x14002e578  mov     [rsp-8+arg_8], rbx
0x14002e57d  mov     [rsp-8+arg_10], rdi
0x14002e582  push    rbp
0x14002e583  lea     rbp, [rsp-57h]
0x14002e588  sub     rsp, 100h
0x14002e58f  mov     rax, cs:__security_cookie
0x14002e596  xor     rax, rsp
0x14002e599  mov     [rbp+57h+var_10], rax
0x14002e59d  movzx   edx, word ptr [rcx]
0x14002e5a0  mov     rdi, rcx
0x14002e5a3  add     rdx, 2; NumberOfBytes
0x14002e5a7  mov     ecx, 1; PoolType
0x14002e5ac  mov     r8d, 6E677077h; Tag
0x14002e5b2  call    cs:__imp_ExAllocatePoolWithTag
0x14002e5b9  nop     dword ptr [rax+rax+00h]
0x14002e5be  mov     rbx, rax
0x14002e5c1  test    rax, rax
0x14002e5c4  jz      loc_14002E6BA
0x14002e5ca  movzx   r8d, word ptr [rdi]; Size
0x14002e5ce  mov     rcx, rax; void *
0x14002e5d1  mov     rdx, [rdi+8]; Src
0x14002e5d5  call    memmove
0x14002e5da  movzx   edx, word ptr [rdi]
0x14002e5dd  xor     ecx, ecx
0x14002e5df  shr     rdx, 1
0x14002e5e2  mov     r8d, 0A8h; Size
0x14002e5e8  mov     [rbx+rdx*2], cx
0x14002e5ec  xor     edx, edx; Val
0x14002e5ee  lea     rcx, [rbp+57h+var_C0]; void *
0x14002e5f2  call    memset
0x14002e5f7  lea     rcx, WimSqmInterval
0x14002e5fe  mov     [rbp+57h+var_B8], 1
0x14002e605  lea     rax, aWim; "Wim"
0x14002e60c  mov     [rbp+57h+var_70], rcx
0x14002e610  mov     [rbp+57h+var_B0], rax
0x14002e614  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x14002e61b  lea     rax, aSqminterval; "SqmInterval"
0x14002e622  mov     [rbp+57h+var_60], rcx
0x14002e626  mov     [rbp+57h+var_78], rax
0x14002e62a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14002e62e  mov     eax, 4
0x14002e633  mov     [rbp+57h+var_A8], 0
0x14002e63b  xorps   xmm0, xmm0
0x14002e63e  mov     [rbp+57h+var_68], eax
0x14002e641  mov     [rbp+57h+var_58], eax
0x14002e644  mov     [rbp+57h+var_A0], 0
0x14002e64b  mov     [rbp+57h+var_98], 0
0x14002e653  mov     [rbp+57h+var_90], 0
0x14002e65a  mov     [rbp+57h+var_80], 20h ; ' '
0x14002e661  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14002e665  call    cs:__imp_RtlInitUnicodeString
0x14002e66c  nop     dword ptr [rax+rax+00h]
0x14002e671  lea     rcx, [rbp+57h+DestinationString]; SystemRoutineName
0x14002e675  call    cs:__imp_MmGetSystemRoutineAddress
0x14002e67c  nop     dword ptr [rax+rax+00h]
0x14002e681  lea     r8, [rbp+57h+var_C0]
0x14002e685  mov     [rsp+100h+Dpc], 0
0x14002e68e  test    rax, rax
0x14002e691  mov     rdx, rbx
0x14002e694  mov     ecx, 80000000h
0x14002e699  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x14002e6a1  xor     r9d, r9d
0x14002e6a4  call    _guard_dispatch_icall
0x14002e6a9  xor     edx, edx; Tag
0x14002e6ab  mov     rcx, rbx; P
0x14002e6ae  call    cs:__imp_ExFreePoolWithTag
0x14002e6b5  nop     dword ptr [rax+rax+00h]
0x14002e6ba  xor     edx, edx; Level
0x14002e6bc  lea     rcx, WimSqmLock; Mutex
0x14002e6c3  call    cs:__imp_KeInitializeMutex
0x14002e6ca  nop     dword ptr [rax+rax+00h]
0x14002e6cf  mov     edx, 1; Type
0x14002e6d4  lea     rcx, WimSqmTimer; Timer
0x14002e6db  call    cs:__imp_KeInitializeTimerEx
0x14002e6e2  nop     dword ptr [rax+rax+00h]
0x14002e6e7  lea     rbx, WimSqmDpc
0x14002e6ee  xor     r8d, r8d; DeferredContext
0x14002e6f1  mov     rcx, rbx; Dpc
0x14002e6f4  lea     rdx, WimSqmDpcRoutine; DeferredRoutine
0x14002e6fb  call    cs:__imp_KeInitializeDpc
0x14002e702  nop     dword ptr [rax+rax+00h]
0x14002e707  imul    rdx, cs:WimOneSecond, 78h ; 'x'; DueTime
0x14002e70f  mov     r9d, 3E8h; TolerableDelay
0x14002e715  mov     [rsp+100h+Dpc], rbx; Dpc
0x14002e71a  xor     r8d, r8d; Period
0x14002e71d  lea     rcx, WimSqmTimer; Timer
0x14002e724  call    cs:__imp_KeSetCoalescableTimer
0x14002e72b  nop     dword ptr [rax+rax+00h]
0x14002e730  mov     rcx, [rbp+57h+var_10]
0x14002e734  xor     rcx, rsp; StackCookie
0x14002e737  call    __security_check_cookie
0x14002e73c  lea     r11, [rsp+100h+var_s0]
0x14002e744  mov     rbx, [r11+18h]
0x14002e748  mov     rdi, [r11+20h]
0x14002e74c  mov     rsp, r11
0x14002e74f  pop     rbp
0x14002e750  retn
```
