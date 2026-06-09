# McGenEventWrite_EventWriteTransfer

- ea: `0x180009950`
- end: `0x1800099a2`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800099a8`
- `0x180009a40`
- `0x18000fc28`
- `0x18000fcf8`

## callees

- `0x180009950`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180009997`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180009997`

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

  v5 = (unsigned __int16 *)qword_180020058;
  if ( qword_180020058 )
  {
    UserData->Ptr = qword_180020058;
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
0x180009950  sub     rsp, 38h
0x180009954  mov     rcx, cs:qword_180020058
0x18000995b  mov     rax, [rsp+38h+arg_20]
0x180009960  test    rcx, rcx
0x180009963  jnz     short loc_18000996D
0x180009965  mov     [rax], rcx
0x180009968  xor     r8d, r8d
0x18000996b  jmp     short loc_180009979
0x18000996d  mov     [rax], rcx
0x180009970  mov     r8d, 2
0x180009976  movzx   ecx, word ptr [rcx]
0x180009979  mov     [rax+8], ecx
0x18000997c  mov     [rax+0Ch], r8d
0x180009980  xor     r8d, r8d; ActivityId
0x180009983  mov     rcx, cs:Microsoft_Windows_LiveId_Context; RegHandle
0x18000998a  mov     [rsp+38h+UserData], rax; UserData
0x18000998f  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180009994  xor     r9d, r9d; RelatedActivityId
0x180009997  call    cs:__imp_EventWriteTransfer
0x18000999d  add     rsp, 38h
0x1800099a1  retn
```
