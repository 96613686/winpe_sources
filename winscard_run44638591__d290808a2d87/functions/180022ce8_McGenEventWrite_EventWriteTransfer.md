# McGenEventWrite_EventWriteTransfer

- ea: `0x180022ce8`
- end: `0x180022d3d`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `85`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180022d44`

## callees

- `0x180022ce8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180022d32`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180022d32`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        __int64 a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  ULONG v6; // r8d

  v5 = (unsigned __int16 *)qword_180045018;
  if ( qword_180045018 )
  {
    UserData->Ptr = qword_180045018;
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
  return EventWriteTransfer(SCARD_PROVIDER_GUID_Context, a2, 0, 0, 3u, UserData);
}

```

## disassembly

```asm
0x180022ce8  sub     rsp, 38h
0x180022cec  mov     rcx, cs:qword_180045018
0x180022cf3  mov     rax, [rsp+38h+arg_20]
0x180022cf8  test    rcx, rcx
0x180022cfb  jnz     short loc_180022D05
0x180022cfd  mov     [rax], rcx
0x180022d00  xor     r8d, r8d
0x180022d03  jmp     short loc_180022D11
0x180022d05  mov     [rax], rcx
0x180022d08  mov     r8d, 2
0x180022d0e  movzx   ecx, word ptr [rcx]
0x180022d11  mov     [rax+8], ecx
0x180022d14  xor     r9d, r9d; RelatedActivityId
0x180022d17  mov     [rax+0Ch], r8d
0x180022d1b  xor     r8d, r8d; ActivityId
0x180022d1e  mov     rcx, cs:SCARD_PROVIDER_GUID_Context; RegHandle
0x180022d25  mov     [rsp+38h+UserData], rax; UserData
0x180022d2a  mov     [rsp+38h+UserDataCount], 3; UserDataCount
0x180022d32  call    cs:__imp_EventWriteTransfer
0x180022d38  add     rsp, 38h
0x180022d3c  retn
```
