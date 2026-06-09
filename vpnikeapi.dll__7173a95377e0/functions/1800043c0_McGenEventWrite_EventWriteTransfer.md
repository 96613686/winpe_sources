# McGenEventWrite_EventWriteTransfer

- ea: `0x1800043c0`
- end: `0x18000440d`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `77`
- prototype: `ULONG __fastcall(REGHANDLE *, const EVENT_DESCRIPTOR *, __int64, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004420`

## callees

- `0x1800043c0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180004402`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180004402`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        REGHANDLE *a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // r8
  int v6; // r10d

  v5 = (unsigned __int16 *)a1[1];
  if ( v5 )
  {
    UserData->Ptr = (ULONGLONG)v5;
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
  return EventWriteTransfer(*a1, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x1800043c0  sub     rsp, 38h
0x1800043c4  mov     r8, [rcx+8]
0x1800043c8  mov     rax, [rsp+38h+arg_20]
0x1800043cd  test    r8, r8
0x1800043d0  jnz     short loc_1800043DA
0x1800043d2  mov     [rax], r8
0x1800043d5  xor     r10d, r10d
0x1800043d8  jmp     short loc_1800043E7
0x1800043da  mov     [rax], r8
0x1800043dd  mov     r10d, 2
0x1800043e3  movzx   r8d, word ptr [r8]
0x1800043e7  mov     [rax+8], r8d
0x1800043eb  xor     r8d, r8d; ActivityId
0x1800043ee  mov     [rsp+38h+UserData], rax; UserData
0x1800043f3  mov     [rax+0Ch], r10d
0x1800043f7  mov     rcx, [rcx]; RegHandle
0x1800043fa  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1800043ff  xor     r9d, r9d; RelatedActivityId
0x180004402  call    cs:__imp_EventWriteTransfer
0x180004408  add     rsp, 38h
0x18000440c  retn
```
