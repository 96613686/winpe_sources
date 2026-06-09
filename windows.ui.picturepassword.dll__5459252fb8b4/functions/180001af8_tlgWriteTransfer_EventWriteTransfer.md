# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001af8`
- end: `0x180001b8f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`
- `0x1800012cc`
- `0x18000133c`
- `0x1800013cc`
- `0x180001670`
- `0x180001b98`
- `0x180001e70`
- `0x180001f44`
- `0x18000573c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001b84`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001b84`

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
0x180001af8  sub     rsp, 48h
0x180001afc  movzx   eax, byte ptr [rdx]
0x180001aff  mov     r11, rcx
0x180001b02  shl     eax, 18h
0x180001b05  mov     r10, r8
0x180001b08  mov     r8, [rsp+48h+arg_28]
0x180001b0d  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001b11  movzx   eax, word ptr [rdx+1]
0x180001b15  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001b19  mov     rax, [rdx+3]
0x180001b1d  add     rdx, 0Bh
0x180001b21  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001b26  mov     rax, [rcx+8]
0x180001b2a  mov     [r8], rax
0x180001b2d  mov     rax, [rcx+8]
0x180001b31  mov     [rsp+48h+UserData], r8; UserData
0x180001b36  movzx   ecx, word ptr [rax]
0x180001b39  mov     [r8+8], ecx
0x180001b3d  lea     rcx, _TraceLoggingMetadata
0x180001b44  mov     [r8+10h], rdx
0x180001b48  mov     dword ptr [r8+0Ch], 2
0x180001b50  movzx   eax, word ptr [rdx]
0x180001b53  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001b58  mov     [r8+18h], eax
0x180001b5c  lea     rax, _TraceLoggingMetadataEnd
0x180001b63  sub     eax, ecx
0x180001b65  mov     dword ptr [r8+1Ch], 1
0x180001b6d  mov     dword ptr [rsp+48h+arg_28], eax
0x180001b71  mov     r8, r10; ActivityId
0x180001b74  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001b78  mov     eax, [rsp+48h+arg_20]
0x180001b7c  mov     rcx, [r11+20h]; RegHandle
0x180001b80  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001b84  call    cs:__imp_EventWriteTransfer
0x180001b8a  add     rsp, 48h
0x180001b8e  retn
```
