# McGenEventWrite_EventWriteTransfer

- ea: `0x180029dd0`
- end: `0x180029e22`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180029e28`
- `0x180029e80`
- `0x180029f00`
- `0x18002e54c`
- `0x18002fccc`

## callees

- `0x180029dd0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180029e17`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180029e17`

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

  v5 = (unsigned __int16 *)qword_180048058;
  if ( qword_180048058 )
  {
    UserData->Ptr = qword_180048058;
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
  return EventWriteTransfer(PROVIDER_TPM_VCARD_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180029dd0  sub     rsp, 38h
0x180029dd4  mov     rcx, cs:qword_180048058
0x180029ddb  mov     rax, [rsp+38h+arg_20]
0x180029de0  test    rcx, rcx
0x180029de3  jnz     short loc_180029DED
0x180029de5  mov     [rax], rcx
0x180029de8  xor     r8d, r8d
0x180029deb  jmp     short loc_180029DF9
0x180029ded  mov     [rax], rcx
0x180029df0  mov     r8d, 2
0x180029df6  movzx   ecx, word ptr [rcx]
0x180029df9  mov     [rax+8], ecx
0x180029dfc  mov     [rax+0Ch], r8d
0x180029e00  xor     r8d, r8d; ActivityId
0x180029e03  mov     rcx, cs:PROVIDER_TPM_VCARD_Context; RegHandle
0x180029e0a  mov     [rsp+38h+UserData], rax; UserData
0x180029e0f  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180029e14  xor     r9d, r9d; RelatedActivityId
0x180029e17  call    cs:__imp_EventWriteTransfer
0x180029e1d  add     rsp, 38h
0x180029e21  retn
```
