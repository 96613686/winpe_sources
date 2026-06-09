# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)

- ea: `0x1800010c0`
- end: `0x18000117c`
- name: `??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001a394`

## callees

- `0x180030700`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000115d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000115d`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        __int64 a1,
        unsigned __int8 *a2)
{
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-30h] BYREF
  unsigned __int8 *v5; // [rsp+58h] [rbp-20h]
  int v6; // [rsp+60h] [rbp-18h]
  int v7; // [rsp+64h] [rbp-14h]

  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_18005F178;
  UserData.Size = *(unsigned __int16 *)off_18005F178;
  v6 = *(unsigned __int16 *)(a2 + 11);
  v5 = a2 + 11;
  UserData.Reserved = 2;
  v7 = 1;
  return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
}

```

## disassembly

```asm
0x1800010c0  sub     rsp, 78h
0x1800010c4  mov     rax, cs:__security_cookie
0x1800010cb  xor     rax, rsp
0x1800010ce  mov     [rsp+78h+var_10], rax
0x1800010d3  movzx   eax, byte ptr [rdx]
0x1800010d6  lea     rcx, [rdx+0Bh]
0x1800010da  shl     eax, 18h
0x1800010dd  xor     r9d, r9d; RelatedActivityId
0x1800010e0  mov     dword ptr [rsp+78h+EventDescriptor.Id], eax
0x1800010e4  xor     r8d, r8d; ActivityId
0x1800010e7  movzx   eax, word ptr [rdx+1]
0x1800010eb  mov     dword ptr [rsp+78h+EventDescriptor.Level], eax
0x1800010ef  mov     rax, [rdx+3]
0x1800010f3  lea     rdx, [rsp+78h+EventDescriptor]; EventDescriptor
0x1800010f8  mov     [rsp+78h+EventDescriptor.Keyword], rax
0x1800010fd  mov     rax, cs:off_18005F178
0x180001104  mov     [rsp+78h+var_30.Ptr], rax
0x180001109  movzx   eax, word ptr [rax]
0x18000110c  mov     [rsp+78h+var_30.Size], eax
0x180001110  movzx   eax, word ptr [rcx]
0x180001113  mov     [rsp+78h+var_18], eax
0x180001117  lea     rax, _TraceLoggingMetadataEnd
0x18000111e  mov     [rsp+78h+var_20], rcx
0x180001123  lea     rcx, _TraceLoggingMetadata
0x18000112a  sub     eax, ecx
0x18000112c  mov     dword ptr [rsp+78h+var_30.0Ch], 2
0x180001134  mov     [rsp+78h+var_14], 1
0x18000113c  mov     [rsp+78h+var_48], eax
0x180001140  mov     eax, [rsp+78h+var_48]
0x180001144  mov     rcx, cs:RegHandle; RegHandle
0x18000114b  lea     rax, [rsp+78h+var_30]
0x180001150  mov     [rsp+78h+UserData], rax; UserData
0x180001155  mov     [rsp+78h+UserDataCount], 2; UserDataCount
0x18000115d  call    cs:__imp_EventWriteTransfer
0x180001164  nop     dword ptr [rax+rax+00h]
0x180001169  mov     rcx, [rsp+78h+var_10]
0x18000116e  xor     rcx, rsp; StackCookie
0x180001171  call    __security_check_cookie
0x180001176  add     rsp, 78h
0x18000117a  retn
```
