# InpReleaseLockAndPerformWork

- ea: `0x140002190`
- end: `0x1400022ad`
- name: `InpReleaseLockAndPerformWork`
- size: `285`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x140001170`
- `0x140001370`
- `0x140001780`
- `0x140001ce0`
- `0x140004cc0`
- `0x1400081ec`
- `0x140008338`
- `0x1400086b0`

## callees

- `0x140002190`
- `0x140005250`
- `0x140011ed0`

## import_xrefs

- `ntoskrnl!KeInsertQueueDpc` at `0x140002272`
- `ntoskrnl!KeInsertQueueDpc` at `0x140002272`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400021bf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002231`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002250`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400021bf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002231`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002250`

## pseudocode

```c
void __fastcall InpReleaseLockAndPerformWork(KSPIN_LOCK *a1, KIRQL a2)
{
  struct _KDPC *v2; // rsi
  KIRQL v3; // di
  char v5; // bp
  KSPIN_LOCK v6; // r14
  char v7; // al
  KSPIN_LOCK *v8; // rcx

  v2 = (struct _KDPC *)a1[142];
  v3 = a2;
  if ( !v2 )
  {
    *((_BYTE *)a1 + 1100) = 0;
    KeReleaseSpinLock(a1 + 136, a2);
    return;
  }
  v5 = *((_BYTE *)a1 + 1100);
  a1[142] = 0;
  *((_BYTE *)a1 + 1100) = 0;
  if ( (v5 & 4) != 0 )
  {
    v6 = *a1;
    v7 = (*(__int64 (__fastcall **)(_QWORD))(*a1 + 2520))(*(_QWORD *)(*a1 + 2368));
    v8 = a1 + 136;
    a2 = v3;
    if ( v7 )
    {
      ++*(_QWORD *)(v6 + 1672);
      KeReleaseSpinLock(v8, v3);
      OutPollQueue(a1, 0);
      goto LABEL_8;
    }
  }
  else
  {
    v8 = a1 + 136;
  }
  KeReleaseSpinLock(v8, a2);
LABEL_8:
  if ( (v5 & 2) != 0 )
    (*(void (__fastcall **)(_QWORD, struct _KDPC *, __int64 (__fastcall *)(), KSPIN_LOCK *))(*a1 + 2528))(
      *(_QWORD *)(*a1 + 2368),
      v2,
      InpProcessingWorkerRoutine,
      a1);
  else
    KeInsertQueueDpc(v2, (PVOID)(v5 & 1), 0);
}

```

## disassembly

```asm
0x140002190  mov     [rsp+arg_10], rbx
0x140002195  mov     [rsp+arg_18], rsi
0x14000219a  push    rdi
0x14000219b  sub     rsp, 30h
0x14000219f  mov     rsi, [rcx+470h]
0x1400021a6  movzx   edi, dl
0x1400021a9  mov     rbx, rcx
0x1400021ac  test    rsi, rsi
0x1400021af  jnz     short loc_1400021DC
0x1400021b1  mov     [rcx+44Ch], sil
0x1400021b8  add     rcx, 440h; SpinLock
0x1400021bf  call    cs:__imp_KeReleaseSpinLock
0x1400021c6  nop     dword ptr [rax+rax+00h]
0x1400021cb  mov     rbx, [rsp+38h+arg_10]
0x1400021d0  mov     rsi, [rsp+38h+arg_18]
0x1400021d5  add     rsp, 30h
0x1400021d9  pop     rdi
0x1400021da  retn
0x1400021dc  mov     [rsp+38h+arg_0], rbp
0x1400021e1  movzx   ebp, byte ptr [rcx+44Ch]
0x1400021e8  mov     [rsp+38h+arg_8], r14
0x1400021ed  mov     qword ptr [rcx+470h], 0
0x1400021f8  mov     byte ptr [rcx+44Ch], 0
0x1400021ff  test    bpl, 4
0x140002203  jz      short loc_140002249
0x140002205  mov     r14, [rcx]
0x140002208  mov     rax, [r14+9D8h]
0x14000220f  mov     rcx, [r14+940h]
0x140002216  call    _guard_dispatch_icall
0x14000221b  lea     rcx, [rbx+440h]; SpinLock
0x140002222  movzx   edx, dil; NewIrql
0x140002226  test    al, al
0x140002228  jz      short loc_140002250
0x14000222a  inc     qword ptr [r14+688h]
0x140002231  call    cs:__imp_KeReleaseSpinLock
0x140002238  nop     dword ptr [rax+rax+00h]
0x14000223d  xor     edx, edx
0x14000223f  mov     rcx, rbx
0x140002242  call    OutPollQueue
0x140002247  jmp     short loc_14000225C
0x140002249  add     rcx, 440h; SpinLock
0x140002250  call    cs:__imp_KeReleaseSpinLock
0x140002257  nop     dword ptr [rax+rax+00h]
0x14000225c  mov     r14, [rsp+38h+arg_8]
0x140002261  test    bpl, 2
0x140002265  jnz     short loc_140002280
0x140002267  and     ebp, 1
0x14000226a  xor     r8d, r8d; SystemArgument2
0x14000226d  mov     edx, ebp; SystemArgument1
0x14000226f  mov     rcx, rsi; Dpc
0x140002272  call    cs:__imp_KeInsertQueueDpc
0x140002279  nop     dword ptr [rax+rax+00h]
0x14000227e  jmp     short loc_1400022A3
0x140002280  mov     rcx, [rbx]
0x140002283  lea     r8, InpProcessingWorkerRoutine
0x14000228a  mov     r9, rbx
0x14000228d  mov     rdx, rsi
0x140002290  mov     rax, [rcx+9E0h]
0x140002297  mov     rcx, [rcx+940h]
0x14000229e  call    _guard_dispatch_icall
0x1400022a3  mov     rbp, [rsp+38h+arg_0]
0x1400022a8  jmp     loc_1400021CB
```
