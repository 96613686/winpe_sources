# PipeUnlockAndSendInterrupt

- ea: `0x140002d20`
- end: `0x140002e0b`
- name: `PipeUnlockAndSendInterrupt`
- size: `235`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140002380`
- `0x140002f04`
- `0x1400030fc`
- `0x140015a60`

## callees

- `0x140002d20`
- `0x140002e70`
- `0x140015a14`
- `0x14001661c`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002d5e`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002d5e`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140002d80`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140002d80`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002da3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002dbb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002df3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002da3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002dbb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002df3`
- `vmbkmcl!VmbChannelSendInterrupt` at `0x140002d71`
- `vmbkmcl!VmbChannelSendInterrupt` at `0x140002dce`
- `vmbkmcl!VmbChannelSendInterrupt` at `0x140002d71`
- `vmbkmcl!VmbChannelSendInterrupt` at `0x140002dce`

## pseudocode

```c
void __fastcall PipeUnlockAndSendInterrupt(KSPIN_LOCK *SpinLock, KIRQL a2, char a3, char a4)
{
  char v6; // di
  _QWORD *v7[3]; // [rsp+20h] [rbp-18h] BYREF

  if ( a3 )
  {
    ++*((_DWORD *)SpinLock + 69);
    v7[1] = v7;
    v7[0] = v7;
    if ( a4 )
    {
      KeReleaseSpinLockFromDpcLevel(SpinLock);
      VmbChannelSendInterrupt(SpinLock[32]);
      KeAcquireSpinLockAtDpcLevel(SpinLock);
      v6 = PipeProcessDeferredReadWrite((__int64)SpinLock, (__int64)v7);
      KeReleaseSpinLock(SpinLock, a2);
      if ( !v6 )
        goto LABEL_7;
    }
    else
    {
      KeReleaseSpinLock(SpinLock, a2);
    }
    VmbChannelSendInterrupt(SpinLock[32]);
LABEL_7:
    PipeCompleteChannelHold((__int64)SpinLock);
    PipeCompleteIrpList(v7);
    return;
  }
  KeReleaseSpinLock(SpinLock, a2);
}

```

## disassembly

```asm
0x140002d20  mov     r11, rsp
0x140002d23  mov     [r11+18h], rbx
0x140002d27  push    rsi
0x140002d28  sub     rsp, 30h
0x140002d2c  movzx   esi, dl
0x140002d2f  mov     rbx, rcx
0x140002d32  test    r8b, r8b
0x140002d35  jz      loc_140002DF3
0x140002d3b  inc     dword ptr [rcx+114h]
0x140002d41  lea     rax, [r11-18h]
0x140002d45  mov     [r11-10h], rax
0x140002d49  lea     rax, [r11-18h]
0x140002d4d  mov     [r11-18h], rax
0x140002d51  mov     [r11+10h], r14
0x140002d55  test    r9b, r9b
0x140002d58  jz      short loc_140002DBB
0x140002d5a  mov     [r11+8], rdi
0x140002d5e  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140002d65  nop     dword ptr [rax+rax+00h]
0x140002d6a  mov     rcx, [rbx+100h]
0x140002d71  call    cs:__imp_VmbChannelSendInterrupt
0x140002d78  nop     dword ptr [rax+rax+00h]
0x140002d7d  mov     rcx, rbx; SpinLock
0x140002d80  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140002d87  nop     dword ptr [rax+rax+00h]
0x140002d8c  lea     rdx, [rsp+38h+var_18]
0x140002d91  mov     rcx, rbx
0x140002d94  call    PipeProcessDeferredReadWrite
0x140002d99  movzx   edx, sil; NewIrql
0x140002d9d  mov     rcx, rbx; SpinLock
0x140002da0  movzx   edi, al
0x140002da3  call    cs:__imp_KeReleaseSpinLock
0x140002daa  nop     dword ptr [rax+rax+00h]
0x140002daf  test    dil, dil
0x140002db2  mov     rdi, [rsp+38h+arg_0]
0x140002db7  jnz     short loc_140002DC7
0x140002db9  jmp     short loc_140002DDA
0x140002dbb  call    cs:__imp_KeReleaseSpinLock
0x140002dc2  nop     dword ptr [rax+rax+00h]
0x140002dc7  mov     rcx, [rbx+100h]
0x140002dce  call    cs:__imp_VmbChannelSendInterrupt
0x140002dd5  nop     dword ptr [rax+rax+00h]
0x140002dda  mov     rcx, rbx
0x140002ddd  call    PipeCompleteChannelHold
0x140002de2  lea     rcx, [rsp+38h+var_18]
0x140002de7  call    PipeCompleteIrpList
0x140002dec  mov     r14, [rsp+38h+arg_8]
0x140002df1  jmp     short loc_140002DFF
0x140002df3  call    cs:__imp_KeReleaseSpinLock
0x140002dfa  nop     dword ptr [rax+rax+00h]
0x140002dff  mov     rbx, [rsp+38h+arg_10]
0x140002e04  add     rsp, 30h
0x140002e08  pop     rsi
0x140002e09  retn
```
