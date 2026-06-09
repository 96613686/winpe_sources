# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x18000140c`
- end: `0x1800014bf`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `179`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180001158`
- `0x1800014c8`
- `0x1800017c0`
- `0x18000ead0`

## callees

- `0x18000fce0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800014a7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800014a7`

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
0x18000140c  sub     rsp, 58h
0x180001410  mov     rax, cs:__security_cookie
0x180001417  xor     rax, rsp
0x18000141a  mov     [rsp+58h+var_10], rax
0x18000141f  movzx   eax, byte ptr [rdx]
0x180001422  mov     r11, rcx
0x180001425  mov     r10, [rsp+58h+arg_28]
0x18000142d  shl     eax, 18h
0x180001430  mov     dword ptr [rsp+58h+EventDescriptor.Id], eax
0x180001434  movzx   eax, word ptr [rdx+1]
0x180001438  mov     dword ptr [rsp+58h+EventDescriptor.Level], eax
0x18000143c  mov     rax, [rdx+3]
0x180001440  add     rdx, 0Bh
0x180001444  mov     [rsp+58h+EventDescriptor.Keyword], rax
0x180001449  mov     rax, [rcx+8]
0x18000144d  mov     [r10], rax
0x180001450  mov     rax, [rcx+8]
0x180001454  mov     [rsp+58h+UserData], r10; UserData
0x180001459  movzx   ecx, word ptr [rax]
0x18000145c  mov     [r10+8], ecx
0x180001460  lea     rcx, _TraceLoggingMetadata
0x180001467  mov     [r10+10h], rdx
0x18000146b  mov     dword ptr [r10+0Ch], 2
0x180001473  movzx   eax, word ptr [rdx]
0x180001476  lea     rdx, [rsp+58h+EventDescriptor]; EventDescriptor
0x18000147b  mov     [r10+18h], eax
0x18000147f  lea     rax, _TraceLoggingMetadataEnd
0x180001486  sub     eax, ecx
0x180001488  mov     dword ptr [r10+1Ch], 1
0x180001490  mov     [rsp+58h+var_28], eax
0x180001494  mov     eax, [rsp+58h+var_28]
0x180001498  mov     eax, [rsp+58h+arg_20]
0x18000149f  mov     rcx, [r11+20h]; RegHandle
0x1800014a3  mov     [rsp+58h+UserDataCount], eax; UserDataCount
0x1800014a7  call    cs:__imp_EventWriteTransfer
0x1800014ad  mov     rcx, [rsp+58h+var_10]
0x1800014b2  xor     rcx, rsp; StackCookie
0x1800014b5  call    __security_check_cookie
0x1800014ba  add     rsp, 58h
0x1800014be  retn
```
