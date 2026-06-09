# McGenEventWrite_EventWriteTransfer

- ea: `0x1800061d0`
- end: `0x180006222`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `21`
- callee_count: `1`
- tags: ``

## callers

- `0x180002530`
- `0x180006160`
- `0x18000ba10`
- `0x18000ba68`
- `0x18000baf8`
- `0x18000bb64`
- `0x18000bbe0`
- `0x18000bc7c`
- `0x18000bd18`
- `0x18000bde4`
- `0x18000bed0`
- `0x18000bfa8`
- `0x18000c070`
- `0x18000c120`
- `0x18000c210`
- `0x18000c2a8`
- `0x18000c39c`
- `0x18000c480`
- `0x18000c554`
- `0x1800152bc`
- `0x1800153a8`

## callees

- `0x1800061d0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180006217`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180006217`

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

  v5 = (unsigned __int16 *)qword_180027008;
  if ( qword_180027008 )
  {
    UserData->Ptr = qword_180027008;
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
  return EventWriteTransfer(SAMLIB_EVENT_PUBLISHER_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x1800061d0  sub     rsp, 38h
0x1800061d4  mov     rcx, cs:qword_180027008
0x1800061db  mov     rax, [rsp+38h+arg_20]
0x1800061e0  test    rcx, rcx
0x1800061e3  jnz     short loc_1800061ED
0x1800061e5  mov     [rax], rcx
0x1800061e8  xor     r8d, r8d
0x1800061eb  jmp     short loc_1800061F9
0x1800061ed  mov     [rax], rcx
0x1800061f0  mov     r8d, 2
0x1800061f6  movzx   ecx, word ptr [rcx]
0x1800061f9  mov     [rax+8], ecx
0x1800061fc  mov     [rax+0Ch], r8d
0x180006200  xor     r8d, r8d; ActivityId
0x180006203  mov     rcx, cs:SAMLIB_EVENT_PUBLISHER_Context; RegHandle
0x18000620a  mov     [rsp+38h+UserData], rax; UserData
0x18000620f  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180006214  xor     r9d, r9d; RelatedActivityId
0x180006217  call    cs:__imp_EventWriteTransfer
0x18000621d  add     rsp, 38h
0x180006221  retn
```
