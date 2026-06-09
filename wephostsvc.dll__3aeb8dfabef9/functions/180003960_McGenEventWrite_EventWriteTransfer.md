# McGenEventWrite_EventWriteTransfer

- ea: `0x180003960`
- end: `0x1800039b2`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800030b8`
- `0x1800034c0`
- `0x1800036b0`

## callees

- `0x180003960`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800039a7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800039a7`

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

  v5 = (unsigned __int16 *)qword_180008018;
  if ( qword_180008018 )
  {
    UserData->Ptr = qword_180008018;
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
  return EventWriteTransfer(Microsoft_Windows_WEPHOSTSVC_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180003960  sub     rsp, 38h
0x180003964  mov     rcx, cs:qword_180008018
0x18000396b  mov     rax, [rsp+38h+arg_20]
0x180003970  test    rcx, rcx
0x180003973  jnz     short loc_18000397D
0x180003975  mov     [rax], rcx
0x180003978  xor     r8d, r8d
0x18000397b  jmp     short loc_180003989
0x18000397d  mov     [rax], rcx
0x180003980  mov     r8d, 2
0x180003986  movzx   ecx, word ptr [rcx]
0x180003989  mov     [rax+8], ecx
0x18000398c  mov     [rax+0Ch], r8d
0x180003990  xor     r8d, r8d; ActivityId
0x180003993  mov     rcx, cs:Microsoft_Windows_WEPHOSTSVC_Context; RegHandle
0x18000399a  mov     [rsp+38h+UserData], rax; UserData
0x18000399f  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1800039a4  xor     r9d, r9d; RelatedActivityId
0x1800039a7  call    cs:__imp_EventWriteTransfer
0x1800039ad  add     rsp, 38h
0x1800039b1  retn
```
