# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)

- ea: `0x18000d760`
- end: `0x18000d86a`
- name: `??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005b40`

## callees

- `0x18000d760`
- `0x180032c20`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000d837`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000d837`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5)
{
  const unsigned __int16 *v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-40h] BYREF
  unsigned __int8 *v11; // [rsp+58h] [rbp-30h]
  int v12; // [rsp+60h] [rbp-28h]
  int v13; // [rsp+64h] [rbp-24h]
  const unsigned __int16 *v14; // [rsp+68h] [rbp-20h]
  int v15; // [rsp+70h] [rbp-18h]
  int v16; // [rsp+74h] [rbp-14h]

  v5 = *a5;
  if ( *a5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *((_BYTE *)v5 + v6) );
    v7 = v6 + 1;
  }
  else
  {
    v5 = &byte_1800416E1;
    v7 = 1;
  }
  v15 = v7;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_180057198;
  v14 = v5;
  v16 = 0;
  UserData.Size = *(unsigned __int16 *)off_180057198;
  v12 = *(unsigned __int16 *)(a2 + 11);
  v11 = a2 + 11;
  UserData.Reserved = 2;
  v13 = 1;
  return EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
}

```

## disassembly

```asm
0x18000d760  sub     rsp, 88h
0x18000d767  mov     rax, cs:__security_cookie
0x18000d76e  xor     rax, rsp
0x18000d771  mov     [rsp+88h+var_10], rax
0x18000d776  mov     rax, [rsp+88h+arg_20]
0x18000d77e  mov     rcx, [rax]
0x18000d781  test    rcx, rcx
0x18000d784  jz      loc_18000D859
0x18000d78a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000d791  inc     rax
0x18000d794  cmp     byte ptr [rcx+rax], 0
0x18000d798  jnz     short loc_18000D791
0x18000d79a  inc     eax
0x18000d79c  mov     [rsp+88h+var_18], eax
0x18000d7a0  xor     r9d, r9d; RelatedActivityId
0x18000d7a3  movzx   eax, byte ptr [rdx]
0x18000d7a6  xor     r8d, r8d; ActivityId
0x18000d7a9  shl     eax, 18h
0x18000d7ac  mov     dword ptr [rsp+88h+EventDescriptor.Id], eax
0x18000d7b0  movzx   eax, word ptr [rdx+1]
0x18000d7b4  mov     dword ptr [rsp+88h+EventDescriptor.Level], eax
0x18000d7b8  mov     rax, [rdx+3]
0x18000d7bc  mov     [rsp+88h+EventDescriptor.Keyword], rax
0x18000d7c1  mov     rax, cs:off_180057198
0x18000d7c8  mov     [rsp+88h+var_40.Ptr], rax
0x18000d7cd  mov     [rsp+88h+var_20], rcx
0x18000d7d2  lea     rcx, [rdx+0Bh]
0x18000d7d6  mov     [rsp+88h+var_14], 0
0x18000d7de  lea     rdx, [rsp+88h+EventDescriptor]; EventDescriptor
0x18000d7e3  movzx   eax, word ptr [rax]
0x18000d7e6  mov     [rsp+88h+var_40.Size], eax
0x18000d7ea  movzx   eax, word ptr [rcx]
0x18000d7ed  mov     [rsp+88h+var_28], eax
0x18000d7f1  lea     rax, _TraceLoggingMetadataEnd
0x18000d7f8  mov     [rsp+88h+var_30], rcx
0x18000d7fd  lea     rcx, _TraceLoggingMetadata
0x18000d804  sub     eax, ecx
0x18000d806  mov     dword ptr [rsp+88h+var_40.0Ch], 2
0x18000d80e  mov     [rsp+88h+var_24], 1
0x18000d816  mov     [rsp+88h+var_58], eax
0x18000d81a  mov     eax, [rsp+88h+var_58]
0x18000d81e  mov     rcx, cs:RegHandle; RegHandle
0x18000d825  lea     rax, [rsp+88h+var_40]
0x18000d82a  mov     [rsp+88h+UserData], rax; UserData
0x18000d82f  mov     [rsp+88h+UserDataCount], 3; UserDataCount
0x18000d837  call    cs:__imp_EventWriteTransfer
0x18000d83e  nop     dword ptr [rax+rax+00h]
0x18000d843  mov     rcx, [rsp+88h+var_10]
0x18000d848  xor     rcx, rsp; StackCookie
0x18000d84b  call    __security_check_cookie
0x18000d850  add     rsp, 88h
0x18000d857  retn
0x18000d859  lea     rcx, byte_1800416E1
0x18000d860  mov     eax, 1
0x18000d865  jmp     loc_18000D79C
```
