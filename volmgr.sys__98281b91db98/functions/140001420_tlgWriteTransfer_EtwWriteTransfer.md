# _tlgWriteTransfer_EtwWriteTransfer

- ea: `0x140001420`
- end: `0x1400014be`
- name: `_tlgWriteTransfer_EtwWriteTransfer`
- size: `158`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140001008`
- `0x140001190`
- `0x140001328`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x1400014ac`
- `ntoskrnl!EtwWriteTransfer` at `0x1400014ac`

## pseudocode

```c
NTSTATUS __fastcall tlgWriteTransfer_EtwWriteTransfer(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  ULONGLONG v6; // rax
  unsigned __int16 *v7; // rdx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+30h] [rbp-18h] BYREF

  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  v6 = *(_QWORD *)(a2 + 3);
  v7 = (unsigned __int16 *)(a2 + 11);
  EventDescriptor.Keyword = v6;
  UserData->Ptr = *(_QWORD *)(a1 + 8);
  UserData->Size = **(unsigned __int16 **)(a1 + 8);
  UserData[1].Ptr = (ULONGLONG)v7;
  UserData->Reserved = 2;
  UserData[1].Size = *v7;
  UserData[1].Reserved = 1;
  return EtwWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, a4, UserDataCount, UserData);
}

```

## disassembly

```asm
0x140001420  sub     rsp, 48h
0x140001424  movzx   eax, byte ptr [rdx]
0x140001427  mov     r11, rcx
0x14000142a  shl     eax, 18h
0x14000142d  mov     r10, r8
0x140001430  mov     r8, [rsp+48h+arg_28]
0x140001435  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x140001439  movzx   eax, word ptr [rdx+1]
0x14000143d  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x140001441  mov     rax, [rdx+3]
0x140001445  add     rdx, 0Bh
0x140001449  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x14000144e  mov     rax, [rcx+8]
0x140001452  mov     [r8], rax
0x140001455  mov     rax, [rcx+8]
0x140001459  mov     [rsp+48h+UserData], r8; UserData
0x14000145e  movzx   ecx, word ptr [rax]
0x140001461  mov     [r8+8], ecx
0x140001465  lea     rcx, _TraceLoggingMetadata
0x14000146c  mov     [r8+10h], rdx
0x140001470  mov     dword ptr [r8+0Ch], 2
0x140001478  movzx   eax, word ptr [rdx]
0x14000147b  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140001480  mov     [r8+18h], eax
0x140001484  lea     rax, _TraceLoggingMetadataEnd
0x14000148b  sub     eax, ecx
0x14000148d  mov     dword ptr [r8+1Ch], 1
0x140001495  mov     dword ptr [rsp+48h+arg_28], eax
0x140001499  mov     r8, r10; ActivityId
0x14000149c  mov     eax, dword ptr [rsp+48h+arg_28]
0x1400014a0  mov     eax, [rsp+48h+arg_20]
0x1400014a4  mov     rcx, [r11+20h]; RegHandle
0x1400014a8  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1400014ac  call    cs:__imp_EtwWriteTransfer
0x1400014b3  nop     dword ptr [rax+rax+00h]
0x1400014b8  add     rsp, 48h
0x1400014bc  retn
```
