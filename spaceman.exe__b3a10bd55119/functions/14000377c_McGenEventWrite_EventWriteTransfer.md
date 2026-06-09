# McGenEventWrite_EventWriteTransfer

- ea: `0x14000377c`
- end: `0x1400037c9`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `77`
- prototype: `ULONG __fastcall(REGHANDLE *, const EVENT_DESCRIPTOR *, __int64, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140002230`
- `0x14000a3b8`
- `0x14000aaa4`
- `0x14000b5d8`
- `0x14000b704`

## callees

- `0x14000377c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400037be`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400037be`

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
0x14000377c  sub     rsp, 38h
0x140003780  mov     r8, [rcx+8]
0x140003784  mov     rax, [rsp+38h+arg_20]
0x140003789  test    r8, r8
0x14000378c  jnz     short loc_140003796
0x14000378e  mov     [rax], r8
0x140003791  xor     r10d, r10d
0x140003794  jmp     short loc_1400037A3
0x140003796  mov     [rax], r8
0x140003799  mov     r10d, 2
0x14000379f  movzx   r8d, word ptr [r8]
0x1400037a3  mov     [rax+8], r8d
0x1400037a7  xor     r8d, r8d; ActivityId
0x1400037aa  mov     [rsp+38h+UserData], rax; UserData
0x1400037af  mov     [rax+0Ch], r10d
0x1400037b3  mov     rcx, [rcx]; RegHandle
0x1400037b6  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1400037bb  xor     r9d, r9d; RelatedActivityId
0x1400037be  call    cs:__imp_EventWriteTransfer
0x1400037c4  add     rsp, 38h
0x1400037c8  retn
```
