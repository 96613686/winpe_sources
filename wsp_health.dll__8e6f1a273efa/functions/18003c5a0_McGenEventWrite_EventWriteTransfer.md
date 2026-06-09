# McGenEventWrite_EventWriteTransfer

- ea: `0x18003c5a0`
- end: `0x18003c5fc`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `92`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18003c604`

## callees

- `0x18003c5a0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18003c5ea`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18003c5ea`

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

  v5 = (unsigned __int16 *)qword_18014D6E8;
  if ( qword_18014D6E8 )
  {
    UserData->Ptr = qword_18014D6E8;
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
0x18003c5a0  sub     rsp, 38h
0x18003c5a4  mov     rcx, cs:qword_18014D6E8
0x18003c5ab  mov     r9d, 2
0x18003c5b1  mov     rax, [rsp+38h+arg_20]
0x18003c5b6  test    rcx, rcx
0x18003c5b9  jnz     short loc_18003C5C3
0x18003c5bb  mov     [rax], rcx
0x18003c5be  xor     r8d, r8d
0x18003c5c1  jmp     short loc_18003C5CC
0x18003c5c3  mov     [rax], rcx
0x18003c5c6  mov     r8d, r9d
0x18003c5c9  movzx   ecx, word ptr [rcx]
0x18003c5cc  mov     [rax+8], ecx
0x18003c5cf  mov     [rax+0Ch], r8d
0x18003c5d3  xor     r8d, r8d; ActivityId
0x18003c5d6  mov     rcx, cs:LOG_PROVIDER_HEALTH_Context; RegHandle
0x18003c5dd  mov     [rsp+38h+UserData], rax; UserData
0x18003c5e2  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18003c5e7  xor     r9d, r9d; RelatedActivityId
0x18003c5ea  call    cs:__imp_EventWriteTransfer
0x18003c5f1  nop     dword ptr [rax+rax+00h]
0x18003c5f6  add     rsp, 38h
0x18003c5fa  retn
```
