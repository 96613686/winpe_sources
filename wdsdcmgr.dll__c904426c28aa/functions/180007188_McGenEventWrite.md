# McGenEventWrite

- ea: `0x180007188`
- end: `0x1800071dc`
- name: `McGenEventWrite`
- size: `84`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800070a4`
- `0x1800071e4`
- `0x180014404`

## callees

- `0x180007188`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x1800071d1`
- `ADVAPI32!EventWriteTransfer` at `0x1800071d1`

## pseudocode

```c
ULONG __fastcall McGenEventWrite(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // r8
  int v6; // eax
  ULONG v7; // r8d

  v5 = (unsigned __int16 *)qword_18001D018;
  v6 = 0;
  if ( qword_18001D018 )
  {
    UserData->Ptr = qword_18001D018;
    v6 = 2;
    v7 = *v5;
  }
  else
  {
    UserData->Ptr = 0;
    v7 = 0;
  }
  UserData->Size = v7;
  UserData->Reserved = v6;
  return EventWriteTransfer(
           MICROSOFT_WINDOWS_DEPLOYMENT_SERVICES_DIAGNOSTICS_Context,
           a2,
           0,
           0,
           UserDataCount,
           UserData);
}

```

## disassembly

```asm
0x180007188  sub     rsp, 38h
0x18000718c  mov     r8, cs:qword_18001D018
0x180007193  xor     eax, eax
0x180007195  mov     rcx, [rsp+38h+arg_20]
0x18000719a  test    r8, r8
0x18000719d  jnz     short loc_1800071A7
0x18000719f  mov     [rcx], rax
0x1800071a2  mov     r8d, eax
0x1800071a5  jmp     short loc_1800071B3
0x1800071a7  mov     [rcx], r8
0x1800071aa  mov     eax, 2
0x1800071af  movzx   r8d, word ptr [r8]
0x1800071b3  mov     [rcx+8], r8d
0x1800071b7  xor     r8d, r8d; ActivityId
0x1800071ba  mov     [rsp+38h+UserData], rcx; UserData
0x1800071bf  mov     [rcx+0Ch], eax
0x1800071c2  mov     rcx, cs:MICROSOFT_WINDOWS_DEPLOYMENT_SERVICES_DIAGNOSTICS_Context; RegHandle
0x1800071c9  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1800071ce  xor     r9d, r9d; RelatedActivityId
0x1800071d1  call    cs:__imp_EventWriteTransfer
0x1800071d7  add     rsp, 38h
0x1800071db  retn
```
