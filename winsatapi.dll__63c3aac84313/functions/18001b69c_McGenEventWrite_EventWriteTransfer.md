# McGenEventWrite_EventWriteTransfer

- ea: `0x18001b69c`
- end: `0x18001b6e9`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `77`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18001b6f0`
- `0x18001b74c`
- `0x18001c1a8`
- `0x18001c21c`
- `0x18001c414`

## callees

- `0x18001b69c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001b6de`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001b6de`

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
0x18001b69c  sub     rsp, 38h
0x18001b6a0  mov     r8, [rcx+8]
0x18001b6a4  mov     rax, [rsp+38h+arg_20]
0x18001b6a9  test    r8, r8
0x18001b6ac  jnz     short loc_18001B6B6
0x18001b6ae  mov     [rax], r8
0x18001b6b1  xor     r10d, r10d
0x18001b6b4  jmp     short loc_18001B6C3
0x18001b6b6  mov     [rax], r8
0x18001b6b9  mov     r10d, 2
0x18001b6bf  movzx   r8d, word ptr [r8]
0x18001b6c3  mov     [rax+8], r8d
0x18001b6c7  xor     r8d, r8d; ActivityId
0x18001b6ca  mov     [rsp+38h+UserData], rax; UserData
0x18001b6cf  mov     [rax+0Ch], r10d
0x18001b6d3  mov     rcx, [rcx]; RegHandle
0x18001b6d6  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18001b6db  xor     r9d, r9d; RelatedActivityId
0x18001b6de  call    cs:__imp_EventWriteTransfer
0x18001b6e4  add     rsp, 38h
0x18001b6e8  retn
```
