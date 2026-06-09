# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001260`
- end: `0x1800012f7`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: ``
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x18000116c`
- `0x180001300`
- `0x180001350`
- `0x1800013e0`
- `0x1800014c0`
- `0x1800015b8`
- `0x180001694`
- `0x180001740`
- `0x1800017a4`
- `0x18000181c`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x1800012ec`
- `ADVAPI32!EventWriteTransfer` at `0x1800012ec`

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
0x180001260  sub     rsp, 48h
0x180001264  movzx   eax, byte ptr [rdx]
0x180001267  mov     r11, rcx
0x18000126a  shl     eax, 18h
0x18000126d  mov     r10, r8
0x180001270  mov     r8, [rsp+48h+arg_28]
0x180001275  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001279  movzx   eax, word ptr [rdx+1]
0x18000127d  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001281  mov     rax, [rdx+3]
0x180001285  add     rdx, 0Bh
0x180001289  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18000128e  mov     rax, [rcx+8]
0x180001292  mov     [r8], rax
0x180001295  mov     rax, [rcx+8]
0x180001299  mov     [rsp+48h+UserData], r8; UserData
0x18000129e  movzx   ecx, word ptr [rax]
0x1800012a1  mov     [r8+8], ecx
0x1800012a5  lea     rcx, _TraceLoggingMetadata
0x1800012ac  mov     [r8+10h], rdx
0x1800012b0  mov     dword ptr [r8+0Ch], 2
0x1800012b8  movzx   eax, word ptr [rdx]
0x1800012bb  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800012c0  mov     [r8+18h], eax
0x1800012c4  lea     rax, _TraceLoggingMetadataEnd
0x1800012cb  sub     eax, ecx
0x1800012cd  mov     dword ptr [r8+1Ch], 1
0x1800012d5  mov     dword ptr [rsp+48h+arg_28], eax
0x1800012d9  mov     r8, r10; ActivityId
0x1800012dc  mov     eax, dword ptr [rsp+48h+arg_28]
0x1800012e0  mov     eax, [rsp+48h+arg_20]
0x1800012e4  mov     rcx, [r11+20h]; RegHandle
0x1800012e8  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1800012ec  call    cs:__imp_EventWriteTransfer
0x1800012f2  add     rsp, 48h
0x1800012f6  retn
```
