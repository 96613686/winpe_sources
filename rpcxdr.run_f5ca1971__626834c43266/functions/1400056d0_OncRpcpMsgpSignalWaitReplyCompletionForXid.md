# OncRpcpMsgpSignalWaitReplyCompletionForXid

- ea: `0x1400056d0`
- end: `0x14000578e`
- name: `OncRpcpMsgpSignalWaitReplyCompletionForXid`
- size: `190`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002f50`

## callees

- `0x1400020c0`
- `0x140004fa0`
- `0x1400056d0`
- `0x140015680`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140005774`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140005774`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005759`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005759`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400056e7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400056e7`

## pseudocode

```c
__int64 __fastcall OncRpcpMsgpSignalWaitReplyCompletionForXid(unsigned int a1, __int64 a2)
{
  KIRQL v4; // bp
  __int64 v5; // rbx
  unsigned int v6; // edi

  v4 = KeAcquireSpinLockRaiseToDpc(&qword_14001A958);
  v5 = OncRpcMsgpRemoveReplyCompletionContextForXid(a1);
  if ( v5 )
  {
    v6 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_805c0885a8ed3962ecc38e19173d6373_Traceguids, a1);
    (*(void (__fastcall **)(__int64, _QWORD))(v5 + 16))(a2, *(_QWORD *)(v5 + 24));
  }
  else
  {
    v6 = -1073741275;
  }
  KeReleaseSpinLock(&qword_14001A958, v4);
  if ( v5 )
    ExFreeToNPagedLookasideList(&stru_14001A780, (PVOID)v5);
  return v6;
}

```

## disassembly

```asm
0x1400056d0  push    rbx
0x1400056d2  push    rbp
0x1400056d3  push    rsi
0x1400056d4  push    rdi
0x1400056d5  push    r14
0x1400056d7  sub     rsp, 20h
0x1400056db  mov     esi, ecx
0x1400056dd  mov     r14, rdx
0x1400056e0  lea     rcx, qword_14001A958; SpinLock
0x1400056e7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400056ee  nop     dword ptr [rax+rax+00h]
0x1400056f3  mov     ecx, esi
0x1400056f5  mov     bpl, al
0x1400056f8  call    OncRpcMsgpRemoveReplyCompletionContextForXid
0x1400056fd  mov     rbx, rax
0x140005700  test    rax, rax
0x140005703  jz      short loc_14000574A
0x140005705  xor     edi, edi
0x140005707  mov     rcx, cs:WPP_GLOBAL_Control
0x14000570e  lea     rax, WPP_GLOBAL_Control
0x140005715  cmp     rcx, rax
0x140005718  jz      short loc_140005738
0x14000571a  mov     edx, [rcx+2Ch]
0x14000571d  test    dl, 4
0x140005720  jz      short loc_140005738
0x140005722  mov     rcx, [rcx+18h]
0x140005726  lea     edx, [rdi+0Ch]
0x140005729  mov     r9d, esi
0x14000572c  lea     r8, WPP_805c0885a8ed3962ecc38e19173d6373_Traceguids
0x140005733  call    WPP_SF_d
0x140005738  mov     rax, [rbx+10h]
0x14000573c  mov     rcx, r14
0x14000573f  mov     rdx, [rbx+18h]
0x140005743  call    _guard_dispatch_icall
0x140005748  jmp     short loc_14000574F
0x14000574a  mov     edi, 0C0000225h
0x14000574f  mov     dl, bpl; NewIrql
0x140005752  lea     rcx, qword_14001A958; SpinLock
0x140005759  call    cs:__imp_KeReleaseSpinLock
0x140005760  nop     dword ptr [rax+rax+00h]
0x140005765  test    rbx, rbx
0x140005768  jz      short loc_140005780
0x14000576a  mov     rdx, rbx; Entry
0x14000576d  lea     rcx, stru_14001A780; Lookaside
0x140005774  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000577b  nop     dword ptr [rax+rax+00h]
0x140005780  mov     eax, edi
0x140005782  add     rsp, 20h
0x140005786  pop     r14
0x140005788  pop     rdi
0x140005789  pop     rsi
0x14000578a  pop     rbp
0x14000578b  pop     rbx
0x14000578c  retn
```
