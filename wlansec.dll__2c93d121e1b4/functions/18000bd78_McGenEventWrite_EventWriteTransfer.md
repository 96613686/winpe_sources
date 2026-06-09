# McGenEventWrite_EventWriteTransfer

- ea: `0x18000bd78`
- end: `0x18000bdcc`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `84`
- prototype: ``
- caller_count: `30`
- callee_count: `1`
- tags: ``

## callers

- `0x180006344`
- `0x180009e70`
- `0x18000a750`
- `0x18000b6dc`
- `0x18000b94c`
- `0x1800141d0`
- `0x180019a64`
- `0x18001a260`
- `0x18001b020`
- `0x18001bd70`
- `0x18001f2dc`
- `0x18002c5b4`
- `0x18002d25c`
- `0x180031b1c`
- `0x180031c30`
- `0x180033be0`
- `0x180035d1c`
- `0x180038034`
- `0x180038dd0`
- `0x18003e5bc`
- `0x180055698`
- `0x180055744`
- `0x180055d50`
- `0x18005633c`
- `0x18005639c`
- `0x180056418`
- `0x18005a440`
- `0x180064a3c`
- `0x180068aa0`
- `0x18006be4c`

## callees

- `0x18000bd78`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000bdab`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000bdab`

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
0x18000bd78  sub     rsp, 38h
0x18000bd7c  mov     r8, [rcx+8]
0x18000bd80  mov     rax, [rsp+38h+arg_20]
0x18000bd85  test    r8, r8
0x18000bd88  jnz     short loc_18000BDBD
0x18000bd8a  mov     [rax], r8
0x18000bd8d  xor     r10d, r10d
0x18000bd90  mov     [rax+8], r8d
0x18000bd94  xor     r8d, r8d; ActivityId
0x18000bd97  mov     [rsp+38h+UserData], rax; UserData
0x18000bd9c  mov     [rax+0Ch], r10d
0x18000bda0  mov     rcx, [rcx]; RegHandle
0x18000bda3  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18000bda8  xor     r9d, r9d; RelatedActivityId
0x18000bdab  call    cs:__imp_EventWriteTransfer
0x18000bdb2  nop     dword ptr [rax+rax+00h]
0x18000bdb7  add     rsp, 38h
0x18000bdbb  retn
0x18000bdbd  mov     [rax], r8
0x18000bdc0  mov     r10d, 2
0x18000bdc6  movzx   r8d, word ptr [r8]
0x18000bdca  jmp     short loc_18000BD90
```
