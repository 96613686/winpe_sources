# McGenEventWrite_EventWriteTransfer

- ea: `0x18000e838`
- end: `0x18000e88a`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e778`
- `0x180027bac`
- `0x180033828`

## callees

- `0x18000e838`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000e871`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000e871`

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

  v5 = (unsigned __int16 *)qword_18004B048;
  if ( qword_18004B048 )
  {
    UserData->Ptr = qword_18004B048;
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
  return EventWriteTransfer(EVENTLOG_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18000e838  sub     rsp, 38h
0x18000e83c  mov     rcx, cs:qword_18004B048
0x18000e843  mov     rax, [rsp+38h+arg_20]
0x18000e848  test    rcx, rcx
0x18000e84b  jnz     short loc_18000E87C
0x18000e84d  mov     [rax], rcx
0x18000e850  xor     r8d, r8d
0x18000e853  mov     [rax+8], ecx
0x18000e856  mov     [rax+0Ch], r8d
0x18000e85a  xor     r8d, r8d; ActivityId
0x18000e85d  mov     rcx, cs:EVENTLOG_Context; RegHandle
0x18000e864  mov     [rsp+38h+UserData], rax; UserData
0x18000e869  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18000e86e  xor     r9d, r9d; RelatedActivityId
0x18000e871  call    cs:__imp_EventWriteTransfer
0x18000e877  add     rsp, 38h
0x18000e87b  retn
0x18000e87c  mov     [rax], rcx
0x18000e87f  mov     r8d, 2
0x18000e885  movzx   ecx, word ptr [rcx]
0x18000e888  jmp     short loc_18000E853
```
