# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x18000219c`
- end: `0x18000223a`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `158`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001e3c`
- `0x180001ee8`
- `0x18001ac14`
- `0x18001adcc`
- `0x18001aef0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180002228`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180002228`

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
0x18000219c  sub     rsp, 48h
0x1800021a0  movzx   eax, byte ptr [rdx]
0x1800021a3  mov     r11, rcx
0x1800021a6  shl     eax, 18h
0x1800021a9  mov     r10, r8
0x1800021ac  mov     r8, [rsp+48h+arg_28]
0x1800021b1  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1800021b5  movzx   eax, word ptr [rdx+1]
0x1800021b9  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1800021bd  mov     rax, [rdx+3]
0x1800021c1  add     rdx, 0Bh
0x1800021c5  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1800021ca  mov     rax, [rcx+8]
0x1800021ce  mov     [r8], rax
0x1800021d1  mov     rax, [rcx+8]
0x1800021d5  mov     [rsp+48h+UserData], r8; UserData
0x1800021da  movzx   ecx, word ptr [rax]
0x1800021dd  mov     [r8+8], ecx
0x1800021e1  lea     rcx, _TraceLoggingMetadata
0x1800021e8  mov     [r8+10h], rdx
0x1800021ec  mov     dword ptr [r8+0Ch], 2
0x1800021f4  movzx   eax, word ptr [rdx]
0x1800021f7  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800021fc  mov     [r8+18h], eax
0x180002200  lea     rax, _TraceLoggingMetadataEnd
0x180002207  sub     eax, ecx
0x180002209  mov     dword ptr [r8+1Ch], 1
0x180002211  mov     dword ptr [rsp+48h+arg_28], eax
0x180002215  mov     r8, r10; ActivityId
0x180002218  mov     eax, dword ptr [rsp+48h+arg_28]
0x18000221c  mov     eax, [rsp+48h+arg_20]
0x180002220  mov     rcx, [r11+20h]; RegHandle
0x180002224  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x180002228  call    cs:__imp_EventWriteTransfer
0x18000222f  nop     dword ptr [rax+rax+00h]
0x180002234  add     rsp, 48h
0x180002238  retn
```
