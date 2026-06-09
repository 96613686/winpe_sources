# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1800015b4`
- end: `0x180001667`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `179`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180001008`
- `0x1800012bc`
- `0x1800017b8`
- `0x180026db4`
- `0x180026fd0`
- `0x18003e380`

## callees

- `0x180042630`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000164f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000164f`

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
0x1800015b4  sub     rsp, 58h
0x1800015b8  mov     rax, cs:__security_cookie
0x1800015bf  xor     rax, rsp
0x1800015c2  mov     [rsp+58h+var_10], rax
0x1800015c7  movzx   eax, byte ptr [rdx]
0x1800015ca  mov     r11, rcx
0x1800015cd  mov     r10, [rsp+58h+arg_28]
0x1800015d5  shl     eax, 18h
0x1800015d8  mov     dword ptr [rsp+58h+EventDescriptor.Id], eax
0x1800015dc  movzx   eax, word ptr [rdx+1]
0x1800015e0  mov     dword ptr [rsp+58h+EventDescriptor.Level], eax
0x1800015e4  mov     rax, [rdx+3]
0x1800015e8  add     rdx, 0Bh
0x1800015ec  mov     [rsp+58h+EventDescriptor.Keyword], rax
0x1800015f1  mov     rax, [rcx+8]
0x1800015f5  mov     [r10], rax
0x1800015f8  mov     rax, [rcx+8]
0x1800015fc  mov     [rsp+58h+UserData], r10; UserData
0x180001601  movzx   ecx, word ptr [rax]
0x180001604  mov     [r10+8], ecx
0x180001608  lea     rcx, _TraceLoggingMetadata
0x18000160f  mov     [r10+10h], rdx
0x180001613  mov     dword ptr [r10+0Ch], 2
0x18000161b  movzx   eax, word ptr [rdx]
0x18000161e  lea     rdx, [rsp+58h+EventDescriptor]; EventDescriptor
0x180001623  mov     [r10+18h], eax
0x180001627  lea     rax, _TraceLoggingMetadataEnd
0x18000162e  sub     eax, ecx
0x180001630  mov     dword ptr [r10+1Ch], 1
0x180001638  mov     [rsp+58h+var_28], eax
0x18000163c  mov     eax, [rsp+58h+var_28]
0x180001640  mov     eax, [rsp+58h+arg_20]
0x180001647  mov     rcx, [r11+20h]; RegHandle
0x18000164b  mov     [rsp+58h+UserDataCount], eax; UserDataCount
0x18000164f  call    cs:__imp_EventWriteTransfer
0x180001655  mov     rcx, [rsp+58h+var_10]
0x18000165a  xor     rcx, rsp; StackCookie
0x18000165d  call    __security_check_cookie
0x180001662  add     rsp, 58h
0x180001666  retn
```
