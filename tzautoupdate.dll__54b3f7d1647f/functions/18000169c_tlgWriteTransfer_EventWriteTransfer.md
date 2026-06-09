# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x18000169c`
- end: `0x180001733`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `17`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`
- `0x1800010bc`
- `0x180001120`
- `0x1800011e4`
- `0x180001290`
- `0x180001384`
- `0x18000144c`
- `0x18000173c`
- `0x180001838`
- `0x1800018fc`
- `0x180001978`
- `0x1800019f8`
- `0x180001ab0`
- `0x180001ba4`
- `0x180001c98`
- `0x180001d30`
- `0x1800123b8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001728`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001728`

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
0x18000169c  sub     rsp, 48h
0x1800016a0  movzx   eax, byte ptr [rdx]
0x1800016a3  mov     r11, rcx
0x1800016a6  shl     eax, 18h
0x1800016a9  mov     r10, r8
0x1800016ac  mov     r8, [rsp+48h+arg_28]
0x1800016b1  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1800016b5  movzx   eax, word ptr [rdx+1]
0x1800016b9  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1800016bd  mov     rax, [rdx+3]
0x1800016c1  add     rdx, 0Bh
0x1800016c5  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800016ca  mov     rax, [rcx+8]
0x1800016ce  mov     [r8], rax
0x1800016d1  mov     rax, [rcx+8]
0x1800016d5  mov     [rsp+48h+UserData], r8; UserData
0x1800016da  movzx   ecx, word ptr [rax]
0x1800016dd  mov     [r8+8], ecx
0x1800016e1  lea     rcx, _TraceLoggingMetadata
0x1800016e8  mov     [r8+10h], rdx
0x1800016ec  mov     dword ptr [r8+0Ch], 2
0x1800016f4  movzx   eax, word ptr [rdx]
0x1800016f7  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800016fc  mov     [r8+18h], eax
0x180001700  lea     rax, _TraceLoggingMetadataEnd
0x180001707  sub     eax, ecx
0x180001709  mov     dword ptr [r8+1Ch], 1
0x180001711  mov     dword ptr [rsp+48h+arg_28], eax
0x180001715  mov     r8, r10; ActivityId
0x180001718  mov     eax, dword ptr [rsp+48h+arg_28]
0x18000171c  mov     eax, [rsp+48h+arg_20]
0x180001720  mov     rcx, [r11+20h]; RegHandle
0x180001724  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001728  call    cs:__imp_EventWriteTransfer
0x18000172e  add     rsp, 48h
0x180001732  retn
```
