# CsCompleteCanceledIrp

- ea: `0x14003a720`
- end: `0x14003a793`
- name: `CsCompleteCanceledIrp`
- size: `115`
- prototype: `IO_CSQ_COMPLETE_CANCELED_IRP`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140004bac`
- `0x14003a720`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14003a780`
- `ntoskrnl!IofCompleteRequest` at `0x14003a780`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a732`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a732`

## pseudocode

```c
void __fastcall CsCompleteCanceledIrp(PIO_CSQ Csq, PIRP Irp)
{
  ExFreePoolWithTag(Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink, 0x56425355u);
  Irp->IoStatus.Status = -1073741536;
  Irp->IoStatus.Information = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids);
  IofCompleteRequest(Irp, 0);
}

```

## disassembly

```asm
0x14003a720  push    rbx
0x14003a722  sub     rsp, 20h
0x14003a726  mov     rbx, rdx
0x14003a729  mov     edx, 56425355h; Tag
0x14003a72e  mov     rcx, [rbx+78h]; P
0x14003a732  call    cs:__imp_ExFreePoolWithTag
0x14003a739  nop     dword ptr [rax+rax+00h]
0x14003a73e  mov     dword ptr [rbx+30h], 0C0000120h
0x14003a745  mov     qword ptr [rbx+38h], 0
0x14003a74d  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a754  lea     rax, WPP_GLOBAL_Control
0x14003a75b  cmp     rcx, rax
0x14003a75e  jz      short loc_14003A77B
0x14003a760  cmp     byte ptr [rcx+29h], 5
0x14003a764  jb      short loc_14003A77B
0x14003a766  mov     rcx, [rcx+18h]
0x14003a76a  lea     r8, WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids
0x14003a771  mov     edx, 24h ; '$'
0x14003a776  call    WPP_SF_
0x14003a77b  xor     edx, edx; PriorityBoost
0x14003a77d  mov     rcx, rbx; Irp
0x14003a780  call    cs:__imp_IofCompleteRequest
0x14003a787  nop     dword ptr [rax+rax+00h]
0x14003a78c  add     rsp, 20h
0x14003a790  pop     rbx
0x14003a791  retn
```
