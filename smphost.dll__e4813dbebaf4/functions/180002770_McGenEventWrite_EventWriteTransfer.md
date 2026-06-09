# McGenEventWrite_EventWriteTransfer

- ea: `0x180002770`
- end: `0x1800027c2`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001bb8`
- `0x180002460`

## callees

- `0x180002770`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800027b7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800027b7`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_180006008;
  if ( qword_180006008 )
  {
    UserData->Ptr = qword_180006008;
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
  return EventWriteTransfer(LOG_SMPHOSTPROVIDER_GUID_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180002770  sub     rsp, 38h
0x180002774  mov     rcx, cs:qword_180006008
0x18000277b  mov     rax, [rsp+38h+arg_20]
0x180002780  test    rcx, rcx
0x180002783  jnz     short loc_18000278D
0x180002785  mov     [rax], rcx
0x180002788  xor     r8d, r8d
0x18000278b  jmp     short loc_180002799
0x18000278d  mov     [rax], rcx
0x180002790  mov     r8d, 2
0x180002796  movzx   ecx, word ptr [rcx]
0x180002799  mov     [rax+8], ecx
0x18000279c  mov     [rax+0Ch], r8d
0x1800027a0  xor     r8d, r8d; ActivityId
0x1800027a3  mov     rcx, cs:LOG_SMPHOSTPROVIDER_GUID_Context; RegHandle
0x1800027aa  mov     [rsp+38h+UserData], rax; UserData
0x1800027af  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1800027b4  xor     r9d, r9d; RelatedActivityId
0x1800027b7  call    cs:__imp_EventWriteTransfer
0x1800027bd  add     rsp, 38h
0x1800027c1  retn
```
