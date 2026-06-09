# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1400012c8`
- end: `0x14000137b`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `179`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140001008`
- `0x1400010cc`
- `0x140001174`
- `0x140001238`
- `0x1400013b0`
- `0x140001448`

## callees

- `0x140025aa0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001363`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140001363`

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
0x1400012c8  sub     rsp, 58h
0x1400012cc  mov     rax, cs:__security_cookie
0x1400012d3  xor     rax, rsp
0x1400012d6  mov     [rsp+58h+var_10], rax
0x1400012db  movzx   eax, byte ptr [rdx]
0x1400012de  mov     r11, rcx
0x1400012e1  mov     r10, [rsp+58h+arg_28]
0x1400012e9  shl     eax, 18h
0x1400012ec  mov     dword ptr [rsp+58h+EventDescriptor.Id], eax
0x1400012f0  movzx   eax, word ptr [rdx+1]
0x1400012f4  mov     dword ptr [rsp+58h+EventDescriptor.Level], eax
0x1400012f8  mov     rax, [rdx+3]
0x1400012fc  add     rdx, 0Bh
0x140001300  mov     [rsp+58h+EventDescriptor.Keyword], rax
0x140001305  mov     rax, [rcx+8]
0x140001309  mov     [r10], rax
0x14000130c  mov     rax, [rcx+8]
0x140001310  mov     [rsp+58h+UserData], r10; UserData
0x140001315  movzx   ecx, word ptr [rax]
0x140001318  mov     [r10+8], ecx
0x14000131c  lea     rcx, _TraceLoggingMetadata
0x140001323  mov     [r10+10h], rdx
0x140001327  mov     dword ptr [r10+0Ch], 2
0x14000132f  movzx   eax, word ptr [rdx]
0x140001332  lea     rdx, [rsp+58h+EventDescriptor]; EventDescriptor
0x140001337  mov     [r10+18h], eax
0x14000133b  lea     rax, _TraceLoggingMetadataEnd
0x140001342  sub     eax, ecx
0x140001344  mov     dword ptr [r10+1Ch], 1
0x14000134c  mov     [rsp+58h+var_28], eax
0x140001350  mov     eax, [rsp+58h+var_28]
0x140001354  mov     eax, [rsp+58h+arg_20]
0x14000135b  mov     rcx, [r11+20h]; RegHandle
0x14000135f  mov     [rsp+58h+UserDataCount], eax; UserDataCount
0x140001363  call    cs:__imp_EventWriteTransfer
0x140001369  mov     rcx, [rsp+58h+var_10]
0x14000136e  xor     rcx, rsp; StackCookie
0x140001371  call    __security_check_cookie
0x140001376  add     rsp, 58h
0x14000137a  retn
```
