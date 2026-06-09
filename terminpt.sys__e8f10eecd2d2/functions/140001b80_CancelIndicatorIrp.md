# CancelIndicatorIrp

- ea: `0x140001b80`
- end: `0x140001c2d`
- name: `CancelIndicatorIrp`
- size: `173`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140001b80`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140001c10`
- `ntoskrnl!IofCompleteRequest` at `0x140001c10`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001bcb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001bcb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001bf0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001bf0`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140001b95`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140001b95`

## pseudocode

```c
void __fastcall CancelIndicatorIrp(__int64 a1, IRP *a2)
{
  PFILE_OBJECT FileObject; // rcx
  PVOID FsContext2; // rax
  __int64 v5; // rdi
  KIRQL v6; // al

  IoReleaseCancelSpinLock(a2->CancelIrql);
  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  if ( FileObject )
  {
    FsContext2 = FileObject->FsContext2;
    if ( FsContext2 )
    {
      v5 = *(_QWORD *)(*(_QWORD *)FsContext2 + 64LL);
      v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 232));
      if ( a2 == *(IRP **)(v5 + 224) )
        *(_QWORD *)(v5 + 224) = 0;
      KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 232), v6);
    }
  }
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = -1073741536;
  IofCompleteRequest(a2, 0);
}

```

## disassembly

```asm
0x140001b80  mov     [rsp+arg_0], rbx
0x140001b85  mov     [rsp+arg_8], rsi
0x140001b8a  push    rdi
0x140001b8b  sub     rsp, 20h
0x140001b8f  mov     cl, [rdx+45h]; Irql
0x140001b92  mov     rbx, rdx
0x140001b95  call    cs:__imp_IoReleaseCancelSpinLock
0x140001b9c  nop     dword ptr [rax+rax+00h]
0x140001ba1  mov     rax, [rbx+0B8h]
0x140001ba8  mov     rcx, [rax+30h]
0x140001bac  test    rcx, rcx
0x140001baf  jz      short loc_140001BFC
0x140001bb1  mov     rax, [rcx+20h]
0x140001bb5  test    rax, rax
0x140001bb8  jz      short loc_140001BFC
0x140001bba  mov     rax, [rax]
0x140001bbd  mov     rdi, [rax+40h]
0x140001bc1  lea     rsi, [rdi+0E8h]
0x140001bc8  mov     rcx, rsi; SpinLock
0x140001bcb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001bd2  nop     dword ptr [rax+rax+00h]
0x140001bd7  cmp     rbx, [rdi+0E0h]
0x140001bde  jnz     short loc_140001BEB
0x140001be0  mov     qword ptr [rdi+0E0h], 0
0x140001beb  mov     dl, al; NewIrql
0x140001bed  mov     rcx, rsi; SpinLock
0x140001bf0  call    cs:__imp_KeReleaseSpinLock
0x140001bf7  nop     dword ptr [rax+rax+00h]
0x140001bfc  xor     edx, edx; PriorityBoost
0x140001bfe  mov     qword ptr [rbx+38h], 0
0x140001c06  mov     rcx, rbx; Irp
0x140001c09  mov     dword ptr [rbx+30h], 0C0000120h
0x140001c10  call    cs:__imp_IofCompleteRequest
0x140001c17  nop     dword ptr [rax+rax+00h]
0x140001c1c  mov     rbx, [rsp+28h+arg_0]
0x140001c21  mov     rsi, [rsp+28h+arg_8]
0x140001c26  add     rsp, 20h
0x140001c2a  pop     rdi
0x140001c2b  retn
```
