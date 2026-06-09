# OncRpcMsgpAddReplyCompletionContextForXid

- ea: `0x140003b14`
- end: `0x140003bcb`
- name: `OncRpcMsgpAddReplyCompletionContextForXid`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000350c`

## callees

- `0x140003b14`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140003b35`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140003b35`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003bb3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003bb3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003b70`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003b70`

## pseudocode

```c
__int64 __fastcall OncRpcMsgpAddReplyCompletionContextForXid(unsigned int a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rbp
  char *v6; // rax
  char *v7; // rbx
  unsigned int v8; // edi
  KIRQL v9; // al
  char *v10; // r8
  char **v11; // rcx

  v5 = a1 % dword_14001A968;
  v6 = (char *)ExAllocateFromNPagedLookasideList(&stru_14001A780);
  v7 = v6;
  if ( v6 )
  {
    *((_QWORD *)v6 + 1) = v6;
    *(_QWORD *)v6 = v6;
    *((_QWORD *)v6 + 2) = &OncRpcMsgpSendCallWaitReplyCompletion;
    *((_QWORD *)v6 + 3) = a3;
    *((_DWORD *)v6 + 8) = a1;
    v9 = KeAcquireSpinLockRaiseToDpc(&qword_14001A958);
    v10 = (char *)P + 16 * v5;
    v11 = (char **)*((_QWORD *)v10 + 1);
    if ( *v11 != v10 )
      __fastfail(3u);
    *((_QWORD *)v7 + 1) = v11;
    v8 = 0;
    *(_QWORD *)v7 = v10;
    *v11 = v7;
    *((_QWORD *)v10 + 1) = v7;
    KeReleaseSpinLock(&qword_14001A958, v9);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v8;
}

```

## disassembly

```asm
0x140003b14  push    rbx
0x140003b16  push    rbp
0x140003b17  push    rsi
0x140003b18  push    rdi
0x140003b19  sub     rsp, 28h
0x140003b1d  mov     eax, ecx
0x140003b1f  xor     edx, edx
0x140003b21  div     cs:dword_14001A968
0x140003b27  mov     edi, ecx
0x140003b29  mov     rsi, r8
0x140003b2c  lea     rcx, stru_14001A780; Lookaside
0x140003b33  mov     ebp, edx
0x140003b35  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140003b3c  nop     dword ptr [rax+rax+00h]
0x140003b41  mov     rbx, rax
0x140003b44  test    rax, rax
0x140003b47  jnz     short loc_140003B50
0x140003b49  mov     edi, 0C000009Ah
0x140003b4e  jmp     short loc_140003BBF
0x140003b50  mov     [rax+8], rbx
0x140003b54  lea     rcx, qword_14001A958; SpinLock
0x140003b5b  mov     [rax], rbx
0x140003b5e  lea     rax, OncRpcMsgpSendCallWaitReplyCompletion
0x140003b65  mov     [rbx+10h], rax
0x140003b69  mov     [rbx+18h], rsi
0x140003b6d  mov     [rbx+20h], edi
0x140003b70  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003b77  nop     dword ptr [rax+rax+00h]
0x140003b7c  mov     r8, rbp
0x140003b7f  shl     r8, 4
0x140003b83  add     r8, cs:P
0x140003b8a  mov     rcx, [r8+8]
0x140003b8e  cmp     [rcx], r8
0x140003b91  jz      short loc_140003B9A
0x140003b93  mov     ecx, 3
0x140003b98  int     29h; Win8: RtlFailFast(ecx)
0x140003b9a  mov     [rbx+8], rcx
0x140003b9e  xor     edi, edi
0x140003ba0  mov     [rbx], r8
0x140003ba3  mov     dl, al; NewIrql
0x140003ba5  mov     [rcx], rbx
0x140003ba8  lea     rcx, qword_14001A958; SpinLock
0x140003baf  mov     [r8+8], rbx
0x140003bb3  call    cs:__imp_KeReleaseSpinLock
0x140003bba  nop     dword ptr [rax+rax+00h]
0x140003bbf  mov     eax, edi
0x140003bc1  add     rsp, 28h
0x140003bc5  pop     rdi
0x140003bc6  pop     rsi
0x140003bc7  pop     rbp
0x140003bc8  pop     rbx
0x140003bc9  retn
```
