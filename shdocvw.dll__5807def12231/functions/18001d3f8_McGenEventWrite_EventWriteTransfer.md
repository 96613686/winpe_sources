# McGenEventWrite_EventWriteTransfer

- ea: `0x18001d3f8`
- end: `0x18001d44d`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `85`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180016f60`
- `0x18001d454`

## callees

- `0x18001d3f8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001d442`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001d442`

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

  v5 = (unsigned __int16 *)qword_180038008;
  if ( qword_180038008 )
  {
    UserData->Ptr = qword_180038008;
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
  return EventWriteTransfer(Microsoft_Windows_Shell_Core_Provider_Context, a2, 0, 0, 2u, UserData);
}

```

## disassembly

```asm
0x18001d3f8  sub     rsp, 38h
0x18001d3fc  mov     rcx, cs:qword_180038008
0x18001d403  mov     r9d, 2
0x18001d409  mov     rax, [rsp+38h+arg_20]
0x18001d40e  test    rcx, rcx
0x18001d411  jnz     short loc_18001D41B
0x18001d413  mov     [rax], rcx
0x18001d416  xor     r8d, r8d
0x18001d419  jmp     short loc_18001D424
0x18001d41b  mov     [rax], rcx
0x18001d41e  mov     r8d, r9d
0x18001d421  movzx   ecx, word ptr [rcx]
0x18001d424  mov     [rax+8], ecx
0x18001d427  mov     [rax+0Ch], r8d
0x18001d42b  xor     r8d, r8d; ActivityId
0x18001d42e  mov     rcx, cs:Microsoft_Windows_Shell_Core_Provider_Context; RegHandle
0x18001d435  mov     [rsp+38h+UserData], rax; UserData
0x18001d43a  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18001d43f  xor     r9d, r9d; RelatedActivityId
0x18001d442  call    cs:__imp_EventWriteTransfer
0x18001d448  add     rsp, 38h
0x18001d44c  retn
```
