# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180019c50`
- end: `0x180019ce7`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x180001144`
- `0x180001270`
- `0x1800013ac`
- `0x1800014b0`
- `0x180001e18`
- `0x1800020cc`
- `0x1800024c0`
- `0x180019ba4`
- `0x180020c0c`
- `0x18002af60`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180019cdc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180019cdc`

## pseudocode

```c
ULONG __fastcall tlgWriteTransfer_EventWriteTransfer(
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
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, a4, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180019c50  sub     rsp, 48h
0x180019c54  movzx   eax, byte ptr [rdx]
0x180019c57  mov     r11, rcx
0x180019c5a  shl     eax, 18h
0x180019c5d  mov     r10, r8
0x180019c60  mov     r8, [rsp+48h+arg_28]
0x180019c65  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180019c69  movzx   eax, word ptr [rdx+1]
0x180019c6d  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180019c71  mov     rax, [rdx+3]
0x180019c75  add     rdx, 0Bh
0x180019c79  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180019c7e  mov     rax, [rcx+8]
0x180019c82  mov     [r8], rax
0x180019c85  mov     rax, [rcx+8]
0x180019c89  mov     [rsp+48h+UserData], r8; UserData
0x180019c8e  movzx   ecx, word ptr [rax]
0x180019c91  mov     [r8+8], ecx
0x180019c95  lea     rcx, _TraceLoggingMetadata
0x180019c9c  mov     [r8+10h], rdx
0x180019ca0  mov     dword ptr [r8+0Ch], 2
0x180019ca8  movzx   eax, word ptr [rdx]
0x180019cab  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180019cb0  mov     [r8+18h], eax
0x180019cb4  lea     rax, _TraceLoggingMetadataEnd
0x180019cbb  sub     eax, ecx
0x180019cbd  mov     dword ptr [r8+1Ch], 1
0x180019cc5  mov     dword ptr [rsp+48h+arg_28], eax
0x180019cc9  mov     r8, r10; ActivityId
0x180019ccc  mov     eax, dword ptr [rsp+48h+arg_28]
0x180019cd0  mov     eax, [rsp+48h+arg_20]
0x180019cd4  mov     rcx, [r11+20h]; RegHandle
0x180019cd8  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180019cdc  call    cs:__imp_EventWriteTransfer
0x180019ce2  add     rsp, 48h
0x180019ce6  retn
```
