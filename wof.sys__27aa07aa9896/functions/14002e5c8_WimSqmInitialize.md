# WimSqmInitialize

- ea: `0x14002e5c8`
- end: `0x14002e7a2`
- name: `WimSqmInitialize`
- size: `474`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140027d3c`

## callees

- `0x140011560`
- `0x140011640`
- `0x1400116c0`
- `0x1400119c0`
- `0x14002e5c8`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14002e6b5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002e6b5`
- `ntoskrnl!KeInitializeMutex` at `0x14002e713`
- `ntoskrnl!KeInitializeMutex` at `0x14002e713`
- `ntoskrnl!KeInitializeDpc` at `0x14002e74b`
- `ntoskrnl!KeInitializeDpc` at `0x14002e74b`
- `ntoskrnl!KeInitializeTimerEx` at `0x14002e72b`
- `ntoskrnl!KeInitializeTimerEx` at `0x14002e72b`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14002e6e9`
- `ntoskrnl!KeSetCoalescableTimer` at `0x14002e774`
- `ntoskrnl!KeSetCoalescableTimer` at `0x14002e774`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14002e6c5`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14002e6c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e6fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e6fe`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002e602`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002e602`

## string_xrefs

- `0x14002e664`: `RtlQueryRegistryValuesEx`

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
0x14002e5c8  mov     [rsp-8+arg_8], rbx
0x14002e5cd  mov     [rsp-8+arg_10], rdi
0x14002e5d2  push    rbp
0x14002e5d3  lea     rbp, [rsp-57h]
0x14002e5d8  sub     rsp, 100h
0x14002e5df  mov     rax, cs:__security_cookie
0x14002e5e6  xor     rax, rsp
0x14002e5e9  mov     [rbp+57h+var_10], rax
0x14002e5ed  movzx   edx, word ptr [rcx]
0x14002e5f0  mov     rdi, rcx
0x14002e5f3  add     rdx, 2; NumberOfBytes
0x14002e5f7  mov     ecx, 1; PoolType
0x14002e5fc  mov     r8d, 6E677077h; Tag
0x14002e602  call    cs:__imp_ExAllocatePoolWithTag
0x14002e609  nop     dword ptr [rax+rax+00h]
0x14002e60e  mov     rbx, rax
0x14002e611  test    rax, rax
0x14002e614  jz      loc_14002E70A
0x14002e61a  movzx   r8d, word ptr [rdi]; Size
0x14002e61e  mov     rcx, rax; void *
0x14002e621  mov     rdx, [rdi+8]; Src
0x14002e625  call    memmove
0x14002e62a  movzx   edx, word ptr [rdi]
0x14002e62d  xor     ecx, ecx
0x14002e62f  shr     rdx, 1
0x14002e632  mov     r8d, 0A8h; Size
0x14002e638  mov     [rbx+rdx*2], cx
0x14002e63c  xor     edx, edx; Val
0x14002e63e  lea     rcx, [rbp+57h+var_C0]; void *
0x14002e642  call    memset
0x14002e647  lea     rcx, WimSqmInterval
0x14002e64e  mov     [rbp+57h+var_B8], 1
0x14002e655  lea     rax, aWim; "Wim"
0x14002e65c  mov     [rbp+57h+var_70], rcx
0x14002e660  mov     [rbp+57h+var_B0], rax
0x14002e664  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x14002e66b  lea     rax, aSqminterval; "SqmInterval"
0x14002e672  mov     [rbp+57h+var_60], rcx
0x14002e676  mov     [rbp+57h+var_78], rax
0x14002e67a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14002e67e  mov     eax, 4
0x14002e683  mov     [rbp+57h+var_A8], 0
0x14002e68b  xorps   xmm0, xmm0
0x14002e68e  mov     [rbp+57h+var_68], eax
0x14002e691  mov     [rbp+57h+var_58], eax
0x14002e694  mov     [rbp+57h+var_A0], 0
0x14002e69b  mov     [rbp+57h+var_98], 0
0x14002e6a3  mov     [rbp+57h+var_90], 0
0x14002e6aa  mov     [rbp+57h+var_80], 20h ; ' '
0x14002e6b1  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14002e6b5  call    cs:__imp_RtlInitUnicodeString
0x14002e6bc  nop     dword ptr [rax+rax+00h]
0x14002e6c1  lea     rcx, [rbp+57h+DestinationString]; SystemRoutineName
0x14002e6c5  call    cs:__imp_MmGetSystemRoutineAddress
0x14002e6cc  nop     dword ptr [rax+rax+00h]
0x14002e6d1  lea     r8, [rbp+57h+var_C0]
0x14002e6d5  mov     [rsp+100h+Dpc], 0
0x14002e6de  test    rax, rax
0x14002e6e1  mov     rdx, rbx
0x14002e6e4  mov     ecx, 80000000h
0x14002e6e9  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x14002e6f1  xor     r9d, r9d
0x14002e6f4  call    _guard_dispatch_icall
0x14002e6f9  xor     edx, edx; Tag
0x14002e6fb  mov     rcx, rbx; P
0x14002e6fe  call    cs:__imp_ExFreePoolWithTag
0x14002e705  nop     dword ptr [rax+rax+00h]
0x14002e70a  xor     edx, edx; Level
0x14002e70c  lea     rcx, WimSqmLock; Mutex
0x14002e713  call    cs:__imp_KeInitializeMutex
0x14002e71a  nop     dword ptr [rax+rax+00h]
0x14002e71f  mov     edx, 1; Type
0x14002e724  lea     rcx, WimSqmTimer; Timer
0x14002e72b  call    cs:__imp_KeInitializeTimerEx
0x14002e732  nop     dword ptr [rax+rax+00h]
0x14002e737  lea     rbx, WimSqmDpc
0x14002e73e  xor     r8d, r8d; DeferredContext
0x14002e741  mov     rcx, rbx; Dpc
0x14002e744  lea     rdx, WimSqmDpcRoutine; DeferredRoutine
0x14002e74b  call    cs:__imp_KeInitializeDpc
0x14002e752  nop     dword ptr [rax+rax+00h]
0x14002e757  imul    rdx, cs:WimOneSecond, 78h ; 'x'; DueTime
0x14002e75f  mov     r9d, 3E8h; TolerableDelay
0x14002e765  mov     [rsp+100h+Dpc], rbx; Dpc
0x14002e76a  xor     r8d, r8d; Period
0x14002e76d  lea     rcx, WimSqmTimer; Timer
0x14002e774  call    cs:__imp_KeSetCoalescableTimer
0x14002e77b  nop     dword ptr [rax+rax+00h]
0x14002e780  mov     rcx, [rbp+57h+var_10]
0x14002e784  xor     rcx, rsp; StackCookie
0x14002e787  call    __security_check_cookie
0x14002e78c  lea     r11, [rsp+100h+var_s0]
0x14002e794  mov     rbx, [r11+18h]
0x14002e798  mov     rdi, [r11+20h]
0x14002e79c  mov     rsp, r11
0x14002e79f  pop     rbp
0x14002e7a0  retn
```
