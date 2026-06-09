# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180002184`
- end: `0x18000221b`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001e24`
- `0x180001ed0`
- `0x1800191fc`
- `0x180019304`
- `0x180019420`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180002210`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180002210`

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
0x180002184  sub     rsp, 48h
0x180002188  movzx   eax, byte ptr [rdx]
0x18000218b  mov     r11, rcx
0x18000218e  shl     eax, 18h
0x180002191  mov     r10, r8
0x180002194  mov     r8, [rsp+48h+arg_28]
0x180002199  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x18000219d  movzx   eax, word ptr [rdx+1]
0x1800021a1  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1800021a5  mov     rax, [rdx+3]
0x1800021a9  add     rdx, 0Bh
0x1800021ad  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800021b2  mov     rax, [rcx+8]
0x1800021b6  mov     [r8], rax
0x1800021b9  mov     rax, [rcx+8]
0x1800021bd  mov     [rsp+48h+UserData], r8; UserData
0x1800021c2  movzx   ecx, word ptr [rax]
0x1800021c5  mov     [r8+8], ecx
0x1800021c9  lea     rcx, _TraceLoggingMetadata
0x1800021d0  mov     [r8+10h], rdx
0x1800021d4  mov     dword ptr [r8+0Ch], 2
0x1800021dc  movzx   eax, word ptr [rdx]
0x1800021df  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800021e4  mov     [r8+18h], eax
0x1800021e8  lea     rax, _TraceLoggingMetadataEnd
0x1800021ef  sub     eax, ecx
0x1800021f1  mov     dword ptr [r8+1Ch], 1
0x1800021f9  mov     dword ptr [rsp+48h+arg_28], eax
0x1800021fd  mov     r8, r10; ActivityId
0x180002200  mov     eax, dword ptr [rsp+48h+arg_28]
0x180002204  mov     eax, [rsp+48h+arg_20]
0x180002208  mov     rcx, [r11+20h]; RegHandle
0x18000220c  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180002210  call    cs:__imp_EventWriteTransfer
0x180002216  add     rsp, 48h
0x18000221a  retn
```
