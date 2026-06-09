# _tlgWriteTransfer_EtwWriteTransfer

- ea: `0x140001030`
- end: `0x1400010ce`
- name: `_tlgWriteTransfer_EtwWriteTransfer`
- size: `158`
- prototype: ``
- caller_count: `21`
- callee_count: `0`
- tags: ``

## callers

- `0x1400010d4`
- `0x140014c90`
- `0x140019c40`
- `0x140019da0`
- `0x14001a20c`
- `0x14001b0bc`
- `0x14001b524`
- `0x14001c244`
- `0x14001c688`
- `0x140023644`
- `0x1400241c4`
- `0x140026210`
- `0x140026de0`
- `0x140027f24`
- `0x14002da54`
- `0x1400303e8`
- `0x140030d54`
- `0x1400318f0`
- `0x140032500`
- `0x1400328d8`
- `0x140033f90`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x1400010bc`
- `ntoskrnl!EtwWriteTransfer` at `0x1400010bc`

## pseudocode

```c
NTSTATUS __fastcall tlgWriteTransfer_EtwWriteTransfer(
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
  return EtwWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, a4, UserDataCount, UserData);
}

```

## disassembly

```asm
0x140001030  sub     rsp, 48h
0x140001034  movzx   eax, byte ptr [rdx]
0x140001037  mov     r11, rcx
0x14000103a  shl     eax, 18h
0x14000103d  mov     r10, r8
0x140001040  mov     r8, [rsp+48h+arg_28]
0x140001045  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x140001049  movzx   eax, word ptr [rdx+1]
0x14000104d  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x140001051  mov     rax, [rdx+3]
0x140001055  add     rdx, 0Bh
0x140001059  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x14000105e  mov     rax, [rcx+8]
0x140001062  mov     [r8], rax
0x140001065  mov     rax, [rcx+8]
0x140001069  mov     [rsp+48h+UserData], r8; UserData
0x14000106e  movzx   ecx, word ptr [rax]
0x140001071  mov     [r8+8], ecx
0x140001075  lea     rcx, _TraceLoggingMetadata
0x14000107c  mov     [r8+10h], rdx
0x140001080  mov     dword ptr [r8+0Ch], 2
0x140001088  movzx   eax, word ptr [rdx]
0x14000108b  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140001090  mov     [r8+18h], eax
0x140001094  lea     rax, _TraceLoggingMetadataEnd
0x14000109b  sub     eax, ecx
0x14000109d  mov     dword ptr [r8+1Ch], 1
0x1400010a5  mov     dword ptr [rsp+48h+arg_28], eax
0x1400010a9  mov     r8, r10; ActivityId
0x1400010ac  mov     eax, dword ptr [rsp+48h+arg_28]
0x1400010b0  mov     eax, [rsp+48h+arg_20]
0x1400010b4  mov     rcx, [r11+20h]; RegHandle
0x1400010b8  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x1400010bc  call    cs:__imp_EtwWriteTransfer
0x1400010c3  nop     dword ptr [rax+rax+00h]
0x1400010c8  add     rsp, 48h
0x1400010cc  retn
```
