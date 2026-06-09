# McGenEventWrite_EventWriteTransfer

- ea: `0x180070160`
- end: `0x1800701bc`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `92`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800701c4`

## callees

- `0x180070160`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800701aa`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800701aa`

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

  v5 = (unsigned __int16 *)qword_180179388;
  if ( qword_180179388 )
  {
    UserData->Ptr = qword_180179388;
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
  return EventWriteTransfer(LOG_PROVIDER_FS_Context, a2, 0, 0, 2u, UserData);
}

```

## disassembly

```asm
0x180070160  sub     rsp, 38h
0x180070164  mov     rcx, cs:qword_180179388
0x18007016b  mov     r9d, 2
0x180070171  mov     rax, [rsp+38h+arg_20]
0x180070176  test    rcx, rcx
0x180070179  jnz     short loc_180070183
0x18007017b  mov     [rax], rcx
0x18007017e  xor     r8d, r8d
0x180070181  jmp     short loc_18007018C
0x180070183  mov     [rax], rcx
0x180070186  mov     r8d, r9d
0x180070189  movzx   ecx, word ptr [rcx]
0x18007018c  mov     [rax+8], ecx
0x18007018f  mov     [rax+0Ch], r8d
0x180070193  xor     r8d, r8d; ActivityId
0x180070196  mov     rcx, cs:LOG_PROVIDER_FS_Context; RegHandle
0x18007019d  mov     [rsp+38h+UserData], rax; UserData
0x1800701a2  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1800701a7  xor     r9d, r9d; RelatedActivityId
0x1800701aa  call    cs:__imp_EventWriteTransfer
0x1800701b1  nop     dword ptr [rax+rax+00h]
0x1800701b6  add     rsp, 38h
0x1800701ba  retn
```
