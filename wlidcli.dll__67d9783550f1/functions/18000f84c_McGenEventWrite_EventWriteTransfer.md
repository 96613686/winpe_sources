# McGenEventWrite_EventWriteTransfer

- ea: `0x18000f84c`
- end: `0x18000f89e`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000f8a4`
- `0x18000f93c`
- `0x180032180`
- `0x180053824`
- `0x1800539ac`

## callees

- `0x18000f84c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f893`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f893`

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

  v5 = (unsigned __int16 *)qword_1800942A8;
  if ( qword_1800942A8 )
  {
    UserData->Ptr = qword_1800942A8;
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
  return EventWriteTransfer(Microsoft_Windows_LiveId_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18000f84c  sub     rsp, 38h
0x18000f850  mov     rcx, cs:qword_1800942A8
0x18000f857  mov     rax, [rsp+38h+arg_20]
0x18000f85c  test    rcx, rcx
0x18000f85f  jnz     short loc_18000F869
0x18000f861  mov     [rax], rcx
0x18000f864  xor     r8d, r8d
0x18000f867  jmp     short loc_18000F875
0x18000f869  mov     [rax], rcx
0x18000f86c  mov     r8d, 2
0x18000f872  movzx   ecx, word ptr [rcx]
0x18000f875  mov     [rax+8], ecx
0x18000f878  mov     [rax+0Ch], r8d
0x18000f87c  xor     r8d, r8d; ActivityId
0x18000f87f  mov     rcx, cs:Microsoft_Windows_LiveId_Context; RegHandle
0x18000f886  mov     [rsp+38h+UserData], rax; UserData
0x18000f88b  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18000f890  xor     r9d, r9d; RelatedActivityId
0x18000f893  call    cs:__imp_EventWriteTransfer
0x18000f899  add     rsp, 38h
0x18000f89d  retn
```
