# Smb2CompleteChainedWrite

- ea: `0x140032f70`
- end: `0x140033034`
- name: `Smb2CompleteChainedWrite`
- size: `196`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140004960`
- `0x140005070`
- `0x140032f70`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140032fe5`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140032fe5`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140033001`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140033001`

## string_xrefs

- `0x140032fcc`: `Srv2PostToThreadPool`

## pseudocode

```c
__int64 __fastcall Smb2CompleteChainedWrite(__int64 a1, __int64 a2, __int64 a3)
{
  bool v4; // zf
  __int64 v5; // rbx
  __int64 v6; // rbx
  char v8; // [rsp+20h] [rbp-18h]

  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)(a3 + 560) + 276LL), 0xFFFFFFFF) == 1 )
  {
    v4 = *(_DWORD *)(a3 + 8) == 5;
    *(_QWORD *)(a3 + 88) = *(_QWORD *)(a3 + 48);
    *(_QWORD *)(a3 + 48) = Srv2PostOnCompletionAndClearCancelCallback;
    *(_DWORD *)(a3 + 72) = 0;
    if ( v4 )
    {
      v8 = 1;
      LOBYTE(a2) = 1;
      SRV2_PERF_ENTER_EX(a3 + 584, a2, 391, "Srv2PostToThreadPool", v8);
    }
    v5 = *(_QWORD *)(*(_QWORD *)(a3 + 64) + 136LL);
    v6 = *(_QWORD *)(v5 + 8LL * KeGetCurrentNodeNumber() + 8);
    if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v6 + 16), (PSLIST_ENTRY)(a3 + 32)) && *(_WORD *)(v6 + 66) )
      RfspThreadPoolNodeWakeIdleWorker((struct _KEVENT *)v6);
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x140032f70  mov     [rsp+arg_0], rbx
0x140032f75  push    rdi
0x140032f76  sub     rsp, 30h
0x140032f7a  mov     rcx, [r8+230h]
0x140032f81  mov     rdi, r8
0x140032f84  or      eax, 0FFFFFFFFh
0x140032f87  lock xadd [rcx+114h], eax
0x140032f8f  cmp     eax, 1
0x140032f92  jnz     loc_140033023
0x140032f98  cmp     dword ptr [r8+8], 5
0x140032f9d  mov     rax, [r8+30h]
0x140032fa1  mov     [r8+58h], rax
0x140032fa5  lea     rax, Srv2PostOnCompletionAndClearCancelCallback
0x140032fac  mov     [r8+30h], rax
0x140032fb0  mov     dword ptr [r8+48h], 0
0x140032fb8  jnz     short loc_140032FDA
0x140032fba  lea     rcx, [r8+248h]
0x140032fc1  mov     [rsp+38h+var_18], 1
0x140032fc6  mov     r8d, 187h
0x140032fcc  lea     r9, SourceString; "Srv2PostToThreadPool"
0x140032fd3  mov     dl, 1
0x140032fd5  call    SRV2_PERF_ENTER_EX
0x140032fda  mov     rax, [rdi+40h]
0x140032fde  mov     rbx, [rax+88h]
0x140032fe5  call    cs:__imp_KeGetCurrentNodeNumber
0x140032fec  nop     dword ptr [rax+rax+00h]
0x140032ff1  movzx   eax, ax
0x140032ff4  lea     rdx, [rdi+20h]; ListEntry
0x140032ff8  mov     rbx, [rbx+rax*8+8]
0x140032ffd  lea     rcx, [rbx+10h]; ListHead
0x140033001  call    cs:__imp_ExpInterlockedPushEntrySList
0x140033008  nop     dword ptr [rax+rax+00h]
0x14003300d  test    rax, rax
0x140033010  jnz     short loc_140033023
0x140033012  movzx   edx, word ptr [rbx+42h]
0x140033016  cmp     ax, dx
0x140033019  jz      short loc_140033023
0x14003301b  mov     rcx, rbx
0x14003301e  call    RfspThreadPoolNodeWakeIdleWorker
0x140033023  mov     rbx, [rsp+38h+arg_0]
0x140033028  mov     eax, 0C0000016h
0x14003302d  add     rsp, 30h
0x140033031  pop     rdi
0x140033032  retn
```
