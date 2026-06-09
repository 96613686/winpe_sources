# SqospTryAcquireDeviceLock

- ea: `0x140004640`
- end: `0x1400046c0`
- name: `SqospTryAcquireDeviceLock`
- size: `128`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140001010`
- `0x1400011c0`
- `0x140002300`

## callees

- `0x140004640`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14000466c`
- `ntoskrnl!KfRaiseIrql` at `0x14000466c`
- `ntoskrnl!KeLowerIrql` at `0x1400046a1`
- `ntoskrnl!KeLowerIrql` at `0x1400046a1`
- `ntoskrnl!KeTryToAcquireSpinLockAtDpcLevel` at `0x140004682`
- `ntoskrnl!KeTryToAcquireSpinLockAtDpcLevel` at `0x140004682`

## pseudocode

```c
char __fastcall SqospTryAcquireDeviceLock(__int64 a1)
{
  KIRQL v3; // si

  if ( *(_DWORD *)(a1 + 832) )
    return 0;
  v3 = KfRaiseIrql(2u);
  if ( KeTryToAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a1 + 832)) )
  {
    *(_BYTE *)(a1 + 840) = v3;
    return 1;
  }
  else
  {
    KeLowerIrql(v3);
    return 0;
  }
}

```

## disassembly

```asm
0x140004640  mov     [rsp+arg_8], rbx
0x140004645  push    rdi
0x140004646  sub     rsp, 20h
0x14000464a  mov     eax, [rcx+340h]
0x140004650  mov     rbx, rcx
0x140004653  test    eax, eax
0x140004655  jz      short loc_140004665
0x140004657  xor     al, al
0x140004659  mov     rbx, [rsp+28h+arg_8]
0x14000465e  add     rsp, 20h
0x140004662  pop     rdi
0x140004663  retn
0x140004665  mov     cl, 2; NewIrql
0x140004667  mov     [rsp+28h+arg_0], rsi
0x14000466c  call    cs:__imp_KfRaiseIrql
0x140004673  nop     dword ptr [rax+rax+00h]
0x140004678  lea     rcx, [rbx+340h]; SpinLock
0x14000467f  movzx   esi, al
0x140004682  call    cs:__imp_KeTryToAcquireSpinLockAtDpcLevel
0x140004689  nop     dword ptr [rax+rax+00h]
0x14000468e  test    al, al
0x140004690  jz      short loc_14000469D
0x140004692  mov     [rbx+348h], sil
0x140004699  mov     al, 1
0x14000469b  jmp     short loc_1400046AF
0x14000469d  movzx   ecx, sil; NewIrql
0x1400046a1  call    cs:__imp_KeLowerIrql
0x1400046a8  nop     dword ptr [rax+rax+00h]
0x1400046ad  xor     al, al
0x1400046af  mov     rsi, [rsp+28h+arg_0]
0x1400046b4  mov     rbx, [rsp+28h+arg_8]
0x1400046b9  add     rsp, 20h
0x1400046bd  pop     rdi
0x1400046be  retn
```
