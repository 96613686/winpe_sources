# OncRpcMsgpCancelReplyCompletionForXid

- ea: `0x140003cb4`
- end: `0x140003d60`
- name: `OncRpcMsgpCancelReplyCompletionForXid`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000350c`

## callees

- `0x1400020c0`
- `0x140003cb4`
- `0x140004fa0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140003d3a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140003d3a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003ced`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003ced`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003ccc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003ccc`

## pseudocode

```c
__int64 __fastcall OncRpcMsgpCancelReplyCompletionForXid(unsigned int a1)
{
  KIRQL v2; // bl
  void *v3; // rdi
  unsigned int v4; // ebx

  v2 = KeAcquireSpinLockRaiseToDpc(&qword_14001A958);
  v3 = (void *)OncRpcMsgpRemoveReplyCompletionContextForXid(a1);
  KeReleaseSpinLock(&qword_14001A958, v2);
  if ( v3 )
  {
    v4 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_805c0885a8ed3962ecc38e19173d6373_Traceguids, a1);
    ExFreeToNPagedLookasideList(&stru_14001A780, v3);
  }
  else
  {
    return (unsigned int)-1073741275;
  }
  return v4;
}

```

## disassembly

```asm
0x140003cb4  mov     [rsp+arg_0], rbx
0x140003cb9  mov     [rsp+arg_8], rsi
0x140003cbe  push    rdi
0x140003cbf  sub     rsp, 20h
0x140003cc3  mov     esi, ecx
0x140003cc5  lea     rcx, qword_14001A958; SpinLock
0x140003ccc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003cd3  nop     dword ptr [rax+rax+00h]
0x140003cd8  mov     ecx, esi
0x140003cda  mov     bl, al
0x140003cdc  call    OncRpcMsgpRemoveReplyCompletionContextForXid
0x140003ce1  mov     dl, bl; NewIrql
0x140003ce3  lea     rcx, qword_14001A958; SpinLock
0x140003cea  mov     rdi, rax
0x140003ced  call    cs:__imp_KeReleaseSpinLock
0x140003cf4  nop     dword ptr [rax+rax+00h]
0x140003cf9  test    rdi, rdi
0x140003cfc  jz      short loc_140003D48
0x140003cfe  xor     ebx, ebx
0x140003d00  mov     rcx, cs:WPP_GLOBAL_Control
0x140003d07  lea     rax, WPP_GLOBAL_Control
0x140003d0e  cmp     rcx, rax
0x140003d11  jz      short loc_140003D30
0x140003d13  mov     eax, [rcx+2Ch]
0x140003d16  test    al, 4
0x140003d18  jz      short loc_140003D30
0x140003d1a  mov     rcx, [rcx+18h]
0x140003d1e  lea     edx, [rbx+0Bh]
0x140003d21  mov     r9d, esi
0x140003d24  lea     r8, WPP_805c0885a8ed3962ecc38e19173d6373_Traceguids
0x140003d2b  call    WPP_SF_d
0x140003d30  mov     rdx, rdi; Entry
0x140003d33  lea     rcx, stru_14001A780; Lookaside
0x140003d3a  call    cs:__imp_ExFreeToNPagedLookasideList
0x140003d41  nop     dword ptr [rax+rax+00h]
0x140003d46  jmp     short loc_140003D4D
0x140003d48  mov     ebx, 0C0000225h
0x140003d4d  mov     rsi, [rsp+28h+arg_8]
0x140003d52  mov     eax, ebx
0x140003d54  mov     rbx, [rsp+28h+arg_0]
0x140003d59  add     rsp, 20h
0x140003d5d  pop     rdi
0x140003d5e  retn
```
