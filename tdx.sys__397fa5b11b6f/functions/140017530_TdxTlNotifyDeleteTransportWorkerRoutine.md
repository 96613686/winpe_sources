# TdxTlNotifyDeleteTransportWorkerRoutine

- ea: `0x140017530`
- end: `0x140017586`
- name: `TdxTlNotifyDeleteTransportWorkerRoutine`
- size: `86`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140017cdc`

## import_xrefs

- `ntoskrnl!IoFreeWorkItem` at `0x140017545`
- `ntoskrnl!IoFreeWorkItem` at `0x140017545`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001755e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001755e`

## pseudocode

```c
void __fastcall TdxTlNotifyDeleteTransportWorkerRoutine(PDEVICE_OBJECT DeviceObject, PIO_WORKITEM *Context)
{
  KSPIN_LOCK *v3; // rdi
  KSPIN_LOCK v4; // rbx

  IoFreeWorkItem(*Context);
  v3 = (KSPIN_LOCK *)Context[1];
  v4 = (KSPIN_LOCK)Context[2];
  ExFreePoolWithTag(Context, 0);
  TdxDeleteTransport(v3, v4);
}

```

## disassembly

```asm
0x140017530  mov     [rsp+arg_0], rbx
0x140017535  mov     [rsp+arg_8], rsi
0x14001753a  push    rdi
0x14001753b  sub     rsp, 20h
0x14001753f  mov     rcx, [rdx]; IoWorkItem
0x140017542  mov     rsi, rdx
0x140017545  call    cs:__imp_IoFreeWorkItem
0x14001754c  nop     dword ptr [rax+rax+00h]
0x140017551  mov     rdi, [rsi+8]
0x140017555  xor     edx, edx; Tag
0x140017557  mov     rbx, [rsi+10h]
0x14001755b  mov     rcx, rsi; P
0x14001755e  call    cs:__imp_ExFreePoolWithTag
0x140017565  nop     dword ptr [rax+rax+00h]
0x14001756a  mov     rdx, rbx
0x14001756d  mov     rcx, rdi
0x140017570  call    TdxDeleteTransport
0x140017575  mov     rbx, [rsp+28h+arg_0]
0x14001757a  mov     rsi, [rsp+28h+arg_8]
0x14001757f  add     rsp, 20h
0x140017583  pop     rdi
0x140017584  retn
```
