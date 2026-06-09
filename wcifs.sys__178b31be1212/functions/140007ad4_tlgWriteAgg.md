# _tlgWriteAgg

- ea: `0x140007ad4`
- end: `0x140007baa`
- name: `_tlgWriteAgg`
- size: `214`
- prototype: `NTSTATUS __fastcall(__int64, unsigned __int8 *, __int64, __int64, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001b0bc`

## callees

- `0x1400074e4`
- `0x1400076a8`
- `0x140007ad4`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140007b97`
- `ntoskrnl!EtwWriteTransfer` at `0x140007b97`

## pseudocode

```c
NTSTATUS __fastcall tlgWriteAgg(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  ULONGLONG v5; // rax
  unsigned __int16 *v6; // rdx
  NTSTATUS result; // eax
  char AggregateFieldTypes; // al
  int v9; // ecx
  int v10; // r8d
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+30h] [rbp-18h] BYREF

  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  v5 = *(_QWORD *)(a2 + 3);
  v6 = (unsigned __int16 *)(a2 + 11);
  EventDescriptor.Keyword = v5;
  UserData->Ptr = (ULONGLONG)off_14000E068;
  UserData->Size = *(unsigned __int16 *)off_14000E068;
  UserData->Reserved = 2;
  UserData[1].Ptr = (ULONGLONG)v6;
  UserData[1].Size = *v6;
  UserData[1].Reserved = 1;
  result = -1073741811;
  if ( (void (__fastcall *)(const struct _GUID *, __int64, char, __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, _QWORD *))qword_14000E088 == TlgAggregateInternalRegisteredProviderEtwCallback )
  {
    AggregateFieldTypes = ExtractAggregateFieldTypes(TlgAggregateInternalRegisteredProviderEtwCallback, UserData);
    if ( AggregateFieldTypes )
      return InsertEventEntryInLookUpTable(
               v9,
               (unsigned int)&EventDescriptor,
               v10,
               (_DWORD)UserData,
               AggregateFieldTypes);
    else
      return EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 0xBu, UserData);
  }
  return result;
}

```

## disassembly

```asm
0x140007ad4  mov     [rsp+arg_18], r9d
0x140007ad9  push    rbx
0x140007ada  sub     rsp, 40h
0x140007ade  movzx   eax, byte ptr [rdx]
0x140007ae1  mov     rbx, [rsp+48h+arg_20]
0x140007ae6  shl     eax, 18h
0x140007ae9  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x140007aed  movzx   eax, word ptr [rdx+1]
0x140007af1  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x140007af5  mov     rax, [rdx+3]
0x140007af9  add     rdx, 0Bh
0x140007afd  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x140007b02  mov     rax, cs:off_14000E068
0x140007b09  mov     [rbx], rax
0x140007b0c  mov     rax, cs:off_14000E068
0x140007b13  movzx   ecx, word ptr [rax]
0x140007b16  mov     [rbx+8], ecx
0x140007b19  lea     rcx, _TraceLoggingMetadata
0x140007b20  mov     dword ptr [rbx+0Ch], 2
0x140007b27  mov     [rbx+10h], rdx
0x140007b2b  movzx   eax, word ptr [rdx]
0x140007b2e  mov     [rbx+18h], eax
0x140007b31  lea     rax, _TraceLoggingMetadataEnd
0x140007b38  sub     eax, ecx
0x140007b3a  mov     dword ptr [rbx+1Ch], 1
0x140007b41  mov     [rsp+48h+arg_18], eax
0x140007b45  lea     rcx, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x140007b4c  mov     eax, [rsp+48h+arg_18]
0x140007b50  cmp     cs:qword_14000E088, rcx
0x140007b57  mov     eax, 0C000000Dh
0x140007b5c  jnz     short loc_140007BA3
0x140007b5e  mov     rdx, rbx
0x140007b61  call    ExtractAggregateFieldTypes
0x140007b66  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140007b6b  test    al, al
0x140007b6d  jz      short loc_140007B7D
0x140007b6f  mov     r9, rbx
0x140007b72  mov     byte ptr [rsp+48h+UserDataCount], al
0x140007b76  call    InsertEventEntryInLookUpTable
0x140007b7b  jmp     short loc_140007BA3
0x140007b7d  mov     rcx, cs:RegHandle; RegHandle
0x140007b84  xor     r9d, r9d; RelatedActivityId
0x140007b87  mov     [rsp+48h+UserData], rbx; UserData
0x140007b8c  xor     r8d, r8d; ActivityId
0x140007b8f  mov     [rsp+48h+UserDataCount], 0Bh; UserDataCount
0x140007b97  call    cs:__imp_EtwWriteTransfer
0x140007b9e  nop     dword ptr [rax+rax+00h]
0x140007ba3  add     rsp, 40h
0x140007ba7  pop     rbx
0x140007ba8  retn
```
