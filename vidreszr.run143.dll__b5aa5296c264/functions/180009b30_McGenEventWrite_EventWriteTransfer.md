# McGenEventWrite_EventWriteTransfer

- ea: `0x180009b30`
- end: `0x180009b82`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002780`
- `0x180009b90`
- `0x180009c10`

## callees

- `0x180009b30`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180009b77`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180009b77`

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

  v5 = (unsigned __int16 *)qword_18001B078;
  if ( qword_18001B078 )
  {
    UserData->Ptr = qword_18001B078;
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
  return EventWriteTransfer(Microsoft_Windows_MediaFoundation_Performance_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180009b30  sub     rsp, 38h
0x180009b34  mov     rcx, cs:qword_18001B078
0x180009b3b  mov     rax, [rsp+38h+arg_20]
0x180009b40  test    rcx, rcx
0x180009b43  jnz     short loc_180009B4D
0x180009b45  mov     [rax], rcx
0x180009b48  xor     r8d, r8d
0x180009b4b  jmp     short loc_180009B59
0x180009b4d  mov     [rax], rcx
0x180009b50  mov     r8d, 2
0x180009b56  movzx   ecx, word ptr [rcx]
0x180009b59  mov     [rax+8], ecx
0x180009b5c  mov     [rax+0Ch], r8d
0x180009b60  xor     r8d, r8d; ActivityId
0x180009b63  mov     rcx, cs:Microsoft_Windows_MediaFoundation_Performance_Context; RegHandle
0x180009b6a  mov     [rsp+38h+UserData], rax; UserData
0x180009b6f  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180009b74  xor     r9d, r9d; RelatedActivityId
0x180009b77  call    cs:__imp_EventWriteTransfer
0x180009b7d  add     rsp, 38h
0x180009b81  retn
```
