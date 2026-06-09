# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1800018c8`
- end: `0x18000195f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x18000131c`
- `0x180001614`
- `0x180001968`
- `0x1800019d8`
- `0x180023b54`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001954`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001954`

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
0x1800018c8  sub     rsp, 48h
0x1800018cc  movzx   eax, byte ptr [rdx]
0x1800018cf  mov     r11, rcx
0x1800018d2  shl     eax, 18h
0x1800018d5  mov     r10, r8
0x1800018d8  mov     r8, [rsp+48h+arg_28]
0x1800018dd  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1800018e1  movzx   eax, word ptr [rdx+1]
0x1800018e5  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1800018e9  mov     rax, [rdx+3]
0x1800018ed  add     rdx, 0Bh
0x1800018f1  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800018f6  mov     rax, [rcx+8]
0x1800018fa  mov     [r8], rax
0x1800018fd  mov     rax, [rcx+8]
0x180001901  mov     [rsp+48h+UserData], r8; UserData
0x180001906  movzx   ecx, word ptr [rax]
0x180001909  mov     [r8+8], ecx
0x18000190d  lea     rcx, _TraceLoggingMetadata
0x180001914  mov     [r8+10h], rdx
0x180001918  mov     dword ptr [r8+0Ch], 2
0x180001920  movzx   eax, word ptr [rdx]
0x180001923  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001928  mov     [r8+18h], eax
0x18000192c  lea     rax, _TraceLoggingMetadataEnd
0x180001933  sub     eax, ecx
0x180001935  mov     dword ptr [r8+1Ch], 1
0x18000193d  mov     dword ptr [rsp+48h+arg_28], eax
0x180001941  mov     r8, r10; ActivityId
0x180001944  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001948  mov     eax, [rsp+48h+arg_20]
0x18000194c  mov     rcx, [r11+20h]; RegHandle
0x180001950  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001954  call    cs:__imp_EventWriteTransfer
0x18000195a  add     rsp, 48h
0x18000195e  retn
```
