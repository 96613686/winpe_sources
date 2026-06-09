# RfspThreadPoolNodeCreateWorker

- ea: `0x14008bd54`
- end: `0x14008bea0`
- name: `RfspThreadPoolNodeCreateWorker`
- size: `332`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14008bc20`
- `0x140091e6c`

## callees

- `0x14008bd54`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14008bdb7`
- `ntoskrnl!ExAllocatePool2` at `0x14008bdb7`
- `ntoskrnl!ZwClose` at `0x14008be8d`
- `ntoskrnl!ZwClose` at `0x14008be8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008be78`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008be78`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14008bd7e`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14008bd7e`
- `ntoskrnl!IoCreateSystemThread` at `0x14008be51`
- `ntoskrnl!IoCreateSystemThread` at `0x14008be51`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14008bdd3`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14008bdd3`

## pseudocode

```c
__int64 __fastcall RfspThreadPoolNodeCreateWorker(__int64 a1)
{
  struct _EX_RUNDOWN_REF *v1; // r14
  __int64 Pool2; // rax
  void *v5; // rdi
  int v6; // esi
  _QWORD *v7; // rcx
  _QWORD v8[4]; // [rsp+40h] [rbp-30h] BYREF
  __int128 v9; // [rsp+60h] [rbp-10h]
  HANDLE Handle; // [rsp+90h] [rbp+20h] BYREF

  v1 = (struct _EX_RUNDOWN_REF *)(a1 + 208);
  Handle = 0;
  if ( !ExAcquireRundownProtection((PEX_RUNDOWN_REF)(a1 + 208)) )
    return 3221226238LL;
  Pool2 = ExAllocatePool2(66, 32, 1382437708);
  v5 = (void *)Pool2;
  if ( !Pool2 )
  {
    v6 = -1073741670;
LABEL_5:
    ExReleaseRundownProtection(v1);
    return (unsigned int)v6;
  }
  *(_QWORD *)(Pool2 + 16) = a1;
  *(_QWORD *)(Pool2 + 24) = 0;
  _InterlockedIncrement16((volatile signed __int16 *)(a1 + 64));
  v7 = *(_QWORD **)(a1 + 216);
  v8[1] = 0;
  v8[2] = 0;
  v8[0] = 48;
  v8[3] = 512;
  v9 = 0;
  v6 = ((__int64 (__fastcall *)(_QWORD, HANDLE *, __int64, _QWORD *, _QWORD, _QWORD, void (__fastcall *)(__int64 *), __int64))IoCreateSystemThread)(
         *v7,
         &Handle,
         0x1FFFFF,
         v8,
         0,
         0,
         RfspThreadPoolNodeWorkerRun,
         Pool2);
  if ( v6 < 0 )
  {
    Handle = 0;
    _InterlockedDecrement16((volatile signed __int16 *)(a1 + 64));
    ExFreePoolWithTag(v5, 0x5266534Cu);
    goto LABEL_5;
  }
  ZwClose(Handle);
  return 0;
}

```

## disassembly

```asm
0x14008bd54  mov     [rsp-18h+arg_8], rbx
0x14008bd59  mov     [rsp-18h+arg_10], rsi
0x14008bd5e  push    rbp
0x14008bd5f  push    rdi
0x14008bd60  push    r14
0x14008bd62  mov     rbp, rsp
0x14008bd65  sub     rsp, 70h
0x14008bd69  lea     r14, [rcx+0D0h]
0x14008bd70  mov     [rbp+Handle], 0
0x14008bd78  mov     rbx, rcx
0x14008bd7b  mov     rcx, r14; RunRef
0x14008bd7e  call    cs:__imp_ExAcquireRundownProtection
0x14008bd85  nop     dword ptr [rax+rax+00h]
0x14008bd8a  test    al, al
0x14008bd8c  jnz     short loc_14008BDA9
0x14008bd8e  mov     eax, 0C00002FEh
0x14008bd93  lea     r11, [rsp+70h+var_s0]
0x14008bd98  mov     rbx, [r11+28h]
0x14008bd9c  mov     rsi, [r11+30h]
0x14008bda0  mov     rsp, r11
0x14008bda3  pop     r14
0x14008bda5  pop     rdi
0x14008bda6  pop     rbp
0x14008bda7  retn
0x14008bda9  mov     edx, 20h ; ' '
0x14008bdae  mov     r8d, 5266534Ch
0x14008bdb4  lea     ecx, [rdx+22h]
0x14008bdb7  call    cs:__imp_ExAllocatePool2
0x14008bdbe  nop     dword ptr [rax+rax+00h]
0x14008bdc3  mov     rdi, rax
0x14008bdc6  test    rax, rax
0x14008bdc9  jnz     short loc_14008BDE3
0x14008bdcb  mov     esi, 0C000009Ah
0x14008bdd0  mov     rcx, r14; RunRef
0x14008bdd3  call    cs:__imp_ExReleaseRundownProtection
0x14008bdda  nop     dword ptr [rax+rax+00h]
0x14008bddf  mov     eax, esi
0x14008bde1  jmp     short loc_14008BD93
0x14008bde3  mov     [rax+10h], rbx
0x14008bde7  mov     qword ptr [rax+18h], 0
0x14008bdef  lock inc word ptr [rbx+40h]
0x14008bdf4  mov     rcx, [rbx+0D8h]
0x14008bdfb  lea     r9, [rbp+var_30]
0x14008bdff  xor     eax, eax
0x14008be01  mov     [rsp+70h+var_38], rdi
0x14008be06  mov     [rbp+var_28], rax
0x14008be0a  lea     rdx, [rbp+Handle]
0x14008be0e  mov     [rbp+var_20], rax
0x14008be12  xorps   xmm0, xmm0
0x14008be15  lea     rax, RfspThreadPoolNodeWorkerRun
0x14008be1c  mov     [rbp+var_30], 30h ; '0'
0x14008be24  mov     [rsp+70h+var_40], rax
0x14008be29  mov     r8d, 1FFFFFh
0x14008be2f  mov     [rbp+var_18], 200h
0x14008be37  movdqu  [rbp+var_10], xmm0
0x14008be3c  mov     rcx, [rcx]
0x14008be3f  mov     [rsp+70h+var_48], 0
0x14008be48  mov     [rsp+70h+var_50], 0
0x14008be51  call    cs:__imp_IoCreateSystemThread
0x14008be58  nop     dword ptr [rax+rax+00h]
0x14008be5d  mov     esi, eax
0x14008be5f  test    eax, eax
0x14008be61  jns     short loc_14008BE89
0x14008be63  mov     [rbp+Handle], 0
0x14008be6b  mov     edx, 5266534Ch; Tag
0x14008be70  lock dec word ptr [rbx+40h]
0x14008be75  mov     rcx, rdi; P
0x14008be78  call    cs:__imp_ExFreePoolWithTag
0x14008be7f  nop     dword ptr [rax+rax+00h]
0x14008be84  jmp     loc_14008BDD0
0x14008be89  mov     rcx, [rbp+Handle]; Handle
0x14008be8d  call    cs:__imp_ZwClose
0x14008be94  nop     dword ptr [rax+rax+00h]
0x14008be99  xor     eax, eax
0x14008be9b  jmp     loc_14008BD93
```
