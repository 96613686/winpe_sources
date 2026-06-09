# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001090`
- end: `0x18000112e`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `158`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000755c`
- `0x18000e928`
- `0x18000f6d0`
- `0x18000f954`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000111c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000111c`

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
0x180001090  sub     rsp, 48h
0x180001094  movzx   eax, byte ptr [rdx]
0x180001097  mov     r11, rcx
0x18000109a  shl     eax, 18h
0x18000109d  mov     r10, r8
0x1800010a0  mov     r8, [rsp+48h+arg_28]
0x1800010a5  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1800010a9  movzx   eax, word ptr [rdx+1]
0x1800010ad  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1800010b1  mov     rax, [rdx+3]
0x1800010b5  add     rdx, 0Bh
0x1800010b9  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800010be  mov     rax, [rcx+8]
0x1800010c2  mov     [r8], rax
0x1800010c5  mov     rax, [rcx+8]
0x1800010c9  mov     [rsp+48h+UserData], r8; UserData
0x1800010ce  movzx   ecx, word ptr [rax]
0x1800010d1  mov     [r8+8], ecx
0x1800010d5  lea     rcx, _TraceLoggingMetadata
0x1800010dc  mov     [r8+10h], rdx
0x1800010e0  mov     dword ptr [r8+0Ch], 2
0x1800010e8  movzx   eax, word ptr [rdx]
0x1800010eb  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800010f0  mov     [r8+18h], eax
0x1800010f4  lea     rax, _TraceLoggingMetadataEnd
0x1800010fb  sub     eax, ecx
0x1800010fd  mov     dword ptr [r8+1Ch], 1
0x180001105  mov     dword ptr [rsp+48h+arg_28], eax
0x180001109  mov     r8, r10; ActivityId
0x18000110c  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001110  mov     eax, [rsp+48h+arg_20]
0x180001114  mov     rcx, [r11+20h]; RegHandle
0x180001118  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x18000111c  call    cs:__imp_EventWriteTransfer
0x180001123  nop     dword ptr [rax+rax+00h]
0x180001128  add     rsp, 48h
0x18000112c  retn
```
