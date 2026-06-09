# McGenEventWrite_EventWriteTransfer

- ea: `0x180007124`
- end: `0x18000717d`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `89`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000755c`

## callees

- `0x180007124`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000716b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000716b`

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

  v5 = (unsigned __int16 *)qword_18001D128;
  if ( qword_18001D128 )
  {
    UserData->Ptr = qword_18001D128;
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
  return EventWriteTransfer(winsrvext_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180007124  sub     rsp, 38h
0x180007128  mov     rcx, cs:qword_18001D128
0x18000712f  mov     rax, [rsp+38h+arg_20]
0x180007134  test    rcx, rcx
0x180007137  jnz     short loc_180007141
0x180007139  mov     [rax], rcx
0x18000713c  xor     r8d, r8d
0x18000713f  jmp     short loc_18000714D
0x180007141  mov     [rax], rcx
0x180007144  mov     r8d, 2
0x18000714a  movzx   ecx, word ptr [rcx]
0x18000714d  mov     [rax+8], ecx
0x180007150  mov     [rax+0Ch], r8d
0x180007154  xor     r8d, r8d; ActivityId
0x180007157  mov     rcx, cs:winsrvext_Context; RegHandle
0x18000715e  mov     [rsp+38h+UserData], rax; UserData
0x180007163  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180007168  xor     r9d, r9d; RelatedActivityId
0x18000716b  call    cs:__imp_EventWriteTransfer
0x180007172  nop     dword ptr [rax+rax+00h]
0x180007177  add     rsp, 38h
0x18000717b  retn
```
