# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001160`
- end: `0x1800011f7`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001034`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800011ec`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800011ec`

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
0x180001160  sub     rsp, 48h
0x180001164  movzx   eax, byte ptr [rdx]
0x180001167  mov     r11, rcx
0x18000116a  shl     eax, 18h
0x18000116d  mov     r10, r8
0x180001170  mov     r8, [rsp+48h+arg_28]
0x180001175  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001179  movzx   eax, word ptr [rdx+1]
0x18000117d  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001181  mov     rax, [rdx+3]
0x180001185  add     rdx, 0Bh
0x180001189  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18000118e  mov     rax, [rcx+8]
0x180001192  mov     [r8], rax
0x180001195  mov     rax, [rcx+8]
0x180001199  mov     [rsp+48h+UserData], r8; UserData
0x18000119e  movzx   ecx, word ptr [rax]
0x1800011a1  mov     [r8+8], ecx
0x1800011a5  lea     rcx, _TraceLoggingMetadata
0x1800011ac  mov     [r8+10h], rdx
0x1800011b0  mov     dword ptr [r8+0Ch], 2
0x1800011b8  movzx   eax, word ptr [rdx]
0x1800011bb  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800011c0  mov     [r8+18h], eax
0x1800011c4  lea     rax, _TraceLoggingMetadataEnd
0x1800011cb  sub     eax, ecx
0x1800011cd  mov     dword ptr [r8+1Ch], 1
0x1800011d5  mov     dword ptr [rsp+48h+arg_28], eax
0x1800011d9  mov     r8, r10; ActivityId
0x1800011dc  mov     eax, dword ptr [rsp+48h+arg_28]
0x1800011e0  mov     eax, [rsp+48h+arg_20]
0x1800011e4  mov     rcx, [r11+20h]; RegHandle
0x1800011e8  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1800011ec  call    cs:__imp_EventWriteTransfer
0x1800011f2  add     rsp, 48h
0x1800011f6  retn
```
