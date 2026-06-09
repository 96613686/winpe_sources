# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x18000113c`
- end: `0x1800011d3`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `23`
- callee_count: `0`
- tags: ``

## callers

- `0x1800011dc`
- `0x18000126c`
- `0x18000134c`
- `0x1800013f8`
- `0x1800016d0`
- `0x180001794`
- `0x180001a48`
- `0x180001d40`
- `0x180001e38`
- `0x180005750`
- `0x180009d30`
- `0x18000e8a8`
- `0x18000ec60`
- `0x1800106f4`
- `0x1800127a8`
- `0x180012b4c`
- `0x1800167a4`
- `0x18001b3f8`
- `0x18001bccc`
- `0x180032024`
- `0x18003230c`
- `0x180032664`
- `0x1800327d0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800011c8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800011c8`

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
0x18000113c  sub     rsp, 48h
0x180001140  movzx   eax, byte ptr [rdx]
0x180001143  mov     r11, rcx
0x180001146  shl     eax, 18h
0x180001149  mov     r10, r8
0x18000114c  mov     r8, [rsp+48h+arg_28]
0x180001151  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x180001155  movzx   eax, word ptr [rdx+1]
0x180001159  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x18000115d  mov     rax, [rdx+3]
0x180001161  add     rdx, 0Bh
0x180001165  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x18000116a  mov     rax, [rcx+8]
0x18000116e  mov     [r8], rax
0x180001171  mov     rax, [rcx+8]
0x180001175  mov     [rsp+48h+UserData], r8; UserData
0x18000117a  movzx   ecx, word ptr [rax]
0x18000117d  mov     [r8+8], ecx
0x180001181  lea     rcx, _TraceLoggingMetadata
0x180001188  mov     [r8+10h], rdx
0x18000118c  mov     dword ptr [r8+0Ch], 2
0x180001194  movzx   eax, word ptr [rdx]
0x180001197  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x18000119c  mov     [r8+18h], eax
0x1800011a0  lea     rax, _TraceLoggingMetadataEnd
0x1800011a7  sub     eax, ecx
0x1800011a9  mov     dword ptr [r8+1Ch], 1
0x1800011b1  mov     dword ptr [rsp+48h+arg_28], eax
0x1800011b5  mov     r8, r10; ActivityId
0x1800011b8  mov     eax, dword ptr [rsp+48h+arg_28]
0x1800011bc  mov     eax, [rsp+48h+arg_20]
0x1800011c0  mov     rcx, [r11+20h]; RegHandle
0x1800011c4  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1800011c8  call    cs:__imp_EventWriteTransfer
0x1800011ce  add     rsp, 48h
0x1800011d2  retn
```
