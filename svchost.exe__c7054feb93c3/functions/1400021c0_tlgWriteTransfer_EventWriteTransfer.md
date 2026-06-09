# _tlgWriteTransfer_EventWriteTransfer

- ea: `0x1400021c0`
- end: `0x140002262`
- name: `_tlgWriteTransfer_EventWriteTransfer`
- size: `162`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140002a40`
- `0x1400067dc`
- `0x140008124`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140002257`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140002257`

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
  UserData->Size = (unsigned __int16)*off_14000F008;
  UserData[1].Ptr = (ULONGLONG)v7;
  UserData->Reserved = 2;
  UserData[1].Size = *v7;
  UserData[1].Reserved = 1;
  return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x1400021c0  mov     [rsp+arg_18], r9
0x1400021c5  sub     rsp, 48h
0x1400021c9  movzx   eax, byte ptr [rdx]
0x1400021cc  xor     r9d, r9d; RelatedActivityId
0x1400021cf  mov     r8, [rsp+48h+arg_28]
0x1400021d4  shl     eax, 18h
0x1400021d7  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x1400021db  movzx   eax, word ptr [rdx+1]
0x1400021df  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x1400021e3  mov     rax, [rdx+3]
0x1400021e7  add     rdx, 0Bh
0x1400021eb  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x1400021f0  mov     rax, cs:off_14000F008
0x1400021f7  mov     [r8], rax
0x1400021fa  mov     rax, cs:off_14000F008
0x140002201  mov     [rsp+48h+UserData], r8; UserData
0x140002206  movzx   ecx, word ptr [rax]
0x140002209  mov     [r8+8], ecx
0x14000220d  lea     rcx, _TraceLoggingMetadata
0x140002214  mov     [r8+10h], rdx
0x140002218  mov     dword ptr [r8+0Ch], 2
0x140002220  movzx   eax, word ptr [rdx]
0x140002223  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140002228  mov     [r8+18h], eax
0x14000222c  lea     rax, _TraceLoggingMetadataEnd
0x140002233  sub     eax, ecx
0x140002235  mov     dword ptr [r8+1Ch], 1
0x14000223d  mov     dword ptr [rsp+48h+arg_18], eax
0x140002241  xor     r8d, r8d; ActivityId
0x140002244  mov     eax, dword ptr [rsp+48h+arg_18]
0x140002248  mov     eax, [rsp+48h+arg_20]
0x14000224c  mov     rcx, cs:RegHandle; RegHandle
0x140002253  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x140002257  call    cs:__imp_EventWriteTransfer
0x14000225d  add     rsp, 48h
0x140002261  retn
```
