# TmIsKTMCommitCoordinatorExt

- ea: `0x140010c10`
- end: `0x140010c63`
- name: `TmIsKTMCommitCoordinatorExt`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14001b338`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x140010c49`
- `ntoskrnl!KeReleaseMutex` at `0x140010c49`

## pseudocode

```c
bool __fastcall TmIsKTMCommitCoordinatorExt(__int64 a1)
{
  __int64 v2; // rax
  bool v3; // bl

  TmpAcquireTransactionMutex(a1);
  v2 = *(_QWORD *)(a1 + 88);
  v3 = 0;
  if ( (*(_DWORD *)(v2 + 196) & 0x400) == 0 )
    v3 = *(_QWORD *)(v2 + 240) == 0;
  KeReleaseMutex((PRKMUTEX)(*(_QWORD *)(a1 + 88) + 32LL), 0);
  return v3;
}

```

## disassembly

```asm
0x140010c10  mov     [rsp+arg_0], rbx
0x140010c15  push    rdi
0x140010c16  sub     rsp, 20h
0x140010c1a  mov     rdi, rcx
0x140010c1d  call    TmpAcquireTransactionMutex
0x140010c22  mov     rax, [rdi+58h]
0x140010c26  xor     ebx, ebx
0x140010c28  cmp     [rax+0F0h], rbx
0x140010c2f  mov     eax, [rax+0C4h]
0x140010c35  mov     rcx, [rdi+58h]
0x140010c39  setz    dl
0x140010c3c  bt      eax, 0Ah
0x140010c40  cmovnb  ebx, edx
0x140010c43  add     rcx, 20h ; ' '; Mutex
0x140010c47  xor     edx, edx; Wait
0x140010c49  call    cs:__imp_KeReleaseMutex
0x140010c50  nop     dword ptr [rax+rax+00h]
0x140010c55  mov     al, bl
0x140010c57  mov     rbx, [rsp+28h+arg_0]
0x140010c5c  add     rsp, 20h
0x140010c60  pop     rdi
0x140010c61  retn
```
