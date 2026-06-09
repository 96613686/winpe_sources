# TdxCleanupTransportWorkerRoutine

- ea: `0x140017a60`
- end: `0x140017aca`
- name: `TdxCleanupTransportWorkerRoutine`
- size: `106`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x14001798c`

## callees

- `0x140017a60`

## import_xrefs

- `ntoskrnl!IoDeleteSymbolicLink` at `0x140017a76`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140017a76`
- `ntoskrnl!IoDeleteDevice` at `0x140017a96`
- `ntoskrnl!IoDeleteDevice` at `0x140017aa6`
- `ntoskrnl!IoDeleteDevice` at `0x140017a96`
- `ntoskrnl!IoDeleteDevice` at `0x140017aa6`
- `ntoskrnl!IoFreeWorkItem` at `0x140017a86`
- `ntoskrnl!IoFreeWorkItem` at `0x140017a86`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017ab7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017ab7`

## pseudocode

```c
void __fastcall TdxCleanupTransportWorkerRoutine(PDEVICE_OBJECT DeviceObject, PVOID Context)
{
  if ( (*(_DWORD *)Context & 1) != 0 )
    IoDeleteSymbolicLink(&TdxTcpSymbolicDeviceName);
  IoFreeWorkItem(*((PIO_WORKITEM *)Context + 1));
  IoDeleteDevice(*((PDEVICE_OBJECT *)Context + 3));
  IoDeleteDevice(*((PDEVICE_OBJECT *)Context + 2));
  ExFreePoolWithTag(Context, 0);
}

```

## disassembly

```asm
0x140017a60  push    rbx
0x140017a62  sub     rsp, 20h
0x140017a66  mov     eax, [rdx]
0x140017a68  mov     rbx, rdx
0x140017a6b  test    al, 1
0x140017a6d  jz      short loc_140017A82
0x140017a6f  lea     rcx, TdxTcpSymbolicDeviceName; SymbolicLinkName
0x140017a76  call    cs:__imp_IoDeleteSymbolicLink
0x140017a7d  nop     dword ptr [rax+rax+00h]
0x140017a82  mov     rcx, [rbx+8]; IoWorkItem
0x140017a86  call    cs:__imp_IoFreeWorkItem
0x140017a8d  nop     dword ptr [rax+rax+00h]
0x140017a92  mov     rcx, [rbx+18h]; DeviceObject
0x140017a96  call    cs:__imp_IoDeleteDevice
0x140017a9d  nop     dword ptr [rax+rax+00h]
0x140017aa2  mov     rcx, [rbx+10h]; DeviceObject
0x140017aa6  call    cs:__imp_IoDeleteDevice
0x140017aad  nop     dword ptr [rax+rax+00h]
0x140017ab2  xor     edx, edx; Tag
0x140017ab4  mov     rcx, rbx; P
0x140017ab7  call    cs:__imp_ExFreePoolWithTag
0x140017abe  nop     dword ptr [rax+rax+00h]
0x140017ac3  add     rsp, 20h
0x140017ac7  pop     rbx
0x140017ac8  retn
```
