# McGenEventWrite_EventWriteTransfer

- ea: `0x18003b130`
- end: `0x18003b185`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `85`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18003b18c`

## callees

- `0x18003b130`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18003b17a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18003b17a`

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

  v5 = (unsigned __int16 *)qword_18014B6E8;
  if ( qword_18014B6E8 )
  {
    UserData->Ptr = qword_18014B6E8;
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
  return EventWriteTransfer(LOG_PROVIDER_HEALTH_Context, a2, 0, 0, 2u, UserData);
}

```

## disassembly

```asm
0x18003b130  sub     rsp, 38h
0x18003b134  mov     rcx, cs:qword_18014B6E8
0x18003b13b  mov     r9d, 2
0x18003b141  mov     rax, [rsp+38h+arg_20]
0x18003b146  test    rcx, rcx
0x18003b149  jnz     short loc_18003B153
0x18003b14b  mov     [rax], rcx
0x18003b14e  xor     r8d, r8d
0x18003b151  jmp     short loc_18003B15C
0x18003b153  mov     [rax], rcx
0x18003b156  mov     r8d, r9d
0x18003b159  movzx   ecx, word ptr [rcx]
0x18003b15c  mov     [rax+8], ecx
0x18003b15f  mov     [rax+0Ch], r8d
0x18003b163  xor     r8d, r8d; ActivityId
0x18003b166  mov     rcx, cs:LOG_PROVIDER_HEALTH_Context; RegHandle
0x18003b16d  mov     [rsp+38h+UserData], rax; UserData
0x18003b172  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18003b177  xor     r9d, r9d; RelatedActivityId
0x18003b17a  call    cs:__imp_EventWriteTransfer
0x18003b180  add     rsp, 38h
0x18003b184  retn
```
