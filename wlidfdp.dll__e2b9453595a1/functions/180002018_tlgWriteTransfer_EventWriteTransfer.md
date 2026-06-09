# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180002018`
- end: `0x1800020af`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`
- `0x1800010d4`
- `0x1800011a4`
- `0x180001458`
- `0x18000176c`
- `0x1800017fc`
- `0x1800018f8`
- `0x180001b9c`
- `0x18000c6cc`
- `0x18000d6dc`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800020a4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800020a4`

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
0x180002018  sub     rsp, 48h
0x18000201c  movzx   eax, byte ptr [rdx]
0x18000201f  mov     r11, rcx
0x180002022  shl     eax, 18h
0x180002025  mov     r10, r8
0x180002028  mov     r8, [rsp+48h+arg_28]
0x18000202d  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180002031  movzx   eax, word ptr [rdx+1]
0x180002035  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180002039  mov     rax, [rdx+3]
0x18000203d  add     rdx, 0Bh
0x180002041  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180002046  mov     rax, [rcx+8]
0x18000204a  mov     [r8], rax
0x18000204d  mov     rax, [rcx+8]
0x180002051  mov     [rsp+48h+UserData], r8; UserData
0x180002056  movzx   ecx, word ptr [rax]
0x180002059  mov     [r8+8], ecx
0x18000205d  lea     rcx, _TraceLoggingMetadata
0x180002064  mov     [r8+10h], rdx
0x180002068  mov     dword ptr [r8+0Ch], 2
0x180002070  movzx   eax, word ptr [rdx]
0x180002073  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180002078  mov     [r8+18h], eax
0x18000207c  lea     rax, _TraceLoggingMetadataEnd
0x180002083  sub     eax, ecx
0x180002085  mov     dword ptr [r8+1Ch], 1
0x18000208d  mov     dword ptr [rsp+48h+arg_28], eax
0x180002091  mov     r8, r10; ActivityId
0x180002094  mov     eax, dword ptr [rsp+48h+arg_28]
0x180002098  mov     eax, [rsp+48h+arg_20]
0x18000209c  mov     rcx, [r11+20h]; RegHandle
0x1800020a0  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1800020a4  call    cs:__imp_EventWriteTransfer
0x1800020aa  add     rsp, 48h
0x1800020ae  retn
```
