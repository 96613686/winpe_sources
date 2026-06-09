# McGenEventWrite_EventWriteTransfer

- ea: `0x180002a00`
- end: `0x180002a52`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002578`
- `0x180002708`
- `0x180002794`
- `0x180002820`

## callees

- `0x180002a00`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180002a47`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180002a47`

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

  v5 = (unsigned __int16 *)qword_180012008;
  if ( qword_180012008 )
  {
    UserData->Ptr = qword_180012008;
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
  return EventWriteTransfer(WSPCEtwProviderGuid_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180002a00  sub     rsp, 38h
0x180002a04  mov     rcx, cs:qword_180012008
0x180002a0b  mov     rax, [rsp+38h+arg_20]
0x180002a10  test    rcx, rcx
0x180002a13  jnz     short loc_180002A1D
0x180002a15  mov     [rax], rcx
0x180002a18  xor     r8d, r8d
0x180002a1b  jmp     short loc_180002A29
0x180002a1d  mov     [rax], rcx
0x180002a20  mov     r8d, 2
0x180002a26  movzx   ecx, word ptr [rcx]
0x180002a29  mov     [rax+8], ecx
0x180002a2c  mov     [rax+0Ch], r8d
0x180002a30  xor     r8d, r8d; ActivityId
0x180002a33  mov     rcx, cs:WSPCEtwProviderGuid_Context; RegHandle
0x180002a3a  mov     [rsp+38h+UserData], rax; UserData
0x180002a3f  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180002a44  xor     r9d, r9d; RelatedActivityId
0x180002a47  call    cs:__imp_EventWriteTransfer
0x180002a4d  add     rsp, 38h
0x180002a51  retn
```
