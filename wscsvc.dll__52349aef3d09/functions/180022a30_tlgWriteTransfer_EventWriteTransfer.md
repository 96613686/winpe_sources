# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180022a30`
- end: `0x180022ac7`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x1800010f4`
- `0x180001300`
- `0x180001448`
- `0x18000148c`
- `0x18000156c`
- `0x1800016a8`
- `0x180001704`
- `0x1800017f8`
- `0x18000190c`
- `0x18002400c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180022abc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180022abc`

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
0x180022a30  sub     rsp, 48h
0x180022a34  movzx   eax, byte ptr [rdx]
0x180022a37  mov     r11, rcx
0x180022a3a  shl     eax, 18h
0x180022a3d  mov     r10, r8
0x180022a40  mov     r8, [rsp+48h+arg_28]
0x180022a45  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180022a49  movzx   eax, word ptr [rdx+1]
0x180022a4d  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180022a51  mov     rax, [rdx+3]
0x180022a55  add     rdx, 0Bh
0x180022a59  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180022a5e  mov     rax, [rcx+8]
0x180022a62  mov     [r8], rax
0x180022a65  mov     rax, [rcx+8]
0x180022a69  mov     [rsp+48h+UserData], r8; UserData
0x180022a6e  movzx   ecx, word ptr [rax]
0x180022a71  mov     [r8+8], ecx
0x180022a75  lea     rcx, _TraceLoggingMetadata
0x180022a7c  mov     [r8+10h], rdx
0x180022a80  mov     dword ptr [r8+0Ch], 2
0x180022a88  movzx   eax, word ptr [rdx]
0x180022a8b  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180022a90  mov     [r8+18h], eax
0x180022a94  lea     rax, _TraceLoggingMetadataEnd
0x180022a9b  sub     eax, ecx
0x180022a9d  mov     dword ptr [r8+1Ch], 1
0x180022aa5  mov     dword ptr [rsp+48h+arg_28], eax
0x180022aa9  mov     r8, r10; ActivityId
0x180022aac  mov     eax, dword ptr [rsp+48h+arg_28]
0x180022ab0  mov     eax, [rsp+48h+arg_20]
0x180022ab4  mov     rcx, [r11+20h]; RegHandle
0x180022ab8  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180022abc  call    cs:__imp_EventWriteTransfer
0x180022ac2  add     rsp, 48h
0x180022ac6  retn
```
