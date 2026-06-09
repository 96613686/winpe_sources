# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)

- ea: `0x1800010b0`
- end: `0x180001165`
- name: `??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z`
- size: `181`
- prototype: `ULONG __fastcall(__int64, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180019168`

## callees

- `0x18002e5b0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000114d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000114d`

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
  UserData.Ptr = (ULONGLONG)off_18005D178;
  UserData.Size = *(unsigned __int16 *)off_18005D178;
  v6 = *(unsigned __int16 *)(a2 + 11);
  v5 = a2 + 11;
  UserData.Reserved = 2;
  v7 = 1;
  return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
}

```

## disassembly

```asm
0x1800010b0  sub     rsp, 78h
0x1800010b4  mov     rax, cs:__security_cookie
0x1800010bb  xor     rax, rsp
0x1800010be  mov     [rsp+78h+var_10], rax
0x1800010c3  movzx   eax, byte ptr [rdx]
0x1800010c6  lea     rcx, [rdx+0Bh]
0x1800010ca  shl     eax, 18h
0x1800010cd  xor     r9d, r9d; RelatedActivityId
0x1800010d0  mov     dword ptr [rsp+78h+EventDescriptor.Id], eax
0x1800010d4  xor     r8d, r8d; ActivityId
0x1800010d7  movzx   eax, word ptr [rdx+1]
0x1800010db  mov     dword ptr [rsp+78h+EventDescriptor.Level], eax
0x1800010df  mov     rax, [rdx+3]
0x1800010e3  lea     rdx, [rsp+78h+EventDescriptor]; EventDescriptor
0x1800010e8  mov     [rsp+78h+EventDescriptor.Keyword], rax
0x1800010ed  mov     rax, cs:off_18005D178
0x1800010f4  mov     [rsp+78h+var_30.Ptr], rax
0x1800010f9  movzx   eax, word ptr [rax]
0x1800010fc  mov     [rsp+78h+var_30.Size], eax
0x180001100  movzx   eax, word ptr [rcx]
0x180001103  mov     [rsp+78h+var_18], eax
0x180001107  lea     rax, _TraceLoggingMetadataEnd
0x18000110e  mov     [rsp+78h+var_20], rcx
0x180001113  lea     rcx, _TraceLoggingMetadata
0x18000111a  sub     eax, ecx
0x18000111c  mov     dword ptr [rsp+78h+var_30.0Ch], 2
0x180001124  mov     [rsp+78h+var_14], 1
0x18000112c  mov     [rsp+78h+var_48], eax
0x180001130  mov     eax, [rsp+78h+var_48]
0x180001134  mov     rcx, cs:RegHandle; RegHandle
0x18000113b  lea     rax, [rsp+78h+var_30]
0x180001140  mov     [rsp+78h+UserData], rax; UserData
0x180001145  mov     [rsp+78h+UserDataCount], 2; UserDataCount
0x18000114d  call    cs:__imp_EventWriteTransfer
0x180001153  mov     rcx, [rsp+78h+var_10]
0x180001158  xor     rcx, rsp; StackCookie
0x18000115b  call    __security_check_cookie
0x180001160  add     rsp, 78h
0x180001164  retn
```
