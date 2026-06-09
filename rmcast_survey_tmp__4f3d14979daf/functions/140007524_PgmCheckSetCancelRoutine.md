# PgmCheckSetCancelRoutine

- ea: `0x140007524`
- end: `0x14000759f`
- name: `PgmCheckSetCancelRoutine`
- size: `123`
- prototype: `__int64 __fastcall(__int64, __int64, char)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140006998`
- `0x14001013c`
- `0x140011904`
- `0x140019424`

## callees

- `0x140007524`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140007580`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140007580`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14000754a`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14000754a`

## pseudocode

```c
__int64 __fastcall PgmCheckSetCancelRoutine(__int64 a1, __int64 a2, char a3)
{
  unsigned int v6; // edi
  KIRQL Irql; // [rsp+40h] [rbp+18h] BYREF

  Irql = 0;
  if ( !a3 )
    IoAcquireCancelSpinLock(&Irql);
  if ( *(_BYTE *)(a1 + 68) )
  {
    v6 = -1073741536;
    *(_DWORD *)(a1 + 48) = -1073741536;
  }
  else
  {
    *(_BYTE *)(*(_QWORD *)(a1 + 184) + 3LL) |= 1u;
    _InterlockedExchange64((volatile __int64 *)(a1 + 104), a2);
    v6 = 0;
  }
  if ( !a3 )
    IoReleaseCancelSpinLock(Irql);
  return v6;
}

```

## disassembly

```asm
0x140007524  mov     rax, rsp
0x140007527  mov     [rax+8], rbx
0x14000752b  mov     [rax+10h], rsi
0x14000752f  push    rdi
0x140007530  sub     rsp, 20h
0x140007534  mov     byte ptr [rax+18h], 0
0x140007538  mov     sil, r8b
0x14000753b  mov     rdi, rdx
0x14000753e  mov     rbx, rcx
0x140007541  test    r8b, r8b
0x140007544  jnz     short loc_140007556
0x140007546  lea     rcx, [rax+18h]; Irql
0x14000754a  call    cs:__imp_IoAcquireCancelSpinLock
0x140007551  nop     dword ptr [rax+rax+00h]
0x140007556  cmp     byte ptr [rbx+44h], 0
0x14000755a  jz      short loc_140007566
0x14000755c  mov     edi, 0C0000120h
0x140007561  mov     [rbx+30h], edi
0x140007564  jmp     short loc_140007577
0x140007566  mov     rax, [rbx+0B8h]
0x14000756d  or      byte ptr [rax+3], 1
0x140007571  xchg    rdi, [rbx+68h]
0x140007575  xor     edi, edi
0x140007577  test    sil, sil
0x14000757a  jnz     short loc_14000758C
0x14000757c  mov     cl, [rsp+28h+Irql]; Irql
0x140007580  call    cs:__imp_IoReleaseCancelSpinLock
0x140007587  nop     dword ptr [rax+rax+00h]
0x14000758c  mov     rbx, [rsp+28h+arg_0]
0x140007591  mov     eax, edi
0x140007593  mov     rsi, [rsp+28h+arg_8]
0x140007598  add     rsp, 20h
0x14000759c  pop     rdi
0x14000759d  retn
```
