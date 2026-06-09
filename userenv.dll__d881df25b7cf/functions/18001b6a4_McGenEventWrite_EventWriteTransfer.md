# McGenEventWrite_EventWriteTransfer

- ea: `0x18001b6a4`
- end: `0x18001b6fd`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `89`
- prototype: ``
- caller_count: `16`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006e18`
- `0x18000ab88`
- `0x18001a508`
- `0x18001b704`
- `0x18001b75c`
- `0x18001b7d0`
- `0x18001b848`
- `0x18001b8a8`
- `0x18001b914`
- `0x18001b9c4`
- `0x18001ba48`
- `0x18001bae4`
- `0x18001bc04`
- `0x18001bcc0`
- `0x18001bd94`
- `0x18001be90`

## callees

- `0x18001b6a4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001b6eb`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001b6eb`

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

  v5 = (unsigned __int16 *)qword_180029098;
  if ( qword_180029098 )
  {
    UserData->Ptr = qword_180029098;
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
  return EventWriteTransfer(S_Microsoft_Windows_Userenv_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18001b6a4  sub     rsp, 38h
0x18001b6a8  mov     rcx, cs:qword_180029098
0x18001b6af  mov     rax, [rsp+38h+arg_20]
0x18001b6b4  test    rcx, rcx
0x18001b6b7  jnz     short loc_18001B6C1
0x18001b6b9  mov     [rax], rcx
0x18001b6bc  xor     r8d, r8d
0x18001b6bf  jmp     short loc_18001B6CD
0x18001b6c1  mov     [rax], rcx
0x18001b6c4  mov     r8d, 2
0x18001b6ca  movzx   ecx, word ptr [rcx]
0x18001b6cd  mov     [rax+8], ecx
0x18001b6d0  mov     [rax+0Ch], r8d
0x18001b6d4  xor     r8d, r8d; ActivityId
0x18001b6d7  mov     rcx, cs:S_Microsoft_Windows_Userenv_Context; RegHandle
0x18001b6de  mov     [rsp+38h+UserData], rax; UserData
0x18001b6e3  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18001b6e8  xor     r9d, r9d; RelatedActivityId
0x18001b6eb  call    cs:__imp_EventWriteTransfer
0x18001b6f2  nop     dword ptr [rax+rax+00h]
0x18001b6f7  add     rsp, 38h
0x18001b6fb  retn
```
