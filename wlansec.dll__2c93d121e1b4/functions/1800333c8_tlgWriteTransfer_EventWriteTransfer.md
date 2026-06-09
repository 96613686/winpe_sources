# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1800333c8`
- end: `0x180033466`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `158`
- prototype: ``
- caller_count: `31`
- callee_count: `0`
- tags: ``

## callers

- `0x180001008`
- `0x18000113c`
- `0x1800013f0`
- `0x180001740`
- `0x1800017bc`
- `0x18000181c`
- `0x180001a60`
- `0x180001b08`
- `0x180001b54`
- `0x180001bd4`
- `0x180001ca4`
- `0x180001d5c`
- `0x180001e4c`
- `0x180001eac`
- `0x180002028`
- `0x180002140`
- `0x1800021a0`
- `0x180002218`
- `0x18000228c`
- `0x180002330`
- `0x180002460`
- `0x180002514`
- `0x1800025cc`
- `0x1800026cc`
- `0x180002744`
- `0x1800027bc`
- `0x18007f81c`
- `0x180080070`
- `0x1800826f0`
- `0x180083060`
- `0x180083198`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180033454`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180033454`

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
0x1800333c8  sub     rsp, 48h
0x1800333cc  movzx   eax, byte ptr [rdx]
0x1800333cf  mov     r11, rcx
0x1800333d2  shl     eax, 18h
0x1800333d5  mov     r10, r8
0x1800333d8  mov     r8, [rsp+48h+arg_28]
0x1800333dd  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1800333e1  movzx   eax, word ptr [rdx+1]
0x1800333e5  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1800333e9  mov     rax, [rdx+3]
0x1800333ed  add     rdx, 0Bh
0x1800333f1  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800333f6  mov     rax, [rcx+8]
0x1800333fa  mov     [r8], rax
0x1800333fd  mov     rax, [rcx+8]
0x180033401  mov     [rsp+48h+UserData], r8; UserData
0x180033406  movzx   ecx, word ptr [rax]
0x180033409  mov     [r8+8], ecx
0x18003340d  lea     rcx, _TraceLoggingMetadata
0x180033414  mov     [r8+10h], rdx
0x180033418  mov     dword ptr [r8+0Ch], 2
0x180033420  movzx   eax, word ptr [rdx]
0x180033423  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x180033428  mov     [r8+18h], eax
0x18003342c  lea     rax, _TraceLoggingMetadataEnd
0x180033433  sub     eax, ecx
0x180033435  mov     dword ptr [r8+1Ch], 1
0x18003343d  mov     dword ptr [rsp+48h+arg_28], eax
0x180033441  mov     r8, r10; ActivityId
0x180033444  mov     eax, dword ptr [rsp+48h+arg_28]
0x180033448  mov     eax, [rsp+48h+arg_20]
0x18003344c  mov     rcx, [r11+20h]; RegHandle
0x180033450  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180033454  call    cs:__imp_EventWriteTransfer
0x18003345b  nop     dword ptr [rax+rax+00h]
0x180033460  add     rsp, 48h
0x180033464  retn
```
