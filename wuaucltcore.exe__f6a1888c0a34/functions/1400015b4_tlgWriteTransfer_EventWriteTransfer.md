# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1400015b4`
- end: `0x140001667`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `179`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140001008`
- `0x1400012bc`
- `0x1400017b8`
- `0x1400112c0`

## callees

- `0x14001aa60`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14000164f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14000164f`

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
0x1400015b4  sub     rsp, 58h
0x1400015b8  mov     rax, cs:__security_cookie
0x1400015bf  xor     rax, rsp
0x1400015c2  mov     [rsp+58h+var_10], rax
0x1400015c7  movzx   eax, byte ptr [rdx]
0x1400015ca  mov     r11, rcx
0x1400015cd  mov     r10, [rsp+58h+arg_28]
0x1400015d5  shl     eax, 18h
0x1400015d8  mov     dword ptr [rsp+58h+EventDescriptor.Id], eax
0x1400015dc  movzx   eax, word ptr [rdx+1]
0x1400015e0  mov     dword ptr [rsp+58h+EventDescriptor.Level], eax
0x1400015e4  mov     rax, [rdx+3]
0x1400015e8  add     rdx, 0Bh
0x1400015ec  mov     [rsp+58h+EventDescriptor.Keyword], rax
0x1400015f1  mov     rax, [rcx+8]
0x1400015f5  mov     [r10], rax
0x1400015f8  mov     rax, [rcx+8]
0x1400015fc  mov     [rsp+58h+UserData], r10; UserData
0x140001601  movzx   ecx, word ptr [rax]
0x140001604  mov     [r10+8], ecx
0x140001608  lea     rcx, _TraceLoggingMetadata
0x14000160f  mov     [r10+10h], rdx
0x140001613  mov     dword ptr [r10+0Ch], 2
0x14000161b  movzx   eax, word ptr [rdx]
0x14000161e  lea     rdx, [rsp+58h+EventDescriptor]; EventDescriptor
0x140001623  mov     [r10+18h], eax
0x140001627  lea     rax, _TraceLoggingMetadataEnd
0x14000162e  sub     eax, ecx
0x140001630  mov     dword ptr [r10+1Ch], 1
0x140001638  mov     [rsp+58h+var_28], eax
0x14000163c  mov     eax, [rsp+58h+var_28]
0x140001640  mov     eax, [rsp+58h+arg_20]
0x140001647  mov     rcx, [r11+20h]; RegHandle
0x14000164b  mov     [rsp+58h+UserDataCount], eax; UserDataCount
0x14000164f  call    cs:__imp_EventWriteTransfer
0x140001655  mov     rcx, [rsp+58h+var_10]
0x14000165a  xor     rcx, rsp; StackCookie
0x14000165d  call    __security_check_cookie
0x140001662  add     rsp, 58h
0x140001666  retn
```
