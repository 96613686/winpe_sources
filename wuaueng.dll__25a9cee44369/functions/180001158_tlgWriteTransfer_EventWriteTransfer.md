# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x180001158`
- end: `0x18000120b`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `179`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *, const GUID *, const GUID *, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180001214`
- `0x1800014c8`
- `0x1800017c0`
- `0x18000ea80`

## callees

- `0x18000fc90`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800011f3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800011f3`

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
0x180001158  sub     rsp, 58h
0x18000115c  mov     rax, cs:__security_cookie
0x180001163  xor     rax, rsp
0x180001166  mov     [rsp+58h+var_10], rax
0x18000116b  movzx   eax, byte ptr [rdx]
0x18000116e  mov     r11, rcx
0x180001171  mov     r10, [rsp+58h+arg_28]
0x180001179  shl     eax, 18h
0x18000117c  mov     dword ptr [rsp+58h+EventDescriptor.Id], eax
0x180001180  movzx   eax, word ptr [rdx+1]
0x180001184  mov     dword ptr [rsp+58h+EventDescriptor.Level], eax
0x180001188  mov     rax, [rdx+3]
0x18000118c  add     rdx, 0Bh
0x180001190  mov     [rsp+58h+EventDescriptor.Keyword], rax
0x180001195  mov     rax, [rcx+8]
0x180001199  mov     [r10], rax
0x18000119c  mov     rax, [rcx+8]
0x1800011a0  mov     [rsp+58h+UserData], r10; UserData
0x1800011a5  movzx   ecx, word ptr [rax]
0x1800011a8  mov     [r10+8], ecx
0x1800011ac  lea     rcx, _TraceLoggingMetadata
0x1800011b3  mov     [r10+10h], rdx
0x1800011b7  mov     dword ptr [r10+0Ch], 2
0x1800011bf  movzx   eax, word ptr [rdx]
0x1800011c2  lea     rdx, [rsp+58h+EventDescriptor]; EventDescriptor
0x1800011c7  mov     [r10+18h], eax
0x1800011cb  lea     rax, _TraceLoggingMetadataEnd
0x1800011d2  sub     eax, ecx
0x1800011d4  mov     dword ptr [r10+1Ch], 1
0x1800011dc  mov     [rsp+58h+var_28], eax
0x1800011e0  mov     eax, [rsp+58h+var_28]
0x1800011e4  mov     eax, [rsp+58h+arg_20]
0x1800011eb  mov     rcx, [r11+20h]; RegHandle
0x1800011ef  mov     [rsp+58h+UserDataCount], eax; UserDataCount
0x1800011f3  call    cs:__imp_EventWriteTransfer
0x1800011f9  mov     rcx, [rsp+58h+var_10]
0x1800011fe  xor     rcx, rsp; StackCookie
0x180001201  call    __security_check_cookie
0x180001206  add     rsp, 58h
0x18000120a  retn
```
