# VidExoBrokerpIrpCancelRoutine

- ea: `0x140012dd0`
- end: `0x140012e71`
- name: `VidExoBrokerpIrpCancelRoutine`
- size: `161`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140012dd0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140012e4d`
- `ntoskrnl!IofCompleteRequest` at `0x140012e4d`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140012de8`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140012de8`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140012dff`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140012dff`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012e35`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012e35`

## pseudocode

```c
void __fastcall VidExoBrokerpIrpCancelRoutine(__int64 a1, IRP *a2)
{
  KIRQL CancelIrql; // si
  struct _LIST_ENTRY *Flink; // rdi
  struct _LIST_ENTRY *v5; // r9
  struct _LIST_ENTRY *Blink; // r8

  CancelIrql = a2->CancelIrql;
  IoReleaseCancelSpinLock(2u);
  Flink = a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)&Flink[754]);
  v5 = a2->Tail.Overlay.ListEntry.Flink;
  if ( (PVOID *)v5->Blink != &a2->Tail.CompletionKey + 6
    || (Blink = a2->Tail.Overlay.ListEntry.Blink, (PVOID *)Blink->Flink != &a2->Tail.CompletionKey + 6) )
  {
    __fastfail(3u);
  }
  Blink->Flink = v5;
  v5->Blink = Blink;
  KeReleaseSpinLock((PKSPIN_LOCK)&Flink[754], CancelIrql);
  a2->IoStatus.Status = -1073741536;
  IofCompleteRequest(a2, 0);
}

```

## disassembly

```asm
0x140012dd0  mov     [rsp+arg_0], rbx
0x140012dd5  mov     [rsp+arg_8], rsi
0x140012dda  push    rdi
0x140012ddb  sub     rsp, 20h
0x140012ddf  mov     sil, [rdx+45h]
0x140012de3  mov     cl, 2; Irql
0x140012de5  mov     rbx, rdx
0x140012de8  call    cs:__imp_IoReleaseCancelSpinLock
0x140012def  nop     dword ptr [rax+rax+00h]
0x140012df4  mov     rdi, [rbx+78h]
0x140012df8  lea     rcx, [rdi+2F20h]; SpinLock
0x140012dff  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140012e06  nop     dword ptr [rax+rax+00h]
0x140012e0b  lea     rax, [rbx+0A8h]
0x140012e12  mov     r9, [rax]
0x140012e15  cmp     [r9+8], rax
0x140012e19  jnz     short loc_140012E6A
0x140012e1b  mov     r8, [rax+8]
0x140012e1f  cmp     [r8], rax
0x140012e22  jnz     short loc_140012E6A
0x140012e24  mov     [r8], r9
0x140012e27  lea     rcx, [rdi+2F20h]; SpinLock
0x140012e2e  mov     dl, sil; NewIrql
0x140012e31  mov     [r9+8], r8
0x140012e35  call    cs:__imp_KeReleaseSpinLock
0x140012e3c  nop     dword ptr [rax+rax+00h]
0x140012e41  xor     edx, edx; PriorityBoost
0x140012e43  mov     dword ptr [rbx+30h], 0C0000120h
0x140012e4a  mov     rcx, rbx; Irp
0x140012e4d  call    cs:__imp_IofCompleteRequest
0x140012e54  nop     dword ptr [rax+rax+00h]
0x140012e59  mov     rbx, [rsp+28h+arg_0]
0x140012e5e  mov     rsi, [rsp+28h+arg_8]
0x140012e63  add     rsp, 20h
0x140012e67  pop     rdi
0x140012e68  retn
0x140012e6a  mov     ecx, 3
0x140012e6f  int     29h; Win8: RtlFailFast(ecx)
```
