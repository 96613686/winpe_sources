# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180024600`
- end: `0x180024697`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x180001034`
- `0x18000112c`
- `0x180001220`
- `0x1800012fc`
- `0x18000141c`
- `0x1800014e4`
- `0x1800243f4`
- `0x1800244b8`
- `0x180024550`
- `0x1800272dc`
- `0x1800274e4`
- `0x18002d57c`
- `0x18002dcc0`
- `0x18002e0c8`
- `0x18002e220`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002468c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002468c`

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
0x180024600  sub     rsp, 48h
0x180024604  movzx   eax, byte ptr [rdx]
0x180024607  mov     r11, rcx
0x18002460a  shl     eax, 18h
0x18002460d  mov     r10, r8
0x180024610  mov     r8, [rsp+48h+arg_28]
0x180024615  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180024619  movzx   eax, word ptr [rdx+1]
0x18002461d  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180024621  mov     rax, [rdx+3]
0x180024625  add     rdx, 0Bh
0x180024629  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18002462e  mov     rax, [rcx+8]
0x180024632  mov     [r8], rax
0x180024635  mov     rax, [rcx+8]
0x180024639  mov     [rsp+48h+UserData], r8; UserData
0x18002463e  movzx   ecx, word ptr [rax]
0x180024641  mov     [r8+8], ecx
0x180024645  lea     rcx, _TraceLoggingMetadata
0x18002464c  mov     [r8+10h], rdx
0x180024650  mov     dword ptr [r8+0Ch], 2
0x180024658  movzx   eax, word ptr [rdx]
0x18002465b  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180024660  mov     [r8+18h], eax
0x180024664  lea     rax, _TraceLoggingMetadataEnd
0x18002466b  sub     eax, ecx
0x18002466d  mov     dword ptr [r8+1Ch], 1
0x180024675  mov     dword ptr [rsp+48h+arg_28], eax
0x180024679  mov     r8, r10; ActivityId
0x18002467c  mov     eax, dword ptr [rsp+48h+arg_28]
0x180024680  mov     eax, [rsp+48h+arg_20]
0x180024684  mov     rcx, [r11+20h]; RegHandle
0x180024688  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x18002468c  call    cs:__imp_EventWriteTransfer
0x180024692  add     rsp, 48h
0x180024696  retn
```
