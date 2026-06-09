# _tlgWriteAgg

- ea: `0x140009c14`
- end: `0x140009cfa`
- name: `_tlgWriteAgg`
- size: `230`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000b1e8`
- `0x14000b4a4`

## callees

- `0x140009c14`
- `0x140009d00`
- `0x140009d88`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140009ce2`
- `ntoskrnl!EtwWriteTransfer` at `0x140009ce2`

## pseudocode

```c
NTSTATUS __fastcall tlgWriteAgg(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        unsigned __int8 a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  ULONGLONG v6; // rax
  unsigned __int16 *v7; // rdx
  NTSTATUS result; // eax
  char AggregateFieldTypes; // al
  int v10; // ecx
  int v11; // r8d
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+30h] [rbp-18h] BYREF

  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  v6 = *(_QWORD *)(a2 + 3);
  v7 = (unsigned __int16 *)(a2 + 11);
  EventDescriptor.Keyword = v6;
  UserData->Ptr = (ULONGLONG)off_140018018;
  UserData->Size = *(unsigned __int16 *)off_140018018;
  UserData->Reserved = 2;
  UserData[1].Ptr = (ULONGLONG)v7;
  UserData[1].Size = *v7;
  UserData[1].Reserved = 1;
  result = -1073741811;
  if ( (void (__fastcall *)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))qword_140018038 == TlgAggregateInternalRegisteredProviderEtwCallback )
  {
    AggregateFieldTypes = ExtractAggregateFieldTypes(TlgAggregateInternalRegisteredProviderEtwCallback, UserData);
    if ( AggregateFieldTypes )
    {
      LOBYTE(v11) = a4;
      return InsertEventEntryInLookUpTable(
               v10,
               (unsigned int)&EventDescriptor,
               v11,
               (_DWORD)UserData,
               AggregateFieldTypes);
    }
    else
    {
      return EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, a4, UserData);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140009c14  mov     [rsp+arg_0], rbx
0x140009c19  mov     [rsp+arg_10], r8
0x140009c1e  push    rdi
0x140009c1f  sub     rsp, 40h
0x140009c23  movzx   eax, byte ptr [rdx]
0x140009c26  mov     edi, r9d
0x140009c29  mov     rbx, [rsp+48h+arg_20]
0x140009c2e  shl     eax, 18h
0x140009c31  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x140009c35  movzx   eax, word ptr [rdx+1]
0x140009c39  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x140009c3d  mov     rax, [rdx+3]
0x140009c41  add     rdx, 0Bh
0x140009c45  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x140009c4a  mov     rax, cs:off_140018018
0x140009c51  mov     [rbx], rax
0x140009c54  mov     rax, cs:off_140018018
0x140009c5b  movzx   ecx, word ptr [rax]
0x140009c5e  mov     [rbx+8], ecx
0x140009c61  lea     rcx, _TraceLoggingMetadata
0x140009c68  mov     dword ptr [rbx+0Ch], 2
0x140009c6f  mov     [rbx+10h], rdx
0x140009c73  movzx   eax, word ptr [rdx]
0x140009c76  mov     [rbx+18h], eax
0x140009c79  lea     rax, _TraceLoggingMetadataEnd
0x140009c80  sub     eax, ecx
0x140009c82  mov     dword ptr [rbx+1Ch], 1
0x140009c89  mov     dword ptr [rsp+48h+arg_10], eax
0x140009c8d  lea     rcx, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x140009c94  mov     eax, dword ptr [rsp+48h+arg_10]
0x140009c98  cmp     cs:qword_140018038, rcx
0x140009c9f  mov     eax, 0C000000Dh
0x140009ca4  jnz     short loc_140009CEE
0x140009ca6  mov     rdx, rbx
0x140009ca9  call    ExtractAggregateFieldTypes
0x140009cae  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x140009cb3  test    al, al
0x140009cb5  jz      short loc_140009CC8
0x140009cb7  mov     r9, rbx
0x140009cba  mov     byte ptr [rsp+48h+UserDataCount], al
0x140009cbe  mov     r8b, dil
0x140009cc1  call    InsertEventEntryInLookUpTable
0x140009cc6  jmp     short loc_140009CEE
0x140009cc8  mov     rcx, cs:RegHandle; RegHandle
0x140009ccf  xor     r9d, r9d; RelatedActivityId
0x140009cd2  movzx   eax, dil
0x140009cd6  xor     r8d, r8d; ActivityId
0x140009cd9  mov     [rsp+48h+UserData], rbx; UserData
0x140009cde  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x140009ce2  call    cs:__imp_EtwWriteTransfer
0x140009ce9  nop     dword ptr [rax+rax+00h]
0x140009cee  mov     rbx, [rsp+48h+arg_0]
0x140009cf3  add     rsp, 40h
0x140009cf7  pop     rdi
0x140009cf8  retn
```
