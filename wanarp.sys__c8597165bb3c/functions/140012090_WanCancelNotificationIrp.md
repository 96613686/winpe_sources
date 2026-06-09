# WanCancelNotificationIrp

- ea: `0x140012090`
- end: `0x1400120f6`
- name: `WanCancelNotificationIrp`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140012090`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400120cb`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400120cb`
- `ntoskrnl!IofCompleteRequest` at `0x1400120dc`
- `ntoskrnl!IofCompleteRequest` at `0x1400120dc`

## pseudocode

```c
void __fastcall WanCancelNotificationIrp(__int64 a1, IRP *a2)
{
  struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *p_ListEntry; // rax
  struct _LIST_ENTRY *Flink; // rdx
  struct _LIST_ENTRY *Blink; // rcx

  p_ListEntry = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)&a2->Tail.Overlay.ListEntry;
  a2->IoStatus.Status = -1073741536;
  a2->IoStatus.Information = 0;
  Flink = a2->Tail.Overlay.ListEntry.Flink;
  if ( (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)Flink->Blink != p_ListEntry
    || (Blink = p_ListEntry->ListEntry.Blink,
        (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)Blink->Flink != p_ListEntry) )
  {
    __fastfail(3u);
  }
  Blink->Flink = Flink;
  Flink->Blink = Blink;
  IoReleaseCancelSpinLock(a2->CancelIrql);
  IofCompleteRequest(a2, 2);
}

```

## disassembly

```asm
0x140012090  push    rbx
0x140012092  sub     rsp, 20h
0x140012096  lea     rax, [rdx+0A8h]
0x14001209d  mov     dword ptr [rdx+30h], 0C0000120h
0x1400120a4  mov     qword ptr [rdx+38h], 0
0x1400120ac  mov     rbx, rdx
0x1400120af  mov     rdx, [rax]
0x1400120b2  cmp     [rdx+8], rax
0x1400120b6  jnz     short loc_1400120EF
0x1400120b8  mov     rcx, [rax+8]
0x1400120bc  cmp     [rcx], rax
0x1400120bf  jnz     short loc_1400120EF
0x1400120c1  mov     [rcx], rdx
0x1400120c4  mov     [rdx+8], rcx
0x1400120c8  mov     cl, [rbx+45h]; Irql
0x1400120cb  call    cs:__imp_IoReleaseCancelSpinLock
0x1400120d2  nop     dword ptr [rax+rax+00h]
0x1400120d7  mov     dl, 2; PriorityBoost
0x1400120d9  mov     rcx, rbx; Irp
0x1400120dc  call    cs:__imp_IofCompleteRequest
0x1400120e3  nop     dword ptr [rax+rax+00h]
0x1400120e8  add     rsp, 20h
0x1400120ec  pop     rbx
0x1400120ed  retn
0x1400120ef  mov     ecx, 3
0x1400120f4  int     29h; Win8: RtlFailFast(ecx)
```
