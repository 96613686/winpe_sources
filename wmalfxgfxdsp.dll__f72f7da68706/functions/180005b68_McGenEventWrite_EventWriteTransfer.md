# McGenEventWrite_EventWriteTransfer

- ea: `0x180005b68`
- end: `0x180005bbd`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `85`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000631c`

## callees

- `0x180005b68`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180005ba4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180005ba4`

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

  v5 = (unsigned __int16 *)qword_1801B6A38;
  if ( qword_1801B6A38 )
  {
    UserData->Ptr = qword_1801B6A38;
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
  return EventWriteTransfer(Microsoft_Windows_MediaFoundation_Performance_Context, a2, 0, 0, 8u, UserData);
}

```

## disassembly

```asm
0x180005b68  sub     rsp, 38h
0x180005b6c  mov     rcx, cs:qword_1801B6A38
0x180005b73  mov     rax, [rsp+38h+arg_20]
0x180005b78  test    rcx, rcx
0x180005b7b  jnz     short loc_180005BAF
0x180005b7d  mov     [rax], rcx
0x180005b80  xor     r8d, r8d
0x180005b83  mov     [rax+8], ecx
0x180005b86  xor     r9d, r9d; RelatedActivityId
0x180005b89  mov     [rax+0Ch], r8d
0x180005b8d  xor     r8d, r8d; ActivityId
0x180005b90  mov     rcx, cs:Microsoft_Windows_MediaFoundation_Performance_Context; RegHandle
0x180005b97  mov     [rsp+38h+UserData], rax; UserData
0x180005b9c  mov     [rsp+38h+UserDataCount], 8; UserDataCount
0x180005ba4  call    cs:__imp_EventWriteTransfer
0x180005baa  add     rsp, 38h
0x180005bae  retn
0x180005baf  mov     [rax], rcx
0x180005bb2  mov     r8d, 2
0x180005bb8  movzx   ecx, word ptr [rcx]
0x180005bbb  jmp     short loc_180005B83
```
