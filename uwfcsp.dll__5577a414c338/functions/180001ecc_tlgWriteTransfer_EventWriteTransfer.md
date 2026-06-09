# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001ecc`
- end: `0x180001f63`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `16`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x1800012bc`
- `0x180001594`
- `0x1800018b0`
- `0x180001b54`
- `0x180001f6c`
- `0x1800022a4`
- `0x180002600`
- `0x180002934`
- `0x18000745c`
- `0x180007788`
- `0x180007b18`
- `0x18000b61c`
- `0x18000b820`
- `0x18000c1ec`
- `0x18000cbfc`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001f58`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001f58`

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
0x180001ecc  sub     rsp, 48h
0x180001ed0  movzx   eax, byte ptr [rdx]
0x180001ed3  mov     r11, rcx
0x180001ed6  shl     eax, 18h
0x180001ed9  mov     r10, r8
0x180001edc  mov     r8, [rsp+48h+arg_28]
0x180001ee1  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001ee5  movzx   eax, word ptr [rdx+1]
0x180001ee9  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001eed  mov     rax, [rdx+3]
0x180001ef1  add     rdx, 0Bh
0x180001ef5  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001efa  mov     rax, [rcx+8]
0x180001efe  mov     [r8], rax
0x180001f01  mov     rax, [rcx+8]
0x180001f05  mov     [rsp+48h+UserData], r8; UserData
0x180001f0a  movzx   ecx, word ptr [rax]
0x180001f0d  mov     [r8+8], ecx
0x180001f11  lea     rcx, _TraceLoggingMetadata
0x180001f18  mov     [r8+10h], rdx
0x180001f1c  mov     dword ptr [r8+0Ch], 2
0x180001f24  movzx   eax, word ptr [rdx]
0x180001f27  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001f2c  mov     [r8+18h], eax
0x180001f30  lea     rax, _TraceLoggingMetadataEnd
0x180001f37  sub     eax, ecx
0x180001f39  mov     dword ptr [r8+1Ch], 1
0x180001f41  mov     dword ptr [rsp+48h+arg_28], eax
0x180001f45  mov     r8, r10; ActivityId
0x180001f48  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001f4c  mov     eax, [rsp+48h+arg_20]
0x180001f50  mov     rcx, [r11+20h]; RegHandle
0x180001f54  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001f58  call    cs:__imp_EventWriteTransfer
0x180001f5e  add     rsp, 48h
0x180001f62  retn
```
