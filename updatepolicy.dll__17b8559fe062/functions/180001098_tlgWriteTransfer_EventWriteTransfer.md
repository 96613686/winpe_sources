# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001098`
- end: `0x18000114b`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `179`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001008`
- `0x18000d910`

## callees

- `0x18000ed40`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001133`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180001133`

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
0x180001098  sub     rsp, 58h
0x18000109c  mov     rax, cs:__security_cookie
0x1800010a3  xor     rax, rsp
0x1800010a6  mov     [rsp+58h+var_10], rax
0x1800010ab  movzx   eax, byte ptr [rdx]
0x1800010ae  mov     r11, rcx
0x1800010b1  mov     r10, [rsp+58h+arg_28]
0x1800010b9  shl     eax, 18h
0x1800010bc  mov     dword ptr [rsp+58h+EventDescriptor.Id], eax
0x1800010c0  movzx   eax, word ptr [rdx+1]
0x1800010c4  mov     dword ptr [rsp+58h+EventDescriptor.Level], eax
0x1800010c8  mov     rax, [rdx+3]
0x1800010cc  add     rdx, 0Bh
0x1800010d0  mov     [rsp+58h+EventDescriptor.Keyword], rax
0x1800010d5  mov     rax, [rcx+8]
0x1800010d9  mov     [r10], rax
0x1800010dc  mov     rax, [rcx+8]
0x1800010e0  mov     [rsp+58h+UserData], r10; UserData
0x1800010e5  movzx   ecx, word ptr [rax]
0x1800010e8  mov     [r10+8], ecx
0x1800010ec  lea     rcx, _TraceLoggingMetadata
0x1800010f3  mov     [r10+10h], rdx
0x1800010f7  mov     dword ptr [r10+0Ch], 2
0x1800010ff  movzx   eax, word ptr [rdx]
0x180001102  lea     rdx, [rsp+58h+EventDescriptor]; EventDescriptor
0x180001107  mov     [r10+18h], eax
0x18000110b  lea     rax, _TraceLoggingMetadataEnd
0x180001112  sub     eax, ecx
0x180001114  mov     dword ptr [r10+1Ch], 1
0x18000111c  mov     [rsp+58h+var_28], eax
0x180001120  mov     eax, [rsp+58h+var_28]
0x180001124  mov     eax, [rsp+58h+arg_20]
0x18000112b  mov     rcx, [r11+20h]; RegHandle
0x18000112f  mov     [rsp+58h+UserDataCount], eax; UserDataCount
0x180001133  call    cs:__imp_EventWriteTransfer
0x180001139  mov     rcx, [rsp+58h+var_10]
0x18000113e  xor     rcx, rsp; StackCookie
0x180001141  call    __security_check_cookie
0x180001146  add     rsp, 58h
0x18000114a  retn
```
