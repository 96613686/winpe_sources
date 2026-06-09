# McGenEventWrite_EventWriteTransfer

- ea: `0x180006744`
- end: `0x18000679d`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `89`
- prototype: `ULONG __fastcall(__int64, __int64, __int64, __int64, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800067a4`

## callees

- `0x180006744`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180006792`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180006792`

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

  v5 = (unsigned __int16 *)qword_180018008;
  if ( qword_180018008 )
  {
    UserData->Ptr = qword_180018008;
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
  return EventWriteTransfer(IIS_LOGGING_ETW_PROVIDER_Context, &IIS_LOGGING_EVENT_LOG_MESG, 0, 0, 0x19u, UserData);
}

```

## disassembly

```asm
0x180006744  sub     rsp, 38h
0x180006748  mov     rcx, cs:qword_180018008
0x18000674f  mov     rax, [rsp+38h+arg_20]
0x180006754  test    rcx, rcx
0x180006757  jnz     short loc_180006760
0x180006759  mov     [rax], rcx
0x18000675c  xor     edx, edx
0x18000675e  jmp     short loc_18000676B
0x180006760  mov     [rax], rcx
0x180006763  mov     edx, 2
0x180006768  movzx   ecx, word ptr [rcx]
0x18000676b  mov     [rax+8], ecx
0x18000676e  xor     r9d, r9d; RelatedActivityId
0x180006771  mov     [rax+0Ch], edx
0x180006774  xor     r8d, r8d; ActivityId
0x180006777  mov     rcx, cs:IIS_LOGGING_ETW_PROVIDER_Context; RegHandle
0x18000677e  lea     rdx, IIS_LOGGING_EVENT_LOG_MESG; EventDescriptor
0x180006785  mov     [rsp+38h+UserData], rax; UserData
0x18000678a  mov     [rsp+38h+UserDataCount], 19h; UserDataCount
0x180006792  call    cs:__imp_EventWriteTransfer
0x180006798  add     rsp, 38h
0x18000679c  retn
```
