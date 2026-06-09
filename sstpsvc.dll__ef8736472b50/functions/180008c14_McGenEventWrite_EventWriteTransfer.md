# McGenEventWrite_EventWriteTransfer

- ea: `0x180008c14`
- end: `0x180008c68`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `84`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003620`
- `0x180008b90`
- `0x18000fec0`

## callees

- `0x180008c14`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180008c56`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180008c56`

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
0x180008c14  sub     rsp, 38h
0x180008c18  mov     r8, [rcx+8]
0x180008c1c  mov     rax, [rsp+38h+arg_20]
0x180008c21  test    r8, r8
0x180008c24  jnz     short loc_180008C2E
0x180008c26  mov     [rax], r8
0x180008c29  xor     r10d, r10d
0x180008c2c  jmp     short loc_180008C3B
0x180008c2e  mov     [rax], r8
0x180008c31  mov     r10d, 2
0x180008c37  movzx   r8d, word ptr [r8]
0x180008c3b  mov     [rax+8], r8d
0x180008c3f  xor     r8d, r8d; ActivityId
0x180008c42  mov     [rsp+38h+UserData], rax; UserData
0x180008c47  mov     [rax+0Ch], r10d
0x180008c4b  mov     rcx, [rcx]; RegHandle
0x180008c4e  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180008c53  xor     r9d, r9d; RelatedActivityId
0x180008c56  call    cs:__imp_EventWriteTransfer
0x180008c5d  nop     dword ptr [rax+rax+00h]
0x180008c62  add     rsp, 38h
0x180008c66  retn
```
