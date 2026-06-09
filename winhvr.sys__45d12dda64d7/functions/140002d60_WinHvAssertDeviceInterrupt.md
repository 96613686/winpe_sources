# WinHvAssertDeviceInterrupt

- ea: `0x140002d60`
- end: `0x140002f1b`
- name: `WinHvAssertDeviceInterrupt`
- size: `443`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x140002d60`
- `0x140009c90`
- `0x14000a040`
- `0x14001b350`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140002ea5`
- `ntoskrnl!KeGetCurrentIrql` at `0x140002ea5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140002db2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140002db2`
- `ntoskrnl!ExAcquireFastMutex` at `0x140002ec0`
- `ntoskrnl!ExAcquireFastMutex` at `0x140002ec0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002edc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002edc`
- `ntoskrnl!HvlInvokeHypercall` at `0x140002e45`
- `ntoskrnl!HvlInvokeHypercall` at `0x140002e45`

## pseudocode

```c
__int64 __fastcall WinHvAssertDeviceInterrupt(__int64 a1, __int64 a2, _OWORD *a3)
{
  __int64 LockArray_high; // r9
  __int64 *v7; // rax
  __int64 v8; // rax
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned __int16 v12; // ax
  unsigned int v13; // ebx
  _QWORD v15[13]; // [rsp+30h] [rbp-68h] BYREF

  memset(v15, 0, 0x40u);
  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  v15[5] = 0;
  LOWORD(v15[4]) = *(_WORD *)(WinHvpProcessorToNode + 2 * LockArray_high);
  v7 = (__int64 *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(WinHvpNodeToHypercallLookaside
                                                                           + ((unsigned __int64)LOWORD(v15[4]) << 7)));
  v15[5] = v7;
  v15[7] = WinHvpReleasePoolBuffers;
  if ( !v7 )
  {
    LOBYTE(v15[6]) = KeGetCurrentIrql();
    if ( LOBYTE(v15[6]) >= 2u )
    {
      LOBYTE(v15[6]) = KeAcquireSpinLockRaiseToDpc(&WinHvpFallbackSpinLock);
      v7 = WinHvpFallbackBuffer;
    }
    else
    {
      ExAcquireFastMutex(&WinHvpFallbackMutex);
      v7 = WinHvpFallbackBuffer2;
    }
    v15[5] = v7;
    v15[7] = WinHvpReleaseFallbackBuffers;
  }
  v8 = v7[2];
  v15[1] = v8;
  v15[0] = v15;
  v15[2] = 0;
  *(_QWORD *)v8 = a1;
  *(_QWORD *)(v8 + 8) = a2;
  *(_OWORD *)(v8 + 16) = *a3;
  if ( *(_BYTE *)(v15[0] + 24LL) )
  {
    v13 = WinHvpSlowHypercallRemote(128, 0, *(_QWORD *)(v15[0] + 8LL), *(_QWORD *)(v15[0] + 16LL), 0);
  }
  else
  {
    if ( *(_QWORD *)(v15[0] + 16LL) )
      v9 = *(_QWORD *)(*(_QWORD *)(v15[0] + 40LL) + 40LL);
    else
      v9 = 0;
    if ( *(_QWORD *)(v15[0] + 8LL) )
      v10 = *(_QWORD *)(*(_QWORD *)(v15[0] + 40LL) + 24LL);
    else
      v10 = 0;
    v11 = 128;
    if ( WinHvpNested )
      v11 = 2147483776LL;
    if ( WinHvpConnected )
    {
      v12 = HvlInvokeHypercall(v11, v10, v9);
      if ( v12 )
        v13 = v12 | 0xC0350000;
      else
        v13 = 0;
    }
    else
    {
      v13 = -1070264320;
    }
  }
  ((void (__fastcall *)(_QWORD))v15[7])(v15[0]);
  return v13;
}

```

## disassembly

```asm
0x140002d60  push    rbx
0x140002d62  push    rbp
0x140002d63  push    rsi
0x140002d64  push    rdi
0x140002d65  sub     rsp, 78h
0x140002d69  mov     rbx, r8
0x140002d6c  mov     rdi, rdx
0x140002d6f  mov     rsi, rcx
0x140002d72  xor     edx, edx; Val
0x140002d74  mov     r8d, 40h ; '@'; Size
0x140002d7a  lea     rcx, [rsp+98h+var_68]; void *
0x140002d7f  call    memset
0x140002d84  mov     eax, gs:1A4h
0x140002d8c  xor     ebp, ebp
0x140002d8e  mov     r9d, eax
0x140002d91  mov     rax, cs:WinHvpProcessorToNode
0x140002d98  mov     [rsp+98h+var_40], rbp
0x140002d9d  movzx   ecx, word ptr [rax+r9*2]
0x140002da2  mov     [rsp+98h+var_48], cx
0x140002da7  shl     rcx, 7
0x140002dab  add     rcx, cs:WinHvpNodeToHypercallLookaside; Lookaside
0x140002db2  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140002db9  nop     dword ptr [rax+rax+00h]
0x140002dbe  mov     [rsp+98h+var_40], rax
0x140002dc3  lea     rcx, WinHvpReleasePoolBuffers
0x140002dca  mov     [rsp+98h+var_30], rcx
0x140002dcf  test    rax, rax
0x140002dd2  jz      loc_140002EA5
0x140002dd8  mov     rax, [rax+10h]
0x140002ddc  lea     rcx, [rsp+98h+var_68]
0x140002de1  mov     [rsp+98h+var_60], rax
0x140002de6  mov     [rsp+98h+var_68], rcx
0x140002deb  mov     [rsp+98h+var_58], rbp
0x140002df0  mov     [rax], rsi
0x140002df3  mov     [rax+8], rdi
0x140002df7  movups  xmm0, xmmword ptr [rbx]
0x140002dfa  movups  xmmword ptr [rax+10h], xmm0
0x140002dfe  mov     rax, [rsp+98h+var_68]
0x140002e03  cmp     [rax+18h], bpl
0x140002e07  jnz     short loc_140002E7D
0x140002e09  cmp     [rax+10h], rbp
0x140002e0d  jnz     short loc_140002E73
0x140002e0f  mov     r8, rbp
0x140002e12  cmp     [rax+8], rbp
0x140002e16  jz      loc_140002F09
0x140002e1c  mov     rdx, [rax+28h]
0x140002e20  mov     rdx, [rdx+18h]
0x140002e24  cmp     cs:WinHvpNested, bpl
0x140002e2b  mov     ecx, 80h
0x140002e30  mov     eax, 80000080h
0x140002e35  cmovnz  ecx, eax
0x140002e38  cmp     cs:WinHvpConnected, bpl
0x140002e3f  jz      loc_140002F11
0x140002e45  call    cs:__imp_HvlInvokeHypercall
0x140002e4c  nop     dword ptr [rax+rax+00h]
0x140002e51  test    ax, ax
0x140002e54  jnz     short loc_140002E9A
0x140002e56  mov     ebx, ebp
0x140002e58  mov     rcx, [rsp+98h+var_68]
0x140002e5d  mov     rax, [rsp+98h+var_30]
0x140002e62  call    _guard_dispatch_icall
0x140002e67  mov     eax, ebx
0x140002e69  add     rsp, 78h
0x140002e6d  pop     rdi
0x140002e6e  pop     rsi
0x140002e6f  pop     rbp
0x140002e70  pop     rbx
0x140002e71  retn
0x140002e73  mov     r8, [rax+28h]
0x140002e77  mov     r8, [r8+28h]
0x140002e7b  jmp     short loc_140002E12
0x140002e7d  mov     r9, [rax+10h]
0x140002e81  xor     edx, edx
0x140002e83  mov     r8, [rax+8]
0x140002e87  mov     ecx, 80h
0x140002e8c  mov     [rsp+98h+var_78], rbp
0x140002e91  call    WinHvpSlowHypercallRemote
0x140002e96  mov     ebx, eax
0x140002e98  jmp     short loc_140002E58
0x140002e9a  movzx   ebx, ax
0x140002e9d  or      ebx, 0C0350000h
0x140002ea3  jmp     short loc_140002E58
0x140002ea5  call    cs:__imp_KeGetCurrentIrql
0x140002eac  nop     dword ptr [rax+rax+00h]
0x140002eb1  mov     [rsp+98h+var_38], al
0x140002eb5  cmp     al, 2
0x140002eb7  jnb     short loc_140002ED5
0x140002eb9  lea     rcx, WinHvpFallbackMutex; FastMutex
0x140002ec0  call    cs:__imp_ExAcquireFastMutex
0x140002ec7  nop     dword ptr [rax+rax+00h]
0x140002ecc  lea     rax, WinHvpFallbackBuffer2
0x140002ed3  jmp     short loc_140002EF3
0x140002ed5  lea     rcx, WinHvpFallbackSpinLock; SpinLock
0x140002edc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002ee3  nop     dword ptr [rax+rax+00h]
0x140002ee8  mov     [rsp+98h+var_38], al
0x140002eec  lea     rax, WinHvpFallbackBuffer
0x140002ef3  lea     rcx, WinHvpReleaseFallbackBuffers
0x140002efa  mov     [rsp+98h+var_40], rax
0x140002eff  mov     [rsp+98h+var_30], rcx
0x140002f04  jmp     loc_140002DD8
0x140002f09  mov     rdx, rbp
0x140002f0c  jmp     loc_140002E24
0x140002f11  mov     ebx, 0C0351000h
0x140002f16  jmp     loc_140002E58
```
