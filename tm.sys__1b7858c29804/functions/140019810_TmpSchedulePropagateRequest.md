# TmpSchedulePropagateRequest

- ea: `0x140019810`
- end: `0x1400198a2`
- name: `TmpSchedulePropagateRequest`
- size: `146`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001904c`

## callees

- `0x14000cfa8`
- `0x140019810`

## import_xrefs

- `ntoskrnl!KeSetTimer` at `0x14001988a`
- `ntoskrnl!KeSetTimer` at `0x14001988a`
- `ntoskrnl!KeCancelTimer` at `0x14001982c`
- `ntoskrnl!KeCancelTimer` at `0x14001982c`
- `ntoskrnl!KeRemoveQueueDpc` at `0x140019844`
- `ntoskrnl!KeRemoveQueueDpc` at `0x140019844`

## pseudocode

```c
BOOLEAN __fastcall TmpSchedulePropagateRequest(char *P)
{
  struct _KTIMER *v2; // rsi
  BOOLEAN v3; // bl
  BOOLEAN v4; // r14

  _InterlockedIncrement((volatile signed __int32 *)P + 2);
  v2 = (struct _KTIMER *)(P + 264);
  v3 = KeCancelTimer((PKTIMER)(P + 264));
  v4 = KeRemoveQueueDpc((PRKDPC)(P + 200));
  if ( v3 )
    TmpDereferencePropagateRequest(P);
  if ( v4 )
    TmpDereferencePropagateRequest(P);
  *((_QWORD *)P + 41) = MEMORY[0xFFFFF78000000014];
  return KeSetTimer(v2, (LARGE_INTEGER)-900000000LL, (PKDPC)(P + 200));
}

```

## disassembly

```asm
0x140019810  push    rbx
0x140019812  push    rbp
0x140019813  push    rsi
0x140019814  push    rdi
0x140019815  push    r14
0x140019817  sub     rsp, 20h
0x14001981b  mov     rdi, rcx
0x14001981e  lock inc dword ptr [rcx+8]
0x140019822  lea     rsi, [rcx+108h]
0x140019829  mov     rcx, rsi; PKTIMER
0x14001982c  call    cs:__imp_KeCancelTimer
0x140019833  nop     dword ptr [rax+rax+00h]
0x140019838  lea     rbp, [rdi+0C8h]
0x14001983f  mov     bl, al
0x140019841  mov     rcx, rbp; Dpc
0x140019844  call    cs:__imp_KeRemoveQueueDpc
0x14001984b  nop     dword ptr [rax+rax+00h]
0x140019850  mov     r14b, al
0x140019853  test    bl, bl
0x140019855  jz      short loc_14001985F
0x140019857  mov     rcx, rdi; P
0x14001985a  call    TmpDereferencePropagateRequest
0x14001985f  test    r14b, r14b
0x140019862  jz      short loc_14001986C
0x140019864  mov     rcx, rdi; P
0x140019867  call    TmpDereferencePropagateRequest
0x14001986c  mov     rax, ds:0FFFFF78000000014h
0x140019876  mov     r8, rbp; Dpc
0x140019879  mov     rdx, 0FFFFFFFFCA5B1700h; DueTime
0x140019880  mov     [rdi+148h], rax
0x140019887  mov     rcx, rsi; Timer
0x14001988a  call    cs:__imp_KeSetTimer
0x140019891  nop     dword ptr [rax+rax+00h]
0x140019896  add     rsp, 20h
0x14001989a  pop     r14
0x14001989c  pop     rdi
0x14001989d  pop     rsi
0x14001989e  pop     rbp
0x14001989f  pop     rbx
0x1400198a0  retn
```
