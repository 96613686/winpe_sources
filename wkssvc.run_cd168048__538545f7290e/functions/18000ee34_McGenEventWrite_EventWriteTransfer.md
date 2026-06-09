# McGenEventWrite_EventWriteTransfer

- ea: `0x18000ee34`
- end: `0x18000ee8d`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `89`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000eba8`
- `0x18000fff0`
- `0x1800100c4`
- `0x18001093c`
- `0x180010aac`
- `0x180010b90`
- `0x180010c2c`
- `0x180010ce8`
- `0x180010e00`
- `0x180011088`
- `0x18001124c`
- `0x180033548`

## callees

- `0x18000ee34`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ee7b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ee7b`

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

  v5 = (unsigned __int16 *)qword_180050738;
  if ( qword_180050738 )
  {
    UserData->Ptr = qword_180050738;
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
  return EventWriteTransfer(Microsoft_Windows_SMBWitnessClient_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18000ee34  sub     rsp, 38h
0x18000ee38  mov     rcx, cs:qword_180050738
0x18000ee3f  mov     rax, [rsp+38h+arg_20]
0x18000ee44  test    rcx, rcx
0x18000ee47  jnz     short loc_18000EE51
0x18000ee49  mov     [rax], rcx
0x18000ee4c  xor     r8d, r8d
0x18000ee4f  jmp     short loc_18000EE5D
0x18000ee51  mov     [rax], rcx
0x18000ee54  mov     r8d, 2
0x18000ee5a  movzx   ecx, word ptr [rcx]
0x18000ee5d  mov     [rax+8], ecx
0x18000ee60  mov     [rax+0Ch], r8d
0x18000ee64  xor     r8d, r8d; ActivityId
0x18000ee67  mov     rcx, cs:Microsoft_Windows_SMBWitnessClient_Context; RegHandle
0x18000ee6e  mov     [rsp+38h+UserData], rax; UserData
0x18000ee73  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18000ee78  xor     r9d, r9d; RelatedActivityId
0x18000ee7b  call    cs:__imp_EventWriteTransfer
0x18000ee82  nop     dword ptr [rax+rax+00h]
0x18000ee87  add     rsp, 38h
0x18000ee8b  retn
```
