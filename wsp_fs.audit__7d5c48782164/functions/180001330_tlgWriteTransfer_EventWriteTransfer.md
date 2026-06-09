# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001330`
- end: `0x1800013ce`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `158`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`
- `0x1800010bc`
- `0x180001100`
- `0x1800013d4`
- `0x180001480`
- `0x180001548`
- `0x180072020`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800013bc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800013bc`

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
0x180001330  sub     rsp, 48h
0x180001334  movzx   eax, byte ptr [rdx]
0x180001337  mov     r11, rcx
0x18000133a  shl     eax, 18h
0x18000133d  mov     r10, r8
0x180001340  mov     r8, [rsp+48h+arg_28]
0x180001345  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001349  movzx   eax, word ptr [rdx+1]
0x18000134d  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x180001351  mov     rax, [rdx+3]
0x180001355  add     rdx, 0Bh
0x180001359  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18000135e  mov     rax, [rcx+8]
0x180001362  mov     [r8], rax
0x180001365  mov     rax, [rcx+8]
0x180001369  mov     [rsp+48h+UserData], r8; UserData
0x18000136e  movzx   ecx, word ptr [rax]
0x180001371  mov     [r8+8], ecx
0x180001375  lea     rcx, _TraceLoggingMetadata
0x18000137c  mov     [r8+10h], rdx
0x180001380  mov     dword ptr [r8+0Ch], 2
0x180001388  movzx   eax, word ptr [rdx]
0x18000138b  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180001390  mov     [r8+18h], eax
0x180001394  lea     rax, _TraceLoggingMetadataEnd
0x18000139b  sub     eax, ecx
0x18000139d  mov     dword ptr [r8+1Ch], 1
0x1800013a5  mov     dword ptr [rsp+48h+arg_28], eax
0x1800013a9  mov     r8, r10; ActivityId
0x1800013ac  mov     eax, dword ptr [rsp+48h+arg_28]
0x1800013b0  mov     eax, [rsp+48h+arg_20]
0x1800013b4  mov     rcx, [r11+20h]; RegHandle
0x1800013b8  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1800013bc  call    cs:__imp_EventWriteTransfer
0x1800013c3  nop     dword ptr [rax+rax+00h]
0x1800013c8  add     rsp, 48h
0x1800013cc  retn
```
