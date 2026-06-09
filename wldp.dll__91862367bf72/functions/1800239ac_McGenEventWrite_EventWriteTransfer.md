# McGenEventWrite_EventWriteTransfer

- ea: `0x1800239ac`
- end: `0x1800239fe`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180023a04`
- `0x180023a5c`
- `0x180023ab8`
- `0x180023ff0`
- `0x180029730`
- `0x180029830`
- `0x180029968`

## callees

- `0x1800239ac`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800239f3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800239f3`

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

  v5 = (unsigned __int16 *)qword_18005A198;
  if ( qword_18005A198 )
  {
    UserData->Ptr = qword_18005A198;
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
  return EventWriteTransfer(SBChecksProviderId_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x1800239ac  sub     rsp, 38h
0x1800239b0  mov     rcx, cs:qword_18005A198
0x1800239b7  mov     rax, [rsp+38h+arg_20]
0x1800239bc  test    rcx, rcx
0x1800239bf  jnz     short loc_1800239C9
0x1800239c1  mov     [rax], rcx
0x1800239c4  xor     r8d, r8d
0x1800239c7  jmp     short loc_1800239D5
0x1800239c9  mov     [rax], rcx
0x1800239cc  mov     r8d, 2
0x1800239d2  movzx   ecx, word ptr [rcx]
0x1800239d5  mov     [rax+8], ecx
0x1800239d8  mov     [rax+0Ch], r8d
0x1800239dc  xor     r8d, r8d; ActivityId
0x1800239df  mov     rcx, cs:SBChecksProviderId_Context; RegHandle
0x1800239e6  mov     [rsp+38h+UserData], rax; UserData
0x1800239eb  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1800239f0  xor     r9d, r9d; RelatedActivityId
0x1800239f3  call    cs:__imp_EventWriteTransfer
0x1800239f9  add     rsp, 38h
0x1800239fd  retn
```
