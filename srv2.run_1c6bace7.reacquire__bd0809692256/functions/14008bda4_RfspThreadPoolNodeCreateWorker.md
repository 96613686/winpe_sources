# RfspThreadPoolNodeCreateWorker

- ea: `0x14008bda4`
- end: `0x14008bef0`
- name: `RfspThreadPoolNodeCreateWorker`
- size: `332`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14008bc70`
- `0x140091ebc`

## callees

- `0x14008bda4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14008be07`
- `ntoskrnl!ExAllocatePool2` at `0x14008be07`
- `ntoskrnl!ZwClose` at `0x14008bedd`
- `ntoskrnl!ZwClose` at `0x14008bedd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008bec8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008bec8`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14008bdce`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14008bdce`
- `ntoskrnl!IoCreateSystemThread` at `0x14008bea1`
- `ntoskrnl!IoCreateSystemThread` at `0x14008bea1`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14008be23`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14008be23`

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
0x14008bda4  mov     [rsp-18h+arg_8], rbx
0x14008bda9  mov     [rsp-18h+arg_10], rsi
0x14008bdae  push    rbp
0x14008bdaf  push    rdi
0x14008bdb0  push    r14
0x14008bdb2  mov     rbp, rsp
0x14008bdb5  sub     rsp, 70h
0x14008bdb9  lea     r14, [rcx+0D0h]
0x14008bdc0  mov     [rbp+Handle], 0
0x14008bdc8  mov     rbx, rcx
0x14008bdcb  mov     rcx, r14; RunRef
0x14008bdce  call    cs:__imp_ExAcquireRundownProtection
0x14008bdd5  nop     dword ptr [rax+rax+00h]
0x14008bdda  test    al, al
0x14008bddc  jnz     short loc_14008BDF9
0x14008bdde  mov     eax, 0C00002FEh
0x14008bde3  lea     r11, [rsp+70h+var_s0]
0x14008bde8  mov     rbx, [r11+28h]
0x14008bdec  mov     rsi, [r11+30h]
0x14008bdf0  mov     rsp, r11
0x14008bdf3  pop     r14
0x14008bdf5  pop     rdi
0x14008bdf6  pop     rbp
0x14008bdf7  retn
0x14008bdf9  mov     edx, 20h ; ' '
0x14008bdfe  mov     r8d, 5266534Ch
0x14008be04  lea     ecx, [rdx+22h]
0x14008be07  call    cs:__imp_ExAllocatePool2
0x14008be0e  nop     dword ptr [rax+rax+00h]
0x14008be13  mov     rdi, rax
0x14008be16  test    rax, rax
0x14008be19  jnz     short loc_14008BE33
0x14008be1b  mov     esi, 0C000009Ah
0x14008be20  mov     rcx, r14; RunRef
0x14008be23  call    cs:__imp_ExReleaseRundownProtection
0x14008be2a  nop     dword ptr [rax+rax+00h]
0x14008be2f  mov     eax, esi
0x14008be31  jmp     short loc_14008BDE3
0x14008be33  mov     [rax+10h], rbx
0x14008be37  mov     qword ptr [rax+18h], 0
0x14008be3f  lock inc word ptr [rbx+40h]
0x14008be44  mov     rcx, [rbx+0D8h]
0x14008be4b  lea     r9, [rbp+var_30]
0x14008be4f  xor     eax, eax
0x14008be51  mov     [rsp+70h+var_38], rdi
0x14008be56  mov     [rbp+var_28], rax
0x14008be5a  lea     rdx, [rbp+Handle]
0x14008be5e  mov     [rbp+var_20], rax
0x14008be62  xorps   xmm0, xmm0
0x14008be65  lea     rax, RfspThreadPoolNodeWorkerRun
0x14008be6c  mov     [rbp+var_30], 30h ; '0'
0x14008be74  mov     [rsp+70h+var_40], rax
0x14008be79  mov     r8d, 1FFFFFh
0x14008be7f  mov     [rbp+var_18], 200h
0x14008be87  movdqu  [rbp+var_10], xmm0
0x14008be8c  mov     rcx, [rcx]
0x14008be8f  mov     [rsp+70h+var_48], 0
0x14008be98  mov     [rsp+70h+var_50], 0
0x14008bea1  call    cs:__imp_IoCreateSystemThread
0x14008bea8  nop     dword ptr [rax+rax+00h]
0x14008bead  mov     esi, eax
0x14008beaf  test    eax, eax
0x14008beb1  jns     short loc_14008BED9
0x14008beb3  mov     [rbp+Handle], 0
0x14008bebb  mov     edx, 5266534Ch; Tag
0x14008bec0  lock dec word ptr [rbx+40h]
0x14008bec5  mov     rcx, rdi; P
0x14008bec8  call    cs:__imp_ExFreePoolWithTag
0x14008becf  nop     dword ptr [rax+rax+00h]
0x14008bed4  jmp     loc_14008BE20
0x14008bed9  mov     rcx, [rbp+Handle]; Handle
0x14008bedd  call    cs:__imp_ZwClose
0x14008bee4  nop     dword ptr [rax+rax+00h]
0x14008bee9  xor     eax, eax
0x14008beeb  jmp     loc_14008BDE3
```
