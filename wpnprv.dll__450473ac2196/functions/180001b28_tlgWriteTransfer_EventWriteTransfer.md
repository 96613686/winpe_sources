# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001b28`
- end: `0x180001bbf`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `48`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`
- `0x1800013a0`
- `0x180001698`
- `0x180001bc8`
- `0x180001ea0`
- `0x180001f74`
- `0x180002038`
- `0x1800020b8`
- `0x180002118`
- `0x180002260`
- `0x1800024cc`
- `0x1800025c8`
- `0x180002688`
- `0x180002788`
- `0x180002a04`
- `0x180002ba0`
- `0x180002ca0`
- `0x180002da4`
- `0x180002ed0`
- `0x180003148`
- `0x1800033cc`
- `0x180003664`
- `0x1800038a0`
- `0x180003ae8`
- `0x180003dd4`
- `0x180003fa4`
- `0x18000418c`
- `0x1800043c8`
- `0x18000455c`
- `0x1800046f0`
- `0x180004908`
- `0x180004a84`
- `0x180004c98`
- `0x180004e70`
- `0x180005030`
- `0x1800051f8`
- `0x180005368`
- `0x1800054d8`
- `0x1800055c4`
- `0x1800056a4`
- `0x1800057a4`
- `0x1800059ac`
- `0x180005aa4`
- `0x180005ec8`
- `0x180005fe8`
- `0x1800060dc`
- `0x180006188`
- `0x18008c3b4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001bb4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001bb4`

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
0x180001b28  sub     rsp, 48h
0x180001b2c  movzx   eax, byte ptr [rdx]
0x180001b2f  mov     r11, rcx
0x180001b32  shl     eax, 18h
0x180001b35  mov     r10, r8
0x180001b38  mov     r8, [rsp+48h+arg_28]
0x180001b3d  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001b41  movzx   eax, word ptr [rdx+1]
0x180001b45  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001b49  mov     rax, [rdx+3]
0x180001b4d  add     rdx, 0Bh
0x180001b51  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x180001b56  mov     rax, [rcx+8]
0x180001b5a  mov     [r8], rax
0x180001b5d  mov     rax, [rcx+8]
0x180001b61  mov     [rsp+48h+UserData], r8; UserData
0x180001b66  movzx   ecx, word ptr [rax]
0x180001b69  mov     [r8+8], ecx
0x180001b6d  lea     rcx, _TraceLoggingMetadata
0x180001b74  mov     [r8+10h], rdx
0x180001b78  mov     dword ptr [r8+0Ch], 2
0x180001b80  movzx   eax, word ptr [rdx]
0x180001b83  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001b88  mov     [r8+18h], eax
0x180001b8c  lea     rax, _TraceLoggingMetadataEnd
0x180001b93  sub     eax, ecx
0x180001b95  mov     dword ptr [r8+1Ch], 1
0x180001b9d  mov     dword ptr [rsp+48h+arg_28], eax
0x180001ba1  mov     r8, r10; ActivityId
0x180001ba4  mov     eax, dword ptr [rsp+48h+arg_28]
0x180001ba8  mov     eax, [rsp+48h+arg_20]
0x180001bac  mov     rcx, [r11+20h]; RegHandle
0x180001bb0  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180001bb4  call    cs:__imp_EventWriteTransfer
0x180001bba  add     rsp, 48h
0x180001bbe  retn
```
