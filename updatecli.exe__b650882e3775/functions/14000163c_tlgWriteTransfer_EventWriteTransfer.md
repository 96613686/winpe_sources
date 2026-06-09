# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x14000163c`
- end: `0x1400016d3`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140001008`
- `0x1400012bc`
- `0x140006db8`
- `0x140006eb8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400016c8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400016c8`

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
0x14000163c  sub     rsp, 48h
0x140001640  movzx   eax, byte ptr [rdx]
0x140001643  mov     r11, rcx
0x140001646  shl     eax, 18h
0x140001649  mov     r10, r8
0x14000164c  mov     r8, [rsp+48h+arg_28]
0x140001651  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x140001655  movzx   eax, word ptr [rdx+1]
0x140001659  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x14000165d  mov     rax, [rdx+3]
0x140001661  add     rdx, 0Bh
0x140001665  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x14000166a  mov     rax, [rcx+8]
0x14000166e  mov     [r8], rax
0x140001671  mov     rax, [rcx+8]
0x140001675  mov     [rsp+48h+UserData], r8; UserData
0x14000167a  movzx   ecx, word ptr [rax]
0x14000167d  mov     [r8+8], ecx
0x140001681  lea     rcx, _TraceLoggingMetadata
0x140001688  mov     [r8+10h], rdx
0x14000168c  mov     dword ptr [r8+0Ch], 2
0x140001694  movzx   eax, word ptr [rdx]
0x140001697  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x14000169c  mov     [r8+18h], eax
0x1400016a0  lea     rax, _TraceLoggingMetadataEnd
0x1400016a7  sub     eax, ecx
0x1400016a9  mov     dword ptr [r8+1Ch], 1
0x1400016b1  mov     dword ptr [rsp+48h+arg_28], eax
0x1400016b5  mov     r8, r10; ActivityId
0x1400016b8  mov     eax, dword ptr [rsp+48h+arg_28]
0x1400016bc  mov     eax, [rsp+48h+arg_20]
0x1400016c0  mov     rcx, [r11+20h]; RegHandle
0x1400016c4  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1400016c8  call    cs:__imp_EventWriteTransfer
0x1400016ce  add     rsp, 48h
0x1400016d2  retn
```
