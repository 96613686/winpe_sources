# TdxCleanupTransport

- ea: `0x14001798c`
- end: `0x140017a50`
- name: `TdxCleanupTransport`
- size: `196`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400036b0`
- `0x140006b40`
- `0x14000bab0`
- `0x14000ccfc`

## callees

- `0x14001798c`
- `0x140017a60`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140017a00`
- `ntoskrnl!KeGetCurrentIrql` at `0x140017a00`
- `ntoskrnl!IoQueueWorkItem` at `0x140017a38`
- `ntoskrnl!IoQueueWorkItem` at `0x140017a38`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400179a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400179b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400179a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400179b5`
- `NETIO!NmrClientDetachProviderComplete` at `0x1400179d2`
- `NETIO!NmrClientDetachProviderComplete` at `0x1400179d2`

## pseudocode

```c
void __fastcall TdxCleanupTransport(__int64 a1)
{
  struct _DEVICE_OBJECT *v1; // rdi

  v1 = *(struct _DEVICE_OBJECT **)(a1 + 88);
  ExFreePoolWithTag(*(PVOID *)(a1 + 48), 0);
  ExFreePoolWithTag(*(PVOID *)(a1 + 64), 0);
  if ( (*(_DWORD *)(a1 + 168) & 4) != 0 )
    NmrClientDetachProviderComplete(*(HANDLE *)(a1 + 152));
  if ( v1 )
  {
    **(_DWORD **)(a1 + 208) ^= ((unsigned __int8)**(_DWORD **)(a1 + 208)
                              ^ (unsigned __int8)(*(_DWORD *)(a1 + 168) >> 3))
                             & 1;
    if ( KeGetCurrentIrql() )
      IoQueueWorkItem(
        *(PIO_WORKITEM *)(*(_QWORD *)(a1 + 208) + 8LL),
        (PIO_WORKITEM_ROUTINE)TdxCleanupTransportWorkerRoutine,
        DelayedWorkQueue,
        *(PVOID *)(a1 + 208));
    else
      TdxCleanupTransportWorkerRoutine(v1, *(PVOID *)(a1 + 208));
  }
}

```

## disassembly

```asm
0x14001798c  mov     [rsp+arg_0], rbx
0x140017991  push    rdi
0x140017992  sub     rsp, 20h
0x140017996  mov     rdi, [rcx+58h]
0x14001799a  mov     rbx, rcx
0x14001799d  mov     rcx, [rcx+30h]; P
0x1400179a1  xor     edx, edx; Tag
0x1400179a3  call    cs:__imp_ExFreePoolWithTag
0x1400179aa  nop     dword ptr [rax+rax+00h]
0x1400179af  mov     rcx, [rbx+40h]; P
0x1400179b3  xor     edx, edx; Tag
0x1400179b5  call    cs:__imp_ExFreePoolWithTag
0x1400179bc  nop     dword ptr [rax+rax+00h]
0x1400179c1  mov     eax, [rbx+0A8h]
0x1400179c7  test    al, 4
0x1400179c9  jz      short loc_1400179DE
0x1400179cb  mov     rcx, [rbx+98h]; NmrBindingHandle
0x1400179d2  call    cs:__imp_NmrClientDetachProviderComplete
0x1400179d9  nop     dword ptr [rax+rax+00h]
0x1400179de  test    rdi, rdi
0x1400179e1  jz      short loc_140017A44
0x1400179e3  mov     r8, [rbx+0D0h]
0x1400179ea  mov     edx, [rbx+0A8h]
0x1400179f0  shr     edx, 3
0x1400179f3  mov     eax, [r8]
0x1400179f6  xor     edx, eax
0x1400179f8  and     edx, 1
0x1400179fb  xor     edx, eax
0x1400179fd  mov     [r8], edx
0x140017a00  call    cs:__imp_KeGetCurrentIrql
0x140017a07  nop     dword ptr [rax+rax+00h]
0x140017a0c  mov     rcx, [rbx+0D0h]
0x140017a13  test    al, al
0x140017a15  jnz     short loc_140017A24
0x140017a17  mov     rdx, rcx; Context
0x140017a1a  mov     rcx, rdi; DeviceObject
0x140017a1d  call    TdxCleanupTransportWorkerRoutine
0x140017a22  jmp     short loc_140017A44
0x140017a24  mov     r9, rcx; Context
0x140017a27  lea     rdx, TdxCleanupTransportWorkerRoutine; WorkerRoutine
0x140017a2e  mov     rcx, [rcx+8]; IoWorkItem
0x140017a32  mov     r8d, 1; QueueType
0x140017a38  call    cs:__imp_IoQueueWorkItem
0x140017a3f  nop     dword ptr [rax+rax+00h]
0x140017a44  mov     rbx, [rsp+28h+arg_0]
0x140017a49  add     rsp, 20h
0x140017a4d  pop     rdi
0x140017a4e  retn
```
