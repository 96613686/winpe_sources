# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001d40`
- end: `0x180001dd7`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001178`
- `0x1800013d0`
- `0x180001bcc`
- `0x180015f00`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001dcc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001dcc`

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
0x180001d40  sub     rsp, 48h
0x180001d44  movzx   eax, byte ptr [rdx]
0x180001d47  mov     r11, rcx
0x180001d4a  shl     eax, 18h
0x180001d4d  mov     r10, r8
0x180001d50  mov     r8, [rsp+48h+arg_28]
0x180001d55  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001d59  movzx   eax, word ptr [rdx+1]
0x180001d5d  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001d61  mov     rax, [rdx+3]
0x180001d65  add     rdx, 0Bh
0x180001d69  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001d6e  mov     rax, [rcx+8]
0x180001d72  mov     [r8], rax
0x180001d75  mov     rax, [rcx+8]
0x180001d79  mov     [rsp+48h+UserData], r8; UserData
0x180001d7e  movzx   ecx, word ptr [rax]
0x180001d81  mov     [r8+8], ecx
0x180001d85  lea     rcx, _TraceLoggingMetadata
0x180001d8c  mov     [r8+10h], rdx
0x180001d90  mov     dword ptr [r8+0Ch], 2
0x180001d98  movzx   eax, word ptr [rdx]
0x180001d9b  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001da0  mov     [r8+18h], eax
0x180001da4  lea     rax, _TraceLoggingMetadataEnd
0x180001dab  sub     eax, ecx
0x180001dad  mov     dword ptr [r8+1Ch], 1
0x180001db5  mov     dword ptr [rsp+48h+arg_28], eax
0x180001db9  mov     r8, r10; ActivityId
0x180001dbc  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001dc0  mov     eax, [rsp+48h+arg_20]
0x180001dc4  mov     rcx, [r11+20h]; RegHandle
0x180001dc8  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001dcc  call    cs:__imp_EventWriteTransfer
0x180001dd2  add     rsp, 48h
0x180001dd6  retn
```
