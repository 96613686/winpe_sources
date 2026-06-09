# PgmCancelCancelRoutine

- ea: `0x1400074c8`
- end: `0x14000751c`
- name: `PgmCancelCancelRoutine`
- size: `84`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x140006998`
- `0x14000738c`
- `0x140007f1c`
- `0x14000cf04`
- `0x14001013c`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140007502`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140007502`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400074df`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400074df`

## pseudocode

```c
__int64 __fastcall PgmCancelCancelRoutine(__int64 a1)
{
  int v2; // ebx
  KIRQL Irql; // [rsp+30h] [rbp+8h] BYREF

  Irql = 0;
  IoAcquireCancelSpinLock(&Irql);
  v2 = -(*(_BYTE *)(a1 + 68) != 0);
  _InterlockedExchange64((volatile __int64 *)(a1 + 104), 0);
  IoReleaseCancelSpinLock(Irql);
  return v2 & 0xC0000120;
}

```

## disassembly

```asm
0x1400074c8  mov     [rsp+arg_8], rbx
0x1400074cd  push    rdi
0x1400074ce  sub     rsp, 20h
0x1400074d2  mov     rdi, rcx
0x1400074d5  mov     [rsp+28h+Irql], 0
0x1400074da  lea     rcx, [rsp+28h+Irql]; Irql
0x1400074df  call    cs:__imp_IoAcquireCancelSpinLock
0x1400074e6  nop     dword ptr [rax+rax+00h]
0x1400074eb  mov     al, [rdi+44h]
0x1400074ee  neg     al
0x1400074f0  sbb     ebx, ebx
0x1400074f2  xor     edx, edx
0x1400074f4  xchg    rdx, [rdi+68h]
0x1400074f8  mov     cl, [rsp+28h+Irql]; Irql
0x1400074fc  and     ebx, 0C0000120h
0x140007502  call    cs:__imp_IoReleaseCancelSpinLock
0x140007509  nop     dword ptr [rax+rax+00h]
0x14000750e  mov     eax, ebx
0x140007510  mov     rbx, [rsp+28h+arg_8]
0x140007515  add     rsp, 20h
0x140007519  pop     rdi
0x14000751a  retn
```
