# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x18000109c`
- end: `0x18000114f`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `179`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `30`
- callee_count: `1`
- tags: ``

## callers

- `0x180001158`
- `0x18000140c`
- `0x180001704`
- `0x1800017b0`
- `0x1800018a4`
- `0x180008c48`
- `0x180008e30`
- `0x180008fc4`
- `0x180009180`
- `0x180009300`
- `0x1800094bc`
- `0x1800096d4`
- `0x180009938`
- `0x18003b804`
- `0x18003babc`
- `0x18003bc5c`
- `0x18003beac`
- `0x18003c114`
- `0x18003c3b8`
- `0x18003c56c`
- `0x18003c7f8`
- `0x18003c978`
- `0x18003cb54`
- `0x18003d5e0`
- `0x18003d7a8`
- `0x18003d8e4`
- `0x18003da28`
- `0x18003e358`
- `0x18003e548`
- `0x18003e64c`

## callees

- `0x1800427d0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001137`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001137`

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
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-20h] BYREF

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
0x18000109c  sub     rsp, 58h
0x1800010a0  mov     rax, cs:__security_cookie
0x1800010a7  xor     rax, rsp
0x1800010aa  mov     [rsp+58h+var_10], rax
0x1800010af  movzx   eax, byte ptr [rdx]
0x1800010b2  mov     r11, rcx
0x1800010b5  mov     r10, [rsp+58h+arg_28]
0x1800010bd  shl     eax, 18h
0x1800010c0  mov     dword ptr [rsp+58h+EventDescriptor.Id], eax
0x1800010c4  movzx   eax, word ptr [rdx+1]
0x1800010c8  mov     dword ptr [rsp+58h+EventDescriptor.Level], eax
0x1800010cc  mov     rax, [rdx+3]
0x1800010d0  add     rdx, 0Bh
0x1800010d4  mov     [rsp+58h+EventDescriptor.Keyword], rax
0x1800010d9  mov     rax, [rcx+8]
0x1800010dd  mov     [r10], rax
0x1800010e0  mov     rax, [rcx+8]
0x1800010e4  mov     [rsp+58h+UserData], r10; UserData
0x1800010e9  movzx   ecx, word ptr [rax]
0x1800010ec  mov     [r10+8], ecx
0x1800010f0  lea     rcx, _TraceLoggingMetadata
0x1800010f7  mov     [r10+10h], rdx
0x1800010fb  mov     dword ptr [r10+0Ch], 2
0x180001103  movzx   eax, word ptr [rdx]
0x180001106  lea     rdx, [rsp+58h+EventDescriptor]; EventDescriptor
0x18000110b  mov     [r10+18h], eax
0x18000110f  lea     rax, _TraceLoggingMetadataEnd
0x180001116  sub     eax, ecx
0x180001118  mov     dword ptr [r10+1Ch], 1
0x180001120  mov     [rsp+58h+var_28], eax
0x180001124  mov     eax, [rsp+58h+var_28]
0x180001128  mov     eax, [rsp+58h+arg_20]
0x18000112f  mov     rcx, [r11+20h]; RegHandle
0x180001133  mov     [rsp+58h+UserDataCount], eax; UserDataCount
0x180001137  call    cs:__imp_EventWriteTransfer
0x18000113d  mov     rcx, [rsp+58h+var_10]
0x180001142  xor     rcx, rsp; StackCookie
0x180001145  call    __security_check_cookie
0x18000114a  add     rsp, 58h
0x18000114e  retn
```
