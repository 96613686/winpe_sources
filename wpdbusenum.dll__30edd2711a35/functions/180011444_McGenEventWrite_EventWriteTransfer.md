# McGenEventWrite_EventWriteTransfer

- ea: `0x180011444`
- end: `0x18001149d`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `89`
- prototype: `ULONG __fastcall(__int64, __int64, __int64, __int64, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800114a4`

## callees

- `0x180011444`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180011492`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180011492`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  ULONG v6; // edx

  v5 = (unsigned __int16 *)qword_18001F008;
  if ( qword_18001F008 )
  {
    UserData->Ptr = qword_18001F008;
    v6 = 2;
    LODWORD(v5) = *v5;
  }
  else
  {
    UserData->Ptr = 0;
    v6 = 0;
  }
  UserData->Size = (unsigned int)v5;
  UserData->Reserved = v6;
  return EventWriteTransfer(
           WPDCI_EVENT_PROVIDER_ID_Context,
           &WPD_I_DATA_TRANSFER_ACCESS_DENIED_BY_POLICY,
           0,
           0,
           0xAu,
           UserData);
}

```

## disassembly

```asm
0x180011444  sub     rsp, 38h
0x180011448  mov     rcx, cs:qword_18001F008
0x18001144f  mov     rax, [rsp+38h+arg_20]
0x180011454  test    rcx, rcx
0x180011457  jnz     short loc_180011460
0x180011459  mov     [rax], rcx
0x18001145c  xor     edx, edx
0x18001145e  jmp     short loc_18001146B
0x180011460  mov     [rax], rcx
0x180011463  mov     edx, 2
0x180011468  movzx   ecx, word ptr [rcx]
0x18001146b  mov     [rax+8], ecx
0x18001146e  xor     r9d, r9d; RelatedActivityId
0x180011471  mov     [rax+0Ch], edx
0x180011474  xor     r8d, r8d; ActivityId
0x180011477  mov     rcx, cs:WPDCI_EVENT_PROVIDER_ID_Context; RegHandle
0x18001147e  lea     rdx, WPD_I_DATA_TRANSFER_ACCESS_DENIED_BY_POLICY; EventDescriptor
0x180011485  mov     [rsp+38h+UserData], rax; UserData
0x18001148a  mov     [rsp+38h+UserDataCount], 0Ah; UserDataCount
0x180011492  call    cs:__imp_EventWriteTransfer
0x180011498  add     rsp, 38h
0x18001149c  retn
```
