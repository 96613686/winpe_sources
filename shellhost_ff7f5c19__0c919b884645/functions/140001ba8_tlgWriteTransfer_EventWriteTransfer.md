# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x140001ba8`
- end: `0x140001c3f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x140001008`
- `0x1400012e0`
- `0x1400013b4`
- `0x140001478`
- `0x14000172c`
- `0x140001c48`
- `0x140001c90`
- `0x140001d20`
- `0x140001dcc`
- `0x14004c880`
- `0x14005bfc4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001c34`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001c34`

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
0x140001ba8  sub     rsp, 48h
0x140001bac  movzx   eax, byte ptr [rdx]
0x140001baf  mov     r11, rcx
0x140001bb2  shl     eax, 18h
0x140001bb5  mov     r10, r8
0x140001bb8  mov     r8, [rsp+48h+arg_28]
0x140001bbd  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x140001bc1  movzx   eax, word ptr [rdx+1]
0x140001bc5  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x140001bc9  mov     rax, [rdx+3]
0x140001bcd  add     rdx, 0Bh
0x140001bd1  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x140001bd6  mov     rax, [rcx+8]
0x140001bda  mov     [r8], rax
0x140001bdd  mov     rax, [rcx+8]
0x140001be1  mov     [rsp+48h+UserData], r8; UserData
0x140001be6  movzx   ecx, word ptr [rax]
0x140001be9  mov     [r8+8], ecx
0x140001bed  lea     rcx, _TraceLoggingMetadata
0x140001bf4  mov     [r8+10h], rdx
0x140001bf8  mov     dword ptr [r8+0Ch], 2
0x140001c00  movzx   eax, word ptr [rdx]
0x140001c03  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140001c08  mov     [r8+18h], eax
0x140001c0c  lea     rax, _TraceLoggingMetadataEnd
0x140001c13  sub     eax, ecx
0x140001c15  mov     dword ptr [r8+1Ch], 1
0x140001c1d  mov     dword ptr [rsp+48h+arg_28], eax
0x140001c21  mov     r8, r10; ActivityId
0x140001c24  mov     eax, dword ptr [rsp+48h+arg_28]
0x140001c28  mov     eax, [rsp+48h+arg_20]
0x140001c2c  mov     rcx, [r11+20h]; RegHandle
0x140001c30  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x140001c34  call    cs:__imp_EventWriteTransfer
0x140001c3a  add     rsp, 48h
0x140001c3e  retn
```
