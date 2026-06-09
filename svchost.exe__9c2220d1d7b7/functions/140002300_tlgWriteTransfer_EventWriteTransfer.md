# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x140002300`
- end: `0x1400023a9`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `169`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140002cb0`
- `0x140006cbc`
- `0x1400086f8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140002397`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140002397`

## pseudocode

```c
ULONG __fastcall tlgWriteTransfer_EventWriteTransfer(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
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
  UserData->Ptr = (ULONGLONG)off_14000F008;
  UserData->Size = *(unsigned __int16 *)off_14000F008;
  UserData[1].Ptr = (ULONGLONG)v7;
  UserData->Reserved = 2;
  UserData[1].Size = *v7;
  UserData[1].Reserved = 1;
  return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x140002300  mov     [rsp+arg_18], r9
0x140002305  sub     rsp, 48h
0x140002309  movzx   eax, byte ptr [rdx]
0x14000230c  xor     r9d, r9d; RelatedActivityId
0x14000230f  mov     r8, [rsp+48h+arg_28]
0x140002314  shl     eax, 18h
0x140002317  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x14000231b  movzx   eax, word ptr [rdx+1]
0x14000231f  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x140002323  mov     rax, [rdx+3]
0x140002327  add     rdx, 0Bh
0x14000232b  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x140002330  mov     rax, cs:off_14000F008
0x140002337  mov     [r8], rax
0x14000233a  mov     rax, cs:off_14000F008
0x140002341  mov     [rsp+48h+UserData], r8; UserData
0x140002346  movzx   ecx, word ptr [rax]
0x140002349  mov     [r8+8], ecx
0x14000234d  lea     rcx, _TraceLoggingMetadata
0x140002354  mov     [r8+10h], rdx
0x140002358  mov     dword ptr [r8+0Ch], 2
0x140002360  movzx   eax, word ptr [rdx]
0x140002363  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140002368  mov     [r8+18h], eax
0x14000236c  lea     rax, _TraceLoggingMetadataEnd
0x140002373  sub     eax, ecx
0x140002375  mov     dword ptr [r8+1Ch], 1
0x14000237d  mov     dword ptr [rsp+48h+arg_18], eax
0x140002381  xor     r8d, r8d; ActivityId
0x140002384  mov     eax, dword ptr [rsp+48h+arg_18]
0x140002388  mov     eax, [rsp+48h+arg_20]
0x14000238c  mov     rcx, cs:RegHandle; RegHandle
0x140002393  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x140002397  call    cs:__imp_EventWriteTransfer
0x14000239e  nop     dword ptr [rax+rax+00h]
0x1400023a3  add     rsp, 48h
0x1400023a7  retn
```
