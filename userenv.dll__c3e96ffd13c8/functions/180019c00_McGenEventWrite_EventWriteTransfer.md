# McGenEventWrite_EventWriteTransfer

- ea: `0x180019c00`
- end: `0x180019c52`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `16`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006904`
- `0x18000a200`
- `0x180018b50`
- `0x180019c58`
- `0x180019cb0`
- `0x180019d20`
- `0x180019d94`
- `0x180019df0`
- `0x180019e5c`
- `0x180019f0c`
- `0x180019f8c`
- `0x18001a028`
- `0x18001a144`
- `0x18001a200`
- `0x18001a2d4`
- `0x18001a3d0`

## callees

- `0x180019c00`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180019c47`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180019c47`

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

  v5 = (unsigned __int16 *)qword_180028098;
  if ( qword_180028098 )
  {
    UserData->Ptr = qword_180028098;
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
  return EventWriteTransfer(S_Microsoft_Windows_Userenv_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180019c00  sub     rsp, 38h
0x180019c04  mov     rcx, cs:qword_180028098
0x180019c0b  mov     rax, [rsp+38h+arg_20]
0x180019c10  test    rcx, rcx
0x180019c13  jnz     short loc_180019C1D
0x180019c15  mov     [rax], rcx
0x180019c18  xor     r8d, r8d
0x180019c1b  jmp     short loc_180019C29
0x180019c1d  mov     [rax], rcx
0x180019c20  mov     r8d, 2
0x180019c26  movzx   ecx, word ptr [rcx]
0x180019c29  mov     [rax+8], ecx
0x180019c2c  mov     [rax+0Ch], r8d
0x180019c30  xor     r8d, r8d; ActivityId
0x180019c33  mov     rcx, cs:S_Microsoft_Windows_Userenv_Context; RegHandle
0x180019c3a  mov     [rsp+38h+UserData], rax; UserData
0x180019c3f  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180019c44  xor     r9d, r9d; RelatedActivityId
0x180019c47  call    cs:__imp_EventWriteTransfer
0x180019c4d  add     rsp, 38h
0x180019c51  retn
```
